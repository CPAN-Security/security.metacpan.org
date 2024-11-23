---
layout: page
title: Reading list
description: Reading list for CPANSec contributors
toc: true
---

## Document status: ⚠️  DRAFT

> [!CAUTION]
> This is the CPAN Security Group recommended reading list.
> **This page is [Open Source](#license-and-use-of-this-document)** – meaning, it's eventual quality and usefulness is proportional to your contribution!
> If you have any additions or improvements, please [open an issue](https://github.com/CPAN-Security/security.metacpan.org/issues), citing this page.
>
> - Contribute on Github: [https://github.com/CPAN-Security/security.metacpan.org/blob/readinglist/docs/readinglist.md](https://github.com/CPAN-Security/security.metacpan.org/blob/readinglist/docs/readinglist.md)
> - Discuss on IRC: [ircs://ssl.irc.perl.org:7062/#cpan-security](ircs://ssl.irc.perl.org:7062/#cpan-security)
> - Discuss on Matrix: [https://matrix.to/#/#cpansec:matrix.org](https://matrix.to/#/#cpansec:matrix.org)


## Software Bills of Materials (SBOM)

* (NTIA-2021-7) [The Minimum Elements For a Software Bill of Materials (SBOM)](https://www.ntia.doc.gov/files/ntia/publications/sbom_minimum_elements_report.pdf) (July 2021)
* (CISA-2023-12) (NSA, ODNI, CISA) [Securing the Software Supply Chain: Recommended Practices for Managing OSS and SBOMs](https://media.defense.gov/2023/Dec/11/2003355557/-1/-1/0/ESF_SECURING_THE_SOFTWARE_SUPPLY_CHAIN%20RECOMMENDED%20PRACTICES%20FOR%20MANAGING%20OPEN%20SOURCE%20SOFTWARE%20AND%20SOFTWARE%20BILL%20OF%20MATERIALS.PDF) (December 2023)
* (NTIA-2021) [Survey of Existing SBOM Formats and Standards](https://www.ntia.gov/sites/default/files/publications/sbom_formats_survey-version-2021_0.pdf) (2021)
* (CISA-2023-4) [CISA Types of Software Bill of Materials (SBOM)](https://www.cisa.gov/resources-tools/resources/types-software-bill-materials-sbom), published 2023-04-21


### SBOM use cases

* (CDX) [CycloneDX Use Cases](https://cyclonedx.org/use-cases/)
* (SPDX) [A Practical Guide to SPDX](https://fossa.com/learn/spdx)
* (SPDX) [How To Use SPDX 2.3 in Different Scenarios](https://spdx.github.io/spdx-spec/v2.3/how-to-use/)


### SBOM Standards

* (ISO/IEC 5962:2021) [SPDX® Specification V2.2.1](https://standards.iso.org/ittf/PubliclyAvailableStandards/c081870_ISO_IEC_5962_2021%28E%29.zip) (Source: ISO's [Publicly Available Standards](https://standards.iso.org/ittf/PubliclyAvailableStandards/index.html) list)
* (ECMA-424) [CycloneDX Bill of materials specification](https://ecma-international.org/publications-and-standards/standards/ecma-424/), published June 2024.


### Useful articles and papers

* (CISA-2024-3) [SBOM Sharing Roles and Considerations](https://www.cisa.gov/resources-tools/resources/sbom-sharing-roles-and-considerations), (March 2024)
* (CISA-2024-3) [CISA SBOM Sharing Roles and Considerations](https://www.cisa.gov/resources-tools/resources/sbom-sharing-roles-and-considerations), published 2024-03-28
* (CISA-2024-5) [SBOM Sharing Primer](https://www.cisa.gov/resources-tools/resources/sbom-sharing-primer), (May 2024)
* (CISA-2024-10) [Framing Software Component Transparency: Establishing a Common Software Bill of Materials (SBOM)](https://www.cisa.gov/resources-tools/resources/framing-software-component-transparency-2024), Sections 2.2.1.4 and 2.2.2 and others, (October 2024)
* (CISA) [Attributes for evaluation and cataloging of Software Bill of Materials Tooling](https://docs.google.com/document/d/1TKPIjT7Rfc38F0OMuXIlPqFRoH7wj2H8x3w13Pgy8V4/edit), (Unpublished)
  * Related [spreadsheet](https://onedrive.live.com/view.aspx?resid=68652AA55C12F19A%216830&authkey=!AG7Yjwi-1S3rjWI)
* (DE-TR) German Technical Requirement [TR-03183 Cyber Resilience Requirements for Manufacturers and Products (part 2)](https://bsi.bund.de/dok/TR-03183), Version 2.0.0, published 2024-09-20.
* (Huges-2023-1) [Managing Open Source and SBOMs](https://resilientcyber.substack.com/p/managing-open-source-and-sboms), (Chris Huges, 2023)
* (Huges-2023-2) [Understanding OWASP’s Bill of Material Maturity Model: Not all SBOMs are created equal](https://www.csoonline.com/article/1246904/not-all-sboms-are-created-equal-understanding-owasps-bill-of-material-maturity-model.html), (Chris Huges, 2023)
* (Lawfare-2023) [Open-Source Security: How Digital Infrastructure Is Built on a House of Cards](https://www.lawfaremedia.org/article/open-source-security-how-digital-infrastructure-built-house-cards), (Lawfare Media, July 2022)
* (NTIA-2019-11) [Roles and Benefits for SBOM Across the Supply Chain](https://www.ntia.gov/files/ntia/publications/ntia_sbom_use_cases_roles_benefits-nov2019.pdf), (November 2019)
* (NTIA-2021-3) [SBOM Tool Classification Taxonomy](https://www.ntia.gov/files/ntia/publications/ntia_sbom_tooling_taxonomy-2021mar30.pdf), published 2021-03-30
* (NTIA-2021-7) [NTIA Minimum Elements for a Software Bill of Materials (SBOM)](https://www.ntia.doc.gov/files/ntia/publications/sbom_minimum_elements_report.pdf#page=9), Published 2021-07-12 (Superseeded by CISA-2024-10)
* (NTIA-2021-11) [Software Suppliers Playbook: SBOM Production and Provision](https://www.ntia.gov/files/ntia/publications/software_suppliers_sbom_production_and_provision_-_final.pdf), (November 2021)
* (SPDX-2.3) [Satisfying NTIA Minimum Elements for an SBOM using SPDX](https://spdx.github.io/spdx-spec/v2.3/how-to-use/#k22-mapping-ntia-minimum-elements-to-spdx-fields), (SPDX 2.3)
* (SPDX-3.0) [Using SPDX to comply with Norms, Standards and Regulation](https://spdx.github.io/spdx-spec/v3.0/annexes/using-SPDX-to-comply-with-industry-guidance/#f1-satisfying-ntia-minimum-elements-for-an-sbom-using-spdx-us-executive-order-14028), (SPDX 3.0)
* (MITRE-2024-10) [Data Normalization Challenges and Mitigations in Software Bill of Materials Processing](https://www.mitre.org/news-insights/publication/data-normalization-challenges-mitigations-software-bill-materials-processing), (October 2024)

See also the [Regulations, directives and laws](#regulations--directives-and-laws) section below.


## Software identification (naming & versioning)

* [PURL Specification](https://github.com/package-url/purl-spec)
* (CPAN) [URI::PackageURL](https://github.com/giterlizzi/perl-URI-PackageURL)
* (CPAN) [CPAN::DistnameInfo](https://github.com/Perl-Toolchain-Gang/CPAN-DistnameInfo)


### Useful articles, papers and resources

* (CISA-2023-10) [Software Identification Ecosystem Option Analysis](https://www.cisa.gov/resources-tools/resources/software-identification-ecosystem-option-analysis); Published October 2023.
* (Repology) [Repology ruleset repo](https://github.com/repology/repology-rules)
* (Ombredanne-2023) [PURLs of Wisdom: Universal software package identification](https://nexb.com/purl-universal-software-package-identification/) Published by Philippe Ombredanne, May 2023.
* (Ombredanne-2022) [Package URL and Version range spec: Towards mostly universal dependency resolution](https://archive.fosdem.org/2022/schedule/event/package_url_and_version_range_spec/) Presented at FOSDEM 2022, 15 minutes length.
* (Video) [Software Identity And The Naming Of Things](https://www.youtube.com/watch?v=wzo81uccSfU) Presented at S4 Conference 2023.
* (OpenSSF-2023-12) [OpenSSF Responds to the CISA RFC on Software Identification Ecosystem Analysis](https://openssf.org/blog/2023/12/11/openssf-responds-to-the-cisa-rfc-on-software-identification-ecosystem-analysis/) Published 2023-12-11.
* (BOMctl) [SBOM Document Linking Scenarios](https://docs.google.com/document/d/1Dj-OAycyAH3d6A9vPJWldNoLRArRVB607to_0s5Fk8w/edit?tab=t.0#heading=h.f7ex7w4dum5t)


## Software Lifecycle

* (OWASP) [Common Lifecycle Enumeration](https://owasp.org/www-project-common-lifecycle-enumeration/)
* (MPO) [Defining End of Life for Medical Devices](https://www.mpo-mag.com/issues/2023-09-01/view_columns/defining-end-of-life-for-medical-devices/), MPO Magazine, 2023-09-06
* (CHAOSS-2020) CHAOSS [Types of Contributions](https://chaoss.community/?p=3432), First created 2020-02-20.
* (arXiv:2408.06723v1) [Sustaining Maintenance Labor for Healthy Open Source Software Projects through Human Infrastructure: A Maintainer Perspective](https://arxiv.org/pdf/2408.06723), Published 2024-08-13.
* (MSFTOSS-2024) [5 things we learned from sponsoring a sampling of our open source dependencies](https://opensource.microsoft.com/blog/2024/06/27/5-things-we-learned-from-sponsoring-a-sampling-of-our-open-source-dependencies/), Published 2024-06-27.


## Provenance & Supply Chain Security

* (OpenSSF-2024-3) [Principles for Package Repository Security](https://repos.openssf.org/principles-for-package-repository-security) (Feb 2024)
* (OpenSSF-2023-7) [Build Provenance for All Package Registries](https://repos.openssf.org/build-provenance-for-all-package-registries) (July 2023)
* (SLSA) [SLSA v1.0 Guiding Principles](https://slsa.dev/spec/v1.0/principles)
* (SLSA) [SLSA v1.0 Terminology](https://slsa.dev/spec/v1.0/terminologye)
* (SLSA) [SLSA v1.0 Developer's quick-start guide](https://slsa.dev/get-started)
* (SLSA) [SLSA v1.0 Infrastructure provider's quick-start guide](https://slsa.dev/how-to-infra)


## Transparency Logs

* (OpenSSF) [Sigstore home](https://openssf.org/community/sigstore/)
* (OpenSSF) [Sigstore: Simplifying Code Signing for Open Source Ecosystems](https://openssf.org/blog/2023/11/21/sigstore-simplifying-code-signing-for-open-source-ecosystems/)
* (Chainguard.dev) [Life of a Sigstore signature](https://www.chainguard.dev/unchained/life-of-a-sigstore-signature)


## Regulations, directives and laws

There are several relevant legislations regarding cybersecurity in Open Source ecosystems and supply chains.
This is not a exhaustive list!


### USA – EO 14028

* (USA) [Executive Order on Improving the Nation’s Cybersecurity](https://www.whitehouse.gov/briefing-room/presidential-actions/2021/05/12/executive-order-on-improving-the-nations-cybersecurity/) (EO 14028, 2021-05-12)
    * Section 4: Enhancing Software Supply Chain Security


### EU and EEA – NIS2

[Directive 2022/2555, Network and Information Security Directive 2](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32022L2555&qid=1710318619717) (NIS2; Published 2022-12-27)

* In the [NIS2 Recitals](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX:32022L2555&qid=1710318619717#page=12)
    * Recital (52): On Open Source cybersecurity tools (page 11)
    * Recital (58): On the handling of discovered vulnerabilities (page 12)
    * Recital (62): Access to correct and timely information about vulnerabilities (page 13)
    * Recital (85): On supply-chain risk management (page 17)
    * Recital (89): Adoption of basic cyber hygiene practices (page 17)
    * Recitals (90-91): On coordinated security risk assessments of supply chains (page 18)
* In [Chapter I](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX:32022L2555&qid=1710318619717#page=32)
    * Article 6: Definitions
* In [Chapter II](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX:32022L2555&qid=1710318619717#page=36)
    * Article 7 paragraph 2(a): Creation of a national cybersecurity strategy regarding the security of supply chains for ICT products and services
* In [Chapter IV](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX:32022L2555&qid=1710318619717#page=48)
    * Article 20
    * Articles 21 paragraphs 1, 2, 3: **All-hazards approach** to cybersecurity risk-management measures (page 48)
    * Article 23
* [Legislative Train Schedule](https://www.europarl.europa.eu/legislative-train/theme-a-europe-fit-for-the-digital-age/file-review-of-the-nis-directive)

#### NIS2 Implemented Regulation

* [Draft act](https://ec.europa.eu/info/law/better-regulation/have-your-say/initiatives/14241-Cybersecurity-risk-management-reporting-obligations-for-digital-infrastructure-providers-and-ICT-service-managers_en)


### EU and EEA – CRA

(EU) [Regulation 2024/2847 (Cyber Resilience Act)](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=OJ:L_202402847) (Published 2024-11-20)

* [Legislative Train Schedule](https://www.europarl.europa.eu/legislative-train/theme-a-europe-fit-for-the-digital-age/file-european-cyber-resilience-act)


#### CRA Recitals

[CRA Recitals](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=OJ:L_202402847#page=3) are for explaining the background and context for the regulation. The ordering is the same as in the Articles. These are for interpretation, and not legally binding.

* Recital (10): CRA relevance for supply chains (page 3)
* Recital (**15**): CRA applies to economic operators that have an intention to monetise a product (page 4)
* Recital (**18**): Open Source Software Contributors (pages 4-5)
* Recital (**19**): Open Source Software Stewards, light-touch regulatory regime, and CE mark implications (page 5)
* Recital (**20**): Open Source package managers considerations as "distributors" (page 5)
* Recital (21): Voluntary security attestation programs for Open Source projects (page 5)
* Recital (22): Submission of SBOMs for Open Source projects (page 5)
* Recital (24): CRA relevance for the NIS2 directive (page 6)
* Recital (31): Manufacturer's liability due to lack of security updates (page 8)
* Recital (**34**): Exercise due diligence when integrating third-party components (pages 8-9)
* Recital (37): Software for testing purposes, alphas, betas (page 9)
* Recital (39): Continued security updates (pages 9-10)
* Recital (41): Substantial modifications requires a new conformity assessment to be done (page 10)
* Recitals (43-45): Important products with digital elements (pages 10-11)
* Recital (**56**): On the download and installation of security updates, and notification of end of support (page 14)
* Recital (**57**): On the requirement to be able to get security updates separately from functionality updates (pages 14)
* Recitals (60-62): Support period (page 15)
* Recital (64): Point of contact (page 15)
* Recital (65): Secure by default (page 16)
* Recital (117): […] establish voluntary security attestation programmes for assessing the conformity of products with digital elements qualifying as free and open-source software […] (page 23)


#### CRA Articles

[CRA Articles](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=OJ:L_202402847#page=28) are legally binding, and describes the scope, definitions and law.

* Chapter I
    * **Article 3**, Definitions (pages 29-31)
    * Article 9, Point 1. (b-c), Stakeholder consultation (page 34)
* Chapter II — Obligations of Economic Operators and Provisions in relation to Free and Open-Source Software
    * **Article 13**, Obligations of Manufacturers (pages 35-38)
        * **Paragraph 5**, "Manufacturers shall exercise due diligence when integrating components" (page 35)
        * Paragraph 6, "[…] they shall share the relevant code or documentation […]" (page 36)
        * Paragraph 12, "[…] manufacturers shall draw up the EU declaration of conformity in accordance with Article 28 and affix the CE marking in accordance with Article 30." (page 36-37)
    * **Article 14**, Reporting obligations of manufacturers (pages 38-40)
        * Paragraph 1, "A manufacturer shall notify any actively exploited vulnerability contained in the product […] that it becomes aware of" (page 38)
        * Paragraph 3, "A manufacturer shall notify any severe incident having an impact on the security of the product […] that it becomes aware of" (page 39
        * Paragraph 8, "After becoming aware of an actively exploited vulnerability or a severe incident, the manufacturer shall inform the impacted users of the product, and where appropriate all users, […] and, […] about risk mitigation and any corrective measures that the users can deploy" (page 40)
    * **Article 15**, Voluntary reporting (page 40)
    * Article 16, Establishment of a single reporting platform (page 41)
    * Article 17, Other provisions related to reporting (page 42)
    * Article 18, Authorized representatives (pages 42-43)
    * **Article 19**, Obligations of importers (pages 43-44)
    * **Article 20**, Obligations of distributors (page 44)
    * **Article 21**, Cases in which obligations of manufacturers apply to importers and distributors (page 44)
    * **Article 22**, Other cases in which obligations of manufacturers apply (page 45)
    * Article 23, Identification of economic operators (page 45)
* Chapter II – Obligations of open-source software stewards (page 45-45)
    * **Article 24**, Obligations of open-source software stewards (page 45)
    * **Article 25**, Security attestation of free and open-source software (page 45)
    * **Article 26**, Guidance (pages 46)
* Chapter III — Conformity of the product with digital elements (47-51)
    * Article 28, EU declaration of conformity (pages 47-48)
    * Article 29, General principles of the CE marking (page 48)
    * Article 30, Rules and conditions for affixing the CE marking (page 48)
* Chapter IV — Notification of Conformity Assessment Bodies (pages 51-57)
    * Article 47, Operational obligations of notified bodies (pages 55-56
* Chapter V — Market Surveillance and Enforcement (pages 57-63)
    * **Article 52**, Market surveillance and control of products (pages 57-5858585858)
        * **Section 3**, Market surveillance authorities […] shall also be responsible for carrying out market surveillance activities in relation to the obligations for open-source software stewards […]. (page 57)
        * Section 11, Market surveillance authorities shall inform consumers of where to submit complaints that could indicate non-compliance with this Regulation […] and […] facilitate reporting of vulnerabilities, incidents and cyber threats […]. (page 57)
    * **Article 54**, Procedure […] concerning products […] presenting a significant cybersecurity risk (pages 58-)
        * Section 1, [If a market authority finds] sufficient reason to consider that a product […], including its vulnerability handling, presents a significant cybersecurity risk, […] it shall […] carry out an evaluation of the product […] concerned in respect of its compliance with all the requirements laid down in this Regulation. (page 58)
        * Section 5, [If the economic operator] not take adequate corrective action […], the market surveillance authority shall take all appropriate provisional measures to prohibit or restrict that product […] from being made available […], to withdraw it from that market or to recall it. (page 59)
    * **Article 58**, Formal non-compliance (page 62)
* Chapter VII — Confidentiality and Penalties (pages 64-65)
    * Article 64 — Penalties (page 64-65)
        * **Section 10(b)**, Rules on administrative fines shall not apply to Open Source Software Stewards (page 65)
* Chapter VIII — Transitional and final provisions (pages 65-67)
    * Article 71 — Entry into force and application (pages 66-67)
        * Section 2, This Regulation shall apply from 11 December 2027. However, Article 14 shall apply from 11 September 2026 and Chapter IV (Articles 35 to 51) shall apply from 11 June 2026. (page 67)

#### CRA Annexes

Annexes are technical materials presented separately from the main text, and have the same value as the Articles (they are legally binding).

* [CRA Annex I](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=OJ:L_202402847#page=68)
    * Essential Cybersecurity Requirements (pages 68-69)
        * Part I — Cybersecurity requirements relating to the properties of products with digital elements (page 68)
        * Part II — Vulnerability handling requirements (pages 68-69)
* [CRA Annex II](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=OJ:L_202402847#page=70)
    * Information and Instructions to the User (pages 70)
* [CRA, Annex VII](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=OJ:L_202402847#page=75)
    * Content of the Technical Documentation (pages 75)


#### Other useful resources

* (EU) [The CRA Fact Sheet](https://digital-strategy.ec.europa.eu/en/library/cyber-resilience-act-factsheet)
* (Eclipse) Open Regulatory Compliance (ORC) WG [mailing list archive](https://www.eclipse.org/lists/open-regulatory-compliance/threads.html)
* (Eclipse) ORC WG [gitlab](https://gitlab.eclipse.org/eclipse-wg/open-regulatory-compliance-wg)
* (Eclipse) ORC WG [Matrix chat](https://matrix.to/#/#open-regulatory-compliance:matrix.eclipse.org)
* (EU) The '[Blue Guide](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=uriserv%3AOJ.C_.2022.247.01.0001.01.ENG&toc=OJ%3AC%3A2022%3A247%3ATOC)' on the implementation of EU product rules (2022/C 247/01). Published 2022-06-29; [PDF](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX:52022XC0629(04))
* (EU) [CRA Corrigendum](https://draftable.com/compare/ShyQnqhNqFGP) comparison. Published 2024-09-03; [Original PDF](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130-FNL-COR01_EN.pdf)

### EU and EEA – PLD

(EU) Product Liability Directive (PLD)

* (EU) [Legislative Train Schedule](https://www.europarl.europa.eu/legislative-train/theme-a-europe-fit-for-the-digital-age/file-new-product-liability-directive)
* (EU) [Product Liability Directive](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0132_EN.html) (85/374/EEC), Published 2024-03-12 by the EU Parliament ([PDF](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0132_EN.pdf))
* (EU) [PLD Corrigendum](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130-FNL-COR01_EN.pdf) (PDF); Published 2024-09-03;

### EU and EEA – DORA

(EU) [Digital Operational Resilience Act](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32022R2554&qid=1710317679922): Regulation (EU) 2022/2554 of the European Parliament and of the Council of 14 December 2022 on digital operational resilience for the financial sector and amending Regulations (DORA, 2022-12-14)


* Article 16-23

* [Legislative Train Schedule](https://www.europarl.europa.eu/legislative-train/theme-a-europe-fit-for-the-digital-age/file-cross-sectoral-financial-services-act-1)


## Other informative articles and guides

* (Checkmarx) [Preparing for Europe’s Most Extensive Cybersecurity Directive, NIS2 – What AppSec teams need to know](https://checkmarx.com/blog/preparing-for-europes-most-extensive-cybersecurity-directive-nis2-what-appsec-teams-need-to-know/)
* (CPAN) [It takes a community to raise a CPAN module](http://neilb.org/2016/02/13/it-takes-a-community.html) – describing the different personas or roles involved in the life-cycle of a CPAN distribution.
* (CISA) [Software Acquisition Guide](https://www.cisa.gov/resources-tools/resources/software-acquisition-guide-government-enterprise-consumers-software-assurance-cyber-supply-chain)


## PCI-SSF

The Payment Card Industry Software Security Framework v1.2.1, Control Objective C.1, states

> * C.1
>     * All components and services used by the software are identified and maintained in a manner that minimizes the exposure of vulnerabilities.
> * C.1.1
>     * Control Objective: All software components and services are documented or otherwise cataloged in a software bill of materials (SBOM).
>     * Test Requirements: The assessor shall examine evidence to confirm that information is maintained that describes all software components and services comprising the software solution, including:
>         * All proprietary software libraries, packages, modules, and/or code packaged in a manner that enables them to be tracked as a freestanding unit of software.
>         * All third-party and Open Source frameworks, libraries, and code embedded in or used by the software during operation.
>         * All third-party software dependencies, APIs, and services called by the software during operation.
>     * Guidance: […] Knowing all of the components that comprise a software application or service, where they come from, and how they are updated and maintained is critical to minimizing and managing vulnerabilities in software applications. Without this information, it would be extremely difficult to identify and track vulnerabilities in software components that could expose the embedding software application to attacks. […]

* (PCI-SSC) [PCI-SSF v1.2.1](https://docs-prv.pcisecuritystandards.org/Software%20Security/Standard/PCI-Secure-Software-Standard-v1_2_1.pdf), Published May 2023


## Information Security

* ISO 27001
    * 6.1.3
    * 9.1
    * 7.2
    * 6.1.2
    * 5.2
    * Article 5.24, Article 5.25, Article 5.26
    * …
* CIS Controls V8
* ISO 27036:2023 (3rd party risk)


## License and use of this document

* Version: 0.5.1
* License: [CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/deed)
* Copyright: © Salve J. Nilsen <sjn@cpan.org>, Some rights reserved.

You may use, modify and share this file under the terms of the CC-BY-SA-4.0 license.


### Acknowledgements

People have been involved in the development of this document

* Salve J. Nilsen (main author)
