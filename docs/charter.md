---
layout: page
title: CPAN Security WG Charter
toc: true
---

**IMPORTANT ⚠️ IMPORTANT ⚠️ IMPORTANT**
-----------------

What you see here is a **proposal** for the charter of a CPAN Security Working Group (_CPAN-SEC_), to be set up in 2023. Until published by a founding member, all of the points and ideas below are *suggested*, and open to revision, deletion or amending.

Discussion on IRC: [ircs://irc.perl.org/#cpan-security](ircs://irc.perl.org/#cpan-security)

**IMPORTANT ⚠️ IMPORTANT ⚠️ IMPORTANT**

------------------


## Purpose

This charter lays out the background, intentions, mandate, scope, means and methods for the CPAN Security Working Group (CPAN-SEC, until a name is decided).
This document also explicitly acknowledges a few related organizations and communitites, and spell out responsibility demarcation lines between these, if any.


## Background

The group was established at the Perl Toolchain Summit 2023 in Lyon, France, with the purpose of establishing a forum for discussing:

- Author/repo signing
- Vulnerability databases + MetaCPAN
- Security incident support for non-core CPAN modules
- Toolchain security
- Supply-chain security
- etc.

This list has been subject for discussions and revisioning, and the resulting tasks and topics are layed out under the subject lines below.


### Founding members

Founding members, from left to right in the group picture linked below.

![Group picture showing stigo, ingy, sjn, leont, tux and garu](../media/cpan-sec-group-picture-PTS2023.jpeg)

- stigo
- Ingy döt Net
- Salve J. Nilsen
- Leon Timmermans
- H. Merijn "Tux" Brand
- Breno "garu" Oliveira


## Goals and Intentions

The _CPAN-SEC_ intends to be a forum for coordinating and assisting in resolving security issues found on CPAN. This may include:

- Assist authors and third-party developers in dealing with vulnerabilities and general security advisories related to distributions indexed on Perl's package manager, CPAN;
- Be a contact point for reporters of potential vulnerabilities when authors are unresponsive;
- Assist in determining the validity and severity of vulnerabilities, if appropriate and needed;
- Offer help in contacting authors;
- Assess, publish and keep track of vulnerability information and general security advisories related to non-core distributions on CPAN;
- Request CVE numbers for vulnerabilities related to non-core distributions on CPAN;
- Share and document best security practices to authors and users;
- Raise awareness to security threats and mitigations in Perl applications that rely on the CPAN ecosystem;
- Act as a trusted intermediator for reporting potential security vulnerabilities to distributions, including managing and responsible disclosure of embargoed security information for a reasonable amount of time pertaining non-core distributions on CPAN, and communication with package managers and distribution channels;
  - ~~In what ways / For how long? (e.g. max 14 days?) /  explain!~~
    - Rationale: Let's keep specific embargo durations out of the charter, so we don't have to re-publish the charter when this changes. (garu)
- Provide a forum for discussing and coordinating around supply chain security, integrity, metadata and the communication of these, including but not limited to:
  - SBOM and other ways for tracking and communicating software changes, including interaction with external tooling and sources of security advisories;
  - The Update Framework (TUF) integration;
  - Third-party vulnerability scanning support;



### In-scope

The _CPAN-SEC_ concerns itself with a limited domain:

- Distributions published on CPAN, including dual-life core modules;
- Supply chain security, including CPAN/MetaCPAN and PAUSE
  - [Artifact Transparency Logs](https://transparency.dev) like sigstore or sigsum
  - Tooling and infrastructure for establishing chain-of-trust
  - Tooling for downstream verification of chain-of-trust
  - Tooling for the creation and verification of SBOM objects commonly in use


### Out-of-scope

- Security issues handled by &lt;cpan-security&#64;perl.org&gt; 
  - The perl interpreter itself
  - Perl Core modules managed by &lt;perl5-porters@perl.org&gt;
- Supply-chain issues that are found outside of CPAN, for example:
  - Downstream security issues related to repackaging or patching of CPAN distros by third party packaging system (e.g. Debian's apt, Redhat's rpm, etc).
- Third party libraries, files and services linked to or used by CPAN distributions;
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

The _CPAN-SEC_ has **no power, agency or special privileges over CPAN distributions or their authors**, except for those releases done by the team itself.

The working group publishes information, advisories and recommendations, but cannot force anyone to follow them.
Our goal is to facilitate in-good-faith productive and security-focused discussions, with the intention to assist in resolving any issues in a responsible and timely manner.


### Relations with commercial, governmental and other non-volunteering entities

_CPAN-SEC_ is a forum to assist in resolving technical issues.
It should be regarded as a contact point for technical staffo.
The _CPAN-SEC_ is not directly associated with any third party and does not do contract work for third parties, nor provides non-technical assistance.

If you represent the management or legal department at your business and/or need to address non-technical issues, we probably cannot help you.

**FIXME**: Allow for "non-technical support" offers, like funding etc.


## Responsibilities and Mandates

While the _CPAN-SEC_ has no formal mandate or responsibilities, it may still seek and accept public statements of support or acknowledgement from the following relevant community stakeholders.
In addition, the _CPAN-SEC_ may ask for formal mandates from _delegating authorities_ (DA):

- The Perl Steering Council (DA)
- The PAUSE core team (DA)
- The MetaCPAN team (DA)
- The Perl Security list (DA)
- Perl NOC
- The Perl Modules list
- The CPAN Workers list
- The Perl and Raku Foundation
- Linux distributions' package manager teams

Public statements of support should not be considered more than an acknowledgment of intent, and as non-binding promises to support each other in good faith to resolve relevant security issues.

Formal mandates, on the other hand are intended to establish clear lines of responsibility and accountability, and with this function as meaningful steps to establish legitimacy.

If the _CPAN-SEC_ asks for a formal mandate from a delegating authority (DA), the _CPAN-SEC_ members acknowledge that delegating authority may withdraw their mandate at any time if they decide the _CPAN-SEC_ is incapable or unwilling to fulfil its mandate, or in case the CPAN-SEC decides to delegate any recieved responsibilities to a third party.

In the unfortunate situation when a delegating authority is disbanded, becomes unresponsive, or transfers/loses its autority to delegate responsibilities to us, the CPAN-SEC members may ask for a formal mandate from a replacing authority.


### Formal Mandates

The _CPAN-SEC_ currently has no formal mandates.


### Volunteer participation and Guarantees

The _CPAN-SEC_ consists of volunteers, and while we enter and engage in this forum with good intentions and willingness to assist in constructive dialogue, we reserve the right to withhold assistance to any individuals or institutions who do not conduct themselves in a like-minded manner.

This means that the products of our work should be considered _best effort_, and be accepted _AS IS_. We do not offer indemnification, insurance or guarantees.


### Joining the _CPAN-SEC_

The _CPAN-SEC_ forum itself is moderated and for invited volunteers. To join it, please reach out to our mailing list. (**FIXME**). 


## Example Means and Methods

The _CPAN-SEC_ activities may include a number of efforts, ongoing activities, security projects, tooling development and managing of publication channels and other resources.

Examples of these may include…


### Ongoing activities

- Gathering of security-relevant statistics, metrics and metadata
- Publish CPAN advisories
- Apply for CVE numbers
- …


### Projects

- Tooling for signing of CPAN artifacts – [CPAN Provenance](https://github.com/orgs/CPAN-Security/projects/3)
- Collect and publish vulnerabilities in CPAN distributions, including creating & managing infrastructure for showing vulnerability info on MetaCPAN. (`CPANSEC` or `CPAN-VULN`) – [CPAN Vulnerability Index](https://github.com/orgs/CPAN-Security/projects/10)
- Tooling for creating and verifying Software Bills of Materials for CPAN distributions – [CPAN Software Bills of Materials](https://github.com/orgs/CPAN-Security/projects/1)
- High-priority updates to CPAN packages
- ~~Registering as a CVE Numbering Authority~~
  - **FIXME**: Probably not useful? Please share your thoughts.
- …


### Tools

- TBD


### Public contact points

- TBD
- ircs://irc.perl.org/#cpan-security
- &lt;cpan-security@perl.org&gt; (mailing list)
- Presence on Mastodon, Twitter, etc.
- …


### Public resources, feeds & channels

- TBD
- RSS/Atom feed with advisories
- Blog under a well-known domain (e.g. security.cpan.org)
- Github group: https://github.com/CPAN-Security
- …


## Other acknowledgements

### Initiators
  
- garu
- stigo
- mickey
- haarg
- leont
- ingy
- …


### Charter authors

- sjn
- stigo
- garu
- timlegge
- …


## Version

v0.6.6
