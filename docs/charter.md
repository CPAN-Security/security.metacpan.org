---
layout: page
title: Charter
description: CPAN Security Group Charter
toc: true
---

## Document status: ⚠️  DRAFT

What you see here is a **DRAFT** for the charter of a CPAN Security Group (_CPANSec_).
Until published by a founding member, all of the points and ideas below are *suggested*, and open to revision, deletion or amending.

* Contribute on Github: [https://github.com/CPAN-Security/security.metacpan.org/blob/charter/docs/charter.md](https://github.com/CPAN-Security/security.metacpan.org/blob/charter/docs/charter.md)
* Discussion on IRC: [ircs://ssl.irc.perl.org:7062/#cpan-security](ircs://ssl.irc.perl.org:7062/#cpan-security)


## Purpose

This charter lays out the background, intentions, mandate, scope, means and methods for the CPAN Security Group.
This document also explicitly acknowledges a few related organizations and communities, and spell out responsibility demarcation lines between these, if any.


## Name

The full name of the group is **CPAN Security Group**.
Valid abbreviations are **CPANSec**.


## Background

The group was established at the Perl Toolchain Summit 2023 in Lyon, France, with the purpose of establishing a forum for discussing and improving:

- Author/repo signing
- Vulnerability databases + MetaCPAN
- Security incident support for non-core CPAN modules
- Toolchain security
- Supply-chain security
- etc.

This list was subject for discussions and revision, and the resulting projects, tasks and topics are laid out under the subject lines below.


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
- CPAN distributions that function as shims (wrappers) for non-CPAN projects or resources. Examples:
  - CPAN Distributions that are pure wrappers around compiled libraries (e.g. XS modules wrapping `libxml2` or `sqlite3`);
  - CPAN Distributions (outside the `Alien::` namespace) that embed or use third-party (non-CPAN) projects or APIs directly;
  - The `Alien::` distribution namespace;
- CPAN supply chain security, Chain-of-Trust infrastructure, and security around the Perl/CPAN Toolchain, CPAN/MetaCPAN itself and PAUSE;
- CPAN distribution metadata and how these are communicated;
- Emergency security updates on CPAN;
- The security culture in CPAN and communities in general;

For details, please consult the [Projects](#projects) list below.


### Out-of-scope

- Security issues handled by &lt;cpan-security&#64;perl.org&gt; 
  - The perl interpreter itself
  - Perl Core modules managed by &lt;perl5-porters@perl.org&gt;
- Supply-chain issues that are found outside of CPAN, for example:
  - Downstream security issues related to repackaging or patching of CPAN distros by third party packaging system (e.g. Debian's apt, RedHat's rpm, etc).
- Third party libraries, files and services linked to or used by CPAN distributions (unless the library is packaged with the affected CPAN distribution);
- MetaCPAN
   - Handled by the MetaCPAN team.
- Mozilla::CA
   - Handled by the libwww-perl team, and semi-automatically updated.
- Perl software published outside of CPAN (e.g. via Github download links, or with private hosting).
- Security issues handled by &lt;pause-admin&#64;perl.org&gt;
  - Compromised PAUSE accounts
  - All other security issues regarding PAUSE


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

While the _CPANSec_ has no formal mandate or responsibilities, it may still seek and accept public statements of support, acknowledgement or formal mandates from the following relevant community stakeholders.

- The Perl Steering Council
- The PAUSE team
- The MetaCPAN team
- The Perl Security list
- Perl NOC
- The Perl Modules list
- The CPAN Workers list
- The Perl and Raku Foundation
- Linux distributions' package manager teams

Public statements of support should not be considered more than an acknowledgment of intent, and as non-binding promises to support each other in good faith to resolve relevant security issues.

Formal mandates, on the other hand are intended to establish clear lines of responsibility and accountability, and with this, function as meaningful steps to establish legitimacy.

If the _CPANSec_ receives _and accepts_ a formal mandate from a community stakeholder group, the _CPANSec_ members acknowledge that this group may withdraw their formal mandate at any time if they decide that _CPANSec_ is incapable or unwilling to fulfill this mandate, or in case the _CPANSec_ decides to delegate any received responsibilities to a third party.

In the unfortunate situation when a stakeholder group _CPANSec_ has received a mandate from is disbanded, becomes unresponsive, or transfers it's responsibilities to a third party, the _CPANSec_ members may ask for a formal mandate from a replacing community stakeholder group.


### Formal Mandates

The _CPANSec_ has currently **no formal mandates**.


### Volunteer participation and Guarantees

The _CPANSec_ consists of volunteers, and while we enter and engage in this forum with good intentions and willingness to assist in constructive dialogue, we reserve the right to withhold assistance to any individuals or institutions who do not conduct themselves in a like-minded manner.

This means that the products of our work should be considered _best effort_, and be accepted _AS IS_. We do not offer indemnification, insurance or guarantees.


### Joining the _CPANSec_

The _CPANSec_ has several forums, but the ones that manage embargoed information is moderated and for invited volunteers.
To join, please reach out through one of the _CPANSec_ [public contact points](#public-contact-points).


### Projects

For an up-to-date list of projects, please consult the _CPANSec_ [Projects page](https://github.com/orgs/CPAN-Security/projects) on Github.


### Public contact points

- Chat (IRC): [ircs://ssl.irc.perl.org:7062/#cpan-security](ircs://ssl.irc.perl.org:7062/#cpan-security)
- Fediverse: [@cpan_security@perl.social](https://perl.social/profile/cpan_security)
- Email: &lt;cpan-security&#64;perl.org&gt;


### Public resources, feeds & channels

- Main website: [https://security.metacpan.org/](https://security.metacpan.org/)
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


## About this document

Version: v0.7.0
License: CC-BY-SA-4.0
