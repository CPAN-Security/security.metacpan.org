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

### Chain of custody

> Auditable documentation of point of origin as well as the method of transfer from point of origin to point of destination and the identity of the transfer agent.

### Component function

> The purpose for which a software component exists.
> Examples of component functions include parsers, database persistence, and authentication providers.

### Component type

> The general classification of a software components architecture.
> Examples of component types include libraries, frameworks, applications, containers, and operating systems.

### CycloneDX :writing_hand:

> An OWASP managed software bill of materials specification designed to be lightweight and security-focused.

### Direct dependency :writing_hand:

> A software component that is referenced by a program itself.
> For indirect dependencies, see [Transitive dependency](#transitive-dependency).

### Package manager :writing_hand:

> A distribution mechanism that makes software artifacts discoverable by ~~requesters~~ users of a specific package ecosystem.

### Package URL (PURL)

> An ecosystem-agnostic specification which standardizes the syntax and location information of software components.

### Pedigree

> Data which describes the lineage and/or process for which software has been created or altered.

### Point of origin :writing_hand:

> The supplier and associated metadata from which a software component has been procured, transmitted, or received.
> ~~Package repositories, release distribution platforms, and version control history are examples of various points of origin.~~

### Procurement :writing_hand:

> The process of agreeing to terms and acquiring software or services for later use.
> This includes agreeing to Open Source licenses.

### Provenance

> The chain of custody and origin of a software component.
> Provenance incorporates the point of origin through distribution as well as derivatives in the case of software that has been modified.

### Software bill of materials (SBOM)

> A complete, formally structured, and machine-readable inventory of all software components and associated metadata, used by or delivered with a given piece of software.

### Software Identification (SWID)

> An ISO standard that formalizes how software is tagged.

### Software Package Data Exchange (SPDX)

> A Linux Foundation project which produces a software bill of materials specification and a standardized list of open source licenses.

### Third-party component :writing_hand:

> ~~Any software component not directly created including open source, "source available", and commercial or proprietary software.~~

> Any software component not directly created, including "source available", commercial or proprietary software.
> Open Source software is closer to a "second-party component" as the developer in fact has a legal relationship with the FOSS component project by accepting the project license.

### Transitive dependency :writing_hand:

> A software component that is indirectly used by a program by means of being a dependency of a dependency.
> Dependencies of transitive dependencies are also transitive dependencies (it's dependencies all the way down!).
> See also [Direct dependency](#direct-dependency).


## References, licenses and terms

This glossary is partly based on

- (SCVS 2020) OWASP [Software Component Verification Standard 1.0 Glossary](https://scvs.owasp.org/scvs/appendix-a-glossary/) Appendix A ([CC-BY-SA-4.0](https://github.com/OWASP/Software-Component-Verification-Standard/blob/master/LICENSE.txt))
- (CPANSec 2024) Misc. improvements marked with :writing_hand: (CC-BY-SA-4.0)
