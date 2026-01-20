---
layout: single
published: false
toc: true
title: "CPANSec: 2025 Year in Review"
date: 2026-01-10 17:05:00 +0000
category: blog
tags: purl cna cve cra sbom year cpansec perl cpan security
authors:
  - timlegge
  - thibaultduponchelle
  - stigtsp
  - sjn
  - jjatria
author_profile: true
excerpt: "CPANSec year in review: Website updates, CVEs published, conference talks held, security modules written and guidelines published."
---

# CPANSec: 2025 Year in Review

## Website Updates
Salve made substantial improvements to the site's layout, style, and content.
The website now features a modern design, and numerous community members have contributed new content throughout the year.

## Outreach and Conferences
We have stickers! Salve created stickers from the CPANSec logo Stig and he made, and has been distributing these at various conferences.
Keep an eye out for them at future events!
Salve has also been "secretly" proposing a mascot for CPANSec, and placed it all over the website and elsewhere. 🦆

### Presentations delivered
(Available at [security.metacpan.org/presentations/](https://security.metacpan.org/presentations/))

1. **FOSDEM 2025** (Software Bill of Materials devroom) (Salve J. Nilsen)
1. **German Perl Workshop 2025** — CPAN Security and Sustainability in light of the EU Cyber Resilience Act (Salve J. Nilsen)
1. **Perl Toolchain Summit 2025** (PTS)
1. **German Perl Workshop 2025** — Metadata Clapalong 👏 (Salve J. Nilsen)
1. **London Perl Workshop 2025** – An update on CPANSec (José Joaquín Atria)

### Podcasts
CPANSec also participated in the [Underbar podcast](https://underbar.cpan.io/) while in Leipzig for PTS 2025.
You can listen to [all episodes](https://underbar.cpan.io/) or jump straight to [Episode 7 featuring CPANSec](https://underbar.cpan.io/episodes/7/).


## New Security-Related Modules
The community released several security-focused modules this year:

1. [Crypt::OpenSSL3](https://metacpan.org/pod/Crypt::OpenSSL3) by **LEONT**
1. [Crypt::SysRandom](https://metacpan.org/pod/Crypt::SysRandom) by **LEONT**
1. [Crypt::URandom::MonkeyPatch](https://metacpan.org/pod/Crypt::URandom::MonkeyPatch) by **RRWO**
1. [Crypt::URandom::Token](https://metacpan.org/pod/Crypt::URandom::Token) by **STIGTSP**
1. [Dist::Zilla::Plugin::Test::MixedScripts](https://metacpan.org/pod/Dist::Zilla::Plugin::Test::MixedScripts) by **RRWO**
1. [Dist::Zilla::Plugin::Test::CVE](https://metacpan.org/pod/Dist::Zilla::Plugin::Test::CVE) by **RRWO** (experimental)
1. [SBOM::CycloneDX](https://metacpan.org/pod/SBOM::CycloneDX) by **GDT**
1. [Software::Policies](https://metacpan.org/pod/Software::Policies) by **MIKKOI**
1. [URI::PackageURL](https://metacpan.org/pod/URI::PackageURL) by **GDT** (new release)
1. [Test::MixedScripts](https://metacpan.org/pod/Test::MixedScripts) by **RRWO**

**Maintenance & Security Adoptions:** The following modules were taken over for active maintenance, often involving security fixes:

1. [Crypt::CBC](https://metacpan.org/pod/Crypt::CBC) by **TIMLEGGE**
1. [Crypt::OpenSSL::PKCS10](https://metacpan.org/pod/Crypt::OpenSSL::PKCS10) by **TIMLEGGE**
1. [Crypt::Primes](https://metacpan.org/pod/Crypt::Primes) by **TIMLEGGE**
1. [Crypt::Random](https://metacpan.org/pod/Crypt::Random) by **TIMLEGGE**
1. [Data::Entropy](https://metacpan.org/pod/Data::Entropy) by **RRWO** (deprecated)
1. [Module::Signature](https://metacpan.org/pod/Module::Signature) by **TIMLEGGE**
1. [Net::CIDR::Set](https://metacpan.org/pod/Net::CIDR::Set) by **RRWO**
1. [Net::OAuth](https://metacpan.org/pod/Net::OAuth) by **RRWO**

## Security Documentation

We published and updated the [CPAN Author's Guide to Random Data for Security](https://security.metacpan.org/2025/01/03/randomness-guide.html).

Additionally, the Perl core and FAQ (v5.42.0) were [updated](https://perldoc.perl.org/5.42.0/perldelta) to recommend modern modules for secure random data generation.

Our outreach to encourage [security policies](https://security.metacpan.org/2025/01/05/add-a-security-policy.html) has shown some success.
As of December 17, 2025, **270 distributions** on CPAN now include an explicit security policy.

## Patch Tooling Initiative
We explored the feasibility of automated distribution patching.
Thibault created a proof-of-concept built on `App::cpm` (with some modularity in mind) consisting of three components:
1. A "database" of patches (mocked as `CPANSec::Patches`) as a patches source.
1. A "match and patch" mechanism based on existing `CPAN::Patches` (note `CPAN::DistroPrefs` could have been used as well).
1. A modified `cpm` installer supporting an opt-in `--with-security-patches` flag.

The patching facility remains opt-in for installer and the extra patching module and database should remain optional runtime requirements.
With a different lifecycle for the database of patches that could be updated anytime (or at each patching run).
Think CPANSA::DB but for patches.
Integration to installers should remain minimal.

This experiment served as a technical exploration rather than a final design choice.
Separately, [Gianni Ceccarelli](https://metacpan.org/author/DAKKAR) released [cpandak](https://metacpan.org/dist/App-CpanDak) for `cpanm`, and Thibault released [CPAN::Tarball::Patch](https://metacpan.org/dist/CPAN-Tarball-Patch) to facilitate patching via `CPAN::Distroprefs`.

## Supply Chain Security
Thibault completed the [CPAN Starjacking study](https://security.metacpan.org/docs/cpan-starjacking.html) and conducted penetration testing on PAUSE (specifically targeting forms and payloads).

He also examined "decompression confusion" and malicious compression uploads, reviewing supply chain attack techniques that surfaced throughout 2025 in other ecosystems.
Thibault, Stig, and Leon also developed two private hardening fixes for PAUSE.

The group collectively reviewed several suspicious uploads, including an encrypted (but non-malicious) package, and discussed the operational model with PAUSE administrators.

## Software Bill of Materials (SBOM)

GDT delivered a coherent stack of modules to support SBOM generation in the CycloneDX format:

At the core is [SBOM::CycloneDX](https://metacpan.org/dist/SBOM-CycloneDX), a library that allows programmatic creation and manipulation of CycloneDX version 1.6 SBOM documents, intended to be reused by other tools and integrations.

Building on top of that, [App::CPAN::SBOM](https://metacpan.org/dist/App-CPAN-SBOM) provides a command-line interface to generate an SBOM for a CPAN distribution, making SBOM generation immediately accessible to authors and maintainers.

Finally, [Module::CoreList::SBOM](https://github.com/giterlizzi/perl-Module-CoreList-SBOM) is an experimental module that generates SBOMs for the Perl core module set as defined by [Module::CoreList](https://metacpan.org/dist/Module-CoreList), which tracks the set of modules and utilities shipped with Perl distribution.

Together, these modules provide a concrete and incremental path toward SBOM adoption in the Perl ecosystem, supporting dependency transparency, traceability, and future regulatory alignment, including emerging requirements around software supply-chain security.

References:
- [Roles and metadata in Open Source supply-chains](https://security.metacpan.org/docs/supplychain-sbom.html)
- [Minimum Elements for Software Bill of Materials](https://www.ntia.gov/files/ntia/publications/sbom_minimum_elements_report.pdf)


## Package URL (PURL) Standardization

Package URL (PURL) is a standard for identifying software packages independently of their ecosystem or distribution channel.
It is designed to support identification of software packages across software supply chains and a wide range of use cases, including Software Bills of Materials, vulnerability databases, advisories and disclosures, exploitability reports, and dependency reporting.

PURL is now a formal specification standardized as [ECMA-427](https://ecma-international.org/publications-and-standards/standards/ecma-427/), developed within the Technical Committee [TC54](https://tc54.org/purl/), and is increasingly adopted as a common reference across tools, SBOM formats, and software supply-chain security processes.

Since they are intended to be used in a wide set of contexts, PURLs need to be versatile enough to cater for at least two different use cases: one in which we need a stable and unambiguous representation of a specific package (to be used in e.g. SBOMs), and one in which we need a broad representation for a wide range of releases or versions of an individual package (for use in e.g. CVEs or security advisories).

We have been working on a schema for PURLs that can be used as a standard way to refer to CPAN distributions in both of these cases.
This includes the definition of the relevant components and their semantics, in a way that is consistent with the CPAN and PAUSE models.

References:
- [URI::PackageURL](https://metacpan.org/dist/URI-PackageURL)
- [CPAN type spec](https://github.com/package-url/purl-spec/blob/main/types-doc/cpan-definition.md)
- [CPANSec pURL Maker](https://gist.github.com/jjatria/5d50d47c53fe77ab3c63dbc4c9de5641)
- [CVE 5.2.0 added support for packageURL fields](https://github.com/CVEProject/cve-schema/releases/tag/v5.2.0)


## The EU Cyber Resilience Act

On the CRA side, Salve attended weekly meetings thoughout the year, contributing to both the [Open Regulatory Working Group's CRA FAQ](https://cra.orcwg.org/), and conversations around the CRA Voluntary Attestation regime.

The FAQ is shaping up to become a quite useful resource, and several people are dedicated to keep it up-to-date with the different authoritative sources on the CRA.

This work helps ensure that the Perl ecosystem remains informed about emerging EU security regulations.
Expect more on this in the coming year!

## Perl and CPAN CNA

The CPAN Security Group was authorized by the CVE Program as a CVE Numbering Authority (CNA) on **February 25, 2025**.
The CNA’s scope includes the Perl core and all CPAN modules.

Throughout the year, Stig, Tim, Robert, and Breno have managed the process of reviewing and publishing CVEs.
Other CPANSec members, Perl developers, and CPAN authors have also been critical in providing technical details for these issues.
If you are interested in helping with the CNA or CVE process, please reach out.

In its first year, the CNA issued **47 CVEs**.
While CVE IDs typically start with the year the vulnerability was discovered or made public, 14 of this year’s CVEs were issued for vulnerabilities that had been public for several years.
CPANSec is making a concerted effort to request CVEs for these older "legacy" vulnerabilities to ensure better historical tracking.

**CVE Issuance by Year of Discovery:**

* **2025:** 34
* **2024:** 9
* **2022 – 2011:** 4 total (1 each for 2022, 2020, 2013, and 2011)

### CVE Coordination

While CVEs are often specific to a single distribution, this year featured a unique coordination effort.
Three different JSON modules shared the same vulnerability, resulting in three separate CVEs.
The maintainers involved were highly responsive, allowing the CNA to coordinate the simultaneous release of the CVEs and patched versions within a short window.
We would like to thank these maintainers for their patience and diligence.

## CVE Types and Trends
The top three vulnerability types issued this year all relate to **insufficient entropy** (weak randomness).
These are generally found in cryptographic functions or authentication mechanisms.
To help developers, the [CPAN Author’s Guide to Random Data for Security](https://security.metacpan.org/docs/guides/random-data-for-security.html) offers guidance on selecting secure random sources.

"Dependencies on Vulnerable Third-Party Components" accounted for **7 CVEs**.
These issues typically occur in **XS-based modules** that include a bundled library in the distribution.
Rounding out the top five were **Buffer Overflows**, which included one Perl core vulnerability along with several XS modules.

### Vulnerability Breakdown (CWE)

| Count | CWE ID | Description |
| :--- | :--- | :--- |
| **22** | CWE-338 | Use of Cryptographically Weak PRNG |
| **11** | CWE-331 | Insufficient Entropy |
| **7** | CWE-340 | Generation of Predictable Numbers or Identifiers |
| **7** | CWE-1395 | Dependency on Vulnerable Third-Party Component |
| **6** | CWE-122 | Heap-based Buffer Overflow |
| **3** | CWE-427 | Uncontrolled Search Path Element |
| **2** | CWE-916 | Password Hash with Insufficient Effort |
| **2** | CWE-190 | Integer Overflow or Wraparound |
| **2** | CWE-1287 | Improper Validation of Input Type |

> [!NOTE]
> 12 other CWE types were recorded with 1 instance each, including Command Injection (CWE-78), Race Conditions (CWE-689), and Timing Discrepancies (CWE-208).

### CVE Program Status
Despite a "funding crisis" earlier this year that threatened the global CVE program, funding was restored and the program is stable.
This event served as a wake-up call, and plans are underway internationally to ensure the long-term sustainability of the CVE ecosystem.

### OSS CNA Users Group
Members of our team regularly attend the **OSS CNA Users Group** (organized by Red Hat) to share insights with other open-source projects and align our processes with industry standards.

## Security and OSS Sustainability
Salve has also spent a substantial time on developing a specification for communicating project needs.
In 2025, this project was accepted to the [EMCA Technical Committee 54](https://tc54.org/) Task Group 4 standardization track: [CONTRIBUTING.yaml](https://tc54.org/contributing-yaml/).
Open Source project sustainability is also a security concern, and this work is taking steps to address some of the long-term communication concerns in this regard.
This specification has drawn experiences from long-term Open Source contributors from a wide and varied selection of communities - including the ones around Perl and CPAN.

## Join CPANSec!
And finally, a reminder: CPAN Security Group is a volunteer effort!
This group's success and capability to respond depends on volunteer efforts by Perl and CPAN experts with a passion for security and sustainability.
If you are such a person, then [reach out to us](https://security.metacpan.org/#learn-more--contribute)!
