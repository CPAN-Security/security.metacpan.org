---
layout: page
title: Supply-chain SBOM roles
description: Roles in a supply-chain who care about SBOM metadata
toc: true
---
# A Simplified Open Source Supply Chain with SBOMs

> [!CAUTION]
> ## Document status: ⚠️  DRAFT
> What you see here is a DRAFT of the Supply Chain SBOM roles & responsibilities overview, by the CPAN Security Group (CPANSec).
> As long as this document is in DRAFT, all of the points and ideas below are _suggestions_, and open to revision, deletion or amending – by you!
>
> - Contribute on Github: [https://github.com/CPAN-Security/security.metacpan.org/tree/main/docs/supplychain-sbom.md](https://github.com/CPAN-Security/security.metacpan.org/tree/main/docs/supplychain-sbom.md)
> - Discuss on IRC: [ircs://ssl.irc.perl.org:7063/#cpan-security](ircs://ssl.irc.perl.org:7063/#cpan-security)


## Roles in a supply chain

In all Open Source Software supply chains, we find people filling distinct roles that each care about some metadata or tasks in SBOMs.

With this diagram we'll attempt to offer an overview of these roles, how they are related, and what they do and care about.

### Basic assumptions

- Any single person may have one or more roles, and switch between them as needed.
- Tasks they may care about include…
    - Exists (create, sign)
    - Correctness (update, annotate, rename, delete)
    - Availability (distribute, assemble, index)
    - Matches the accompanying software component (verify).


```mermaid
stateDiagram-v2
    direction TB
    accTitle: An idealized Open Source supply chain

    state "Open Source Steward\nOwner" as author_owner
    state "Author\nCustodian" as author
    state "Distributor" as repository_distributor
    state "Packager" as language_packager
    state "Curator" as language_curator
    state "Distributor" as language_distributor
    state "Contributor" as contributor
    state "Patcher" as package_patcher
    state "Packager\nBuilder" as package_packager
    state "Curator" as package_curator
    state "Distributor" as package_distributor
    state "Manufacturer\nOwner" as integrator_owner
    state "Developer" as developer
    state "Deployer\nBuilder" as deployer
    state "Scanner\nSecOps\nPentester" as scanner
    state "Consumer\nUser" as consumer
    state "Auditor" as auditor_internal
    state "Auditor" as auditor_external

    classDef createsSBOM stroke:red,stroke-width:2px;
    classDef updatesSBOM stroke:orange,stroke-width:2px;
    classDef assemblesSBOM stroke:cyan,stroke-width:2px;
    classDef verifiesSBOM stroke:green,stroke-width:2px;

    class author_owner createsSBOM
    class manufacturer_owner createsSBOM
    class author createsSBOM
    class package_patcher updatesSBOM
    class package_packager assemblesSBOM
    class package_distributor updatesSBOM
    class language_distributor updatesSBOM
    class developer assemblesSBOM
    class deployer assemblesSBOM
    class auditor_internal verifiesSBOM
    class auditor_external verifiesSBOM

    [*] --> ecosystem_author

    state "Author Environment" as ecosystem_author {
        [*] --> author
        author_owner --> author
        author --> language_packager
    }

    author --> ecosystem_repo
    ecosystem_repo --> author
    language_packager --> ecosystem_lang

    state "Language Ecosystem" as ecosystem_lang {
        [*] --> language_distributor
        [*] --> language_curator
        language_curator --> language_distributor
    }

    language_distributor --> ecosystem_integrator
    language_distributor --> ecosystem_package
    ecosystem_lang --> ecosystem_lang

    state "Public Collaboration Ecosystem" as ecosystem_repo {
        [*] --> repository_distributor
    }

    repository_distributor --> contributor
    contributor --> repository_distributor

    repository_distributor --> ecosystem_package
    repository_distributor --> ecosystem_integrator

    state "Package Ecosystem" as ecosystem_package {
        [*] --> package_patcher
        [*] --> package_packager
        package_patcher --> package_packager
        package_packager --> package_curator
        package_packager --> package_distributor
        package_curator --> package_distributor
    }

    package_distributor --> ecosystem_integrator
    ecosystem_package --> ecosystem_package

    state "Manufacturer Environment" as ecosystem_integrator {
        [*] --> developer
        integrator_owner --> developer
    }

    developer --> auditor_internal
    developer --> ecosystem_prod
    developer --> [*]

    state "Production Environment" as ecosystem_prod {
        [*] --> deployer
        deployer --> scanner
    }

    deployer --> consumer
    deployer --> auditor_external
```

# Supply-chain Ecosystems and Environments

## Author Environment

One or more developers that publish an Open Source component.

* Publishes Open Source
* May have a project development life-cycle


## Integrator Environment

A business or institution that is responsible for developing and building the application that is required to have an accompanying SBOM document.
Management is expected to ensure that this assembled SBOM document describes the application as required by law.

* Does NOT publish Open Source
* Has a project development life-cycle

### Manufacturer Environment

* See [Integrator Environment](#integrator-environment).


## Language Ecosystem

A language ecosystem hosts, indexes and distributes components specific for a programming language

* Examples: CPAN (Perl), PyPI (Python), NPM (Node/JS)
* May have upstream language ecosystems
* May have downstream language ecosystems
* May have automated Patcher
* May be Public or Private


## Package Ecosystem

A package ecosystem [patches](#patcher), [repackages](#packager), [curates](#curator), [indexes and hosts](#distributor) components for a specific OS distribution making packages available for easy download and use.

* Examples: APT (Debian, Ubuntu), RPM (AlmaLinux, SuSE), Ports (FreeBSD, OpenBSD)
* May have upstream package ecosystems
* May have downstream package ecosystems
* May be Public or Private


## Public Collaboration Ecosystem

A website or tool that offers a public collaboration repository to Authors, so they may cooperate and share ongoing work in public.

* Examples: Github, Codeberg, Bitbucket, Gitlab, Gitea and others.

### Repository Ecosystem

* See [Public Collaboration Ecosystem](#public-collaboration-ecosystem).


## Production Environment

The environment and systems where a product or service is executed on behalf of a customer, and thereby made available to their users.

* See also [Customer Environment](#customer-environment).

### Customer Environment

The environment and systems where a product or service is executed by a customer and thereby made available to their users.

* See also [Production Environment](#production-environment)


# Supply-chain Roles

## Open Source Steward

Within an [Author Environment](#author-environment), has the duty to ensure that the obligations in the EU Cyber Resilience Act are met.

> NOTE: Steward gets a specific defined meaning in the Cyber Resilience Act, so until this definition is established, we'll avoid using the term.

* See also [Owner](#owner)


## Manufacturer

Is a role within an [Integrator Environment](#integrator-environment).
When doing business within the European Economic Area (EEA), has the duty to ensure that the obligations in the EU Cyber Resilience Act are met.

* See also [Owner](#owner)

> [!IMPORTANT]
> | Field name                    | Required | Data type    | CycloneDX | SPDX | Legislation          |
> | :---------------------------- | :------- | :----------- | --------- | ---- | -------------------- |
> | CE Declaration                | No       | URL          |           |      | CRA AII.7            |
> | CE Support End Date           | No       | URL          |           |      | CRA AII.8            |
> | CE Instructions               | No       | URL          |           |      | CRA AII.9            |
> | CE Conformity Assessment Body | No       | URL          |           |      | CRA Article 47.1     |
> | SBOM Type                     | Yes      |              |           |      | |
> | SBOM Author                   | No       | Text         |           |      | NTIA-SBOM            |
> | SBOM Creation Time-stamp      | No       | DateTime     |           |      | NTIA-SBOM            |

> [!NOTE]
> Manufacturer has a specific defined meaning in the Cyber Resilience Act, so until this definition is established, be careful when using the term.

## Owner

Operates in an [Author Environment](#author-environment) or [Integrator Environment](#integrator-environment).
Has the legal ownership rights and liabilities for the component.
Is usually the [Author](#author), a business or some other type of legal entity.
May decide the name of the project and other project parameters for (or on behalf of) the [Author](#author) or [Developer](#developer).

> [!IMPORTANT]
> | Field name                    | Required | Data type    | CycloneDX | SPDX | Legislation          |
> | :---------------------------- | :------- | :----------- | --------- | ---- | -------------------- |
> | Manufacturer, Supplier Name   | Yes      | Text         |           |      | CRA AII.1, NTIA-SBOM |
> | Licenses                      | Yes      | SPDX License |           |      | |
> | Code Repository               | Yes      |              |           |      | |
> | SBOM Type                     | Yes      |              |           |      | |
> | SBOM Author                   | No       | Text         |           |      | NTIA-SBOM            |
> | SBOM Creation Time-stamp      | No       | DateTime     |           |      | NTIA-SBOM            |

* See also [Manufacturer](#manufacturer), [Open Source Steward](#open-source-steward).

### Supplier

Is a role within an [Integrator Environment](#integrator-environment).
The term is used within the NTIA "SBOM Minimum Elements" document as the legal source of a component.

* See also [Manufacturer](#manufacturer), [Owner](#owner).


## Author

Operates within an [Author Environment](#author-environment).
The initial and/or main creator of the component in question.
Typically works on all aspects of the code, including features, bug fixes, tests and security issues.
Has the final say on the original contents of the package.
The Author _can_ be a group of people, though a single point of responsibility is common.
If an Author has upstream (reverse) dependencies, the Author is also considered to be a Developer (as seen from the upstream Author's perspective.
See below).

> [!IMPORTANT]
> | Field name                    | Required | Data type    | CycloneDX | SPDX | Legislation          |
> | :---------------------------- | :------- | :----------- | --------- | ---- | -------------------- |
> | Manufacturer, Supplier Name   | Yes      | Text         |           |      | CRA AII.1, NTIA-SBOM |
> | Component Name                | Yes      | Text         |           |      | NTIA-SBOM            |
> | Version                       | Yes      | Text         |           |      | NTIA-SBOM            |
> | Dependencies                  | Yes      | List         |           |      | NTIA-SBOM            |
> | Security contact              | Yes      | URL          |           |      | CRA AII.2            |
> | Unique ID, Product ID         | Yes      | PURL         |           |      | CRA AII.3, NTIA-SBOM |
> | Purpose, Intended Use         | Yes      | Text         |           |      | CRA AII.4            |
> | Licenses                      | Yes      | SPDX License |           |      | |
> | Code Commit Revision          | No       |              |           |      | |
> | Code Repository               | Yes      |              |           |      | |
> | CE Declaration                | No       | URL          |           |      | CRA AII.7            |
> | SBOM Type                     | Yes      |              |           |      | |
> | SBOM Author                   | No       | Text         |           |      | NTIA-SBOM            |
> | SBOM Creation Time-stamp      | No       | DateTime     |           |      | NTIA-SBOM            |
> | SBOM Location                 | No       | URL          |           |      | CRA AII.10           |
> | Vulnerable versions/locations | No       |              |           |      | |


### Custodian

Operates within an [Author Environment](#author-environment).
A type of [Author](#author) with reduced responsibilities, working on behalf of the actual author.
Cares about the ongoing security of the code.
Typically only concerned with updating dependencies or applying security fixes.
Works with the Author primarily, and may take responsibility on their behalf when it comes to security concerns.
May work on behalf of the author if they are unavailable or unresponsive.


### Contributor

Operates independently, but through a [Public Collaboration Ecosystem](#public-collaboration-ecosystem).
Interacts with component with bug reports, feedback, quality assurance, testing, patches or pull requests.
May or may not have repository commit privileges.
May also have additional roles, including being a downstream [Developer](#developer), [Patcher](#patcher) or [Author](#author).


## Patcher

Operates within a [Package Ecosystem](#package-ecosystem).
Applies security and/or bug fixes to packages before building and packaging.
Works mainly with a downstream [Packager](#packager), and has [Author](#author)'s downstream ecosystems as upstream.

This role is necessary when...

* Upstream Author roles are not responsive or available, and thereby security fixes aren't applied there.
* When downstream constraints and requirements call for it – e.g. when back-porting of fixes are needed due to downstream LTS requirements.

> [!NOTE]
> * Patchers (a role that often is held by the same person as the Packager), may select and apply patches before building.
> * These patches may include back-ports of features, security fixes or other accommodations necessary for distributing multiple releases of the same upstream project, but within publishing constraints decided by the Curator of the Ecosystem (e.g. LTS releases, support contracts, etc.).
> * A Packager can both be found in-house (e.g. a business who uses a company-internal package mirror), for a Package Ecosystem provider (e.g. Debian), or a Language Ecosystem provider (e.g. a company-internal CPAN mirror that distributes patched packages).


## Packager

Operates within a [Package Ecosystem](#package-ecosystem) or an [Author Environment](#author-environment).
Within a package ecosystem, builds and creates packages from components received from an upstream source, optionally with patches applied from the [Patcher](#patcher).
Within an author environment, creates packages from their own project in preparation for publication in a downstream [Language Ecosystem](#language-ecosystem) (e.g. create a CPAN package for uploading to CPAN using the PAUSE interface).
Concerns themselves with correct package format and structure, and that package metadata is preserved and updated.

> [!NOTE]
> * Packagers take upstream components from an upstream source  and build and install them into a custom environment for producing system packages for their native packaging ecosystem (e.g. APT).
> * Upstream sources may be…
>     * Author's repository, or a Custodian's if a project is dormant (e.g. a repository on Codeberg).
>     * Language-specific packages distributed by a Language Ecosystem (e.g. CPAN).
> * E.g. someone in the #debian-perl group downloads, builds, tests and installs something from CPAN, but instead of doing a regular install, they us tooling like `dh-make-perl` to produce a custom installation directory that can be incorporated into a .deb archive.

> [!IMPORTANT]
> Packagers should add build environment metadata (including resolved dependencies) in an accompanying SBOM file.

### Builder

* See [Packager](#packager)


## Curator

Operates within a [Package Ecosystem](#package-ecosystem) or a [Language Ecosystem](#language-ecosystem).
Selects or pins which components are suitable for use downstream of the package ecosystem.
Works mainly with the [Distributor](#distributor) role.
Concerns themselves with both the stability and predictability of components, and how this is prioritized against the need for features, bug fixes and security updates.

> [!NOTE]
> * Curators may decide both whether and where the output of a Packager is distributed.
> * Curators may operate both in-house, in order to keep an eye on what is being automatically installed there, or they may make the decisions that happen on the Package or Language Ecosystem provider side.
> * Typically, a curator may consider LTS status, support contract terms or other reasons for distributing a package.


## Distributor

Operates within a [Package Ecosystem](#package-ecosystem) or a [Language Ecosystem](#language-ecosystem).
Ensures the availability of packages, that they are indexed correctly, and that any related metadata is up-to-date, correct and available.

> [!NOTE]
> * Distributors take packages that Patchers and Packagers produce, and ensure these are made available in a reliable way for downstream users according to the Curator's requirements. (e.g. by setting up and managing a Debian APT repository, or a CPAN mirror, or similar).
> If SBOM metadata is expected to accompany the packages in question, the Distributor makes sure this happens.

> [!IMPORTANT]
> | Field name                    | Required | Data type    | CycloneDX | SPDX | Legislation          |
> | :---------------------------- | :------- | :----------- | --------- | ---- | -------------------- |
> | Download location             | Yes      |              |           |      |                      |


## Developer

Operates within an [Integrator Environment](#integrator-environment).
Uses packages and components as dependencies in their own project, product or component.
A Developer is in many ways identical to an [Author](#author) from the upstream Author's perspective, with the main difference being that a Developer doesn't publish their work as Open Source.
A Developer that publishes their software as Open Source, is called an [Author](#author).

> [!IMPORTANT]
> * See also [Author](#Author).


### Deployer

Operates within a [Production Environment](#production-environment).
Final preparation and installation of the software into a CI/CD or [Production Environment](#production-environment).


## Scanner

May operate within a [Production Environment](#production-environment) or an [Integrator Environment](#integrator-environment).
Responsible for security checks, including runtime, dynamic and static checks, vulnerability monitoring, etc.
Communicates any issues or findings to any number of upstream roles, including the component [Deployer](#deployer), [Developer](#developer) or [Author](#author).

### SecOps

* See [Scanner](#scanner).

### Pentester

* See [Scanner](#scanner).


## Consumer

The software in use, in production, by a user.

### User

* See [Consumer](#consumer).


## Auditor

Verifies that all necessary metadata is available, up-to-date and made use of.


### Compliance

* See [Auditor](#auditor).


# Other terms

~~## Publisher

Operates within an [Author Environment](#author-environment).
Places the component on an ecosystem publishing platform, on behalf of the Author or Custodian.
Typically this role is done by the same people, but in some cases a separate account may be used; e.g. a business or organization account.~~


# References

* CRA AII: [Cyber Resilience Act, Annex II](https://data.consilium.europa.eu/doc/document/ST-17000-2023-INIT/EN/pdf#page=168), Draft dated 2023-12-20
* NTIA SBOM: [NTIA Minimum Elements for a Software Bill of Materials (SBOM)](https://www.ntia.doc.gov/files/ntia/publications/sbom_minimum_elements_report.pdf#page=9), Published 2021-07-12

# License

This document is © Salve J. Nilsen <sjn@cpan.org>.
Some rights reserved.
You may use, modify and share this file under the terms of the CC-BY-SA-4.0 license.
