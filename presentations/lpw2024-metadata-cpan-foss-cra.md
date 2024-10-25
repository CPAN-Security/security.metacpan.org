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

* Cyber Resilience Act is arriving in the next weeks
* 1st law to affect Open Source projects substantially


Note:


[comment]: # (!!!)

## (I am not a lawyer)


[comment]: # (!!!)

## EU Cyber Resilience Act

* Approved by the EU Parliament Mar 12th 2024
* Adopted by the EU Commission on Oct 10th 2024
* Published in the official EU Journal [soon]
* **Takes effect 36 months after publication** – ̃Q4 2027

<div style="font-size: large;">

> * [Council adoption](https://www.consilium.europa.eu/en/press/press-releases/2024/10/10/cyber-resilience-act-council-adopts-new-law-on-security-requirements-for-digital-products/) – 2024-10-10

</div>

Note:


[comment]: # (!!!)

## CRA Applies to...

* All Manufacturers that wish to place "Products with Digital Elements" on the EU market. ([Recital 9](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=10))

* Connected devices
* Remote data processing solutions
* Non-tangible digital products
* Related systems and services needed for operation

<div style="font-size: large;">

> * Product with Digital Elements: [Article 3 (1), (4), (6), (7)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=136)
> * Placing on the market: [Article 3 (21)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=140)

</div>

Note:

Devices, components, routers, toys, etc. Anything which has software may be affected!


[comment]: # (!!!)

## CRA does not apply to...

* Software that is part of a service  ([Recital 12](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=13))
* Though NIS2 applies if the service is considered part of critical infrastructure


[comment]: # (!!!)

## Six "Roles"

* Manufacturer
* Distributor, Importer and Market Authorities
* Open Source Software Steward
* Open Source Developers

[comment]: # (!!! data-auto-animate)

## Six "Roles"

* Manufacturer 🔍
* Distributor, Importer and Market Authorities
* Open Source Software Steward
* Open Source Developers

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

* Place a CE mark on their products

<div style="font-size: large;">

> * [Article 28](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=218)

</div>

[comment]: # (|||)

### Obligations of Manufacturers – Support period

* Determine the product support period
    * Default is 5 years, but should reflect expected use time
    * Support period can also set by authorities
* Security fixes must remain available for 10 years after issuing

<div style="font-size: large;">

> * [Article 13 (8)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=165)
> * [Article 13 (9)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=166)

</div>

[comment]: # (|||)

### Obligations of Manufacturers – Point of Contact

* Set up a single point of contact ([Annex II.2](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=303))


[comment]: # (|||)

### Obligations of Manufacturers — Unique ID

* Create a unique identification of their product

<div style="font-size: large;">

> * [Annex II (3)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=303)

</div>

[comment]: # (|||)

### Obligations of Manufacturers – Build & Dependencies

* Be able to identify and document vulnerabilities and components contained in products
* Describe how the product is put together

<div style="font-size: large;">

> * [Annex I, Part II (1)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=297)
> * [Annex VII.2 (a)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=314)

</div>

[comment]: # (|||)

### Obligations of Manufacturers – Produce SBOMs

* Produce SBOMs upon request by regulators
    * At minimum, top level dependencies

<div style="font-size: large;">

> * [Recital 22](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=26)
> * [Annex I, Part II (1)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=300)

</div>

[comment]: # (|||)

### Obligations of Manufacturers – No Vulnerabilities

* Product has **no known vulnerabilities** in their products
* Product is **secure by default**
* 😍 Exercise due diligence when integrating third party components to avoid they compromise security
* Report vulnerabilities to the Manufacturer or Open Source maintainer

<div style="font-size: large;">

> * [Article 13.1](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=161)
> * [Annex I, Part I (2 (a))](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=297)
> * [Recital 65](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=73)
> * [Article 13.5](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=163)
> * [Article 13.6](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=164)

</div>

[comment]: # (|||)

### Obligations of Manufacturers – Offer timely security updates

* Make security updates available to customers effectively for the duration of the support period
* Ensure vulnerabilities can be addressed through security updates, in a timely manner

<div style="font-size: large;">

> * [Article 13.8](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=165)
> * [Annex I part II](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=300)
> * [Annex I, Part I (2 (c))](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=297)
>    * [Annex I, Part II (7)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=302)

</div>

[comment]: # (|||)

### Obligations of Manufacturers – Early warning system

* Take part in the EU early warning notification regime
    * Submit early warning within 24h after exploit discovery
    * Submit vulnerability notification within 72h, incl. corrective measures
    * Submit a final report no later than a month after discovery
* Incident reports must be submitted to a common EU reporting platform

<div style="font-size: large;">

> * [Article 13.6](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=164)
> * [Article 14.1](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=176)
> * [Article 14.2 (a)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=177)
> * [Article 14.2 (b)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=177)
> * [Article 14.2 (c)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=178)

</div>

[comment]: # (|||)

## Six "Roles"

* Manufacturer ✅
* Distributor, Importer and Market Authorities
* Open Source Software Steward
* Open Source Developers


[comment]: # (!!! data-auto-animate)

## Six "Roles"

* Manufacturer ✅
* Distributor, Importer and Market Authorities ❌
* Open Source Software Steward
* Open Source Developers


[comment]: # (!!! data-auto-animate)

## Six "Roles"

* Manufacturer ✅
* Distributor, Importer and Market Authorities ❌
* Open Source Software Steward ❌
* Open Source Developers


[comment]: # (!!! data-auto-animate)

## Six "Roles"

* Manufacturer ✅
* Distributor, Importer and Market Authorities ❌
* Open Source Software Steward ❌
* Open Source Developers 🔍


[comment]: # (||| data-auto-animate)

## Open Source Developers

* CRA doesn't really talk about Open Source **Developers**


[comment]: # (|||)

### Obligations to Open Source Developers – Status Quo

* CRA **does not apply** to Developers if...
    * they contribute code to projects they are **not responsible for**
    * they are **not monetising** their product
    * their product is ultimately **not intended for commercial activities**

<div style="font-size: large;">

> * [Recital (18)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=20))
> * [Recital (19)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=22))

</div>

[comment]: # (|||)

### Obligations to Open Source Developers – With a FOSS Steward

* CRA **applies voluntarily** if the Developer decides...
    * their product **is ultimately intended** for commercial activities

<div style="font-size: large;">

> * [Recital (19)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=22)

</div>


[comment]: # (|||)

## Six "Roles"

* Manufacturer ✅
* Distributor, Importer and Market Authorities ❌
* Open Source Software Steward ❌
* Open Source Developers ✅


[comment]: # (!!! data-auto-animate)

## Now what?


[comment]: # (||| data-auto-animate)

## Metadata

* The "Minimum Elements" or "Baseline Attributes" are required
* Additionally attributes are needed to achieve the purpose



[comment]: # (|||)



| Attribute name                      | Required | References                                 |
| :---------------------------------- | :------: | -----------------------------------------: |
| Primary Component Name              | Yes      | NTIA-SBOM, CISA-2024-9, CRA-AV             |
| Unique Product Identifier           | Yes      | CRA-AII(3), CRA-AV, NTIA-SBOM, CISA-2024-9 |
| Version                             | Yes      | CISA-2024-9, CRA-AV                        |
| Purpose, Intended Use               | Yes      | CRA-AII(4)                                 |
| Supplier Name                       | Yes      | CRA-AII(1), CRA-AV, NTIA-SBOM, CISA-2024-9 |
| Security contact                    | Yes      | CRA-AII(2)                                 |


[comment]: # (|||)



| Attribute name                      | Required | References                                 |
| :---------------------------------- | :------: | -----------------------------------------: |
| Dependencies                        | Yes      | CRA-AII(5), NTIA-SBOM, CISA-2024-9         |
| Relationships                       | Yes      | CISA-2024-9                                |
| Cryptographic Hash                  | Yes      | CISA-2024-9                                |
| Copyright Notice                    | Yes      | CISA-2024-9                                |
| License(s)                          | Yes      | CISA-2024-9                                |
| Download location                   | No       |                                            |
| Code Commit Revision                | No       |                                            |
| Code Repository                     | No       |                                            |


[comment]: # (|||)



| Attribute name                      | Required | References                                 |
| :---------------------------------- | :------: | -----------------------------------------: |
| SBOM Author                         | Yes      | NTIA-SBOM, CISA-2024-9                     |
| SBOM Creation Time-stamp            | Yes      | NTIA-SBOM, CISA-2024-9                     |
| SBOM Format                         | Yes      | CycloneDX 1.6, SPDX 2.3                    |
| SBOM Release                        | Yes      | CycloneDX 1.6, SPDX 2.3                    |
| SBOM Serial Number                  | Yes      | CycloneDX 1.6  SPDX 2.3                    |
| SBOM Generation Tool                | No       |                                            |
| SBOM Location                       | No       | CRA-AII(9)                                 |
| SBOM Type                           | No       | CISA-2023, CISA-2024-9                     |



[comment]: # (|||)


| Attribute name                      | Required | References                                 |
| :---------------------------------- | :------: | -----------------------------------------: |
| Intended for Commercial Use         | No       | CRA-Rec-15, CRA-Rec-18                     |
| Open Source Software Steward        | No       | CRA-Rec-19                                 |
| Security Attestation                | No       | CRA-Rec-21                                 |



[comment]: # (|||)


| Attribute name                      | Required | References                                 |
| :---------------------------------- | :------: | -----------------------------------------: |
| CE Conformity Assessment Body       | No       | CRA-Art-47(1), CRA-AV                      |
| CE Declaration of Conformity        | No       | CRA-AII(6), CRA-AV                         |
| CE Support End Date                 | No       | CRA-AII(7)                                 |
| CE Technical Documentation          | No       | CRA-AII(8)                                 |




[comment]: # (|||)



[comment]: # (|||)



[comment]: # (!!!)

## Further work in CPANSec

* Let's coordinate on #cpan-security on irc.perl.org! 😍


[comment]: # (!!!)

# Thanks!

Salve J. Nilsen

@sjn\@chaos.social

🦆🦆🦆
