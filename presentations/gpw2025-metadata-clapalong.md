[comment]: # (Compile this presentation with the command below)
[comment]: # (mdslides pts2024-sbom-intro.md --include ../media)
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


## CRA Metadata Clapalong

German Perl Workshop 2025

Salve J. Nilsen

🐘 Mastodon — @sjn\@chaos.social



Note:


[comment]: # (!!! data-auto-animate)

## CRA Metadata Clapalong 👏


[comment]: # (||| data-auto-animate)

## CRA Metadata Clapalong 👏

* How Useful?

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

### SBOM Meta-Attributes

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

* Bundesamt für Sicherheit in der Informationstechnik

<div style="font-size: x-large;">

[TR-03183]:https://bsi.bund.de/dok/TR-03183 'TR-03183 Cyber Resilience Requirements for Manufacturers and Products, Part 2'

| Attribute name                      | Required | References                                 |
| :---------------------------------- | :------: | -----------------------------------------: |
| Executable Property                 | Yes      | [TR-03183]                                 |
| Archive Property                    | Yes      | TR-03183                                   |
| Structured Property                 | Yes      | TR-03183                                   |

</div>


Notes:


[comment]: # (|||)

### Special Attributes for Integrators in the Indian Financial Sector

* Securities and Exchange Board of India

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

Notes:


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

## CRA Metadata Clapalong 👏

* Metadata Quality is Fun!

[comment]: # (||| data-auto-animate)

## CRA Metadata Clapalong 👏

* Metadata Quality is Fun!
* "Custom" metadata?
  * Try [CycloneDX properties](https://github.com/CycloneDX/cyclonedx-property-taxonomy?tab=readme-ov-file)


[comment]: # (!!! data-auto-animate)

# Thanks!

Salve J. Nilsen

🐘 Mastodon — @sjn\@chaos.social

🦆🦆🦆

