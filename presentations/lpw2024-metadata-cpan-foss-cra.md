[comment]: # (Compile this presentation with the command below)
[comment]: # (mdslides pts2024-sbom-intro.md --include ../media)
[comment]: # (...or by running the Makefile with "make")
[comment]: # (mdslides can be installed from https://github.com/dadoomer/markdown-slides/)

[comment]: # (THEME = solarized)

[comment]: # (minScale: 0.2)
[comment]: # (maxScale: 4.0)
[comment]: # (controls: true)
[comment]: # (width: "960")
[comment]: # (height: "700")
[comment]: # (help: true)
[comment]: # (progress: true)
[comment]: # (controlsBackArrows: "true")


## Metadata, CPAN, Supply Chains, and EU's Cyber Resilience Act

LPW 2024

Salve J. Nilsen

@sjn\@chaos.social

Note:


[comment]: # (!!!)

## New laws, new obligations

* Cyber Resilience Act is arriving soon!
* First law to affect Open Source projects substantially


Note:


[comment]: # (!!!)

## (I am not a lawyer)


[comment]: # (!!!)

## EU Cyber Resilience Act

* Approved by the EU Parliament March 12th 2024
* Adopted by the EU Commission on October 12th 2024 
* Final publication expected by 
* Three year implementation period
* **CRA expexted to take effect in Q2 2027**

<div style="font-size: large;">

> * Parliament resolution [T9-0130/2024](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.html)

</div>

Note:

Approved 6 weeks ago
Law is expected to be approved by the Council in April 2024!


[comment]: # (!!!)

## CRA Applies to...

* All Manufacturers that wish to place "Products with Digital Elements" on the EU market. ([Recital 9](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=10))

* Connected devices
* Remote data processing solutions
* Non-tangible digital products

<div style="font-size: large;">

> * Product with Digital Elements: [Article 3 (1), (4), (6), (7)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=136)
> * Placing on the market: [Article 3 (21)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=140)

</div>

Note:

Devices, components, routers, toys, etc. Anything which has software may be affected!


[comment]: # (!!!)

## CRA does not apply to...

* Software that is part of a service  ([Recital 12](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=13))
* Though NIS2 applies if the services is considered critical infrastructure (70%)


[comment]: # (!!!)

## Five "Roles"

* Manufacturer
* Distributor
* Importer
* Open-Source Software Steward
* Open-Source Developers

[comment]: # (!!! data-auto-animate)

## Five "Roles"

* Manufacturer 🔍
* Distributor
* Importer
* Open-Source Software Steward
* Open-Source Developers

[comment]: # (||| data-auto-animate)

## Manufacturer

* A natural or legal person who 
    * **develops** or manufactures **products with digital elements**
    * or **has products with digital elements** designed, **developed** or manufactured,
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

* Determine the product support period.
    * Default is 5 years, but should reflect expected use time. ([Article 13.8](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=165))
    * Support period can also set by authorities if deemed inadequate, or for certain categories.
* Security fixes must remain available for 10 years after publishing ([Article 13.9](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=167))

<div style="font-size: large;">

> * Period length may be different per product (40%)

</div>

[comment]: # (|||)

### Obligations of Manufacturers – Point of Contact

* Set up a single point of contact ([Annex II.2](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=303))

<div style="font-size: large;">

> May require confirmation (60%)

</div>

[comment]: # (|||)

### Obligations of Manufacturers — Unique ID

* Create a unique identification of their product ([Annex II.3](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=303))

<div style="font-size: large;">

> PackageURL can solve this! (85%)

</div>

[comment]: # (|||)

### Obligations of Manufacturers – Build & Dependencies

* Be able to identify and document vulnerabilities and components contained in products ([Annex I, Part II (1)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=297))
* Describe how the product is put together ([Annex VII.2 (a)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=314))

<div style="font-size: large;">

> Match Unique ID to vulnerability databases (90%)

</div>

[comment]: # (|||)

### Obligations of Manufacturers – Produce SBOMs

* Produce SBOMs upon request by regulators ([Recital 22](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=26))
    * At minimum, top level dependencies ([Annex I, Part II (1)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=300))
* See also: The German Federal Office for Information Security's [Technical Guideline TR-03183](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/TechGuidelines/TR03183/BSI-TR-03183-2.pdf) version 1.1 (published 2023-11-28)

<div style="font-size: large;">

> * Requires ways to refer to both embedded and cross-ecosystem dependencies (95%)
> * Transitive dependencies are implied to be produced (70%)

</div>

[comment]: # (|||)

### Obligations of Manufacturers – No Vulnerabilities

* Product has **no known vulnerabilities** in their products ([Article 13.1](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=161); [Annex I, Part I (2 (a))](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=297))
* Product is **secure by default** ([Recital 65](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=73))
* 😍 Exercise due diligence when integrating third party components to avoid they compromise security ([Article 13.5](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=163))
* Report vulnerabilities to the Manufacturer or Open Source maintainer ([Article 13.6](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=164))

<div style="font-size: large;">

> * Implies they have a complete picture of dependencies (95%)
> * Though the minimum is "top level dependencies" ([Annex I, Part II, (1)]())

</div>

[comment]: # (|||)

### Obligations of Manufacturers – Offer timely security updates

* Make security updates available to customers effectively for the duration of the support period ([Article 13.8](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=165); [Annex I part II](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=300))
* Ensure vulnerabilities can be addressed through security updates ([Annex I, Part I (2 (c))](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=))
    * In a timely manner ([Annex I, Part II (7)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=302))


[comment]: # (|||)

### Obligations of Manufacturers – Early warning system

* Take part in the EU early warning notification regime ([Article 13.6](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=164); [Article 14.1](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=176))
    * Submit early warning within 24h after exploit discovery ([Article 14.2 (a)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=177))
    * Submit vulnerability notification within 72h, incl. corrective measures ([Article 14.2 (b)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=177))
    * Submit a final report no later than 14 days after discovery ([Article 14.2 (c)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=178))
* Incident reports must be submitted to a common EU reporting platform


[comment]: # (|||)

## Five "Roles"

* Manufacturer ✅
* Distributor
* Importer
* Open-Source Software Steward
* Open-Source Developers


[comment]: # (!!! data-auto-animate)

## Five "Roles"

* Manufacturer ✅
* Distributor ❌
* Importer
* Open-Source Software Steward
* Open-Source Developers


[comment]: # (!!! data-auto-animate)

## Five "Roles"

* Manufacturer ✅
* Distributor ❌
* Importer ❌
* Open-Source Software Steward
* Open-Source Developers


[comment]: # (!!! data-auto-animate)

## Five "Roles"

* Manufacturer ✅
* Distributor ❌
* Importer ❌
* Open-Source Software Steward 🔍
* Open-Source Developers


[comment]: # (||| data-auto-animate)

## Open Source Steward

* A legal person, but not natural person, who...
    * must be a non-profit ([Recital 15](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=17))
    * provides support for OSS projects that are intended for commercial activities ([Recital 18](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=20))
    * may provide voluntary security attestation ([Recital 21](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=25))


[comment]: # (|||)

### Obligations of Open Source Stewards – Community Policy

* Must create cybersecurity policy and documentation for it's community, that fosters...
    * Development of secure products ([Article 24.1](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=208))
    * Effective handling and information sharing around vulnerabilities ([Article 24.1](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=208))
    * Voluntary vulnerability reporting ([Article 15](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=185))


[comment]: # (|||)

### Obligations of Open Source Stewards – Cooperation

* Must cooperate with market surveillance authorities in... ([Article 24.2](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=209))
    * Mitigating risks
    * Provide above documentation upon request
    * Notify of exploited vulnerability discoveries ([Article 14.1](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=176))
    * Informing users of the impact of active exploited vulnerabilities or severe incidents ([Article 14.8](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=183))

<div style="font-size: large;">

> * Here, Stewards "add value" for Manufacturers by offloading some of the due diligence tasks. This is valuable!

</div>


[comment]: # (|||)

### Obligations of Open Source Stewards – Security Attestation

* 😍 Facilitate Manufacturer's due diligence as laid out in [Article 13.5](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=163) ([Article 25](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=210))
* EU Commision is tasked to set up a security attestation programme to facilitate this ([Recital 21](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=25))

<div style="font-size: large;">

> * Stewards "add value" for Manufacturers by providing a Security Attestation via. This is valuable!

</div>


[comment]: # (|||)

## Five "Roles"

* Manufacturer ✅
* Distributor ❌
* Importer ❌
* Open-Source Software Steward ✅
* Open-Source Developers


[comment]: # (!!! data-auto-animate)

## Five "Roles"

* Manufacturer ✅
* Distributor ❌
* Importer ❌
* Open-Source Software Steward ✅
* Open-Source Developers 🔍


[comment]: # (||| data-auto-animate)

## Open Source Developers

* CRA doesn't really talk about Open Source **Developers**


[comment]: # (|||)

### Obligations to Open Source Developers – Status Quo

* CRA **does not apply** to Developers if...
    * they contribute code to projects they are **not responsible for** ([Recital (18)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=20))
    * they are **not monetising** their product ([Recital (18)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=20))
    * their product **is not ultimately** intended for commercial activities ([Recital (19)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=22))


[comment]: # (|||)

### Obligations to Open Source Developers – With a FOSS Steward

* CRA **applies voluntarily** if the Developer decides...
    * their product **is ultimately intended** for commercial activities ([Recital (19)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=22))


A Open Source Software Steward to assist them in improving their product's security posture.


[comment]: # (|||)

## Five "Roles"

* Manufacturer ✅
* Distributor ❌
* Importer ❌
* Open-Source Software Steward ✅
* Open-Source Developers ✅


[comment]: # (!!! data-auto-animate)

## Now what?


[comment]: # (||| data-auto-animate)

## Now what?

* We can help our users comply with EU Law!


[comment]: # (||| data-auto-animate)

## Metadata

* Update CPAN::Meta::Spec
    * Add CRA compliance fields
    * Add project sustainability fields
    * Who would like to make this happen? ✋


[comment]: # (|||)

## SBOM

* Support Software Bill of Materials in the toolchain
    * PackageURL for helping with out-of-ecosystem dependencies and requirements
    * SBOM-aware PAUSE
    * SBOM discovery API on MetaCPAN
    * Who would like to make this work? ✋


[comment]: # (|||)

## Documentation

* Create an overview of roles, metadata, responsibilities and terminology
    * Who needs the metadata required by CRA?
    * Where does it come from?
    * **LOTS done!**
    * See https://security.metacpan.org/docs/


[comment]: # (|||)

## CPANSec's supply-chain SBOM overview

Let's take a look!


[comment]: # (!!!)

## Further work in CPANSec

* Let's coordinate on #cpan-security on irc.perl.org! 😍


[comment]: # (!!!)

# Thanks!

Salve J. Nilsen

@sjn\@chaos.social

🦆🦆🦆
