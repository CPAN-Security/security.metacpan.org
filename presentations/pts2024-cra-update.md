[comment]: # (Compile this presentation with the command below)
[comment]: # (mdslides pts2024-sbom-intro.md --include ../media)
[comment]: # (...or by running the Makefile with "make")
[comment]: # (mdslides can be installed from https://github.com/dadoomer/markdown-slides/)
[comment]: # (diagram was made on https://dreampuf.github.io/GraphvizOnline/ using media/CPAN-deps-1.dot as input)

[comment]: # (THEME = solarized)

[comment]: # (minScale: 0.2)
[comment]: # (maxScale: 4.0)
[comment]: # (controls: true)
[comment]: # (width: "960")
[comment]: # (height: "700")
[comment]: # (help: true)
[comment]: # (progress: true)
[comment]: # (controlsBackArrows: "true")


## Cyber Resilience Act, SBOMs and CPAN

PTS 2024

Salve J. Nilsen

Mastodon: @sjn\@chaos.social

Note:

* Presentation from 2023 is still _mostly correct_ (80-90%), and many of the concerns and worries laid out there are **still relevant**


* A new role was specified in December 2023 – the Open Source Software **Steward**
* The purpose of this role is to help FOSS communities become an active part in the new security landscape without having to worry about the liability risks

| Author | Steward | Manufacturer | Importer | Distributor |


- Unescapable new **legislative requirements**
- Get an end-to-end correct and up-to-date provenance
- Reduce false positives in security tooling


[comment]: # (!!!)

## Our mission

* There are substantial changes to the landscape – Our maps need updating!
* Let's pretend we're **scouts on a fact-finding mission**

* Focus – questions, facts, references
    * otherwise – we state our confidence (0-100%)

Note:

Inspiration from Julia Galef's "The Scout Mindset" book (2021)


[comment]: # (!!!)

## EU Cyber Resilience Act

* Law was approved by the EU Parliament March 12th 2024
* Final translations/fixes ongoing
* Law is adopted when EU Council gives final approval
* Three year implementation period
* Law takes effect in Q2 2027

<div style="font-size: large;">

> * Parliament resolution [T9-0130/2024](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.html)

</div>

Note:

Law is expected to be approved by the Council in April 2024!


[comment]: # (!!!)

## CRA Applies to...

* All Manufacturers that wish to place "Products with Digital Elements" on the EU market.

<div style="font-size: large;">

> * Product with Digital Elements: [Article 3 (1), (4), (6), (7)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=136)
> * Placing on the market: [Article 3 (21)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=140)

</div>

Note:

Devices, components, routers, toys, etc. Anything which has software may be affected!


[comment]: # (!!!)

## Five "Roles"

* Manufacturer
* Distributor (not relevant)
* Importer (not relevant)
* Open-Source Software Steward (NEW!)
* Open-Source Developers & Contributors

[comment]: # (!!! data-auto-animate)

## Five "Roles"

* Manufacturer 👈
* Distributor (not relevant)
* Importer (not relevant)
* Open-Source Software Steward (NEW!)
* Open-Source Developers & Contributors

[comment]: # (||| data-auto-animate)

## Manufacturer

* A natural or legal person who 
    * **develops** or manufactures products with digital elements
    * or **has products** with digital elements **designed**, developed or manufactured,
    * and **markets them under its name** or trademark,
    * whether for payment, monetisation or free of charge

<div style="font-size: large;">

> * [Article 3 (12), (13)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=138)

</div>

[comment]: # (|||)

### Obligations of Manufacturers – Conformance

![CE Mark](media/280px-Conformité_Européenne.png)

* Place a CE mark on their products ([Article 28](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=218))

<div style="font-size: large;">

> * Automating this (on MetaCPAN) may be an awesome way to help the sustainability of FOSS projects! (50%)

</div>

[comment]: # (|||)

### Obligations of Manufacturers – Support period

* Determine the product support period. Default is 10 years. ([Recital 118](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=120))
* Security fixes must remain available for 10 years afted publishing ([Article 13 point 9](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=167))

<div style="font-size: large;">

> * Period length may be different per product (40%)

</div>

[comment]: # (|||)

### Obligations of Manufacturers – Point of Contact

* Set up a single point of contact ([Annex II point 2](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=303))

<div style="font-size: large;">

> May require confirmation (60%)

</div>

[comment]: # (|||)

### Obligations of Manufacturers — Unique ID

* Create a unique identification of their product ([Annex II point 3](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=303))

<div style="font-size: large;">

> PackageURL can solve this! (85%)

</div>

[comment]: # (|||)

### Obligations of Manufacturers – Build & Dependencies

* Be able to identify and document vulnerabilities and components contained in products ([Annex I, Part II (1)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=297))
* Describe how the product is put together ([Annex VII point 2 (a)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=314))

<div style="font-size: large;">

> Match Unique ID to vulnerability databases (90%)

</div>

[comment]: # (|||)

### Obligations of Manufacturers – Produce SBOMs

* Produce SBOMs upon request by regulators ([Recital 22](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=26))
    * At minimum, top level dependencies ([Annex I, Part II (1)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=300))
* See also: The German Federal Office for Information Security's [Technical Guideline TR-03183](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/TechGuidelines/TR03183/BSI-TR-03183-2.pdf) version 1.1 (published 2023-11-28)

<div style="font-size: large;">

> * Requries ways to refer to both embedded and cross-ecosystem dependencies (95%)
> * Transitive dependencies are implied to be produced (70%)

</div>

[comment]: # (|||)

### Obligations of Manufacturers – No Vulnerabilities

* Product has **no known vulnerabilities** in their products ([Article 13 point 1](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=161); [Annex I, Part I (2 (a))](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=297))
* Product is **secure by default** ([Recital 65] https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=73))
* Exercise due diligence when integrating third party components to avoid they compromise security ([Article 13 point 5](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=163))
* Report vulnerabilities to the Manufacturer or Open Source maintainer ([Article 13 point 6](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=164))

<div style="font-size: large;">

> * Implies they have a complete picture of dependencies (95%)
> * Though the minimum is "top level dependencies" ([Annex I, Part II, (1)]())

</div>

[comment]: # (|||)

### Obligations of Manufacturers – Offer timely security updates

* Make security updates available to customers effectively for the duration of the support period ([Article 13 point 8](); [Annex I part II]())
* Ensure vulnerabilities can be addressed through security updates ([Annex I, Part I (2 (c))]())
    * In a timely manner ([Annex I, Part I (8)]())

<div style="font-size: large;">

> This means they must have updateable products! No more servers running RHEL6.

</div>

[comment]: # (|||)

### Obligations of Manufacturers – Early warning system

* Take part in the EU early warning notification regime for responding to actively exploited vulnerabilities ([Article 13 Point 6](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=164); [Article 14 point 1](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=176))
    * Submit early warning within 24h after exploit discovery ([Article 14 point 2 (a)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=177))
    * Submit vulnerability notification within 72h, including corrective measures ([Article 14 point 2 (b)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=177))
    * Submit a final report no later than 14 days after discovery ([Article 14 point 2 (c)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=178))
* Incident reports must be submitted to a common EU reporting platform


[comment]: # (|||)

## Five "Roles"

* Manufacturer ✅
* Distributor (not relevant)
* Importer (not relevant)
* Open-Source Software Steward (NEW!)
* Open-Source Developers & Contributors


[comment]: # (!!! data-auto-animate)

## Five "Roles"

* Manufacturer ✅
* Distributor (not relevant) ❌
* Importer (not relevant)
* Open-Source Software Steward (NEW!)
* Open-Source Developers & Contributors


[comment]: # (!!! data-auto-animate)

## Five "Roles"

* Manufacturer ✅
* Distributor (not relevant) ❌
* Importer (not relevant) ❌
* Open-Source Software Steward (NEW!)
* Open-Source Developers & Contributors


[comment]: # (!!! data-auto-animate)

## Five "Roles"

* Manufacturer ✅
* Distributor (not relevant) ❌
* Importer (not relevant) ❌
* Open-Source Software Steward (NEW!) 👈
* Open-Source Developers & Contributors


[comment]: # (||| data-auto-animate)

## Open Source Steward

* A legal person, but not natural person, who...
    * must be a non-profit ([Recital 15](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=17))
    * provides support for OSS projects that are intended for commercial activities ([Recital 18](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=20))
    * may provide voluntary security attestation ([Recital 21](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=25))


[comment]: # (|||)

### Obligations of Open Source Stewards – Community Policy

* Must create cybersecurity policy and documentation for it's community, that fosters...
    * Development of secure products ([Article 24 point 1](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=208))
    * Effective handling and information sharing around vulnerabilities ([Article 24 point 1](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=208))
    * Voluntary vulnerability reporting


[comment]: # (|||)

### Obligations of Open Source Stewards – Cooperation

* Must cooperate with market surveillance authorities in...
    * Mitigating risks ([Article 24 point 2](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=209))
    * Provide above documentation upon request ([Article 24 point 2](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=209))
    * Notify of exploited vulnerability discoveries ([Article 14 point 1](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=176))
    * Informing users of the impact of active exploited vulnerabilities or severe incidents ([Article 14 point 8](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=183))

<div style="font-size: 1em;">

> * The Steward's role seems to be about "adding value" for Manufacturers by offloading some of the due diligence tasks. This is valuable!

</div>

[comment]: # (|||)

### Obligations of Open Source Stewards II






[comment]: # (|||)

## Five "Roles"

* Manufacturer ✅
* Distributor (not relevant) ❌
* Importer (not relevant) ❌
* Open-Source Software Steward (NEW!) ✅
* Open-Source Developers & Contributors


[comment]: # (!!! data-auto-animate)

## Five "Roles"

* Manufacturer ✅
* Distributor (not relevant) ❌
* Importer (not relevant) ❌
* Open-Source Software Steward (NEW!) ✅
* Open-Source Developers & Contributors 👈



[comment]: # (||| data-auto-animate)

## Open Source Developers


Note:

SBOMs are for keeping track of important information across dependencies


[comment]: # (!!!)

![Example dependency tree](media/CPAN-deps-1.svg)


[comment]: # (!!!)

## Software Bill of Materials




## Software identification

* [PURL](https://github.com/package-url/purl-spec) – _Package URL_
    * [URI::PackageURL](https://metacpan.org/pod/URI::PackageURL) by GTD


```txt
pkg:cpan/SJN/Acme-Godot@0.1
```


[comment]: # (!!!)


## What can go into an SBOM?



[comment]: # (!!!)

## The Minimum Elements For a Software Bill of Materials (SBOM)

[Pursuant to Executive Order 14028 on Improving the Nation’s Cybersecurity](https://www.ntia.doc.gov/sites/default/files/publications/sbom_minimum_elements_report_0.pdf)

July 12, 2021


Note:

US Department of Commerce published a list of minimum required fields in an SBOM


[comment]: # (!!!)

| Data Field               | SBOM | CPAN |
| ------------------------ | ---- | ---- |
| Supplier Name            | yes  | yes  |
| Component Name           | yes  | yes  |
| Version of the Component | yes  | yes  |
| Other Unique Identifiers | yes  | no   |
| Dependency Relationship  | yes  | yes  |
| Author of SBOM Data      | yes  | no   |
| Time-stamp               | yes  | no   |



[comment]: # (!!! data-auto-animate)



[comment]: # (!!!)

# Thanks!

Salve J. Nilsen

Mastodon: @sjn\@chaos.social

🦆🦆🦆
