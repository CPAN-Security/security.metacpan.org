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


## Where in the OSS Supply Chain do SBOM attributes come from?

FOSDEM 2025

Salve J. Nilsen

🐘 Mastodon — @sjn\@chaos.social



Note:


[comment]: # (!!!)

## 



Note:


[comment]: # (!!!)

## (I am not a lawyer)


[comment]: # (||| data-auto-animate)

## (I am not a ~lawyer~)

* (Also, I am not an "authority")


[comment]: # (||| data-auto-animate)

## (I am not a ~lawyer~)

* (Also, I am not an ~"authority"~)
* I'm a _volunteer_


[comment]: # (||| data-auto-animate)

## (I am not a ~lawyer~)

* (Also, I am not an ~"authority"~)
* I'm a _volunteer_


[comment]: # (!!! data-auto-animate)

## These findings are _preliminary_



[comment]: # (|||)

## 

Note:



[comment]: # (|||)

##

<div style="font-size: large;">


</div>

Note:



[comment]: # (!!! data-auto-animate)

## What Metadata is being asked for?


[comment]: # (||| data-auto-animate)

## Metadata "today"

* OSS components and ecosystems are _universal_
* Requirements are coming from "everywhere"
  * "Minimum Elements" or "Baseline Attributes"
  * "Minimum" – "Recommended" – "Aspirational"

<div style="font-size: large;">

> * (NTIA-SBOM) [NTIA Minimum Elements for a Software Bill of Materials (SBOM)](https://www.ntia.doc.gov/files/ntia/publications/sbom_minimum_elements_report.pdf#page=9), Published 2021-07-12
> * (CISA-2024-10) [CISA Framing Software Component Transparency: Establishing a Common Software Bill of Materials (SBOM)](https://www.cisa.gov/sites/default/files/2024-10/SBOM%20Framing%20Software%20Component%20Transparency%202024.pdf), Third edition, Section 2 and Appendix B; Published 2024-10-15

</div>


Note:

* It's necessary to look at metadata requirements in general
    * Not just from the CRA (Europe's)
* "Required" attributes come in different forms
    * Keep in mind what the _purpose_ of the metadata is – not just it's "requiredness"


[comment]: # (||| data-auto-animate)

## Metadata Headaches

* No common glossary of terms
    * Needed – a _Metadata Rosetta Stone_
* Not following existing "Best Practices"

> ~~As **much optional** as _possible_;<br> As **little required** as _necessary_.~~

Note:

* The current landscape is still a mess
    * Which means that well-considered constructive implementations can become a good example for others to consider


[comment]: # (|||)

### Component attributes

<div style="font-size: x-large;">

[CSCRF]:https://www.sebi.gov.in/legal/circulars/aug-2024/cybersecurity-and-cyber-resilience-framework-cscrf-for-sebi-regulated-entities-res-_85964.html 'Cybersecurity and Cyber Resilience Framework (CSCRF) for SEBI Regulated Entities (REs), (GV.SC.S5, page 89), Securities and Exchange Board of India'

| Attribute name                      | Required | References                                            |
| :---------------------------------- | :------: | ----------------------------------------------------: |
| Primary Component Name              | Yes      | NTIA-SBOM, CISA-2024-10, CRA-AV, TR-03183             |
| **Version**  👈                     | Yes      | CISA-2024-10, CRA-AV, TR-03183                        |
| Purpose, Intended Use               | Yes      | CRA-AII(4)                                            |
| **Supplier** Name  👈               | Yes      | CRA-AII(1), CRA-AV, NTIA-SBOM, CISA-2024-10, TR-03183 |
| Security contact                    | Yes      | CRA-AII(2)                                            |
| Copyright Notice                    | Yes      | CISA-2024-10                                          |
| License(s)                          | Yes      | CISA-2024-10, TR-03183, [CSCRF]                       |

</div>

Note:

* Version:
    * Semantic Versions ("SemVer"), Calendar Versions ("CalVer")
    * On CPAN: Decimal Versions ("DeciVer").
* Reality: Arbitrary Versions formats has to be supported


[comment]: # (|||)

### Dependency Attributes

<div style="font-size: x-large;">

[CSCRF]:https://www.sebi.gov.in/legal/circulars/aug-2024/cybersecurity-and-cyber-resilience-framework-cscrf-for-sebi-regulated-entities-res-_85964.html 'Cybersecurity and Cyber Resilience Framework (CSCRF) for SEBI Regulated Entities (REs), (GV.SC.S5, page 89), Securities and Exchange Board of India'

| Attribute name                      | Required | References                                             |
| :---------------------------------- | :------: | -----------------------------------------------------: |
| **Unique Product ID** 👈            | Yes      | CRA-AII(3), CRA-AV, NTIA-SBOM, CISA-2024-10            |
| Cryptographic Hash                  | Yes      | CISA-2024-10, TR-03183, [CSCRF]                        |
| Primary Component Filename          | Yes      | TR-03183                                               |
| Dependencies                        | Yes      | CRA-AII(5), NTIA-SBOM, CISA-2024-10, TR-03183, [CSCRF] |
| **Relationships**  👈               | Yes      | CISA-2024-10                                           |

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

### The SBOM Document Itself

<div style="font-size: x-large;">

| Attribute name                      | Required | References                                 |
| :---------------------------------- | :------: | -----------------------------------------: |
| SBOM Author                         | Yes      | NTIA-SBOM, CISA-2024-10, TR-03183          |
| SBOM Creation Time-stamp            | Yes      | NTIA-SBOM, CISA-2024-10, TR-03183          |
| SBOM Format                         | Yes      | CycloneDX 1.6, SPDX 2.3                    |
| SBOM Generation Tool                | No       |                                            |
| **SBOM Location**       👈          | Yes      | CRA-AII(9), TR-03183                       |
| SBOM Primary Component              | No       | CycloneDX 1.6, SPDX 3.0                    |
| SBOM Release                        | Yes      | CycloneDX 1.6, SPDX 2.3                    |
| SBOM Serial Number                  | Yes      | CycloneDX 1.6  SPDX 2.3                    |
| SBOM Type                           | No       | CISA-2023-4, CISA-2024-10                  |

</div>


Note:

* Location: Where to get the most recent SBOM
* Type: "When" in a Supply Chain an SBOM was created

[comment]: # (|||)

### Integrators in Germany

<div style="font-size: x-large;">

[TR-03183]:https://bsi.bund.de/dok/TR-03183 'TR-03183 Cyber Resilience Requirements for Manufacturers and Products, Part 2'

| Attribute name                      | Required | References                                 |
| :---------------------------------- | :------: | -----------------------------------------: |
| Executable Property                 | Yes      | [TR-03183]                                 |
| Archive Property                    | Yes      | TR-03183                                   |
| Structured Property                 | Yes      | TR-03183                                   |

</div>

Note:


[comment]: # (|||)

### Integrators in the Indian Financial Sector

<div style="font-size: x-large;">

[CSCRF]:https://www.sebi.gov.in/legal/circulars/aug-2024/cybersecurity-and-cyber-resilience-framework-cscrf-for-sebi-regulated-entities-res-_85964.html 'Cybersecurity and Cyber Resilience Framework (CSCRF) for SEBI Regulated Entities (REs), (GV.SC.S5, page 89), Securities and Exchange Board of India'

| Attribute name                      | Required | References                                 |
| :---------------------------------- | :------: | -----------------------------------------: |
| Dependencies (Known unknowns)       | Yes      | [CSCRF]                                    |
| Encryption used                     | Yes      | CSCRF                                      |
| Frequency of updates                | Yes      | CSCRF                                      |
| Access control                      | Yes      | CSCRF                                      |
| Methods for accommodating errors 👈 | Yes      | CSCRF                                      |

</div>

Note:


[comment]: # (|||)

### Actually Useful Attributes

<div style="font-size: x-large;">

| Attribute name                      | Required | References                                 |
| :---------------------------------- | :------: | -----------------------------------------: |
| Download location                   | No  👈   |                                            |
| Code Commit Revision                | No  👈   |                                            |
| Code Repository                     | No  👈   |                                            |

</div>

Note:

* What else is needed to make it easier to manage vulnerabilities?
    * A list of known vulnerabilities addressed
    * Details on which function/method had a vulnerability fixed
    * When & where the package was downloaded from


[comment]: # (|||)

### Open Source Stewards

<div style="font-size: x-large;">

[CRA-Rec-15]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_15 'CRA applies to economic operators that have an intention to monetise a product'
[CRA-Rec-18]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_18 'Open Source Software Contributors'
[CRA-Rec-19]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_19 'Open Source Software Stewards, light-touch regulatory regime, and CE mark implications'
[CRA-Rec-21]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_21 'Voluntary security attestation programs for Open Source projects'

| Attribute name                      | Required | References                                 |
| :---------------------------------- | :------: | -----------------------------------------: |
| Intended for Commercial Use         | No       | [CRA-Rec-15], [CRA-Rec-18]                 |
| Open Source Software Steward        | No       | [CRA-Rec-19]                               |
| **Security Attestation**  👈        | No       | [CRA-Rec-21]                               |

</div>

Note:

* Intended for Commercial Use + Attestations + OSS Steward = Possible funding source


[comment]: # (|||)

### Manufacturers

<div style="font-size: x-large;">

[CRA-Art-18]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_18 'Authorised representatives'
[CRA-Art-47]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_47 'Operational obligations of notified bodies'
[CRA-AII]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#anx_II 'Information and Instructions to the User'
[CRA-AV]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#anx_V 'EU Declaration of Conformity'


| Attribute name                      | Required | References                                 |
| :---------------------------------- | :------: | -----------------------------------------: |
| CE Conformity Assessment Body       | No       | [CRA-Art-47]\(1), [CRA-AV]                 |
| CE Declaration of Conformity        | No       | [CRA-AII]\(6), CRA-AV                      |
| CE Support End Date                 | No       | CRA-AII(7)                                 |
| CE Technical Documentation          | No       | CRA-AII(8)                                 |
| CE Authorized Representative        | No       | [CRA-Art-18]                               |

</div>


Note:

* What's needed for components that are monetized?
  * Maintainer becomes a Manufacturer
  * Does the Manufacturer have a Authorised representative?
  * This needs also to be supported


[comment]: # (|||)

## References

<div style="font-size: large;">

* (CISA-2023-4) [CISA Types of Software Bill of Materials (SBOM)](https://www.cisa.gov/resources-tools/resources/types-software-bill-materials-sbom), published 2023-04-21
* (CISA-2024-10) [CISA Framing Software Component Transparency: Establishing a Common Software Bill of Materials (SBOM)](https://www.cisa.gov/sites/default/files/2024-10/SBOM%20Framing%20Software%20Component%20Transparency%202024.pdf), Third edition, sections 2.2.1.4, 2.2.2 and Appendix B; Published 2024-10-15
* (CRA-AII) [Cyber Resilience Act, Annex II](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#anx_II) Information and Instructions to the User
* (CRA-AV) [Cyber Resilience Act, Annex V](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#anx_V) EU Declaration of Conformity
* (CRA-AVII) [Cyber Resilience Act, Annex VII](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#anx_VII) Contents of the Technical Documentation
* (CRA-Art-18) [Cyber Resilience Act, Article 18](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_18) Obligations of Authorized Representatives
* (CRA-Art-47) [Cyber Resilience Act, Article 47](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_47) Operational obligations of notified bodies
* (CRA-Rec-15) [Cyber Resilience Act, Recital 15](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_15) Economic operators
* (CRA-Rec-18) [Cyber Resilience Act, Recital 18](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_18) Open Source Software Contributors
* (CRA-Rec-19) [Cyber Resilience Act, Recital 19](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_19) Open Source Software Stewards
* (CRA-Rec-21) [Cyber Resilience Act, Recital 21](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_21) Open Source Security Attestation
* (CSCRF) [Cybersecurity and Cyber Resilience Framework (CSCRF) for SEBI Regulated Entities (REs)](https://www.sebi.gov.in/legal/circulars/aug-2024/cybersecurity-and-cyber-resilience-framework-cscrf-for-sebi-regulated-entities-res-_85964.html), (GV.SC.S5, page 89), Securities and Exchange Board of India, Published 2024-08-20
* (TR-03183) German Technical Requirement [TR-03183 Cyber Resilience Requirements for Manufacturers and Products](https://bsi.bund.de/dok/TR-03183), Part 2: Software Bill of Materials (SBOM), Version 2.0.0, published 2024-09-20
* (NTIA-SBOM) [NTIA Minimum Elements for a Software Bill of Materials (SBOM)](https://www.ntia.doc.gov/files/ntia/publications/sbom_minimum_elements_report.pdf#page=9), Published 2021-07-12

</div>



[comment]: # (||| data-auto-animate)

## Metadata Headaches

Lots of "opinions" from legislators & gov't orgs

* ⚠️  Inconsistencies in Terms
* ⚠️  Missing: More attributes needed to achieve security goals?
* ⚠️  Too much: Unnecessary additions, leading to complexity


Note:

* This picture is likely to evolve in the coming years
* Ecosystems would do well to prepare a smooth evolution


[comment]: # (|||)

## Conclusions?

* It's a mess
* It's up to volunteers to improve it
* ~"If it ain't broke, don't fix it"~
* Don't be a bystander


Note:

* "Permissionless Innovation"
* "Being a Good Open Source Citizen"
* We already know that being a bystander doesn't work – better to step up instead!


[comment]: # (!!!)

## Questions & Comments


[comment]: # (!!!)

# Thanks!

Salve J. Nilsen

🐘 Mastodon — @sjn\@chaos.social

🦆🦆
