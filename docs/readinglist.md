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


### Related regulations, etc.

* (USA) [Executive Order on Improving the Nation’s Cybersecurity](https://www.whitehouse.gov/briefing-room/presidential-actions/2021/05/12/executive-order-on-improving-the-nations-cybersecurity/)
    * Section 4
* (EU) [Directive 2022/2555](https://eur-lex.europa.eu/eli/dir/2022/2555) (NIS 2 Directive)
    * Article 6, Definitions for "manufacturer", "provider"
    * Recitals (58), (62), (85), (89), (90), (91)
    * Chapter II, 2 (a)
    * Chapter IV, Article 21(2) and (3)
* (EU) Directive 2020/1828/EC [Cyber Resilience Act](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CONSIL:ST_17000_2023_INIT) (CRA, 2023-12-20 update)
    * Annex I (Pages 164-167)
        * Essential Cybersecurity Requirements
    * Annex II (Pages 168-169)
        * Recitals (8), (**10a-h**), (18a), (21)
        * Chapter I, Article 3 (Definitions)
        * Chapter II, Article 14 (Obligations of distributors)
        * Chapter II, Article 17a (Obligations of open-source software stewards)
* (EU) [Product Liability Directive](https://www.europarl.europa.eu/legislative-train/theme-a-europe-fit-for-the-digital-age/file-new-product-liability-directive) (PLD)


### Useful articles and papers

* (NTIA) [Software Suppliers Playbook: SBOM Production and Provision](https://www.ntia.gov/files/ntia/publications/software_suppliers_sbom_production_and_provision_-_final.pdf) (November 2021)
* [Managing Open Source and SBOMs](https://resilientcyber.substack.com/p/managing-open-source-and-sboms) (Chris Huges, 2023)
* [Understanding OWASP’s Bill of Material Maturity Model: Not all SBOMs are created equal](https://www.csoonline.com/article/1246904/not-all-sboms-are-created-equal-understanding-owasps-bill-of-material-maturity-model.html) (Chris Huges, 2023)
* (NTIA) [Framing Software Component Transparency: Establishing a Common Software Bill of Materials (SBOM)](https://www.ntia.gov/files/ntia/publications/ntia_sbom_framing_2nd_edition_20211021.pdf) (October 2021)
* (Lawfare Media) [Open-Source Security: How Digital Infrastructure Is Built on a House of Cards](https://www.lawfaremedia.org/article/open-source-security-how-digital-infrastructure-built-house-cards) (July 2022)
* (EU) [The CRA Fact Sheet](https://digital-strategy.ec.europa.eu/en/library/cyber-resilience-act-factsheet)


## Software identification

* [PURL Specification](https://github.com/package-url/purl-spec)
* (CPAN) [URI::PackageURL](https://github.com/giterlizzi/perl-URI-PackageURL)
* (CPAN) [CPAN::DistnameInfo](https://github.com/Perl-Toolchain-Gang/CPAN-DistnameInfo)


### Useful articles and papers

* (CISA) [Software Identification Ecosystem Option Analysis](https://www.cisa.gov/resources-tools/resources/software-identification-ecosystem-option-analysis) (October 2023)


## Provenance & Supply Chain Security

* (OpenSSF) [Principles for Package Repository Security](https://repos.openssf.org/principles-for-package-repository-security) (Feb 2024)
* (SLSA) [SLSA v1.0 Guiding Priciples](https://slsa.dev/spec/v1.0/principles)
* (SLSA) [SLSA v1.0 Terminology](https://slsa.dev/spec/v1.0/terminologye)
* (SLSA) [SLSA v1.0 Developer's quick-start guide](https://slsa.dev/get-started)
* (SLSA) [SLSA v1.0 Infrastructure provider's quick-start guide](https://slsa.dev/how-to-infra)
