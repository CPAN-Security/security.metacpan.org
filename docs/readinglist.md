---
layout: page
title: Reading List
toc: true
---

> [!CAUTION]
> ## Document status: ⚠️  DRAFT
> This is The CPAN Security Group recommended reading list.
> If you have any additions or improvements, please [open an issue](https://github.com/CPAN-Security/security.metacpan.org/issues), citing this page.
>
> - Contribute on Github: [https://github.com/CPAN-Security/security.metacpan.org/blob/main/docs/readinglist.md](https://github.com/CPAN-Security/security.metacpan.org/blob/main/docs/readinglist.md)
> - Discuss on IRC: [ircs://ssl.irc.perl.org:7062/#cpan-security](ircs://ssl.irc.perl.org:7062/#cpan-security)


## Software Bills of Materials (SBOM)

* (NTIA) [The Minimum Elements For a Software Bill of Materials (SBOM)](https://www.ntia.doc.gov/files/ntia/publications/sbom_minimum_elements_report.pdf) (July 2021)
* (NSA, ODNI, CISA) [Securing the Software Supply Chain: Recommended Practices for Managing OSS and SBOMs](https://media.defense.gov/2023/Dec/11/2003355557/-1/-1/0/ESF_SECURING_THE_SOFTWARE_SUPPLY_CHAIN%20RECOMMENDED%20PRACTICES%20FOR%20MANAGING%20OPEN%20SOURCE%20SOFTWARE%20AND%20SOFTWARE%20BILL%20OF%20MATERIALS.PDF) (December 2023)
* (NTIA) [Survey of Existing SBOM Formats and Standards](https://www.ntia.gov/sites/default/files/publications/sbom_formats_survey-version-2021_0.pdf) (2021)

### SBOM use cases

* (CDX) [CycloneDX Use Cases](https://cyclonedx.org/use-cases/)
* (SPDX) [A Practical Guide to SPDX](https://fossa.com/learn/spdx)

### Useful articles and papers

* (NTIA) [Software Suppliers Playbook: SBOM Production and Provision](https://www.ntia.gov/files/ntia/publications/software_suppliers_sbom_production_and_provision_-_final.pdf) (November 2021)
* [Managing Open Source and SBOMs](https://resilientcyber.substack.com/p/managing-open-source-and-sboms) (Chris Huges, 2023)
* [Understanding OWASP’s Bill of Material Maturity Model: Not all SBOMs are created equal](https://www.csoonline.com/article/1246904/not-all-sboms-are-created-equal-understanding-owasps-bill-of-material-maturity-model.html) (Chris Huges, 2023)
* (NTIA) [Framing Software Component Transparency: Establishing a Common Software Bill of Materials (SBOM)](https://www.ntia.gov/files/ntia/publications/ntia_sbom_framing_2nd_edition_20211021.pdf) (October 2021)
* (Lawfare Media) [Open-Source Security: How Digital Infrastructure Is Built on a House of Cards](https://www.lawfaremedia.org/article/open-source-security-how-digital-infrastructure-built-house-cards) (July 2022)
* (EU) [The CRA Fact Sheet](https://digital-strategy.ec.europa.eu/en/library/cyber-resilience-act-factsheet)

### Regulations, directives and laws

There are several relevant legislation regarding cybersecurity in Open Source ecosystems and supply chains.

#### USA – EO 14028

* (USA) [Executive Order on Improving the Nation’s Cybersecurity](https://www.whitehouse.gov/briefing-room/presidential-actions/2021/05/12/executive-order-on-improving-the-nations-cybersecurity/) (EO 14028, 2021-05-12)
    * Section 4: Enhancing Software Supply Chain Security

#### USA — H. R. 2617

* FDA (Food and Drug Administration) demands for SBOMs accompaning new medical devices – [H. R. 2617](https://www.congress.gov/117/bills/hr2617/BILLS-117hr2617enr.pdf#page=1374) Section 3305

#### EU and EEA – NIS2

[Directive 2022/2555, Network and Information Security Directive 2](https://eur-lex.europa.eu/eli/dir/2022/2555) (NIS2)

* [Legislative Train Schedule](https://www.europarl.europa.eu/legislative-train/theme-a-europe-fit-for-the-digital-age/file-review-of-the-nis-directive)
* In the [NIS2 Recitals](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX:32022L2555&qid=1710318619717#page=12)
    * Recital (58): On the handling of discovered vulnerabilities (page 12)
    * Recital (62): Access to correct and timely information about vulnerabilities (page 13)
    * Recital (85): On supply-chain risk management (page 17)
    * Recital (89): Adoption of basic cyber hygiene practices (page 17)
    * Recitals (90-91): On coordinated security risk assessments of supply chains (page 18)
* In [Chapter I](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX:32022L2555&qid=1710318619717#page=32)
    * Article 6: Definitions
* In [Chapter II](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX:32022L2555&qid=1710318619717#page=36)
    * Article 7, point 2(a): Creation of a national cybersecurity strategy regarding the security of supply chains for ICT products and services
* In [Chapter IV](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX:32022L2555&qid=1710318619717#page=48)
    * Articles 21, points 1, 2 and 3: **All-hazards approach** to cybersecurity risk-management measures (page 48)

#### EU and EEA – CRA

(EU) [Cyber Resilience Act](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.html) (CRA, updated 2024-03-12)

* In the [CRA Recitals](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=11)
    * Recital (10): CRA relevance for supply chains (page 11)
    * Recitals (16-17): CRA relevance for Open Source projects (page 18-19)
    * Recital (**18**): Open Source Software Contributors (page 20)
    * Recital (**19**): Open Source Software Stewards, light-touch regulatory regime, and CE mark implications (page 22)
    * Recital (**20**): Open Source package managers considerations as "distributors" (page 24)
    * Recitals (21): Voluntary security attestation programs for Open Source projects (page 25)
    * Recitals (22): Submission of SBOMs for Open Source projects (page 26)
    * Recital (24): CRA relevance for the NIS2 directive (page 29)
    * Recital (31): Manufacturer's liability due to lack of security updates (page 36)
    * Recital (34): Due diligence when integrating third-party components (page 39)
    * Recital (37): Software for testing purposes, alphas, betas (page 42)
    * Recital (39): Continued security updates (page 44)
    * Recitals (60-62): Support period (page 69-71)
    * Recital (64): Point of contact (page 73)
    * Recital (65): Secure by default (page 73)
* In the [CRA Chapters](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=136)
    * Chapter I, Article 3: Definitions (pages 136-146)
    * Chapter I, Article 9, Point 1. (b-c): Stakeholder consultation (pages 155-156)
    * Chapter II — Obligations of Economic Operators and Provisions in relation to Free and Open-Source Software
        * Article 13, Obligations of Manufacturers (pages 161-175)
        * **Article 14**, Reporting obligations of manufacturers (pages 176-184)
        * **Article 15**, Voluntary reporting (pages 185-186)
        * Article 16, Establishment of a single reporting platform (pages 187-192)
        * Article 17, Other provisions related to reporting (pages 193-195)
        * Article 18, Authorized representatives (pages 195-196)
        * Article 19, Obligations of importers (pages 197-201)
        * Article 20, Obligations of distributors (pages 202-205)
        * Article 21, Cases in which obligations of manufacturers apply to importers and distributors (page 205)
        * Article 22, Other cases in which obligations of manufacturers apply (page 206)
        * Article 23, Identification of economic operators (page 207)
    * Chapter II – Obligations of open-source software stewards
        * **Article 24**, Obligations of open-source software stewards (pages 208-209)
        * Article 25, Security attestation of free and open-source software (page 210)
        * Article 26, Guidance (pages 211-212)
    * Chapter III — Conformity of the product with digital elements
        * Article 28, EU declaration of conformity (pages 218-219)
        * Article 29, General principles of the CE marking (page 219)
        * Article 30, Rules and conditions for affixing the CE marking (pages 220-222)
    * Chapter V — Market Surveillance and Enforcement
        * Article 58, Formal non-compliance (pages 276)
* In [CRA Annex I](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=297)
    * Essential Cybersecurity Requirements (pages 297-302)
        * Part I — Cybersecurity requirements relating to the properties of products with digital elements (pages 297-300)
        * Part II — Vulnerability handling requirements (pages 300-302)
* In [CRA Annex II](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=303)
    * Information and Instructions to the User (pages 303-305)
* [Legislative Train Schedule](https://www.europarl.europa.eu/legislative-train/theme-a-europe-fit-for-the-digital-age/file-european-cyber-resilience-act)

#### EU and EEA – PLD

(EU) Product Liability Directive (PLD)

* [Legislative Train Schedule](https://www.europarl.europa.eu/legislative-train/theme-a-europe-fit-for-the-digital-age/file-new-product-liability-directive)

#### EU and EEA – DORA

(EU) [Digital Operational Resilience Act](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32022R2554&qid=1710317679922): Regulation (EU) 2022/2554 of the European Parliament and of the Council of 14 December 2022 on digital operational resilience for the financial sector and amending Regulations (DORA, 2022-12-14)

* [Legislative Train Schedule](https://www.europarl.europa.eu/legislative-train/theme-a-europe-fit-for-the-digital-age/file-cross-sectoral-financial-services-act-1)


## Software identification (naming & versioning)

* [PURL Specification](https://github.com/package-url/purl-spec)
* (CPAN) [URI::PackageURL](https://github.com/giterlizzi/perl-URI-PackageURL)
* (CPAN) [CPAN::DistnameInfo](https://github.com/Perl-Toolchain-Gang/CPAN-DistnameInfo)

### Useful articles, papers and resources

* (CISA) [Software Identification Ecosystem Option Analysis](https://www.cisa.gov/resources-tools/resources/software-identification-ecosystem-option-analysis) (October 2023)
* (Repology) [Repology ruleset repo](https://github.com/repology/repology-rules)


## Provenance & Supply Chain Security

* (OpenSSF) [Principles for Package Repository Security](https://repos.openssf.org/principles-for-package-repository-security) (Feb 2024)
* (OpenSSF) [Build Provenance for All Package Registries](https://repos.openssf.org/build-provenance-for-all-package-registries) (July 2023)
* (SLSA) [SLSA v1.0 Guiding Principles](https://slsa.dev/spec/v1.0/principles)
* (SLSA) [SLSA v1.0 Terminology](https://slsa.dev/spec/v1.0/terminologye)
* (SLSA) [SLSA v1.0 Developer's quick-start guide](https://slsa.dev/get-started)
* (SLSA) [SLSA v1.0 Infrastructure provider's quick-start guide](https://slsa.dev/how-to-infra)


## Transparency Logs

* (OpenSSF) [Sigstore home](https://openssf.org/community/sigstore/)
* (OpenSSF) [Sigstore: Simplifying Code Signing for Open Source Ecosystems](https://openssf.org/blog/2023/11/21/sigstore-simplifying-code-signing-for-open-source-ecosystems/)
* (Chainguard.dev) [Life of a Sigstore signature](https://www.chainguard.dev/unchained/life-of-a-sigstore-signature)


## Other articles and guides

* (Checkmarx) [Preparing for Europe’s Most Extensive Cybersecurity Directive, NIS2 – What AppSec teams need to know](https://checkmarx.com/blog/preparing-for-europes-most-extensive-cybersecurity-directive-nis2-what-appsec-teams-need-to-know/)
