---
layout: page
title: Glossary of Terms
description: List of terms used throughout CPANSec projects
toc: true
---

## Document status: ⚠️  DRAFT

> [!CAUTION]
> What you see here is a DRAFT of the Glossary used by the CPAN Security Group (CPANSec).
> As long as this document is in DRAFT, all of the points and ideas below are _suggestions_, and open to revision, deletion or amending – by you!
>
> - Contribute on Github: [https://github.com/CPAN-Security/security.metacpan.org/blob/main/docs/glossary.md](https://github.com/CPAN-Security/security.metacpan.org/blob/main/docs/glossary.md)
> - Discuss on IRC: [ircs://ssl.irc.perl.org:7062/#cpan-security](ircs://ssl.irc.perl.org:7062/#cpan-security)

### Legend

> [!NOTE]
> * ⚠️  — The definition has problems or errors or may be confusing, and therefore requires correction or additional explanation.
> * ✍️  — Changes have been made to the original definition, mostly for clarity or consistency.


## Glossary

### Artifact ✍️

> [!NOTE]
> Component and Artifact seem to have overlapping definitions.
> We recommend using the term Artifact specifically when referring to files (as defined), and Component in other situations. (CPANSec)

> 1. An immutable blob of data; primarily refers to [software](#software), but SLSA can be used for any artifact.
>     * E.g. a file, a git commit, a directory of files (serialized in some way), a container image, a firmware image.
>
> See also: [Component](#component-).
>
> (Ref: [SLSA 2023](#references-and-terms), CPANSec 2024)

### Author

> 1. An entity that creates an SBOM.
> > 1. [author](#author) and [supplier](#supplier) will often be different. In the case of SBOMs, the author creates the SBOM. The supplier is the provider of the software included in the SBOM (NTIA 2021)
> 2. A developer that publishes something as Open Source software. (CPANSec 2024)
>
> See also: [Author](supplychain-sbom#author) in the Supply-chain SBOM Roles document.
>
> (Ref: [NTIA 2021](#references-and-terms), CPANSec 2024)


### Attestation

> 1. An authenticated statement (metadata) about a software artifact or collection of software artifacts.
>     * E.g. a signed SLSA Provenance file.
>
> (Ref: [SLSA 2023](#references-and-terms))

### Build

> 1. Process that transforms a set of input artifacts into a set of output artifacts.
>     * The inputs may be sources, dependencies, or ephemeral build outputs.
>     * E.g. .travis.yml (process) run by Travis CI (platform).
>
> (Ref: [SLSA 2023](#references-and-terms))

### CE Marking ⚠️

> 1. A marking by which a manufacturer indicates that a product with digital elements and the processes put in place by the manufacturer are in conformity with the essential requirements set out in [EU Cyber Resilience Act, Annex I](#other-supporting-matter) and other applicable European Union harmonization legislation providing for its affixing.
>
> (Ref: [CRA 2024-03](#references-and-terms))

### Chain of custody

> 1. Auditable documentation of point of origin as well as the method of transfer from point of origin to point of destination and the identity of the transfer agent.
>
> (Ref: [SCVS 2020](#references-and-terms))

### Component ✍️

> [!NOTE]
> Component and Artifact seem to have overlapping definitions.
> We recommend using the term Artifact specifically when referring to files (as defined), and Component in other situations. (CPANSec)

> 1. Software or hardware intended for integration into an [electronic information system](#electronic-information-system). (CRA 2024-03)
> 2. A unit of software defined by a supplier at the time the component is built, packaged, or delivered. Many components contain sub-components. Examples of components include a software product, a device, a library, or a single file. (NTIA 2021)
>
> See also: [Artifact](#artifact-).
>
> (Ref: [CRA 2024-03](#references-and-terms), NTIA 2021, CPANSec 2024)

#### Component function

> 1. The purpose for which a software component exists.
>     * Examples of component functions include parsers, database persistence, and authentication providers.
>
> (Ref: [SCVS 2020](#references-and-terms))

#### Component, second-party ✍️

> 1. Any software component created through the interaction with a second party, including open source, "source available", and proprietary software where the source is made available for either inspection, use, modification, building or sharing. (CPANSec)
>     * Open Source software components that are dependencies should be considered as "second-party components", since the user of these components have an ongoing legal relationship with the FOSS component project, by the fact that the user has accepted the project license.
>
> (Ref: [SCVS 2020](#references-and-terms), CPANSec 2024)

#### Component, third-party ✍️

> 1. Any software component not directly created including open source, "source available", and commercial or proprietary software. (SCVS 2020)
> 2. Any software component not directly created including "source available", commercial or proprietary software. (CPANSec 2024)
>     * Open Source software components that are dependencies should be considered as "second-party components", since the user of these components have an ongoing legal relationship with the FOSS component project, by the fact that the user has accepted the project license.
>
> (Ref: [SCVS 2020](#references-and-terms), CPANSec 2024)

#### Component type

> 1. The general classification of a software components architecture.
>     * Examples of component types include libraries, frameworks, applications, containers, and operating systems.
>
> (Ref: [SCVS 2020](#references-and-terms))

### Consumer

> 1. Entity that obtains SBOMs. (NTIA 2021)
>     * An entity can be both a supplier and consumer, using components with SBOM data in its own software, which is then passed downstream.
>     * An “end-user” consumer (that is not also a supplier) may also be called an operator or a leaf entity.
>
> (Ref: [NTIA 2021](#references-and-terms))


### CycloneDX ✍️

> 1. An OWASP managed software bill of materials specification designed to be lightweight and security-focused. (SCVS 2020)
>     * CycloneDX is considered to be one of the three [SBOM](#sbom--software-bill-of-materials-) formats, together with [SWID](#software-identification--swid-) and [SPDX](#software-package-data-exchange--spdx-).
>
> (Ref: [SCVS 2020](#references-and-terms), CPANSec 2024)

### Dependency ⚠️  ✍️

> 1. An [Artifact](#artifact) that is an input to a build process but that is not a source. (SLSA 2023)
>     * In the SLSA model, it is always a package.
>     * E.g. an Alpine package ([package](#package---)) distributed on Alpine Linux ([platform](#platform)).
> 2. Characterizing the relationship that an upstream component X is ~~included~~ in software Y. (NTIA 2021) ⚠️

> [!NOTE]
> * Dependencies may be referenced, included, development/build/test/deploy/runtime phase-specific, dynamic, static, unresolved, resolved, embedded, direct or transitive. The definition above is, in this sense, entirely insufficient. (CPANSec 2024)
>
> (Ref: [SLSA 2023](#references-and-terms), NTIA 2021, CPANSec 2024)

#### Dependency (Direct) ✍️

> 1. A software component that is referenced by a ~~program~~ [software](#software) itself. (SCVS 2020)
>
>> NOTE: A program, library, plugin, or component. (CPANSec 2024)
>
> For indirect dependencies, see [Dependency (Transitive)](#dependency-transitive-).
>
> (Ref: [SCVS 2020](#references-and-terms), CPANSec 2024)

#### Dependency (Transitive) ✍️

> 1. A software component that is indirectly used by a program by means of being a dependency of a dependency. (SCVS 2020)
> 2. Characterizing the relationship that if an upstream component X is included in software Y and component Z is included in component X then component Z is included in software Y. (NTIA 2021)
>
>> NOTE: Dependencies of transitive dependencies are also transitive dependencies (it's dependencies all the way down!). (CPANSec 2024)
>
> See also: [Dependency (Direct)](#dependency-direct-).
>
> (Ref: [SCVS 2020](#references-and-terms), NTIA 2021, CPANSec 2024)

#### Dependency (Embedded) ✍️

> FIXME

#### Dependency (Required, Unresolved) ✍️

> FIXME

#### Dependency (Resolved) ✍️

> FIXME

#### Dependency (Pinned) ✍️

> FIXME

### Distributor ⚠️

> [!WARNING]
> The Cyber Resilience Act defines a distributor as someone who **does not** [Substantially Modify](#substantial-modification) a package/component.
> This means if an [Importer](#importer) or distributor applies a patch with [Substantial Modifications](#substantial-modification), they are to be treated as a [manufacturer](#manufacturer), including any consequences this may entail. (CRA 2024-03 Article 21, 22)
>
> FIXME: Confirm with lawyer after final version of CRA is adopted.

> 1. A natural or legal person in the supply chain, other than the manufacturer or the importer, that makes a product with digital elements available on the Union market without affecting its properties. (2024-03)
>
> (Ref: [CRA 2024-03](#references-and-terms))

### Downstream

> 1. Referring to how a component is subsequently used in other pieces of software at a later stage in the supply chain. (NTIA 2021)
>
> (Ref: [NTIA 2021](#references-and-terms))

### Electronic information system

> 1. A system, including electrical or electronic equipment, capable of processing, storing or transmitting digital data. (CRA 2024-03)
>
> (Ref: [CRA 2024-03](#references-and-terms))

### Hardware

> 1. A physical electronic information system, or parts thereof capable of processing, storing or transmitting digital data. (CRA 2024-03)
>
> (Ref: [CRA 2024-03](#references-and-terms))

### Importer

> 1. A natural or legal person established in the Union who places on the market a product with digital elements that bears the name or trademark of a natural or legal person established outside the European Union. (CRA 2024-03)
>
> (Ref: [CRA 2024-03](#references-and-terms))

### Life-cycle Phase

> 1. The stage in the software life-cycle where an SBOM is generated (e.g. from source, at the time of build or packaging, or from a built executable). (NTIA 2021)
>
> (Ref: [NTIA 2021](#references-and-terms))

### Making available on the market

> The supply of a product with digital elements for distribution or use on the European Union market in the course of a commercial activity, whether in return for payment or free of charge. (CRA 2024-03)
>
> (Ref: [CRA 2024-03](#references-and-terms))

> FIXME: Add some clarification regarding Manufacturers, Importers, Distributors and Open Source Stewards.

### Manufacturer

> 1. Any natural or legal person who develops or manufactures products with digital elements or has products with digital elements designed, developed or manufactured, and markets them under his or her name or trademark, whether for payment, monetisation or free of charge.
>
> (Ref: [CRA 2024-03](#references-and-terms))

### Open-source software

> 1. Software that can be accessed, used, modified, and shared by anyone. (NTIA 2021)
>
> (Ref: [NTIA 2021](#references-and-terms))

### Open-source software steward ⚠️

> [!NOTE]
> FIXME: This is a definition that was added to the CRA on 2023-12-20, meaning it may change in the final version of the regulation.

> 1. Any legal person, other than a [manufacturer](#manufacturer), which has the purpose or objective to systematically provide support on a sustained basis for the development of specific products with digital elements qualifying as free and open-source software that are intended for commercial activities, and ensures the viability of those products.
>
> (Ref: [CRA 2024-03](#references-and-terms))

### Package ⚠️  ✍️

> 1. [An] [Artifact](#artifact-) that is “published” for use by others. (SLSA 2023)
>     * In the model, it is always the output of a build process, though that build process can be a no-op.
>     * E.g. a Docker image (package) distributed on DockerHub (platform).
>     * E:g. a ZIP file containing source code is a package, not a source, because it is built from some other source, such as a git commit.
> 2. An identifiable unit of software intended for distribution, ambiguously meaning either an “artifact” or a “package name”. (SLSA 2023)
>     * Only use this term when the ambiguity is acceptable or desirable.
>
> (Ref: [SLSA 2023](#references-and-terms), CPANSec 2024)

### Package manager ✍️

> 1. A distribution mechanism that makes software artifacts discoverable by ~~requesters~~ users of a specific package ecosystem.
>
> (Ref: [SCVS 2020](#references-and-terms), CPANSec 2024)

### Package URL (PURL)

> 1. An ecosystem-agnostic specification which standardizes the syntax and location information of software components. The PURL spec can be found in [GitHub](https://github.com/package-url/purl-spec). As it is an open source project it is constantly evolving.
>
> (Ref: [SCVS 2020](#references-and-terms))

### Pedigree

> 1. Data which describes the lineage and/or process for which software has been created or altered. (SCVS 2020)
> 2. Data on the origins of components that have come together to make a piece of software and the process under which they came together. This could include data beyond the minimum elements, such as compiler details and settings. (NTIA 2021)
>
> (Ref: [SCVS 2020](#references-and-terms), NTIA 2021)

### Placing on the market

> 1. The first making available of a product with digital elements on the Union market. (CRA 2024-03)
>
> (Ref: [CRA 2024-03](#references-and-terms))


### Point of origin ✍️

> [!WARNING]
> Discouraged term. Confusing definition, having common meaning with both [Source](#source---), [Manufacturer](#manufacturer) and [Distributor](#distrubutor-). (CPANSec)

> 1. The supplier and associated metadata from which a software component has been procured, transmitted, or received. (SCVS)
>     * ~~Package repositories, release distribution platforms, and version control history are examples of various points of origin.~~
>
> (Ref: [SCVS 2020](#references-and-terms), CPANSec 2024)

### Procurement ✍️

> 1. The process of agreeing to terms and acquiring software or services for later use. (SCVS 2020)
>     * This includes agreeing to Open Source licenses. (CPANSec 2024)
>
> (Ref: [SCVS 2020](#references-and-terms), CPANSec 2024)

### Product with digital elements

> 1. A software or hardware product and its [Remote Data Processing](#remote-data-processing) solutions, including software or hardware components being placed on the market separately. (CRA 2024-03)
>
> (Ref: [CRA 2024-03](#references-and-terms))

### Provenance ✍️

> 1. The [chain of custody](#chain-of-custody) and origin of a software component.
>     * Provenance incorporates the [point of origin](#point-of-origin-) through ~~distribution~~ [distributor](#distributor-) as well as derivatives in the case of software that has been modified. (SCVS 2020)
> 2. Data about the chain of custody of the software and all of the constituent components, potentially including data about the authors and locations from where the components were obtained. (NTIA 2021)
>
> (Ref: [SCVS 2020](#references-and-terms), NTIA 2021, CPANSec 2024)

### Remote Data Processing

> 1. Data processing at a distance the software for which is designed and developed by the manufacturer, or under the responsibility of the manufacturer, and the absence of which would prevent the product with digital elements from performing one of its functions. (CRA 2024-03)
>
> (Ref: [CRA 2024-03](#references-and-terms))


### Second-party component ✍️

> See [Component, second-party](#component-second-party-).

### SBOM (Software Bill of Materials)

> 1. A formal record containing details and supply chain relationships of components included in the software elements of a product with digital elements. (CRA 2024)
> 2. A complete, formally structured, and machine-readable inventory of all software components and associated metadata, used by or delivered with a given piece of software. (SCVS 2020)
> 3. A formal record containing the details and supply chain relationships of various components used in building software. (NTIA 2021)
>     * Software developers and vendors often create products by assembling existing open source and commercial software components.
>     * The SBOM enumerates these components in a product.
>
> (Ref: [CRA 2024-03](#references-and-terms), SCVS 2020, NTIA 2021)

### SBOM Roles

> "Data is only good if it is in the hands of the right people." (CISA 2024)
>
> (Ref: [CISA 2024](#references-and-terms))


#### SBOM Assembler (Role) ✍️

> 1. Someone that gathers, assembles or updates SBOMs from different sources into a new SBOM. (CPANSec 2024)
>     * This is a _proposed_ Role separate from "SBOM Author" for clarifying the responsibility when the Role intends to _gather_, _assemble_ or _update_ metadata fields, instead of being the authoritative source of a field.
>     * This assumes some fields may be in need of updating as an SBOM is passed down a supply-chain – for example to correct upstream assumptions like 'Download location', add missing fields, or update the list of resolved dependencies.
>     * The intention is to distinguish between "SBOM Author" and "SBOM Assembler" in the same way as one distinguishes between "Create" and "Update" in CRUD – to clarify responsibilities and expectations for who is the original source of some metadata fields.
> (Ref: CPANSec 2024)


#### SBOM Author (Role) ✍️

> 1. The creator of an SBOM. (CISA 2024)
> 2. The Authoritative source of an SBOM. (CPANSec 2024)
>
> (Ref: [CISA 2024](#references-and-terms), CPANSec 2024)

#### SBOM Distributor (Role)

> 1. Receives SBOMs for the purpose of sharing them with [SBOM Consumers](#sbom-consumer--role-) or other Distributors. (CISA 2024)
>
> (Ref: [CISA 2024](#references-and-terms))

#### SBOM Consumer (Role)

> 1. Receives the transferred SBOM. (CISA 2024)
>      * This could include roles such as third parties, authors, integrators, and end users.
>
> (Ref: [CISA 2024](#references-and-terms))


### SBOM Types

> 1. [Software Bill of Materials](#sbom-software-bill-of-materials) variations, produced under certain circumstances.
>
> (Ref: [CPANSec 2024](#references-and-terms))

#### Design SBOM (Type)

> 1. SBOM of intended, planned software project or product with included components (some of which may not yet exist) for a new software artifact.
>
> (Ref: [CISA 2023](#references-and-terms))

#### Source SBOM (Type)

> 1. SBOM created directly from the development environment, source files, and included dependencies used to build an product artifact.
>
> (Ref: [CISA 2023](#references-and-terms))

#### Build SBOM (Type)

> 1. SBOM generated as part of the process of building the software to create a releasable artifact (e.g., executable or package) from data such as source files, dependencies, built components, build process ephemeral data, and other SBOMs.
>
> (Ref: [CISA 2023](#references-and-terms))

#### Analyzed SBOM (Type)

> 1. SBOM generated through analysis of artifacts (e.g., executables, packages, containers, and virtual machine images) after its build.
>     * Such analysis generally requires a variety of heuristics.
>     * In some contexts, this may also be referred to as a “3rd party” SBOM.
>
> (Ref: [CISA 2023](#references-and-terms))

#### Deployed SBOM (Type)

> 1. SBOM provides an inventory of software that is present on a system.
>     * This may be an assembly of other SBOMs that combines analysis of configuration options, and examination of execution behavior in a (potentially simulated) deployment environment.
>
> (Ref: [CISA 2023](#references-and-terms))

#### Runtime SBOM (Type)

> 1. SBOM generated through instrumenting the system running the software, to capture only components present in the system, as well as external call-outs or dynamically loaded components.
>    *  In some contexts, this may also be referred to as an “Instrumented” or “Dynamic” SBOM.
>
> (Ref: [CISA 2023](#references-and-terms))

### Software

> 1. The part of an electronic information system which consists of computer code. (CRA 2024-03)
>
> (Ref: [CRA 2024-03](#references-and-terms))

### Software Bill of Materials (SBOM)

> 1. See [SBOM (Software Bill of Materials](#sbom--software-bill-of-materials-).

### Software Identification (SWID)

> 1. An ISO standard that formalizes how software is tagged.
>    * SWID is considered to be one of three [SBOM](#sbom--software-bill-of-materials-) formats, together with [CycloneDX](#cyclonedx--) and [SPDX](#software-package-data-exchange--spdx-).
>
> (Ref: [SCVS 2020](#references-and-terms))

### Software Package Data Exchange (SPDX)

> 1. A Linux Foundation project which produces a [software bill of materials](#sbom-software-bill-of-materials) specification and a standardized list of open source licenses. (SCVS 2020)
>     * SPDX is considered to be one of three [SBOM](#sbom--software-bill-of-materials-) formats, together with [CycloneDX](#cyclonedx--) and [SWID](#software-identification--swid-).
>
> (Ref: [SCVS 2020](#references-and-terms))

### Source ⚠️  ✍️

> 1. An [artifact](#artifact) that was directly authored ~~or reviewed~~ by persons, without modification. (SLSA 2023)
>     * It is the beginning of the supply chain; we do not trace the provenance back any further.
>     * E.g. a git commit (source) hosted on GitHub ([platform](#platform)).
>
> (Ref: [SLSA 2023](#references-and-terms), CPANSec 2024)

### SPDX (Software Package Data Exchange)

> See [Software Package Data Exchange (SPDX)](#software-package-data-exchange--spdx-).

### Substantial Modification

> 1. A change to the product with digital elements following its placing on the market, which affects the compliance of the product with digital elements with the essential requirements set out in the EU Cyber Resilience Act, Annex I, Part I, or which results in a modification to the intended purpose for which the product with digital elements has been assessed. (CRA 2024-03)
>     * Where products with digital elements are subsequently modified, by physical or digital means, in a way that is not foreseen by the manufacturer [...], the modification should be considered as substantial. (CRA 2024-03 Recital 38)
>     * Security updates are not Substantial Modifications. (CRA 2024-03 Recital 39)
>
> (Ref: [CRA 2024-03](#references-and-terms))


### Supplier

> 1. An entity that creates, defines, and identifies components and produces associated SBOMs. (NTIA 2021)
>     * A supplier may also be known as a manufacturer, vendor, developer, integrator, maintainer, or provider.
>     * Ideally, all suppliers are also authors of SBOMs for the suppliers’ components.
>     * Most suppliers are also consumers.
>     * A supplier with no included upstream components is a root entity.
>
> (Ref: [NTIA 2021](#references-and-terms))

### SWID (Software Identification)

> See [Software Identification (SWID)](#software-identification--swid-).

### Third-party component ✍️

> See [Component, third-party](#component-third-party-).

### Transitive Dependency

> See [Dependency (Transitive)](#dependency--transitive-)

### Vendor

> See [Manufacturer](#manufacturer) or [Author](#author).


## References and terms

This glossary is partly based on terms from the following sources.

- (CPANSec 2024) – These are commentary and proposed improvements made by the author(s) of this document.
- (CISA 2023) CISA [Types of Software Bill of Materials (SBOM)](https://www.cisa.gov/resources-tools/resources/types-software-bill-materials-sbom) (Public Domain)
- (CPANSec 2024) CPAN Security Group improvements and commentary, marked with ✍️ (CC-BY-SA-4.0)
- (SCVS 2020) OWASP [Software Component Verification Standard 1.0 Glossary](https://scvs.owasp.org/scvs/appendix-a-glossary/) Appendix A ([CC-BY-SA-4.0](https://github.com/OWASP/Software-Component-Verification-Standard/blob/master/LICENSE.txt))
- (SLSA 2023) OpenSSF [Supply-chain Levels for Software Artifacts 1.0 Terminology](https://slsa.dev/spec/v1.0/terminology)
- (CRA 2024-03) EU [Cyber Resilience Act, Annex II, Chapter I, Article 3 (Definitions)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=136), pages 136-146, published 2024-03-12.
- (CPAN 2015) [CPAN Glossary](http://neilb.org/2015/09/05/cpan-glossary.html) by Neil Bowers, published 2015-09-05.
- (SBOMit 2024) [SBOM on in-toto Terminology](https://github.com/SBOMit/specification/blob/main/specification.md#15-terminology)
- (NTIA 2021) [NTIA The Minimum Elements for an SBOM, Glossary](https://www.ntia.doc.gov/files/ntia/publications/sbom_minimum_elements_report.pdf#page=25), pages 25-27, published 2021-07-12.
- (CISA 2024) [CISA SBOM Sharing Roles and Considerations](https://www.cisa.gov/resources-tools/resources/sbom-sharing-roles-and-considerations), Appendix, published 2024-03-28.


## About this document

Version: 0.5.0
License: [CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/deed)
Copyright: © Salve J. Nilsen <sjn@oslo.pm>, Some rights reserved.

You may use, modify and share this file under the terms of the [CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/deed) license.


### Acknowledgements

Several people have been involved in the development of this document

* Salve J. Nilsen (main author)
* Josh Bressers
