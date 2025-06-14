---
layout: single
title:  "CPANSec retrospective 2024"
date:   2025-03-13 00:23:17 +0200
category: blog
tags: cpansec update history
author: Thibault Duponchelle
excerpt: Here is the CPANSec 2024 Retrospective
---

That was a big year for CPANSec.

In case some of the activities this year flew under your radar, please find some of the achievements listed in this retrospective!

## Common Vulnerabilities and Exposures (CVEs)
In 2024, CPANSec worked to illustrate the importance of the Common Vulnerabilities and Exposures (CVE) process.

Until then, our experience is that very few CVEs were published for Perl modules and tooling.  
Beyond that, people and authors were a bit reluctant to deal with those CVEs.

CVEs are not a sign of bad quality or maintenance of a code,
but a professional way of tagging and tracking a vulnerability,
also indicating the importance of the concerned code.

### Vulnerable Spreadsheet Parsing modules
The start of the year was marked by vulnerabilities reported for [Spreadsheet::ParseExcel](https://metacpan.org/pod/Spreadsheet::ParseExcel):
- [CVE-2023-7101: Spreadsheet::ParseExcel arbitrary code execution vulnerability](https://security.metacpan.org/2024/02/10/vulnerable-spreadsheet-parsing-modules.html#cve-2023-7101-spreadsheetparseexcel-arbitrary-code-execution-vulnerability)
- [CVE-2024-22368: Spreadsheet::ParseXLSX denial of service vulnerability](https://security.metacpan.org/2024/02/10/vulnerable-spreadsheet-parsing-modules.html#cve-2024-22368-spreadsheetparsexlsx-denial-of-service-vulnerability)
- [CVE-2024-23525: Spreadsheet::ParseXLSX XML external entity attack vulnerability](https://security.metacpan.org/2024/02/10/vulnerable-spreadsheet-parsing-modules.html#cve-2024-23525-spreadsheetparsexlsx-xml-external-entity-attack-vulnerability)

### Insecure modes of CPAN installers
CPANSec continued with CPAN installer [cpanminus](https://github.com/miyagawa/cpanminus) (a major installer of the Perl ecosystem):
- [CVE-2024-45321: App::cpanminus through 1.7047 downloads code using insecure HTTP](https://security.metacpan.org/2024/08/26/cpanminus-downloads-code-using-insecure-http.html#cve-2024-45321)

This latest is a bit related to a fix from a CPANSec member earlier in 2023 to the CPAN installer [cpan](https://metacpan.org/dist/CPAN/view/scripts/cpan) (part of Perl core distribution):
- [CVE-2023-31484: CPAN.pm before 2.35 does not verify TLS certificates when downloading distributions over HTTPS](https://nvd.nist.gov/vuln/detail/CVE-2023-31484)

### Other
Similarly, a CVE was emitted for the [POSIX::2008](https://metacpan.org/dist/POSIX-2008) module:
- [CVE-2024-55564: POSIX::2008 package before 0.24 for Perl has a potential execve50c env buffer overflow](https://nvd.nist.gov/vuln/detail/CVE-2024-55564)

## Improving CVE tooling
Along with CVEs, tooling to monitor, fetch or test for them is very useful.
They can be installed in workflows or tooling as a gate keeper
so that companies do not ship vulnerable pieces of code.

CPANSec produced and improved a few tools to fetch or test for CVEs:
- [CPANSEC::Admin::Command::CVEScan](https://metacpan.org/pod/CPANSEC::Admin::Command::CVEScan)
- [Net::NVD](https://metacpan.org/pod/Net::NVD)
- [Net::CVE](https://metacpan.org/pod/Net::CVE)
- [Test::CVE](https://metacpan.org/pod/Test::CVE)

Note: Not all CVE tooling are managed by CPANSec, I'm thinking in particular [CPAN::Audit](https://metacpan.org/pod/CPAN::Audit) and its sidecar [CPAN::Audit::DB](https://metacpan.org/pod/CPAN::Audit::DB) or [NIST::NVD](https://metacpan.org/pod/NIST::NVD).

But CPANSec follows closely and contributes to them when possible.

## CPANSec as a CVE Numbering Authority (CNA)
In 2023 and 2024, if CPANSec helped with or contributed to CVEs for CPAN,
the _assignment_ of CVEs remained under control of another CNA, MITRE.

CPANSec members worked throughout the year to give the group the ability to assign CVEs.
After all, who knows better than CPANSec the impact of CVEs on Perl modules? (If you know someone, send them our way! :)

By end of the year, the groundwork to become a CNA was completed.

This designation was officially granted in February 2025: [CPANSec is now a CVE Numbering Authority (CNA)!](https://security.metacpan.org/2025/02/25/cpansec-is-cna-for-perl-and-cpan.html)

The news of CPANSec becoming CVE Numbering Authority (CNA) was [saluted](https://social.kernel.org/notice/ArVdrlmn4RNfxhSJhQ) by community luminaries like Greg Kroah-Hartman (Linux kernel) and Daniel Stenberg (cURL).

The CNA administrators are Timothy Legge, Stig Palmquist and Breno G. de Oliveira.

## Introduced a SECURITY Policy template
In parallel, CPANSec collectively pushed for authors to publish a Security Policy.

Doing so is considered Open Source Good Practice, especially as security is becoming more and more critical.

This effort resulted in creating a [template](https://security.metacpan.org/docs/guides/security-policy-for-authors.html#examples), providing [guidelines](https://security.metacpan.org/docs/guides/security-policy-for-authors.html) and, last but not least, communicating this initiative in various channels.

In order to help authors integrating a Security Policy, new tools [Software::Security::Policy](https://metacpan.org/pod/Software::Security::Policy) and [Dist::Zilla::Plugin::SecurityPolicy](https://metacpan.org/pod/Dist::Zilla::Plugin::SecurityPolicy) were created and published.

## Study on Random Number generation for Security
Generating random numbers can help in a wide variety of tasks.
All of them don't have the same level of criticality.
In particular, random generated data used in a security context requires extra care.

CPANSec studied and reviewed CPAN modules for this use, and shared this in [Random Data For Security Use](https://security.metacpan.org/docs/guides/random-data-for-security.html).

## Working on "TLS in core"
A vanilla install of Perl (distribution) does not provide HTTPS capabilities, and this is annoying.
That's an important (and difficult) topic that is addressed, across core developers and CPANSec.

Things started to go into motion in 2024 to make it happen.

[Discussions](https://www.nntp.perl.org/group/perl.perl5.porters/2024/11/msg269050.html), with the Perl Steering Council and core contributors. A [plan](https://www.nntp.perl.org/group/perl.perl5.porters/2024/11/msg269202.html) was created, with some preliminary work happening.

One notable contribution is the creation of the new module [Crypt::Bear](https://metacpan.org/dist/Crypt-Bear) by [LEONT](https://metacpan.org/author/LEONT) to wrap the TLS library BearSSL.

## Software Bill Of Materials (SBOM)
CPANSec attended many meetings in other security-related communities, and cross-connected with several other organization working on the topic.

One of the outcomes of this effort is available as in the form of an ongoing study on [Roles and metadata in open source supply-chains](https://security.metacpan.org/docs/supplychain-sbom.html), but it goes well beyond that.

## Adopting security related modules
CPANSec volunteers adopted security related modules:
- [Crypt::DSA](https://metacpan.org/dist/Crypt-DSA)
- [Crypt::DES_EDE3](https://metacpan.org/dist/Crypt-DES_EDE3)
- [Crypt::OpenPGP](https://metacpan.org/dist/Crypt-OpenPGP)
- [Crypt::OpenSSL::AES](https://metacpan.org/dist/Crypt-OpenSSL-AES)
- [Crypt::OpenSSL::Blowfish](https://metacpan.org/dist/Crypt-OpenSSL-Blowfish)
- [Crypt::OpenSSL::PKCS10](https://metacpan.org/dist/Crypt-OpenSSL-PKCS10)
- [Crypt::Primes](https://metacpan.org/dist/Crypt-Primes)
- [Crypt::Random](https://metacpan.org/dist/Crypt-Random)
- [Module::Signature](https://metacpan.org/dist/Module-Signature)
- [Net::OAuth](https://metacpan.org/pod/Net::OAuth)

Adopting modules is not always the only option, and CPANSec also reviewed modules for insecure algorithms in order to offer recommendations or propose deprecation.

## Reviewing CPAN for supply chain attacks
Through the year, CPANSec volunteers preformed an analysis of the CPAN ecosystem to know exactly how much vulnerable it would be to some common supply chain attacks:

- [Study CPAN Dependency Confusion](https://security.metacpan.org/docs/cpan-dependency-confusion.html)

More attacks vectors were also looked at, including _starjacking_ and the topic of _stealing namespaces_.

## Pentesting PAUSE
CPANSec volunteers reviewed and tested PAUSE with various attempts to break it with nasty modules, steal namespaces or execute remote code.

This was done on a local instance made possible thanks to the hard work of automation from "Table PAUSE" at [Perl Toolchain Summit 2024](https://perltoolchainsummit.org/pts2024/) that was later improved, tweaked (fast indexing, minor fixes...) and containerized by CPANSec. 

Outside of pentesting, these deliveries are useful for plenty of tests (on indexing, on PAUSE functionning itself) or as a local development environment of PAUSE.

## Outreach
If CPANSpec is taking care of security aspects of CPAN and Perl, it's also promoting Perl in general, actively recruiting for open source security.

This is in this scope that the group had a presence in several events. From [Perl Toolchain Summit 2024](https://perltoolchainsummit.org/pts2024/) to [London Perl and Raku Workshop 2024](https://act.yapc.eu/lpw2024/), but also [FOSDEM 2024](https://archive.fosdem.org/2024/) and the [OpenSSF summit](https://events.linuxfoundation.org/open-source-summit-europe/).

## Other
CPANSec also initiated a discussion (with a proposed change) to enable [Secure by default sessions in Mojolicious](https://github.com/mojolicious/mojo/pull/2200).

CPANSec had a recurring discussion on the topic of module signatures. Reviewing the limitations "by design" of the current options, and thinking about a correct way to implement that feature.
Similarly, discussions about CPAN installer enhancements ("Do not install module version with a CVE", "Patch module on the fly at install". etc...) were had, but only at an early stage.

At the very end of 2024, CPANSec reviewed the state of the art vulnerability of Perl bcrypt related modules ([Crypt::bcrypt](https://metacpan.org/dist/Crypt-Bcrypt), [Digest::Bcrypt](https://metacpan.org/pod/Digest::Bcrypt)) on misuse following the [Okta reported incident](https://medium.com/@rajat29gupta/bcrypt-and-the-okta-incident-what-developers-need-to-know-9d13a446738a).

## Who we are?
I attributed many of previous achievements to "CPANSec", but who was part of the "CPANSec group" in 2024? 

In last name alphabetical order:
```
Olaf Alders
José Joaquín Atria
H.Merijn Brand
Thibault Duponchelle
Alexander Hartmaier
Alexander Karelas
Peter Krawczyk
Timothy Legge
Tina Müller
Ingy döt Net
Salve J. Nilsen
Breno G. de Oliveira
Stig Palmquist
Nicolas Rochelemagne
Robert Rothenberg
Giuseppe Di Terlizzi
Leon Timmermans
```

## Final words
This was a big year; The group really took shape and get full speed with progress in many places.

The group met regularly ([18 meetings!](https://security.metacpan.org/meetings/)), had fun and got outstanding results.
This is the year when CPANSec got traction as a recognized supporting organization for securing the Perl/CPAN ecosystem.

With so many visible and impacting outcomes, 2024 confirmed well beyond expectations that CPANSec has a _raison d'être_.

It was also a very rewarding year for all people involved! Looking forward to a similarly successful 2025 :)
