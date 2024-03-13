---
layout: page
title: Reading List
toc: true
---

This is The CPAN Security Group recommended reading list. If you have any additions or improvements, please [open an issue](https://github.com/CPAN-Security/security.metacpan.org/issues), citing this page.


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


# Regulations, directives and laws

* (USA) [Executive Order on Improving the Nation’s Cybersecurity](https://www.whitehouse.gov/briefing-room/presidential-actions/2021/05/12/executive-order-on-improving-the-nations-cybersecurity/)
    * Section 4
* (EU) [Directive 2022/2555, Network and Information Security Directive 2](https://eur-lex.europa.eu/eli/dir/2022/2555) (NIS2)
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
* (EU) [Directive 2020/1828/EC, the Cyber Resilience Act](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CONSIL%3AST_17000_2023_INIT&qid=1710309054521) (CRA, updated 2023-12-20)
    * [Legislative Train Schedule](https://www.europarl.europa.eu/legislative-train/theme-a-europe-fit-for-the-digital-age/file-european-cyber-resilience-act)
    * In the [CRA Recitals](https://data.consilium.europa.eu/doc/document/ST-17000-2023-INIT/EN/pdf#page=7)
        * Recital (8): CRA relevance for supply chains (page 7)
        * Recitals (10a-b): CRA relevance for Open Source projects (page 10-11)
        * Recital (**10c**): Open Source Software Contributors (page 12)
        * Recital (**10d**): Open Source Software Stewards, light-touch regulatory regime, and CE mark implications (page 13)
        * Recital (**10e**): Open Source package managers considerations as "distributors" (page 14)
        * Recitals (10f): Voluntary security attestation programs for Open Source projects (page 14)
        * Recitals (10g): Submission of SBOMs for Open Source projects (page 14)
        * Recital (11): CRA relevance for the NIS2 directive (page 16)
        * Recital (16): Manufacturer's liability due to lack of security updates (page 21)
        * Recital (18a): Due diligence when integrating third-party components (page 23)
        * Recital (21): Software for testing purposes, alphas, betas (page 24)
        * Recital (22b): Continued security updates (page 27)
        * Recitals (33a-c): Support period (page 38-39)
        * Recital (33e): Point of contact (page 40)
        * Recital (33f): Secure by default (page 40)
    * In the [CRA Chapters](https://data.consilium.europa.eu/doc/document/ST-17000-2023-INIT/EN/pdf#page=75)
        * Chapter I, Article 3: Definitions (pages 75-80)
        * Chapter I, Article 6 (b-c): Stakeholder consultation (pages 86-87)
        * Chapter II, Articles 10, 11, 13, 14, 15, 16: Obligations of Economic Operators and Provisions in relation to Free and Open-Source Software (pages 90-113)
        * Chapter II, Articles 17 (a-c): Obligations of open-source software stewards (pages 113-115)
        * Chapter III, Articles 20, 21, 22: EU declaration of conformity (pages 119-121)
    * In [CRA Annex I](https://data.consilium.europa.eu/doc/document/ST-17000-2023-INIT/EN/pdf#page=164)
        * Essential Cybersecurity Requirements (pages 164-167)
    * In [CRA Annex II](https://data.consilium.europa.eu/doc/document/ST-17000-2023-INIT/EN/pdf#page=168)
        * Information and Instructions to the User (pages 168-169)
    * [CRA Legislative Procedure](https://eur-lex.europa.eu/procedure/EN/2022_272) Status page
* (EU) [Product Liability Directive](https://www.europarl.europa.eu/legislative-train/theme-a-europe-fit-for-the-digital-age/file-new-product-liability-directive) (PLD)
    * [Legislative Train Schedule](https://www.europarl.europa.eu/legislative-train/theme-a-europe-fit-for-the-digital-age/file-new-product-liability-directive)
* (EU) [Digital Operational Resilience Act](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32022R2554&qid=1710317679922): Regulation (EU) 2022/2554 of the European Parliament and of the Council of 14 December 2022 on digital operational resilience for the financial sector and amending Regulations (DORA, 2022-12-14)
    * [Legislative Train Schedule](https://www.europarl.europa.eu/legislative-train/theme-a-europe-fit-for-the-digital-age/file-cross-sectoral-financial-services-act-1)

## Articles and guides

* (Checkmarx) [Preparing for Europe’s Most Extensive Cybersecurity Directive, NIS2 – What AppSec teams need to know](https://checkmarx.com/blog/preparing-for-europes-most-extensive-cybersecurity-directive-nis2-what-appsec-teams-need-to-know/)
