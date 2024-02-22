---
layout: page
title: Charter
description: CPAN Security Group Charter
toc: true
---

## Document status: ⚠️  DRAFT

What you see here is a **DRAFT** for the charter of a CPAN Security Group (_CPANSec_).
Until published by a founding member, all of the points and ideas below are *suggested*, and open to revision, deletion or amending.

Discussion on IRC: [ircs://ssl.irc.perl.org:7062/#cpan-security](ircs://ssl.irc.perl.org:7062/#cpan-security)


## Purpose

This charter lays out the background, intentions, mandate, scope, means and methods for the CPAN Security Group (CPANSec).
This document also explicitly acknowledges a few related organizations and communitites, and spell out responsibility demarcation lines between these, if any.


## Name

The full name of the group is **CPAN Security Group**. Valid abbreviations are **CPANSec**.


## Background

The group was established at the Perl Toolchain Summit 2023 in Lyon, France, with the purpose of establishing a forum for discussing and improving:

- Author/repo signing
- Vulnerability databases + MetaCPAN
- Security incident support for non-core CPAN modules
- Toolchain security
- Supply-chain security
- etc.

This list was subject for discussions and revisioning, and the resulting projects, tasks and topics are laid out under the subject lines below.


## Goals and Intentions

The _CPANSec_ intends to be a forum for coordinating and assisting in resolving security issues found on CPAN. This may include:

- Assist authors and third-party developers in dealing with vulnerabilities and general security advisories related to distributions indexed on Perl's package ecosystem, CPAN;
- Be a contact point for reporters of potential vulnerabilities when authors are unresponsive;
- Assist in determining the validity and severity of vulnerabilities, if appropriate and needed;
- Offer help in contacting authors;
- Assess, publish and keep track of vulnerability information and general security advisories related to non-core distributions on CPAN;
- Request CVE numbers for vulnerabilities related to non-core distributions on CPAN;
- Share and document best security practices to authors and users;
- Raise awareness to security threats and mitigations in Perl applications that rely on the CPAN ecosystem;
- Act as a trusted intermediator for reporting potential security vulnerabilities to distributions, including managing and responsible disclosure of embargoed security information for a reasonable amount of time pertaining non-core distributions on CPAN, and communication with package managers and distribution channels;
- Provide a forum for discussing and coordinating around supply chain security, integrity, metadata and the communication of these, including but not limited to:
  - SBOM and other ways for tracking and communicating software and metadata changes, including interaction with external tooling and sources of security advisories;
  - The Update Framework (TUF) integration;
  - Third-party vulnerability scanning support;


### In-scope

The _CPANSec_ concerns itself with a limited domain:

- Distributions published on CPAN, not including dual-life core modules;
- CPAN supply chain security, Chain-of-Trust infrastructure, and security around the Perl/CPAN toolchain, CPAN/MetaCPAN itself and PAUSE;
- CPAN distribution metadata and how these are communicated;
- Emergency security updates on CPAN;
- The security culture in CPAN and communities in general;

For details, please consult the [Projects](#projects) list below.


### Out-of-scope

- Security issues handled by &lt;cpan-security&#64;perl.org&gt; 
  - The perl interpreter itself
  - Perl Core modules managed by &lt;perl5-porters@perl.org&gt;
- Supply-chain issues that are found outside of CPAN, for example:
  - Downstream security issues related to repackaging or patching of CPAN distros by third party packaging system (e.g. Debian's apt, Redhat's rpm, etc).
- Third party libraries, files and services linked to or used by CPAN distributions (unless the library is packaged with the affected CPAN distribution);
- ~~CPAN distributions that function as shims (wrappers) for non-CPAN projects or resources.~~ Examples:
  - ~~CPAN Distributions that are pure wrappers around compiled libraries (e.g. XS modules wrapping `libxml2` or `sqlite3`)~~
    - **Rationale**: XS modules are _in scope_ until tooling for warning about upstream vulnerabilities is in place. (sjn)
  - ~~CPAN Distributions (outside the `Alien::` namespace) that embed or use third-party (non-CPAN) projects or APIs directly.~~
    - **Rationale**: Shims/wrappers/api modules on CPAN are _in scope_, but we cannot address issues related to the third-party (external) libraries or APIs they link to or use. So for example if `XML::LibXML` contains a vulnerability, it's in scope, but if libxml2 (which it links to) has a vulnerability, we have nothing to do with it, as it is not directly related to code *on* CPAN. (garu)
  - ~~The `Alien::` distribution namespace~~
    - **Rationale**: `Alien::` distributions are _in scope_ until tooling for warning about upstream vulnerabilities is in place. (stigo)
  - ~~Mozilla::CA~~
    - **Rationale**: `Mozilla::CA` is _in scope_ until the module is either phased out/deprecated or kept automatically in sync with upstream CA. (stigo); Furthermore, Mozilla::CA is apparently about to be auto-updated sometime soon?
- MetaCPAN
  - **FIXME**: Offloading managment of MetaCPAN security issues depends on getting an agreement with the MetaCPAN folks, which we don't have as of 2023-06-17. Also - is this necessary and desirable? Please share why we should (not) do this.
- Perl software published outside of CPAN (e.g. via github download links, or with private hosting).
- …


### Relations with CPAN Authors and Distributions

The _CPANSec_ has **no power, agency or special privileges over CPAN distributions or their authors**, except for those releases done by the team itself.

The working group publishes information, advisories and recommendations, but cannot force anyone to follow them.
Our goal is to facilitate in-good-faith productive and security-focused discussions, with the intention to assist in resolving any issues in a responsible and timely manner.


### Relations with commercial, governmental and other non-volunteering entities

_CPANSec_ is a forum to assist in resolving technical issues.
It should be regarded as a contact point for technical staff.
The _CPANSec_ is not directly associated with any third party and does not do contract work for third parties, nor provides non-technical assistance.

If you represent the management or legal department at your business and/or need to address non-technical issues, we probably cannot help you.

**FIXME**: Allow for "non-technical support" offers, like funding etc.


## Responsibilities and Mandates

While the _CPANSec_ has no formal mandate or responsibilities, it may still seek and accept public statements of support or acknowledgement from the following relevant community stakeholders.
In addition, the _CPANSec_ may ask for formal mandates from _delegating authorities_ (DA):

- The Perl Steering Council (DA)
- The PAUSE team (DA)
- The MetaCPAN team (DA)
- The Perl Security list (DA)
- Perl NOC
- The Perl Modules list
- The CPAN Workers list
- The Perl and Raku Foundation
- Linux distributions' package manager teams

Public statements of support should not be considered more than an acknowledgment of intent, and as non-binding promises to support each other in good faith to resolve relevant security issues.

Formal mandates, on the other hand are intended to establish clear lines of responsibility and accountability, and with this, function as meaningful steps to establish legitimacy.

If the _CPANSec_ asks for a formal mandate from a delegating authority (DA), the _CPANSec_ members acknowledge that delegating authority may withdraw their mandate at any time if they decide the _CPANSec_ is incapable or unwilling to fulfil its mandate, or in case the CPANSec decides to delegate any received responsibilities to a third party.

In the unfortunate situation when a delegating authority is disbanded, becomes unresponsive, or transfers/loses its autority to delegate responsibilities to us, the CPANSec members may ask for a formal mandate from a replacing authority.


### Formal Mandates

The _CPANSec_ has currently **no formal mandates**.


### Volunteer participation and Guarantees

The _CPANSec_ consists of volunteers, and while we enter and engage in this forum with good intentions and willingness to assist in constructive dialogue, we reserve the right to withhold assistance to any individuals or institutions who do not conduct themselves in a like-minded manner.

This means that the products of our work should be considered _best effort_, and be accepted _AS IS_. We do not offer indemnification, insurance or guarantees.


### Joining the _CPANSec_

The _CPANSec_ forum itself is moderated and for invited volunteers. To join it, please reach out to our mailing list, or our IRC chat for an informal conversation. (**FIXME**). 


### Projects

- [Artifact Transparency Logs](https://github.com/orgs/CPAN-Security/projects/2)
  - Introduce sigstore or sigsum to CPAN, possibly based on guidelines from [transparency.dev](https://transparency.dev)
- [Provenance and Supply Chain Security](https://github.com/orgs/CPAN-Security/projects/3)
  - Introduce tooling and infrastructure for establishing provenance, chain-of-trust and chain-of-custody
  - Introduce tooling for downstream verification of provenance, chain-of-trust and chain-of-custody
- [Metadata and Software Bill of Materials](https://github.com/orgs/CPAN-Security/projects/1)
  - Tooling for the creation and verification of SBOM objects commonly used to communicate the composition and pedigree of CPAN dependencies, even when these dependencies cross ecosystem boundraries.
  - Update CPAN package metadata to enable end-users to comply with legislative obligations.
- [Vulnerability Index](https://github.com/orgs/CPAN-Security/projects/10)
  - Standardization and publishing of CPAN package vulnerabilities in relevant indexes (our own, CPANSA, CVE or whatever), to ensure that common (including third-party) tooling for Software Composition Analysis or vulnerability assessment work with CPAN dependencies.
- [Software Composition Analysis](https://github.com/orgs/CPAN-Security/projects/6)
  - Improve or create user-interfacing tooling used for analyzing dependencies for known vulnerabilities.
- [Security Patch Tooling](https://github.com/orgs/CPAN-Security/projects/11)
  - Develop tooling for publishing and applying third-party security patches to CPAN distributions that have non-responsive authors, to enable high-priority updates to CPAN packages.
  - Explore opportunities for simplifying downstream fixes to reach upstream authors.
- [Security Outreach & Information](https://github.com/orgs/CPAN-Security/projects/12)
  - Establish a website and social media presence for outreach and information sharing, and keep these up to date.
- [CPANSec Governance, Policy & Funding](https://github.com/orgs/CPAN-Security/projects/7)
  - Establish procedures for responsible disclosure, communication and other related mechanisms, including documentation on how vulnerabilities and malicious code incidents are handled.
  - Create a group charter and accountability procedures.
  - Raise funds for CPAN Security Group projects.


### Public contact points

- Main website: [https://security.metacpan.org/](https://security.metacpan.org/)
- Chat (IRC): [ircs://ssl.irc.perl.org:7062/#cpan-security](ircs://ssl.irc.perl.org:7062/#cpan-security)
- Fediverse: [@cpan_security@perl.social](https://perl.social/profile/cpan_security)
- Email: &lt;cpan-security&#64;perl.org&gt;


### Public resources, feeds & channels

- [CPANSec News RSS feed](https://security.metacpan.org/feed.xml).
- Github group: [https://github.com/CPAN-Security](https://github.com/CPAN-Security)


## Acknowledgements

### Founding members

![Group picture showing stigo, ingy, sjn, leont, tux and garu](../media/cpan-sec-group-picture-PTS2023.jpeg)

Picture taken by `sjn` at the Perl Toolchain Summit 2023 in Lyon, France.

From left to right,

- stigo
- Ingy döt Net
- Salve J. Nilsen
- Leon Timmermans
- H. Merijn "Tux" Brand
- Breno "garu" Oliveira

#### Additional initiators

- haarg
- mickey


### Charter authors

- sjn
- stigo
- garu
- timlegge
- …


## Version

v0.6.7
