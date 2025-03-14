---
layout: post
title:  "CPANSec retrospective 2024"
date:   2025-03-13 00:23:17 +0200
categories: cpansec update
author: Thibault Duponchelle
excerpt: Here is the CPANSec 2024 Retrospective
---

That was a big year for CPANSec.

If it gets a bit under the radar to you, please find some of the achievements listed in this retrospective!

## Common Vulnerabilities and Exposures (CVEs)
2024 was the year where, with the contribution of CPANSec, Perl communities evolved in their mindset
and their attitudes towards Common Vulnerabilities and Exposures (CVEs).

Until then, our experience is that very few CVEs were emitted for Perl modules and tooling.  
Beyond that, people and authors were a bit reluctant to deal with those CVEs.

CVE are not a sign of bad quality or maintenance of a code,
but a professional way of tagging and tracking a vulnerability,
also signifying the importance of the concerned code.

### Vulnerable Spreadsheet Parsing modules
The start of the year was marked by vulnerabilities reported for [Spreadsheet::ParseExcel](https://metacpan.org/pod/Spreadsheet::ParseExcel)

- [CVE-2023-7101: Spreadsheet::ParseExcel arbitrary code execution vulnerability](https://security.metacpan.org/2024/02/10/vulnerable-spreadsheet-parsing-modules.html#cve-2023-7101-spreadsheetparseexcel-arbitrary-code-execution-vulnerability)
- [CVE-2024-22368: Spreadsheet::ParseXLSX denial of service vulnerability](https://security.metacpan.org/2024/02/10/vulnerable-spreadsheet-parsing-modules.html#cve-2024-22368-spreadsheetparsexlsx-denial-of-service-vulnerability)
- [CVE-2024-23525: Spreadsheet::ParseXLSX XML external entity attack vulnerability](https://security.metacpan.org/2024/02/10/vulnerable-spreadsheet-parsing-modules.html#cve-2024-23525-spreadsheetparsexlsx-xml-external-entity-attack-vulnerability)

### Insecure modes of CPAN installers
CPANSec continued with CPAN installer [cpanminus](https://github.com/miyagawa/cpanminus) (a major installer of the Perl ecosystem)
- [CVE-2024-45321: App::cpanminus through 1.7047 downloads code using insecure HTTP](https://security.metacpan.org/2024/08/26/cpanminus-downloads-code-using-insecure-http.html#cve-2024-45321)

This latest is a bit related to a fix from a CPANSec member earlier in 2023 to the CPAN installer [cpan]() (part of Perl core distribution)
- [CVE-2023-31484: CPAN.pm before 2.35 does not verify TLS certificates when downloading distributions over HTTPS](https://nvd.nist.gov/vuln/detail/CVE-2023-31484)

### Other
Similarly, a CVE was emitted for the [POSIX::2008](https://metacpan.org/dist/POSIX-2008) module:
- [CVE-2024-55564: POSIX::2008 package before 0.24 for Perl has a potential execve50c env buffer overflow](https://nvd.nist.gov/vuln/detail/CVE-2024-55564)

## Improving CVE tooling
Along with CVEs, tooling to monitor, fetch or test for them is very useful.
They can be installed in workflows or tooling as a gate keeper
for companies to do not ship vulnerable piece of code.

CPANSec produced and improved a few tools to fetch or test for CVEs:
- [CPANSEC::Admin::Command::CVEScan](https://metacpan.org/pod/CPANSEC::Admin::Command::CVEScan)
- [Net::NVD](https://metacpan.org/pod/Net::NVD)
- [Net::CVE](https://metacpan.org/pod/Net::CVE)
- [Test::CVE](https://metacpan.org/pod/Test::CVE)

Note: Not all CVE tooling are managed by CPANSec, I'm thinking in particular [CPAN::Audit](https://metacpan.org/pod/CPAN::Audit) and its sidecar [CPAN::Audit::DB](https://metacpan.org/pod/CPAN::Audit::DB) or [NIST::NVD](https://metacpan.org/pod/NIST::NVD).
But CPANSec follow closely and contribute to them when possible.

## CPANSec as a CVE Numbering Authority (CNA)
In 2023 and 2024, CPANSec helped with or contributed to CVEs for CPAN,
while assigning CVEs remained under control of another CVE Numbering Authority (CNA).

CPANSec members [TIMLEGGE](https://metacpan.org/author/TIMLEGGE) and [STIGTSP](https://metacpan.org/author/STIGTSP) worked throughout the year to give the group the ability to assign CVEs.
After all, who knows better than CPANSec the impact of CVEs on Perl modules? :)

By end of the year, the groundwork to become a CNA was completed.

This designation was officially granted in February 2025: [CPANSec is now a CVE Numbering Authority (CNA)!](https://security.metacpan.org/2025/02/25/cpansec-is-cna-for-perl-and-cpan.html)

The news of CPANSec becoming CVE Numbering Authority (CNA) was saluted by big names like Greg Kroah-Hartman (GNU/Linux) and Daniel Stenberg (curl).

## Introduced a SECURITY Policy
In parallel, CPANSec collectively pushed for authors to publish a Security Policy.

Doing so is considered Open Source Good Practice, especially as security is becoming more and more critical.

This effort resulted in creating a [template](https://security.metacpan.org/docs/guides/security-policy-for-authors.html#examples), providing [guidelines](https://security.metacpan.org/docs/guides/security-policy-for-authors.html) and, last but not least, communicating about the initiative in various channels.

## Study on Random Number generation for Security
Generating random numbers can help in a wide variety of tasks.
All of them don't have the same level of criticality.
In particular, random generated data used in a security context requires extra care.

CPANSec contributor [RRWO](https://metacpan.org/author/RRWO) studied and reviewed CPAN modules for this use, and shared this in [Random Data For Security Use](https://security.metacpan.org/docs/guides/random-data-for-security.html).

## Working on "TLS in core"
A vanilla install of Perl (distribution) does not provide HTTPS capabilities, and this is annoying.
That's an important (and difficult) topic that is addressed, across core developers and CPANSec.

Things started to go into motion in 2024 to make it happen.

[Discussions](https://www.nntp.perl.org/group/perl.perl5.porters/2024/11/msg269050.html), with the Perl Steering Council or core contributor. A [plan](https://www.nntp.perl.org/group/perl.perl5.porters/2024/11/msg269202.html) was built, with some preliminary work happening.

The creation of the new module [Crypt::Bear](https://metacpan.org/dist/Crypt-Bear) to wrap the TLS library BearSSL.

## SBOM
CPANSec attended a billion of meetings, cross connected with several other organization working on the topic.

One of the outcome of this huge effort is available as a document [Roles and metadata in open source supply-chains](https://security.metacpan.org/docs/supplychain-sbom.html) but it goes well beyond that.

## Adopting security related modules
CPANSec adopted security related modules:
- [Crypt::DSA](https://metacpan.org/dist/Crypt-DSA)
- [Crypt::DES_EDE3](https://metacpan.org/dist/Crypt-DES_EDE3)
- [Crypt::OpenPGP](https://metacpan.org/dist/Crypt-OpenPGP)
- [Crypt::OpenSSL::AES](https://metacpan.org/dist/Crypt-OpenSSL-AES)
- [Crypt::OpenSSL::Blowfish](https://metacpan.org/dist/Crypt-OpenSSL-Blowfish)
- [Crypt::OpenSSL::ConfiguredAPI](https://metacpan.org/dist/Crypt-OpenSSL-ConfiguredAPI)
- [Crypt::OpenSSL::PKCS10](https://metacpan.org/dist/Crypt-OpenSSL-PKCS10)
- [Crypt::OpenSSL::SignCSR](https://metacpan.org/dist/Crypt-OpenSSL-SignCSR)
- [Crypt::OpenSSL::Verify](https://metacpan.org/dist/Crypt-OpenSSL-Verify)
- [Crypt::OpenSSL::VerifyX509](https://metacpan.org/dist/Crypt-OpenSSL-VerifyX509)
- [Crypt::Primes](https://metacpan.org/dist/Crypt-Primes)
- [Crypt::Random](https://metacpan.org/dist/Crypt-Random)
- [Module::Signature](https://metacpan.org/dist/Module-Signature)

Adopting modules is not always the only option and CPANSec also reviewed modules for insecure algorithms
in order to make recommendations or push some modules to deprecation.

## Reviewing CPAN for supply chain attacks
Through the year, CPANSec tried to come with analysis of the CPAN ecosystem
to know exactly how much vulnerable it would be to some common supply chain attacks:

- [Study CPAN Dependency Confusion](https://security.metacpan.org/docs/cpan-dependency-confusion.html)
- [Study CPAN StarJacking](https://security.metacpan.org/docs/cpan-starjacking.html)

## Pentesting PAUSE
CPANSec reviewed and tested PAUSE with various attempts to break it with nasty modules, steal namespaces or execute remote code.

This was done on a local instance that was a good opportunity to work on automating more the reproducibility and ease of setup.

## Other
CPANSec also opened discussion (with a proposed change) to [Secure by default sessions in Mojolicious](https://github.com/mojolicious/mojo/pull/2200)

Through the year, CPANSec discussed the topic of module signatures. Reviewing the limitations "by design" of the current options and thinking about a correct way to implement that feature.
Similarly, discussions about CPAN installer enhancements ("Do not install module version with a CVE", "Patch module on the fly at install". etc...) were discussed, but still early stage.

Very end of 2024, CPANSec folks reviewed the state of the art vulnerability of Perl bcrypt related modules ([Crypt::bcrypt](https://metacpan.org/dist/Crypt-Bcrypt), [Digest::Bcrypt](https://metacpan.org/pod/Digest::Bcrypt)) on misuse following the [Okta reported incident](https://medium.com/@rajat29gupta/bcrypt-and-the-okta-incident-what-developers-need-to-know-9d13a446738a).

## Final words
This was a big year, the group really took shape and get full speed with progress in many places.

The CPANSec group met regularly ([18 meetings!](https://security.metacpan.org/meetings/)), had fun and got outstanding results.
This is the year where CPANSec has positioned as a recognized servant organization for securing the Perl ecosystem.

With such a lot of visible and impacting results, the year 2024 confirmed the reason of living of the group well beyond expectations.

It was also a very rewarding year for all people involved! Looking forward to a similarly successful 2025 :)
