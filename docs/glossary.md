---
layout: page
title: Glossary of Terms
description: List of terms used throughout CPANSec projects
toc: true
---

> [!CAUTION]
> ## Document status: :warning: DRAFT
> What you see here is a DRAFT of the Glossary used by the CPAN Security Group (CPANSec).
> As long as this document is in DRAFT, all of the points and ideas below are _suggestions_, and open to revision, deletion or amending – by you!
>
> - Contribute on Github: https://github.com/CPAN-Security/security.metacpan.org/tree/sbom-draft/sbom
> - Discuss on IRC: [ircs://ssl.irc.perl.org:7062/#cpan-security](ircs://ssl.irc.perl.org:7062/#cpan-security)

## Glossary

### Artifact

> An immutable blob of data; primarily refers to software, but SLSA can be used for any artifact.
> E.g. a file, a git commit, a directory of files (serialized in some way), a container image, a firmware image.
>
> ([Ref](#references-and-terms): SLSA 2023)

### Attestation

> An authenticated statement (metadata) about a software artifact or collection of software artifacts.
> E.g. a signed SLSA Provenance file.
>
> ([Ref](#references-and-terms): SLSA 2023)

### Build

> Process that transforms a set of input artifacts into a set of output artifacts.
> The inputs may be sources, dependencies, or ephemeral build outputs.
> E.g. .travis.yml (process) run by Travis CI (platform).
>
> ([Ref](#references-and-terms): SLSA 2023)

### CE Marking :warning:

> A marking by which a manufacturer indicates that a product with digital elements and the processes put in place by the manufacturer are in conformity with the essential requirements set out in [EU Cyber Resilience Act, Annex I](#references-and-terms) and other applicable European Union harmonisation legislation providing for its affixing.
>
> ([Ref](#references-and-terms): CRA 2024 I, CRA 2024 II (21))

### Chain of custody

> Auditable documentation of point of origin as well as the method of transfer from point of origin to point of destination and the identity of the transfer agent.
>
> ([Ref](#references-and-terms): SCVS 2020)

### Component function

> The purpose for which a software component exists.
> Examples of component functions include parsers, database persistence, and authentication providers.
>
> ([Ref](#references-and-terms): SCVS 2020)

### Component type

> The general classification of a software components architecture.
> Examples of component types include libraries, frameworks, applications, containers, and operating systems.
>
> ([Ref](#references-and-terms): SCVS 2020)

### CycloneDX :writing_hand:

> An OWASP managed software bill of materials specification designed to be lightweight and security-focused.
>
> ([Ref](#references-and-terms): SCVS 2020, CPANSec 2024)

### Dependency :writing_hand: :warning:

> [Artifact](#artifact) that is an input to a build process but that is not a source.
> In the SLSA model, it is always a package.
> E.g. an Alpine package ([package](#package)) distributed on Alpine Linux ([platform](#platform)).
>
> ([Ref](#references-and-terms): SLSA 2023)

### Direct dependency :writing_hand:

> A software component that is referenced by a program itself.
> For indirect dependencies, see [Transitive dependency](#transitive-dependency).
>
> ([Ref](#references-and-terms): SCVS 2020, CPANSec 2024)


### Distributor (EU) :warning:

> [!WARNING]
> The Cyber Resilience Act defines a distributor as someone who **does not** change a package/component. This means if a distributor applies a patch, they should be treated as a [manufacturer](#manufacturer) or [Open-Source software steward](#open-source-software-steward), including the consequences this entails.
>
> TODO: Check with lawyer after final version of CRA is adopted.

> Any natural or legal person in the supply chain, other than the manufacturer or the importer, that makes a product with digital elements available on the European Union market without affecting its properties.
>
> ([Ref](#references-and-terms): CRA 2024 II (21))


### Open-source software steward :warning:

> [!NOTE]
> TODO: This is an addition that was added 2023-12-20, which may mean this defenition may change in the final version of the CRA.

> Any legal person, other than a [manufacturer](#manufacturer), which has the purpose or objective to systematically provide support on a sustained basis for the development of specific products with digital elements qualifying as free and open-source software that are intended for commercial activities, and ensures the viability of those products.
>
> ([Ref](#references-and-terms): CRA 2024 II (18a))


### Manufacturer

> Any natural or legal person who develops or manufactures products with digital elements or has products with digital elements designed, developed or manufactured, and markets them under his or her name or trademark, whether for payment, monetisation or free of charge.
>
> ([Ref](#references-and-terms): CRA 2024 II (18))


### Package :writing_hand: :warning:

> Artifact that is ~~“published”~~ for use by others.
> In the model, it is always the output of a build process, though that build process can be a no-op.
> E.g. a Docker image (package) distributed on DockerHub (platform).
> E:g. a ZIP file containing source code is a package, not a source, because it is built from some other source, such as a git commit.
>
> ([Ref](#references-and-terms): SLSA 2023, CPANSec 2024)

### Package manager :writing_hand:

> A distribution mechanism that makes software artifacts discoverable by ~~requesters~~ users of a specific package ecosystem.
>
> ([Ref](#references-and-terms): SCVS 2020, CPANSec 2024)

### Package URL (PURL)

> An ecosystem-agnostic specification which standardizes the syntax and location information of software components.
>
> ([Ref](#references-and-terms): SCVS 2020)

### Pedigree

> Data which describes the lineage and/or process for which software has been created or altered.
>
> ([Ref](#references-and-terms): SCVS 2020)

### Point of origin :writing_hand:

> The supplier and associated metadata from which a software component has been procured, transmitted, or received.
> ~~Package repositories, release distribution platforms, and version control history are examples of various points of origin.~~
>
> ([Ref](#references-and-terms): SCVS 2020, CPANSec 2024)

### Procurement :writing_hand:

> The process of agreeing to terms and acquiring software or services for later use.
> This includes agreeing to Open Source licenses.
>
> ([Ref](#references-and-terms): SCVS 2020, CPANSec 2024)

### Provenance

> The chain of custody and origin of a software component.
> Provenance incorporates the point of origin through distribution as well as derivatives in the case of software that has been modified.
>
> ([Ref](#references-and-terms): SCVS 2020)

### SBOM Types

[Software Bill of Materials](#software-bill-of-materials--sbom-) types, produced under certain circumstances.

#### Design SBOM (Type)

> SBOM of intended, planned software project or product with included components (some of which may not yet exist) for a new software artifact.
>
> ([Ref](#references-and-terms): CISA 2023)

#### Source SBOM (Type)

> SBOM created directly from the development environment, source files, and included dependencies used to build an product artifact.
>
> ([Ref](#references-and-terms): CISA 2023)

#### Build SBOM (Type)

> SBOM generated as part of the process of building the software to create a releasable artifact (e.g., executable or package) from data such as source files, dependencies, built components, build process ephemeral data, and other SBOMs.
>
> ([Ref](#references-and-terms): CISA 2023)

#### Analyzed SBOM (Type)

> SBOM generated through analysis of artifacts (e.g., executables, packages, containers, and virtual machine images) after its build.
> Such analysis generally requires a variety of heuristics.
> In some contexts, this may also be referred to as a “3rd party” SBOM.
>
> ([Ref](#references-and-terms): CISA 2023)

#### Deployed SBOM (Type)

> SBOM provides an inventory of software that is present on a system.
> This may be an assembly of other SBOMs that combines analysis of configuration options, and examination of execution behavior in a (potentially simulated) deployment environment.
>
> ([Ref](#references-and-terms): CISA 2023)

#### Runtime SBOM (Type)

> SBOM generated through instrumenting the system running the software, to capture only components present in the system, as well as external call-outs or dynamically loaded components.
> In some contexts, this may also be referred to as an “Instrumented” or “Dynamic” SBOM.
>
> ([Ref](#references-and-terms): CISA 2023)

### Software bill of materials (SBOM)

> A complete, formally structured, and machine-readable inventory of all software components and associated metadata, used by or delivered with a given piece of software.
>
> ([Ref](#references-and-terms): SCVS 2020)

### Software Identification (SWID)

> An ISO standard that formalizes how software is tagged.
>
> ([Ref](#references-and-terms): SCVS 2020)

### Software Package Data Exchange (SPDX)

> A Linux Foundation project which produces a software bill of materials specification and a standardized list of open source licenses.
>
> ([Ref](#references-and-terms): SCVS 2020)

### Source :writing_hand: :warning:

> Artifact that was directly authored or reviewed by persons, without modification.
> It is the beginning of the supply chain; we do not trace the provenance back any further.
> E.g. a git commit (source) hosted on GitHub ([platform](#platform)).
>
> ([Ref](#references-and-terms): SLSA 2023, CPANSec 2024)

### Third-party component :writing_hand:

> ~~Any software component not directly created including open source, "source available", and commercial or proprietary software.~~

> Any software component not directly created, including "source available", commercial or proprietary software.
> Open Source software is closer to a "second-party component" as the developer in fact has a legal relationship with the FOSS component project by accepting the project license.
>
> ([Ref](#references-and-terms): SCVS 2020, CPANSec 2024)

### Transitive dependency :writing_hand:

> A software component that is indirectly used by a program by means of being a dependency of a dependency.
> Dependencies of transitive dependencies are also transitive dependencies (it's dependencies all the way down!).
> See also [Direct dependency](#direct-dependency).
>
> ([Ref](#references-and-terms): SCVS 2020, CPANSec 2024)

## References and terms

This glossary is partly based on

- (CISA 2023) CISA [Types of Software Bill of Materials (SBOM)](https://www.cisa.gov/resources-tools/resources/types-software-bill-materials-sbom) (Public Domain)
- (CPANSec 2024) CPAN Security Group improvements marked with :writing_hand: (CC-BY-SA-4.0)
- (SCVS 2020) OWASP [Software Component Verification Standard 1.0 Glossary](https://scvs.owasp.org/scvs/appendix-a-glossary/) Appendix A ([CC-BY-SA-4.0](https://github.com/OWASP/Software-Component-Verification-Standard/blob/master/LICENSE.txt))
- (SLSA 2023) OpenSSF [Supply-chain Levels for Software Artifacts 1.0 Terminology](https://slsa.dev/spec/v1.0/terminology)
- (CRA 2024 I 2023-09-15) EU [Cyber Resilience Act, Annex I](https://eur-lex.europa.eu/resource.html?uri=cellar:864f472b-34e9-11ed-9c68-01aa75ed71a1.0001.02/DOC_2&format=PDF)
- (CRA 2024 II 2023-12-20 update) EU [Cyber Resilience Act, Annex II, Chapter I, Article 3 (Definitions)](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CONSIL:ST_17000_2023_INIT)
