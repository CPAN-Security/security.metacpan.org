---
layout: page
title: Glossary of Terms
description: List of terms used throughout CPANSec projects
toc: true
---

> [!CAUTION]
> ## Document status: ⚠️  DRAFT
> What you see here is a DRAFT of the Glossary used by the CPAN Security Group (CPANSec).
> As long as this document is in DRAFT, all of the points and ideas below are _suggestions_, and open to revision, deletion or amending – by you!
>
> - Contribute on Github: [https://github.com/CPAN-Security/security.metacpan.org/blob/main/docs/glossary.md](https://github.com/CPAN-Security/security.metacpan.org/blob/main/docs/glossary.md)
> - Discuss on IRC: [ircs://ssl.irc.perl.org:7062/#cpan-security](ircs://ssl.irc.perl.org:7062/#cpan-security)

> [!NOTE]
> ### Legend
> * ✍️  — Changes have been made to the original definition, mostly for clarity or consistency.
> * ⚠️  — Definition has problems or errors or may be confusing, and therefore requires correction or additional explanation.


## Glossary

### Artifact ✍️

> 1. An immutable blob of data; primarily refers to [software](#software), but SLSA can be used for any artifact.
> E.g. a file, a git commit, a directory of files (serialized in some way), a container image, a firmware image.
> 2. See also [Component](#component).
>
> (Ref: [SLSA 2023](#references-and-terms))

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

> 1. A marking by which a manufacturer indicates that a product with digital elements and the processes put in place by the manufacturer are in conformity with the essential requirements set out in [EU Cyber Resilience Act, Annex I](#other-supporting-matter) and other applicable European Union harmonisation legislation providing for its affixing.
>
> (Ref: [CRA 2024](#references-and-terms))

### Chain of custody

> 1. Auditable documentation of point of origin as well as the method of transfer from point of origin to point of destination and the identity of the transfer agent.
>
> (Ref: [SCVS 2020](#references-and-terms))

### Component ✍️

> [!NOTE]
> 1. Software or hardware intended for integration into an [electronic information system](#electronic-information-system).
> 2. See also [Artifact](#artifact).
>
> (Ref: [CRA 2024](#references-and-terms), CPANSec 2024)

#### Component function

> 1. The purpose for which a software component exists.
>     * Examples of component functions include parsers, database persistence, and authentication providers.
>
> (Ref: [SCVS 2020](#references-and-terms))

#### Component, third-party ✍️

> 1. ~~Any software component not directly created including open source, "source available", and commercial or proprietary software.~~ (SCVS)
> 2. Any software component not directly created, including "source available", commercial or proprietary software. (CPANSec)
>     * Open Source software is closer to a "second-party component" as the developer in fact has a legal relationship with the FOSS component project by accepting the project license.
>
> (Ref: [SCVS 2020](#references-and-terms), CPANSec 2024)

#### Component type

> 1. The general classification of a software components architecture.
>     * Examples of component types include libraries, frameworks, applications, containers, and operating systems.
>
> (Ref: [SCVS 2020](#references-and-terms))

### CycloneDX ✍️

> 1. An OWASP managed software bill of materials specification designed to be lightweight and security-focused.
>
> (Ref: [SCVS 2020](#references-and-terms), CPANSec 2024)

### Dependency ✍️  ⚠️

> 1. [Artifact](#artifact) that is an input to a build process but that is not a source.
>     * In the SLSA model, it is always a package.
>     * E.g. an Alpine package ([package](#package)) distributed on Alpine Linux ([platform](#platform)).
>
> (Ref: [SLSA 2023](#references-and-terms))

#### Dependency (Direct) ✍️

> 1. A software component that is referenced by a ~~program~~ [software](#software) itself.
>
> For indirect dependencies, see [Dependency (Transitive)](#dependency-transitive).
>
> (Ref: [SCVS 2020](#references-and-terms), CPANSec 2024)

#### Dependency (Transitive) ✍️

> 1. A software component that is indirectly used by a program by means of being a dependency of a dependency.
>     * Dependencies of transitive dependencies are also transitive dependencies (it's dependencies all the way down!).
> 2. See also [Dependency (Direct)](#dependency-direct).
>
> (Ref: [SCVS 2020](#references-and-terms), CPANSec 2024)

### Distributor ⚠️

> [!WARNING]
> The Cyber Resilience Act defines a distributor as someone who **does not** change a package/component. This means if a distributor applies a patch, they should be treated as a [manufacturer](#manufacturer) or [Open-Source software steward](#open-source-software-steward), including any consequences this may entail.
>
> TODO: Check with lawyer after final version of CRA is adopted.

> 1. Any natural or legal person in the supply chain, other than the manufacturer or the importer, that makes a product with digital elements available on the European Union market without affecting its properties.
>
> (Ref: [CRA 2024](#references-and-terms))

### Electronic information system

> 1. Any system, including electrical or electronic equipment, capable of processing, storing or transmitting digital data.
>
> (Ref: [CRA 2024](#references-and-terms))

### Hardware

> 1. A physical electronic information system, or parts thereof capable of processing, storing or transmitting of digital data.
>
> (Ref: [CRA 2024](#references-and-terms))

### Manufacturer

> 1. Any natural or legal person who develops or manufactures products with digital elements or has products with digital elements designed, developed or manufactured, and markets them under his or her name or trademark, whether for payment, monetisation or free of charge.
>
> (Ref: [CRA 2024](#references-and-terms))

### Open-source software steward ⚠️

> [!NOTE]
> TODO: This is a definition that was added to the CRA on 2023-12-20, meaning it may change in the final version of the regulation.

> 1. Any legal person, other than a [manufacturer](#manufacturer), which has the purpose or objective to systematically provide support on a sustained basis for the development of specific products with digital elements qualifying as free and open-source software that are intended for commercial activities, and ensures the viability of those products.
>
> (Ref: [CRA 2024](#references-and-terms))

### Package ✍️  ⚠️

> 1. [Artifact](#artifact) that is ~~“published”~~ for use by others.
>     * In the model, it is always the output of a build process, though that build process can be a no-op.
>     * E.g. a Docker image (package) distributed on DockerHub (platform).
>     * E:g. a ZIP file containing source code is a package, not a source, because it is built from some other source, such as a git commit.
>
> (Ref: [SLSA 2023](#references-and-terms), CPANSec 2024)

### Package manager ✍️

> 1. A distribution mechanism that makes software artifacts discoverable by ~~requesters~~ users of a specific package ecosystem.
>
> (Ref: [SCVS 2020](#references-and-terms), CPANSec 2024)

### Package URL (PURL)

> 1. An ecosystem-agnostic specification which standardizes the syntax and location information of software components.
>
> (Ref: [SCVS 2020](#references-and-terms))

### Pedigree

> 1. Data which describes the lineage and/or process for which software has been created or altered.
>
> (Ref: [SCVS 2020](#references-and-terms))

### Point of origin ✍️

> [!WARNING]
> Discouraged term. Confusing definiton, having common meaning with [Source](#source). (CPANSec)

> 1. The supplier and associated metadata from which a software component has been procured, transmitted, or received. (SCVS)
>     * ~~Package repositories, release distribution platforms, and version control history are examples of various points of origin.~~
>
> (Ref: [SCVS 2020](#references-and-terms), CPANSec 2024)

### Procurement ✍️

> 1. The process of agreeing to terms and acquiring software or services for later use. (SCVS)
>
> This includes agreeing to Open Source licenses. (CPANSec)
>
> (Ref: [SCVS 2020](#references-and-terms), CPANSec 2024)

### Product with digital elements

> 1. Any software or hardware product and its remote data processing solutions, including software or hardware components to be placed on the market separately.
>
> (Ref: [CRA 2024](#references-and-terms))

### Provenance ✍️

> 1. The [chain of custody](#chain-of-custody) and origin of a software component.
>     * Provenance incorporates the [point of origin](#point-of-origin) through ~~distribution~~  [distributor](#distributor) as well as derivatives in the case of software that has been modified.
>
> (Ref: [SCVS 2020](#references-and-terms))

### SBOM (Software Bill of Materials)

> 1. A formal record containing details and supply chain relationships of components included in the software elements of a product with digital elements. (CRA 2024)
> 2. A complete, formally structured, and machine-readable inventory of all software components and associated metadata, used by or delivered with a given piece of software. (SCVS 2020)
>
> (Ref: [CRA 2024](#references-and-terms), SCVS 2020)

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

> 1. The part of an electronic information system which consists of computer code.
>
> (Ref: [CRA 2024](#references-and-terms))

### Software Bill of Materials (SBOM)

> 1. See [SBOM (Software Bill of Materials](#sbom-software-bill-of-materials).

### Software Identification (SWID)

> 1. An ISO standard that formalizes how software is tagged.
>
> (Ref: [SCVS 2020](#references-and-terms))

### Software Package Data Exchange (SPDX)

> 1. A Linux Foundation project which produces a [software bill of materials](#sbom-software-bill-of-materials) specification and a standardized list of open source licenses.
>
> (Ref: [SCVS 2020](#references-and-terms))

### Source ✍️  ⚠️

> 1. An [artifact](#artifact) that was directly authored ~~or reviewed~~ by persons, without modification.
>     * It is the beginning of the supply chain; we do not trace the provenance back any further.
>     * E.g. a git commit (source) hosted on GitHub ([platform](#platform)).
>
> (Ref: [SLSA 2023](#references-and-terms), CPANSec 2024)

### SPDX (Software Package Data Exchange)

> See [Software Package Data Exchange (SPDX)](#software-package-data-exchange-spdx).

### SWID (Software Identification)

> See [Software Identification (SWID)](#software-identification-swid).

### Component, third-party ✍️

> See [Component, third-party](#component-third-party).


## References and terms

This glossary is partly based on

- (CISA 2023) CISA [Types of Software Bill of Materials (SBOM)](https://www.cisa.gov/resources-tools/resources/types-software-bill-materials-sbom) (Public Domain)
- (CPANSec 2024) CPAN Security Group improvements marked with ✍️  (CC-BY-SA-4.0)
- (SCVS 2020) OWASP [Software Component Verification Standard 1.0 Glossary](https://scvs.owasp.org/scvs/appendix-a-glossary/) Appendix A ([CC-BY-SA-4.0](https://github.com/OWASP/Software-Component-Verification-Standard/blob/master/LICENSE.txt))
- (SLSA 2023) OpenSSF [Supply-chain Levels for Software Artifacts 1.0 Terminology](https://slsa.dev/spec/v1.0/terminology)
- (CRA 2024) EU [Cyber Resilience Act, Annex II, Chapter I, Article 3 (Definitions)](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CONSIL:ST_17000_2023_INIT), page 75, published 2023-12-20.


## Other supporting matter

- (CRA 2023) EU [Cyber Resilience Act, Annex I](https://eur-lex.europa.eu/resource.html?uri=cellar:864f472b-34e9-11ed-9c68-01aa75ed71a1.0001.02/DOC_2&format=PDF), published 2023-09-15.
