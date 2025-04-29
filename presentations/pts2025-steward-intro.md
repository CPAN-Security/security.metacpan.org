[comment]: # (Compile this presentation with the command below)
[comment]: # (mdslides pts2025-steward-intro.md --include ../media)
[comment]: # (...or by running the Makefile with "make")
[comment]: # (mdslides can be installed from https://github.com/dadoomer/markdown-slides/)

[comment]: # (THEME = solarized)

[comment]: # (minScale: 0.4)
[comment]: # (maxScale: 2.0)
[comment]: # (controls: true)
[comment]: # (width: "1440")
[comment]: # (height: "810")
[comment]: # (help: true)
[comment]: # (progress: true)
[comment]: # (controlsBackArrows: "true")


## What is an Open Source Steward?

PTS 2025

Salve J. Nilsen

🐘 Mastodon — @sjn\@chaos.social



Note:


[comment]: # (!!! data-auto-animate)

## 

"Where does the metadata come from?"


Note:

[comment]: # (||| data-auto-animate)


[Annex II]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#anx_II 'Information and Instructions to the User'
[Article 13(18)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.018 'Manufacturers shall ensure product s are accompanied by documentation listed in Annex II, and available for at least 10 years'
[Article 64(4)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#064.004 'Supplying incorrect, incomplete or misleading information may be fined up to 5M EUR or 1% of global turnover'

## Why even ask this question?

"Where does the metadata come from?"

<div style="font-size: xxx-large;">

> Supplying incorrect, incomplete or misleading information may be fined up to 5M EUR or 1% of global turnover

</div>
<div style="font-size: xx-large;">

> — Cyber Resilience Act, [Article 64(4)],<br> e.g. w.r.t. metadata described in [Annex II],<br> as required in [Article 13(18)]

</div>


[comment]: # (||| data-auto-animate)


[Annex II]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#anx_II 'Information and Instructions to the User'
[Article 13(18)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.018 'Manufacturers shall ensure product s are accompanied by documentation listed in Annex II, and available for at least 10 years'
[Article 64(4)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#064.004 'Supplying incorrect, incomplete or misleading information may be fined up to 5M EUR or 1% of global turnover'

## Why even ask this question?

"Where does the metadata come from?"

<div style="font-size: xxx-large;">

> Supplying <span style="color:darkred">**incorrect**</span>, <span style="color:darkred">**incomplete**</span> or <span style="color:darkred">**misleading**</span> information may be fined up to 5M EUR or 1% of global turnover

</div>
<div style="font-size: xx-large;">

> — Cyber Resilience Act, [Article 64(4)],<br> w.r.t. metadata described in [Annex II],<br> as required in [Article 13(18)]

</div>


[comment]: # (||| data-auto-animate)

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

## ⚠️  DRAFT ⚠️

This is a __work in progress__

[comment]: # (||| data-auto-animate)

## ⚠️  DRAFT ⚠️

This is a __work in progress__

Contributions appreciated!

[comment]: # (!!! data-auto-animate)

<div style="float: left; scale: 100%">

![Supply chain](media/metadata-sources.png)

</div>

## Supply-chain Metadata

### «Ecosystem perspective»

* Actions
* Actors
* Attributes
* Metadata


[comment]: # (||| data-auto-animate)


<div style="float: left; scale: 100%">

![Supply chain](media/metadata-sources.png)

</div>

## Supply-chain Metadata

### «Ecosystem perspective»

* Actions
* Actors
* Attributes
* Metadata
* … More?


[comment]: # (||| data-auto-animate)

<div style="float: left; scale: 100%">

![Supply chain](media/metadata-sources.png)

</div>


## Metadata Actions

* 🟥&nbsp;Create
* 🟨&nbsp;Contribute
* 🟩&nbsp;Distribute
* 🟦&nbsp;Verify
* 🟪&nbsp;Censor


[comment]: # (!!! data-auto-animate)

<div style="float: left; scale: 100%">

![Supply chain](media/metadata-sources.png)

</div>


## Metadata Actors

<div style="font-size: xx-large;">

* 🟦 Analyst
* 🟨🟦 Assembler
* 🟦 Auditor
* 🟦 Authenticator
* 🟥 Author
* 🟨🟦 Builder
* 🟨 Contributor
* 🟨 Curator
* 🟨 Custodian
* 🟨🟩 Deployer
* 🟩 Depositary
* 🟦 Distributor
* 🟦 End-user


* 🟦 Importer
* 🟥🟨🟦 Integrator
* 🟥🟨 Maintainer
* 🟥 Manufacturer
* 🟦 Distributor
* 🟦 Importer
* 🟥🟨🟩🟦 OSS Steward
* 🟥 Owner
* 🟨🟦 Packager
* 🟨 Patcher
* 🟩 Publisher
* 🟩🟪 Censor
* …

</div>


[comment]: # (||| data-auto-animate)

<div style="float: left; scale: 100%">

![Supply chain](media/metadata-sources.png)

</div>


## Metadata Actors

<div style="font-size: xx-large;">

* 🟥 Author
* 🟥🟨 Maintainer
* 🟨 Custodian
* 🟨 Contributor
* 🟨🟦 Builder
* 🟨 Curator
* 🟥🟨🟦 OSS Steward
* 🟨 Patcher
* 🟨🟦 Packager
* 🟨🟦 Assembler
* 🟥🟨🟦 Integrator
* 🟨🟩 Deployer
* 🟩🟪 Censor

</div>


[comment]: # (||| data-auto-animate)

<div style="float: left; scale: 100%">

![Supply chain](media/metadata-sources.png)

</div>


## Metadata Actors

<div style="font-size: xx-large;">

* 🟥 Author
* 🟥🟨 Maintainer
* 🟨 Custodian
* 🟨 Contributor
* 🟨🟦 Builder
* 🟨 Curator
* 🟥🟨🟦 OSS Steward
* 🟨 Patcher
* 🟨🟦 Packager
* 🟨🟦 Assembler
* 🟥🟨🟦 Integrator
* 🟨🟩 Deployer
* 🟩🟪 Censor

</div>

**These are the sources of the Required Metadata**


[comment]: # (!!! data-auto-animate)

<div style="float: left; scale: 100%">

![Supply chain](media/metadata-sources.png)

</div>


## Metadata Attributes


[comment]: # (||| data-auto-animate)

<div style="float: left; scale: 100%">

![Supply chain](media/metadata-sources.png)

</div>


## Metadata Attributes

### SBOM Metadata

<div style="font-size: xx-large;">

* **SBOM Author**
* **SBOM Creation Time-stamp**
* **SBOM Format**
* **SBOM Generation Tool**
* **SBOM Location**
* **SBOM Primary Component**
* **SBOM Release**
* **SBOM Serial Number**
* **SBOM Type**

</div>

[comment]: # (||| data-auto-animate)

<div style="float: left; scale: 100%">

![Supply chain](media/metadata-sources.png)

</div>


## Metadata Attributes

### NTIA Minimum Elements

<div style="font-size: xx-large;">

* **Dependencies**
* **Primary Component Name**
* SBOM Author
* SBOM Creation Time-stamp
* SBOM Format
* SBOM Generation Tool
* SBOM Location
* SBOM Primary Component
* SBOM Release
* SBOM Serial Number
* SBOM Type
* **Supplier Name**
* **Unique Product Identifier**

</div>

[comment]: # (||| data-auto-animate)

<div style="float: left; scale: 100%">

![Supply chain](media/metadata-sources.png)

</div>


## Metadata Attributes

### CISA Framing

<div style="font-size: x-large;">

* **Copyright Notice**
* **Cryptographic Hash**
* Dependencies
* **Dependency Relationships**
* **License(s)**
* Primary Component Name
* **SBOM Author**
* **SBOM Creation Time-stamp**
* SBOM Format
* SBOM Generation Tool
* SBOM Location
* SBOM Primary Component
* SBOM Release
* SBOM Serial Number
* **SBOM Type**
* Supplier Name
* Unique Product Identifier
* **Version**



[comment]: # (||| data-auto-animate)

<div style="float: left; scale: 100%">

![Supply chain](media/metadata-sources.png)

</div>


## Metadata Attributes

### EU CRA

<div style="font-size: x-large;">

* **CE Authorised Representative**
* **CE Conformity Assessment Body**
* **CE Declaration of Conformity**
* **CE Support End Date**
* **CE Technical Documentation**
* Copyright Notice
* Cryptographic Hash
* Dependencies
* Dependency Relationships
* **Intended for Commercial Use**
* License(s)
* **Open Source Software Steward**
* Primary Component Name
* **Purpose, Intended Use**


* SBOM Author
* SBOM Creation Time-stamp
* SBOM Format
* SBOM Generation Tool
* SBOM Location
* SBOM Primary Component
* SBOM Release
* SBOM Serial Number
* SBOM Type
* **Security Attestation**
* **Security contact**
* Supplier Name
* Unique Product Identifier
* Version


</div>


[comment]: # (||| data-auto-animate)

<div style="float: left; scale: 100%">

![Supply chain](media/metadata-sources.png)

</div>

[TR-03183]:https://bsi.bund.de/dok/TR-03183 'TR-03183 Cyber Resilience Requirements for Manufacturers and Products, Part 2'

## Metadata Attributes

### BSI [TR-03183] 2.0

<div style="font-size: x-large;">


* **Archive Property**
* CE Authorised Representative
* CE Conformity Assessment Body
* CE Declaration of Conformity
* CE Support End Date
* CE Technical Documentation
* Copyright Notice
* Cryptographic Hash
* Dependencies
* Dependency Relationships
* **Executable Property**
* Intended for Commercial Use
* License(s)
* Open Source Software Steward
* Primary Component Name
* Purpose, Intended Use


* SBOM Author
* SBOM Creation Time-stamp
* SBOM Format
* SBOM Generation Tool
* SBOM Location
* SBOM Primary Component
* SBOM Release
* SBOM Serial Number
* SBOM Type
* Security Attestation
* Security contact
* **Structured Property**
* Supplier Name
* Unique Product Identifier
* Version

</div>

Note:

* Bundesamt für Sicherheit in der Informationstechnik
* Technical Guideline TR-03183: Cyber Resilience Requirements for Manufacturers and Products

[comment]: # (||| data-auto-animate)

<div style="float: left; scale: 100%">

![Supply chain](media/metadata-sources.png)

</div>

[CSCRF]:https://www.sebi.gov.in/legal/circulars/aug-2024/cybersecurity-and-cyber-resilience-framework-cscrf-for-sebi-regulated-entities-res-_85964.html 'Cybersecurity and Cyber Resilience Framework (CSCRF) for SEBI Regulated Entities (REs), (GV.SC.S5, page 89), Securities and Exchange Board of India'

## Metadata Attributes

### SEBI [CSCRF]

<div style="font-size: x-large;">

* **Access control**
* Archive Property
* CE Authorised Representative
* CE Conformity Assessment Body
* CE Declaration of Conformity
* CE Support End Date
* CE Technical Documentation
* Copyright Notice
* Cryptographic Hash
* **Dependencies (Known unknowns)**
* Dependencies
* Dependency Relationships
* **Encryption used**
* Executable Property
* **Frequency of updates**
* Intended for Commercial Use
* License(s)
* **Methods for accommodating errors**


* Open Source Software Steward
* Primary Component Name
* Purpose, Intended Use
* SBOM Author
* SBOM Creation Time-stamp
* SBOM Format
* SBOM Generation Tool
* SBOM Location
* SBOM Primary Component
* SBOM Release
* SBOM Serial Number
* SBOM Type
* Security Attestation
* Security contact
* Structured Property
* Supplier Name
* Unique Product Identifier
* Version

</div>

notes:

* Securities and Exchange Board of India
* Cybersecurity and Cyber Resilience Framework (CSCRF) for SEBI Regulated Entities (REs)


[comment]: # (!!! data-auto-animate)

<div style="float: left; scale: 100%">

![Supply chain](media/metadata-sources.png)

</div>


## (Ecosystem response)


<div style="font-size: xx-large;">

* Ecosystems **are Open Source**
   * Tooling
   * Services
   * Specs
* Open Source Constraints
   * Break nothing
   * Preserve compatibility
   * No-fuzz upgrades
   * Information & outreach
* As volunteers!
   * **Contribution = life-blood**

</div>

<br>

### _Well volunteered!_

[comment]: # (||| data-auto-animate)

<div style="float: left; scale: 100%">

![Supply chain](media/metadata-sources.png)

</div>

## (Ecosystem response)

### _Well volunteered!_

<div style="font-size: x-large;">

* Access control
* Archive Property
* CE Authorised Representative
* CE Conformity Assessment Body
* CE Declaration of Conformity
* CE Support End Date
* CE Technical Documentation
* Copyright Notice
* Cryptographic Hash
* Dependencies (Known unknowns)
* **Dependencies**
* **Dependency Relationships**
* Encryption used
* Executable Property
* Frequency of updates
* Intended for Commercial Use
* **License(s)**
* Methods for accommodating errors


* Open Source Software Steward
* **Primary Component Name**
* **Purpose, Intended Use**
* SBOM Author
* SBOM Creation Time-stamp
* SBOM Format
* SBOM Generation Tool
* SBOM Location
* SBOM Primary Component
* SBOM Release
* SBOM Serial Number
* SBOM Type
* Security Attestation
* Security contact
* Structured Property
* **Supplier Name**
* Unique Product Identifier
* **Version**

</div>

[comment]: # (||| data-auto-animate)

<div style="float: left; scale: 100%">

![Supply chain](media/metadata-sources.png)

</div>

## (Ecosystem response)

### _Well volunteered!_

Who?

* Ecosystem people
* Standards people
* Regulators 🆕


[comment]: # (||| data-auto-animate)

<div style="float: left; scale: 100%">

![Supply chain](media/metadata-sources.png)

</div>

## (Ecosystem response)

### _Well volunteered!_

Who?

* Ecosystem people
* Standards people
* Regulators 🆕

<br>
<br>

**"Where do SBOM attributes come from?"**


[comment]: # (!!! data-auto-animate)

## A quick Attribute Poll


[comment]: # (||| data-auto-animate)

[TR-03183]:https://bsi.bund.de/dok/TR-03183 'TR-03183 Cyber Resilience Requirements for Manufacturers and Products, Part 2'
### Component Attributes

<div style="font-size: x-large;">

[TR-03183]:https://bsi.bund.de/dok/TR-03183 'TR-03183 Cyber Resilience Requirements for Manufacturers and Products, Part 2'
[NTIA-SBOM]:https://www.ntia.doc.gov/files/ntia/publications/sbom_minimum_elements_report.pdf#page=9 'NTIA Minimum Elements for a Software Bill of Materials (SBOM)'
[CISA-2023-4]:https://www.cisa.gov/resources-tools/resources/types-software-bill-materials-sbom 'CISA Types of Software Bill of Materials (SBOM)'
[CISA-2024-10]:https://www.cisa.gov/sites/default/files/2024-10/SBOM%20Framing%20Software%20Component%20Transparency%202024.pdf 'CISA Framing Software Component Transparency: Establishing a Common Software Bill of Materials (SBOM)'
[CRA-II]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#anx_II 'Information and Instructions to the User'
[CRA-AV]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#anx_V 'EU Declaration of Conformity'
[CSCRF]:https://www.sebi.gov.in/legal/circulars/aug-2024/cybersecurity-and-cyber-resilience-framework-cscrf-for-sebi-regulated-entities-res-_85964.html 'Cybersecurity and Cyber Resilience Framework (CSCRF) for SEBI Regulated Entities (REs), (GV.SC.S5, page 89), Securities and Exchange Board of India'


| Attribute name                      | Required | References                                            |
| :---------------------------------- | :------: | ----------------------------------------------------: |
| Primary Component Name              | Yes      | [NTIA-SBOM], [CISA-2024-10], [CRA-AV], [TR-03183]     |
| Version                             | Yes      | CISA-2024-10, CRA-AV, TR-03183                        |
| Purpose, Intended Use               | Yes      | [CRA-AII]\(4)                                         |
| Supplier Name                       | Yes      | CRA-AII(1), CRA-AV, NTIA-SBOM, CISA-2024-10, TR-03183 |
| Security contact                    | Yes      | CRA-AII(2)                                            |
| Copyright Notice                    | Yes      | CISA-2024-10                                          |
| License(s)                          | Yes      | CISA-2024-10, TR-03183, [CSCRF]                       |

</div>

Note:


[comment]: # (|||)

### Dependency Attributes

<div style="font-size: x-large;">

[TR-03183]:https://bsi.bund.de/dok/TR-03183 'TR-03183 Cyber Resiliencee Requirements for Manufacturers and Products, Part 2'
[NTIA-SBOM]:https://www.ntia.doc.gov/files/ntia/publications/sbom_minimum_elements_report.pdf#page=9 'NTIA Minimum Elements for a Software Bill of Materials (SBOM)'
[CISA-2023-4]:https://www.cisa.gov/resources-tools/resources/types-software-bill-materials-sbom 'CISA Types of Software Bill of Materials (SBOM)'
[CISA-2024-10]:https://www.cisa.gov/sites/default/files/2024-10/SBOM%20Framing%20Software%20Component%20Transparency%202024.pdf 'CISA Framing Software Component Transparency: Establishing a Common Software Bill of Materials (SBOM)'
[CRA-AII]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#anx_II 'Information and Instructions to the User'
[CRA-AV]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#anx_V 'EU Declaration of Conformity'
[CSCRF]:https://www.sebi.gov.in/legal/cireculars/aug-2024/cybersecurity-and-cyber-resilience-framework-cscrf-for-sebi-regulated-entities-res-_85964.html 'Cybersecurity and Cyber Resilience Framework (CSCRF) for SEBI Regulated Entities (REs), (GV.SC.S5, page 89), Securities and Exchange Board of India'

| Attribute name                      | Required | References                                             |
| :---------------------------------- | :------: | -----------------------------------------------------: |
| Unique Product ID                   | Yes      | [CRA-AII]\(3), [CRA-AV], [NTIA-SBOM], [CISA-2024-10]   |
| Cryptographic Hash                  | Yes      | CISA-2024-10, [TR-03183], [CSCRF]                      |
| Primary Component Filename          | Yes      | TR-03183                                               |
| Dependencies                        | Yes      | CRA-AII(5), NTIA-SBOM, CISA-2024-10, TR-03183, CSCRF   |
| Dependency Relationships            | Yes      | CISA-2024-10                                           |

</div>


Note:


[comment]: # (|||)

### SBOM Attributes

<div style="font-size: x-large;">

[TR-03183]:https://bsi.bund.de/dok/TR-03183 'TR-03183 Cyber Resilience Requirements for Manufacturers and Products, Part 2'
[NTIA-SBOM]:https://www.ntia.doc.gov/files/ntia/publications/sbom_minimum_elements_report.pdf#page=9 'NTIA Minimum Elements for a Software Bill of Materials (SBOM)'
[CISA-2023-4]:https://www.cisa.gov/resources-tools/resources/types-software-bill-materials-sbom 'CISA Types of Software Bill of Materials (SBOM)'
[CISA-2024-10]:https://www.cisa.gov/sites/default/files/2024-10/SBOM%20Framing%20Software%20Component%20Transparency%202024.pdf 'CISA Framing Software Component Transparency: Establishing a Common Software Bill of Materials (SBOM)'
[CRA-AII]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#anx_II 'Information and Instructions to the User'


| Attribute name                      | Required | References                                 |
| :---------------------------------- | :------: | -----------------------------------------: |
| SBOM Author                         | Yes      | [NTIA-SBOM], [CISA-2024-10], [TR-03183]    |
| SBOM Creation Time-stamp            | Yes      | NTIA-SBOM, CISA-2024-10, TR-03183          |
| SBOM Format                         | Yes      | CycloneDX 1.6, SPDX 2.3                    |
| SBOM Generation Tool                | No       |                                            |
| SBOM Location                       | Yes      | [CRA-AII]\(9), TR-03183                    |
| SBOM Primary Component              | No       | CycloneDX 1.6, SPDX 3.0                    |
| SBOM Release                        | Yes      | CycloneDX 1.6, SPDX 2.3                    |
| SBOM Serial Number                  | Yes      | CycloneDX 1.6  SPDX 2.3                    |
| SBOM Type                           | No       | [CISA-2023-4], CISA-2024-10                |

</div>


Note:

[comment]: # (|||)

### Open Source Steward Attributes

<div style="font-size: x-large;">

[CRA-Rec-15]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_15 'CRA applies to economic operators that have an intention to monetise a product'
[CRA-Rec-18]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_18 'Open Source Software Contributors'
[CRA-Rec-19]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_19 'Open Source Software Stewards, light-touch regulatory regime, and CE mark implications'
[CRA-Rec-21]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_21 'Voluntary security attestation programs for Open Source projects'

| Attribute name                      | Required | References                                 |
| :---------------------------------- | :------: | -----------------------------------------: |
| Intended for Commercial Use         | No       | [CRA-Rec-15], [CRA-Rec-18]                 |
| Open Source Software Steward        | No       | [CRA-Rec-19]                               |
| Security Attestation                | No       | [CRA-Rec-21]                               |

</div>

Note:


[comment]: # (|||)

### Manufacturer Attributes

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

### Special Attributes for Integrators in Germany

<div style="font-size: x-large;">

[TR-03183]:https://bsi.bund.de/dok/TR-03183 'TR-03183 Cyber Resilience Requirements for Manufacturers and Products, Part 2'

| Attribute name                      | Required | References                                 |
| :---------------------------------- | :------: | -----------------------------------------: |
| Executable Property                 | Yes      | [TR-03183]                                 |
| Archive Property                    | Yes      | TR-03183                                   |
| Structured Property                 | Yes      | TR-03183                                   |

</div>


[comment]: # (|||)

### Special Attributes for Integrators in the Indian Financial Sector

<div style="font-size: x-large;">

[CSCRF]:https://www.sebi.gov.in/legal/circulars/aug-2024/cybersecurity-and-cyber-resilience-framework-cscrf-for-sebi-regulated-entities-res-_85964.html 'Cybersecurity and Cyber Resilience Framework (CSCRF) for SEBI Regulated Entities (REs), (GV.SC.S5, page 89), Securities and Exchange Board of India'

| Attribute name                      | Required | References                                 |
| :---------------------------------- | :------: | -----------------------------------------: |
| Dependencies (Known unknowns)       | Yes      | [CSCRF]                                    |
| Encryption used                     | Yes      | CSCRF                                      |
| Frequency of updates                | Yes      | CSCRF                                      |
| Access control                      | Yes      | CSCRF                                      |
| Methods for accommodating errors    | Yes      | CSCRF                                      |

</div>


[comment]: # (|||)

### (Optional Attributes)

<div style="font-size: x-large;">

| Attribute name                      | Required | References                                 |
| :---------------------------------- | :------: | -----------------------------------------: |
| Download location                   | No       |                                            |
| Code Commit Revision                | No       |                                            |
| Code Repository                     | No       |                                            |

</div>

Note:


[comment]: # (!!! data-auto-animate)

<div style="float: left; scale: 100%">

![Supply chain](media/metadata-sources.png)

</div>

## Dear Regulators

<div style="font-size: xx-large;">


</div>


Note:

* Not just BSI or the Securities and Exchange Board of India

[comment]: # (||| data-auto-animate)

<div style="float: left; scale: 100%">

![Supply chain](media/metadata-sources.png)

</div>

## Dear Regulators

<br>

### Welcome to the Open Source Communities!

* We're many
* We're _everywhere_
* We support _everyone_
* We don't _work for free_
* We _volunteer_


note:


[comment]: # (||| data-auto-animate)

<div style="float: left; scale: 100%">

![Supply chain](media/metadata-sources.png)

</div>

## Dear Regulators

### Your contributions _are welcome_

* But not all of them
   * — Only the useful ones!

* Do like NIST and CISA 
   * — Only require the minimum!


[comment]: # (||| data-auto-animate)

<div style="float: left; scale: 100%">

![Supply chain](media/metadata-sources.png)

</div>

## Dear Regulators

### Your contributions _are welcome_

* But not all of them
   * — Only the useful ones!

* Do like NIST and CISA 
   * — Only require the minimum!

<br>
<br>

### Well volunteered!


[comment]: # (!!! data-auto-animate)

## Questions & Comments


[comment]: # (!!!)

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



[comment]: # (!!!)

# Thanks!

Salve J. Nilsen

🐘 Mastodon — @sjn\@chaos.social

🦆🦆

