---
layout: page
published: true
toc: true
title: "CPANSec CNA Disclosure Policy"
date: 2025-01-05 18:15:00 +0000
tags: authors guides cpan modules security cna
author: Timothy Legge
excerpt: "The CPANSec CNA Disclosure Policy discusses how you should interact with Perl, CPAN Modules and the CNA to report security vulnerabilities and the rules the CNA follows with respect to disclosing security vulnerabilities and settling disputes."
---
## Document status: Published

## Perl Security

> The Perl project takes security issues seriously.
>
> The responsibility for handling security reports in a timely and effective manner has been delegated to a security team composed of a subset of the Perl core developers.
>
> — the Perl Security team

Please report security bugs as specified below.

## CPAN Security

The CPAN Security group takes security on CPAN very seriously.
Issues in modules and distributions published on CPAN should be reported as specified below.
While the CPAN Security group does not directly fix issues in CPAN modules it will triage and attempt to coordinate communication as necessary.
The CPAN Security group has been tasked with running the CNA (CVE Numbering Authority) for Perl and CPAN modules.

## Reporting vulnerabilities

Instructions on how to report security issues with Perl or Perl modules hosted on CPAN, or related infrastructure can be found at [https://security.metacpan.org/docs/report.html](https://security.metacpan.org/docs/report.html).


### Perl Core (the interpreter)

The Perl Core team has a security team that can be contacted at [perl-security@perl.org](mailto:perl-security@perl.org).
This address is a closed membership mailing list monitored by the Perl security team who can properly evaluate and verify the bug report and develop and release a fix.
If you already have a proposed fix, please include it with your report, as that can speed up the process considerably.
It is possible that the security team will bring in extra help from area maintainers to understand and fix the security vulnerability.

The full Perl security policy can be found at [https://perldoc.perl.org/perlsecpolicy](https://perldoc.perl.org/perlsecpolicy).

### Dual-Life Modules
Security issues in Perl modules that are maintained in both the core Perl distribution and on CPAN should be reported to the maintainer of the module but, as per the [Perl Security Policy](https://perldoc.perl.org/perlsecpolicy), can be reported to the [perl-security@perl.org](mailto:perl-security@perl.org) list who can help to forward the report to the proper maintainer.

### CPAN Modules
Security issues in Perl Modules, maintained by independent developers and published on CPAN/MetaCPAN, should be reported to the maintainer of the module in question.
In the event that you are unable to contact the maintainer you may reach out to the CPAN Security Group at [cpan-security@security.metacpan.org](mailto:cpan-security@security.metacpan.org).
This address is a closed membership mailing list monitored by the CPAN Security Group who can assist in contacting the maintainer and triaging the issue.
In general the CPAN Security Group does not fix the issue but may be able to facilitate getting the issue resolved.

## Published advisories and mailing list
Security advisories are published to our [cve-announce](https://lists.security.metacpan.org/cve-announce) mailing list.

Subscribe to the mailing list if you'd like to be updated on newly published security advisories.
The mailing list has a public archive including all historical advisories sent to the list.

## Vulnerability credit and bounties
Please see the [Perl Security Policy](https://perldoc.perl.org/perlsecpolicy).
While our thanks and credit will be given, as non-profit community supported project, we are unable to provide any monetary rewards.

Independent CPAN Module developers may have their own policy but in general one should also expect that no monetary rewards will be available.

## Requesting a CVE
If you are unable to go through the Perl Security group for Perl Core or the module author/maintainer to report or obtain a CVE you can send an email directly to [cve-request@security.metacpan.org](mailto:cve-request@security.metacpan.org).

## CVE Numbering Authority (CNA) contact
If you need to contact the Perl and CPAN CNA directly, such as for updating or disputing a CVE record, you can send an email to [cna@security.metacpan.org](mailto:cna@security.metacpan.org).
Be sure that the CVE record in question was issued by the Perl and CPAN CNA and not a different CNA.

## CVE Dispute Mechanism
In the event that either the reporter or the developer (perl-core, or CPAN maintainer) disputes the details or validity of a CVE a dispute may be raised by contacting the CNA at [cna@security.metacpan.org](mailto:cna@security.metacpan.org).
The dispute process will follow the [CVE Record Dispute Policy](https://www.cve.org/Resources/General/Policies/CVE-Record-Dispute-Policy.pdf).
The CNA will acknowledge the receipt of a dispute within 5 business days.
The information provided will be validated, and if necessary discussed with the involved parties and a decision made and communicated.
