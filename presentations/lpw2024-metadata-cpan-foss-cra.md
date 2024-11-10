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

* This talk is more about _the future_ of our community, than the present

[comment]: # (!!!)

## (I am not a lawyer)


[comment]: # (||| data-auto-animate)

## (I am not a lawyer)

* (Also, I am not an "authority")


[comment]: # (||| data-auto-animate)

## (I am not a lawyer)

* (Also, I am not an ~"authority"~)
* I'm a _volunteer_


[comment]: # (!!! data-auto-animate)

## EU Cyber Resilience Act

* Approved by the EU Parliament Mar 12th 2024
* Adopted by the EU Commission on **Oct 10th 2024**
* Published in the official EU Journal [soon]
* **Takes effect 36 months after publication**

<div style="font-size: large;">

> * [Council adoption](https://www.consilium.europa.eu/en/press/press-releases/2024/10/10/cyber-resilience-act-council-adopts-new-law-on-security-requirements-for-digital-products/) announcement – 2024-10-10

</div>

Note:

* Into full effect by the end of 2027
* This talk is to...
    * _help you_ prepare, and
    * for you to _help us_ prepare


[comment]: # (|||)

## What is the goal of the CRA?

* Increase the general Cybersecurity across Europe
* To ensure they are safe before placement on the market

Note:

* Details in the upcoming slides


[comment]: # (|||)

## CRA Applies to...

* All Manufacturers that wish to place "Products with Digital Elements" on the EU market.
  * Connected devices
  * Remote data processing solutions
  * Non-tangible digital products
  * _Related systems and services needed for operation_

<div style="font-size: large;">

> * Background: [Recital 9](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=10)
> * Product with Digital Elements: [Article 3 (1), (4), (6), (7)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=136)
> * Placing on the market: [Article 3 (21)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=140)

</div>

Note:

* Devices, components
* routers, cameras, fridges, toys, etc.
* Anything which has software may be affected!


[comment]: # (|||)

## CRA **does not** apply to...

* Software that is purely _part of a service_
* Software that is covered by other regulation (NIS2, AI Act, Health regulations, etc.)
* Software that is Open Source*

<div style="font-size: large;">

> * [Recital 12](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=13)
> * [Recital 18](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=21)

</div>

[comment]: # (!!!)

## Six "Roles"

* Manufacturer
* Distributor, Importer and Market Authorities
* Open Source Software Steward
* Open Source Developers


[comment]: # (||| data-auto-animate)

## Six "Roles"

* Manufacturer
* Distributor, Importer and Market Authorities ❌
* Open Source Software Steward ❌
* Open Source Developers


[comment]: # (||| data-auto-animate)

## Six "Roles"

* Manufacturer 🔍
* Distributor, Importer and Market Authorities ❌
* Open Source Software Steward ❌
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

### Obligations of Manufacturers<br> — Conformance

![CE Mark](media/280px-Conformité_Européenne.png)

* Place a CE mark on their products

<div style="font-size: large;">

> * [Article 28](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=218)

</div>


Note:

* "I am following EU Law"


[comment]: # (|||)

### — Support period

* Determine the product support period
    * Default is 5 years, but should reflect expected use time
    * Support period can also set by authorities
* Security fixes must remain available for 10 years after issuing

<div style="font-size: large;">

> * [Article 13 (8)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=165)
> * [Article 13 (9)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=166)

</div>


[comment]: # (|||)

### — Point of Contact

* Set up a single point of contact


<div style="font-size: large;">

> * [Annex II.2](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=303)

</div>

[comment]: # (|||)

### — Unique ID

* Create a unique identification of their product

<div style="font-size: large;">

> * [Annex II (3)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=303)

</div>

[comment]: # (|||)

### — Build & Dependencies

* Be able to identify and document vulnerabilities and components contained in products
* Describe how the product is put together

<div style="font-size: large;">

> * [Annex I, Part II (1)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=297)
> * [Annex VII.2 (a)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=314)

</div>

[comment]: # (|||)

### — Produce SBOMs

* Produce SBOMs upon request by regulators
    * At minimum, top level dependencies

<div style="font-size: large;">

> * [Recital 22](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=26)
> * [Annex I, Part II (1)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=300)

</div>

[comment]: # (|||)

### — No Vulnerabilities

* Product has **no known vulnerabilities**
* Product is **secure by default**, and **secure by design**
* 😍 Exercise due diligence when integrating third party components
* 😍 Report vulnerabilities to the Manufacturer or Open Source maintainer

<div style="font-size: large;">

> * [Article 13.1](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=161)
> * [Annex I, Part I (2 (a))](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=297)
> * [Recital 65](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=73)
> * [Article 13.5](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=163)
> * [Article 13.6](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=164)

</div>

Note:

* Due diligence – to avoid these components compromise security

[comment]: # (|||)

### — Offer timely security updates

* Make security updates available to customers effectively for the duration of the support period
* Ensure vulnerabilities can be addressed through security updates

<div style="font-size: large;">

> * [Article 13.8](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=165)
> * [Annex I part II](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=300)
> * [Annex I, Part I (2 (c))](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=297)
> * [Annex I, Part II (7)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=302)

</div>


Note:

* Address vulnerabilities _in a timely manner_


[comment]: # (|||)

### — Early warning system

* Take part in the EU early warning notification regime
    * **Early warning within 24h** after exploit discovery
    * **Vulnerability notification within 72h**, incl. corrective measures
    * **Final report no later than a month after discovery**
* Incident reports submitted to a common EU reporting platform

<div style="font-size: large;">

> * [Article 13.6](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=164)
> * [Article 14.1](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=176)
> * [Article 14.2 (a)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=177)
> * [Article 14.2 (b)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=177)
> * [Article 14.2 (c)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=178)

</div>

[comment]: # (!!!)

## Six "Roles"

* Manufacturer 🔍
* Distributor, Importer and Market Authorities ❌
* Open Source Software Steward ❌
* Open Source Developers


[comment]: # (||| data-auto-animate)

## Six "Roles"

* Manufacturer ✅
* Distributor, Importer and Market Authorities ❌
* Open Source Software Steward ❌
* Open Source Developers 🔍


[comment]: # (||| data-auto-animate)

## Open Source Developers

* CRA doesn't really talk about Open Source **Developers**


[comment]: # (|||)

### Obligations to Open Source Developers<br> – Status Quo

* CRA **does not apply** to Developers if...
    * they contribute code to projects they are **not responsible for**
    * they are **not monetising** their product
    * their product is ultimately **not intended for commercial activities**

<div style="font-size: large;">

> * [Recital (18)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=20))
> * [Recital (19)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=22))

</div>


[comment]: # (|||)

### – With a FOSS Steward

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
* Open Source Developers 🔍


[comment]: # (||| data-auto-animate)

## Six "Roles"

* Manufacturer ✅
* Distributor, Importer and Market Authorities ❌
* Open Source Software Steward ❌
* Open Source Developers ✅


[comment]: # (!!! data-auto-animate)

## What Metadata is being asked for?


[comment]: # (||| data-auto-animate)

## Metadata

* Open Source ecosystems are _universal_
* Is there a "CPAN philosophy" regarding Metadata? 😅

"Optional, As Much as Possible"


Note:

* It makes sense to look at metadata requirements in general
    * Not just CRA's
* "Optional" isn't really an option any more
    * Some fields are actually _required_


[comment]: # (||| data-auto-animate)

## Metadata Headaches

* New requirements: "Minimum Elements" or "Baseline Attributes"
  * Some operate with multiple levels of "Requiredness"
  * Minimum, Recommended, Aspirational

<div style="font-size: large;">

> * (NTIA-SBOM) [NTIA Minimum Elements for a Software Bill of Materials (SBOM)](https://www.ntia.doc.gov/files/ntia/publications/sbom_minimum_elements_report.pdf#page=9), Published 2021-07-12
> * (CISA-2024-10) [CISA Framing Software Component Transparency: Establishing a Common Software Bill of Materials (SBOM)](https://www.cisa.gov/sites/default/files/2024-10/SBOM%20Framing%20Software%20Component%20Transparency%202024.pdf), Third edition, Section 2 and Appendix B; Published 2024-10-15

</div>


Note:

* "Required" attributes come in different forms
  * Keep in mind what the _purpose_ of the metadata is – not just it's "requiredness"


[comment]: # (||| data-auto-animate)

## Metadata Headaches

* No common glossary of terms
* Needed: a "Metadata Rosetta Stone"


Note:

* The current landscape is still a mess
  * Which means that well-considered constructive implementations can become a good example for others to consider


[comment]: # (|||)

### Component attributes

<div style="font-size: x-large;">

| Attribute name                      | Required | References                                 |
| :---------------------------------- | :------: | -----------------------------------------: |
| Primary Component Name              | Yes      | NTIA-SBOM, CISA-2024-10, CRA-AV, TR-03183  |
| **Version**  👈                     | Yes      | CISA-2024-10, CRA-AV, TR-03183             |
| Purpose, Intended Use               | Yes      | CRA-AII(4)                                 |
| Supplier Name                       | Yes      | CRA-AII(1), CRA-AV, NTIA-SBOM, CISA-2024-10, TR-03183 |
| Security contact                    | Yes      | CRA-AII(2)                                 |
| Copyright Notice                    | Yes      | CISA-2024-10                               |
| License(s)                          | Yes      | CISA-2024-10, TR-03183                     |

</div>

Note:

* Version:
    * Semantic Versions ("SemVer"), Calendar Versions ("CalVer")
    * On CPAN: Decimal Versions ("DeciVer").
* Reality: Arbitrary Versions formats have to be supported


[comment]: # (|||)

### Dependency Attributes

<div style="font-size: x-large;">

| Attribute name                      | Required | References                                 |
| :---------------------------------- | :------: | -----------------------------------------: |
| **Unique Product ID** 👈            | Yes      | CRA-AII(3), CRA-AV, NTIA-SBOM, CISA-2024-10 |
| Cryptographic Hash                  | Yes      | CISA-2024-10, TR-03183                     |
| Primary Component Filename          | Yes      | TR-03183                                   |
| Dependencies                        | Yes      | CRA-AII(5), NTIA-SBOM, CISA-2024-10, TR-03183 |
| **Relationships**          👈       | Yes      | CISA-2024-10                               |

</div>


Note:

* Unique ID: CPE (Common Platform Enumeration), Package URL, SWID, UUIDs, SWHID (Software Heritage ID), OmniBOR
    * Intrinsic vs. Extrinsic
    * Global uniqueness required
    * This is a mess, and very hard to solve. Best option for OSS today: Package URLs
* Relationships: If a dependency is static, remote, provided, or dynamic
   * "Primary", "Included in", "Heritage or Pedigree"
   * Relationship completeness


[comment]: # (|||)

### Other useful attributes

<div style="font-size: x-large;">

| Attribute name                      | Required | References                                 |
| :---------------------------------- | :------: | -----------------------------------------: |
| Download location                   | No       |                                            |
| Code Commit Revision                | No       |                                            |
| Code Repository                     | No       |                                            |

</div>


Note:

* What else is needed to make it easier to manage vulnerabilities?
    * A list of known vulnerabilities addressed
    * Details on which function/method had a vulnerability fixed
    * When & where the package was downloaded from


[comment]: # (|||)

### The SBOM Document Itself

<div style="font-size: x-large;">

| Attribute name                      | Required | References                                 |
| :---------------------------------- | :------: | -----------------------------------------: |
| SBOM Author                         | Yes      | NTIA-SBOM, CISA-2024-10, TR-03183          |
| SBOM Creation Time-stamp            | Yes      | NTIA-SBOM, CISA-2024-10, TR-03183          |
| SBOM Format                         | Yes      | CycloneDX 1.6, SPDX 2.3                    |
| SBOM Release                        | Yes      | CycloneDX 1.6, SPDX 2.3                    |
| SBOM Serial Number                  | Yes      | CycloneDX 1.6  SPDX 2.3                    |
| **SBOM Location**       👈          | Yes      | CRA-AII(9), TR-03183                       |
| SBOM Type                           | No       | CISA-2023-4, CISA-2024-10                  |
| SBOM Generation Tool                | No       |                                            |

</div>


Note:

* Location: Where to get the most recent SBOM
* Type: "When" in a Supply Chain an SBOM was created


[comment]: # (|||)

### Open Source Stewards

<div style="font-size: x-large;">

| Attribute name                      | Required | References                                 |
| :---------------------------------- | :------: | -----------------------------------------: |
| Intended for Commercial Use         | No       | CRA-Rec-15, CRA-Rec-18                     |
| Open Source Software Steward        | No       | CRA-Rec-19                                 |
| **Security Attestation**  👈        | No       | CRA-Rec-21                                 |

</div>


Note:

* Intended for Commercial Use + Attestations + OSS Steward = Possible funding source


[comment]: # (|||)

### Manufacturers

<div style="font-size: x-large;">

| Attribute name                      | Required | References                                 |
| :---------------------------------- | :------: | -----------------------------------------: |
| CE Conformity Assessment Body       | No       | CRA-Art-47(1), CRA-AV                      |
| CE Declaration of Conformity        | No       | CRA-AII(6), CRA-AV                         |
| CE Support End Date                 | No       | CRA-AII(7)                                 |
| CE Technical Documentation          | No       | CRA-AII(8)                                 |

</div>


Note:

* What's needed for components that are monetized?
  * Maintainer becomes a Manufacturer
  * This needs also to be supported


[comment]: # (|||)

## References


<div style="font-size: large;">

* (CISA-2023-4) [CISA Types of Software Bill of Materials (SBOM)](https://www.cisa.gov/resources-tools/resources/types-software-bill-materials-sbom), published 2023-04-21
* (CISA-2024-10) [CISA Framing Software Component Transparency: Establishing a Common Software Bill of Materials (SBOM)](https://www.cisa.gov/sites/default/files/2024-10/SBOM%20Framing%20Software%20Component%20Transparency%202024.pdf), Third edition, sections 2.2.1.4, 2.2.2 and Appendix B; Published 2024-10-15
* (CRA-AII) [Cyber Resilience Act, Annex II](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=303) Information and Instructions to the User, Dated 2024-03-12
* (CRA-AV) [Cyber Resilience Act, Annex V](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=311) EU Declaration of Conformity, Dated 2024-03-12
* (CRA-AVII) [Cyber Resilience Act, Annex VII](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=314) Contents of the Technical Documentation, Dated 2024-03-12
* (CRA-Art-47) [Cyber Resilience Act, Article 47](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=249) Operational obligations of notified bodies, Dated 2024-03-12
* (CRA-Rec-15) [Cyber Resilience Act, Recital 15](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=17) Economic operators, Dated 2024-03-12
* (CRA-Rec-18) [Cyber Resilience Act, Recital 18](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=20) Open Source Software Contributors, Dated 2024-03-12
* (CRA-Rec-19) [Cyber Resilience Act, Recital 19](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=22) Open Source Software Stewards, Dated 2024-03-12
* (CRA-Rec-21) [Cyber Resilience Act, Recital 21](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=25) Open Source Security Attestation, Dated 2024-03-12
* (TR-03183) German Technical Requirement [TR-03183 Cyber Resilience Requirements for Manufacturers and Products](https://bsi.bund.de/dok/TR-03183), Part 2: Software Bill of Materials (SBOM), Version 2.0.0, published 2024-09-20
* (NTIA-SBOM) [NTIA Minimum Elements for a Software Bill of Materials (SBOM)](https://www.ntia.doc.gov/files/ntia/publications/sbom_minimum_elements_report.pdf#page=9), Published 2021-07-12

</div>



[comment]: # (||| data-auto-animate)

## Metadata Headaches

* Lots of "opinions" from legislators & gov't orgs
* ⚠️  Inconsistencies in Terms
* ⚠️  Missing: More attributes needed to achieve security goals?


Note:

* This picture is likely to evolve in the coming years
* Ecosystems would do well to prepare a smooth evolution


[comment]: # (|||)

## Conclusions?

* It's a mess
* It's up to us to improve it
* ~"If it ain't broke, don't fix it"~
* Don't be a bystander


Note:

* "Permissionless Innovation"
* "Being a Good Open Source Citizen"
* We already know that being a bystander doesn't work – better to step up instead!


[comment]: # (!!!)

## Questions & Comments


[comment]: # (!!!)

## Join the work!

* Pick something you are passionate about
* Let's coordinate on #cpan-security on irc.perl.org! 😍
* [https://security.metacpan.org/](https://security.metacpan.org/)


[comment]: # (!!!)

# Thanks!

Salve J. Nilsen

@sjn\@chaos.social

🦆🦆🦆🦆
