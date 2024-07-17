---
layout: page
title: An EU Cyber Resilience Act Summary 
description: A short overview of the parts of the CRA that affect different entities in Open Source supply-chains
toc: true
mermaid: true
---

## Document status: ⚠️  DRAFT

> [!CAUTION]
> What you see here is a DRAFT overview by the CPAN Security Group (CPANSec) of the core obligations set out by the EU Cyber Resilience Act, as applied to Open Source ecosystems and supply chains,
> As long as this document is in DRAFT, all of the points and ideas below are _suggestions_, and open to revision, deletion or amending – by you!
>
> - Contribute on Github: [https://github.com/CPAN-Security/security.metacpan.org/tree/cra-summary/docs/eu-cra-summary.md](https://github.com/CPAN-Security/security.metacpan.org/tree/cra-summary/docs/eu-cra-summary.md)
> - Discuss on IRC: [ircs://ssl.irc.perl.org:7063/#cpan-security](ircs://ssl.irc.perl.org:7063/#cpan-security)


## About this document

This text attempts to summarize the most important parts of the CRA, for Open Source ecosystems.

For license information and acknowledgements, see the [end of this document](#license-and-use-of-this-document).


### Manufacturers

(Art 13 to Art 17, Art 18 for authorised representatives)

* Manufacturers are obliged to exercise due diligence when integrating components from third parties. ([Article 13(5)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=163))
  * …after the Manufacturer conducts a risk assessment, as laid out in [Article 13(2)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=161)
  * …in accordance with essential requirements laid out in [Annex I, Part I](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=297).
* …must report on actively exploited vulnerabilities and severe incidents via an ENISA-run single reporting platform (as laid out in [Article 16](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=187)), in the way described in [Article 14](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=176).
* …required to report discovered vulnerabilities in components to their maintainers. ([Article 13(6)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=164))


* …Testing necessary, provide technical documentation, as laid out in [Article 13(6)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=164).⚠️
* …Vulnerability management
* …perform risk assessments
* …Coordinated vulnerability disclosure (CVD) policy mandatory
* …CE Marking: must feature a CE marking to indicate conformity prior to entering the market, keep records for ten years

* …must provide Software Bill of Materials (SBOM) upon request by authorities, but no need for publication
* …offer support for their products for at least 5 years, security updates for 10 years

### Open Source Stewards

* Open Source Stewards are obliged to
  * …facilitate the Manufacturer's due diligence obligation set out in [Article 13(5)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=163)⚠️
  * …provide a cybersecurity policy for voluntary reporting of vulnerabilities, as laid out in [Article 15](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=185)
  * …cooperate with market surveillance authorities and provide documentation
  * …report on actively exploited vulnerabilities and severe incidents via an ENISA-run single reporting platform (as laid out in [Article 16](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=187)), in the way described in [Article 14](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=176).

* FOSS Software may get a voluntary security attestation, as described in [Article 25](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=210)⚠️
  * …using an EU Attestation program as laid out in [Recital (21)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=25)
    * …by requesting a certification from ENISA, as laid out in [Regulation (EU) 2019/881, Article (48)](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX:32019R0881#page=8)
    * …in such a way that this security attestation can be initiated or financed by not only FOSS projects, but also by others, including manufacturers, users, or public administrations.
    * …so this Attestation becomes a "proof of due diligence exercised"? ⚠️  FIXME: (Dis)confirm this.
  * …to facilitate Manufacturers' obligations to exercise due diligence when integrating components from third parties.


## An idealized Open Source Steward Supply-Chain graph

```mermaid
stateDiagram-v2
    direction TB

    state "🟥🟨🟦 Maintainer Environment" as environment_maintainer
    state "🟩 Collaboration Ecosystem" as ecosystem_repo
    state "🟨🟩 Language Ecosystem" as ecosystem_lang
    state "🟨🟩 Package Ecosystem" as ecosystem_package
    state "🟥 Attestation Authority" as authority_attestation
    state "🟥🟨🟩🟦 OSS Steward" as ecosystem_steward
    %%state "🟩 Content Delivery Network" as network_delivery
    state "🟥🟨 Integrator Environment" as environment_integrator
    state "🟥🟨🟦🟪 Manufacturer Environment" as environment_manufacturer
    state "🟦 Production Environment" as environment_prod
    state "🟦 Auditor" as authority_auditor

    [*]                      --> environment_maintainer
    ecosystem_repo           --> environment_maintainer
    %%environment_maintainer   --> network_delivery
    ecosystem_repo           --> ecosystem_lang
    environment_maintainer   --> ecosystem_lang
    ecosystem_lang           --> ecosystem_lang
    environment_maintainer   --> ecosystem_repo
    %%ecosystem_lang           --> network_delivery
    ecosystem_repo           --> ecosystem_package
    ecosystem_lang           --> ecosystem_package
    ecosystem_package        --> ecosystem_package
    %%ecosystem_package        --> network_delivery
    %%network_delivery         --> environment_integrator
    ecosystem_package        --> ecosystem_steward
    ecosystem_lang           --> ecosystem_steward
    authority_attestation    --> ecosystem_steward
    ecosystem_repo           --> environment_integrator
    ecosystem_lang           --> environment_integrator
    ecosystem_package        --> environment_integrator
    ecosystem_steward        --> environment_manufacturer
    environment_integrator   --> environment_prod
    environment_manufacturer --> environment_prod
    environment_manufacturer --> authority_auditor
    environment_prod         --> [*]

    %% Copyright © 2024 Salve J. Nilsen <sjn@oslo.pm>
    %% Some rights reserved. Licenced CC-BY-SA-4.0
```


## Are you… a Manufacturer, Steward or Author?

```mermaid
graph TB
    start-here(Start here) --> involved{"Involved<br>with OSS products?<br>CRA Recital (18)"}
    involved  -->|No| not-relevant-for-you("This chart isn't<br>relevant for you")
    involved -->|Yes| contributing{"Contributing<br>unpaid to OSS?<br>CRA Recital (18)"}
    contributing  -->|No| monetised{"Monetizing<br>the product?<br>CRA Recital (18)"}
    contributing -->|Yes| cra-is-out-of-scope(CRA is out-of-scope)
    monetised -->|Yes| cra-manufacturer("CRA is in-scope<br>You are a Manufacturer<br>CRA Recital (18), (15)")
    monetised -->|No| is-legal-entity{"Legal person,<br> but not natural person?<br>CRA Recital (19)"}
    is-legal-entity -->|Yes| intended-commercial-use{"Is product<br>intended for<br>commerial use?<br>CRA Recital (19)"}
    is-legal-entity -->|No| cra-is-out-of-scope
    intended-commercial-use -->|No| cra-is-out-of-scope
    intended-commercial-use -->|Yes| product-supporter{"Providing<br>support for OSS<br>products?<br>CRA Recital (18)"}
    product-supporter -->|Yes| cra-oss-steward("CRA in-scope<br>You are an Open-Source Software Steward<br>CRA Article 3 (14)")
    product-supporter -->|No| cra-is-out-of-scope

    %% Based on the flowchart made by Maarten Aertsen (NLNetLabs) found at
    %% https://blog.nlnetlabs.nl/what-i-learned-in-brussels-the-cyber-resilience-act/

    %% Original flowchart © Maarten Aertsen <maarten@nlnetlabs.nl>
    %% License: CC0 1.0 Universal
    %% Adapted to Mermaid and modified by Salve J. Nilsen <sjn@oslo.pm>
```


## References

* (CISA-2024)  [CISA SBOM Sharing Roles and Considerations](https://www.cisa.gov/resources-tools/resources/sbom-sharing-roles-and-considerations), published 2024-03-28.
* (CRA-AII)    [Cyber Resilience Act, Annex II](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=303) Information and Instructions to the User, Dated 2024-03-12
* (CRA-AV)     [Cyber Resilience Act, Annex V](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=311) EU Declaration of Conformity, Dated 2024-03-12
* (CRA-AVII)   [Cyber Resilience Act, Annex VII](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=314) Contents of the Technical Documentation, Dated 2024-03-12
* (CRA-Art-3)  [Cyber Resilience Act, Article 3](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=136) Definitions, Dated 2024-03-12
* (CRA-Art-20) [Cyber Resilience Act, Article 20](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=202) Obligations of distributors, Dated 2024-03-12
* (CRA-Art-47) [Cyber Resilience Act, Article 47](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=249) Operational obligations of notified bodies, Dated 2024-03-12
* (CRA-Rec-15) [Cyber Resilience Act, Recital 15](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=17) Economic operators, Dated 2024-03-12
* (CRA-Rec-18) [Cyber Resilience Act, Recital 18](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=20) Open Source Software Contributors, Dated 2024-03-12
* (CRA-Rec-19) [Cyber Resilience Act, Recital 19](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=22) Open Source Software Stewards, Dated 2024-03-12
* (DE-TR) German Technical Requirement [TR-03183 Cyber Resilience Requirements for Manufacturers and Products (part 2)](https://bsi.bund.de/dok/TR-03183), Version 1.1, published 2023-11-28.
* (NTIA-2021) [SBOM Tool Classification Taxonomy](https://www.ntia.gov/files/ntia/publications/ntia_sbom_tooling_taxonomy-2021mar30.pdf), published 2021-03-30.
* (NTIA-SBOM) [NTIA Minimum Elements for a Software Bill of Materials (SBOM)](https://www.ntia.doc.gov/files/ntia/publications/sbom_minimum_elements_report.pdf#page=9), Published 2021-07-12

* (CPANSec-2024) CPAN Security Group commentary by Author.


## License and use of this document

* Version: 0.5.1
* License: [CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/deed)
* Copyright: © Salve J. Nilsen <sjn@oslo.pm>, Some rights reserved.

You may use, modify and share this file under the terms of the [CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/deed) license.


### Acknowledgements

Several people have been involved in the development of this document

* Salve J. Nilsen (main author)