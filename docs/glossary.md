---
layout: page
title: Glossary of Terms
description: List of terms used throughout CPANSec projects
draft: true
draft_text: What you see here is a DRAFT of the Glossary used by the CPAN Security Group (CPANSec).
contribution_url: https://github.com/CPAN-Security/security.metacpan.org/blob/main/docs/glossary.md
toc: true
---

## Document status: ⚠️  DRAFT {#document-status}

> [!CAUTION]
> What you see here is a DRAFT of the Glossary used by the CPAN Security Group (CPANSec).
> As long as this document is in DRAFT, all of the points and ideas below are _suggestions_, and open to revision, deletion or amending – by you!
>
> - Contribute on Github: [https://github.com/CPAN-Security/security.metacpan.org/blob/main/docs/glossary.md](https://github.com/CPAN-Security/security.metacpan.org/blob/supplychain-sbom/docs/glossary.md)
> - Discuss on IRC: [ircs://ssl.irc.perl.org:7062/#cpan-security](ircs://ssl.irc.perl.org:7062/#cpan-security)
> - Discuss on Matrix: [https://matrix.to/#/#cpansec:matrix.org](https://matrix.to/#/#cpansec:matrix.org)

### This document is **opinionated**

This glossary is not an authoritative source of terms, but rather intended as a guide for reducing ambiguity and confusion in a technical field where many institutions are making up their own definitions as they go.

Please take this into account when commenting this document.

#### **Descriptive** and **prescriptive**

While some aspects of this document are descriptive – meaning it refers to other definitions and terms – we don't shy away from recommending or discouraging some of them.

Please take this into account when commenting this document.

#### **Visionary** and a **proposal**

Some aspects of this document – including those related to the role of Open Source Stewards, the Cyber Resilience Act and CE Marking – are presented as **suggestions, proposals or visions of a possible future**.

Please take this into account when commenting this document.


### Legend

> [!NOTE]
> * ⚠️  — The definition has problems or errors or may be confusing, and therefore requires correction or additional explanation.
> * ✍️  — Changes have been made to the original definition, mostly for clarity or consistency.


## Glossary

### Artifact ✍️ {#artifact}

> [!NOTE]
> Component and Artifact seem to have overlapping definitions.
> We recommend using the term Artifact specifically when referring to files (as defined), and Component in other situations. (CPANSec-2024)

> 1. (SLSA-2023) An immutable blob of data; primarily refers to [software](#software), but SLSA can be used for any artifact.
>     * E.g. a file, a git commit, a directory of files (serialized in some way), a container image, a firmware image.
>
> * See also:
>     * [Component](#component)
>
> (Ref: [SLSA-2023](#references-and-terms), CPANSec-2024)


### Author (SBOM Role)

> 1. (NTIA-2021) An entity that creates an SBOM.
>     * [author](#author) and [supplier](#supplier) will often be different. In the case of SBOMs, the author creates the SBOM. The supplier is the provider of the software included in the SBOM.
>
> * See also:
>     * [Author](supplychain-sbom#author) in the Supply-chain SBOM Roles document.


### Author (Project Role)

> 1. (CPANSec-2024) A developer that publishes something as Open Source software.
>
> (Ref: [CPANSec-2024](#references-and-terms))


### Attestation

> 1. An authenticated statement (metadata) about a software artifact or collection of software artifacts.
>     * E.g. a signed SLSA Provenance file.
>
> (Ref: [SLSA-2023](#references-and-terms))


### Build

> 1. (SLSA-2023) Process that transforms a set of input artifacts into a set of output artifacts.
>     * The inputs may be sources, dependencies, or ephemeral build outputs.
>     * E.g. .travis.yml (process) run by Travis CI (platform).
>
> (Ref: [SLSA-2023](#references-and-terms))


### CE Marking ⚠️  {#ce-marking}

> 1. (CRA-2024-03) A marking by which a manufacturer indicates that a product with digital elements and the processes put in place by the manufacturer are in conformity with the essential requirements set out in [EU Cyber Resilience Act, Annex I](#other-supporting-matter) and other applicable European Union harmonization legislation providing for its affixing.
>
> (Ref: [CRA-2024-03](#references-and-terms))


### Chain of custody

> 1. (SCVS-2020, CDXAG-2024) Auditable documentation of point of origin as well as the method of transfer from point of origin to point of destination and the identity of the transfer agent.
>
> (Ref: [SCVS-2020](#references-and-terms), CDXAG-2024)


### Component ✍️ {#component}

> [!NOTE]
> 1. (CPANSec) Component and Artifact seem to have overlapping definitions.
>     * Recommendation: use the term Artifact specifically when referring to files (as defined), and Component in other situations.

> 1. (CRA-2024-03) Software or hardware intended for integration into an [electronic information system](#electronic-information-system).
> 1. (NTIA-2021) A unit of software defined by a supplier at the time the component is built, packaged, or delivered. Many components contain sub-components. Examples of components include a software product, a device, a library, or a single file.
>
> See also: [Artifact](#artifact).
>
> (Ref: [CRA-2024-03](#references-and-terms), NTIA-2021, CPANSec-2024)

#### Component function

> 1. (SCVS-2020, CDXAG-2024) The purpose for which a software component exists.
>     * Examples of component functions include parsers, database persistence, and authentication providers.
>
> (Ref: [SCVS-2020](#references-and-terms), CDXAG-2024)

#### Component, second-party ✍️ {#second-party}

> 1. (CPANSec-2024) Any software component created through the interaction with a second party, including open source, "source available", and proprietary software where the source is made available for either inspection, use, modification, building or sharing.
>     * Open Source software components that an application has as dependencies should be considered as "second-party" components or dependencies, since the application owner has an ongoing relationship with the FOSS component project, by the fact that the owner has accepted the open source project's license.
>
> (Ref: [CPANSec-2024](#references-and-terms))

#### Component, third-party ✍️ {#third-party}

> 1. (SCVS-2020, CDXAG-2024) Any software component not directly created including open source, "source available", and commercial or proprietary software.
> 1. (CPANSec-2024) Any software component not directly created including "source available", commercial or proprietary software.
>     * See [Component, second-party](#second-party).
>
> (Ref: [SCVS-2020](#references-and-terms), CDXAG-2024, CPANSec-2024)

#### Component type

> 1. (SCVS-2020, CDXAG-2024) The general classification of a software components architecture.
>     * Examples of component types include libraries, frameworks, applications, containers, and operating systems.
>
> (Ref: [SCVS-2020](#references-and-terms), CDXAG-2024)


### Consumer

> * See also
>     * [End-user](#end-user)


### CycloneDX ✍️ {#cyclonedx}

> 1. (SCVS-2020) An OWASP managed software bill of materials specification designed to be lightweight and security-focused.
>     * CycloneDX is considered to be one of the three [SBOM](#sbom) formats, together with [SWID](#swid) and [SPDX](#spdx).
>
> (Ref: [SCVS-2020](#references-and-terms))


### Dependency ⚠️  ✍️ {#dependency}

> [!CAUTION]
> * (CPANSec-2024) Dependencies may be declared/stated/referenced or included/embedded or assumed/implied/detected, development phase-specific (e.g. developer, config, build, test, deploy, or runtime-specific), dynamic or static, unresolved or resolved, direct or transitive, or required, recommended or suggested.
>     * The NTIA-2021 definition below is therefore not only **wrong**, but also **entirely insufficient** — is for any practical purpose useless and should not be used.
>     * The SLSA-2023 definition below is preferred, though it doesn't sufficiently distinguish between stated, included and assumed dependencies.
>     * Please consider using the CPANSec-2024 definition

> 1. (CPANSec-2024) A dependency is a software component that is required for another software to work as expected.
>     * This means the component which is depended upon (required) has been made available for use by the depending software so it may function as expected, without modification.
>     * Dependencies exist _after_ they have been made available to the depending software.
>     * If a dependency is unmet (meaning – not made available, deployed, or installed), then it is called a _Requirement_.
>     * A dependency can come in many forms,
>         * Static, Dynamic
>         * Component, Resource or Service
>         * Vendored-in (Bundled, Embedded, Included)
>         * Direct or Transitive
>         * Optional, Virtual, Assumed (Phantom) or Unused (Zombie)
>         * In-ecosystem (Native) or Out-of-ecosystem (Non-native)
>         * Unresolved, or Resolved during Development, Configuration, Build, Test, Deploy or at Runtime
> 1. (SLSA-2023) An [Artifact](#artifact) that is an input to a build process but that is not a source.
>     * In the SLSA model, it is always a package.
>     * E.g. an Alpine package ([package](#package)) distributed on Alpine Linux ([platform](#platform)).
> 1. ⚠️  (NTIA-2021) Characterizing the relationship that an upstream component X is included in software Y.
>
> (Ref: [SLSA-2023](#references-and-terms), [NTIA-2021](#references-and-terms), [CPANSec-2024](#references-and-terms))

#### Dependency, Direct ✍️ {#dependency-direct}

> 1. (SCVS-2020, CDXAG-2024) A software component that is referenced by a program itself.
> 1. (CPANSec-2024) A [software](#software) program, library, plugin, service, resource or component that is required for another software program or component to function as expected.
>
> * See also
>     * [Dependency (Transitive)](#dependency-transitive)
>     * [Dependency (Indirect)](#dependency-indirect)
>
> (Ref: [SCVS-2020](#references-and-terms), CDXAG-2024, CPANSec-2024)

#### Dependency, Dynamic

> [!NOTE]
> * FIXME: Expand on this topic

> * See also
>     * [Dependency (Static)](#dependency-static)

#### Dependency, Indirect {#dependency-indirect}

> 1. (CPANSec-2024) A dependency that is used during the author, build, test or deployment stages of a program, but is is not needed any more during runtime.
>     * Examples: Compilers, test harnesses, build tooling, editors, software packaging tooling, software repositories and publishing platforms.

#### Dependency, Transitive ✍️ {#dependency-transitive}

> 1. (SCVS-2020) A software component that is indirectly used by a program by means of being a dependency of a dependency.
> 1. (NTIA-2021) Characterizing the relationship that if an upstream component X is included in software Y and component Z is included in component X then component Z is included in software Y.
> 1. (CPANSec-2024) Dependencies of transitive dependencies are also transitive dependencies (it's dependencies all the way down!).
>
> * See also
>    * [Dependency (Direct)](#dependency-direct).
>
> (Ref: [SCVS-2020](#references-and-terms), NTIA-2021, CPANSec-2024)

#### Dependency, Vendored-in (Bundled, Contained, Embedded, Included, Pre-resolved) ✍️ {#dependency-vendored}

> 1. (CPANSec-2024) A dependency that is supplied as part of a software package, and therefore already resolved by the Author of the package.
>
> (Ref: [CPANSec-2024](#references-and-terms))

#### Dependency, Pinned at Source ✍️

> * See
>     * [Dependency, Vendored-in)](#dependency-vendored)

#### Dependency, Resolved at Source ✍️

> * See
>     * [Dependency, Vendored-in](#dependency-vendored)

#### Dependency, Phantom (Assumed, Implied, Unknown, Unstated) ✍️ {#dependency-phantom}

> [!NOTE]
> * FIXME: Expand on this topic

> 1. (CPANSec-2024) A dependency that is used but not explicitly stated as required in the component or package metadata.
>     * A phantom dependency is a component that is required to perform an action or functionality, but has not been explicitly stated as required.
>     * An phantom dependency should be considered as a bug in the component metadata, and corrected as soon as possible.
>     * If a dependency has to be assumed or implied due to lacking capabilities in the tooling used to create the component or package, this should be considered as a bug in the tooling.
>
> (Ref: [CPANSec-2024](#references-and-terms))

#### Dependency, Detected during Analysis ✍️

> 1. (CPANSec-2024) A previously unknown dependency that was discovered during software dependency analysis.
>
> * See
>     * [Dependency Phantom (Assumed, Implied, Unknown, Unstated)](#dependency-phantom)
>
> (Ref: [CPANSec-2024](#references-and-terms))

#### Dependency, Optional

> [!NOTE]
> * FIXME: Expand on this topic

> * See also
>     * [Dependency (Static)](#dependency-static)

#### Dependency, Unresolved (Required) {#dependency-unresolved}

> * See
>     * [Requirement](#requirement)

#### Dependency, Resolved during Configuration ✍️ {#dependency-configuration-time}

> [!NOTE]
> * FIXME: Expand on this topic

#### Dependency, Resolved during Build ✍️ {#dependency-build-time}

> [!NOTE]
> * FIXME: Expand on this topic

#### Dependency, Pinned during Build ✍️ {#dependency-build-pinned)

> [!NOTE]
> * FIXME: Expand on this topic

#### Dependency, Resolved during Deploy ✍️ {#dependency-deploy-time}

> [!NOTE]
> * FIXME: Expand on this topic

#### Dependency, Resolved at Runtime ✍️ {#dependency-runtime}

> [!NOTE]
> * FIXME: Expand on this topic

#### Dependency, In-ecosystem (Native) ✍️ {#dependency-in-ecosystem}

> [!NOTE]
> * FIXME: Expand on this topic

> * See
>     * [Dependency (Out-of-ecosystem)](#dependency-out-of-ecosystem)

#### Dependency, Out-of-ecosystem (Non-native) ✍️ {#dependency-out-of-ecosystem}

> [!NOTE]
> * FIXME: Expand on this topic

> * See also
>     * [Dependency (In-ecosystem)](#dependency-in-ecosystem)

#### Dependency, Service ✍️ {#dependency-service}

> [!NOTE]
> * FIXME: Expand on this topic

> 1. (CPANSec-2024) A network service dependency that are required for component to function as expected
> 1. (PCISSF-2023) Required by the PCI Software Security Framework version 1.2.1
>
> (Ref: [CPANSec-2024](#references-and-terms), [PCISSF-2023](#references-and-terms))

#### Dependency, Static

> [!NOTE]
> * FIXME: Expand on this topic

> * See also
>     * [Dependency (Dynamic)](#dependency-dynamic)

#### Dependency, Dynamic

> [!NOTE]
> * FIXME: Expand on this topic

> * See also
>     * [Dependency (Static)](#dependency-static)

#### Dependency, Virtual

> [!NOTE]
> * FIXME: Expand on this topic

> 1. (CPANSec-2024) A dependency that is present, but cannot be represented by an actual software package.
>     * e.g. The OS kernel and base file-system and services that have to be in place before the first regular package may be installed.
>
> (Ref: [CPANSec-2024](#references-and-terms))

#### Dependency, Zombie (Unused) {#dependency-zombie}

> 1. (CPANSec-2024) A dependency that has been resolved and installed, but is not in use anywhere (any more).
>     * May be a build artifact left over after earlier stages in the build process (e.g. development, configure, or testing)
>     * May be misused or exploited for downgrade attacks or expose other vulnerabilities or sensitive data.
>     * Recommended to be removed before deployment or packaging.
>
> (Ref: [CPANSec-2024](#references-and-terms))

### Requirement ✍️ {#requirement}

> 1. (CPANSec-2024) A dependency that that needs to be resolved (be made available) for a software component to function as expected.
>     * Requirements are expected to be resolved by the Builder, Packager or Integrator of the component.
>     * An unresolved dependency has always a version constraint associated with it (implied or explicitly), to be used during dependency resolution.
>     * Also referred to as a "prereq", "dependency".
>
> * See Also
>     * [Dependency](#dependency)
>
> (Ref: [CPANSec-2024](#references-and-terms))

### Pre-Requirement

> * See
>     * [Requirement](#requirement)

### Provider (Ecosystem Role) ✍️ {#provider}

Package _Providers_ are responsible for making packages or containers that Patchers and Packagers produce, and ensure these are made available in a reliable way for downstream users, possibly in accordance with a Curator's requirements.
(e.g. by setting up and managing a Debian APT repository, or a CPAN mirror, or a Docker container registry, or similar).

> 1. (CPANSec-2024) The Role that is tasked with ensuring a component artifact is available for download by anyone downstream
>     * This term is in place of the term [Distributor](#distributor) when referring to Open Source Ecosystem component suppliers.
>     * This is to disambiguate from the term [Distributor](#distributor) in the context of the EU Cyber Resilience Act.
>     * If SBOM metadata is expected to accompany the packages or containers in question, the Provider makes sure this happens.
>
> * See also:
>     * [Provider](supplychain-sbom.md#provider) in the Supply Chain
>     * [Distributor](supplychain-sbom.md#distributor) in the Supply Chain

> (Ref: [CPANSec-2024](#references-and-terms), [Distributor](#distributor))

#### Distributor (CRA) ⚠️  {#distributor}

> [!WARNING]
> 1. (CPANSec-2024) The Cyber Resilience Act defines a distributor as someone who **does not** [Substantially Modify](#substantial-modification) a package/component.
>     * (CRA-2024-03 Article 21, 22) This means if an [Importer](#importer) or Distributor applies a patch with [Substantial Modifications](#substantial-modification), they are to be treated as a [Manufacturer](#manufacturer), including any consequences this may entail.
>     * (CPANSec-2024) To disambiguate, we recommend Open Source Supply-chain Roles like this to be referred to as [Provider](#provider)
> 1. (CRA-2024-03) A natural or legal person in the supply chain, other than the manufacturer or the importer, that makes a product with digital elements available on the Union market without affecting its properties.
> 1. (EUBG-2022-3) The distributor is a natural or a legal person in the supply chain, other than the manufacturer or the importer, who makes a product available on the market.
>     *  Distributors are subject to specific obligations and have a key role to play in the context of market surveillance.
>
> * See also:
>     * [Provider](#provider)
>
> (Ref: [CRA-2024-03](#references-and-terms), [EUBG-2022-3](#references-and-terms), [CPANSec-2024](#references-and-terms))


### Downstream

> 1. (NTIA-2021) Referring to how a component is subsequently used in other pieces of software at a later stage in the supply chain.
>
> (Ref: [NTIA-2021](#references-and-terms))


### Economic operator (CRA)

> 1. (CRA-2024-03) The [Manufacturer](#manufacturer), the authorised representative, the [Importer](#importer), the [Distributor](#distributor), or other natural or legal person who is subject to obligations in relation to the manufacture of products with digital elements or to the making available of products on the market in accordance with [the Cyber Resilience Act].
>
> (Ref: [CRA-2024-03](#references-and-terms))


### Electronic information system (CRA)

> 1. (CRA-2024-03) A system, including electrical or electronic equipment, capable of processing, storing or transmitting digital data.
>
> (Ref: [CRA-2024-03](#references-and-terms))


### End-user

> 1. (NTIA-2021) Entity that obtains SBOMs.
>     * An entity can be both a supplier and consumer, using components with SBOM data in its own software, which is then passed downstream.
>     * An “end-user” consumer (that is not also a supplier) may also be called an operator or a leaf entity.
> 1. (EUBG-2022-3) The end user is any natural or legal person residing or established in the European Union, to whom a product has been made available either as a consumer outside of any trade, business, craft or profession or as a professional end user in the course of its industrial or professional activities.
>     * Many products covered by European Union product harmonisation legislation are used at work and thus also subject to Union safety at work legislation.
>
> (Ref: [NTIA-2021](#references-and-terms), [EUBG-2022-3](#references-and-terms))


### GrayPAN/GreyPAN {#greypan}

> 1. A GrayPAN is a publicly accessible CPAN, but published outside the CPAN infrastructure, resulting in a codebase that is factually public, but functionally non existent from the perspective of CPAN (e.g. own index).
> (Ref [About the various PANs](https://www.olafalders.com/2019/02/19/about-the-various-pans/))

### Hardware

> 1. (CRA-2024-03) A physical electronic information system, or parts thereof capable of processing, storing or transmitting digital data.
>
> (Ref: [CRA-2024-03](#references-and-terms))


### Importer (CRA)

> 1. (CRA-2024-03) A natural or legal person established in the Union who places on the market a product with digital elements that bears the name or trademark of a natural or legal person established outside the European Union.
> 1. (EUBG-2022-3) The importer is a natural or legal person established in the Union who places a product from a third country on the EU market.
>    * [Their] obligations build on the obligations of the manufacturer.
>
> (Ref: [CRA-2024-03](#references-and-terms), [EUBG-2022-3](#references-and-terms))


### Life-cycle Phase

> 1. (NTIA-2021) The stage in the software life-cycle where an SBOM is generated (e.g. from source, at the time of build or packaging, or from a built executable).
>
> (Ref: [NTIA-2021](#references-and-terms))
>
> * See also
>     * [SBOM Types](#sbom-types)


### Making available on the market (CRA)

> [!NOTE]
> * FIXME: Expand on this topic
> * FIXME: Add some clarification regarding Manufacturers, Importers, Distributors and Open Source Stewards.

> 1. (CRA-2024-03) The supply of a product with digital elements for distribution or use on the European Union market in the course of a commercial activity, whether in return for payment or free of charge.
> 1. (EUBG-2022-2, Chapter 2.2) A product is made available on the market when supplied for distribution, consumption or use on the Union market in the course of a commercial activity, whether in return for payment or free of charge.
>     * The concept of making available refers to each individual product.
>     * A product is made available on the market when supplied for distribution, consumption or use on the Union market in the course of a commercial activity, whether in return for payment or free of charge.
>     * Such supply includes any offer for distribution, consumption or use on the Union market which could result in actual supply in relation to products already manufactured (e.g. an invitation to purchase, advertising campaigns).
>
> (Ref: [CRA-2024-03](#references-and-terms), [EUBG-2022-2](#references-and-terms))

### Manufacturer (CRA)

> 1. (CRA-2024-03) Any natural or legal person who develops or manufactures products with digital elements or has products with digital elements designed, developed or manufactured, and markets them under his or her name or trademark, whether for payment, monetisation or free of charge.
> 1. (EUBG-2022-3, Chapter 3.1) The manufacturer is any natural or legal person who manufactures a product or has a product designed or manufactured, and places it on the market under his own name or trademark.
>     * The manufacturer is responsible for the conformity assessment of the product and is subject to a series of obligations including traceability requirements.
>     * When placing a product on the Union market, the responsibilities of a manufacturer are the same whether he is established outside the European Union or in a Member State.
>     * The manufacturer must cooperate with the competent national authorities in charge of market surveillance in case of a product presenting a risk or being non-compliant.
>
> (Ref: [CRA-2024-03](#references-and-terms), [EUBG-2022-3](#references-and-terms))


### Open-source software

> 1. (NTIA-2021) Software that can be accessed, used, modified, and shared by anyone.
>
> (Ref: [NTIA-2021](#references-and-terms))


### Open source software steward (CRA) ⚠️  {#oss-steward}

> [!NOTE]
> * FIXME: Expand on this topic
> * FIXME: This is a definition that was added to the CRA on 2023-12-20, meaning it may change in the final version of the regulation.

> 1. (CRA-2024-03) Any legal person, other than a [manufacturer](#manufacturer), which has the purpose or objective to systematically provide support on a sustained basis for the development of specific products with digital elements qualifying as free and open source software that are intended for commercial activities, and ensures the viability of those products.
>
> (Ref: [CRA-2024-03](#references-and-terms))


### Package ⚠️  ✍️ {#package}

> 1. (SLSA-2023) [An] [Artifact](#artifact) that is “published” for use by others.
>     * In the model, it is always the output of a build process, though that build process can be a no-op.
>     * E.g. a Docker image (package) distributed on DockerHub (platform).
>     * E:g. a ZIP file containing source code is a package, not a source, because it is built from some other source, such as a git commit.
> 1. (CPANSec-2024) An identifiable unit of software intended for distribution, ambiguously meaning either an “artifact” or a “package name”.
>     * Only use this term when the ambiguity is acceptable or desirable.
>
> (Ref: [SLSA-2023](#references-and-terms), CPANSec-2024)


### Package manager ✍️ {#package-manager}

> 1. (SCVS-2020, CDXAG-2024) A distribution mechanism that makes software artifacts discoverable by requesters of a specific package ecosystem.
> 1. (CPANSec-2024) A distribution mechanism that makes software artifacts discoverable and installable by users of a specific package ecosystem.
>
> (Ref: [SCVS-2020](#references-and-terms), CDXAG-2024, CPANSec-2024)


### Package URL (PURL) {#purl}

> 1. (SCVS-2020, CDXAG-2024) An ecosystem-agnostic specification which standardizes the syntax and location information of software components.
>    * (CPANSec-2024) The PURL spec can be found in [GitHub](https://github.com/package-url/purl-spec). As it is an open source project it is constantly evolving.
>
> (Ref: [SCVS-2020](#references-and-terms), CDXAG-2024, CPANSec-2024)


### Pedigree

> 1. (SCVS-2020, CDXAG-2024) Data which describes the lineage and/or process for which software has been created or altered.
> 1. (NTIA-2021) Data on the origins of components that have come together to make a piece of software and the process under which they came together. This could include data beyond the minimum elements, such as compiler details and settings.
>
> (Ref: [SCVS-2020](#references-and-terms), CDXAG-2024, NTIA-2021)


### Placing on the market (CRA)

> 1. (CRA-2024-03) The first making available of a product with digital elements on the Union market.
> 1. (EUBG-2022-2, Chapter 2.3) A product is placed on the market when it is made available for the first time on the Union market.
>     * According to Union harmonisation legislation, each individual product can only be placed once on the Union market.
>     * Products made available on the market must comply with the applicable Union harmonisation legislation at the moment of placing on the market.
>
> (Ref: [CRA-2024-03](#references-and-terms), [EUBG-2022-2](#references-and-terms))


### Point of origin ⚠️  ✍️ {#point-of-origin}

> 1. (SCVS-2020, CDXAG-2024) The supplier and associated metadata from which a software component has been procured, transmitted, or received.
>     * Package repositories, release distribution platforms, and version control history are examples of various points of origin.
> 1. (CPANSec-2024) Discouraged term – Confusing definition, having common meaning with both [Source](#source), [Manufacturer](#manufacturer) and [Distributor](#distrubutor). 
>
> (Ref: [SCVS-2020](#references-and-terms), CDXAG-2024, CPANSec-2024)


### Presumption of Conformity (CRA)

> [!CAUTION]
> * FIXME: Find a better definition! The one in the Blue Guide is more of an explanation with context. In the meantime, please read the Blue Guide text.

> 1. (EUBG-2022-4, Chapters 4.1.2.2, 4.1.2.3)
>     * The terms ‘standard’, ‘national standard’, ‘European standard’, ‘harmonised standard’ and ‘international standard’ are subject to concrete definitions in Article 2 of Regulation (EU) No 1025/2012.
>     * Standards are technical specifications and are therefore useful and effective in promoting and disseminating good technical practises and technical solutions.
>     * Standards are in themselves of voluntary application.
>     * Harmonised standards are European standards adopted on the basis of a request made by the Commission for the application of Union harmonisation legislation.
>     * If references of harmonised standards have been published in the Official Journal of the European Union (OJEU), they provide a presumption of conformity with the essential or other legislative requirements they aim to cover.
>
>
> (Ref: [CRA-2024-03](#references-and-terms), [EUBG-2022-4](#references-and-terms))


### Procurement ✍️ {#procurement}

> 1. (SCVS-2020, CDXAG-2024) The process of agreeing to terms and acquiring software or services for later use.
>     * (CPANSec-2024) This includes agreeing to Open Source licenses.
>
> (Ref: [SCVS-2020](#references-and-terms), CDXAG-2024, CPANSec-2024)


### Product

> 1. (CPANSec-2024) A release of a project codebase that has been made ready for easy deployment and use, and that is made available, marketed or sold with a recognizable name or trademark.
>     * Please note that a _Product_ is distinct from a _Project_, in that a Product's technology, creation, maintenance, sustainability or governance is not central factors during procurement.
>     * If a Product's technology, creation, maintenance, sustainability or governance is in-scope during procurement, then one should instead consider the underlying [Project](#project) for these selection criteria.
>
> * See also:
>     * [Project](#project)
>
> (Ref: [CPANSec-2024](#references-and-terms))


### Product with digital elements (CRA) {#pde}

> 1. (CRA-2024-03) A software or hardware product and its [Remote Data Processing](#remote-data-processing) solutions, including software or hardware components being placed on the market separately.
>
> (Ref: [CRA-2024-03](#references-and-terms))


### Project

> 1. (CPANSec-2024) the social and technical organization around a codebase which works on and decides how it is developed over time.
>     * A project has a name, a maintainer and a repository for collaboration, and may have one or more co-maintainers (possibly constituting a "core" of the Project) that help take care of the codebase.
>     * Other important features include the Project's license, governance structures, culture and community.
>     * If the Project's license is recognized by the Open Source Initiative as an Open Source license, then the project is an Open Source Project.
>
> (Ref: [CPANSec-2024](#references-and-terms))


### Project Roles

These are roles that may be found in Open Source projects.

#### Project Lead (Project Role) ⚠️  {#project-lead}

> 1. A person who is in charge of a project.
> 1. (CPANSec-2024) Discouraged, due to lack of precision and confusion with common usage i commercial settings.
>    * Instead, use terms like [Author](#author), [Maintainer](#maintainer) or [Owner](#owner).
>
> (Ref: [CPANSec-2024](#references-and-terms))

#### Release Manager (Project Role)

> [!NOTE]
> * FIXME: Expand on this topic

#### Contributor (Project Role) {#packager}

> [!NOTE]
> * FIXME: Expand on this topic

#### Packager (Project Role) {#packager}

> [!NOTE]
> * FIXME: Expand on this topic

#### Custodian (Project Role) ✍️ {#custodian}

> 1. (CPANSec-2024) A role that operates as a temporary replacement of a [Maintainer](#maintainer), or [Owner](#owner), or works on their behalf in the case they are not available, or the project does not have any.
>     * Operates on behalf of a [Maintainer](#maintainer) in a [Language Ecosystem](#language-ecosystem) or [Package Ecosystem](#package-ecosystem).
>     * A type of low-effort [Maintainer](#maintainer) with reduced responsibilities, working as a stand-in of the actual Maintainer.
>     * Cares about the continued security posture of the project.
>     * Concerned mostly with updating dependencies or applying security fixes.
> * May step in on behalf of the Maintainer on behalf of the [Language Ecosystem](#language-ecosystem) or [Package Ecosystem](#package-ecosystem) where the component is published.
> * May step in on behalf of the Maintainer if they are unavailable or unresponsive.
> * May have repository commit privileges for the [Maintainer](#maintainer)'s project.
> * May publish updates on behalf of the [Maintainer](#maintainer).


### Provenance ✍️ {#provenance}

> 1. (SCVS-2020, CDXAG-2024) The [chain of custody](#chain-of-custody) and origin of a software component.
>     * Provenance incorporates the [point of origin](#point-of-origin) through distribution as well as derivatives in the case of software that has been modified.
> 1. (NTIA-2021) Data about the chain of custody of the software and all of the constituent components, potentially including data about the authors and locations from where the components were obtained.
>
> (Ref: [SCVS-2020](#references-and-terms), NTIA-2021, CPANSec-2024)


### Release

> 1. (CPANSec-2024) A named and versioned snapshot of the codebase, that is announced as suitable for general use (e.g. "is stable"), and possibly published through a public repository, a language or package ecosystem or, some other way.
>
> (Ref: [CPANSec-2024](#references-and-terms))


### Remote Data Processing (CRA)

> 1. (CRA-2024-03) Data processing at a distance the software for which is designed and developed by the manufacturer, or under the responsibility of the manufacturer, and the absence of which would prevent the product with digital elements from performing one of its functions.
>
> (Ref: [CRA-2024-03](#references-and-terms))

### Repository

> 1. (CPANSec-2024) The tooling, storage, services and regime used for collaborating on improving a codebase over time, either locally or remotely across a network.
>
> (Ref: [CPANSec-2024](#references-and-terms))


### Second-party component ✍️ {#second-party-component}

> * See
>     * [Component, second-party](#second-party).


### SBOM (Software Bill of Materials) {#sbom}

> 1. (CRA-2024-03) A formal record containing details and supply chain relationships of components included in the software elements of a product with digital elements.
> 1. (SCVS-2020, CDXAG-2024) A complete, formally structured, and machine-readable inventory of all software components and associated metadata, used by or delivered with a given piece of software.
> 1. (NTIA-2021) A formal record containing the details and supply chain relationships of various components used in building software.
>     * Software developers and vendors often create products by assembling existing open source and commercial software components.
>     * The SBOM enumerates these components in a product.
>
> (Ref: [CRA-2024-03](#references-and-terms), SCVS-2020, CDXAG-2024, NTIA-2021)


### SBOM Attributes

#### SBOM Author Name (Attribute) {#sbom-author}

> [!NOTE]
> * FIXME: Expand on this topic

> (Ref: [CISA-2024-9](#references-and-terms))

#### SBOM Timestamp (Attribute) {#sbom-timestamp}

> [!NOTE]
> * FIXME: Expand on this topic

> (Ref: [CISA-2024-9](#references-and-terms))

#### SBOM Type (Attribute) {#sbom-type}

> [!NOTE]
> * FIXME: Expand on this topic

> (Ref: [CISA-2024-9](#references-and-terms))

#### SBOM Primary Component (Attribute) {#sbom-primary-component}

> 1. (CISA-2024-9) The Primary Component, or root of dependencies, is the subject of the SBOM or the foundational component being described in the SBOM.
>     * […] component attributes […] are also identified for this component, just as they are for the direct and transitive components.
>
> (Ref: [CISA-2024-9](#references-and-terms))

#### Component Name (Attribute) {#component-name}

> [!NOTE]
> * FIXME: Expand on this topic

> (Ref: [CISA-2024-9](#references-and-terms))

#### Version (Attribute) {#version}

> [!NOTE]
> * FIXME: Expand on this topic

> (Ref: [CISA-2024-9](#references-and-terms))

#### Supplier Name (Attribute) {#supplier-name}

> [!NOTE]
> * FIXME: Expand on this topic

> (Ref: [CISA-2024-9](#references-and-terms))

#### Cryptographic Hash (Attribute) {#cryptographic-hash}

> [!NOTE]
> * FIXME: Expand on this topic

> (Ref: [CISA-2024-9](#references-and-terms))

#### Unique Identifier (Attribute) {#unique-identifier}

> [!NOTE]
> * FIXME: Expand on this topic

> (Ref: [CISA-2024-9](#references-and-terms))

#### Relationships (Attribute) {#relationships}

> [!NOTE]
> * FIXME: Expand on this topic

> (Ref: [CISA-2024-9](#references-and-terms))

#### License (Attribute) {#license}

> [!NOTE]
> * FIXME: Expand on this topic

> (Ref: [CISA-2024-9](#references-and-terms))

#### Copyright Holder (Attribute) {#copyright-holder}

> [!NOTE]
> * FIXME: Expand on this topic

> (Ref: [CISA-2024-9](#references-and-terms))


### SBOM Roles

> 1. (CPANSec-2024) A person, agent or actor that does something with an SBOM document, or with specific metadata attributes in an SBOM document.
>     * This may include operations like Creating, Updating, Verifying, Censoring or Sharing SBOM documents or attributes.
> 1. (CISA-2024-3) "Data is only good if it is in the hands of the right people."
>
> (Ref: [CISA-2024-3](#references-and-terms))

#### SBOM Assembler (Role) ✍️ {#sbom-assembler-role}

> 1. (CPANSec-2024) An 🟨 [SBOM Contributor](#sbom-contributor) (Non-authoritative metadata provider) that produces an SBOM that contains any resolved dependencies as part of a build, packaging or container assembly process.
>    * MAY consume [Source SBOM](#source-sbom-type), [Build SBOM](#build-sbom-type) and/or [Deployed SBOM](#deployed-sbom-type) type documents
>    * SHOULD produce [Build SBOM](#build-sbom-type) and/or [Deployed SBOM](#deployed-sbom-type) type documents
>
> (Ref: [CPANSec-2024](#references-and-terms))

#### SBOM Author (Authoritative Metadata provider) (Role) ✍️ {#sbom-author-role}

> [!NOTE]
> 1. (CPANSec-2024) SBOM Authors who are not authoritative sources, but instead gather SBOM metadata from different dependencies, may be referred to as an [SBOM Assembler](glossary#sbom-assembler-role).
> 1. (CPANSec-2024) SBOM Authors may also collect, assemble, update, or annotate SBOM metadata — _They make sure the metadata and related artifacts are **Current**_.
>     * They may for example collect SBOMs throughout build dependency resolution, and assemble (merge), translate (transform), to produce SBOMs for analysis or audit purposes. (NTIA-2021, "Transform" category, paraphrased)
> 1. (CPANSec-2024) An SBOM Author who is tasked with removing (censoring) sensitive information from SBOM documents may be called [SBOM Censor](glossary#sbom-censor-role)

> 1. (CPANSec-2024) 🟥 SBOM Author (Authoritative).
>     * An authoritative source of an SBOM, or an SBOM metadata attributes.
> 1. (CISA-2024-3) Creates an SBOM.
> 1. (CPANSec-2024) SBOM Authors create, define, or sign SBOM metadata — _They make sure the attributes and related artifacts **Exist**_.
>     * This mostly means authoritative metadata attributes as laid out in the different [Supply-chain Roles](supplychain-sbom#supply-chain-roles-and-metadata).
>     * In addition to attributes encountered throughout the supply-chain, they care about the attributes listed in the table below.
>     * They may edit SBOM files manually or use tooling for analyzing artifacts, or ideally – use have SBOMs generated automatically as part of a build process. (NTIA-2021, "Produce" category)
>
> (Ref: [CISA-2024-3](#references-and-terms), [NTIA-2021](#references-and-terms), [CPANSec-2024](#references-and-terms))

#### SBOM Contributor (Non-authoritative metadata provider) (Role) {#sbom-contributor-role}

> 1. (CPANSec-2024) 🟨 SBOM Author (Non-authoritative)
>     * A non-authoritative [SBOM Author](#sbom-author-role).
> 1. (CPANSec-2024) Someone that gathers, assembles or updates SBOMs from different sources into a new SBOM.
>     * This is a _informal_ Role separate from "SBOM Author" for clarifying the responsibility when the Role intends to _gather_, _assemble_ or _update_ metadata attributes, instead of being the authoritative _creator_ of an attributes.
>     * This assumes some attributes may be in need of updating as an SBOM is passed down a supply-chain – for example to correct upstream assumptions like 'Download location', add missing attributes, or update the list of resolved dependencies.
>     * The intention is to distinguish between "SBOM Author" and "SBOM Assembler" in the same way as one distinguishes between "Create" and "Update" in CRUD – to clarify responsibilities and expectations for who is the original source of some metadata attributes.
> 
> (Ref: [CISA-2024-3](#references-and-terms), [NTIA-2021](#references-and-terms), [CPANSec-2024](#references-and-terms))

#### SBOM Distributor (Role) {#sbom-distributor-role}

> 1. (CPANSec-2024) 🟩 SBOM Distributor.
>     * SBOM Distributor roles distribute, curate, or index SBOM metadata — _They make sure the metadata and related artifacts are made **Available** to others_.
>     * They don't have any specific metadata attributes that are commonly used across the different supply-chain consumer roles, beyond ensuring that SBOMs are available for others to use and refer to.
> 1. (CISA-2024-3) Receives SBOMs for the purpose of sharing them with [SBOM Consumers](#sbom-consumer-role) or other Distributors.
> 1. (CISA-2023) Additionally, an SBOM Distributor may care about the following activities.
>     * Discovery: Mechanism used by the consumer to know the SBOM exists and how to access it.
>     * Access: Access control mechanisms used by the author or provider to regulate who can view or use an SBOM.
>     * Transport: Mechanism provided by the author or distributor to transfer an SBOM.  Also, the action of the consumer receiving an SBOM.
> 
> (Ref: [CISA-2023](#references-and-terms), [CISA-2024-3](#references-and-terms), [CPANSec-2024](#references-and-terms))

#### SBOM Consumer (Role) {#sbom-consumer-role}

> 1. (CPANSec-2024) 🟦 SBOM Consumer.
>     * SBOM Consumer roles gather, inspect, analyze, aggregate or verify SBOM metadata — _They make sure metadata and related artifacts are **Useful**, **Complete**, **Correct** or **Compliant**_.
>     * They don't have any specific metadata attributes that are commonly used across the different supply-chain Consumer roles.
> 1. (CISA-2024-3) Receives the transferred SBOM.
>     * This could include roles such as third parties, authors, integrators, and end users.
> 1. (NTIA-2021, "Consume" category) They may view SBOM files to understand the contents, and use this information to support decision making & business processes, or to compare and contrast SBOMs to discover significant changes or vulnerabilities.
> 
> (Ref: [CISA-2024-3](#references-and-terms), [NTIA-2021](#references-and-terms), [CPANSec-2024](#references-and-terms))

#### SBOM Censor (Role) {#sbom-censor-role}

> 1. (CPANSec-2024) 🟪 SBOM Censor.
>     * An [SBOM Author](#sbom-author) that removes or anonymizes sensitive metadata from an SBOM before distribution.
>
> (Ref: [CPANSec-2024](#references-and-terms))


### SBOM Types

> 1. (CPANSec-2024) [Software Bill of Materials](#sbom-software-bill-of-materials) variations, produced under certain circumstances.
>
> (Ref: [CPANSec-2024](#references-and-terms))

#### Design SBOM (Type) {#sbom-design-type}

> 1. (CISA-2023) SBOM of intended, planned software project or product with included components (some of which may not yet exist) for a new software artifact.
>
> (Ref: [CISA-2023](#references-and-terms))

#### Source SBOM (Type) {#sbom-source-type}

> 1. (CISA-2023) SBOM created directly from the development environment, source files, and included dependencies used to build an product artifact.
>
> (Ref: [CISA-2023](#references-and-terms))

#### Build SBOM (Type) {#sbom-build-type}

> 1. (CISA-2023) SBOM generated as part of the process of building the software to create a releasable artifact (e.g., executable or package) from data such as source files, dependencies, built components, build process ephemeral data, and other SBOMs.
>
> (Ref: [CISA-2023](#references-and-terms))

#### Analyzed SBOM (Type) {#sbom-analyzed-type}

> 1. (CISA-2023) SBOM generated through analysis of artifacts (e.g., executables, packages, containers, and virtual machine images) after its build.
>     * Such analysis generally requires a variety of heuristics.
>     * In some contexts, this may also be referred to as a “3rd party” SBOM.
>
> (Ref: [CISA-2023](#references-and-terms))

#### Deployed SBOM (Type) {#sbom-deployed-type}

> 1. (CISA-2023) SBOM provides an inventory of software that is present on a system.
>     * This may be an assembly of other SBOMs that combines analysis of configuration options, and examination of execution behavior in a (potentially simulated) deployment environment.
>
> (Ref: [CISA-2023](#references-and-terms))

#### Runtime SBOM (Type) {#sbom-runtime-type}

> 1. (CISA-2023) SBOM generated through instrumenting the system running the software, to capture only components present in the system, as well as external call-outs or dynamically loaded components.
>    *  In some contexts, this may also be referred to as an “Instrumented” or “Dynamic” SBOM.
>
> (Ref: [CISA-2023](#references-and-terms))


### Software

> 1. (CRA-2024-03) The part of an electronic information system which consists of computer code.
>
> (Ref: [CRA-2024-03](#references-and-terms))


### Software Bill of Materials (SBOM) {#software-bill-of-materials}

> * See
>     * [SBOM (Software Bill of Materials)](#sbom).


### Software Identification (SWID) {#swid}

> 1. (SCVS-2020) An ISO standard that formalizes how software is tagged.
>    * SWID is considered to be one of three [SBOM](#sbom) formats, together with [CycloneDX](#cyclonedx) and [SPDX](#spdx).
>
> (Ref: [SCVS-2020](#references-and-terms))


### Software Package Data Exchange (SPDX) {#spdx}

> 1. (SCVS-2020) A Linux Foundation project which produces a [software bill of materials](#sbom-software-bill-of-materials) specification and a standardized list of open source licenses.
>     * SPDX is considered to be one of three [SBOM](#sbom) formats, together with [CycloneDX](#cyclonedx) and [SWID](#swid).
>
> (Ref: [SCVS-2020](#references-and-terms))


### Source ⚠️  ✍️ {#source}

> 1. (SLSA-2023) An [artifact](#artifact) that was directly authored ~~or reviewed~~ by persons, without modification.
>     * It is the beginning of the supply chain; we do not trace the provenance back any further.
>     * E.g. a git commit (source) hosted on GitHub ([platform](#platform)).
>
> (Ref: [SLSA-2023](#references-and-terms), CPANSec-2024)


### SPDX (Software Package Data Exchange)

> * See
>     * [Software Package Data Exchange (SPDX)](#spdx).


### Substantial Modification (CRA)

> 1. (CRA-2024-03) A change to the product with digital elements following its placing on the market, which affects the compliance of the product with digital elements with the essential requirements set out in the EU Cyber Resilience Act, Annex I, Part I, or which results in a modification to the intended purpose for which the product with digital elements has been assessed.
>     * Where products with digital elements are subsequently modified, by physical or digital means, in a way that is not foreseen by the manufacturer [...], the modification should be considered as substantial. (CRA-2024-03, Recital 38)
>     * Security updates are not Substantial Modifications. (CRA-2024-03, Recital 39)
>
> (Ref: [CRA-2024-03](#references-and-terms))


### Supplier ⚠️  {#supplier}

> [!CAUTION]
> * (CPANSec-2024) The term 'Supplier' is not well defined, and should be either avoided in favor of a more precise term, or otherwise be disambiguated.

> 1. (NTIA-2021) An entity that creates, defines, and identifies components and produces associated SBOMs.
>     * A supplier may also be known as a manufacturer, vendor, developer, integrator, maintainer, or provider.
>     * Ideally, all suppliers are also authors of SBOMs for the suppliers’ components.
>     * Most suppliers are also consumers.
>     * A supplier with no included upstream components is a root entity.
> 1. (CDXAG-2024) The name of an entity that creates, defines, and identifies components.
>
> * See also
>     * [Author](#author)
>     * [Maintainer](#maintainer)
>     * [Manufacturer](#manufacturer)
>
> (Ref: [NTIA-2021](#references-and-terms), CDXAG-2024)


### SWID (Software Identification) {#software-identification-id}

> * See
>     * [Software Identification (SWID)](#swid).


### Third-party component ✍️ {#third-party-component}

> * See
>     * [Component, third-party](#third-party).


### Transitive Dependency

> * See
>     * [Dependency (Transitive)](#dependency-transitive)


### Vendor

> * See also
>     * [Manufacturer](#manufacturer) or
>     * [Author](#author).


## References and terms

This glossary is partly based on terms from the following sources.

- (CPANSec-2024) – These are commentary and proposed improvements made by the author(s) of this document. If you agree or have improvements, [share it with us](#document-status)!
- (CISA-2023) CISA [Types of Software Bill of Materials (SBOM)](https://www.cisa.gov/resources-tools/resources/types-software-bill-materials-sbom) (Public Domain)
- (SCVS-2020) OWASP [Software Component Verification Standard 1.0 Glossary](https://scvs.owasp.org/scvs/appendix-a-glossary/) Appendix A ([CC-BY-SA-4.0](https://github.com/OWASP/Software-Component-Verification-Standard/blob/master/LICENSE.txt))
- (SLSA-2023) OpenSSF [Supply-chain Levels for Software Artifacts 1.0 Terminology](https://slsa.dev/spec/v1.0/terminology)
- (CRA-2024-03) EU [Cyber Resilience Act, Annex II, Chapter I, Article 3 (Definitions)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=136), pages 136-146, published 2024-03-12.
- (CPAN-2015) [CPAN Glossary](https://neilb.org/2015/09/05/cpan-glossary.html) by Neil Bowers, published 2015-09-05.
- (SBOMit-2023) [SBOM on in-toto Terminology](https://github.com/SBOMit/specification/blob/main/specification.md#15-terminology), Specification introduction section 1.5, published July 2023.
- (NTIA-2021) [NTIA The Minimum Elements for an SBOM, Glossary](https://www.ntia.doc.gov/files/ntia/publications/sbom_minimum_elements_report.pdf#page=25), pages 25-27, published 2021-07-12.
- (CISA-2024-3) [CISA SBOM Sharing Roles and Considerations](https://www.cisa.gov/resources-tools/resources/sbom-sharing-roles-and-considerations), Appendix, published 2024-03-28.
- (PCISSF-2023) [PCI Software Security Framework](https://docs-prv.pcisecuritystandards.org/Software%20Security/Standard/PCI-Secure-Software-Standard-v1_2_1.pdf), published May 2023.
- (CDXAG-2024) [Authoritative Guide to SBOM](https://cyclonedx.org/guides/OWASP_CycloneDX-Authoritative-Guide-to-SBOM-en.pdf), Second edition, Appendix A, published April 2024.
- (CISA-2024-9) [CISA Framing Software Component Transparency: Establishing a Common Software Bill of Materials (SBOM)](), Third edition, Sections 2.2.1.4, 2.2.2, and Appendix B, Published 2024-09-03
    - FIXME: Replace after publishing: [draft document](https://docs.google.com/document/d/1z8hKtPxs5OWaspst120NHN9XXgyULGl2aKdSebwIYPc/edit)
- (EUBG-2022-2) [The ‘Blue Guide’ on the implementation of EU product rules](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:52022XC0629(04)#d1e2047-1-1) Chapter 2.2, published 2022-06-29.
- (EUBG-2022-3) [The ‘Blue Guide’ on the implementation of EU product rules](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:52022XC0629(04)#d1e3120-1-1) Chapter 3.1, published 2022-06-29.
- (EUBG-2022-4) [The ‘Blue Guide’ on the implementation of EU product rules](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:52022XC0629(04)#d1e4315-1-1) Chapter 4.3, published 2022-06-29.
- (NIXOS-2024) [Nix concepts](https://zero-to-nix.com/concepts), as of 2024-08-15

## About this document

* Version: 0.7.1
* License: [CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/deed)
* Copyright: © Salve J. Nilsen <sjn@oslo.pm>, Some rights reserved.

You may use, modify and share this file under the terms of the [CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/deed) license.


### Acknowledgements

Several people have been involved in the development of this document

* Salve J. Nilsen (main author)
* Josh Bressers
