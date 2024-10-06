# Vulnerability Disclosure Policy

## Document status: ⚠️  DRAFT

What you see here is a **DRAFT** for the CNA Disclosure Policy.
Until published by a founding member, all of the points and ideas below are *suggested*, and open to revision, deletion or amending.

Discussion on IRC: [ircs://ssl.irc.perl.org:7062/#cpan-security](ircs://ssl.irc.perl.org:7062/#cpan-security)

## Perl Security

> The Perl project takes security issues seriously.
>
> The responsibility for handling security reports in a timely and effective manner has been delegated to a security team composed of a subset of the Perl core developers.
>
> — the Perl Security team

Please report security bugs as specified below.

## CPAN Security

The CPAN Security group takes security on CPAN very seriously.
Issues in modules and distributions published on CPAN should be repoorted as specified below.
While the CPAN Security group does not directly fix issues in CPAN modules it will triage and attempt to coordinate communitation as necessary.
The CPA Security group has been tasked with runing the CNA for Perl and CPAn modules.

## Reporting vulnerabilities

Instructions on how to report security issues with Perl or Perl modules hosted on CPAN, or related infrastrcuture can be found at https://security.metacpan.org/docs/report.html


### Perl Core (the interpreter)

The Perl Core team has a security team that can be contacted at [perl-security@perl.org](mailto:perl-security@perl.org).
This address is a closed membership mailing list monitored by the Perl security team who can properly evaluate and verify the bug report and develop and release a fix.
If you already have a proposed fix, please include it with your report, as that can speed up the process considerably.
It is possible that the security team will bring in extra help from area maintainers to understand and fix the security vulnerability.

The full Perl security policy can be found at https://perldoc.perl.org/perlsecpolicy

### Dual-Life Modules
Security issues in Perl modules that are maintained in both the core Perl distribution and on CPAN should be reported to the maintainer of the module but, as per the [Perl Security Policy](https://perldoc.perl.org/perlsecpolicy), can be reported to the perl-security@perl.org list who can help to forward the report to the proper maintainer.

### CPAN Modules
Security issues in Perl Modules, maintained by independant developers and published on CPAN/MetaCPAN, should be reported to the maintainer of the module in question.
In the event that you are unable to contact the maintainer you may reach out to the CPAN Security Group at [cpan-security@perl.org](mailto:cpan-security@perl.org).
This address is a closed membership mailing list monitored by the CPAN Security Group who can assist in contacting the maintainer and triaging the issue.
In general the CPAN Security Group does not fix the issue but may be able to facilitate getting the issue resolved.

## Published advisories and mailing list
Security advisories are published to multiple public locations. Advisories are sent via email to the [perl5-porters](https://lists.perl.org/list/perl5-porters.html) and [oss-security](https://oss-security.openwall.org/wiki/mailing-lists/oss-security) mailing lists.
Subscribe to the mailing list if you'd like to be updated on newly published security advisories.
The mailing list has a public archive including all historical advisories sent to the list.

There is also an advisory database published to GitHub FIXME using the Open Source Vulnerability (OSV) format which can be consumed using automated tooling.

## Vulnerability credit and bounties
Please see the [Perl Security Policy](https://perldoc.perl.org/perlsrecpolicy).
While our thanks and credit will be given, as non-profit community supported project, we are unable to provide any monetary rewards.

Independant CPAN Module developers may have their own policy but in general one should also expect that no monetary rewards will be available.

## CVE Numbering Authority (CNA) contact
If you need to contact the Perl and CPAN CNA directly, such as for updating or disputing a CVE record, you can send an email to cna@perl.org.
Be sure that the CVE record in question was issued by the Perl and CPAN CNA and not a different CNA.

## CVE Dispute Mechanism
In the event that either the reporter or the developer (perl-core, or cpan maintainer) disputes the details or validity of a CVE a dispute may be raised by contacting the CNA at cna@perl.org.
The dispute process will follow the [CVE Record Dispute Policy](https://www.cve.org/Resources/General/Policies/CVE-Record-Dispute-Policy.pdf).
The CNA will acknowledge the receipt of a dispute within 5 business days.
The information provided will be validated, and if necessary discussed with the involved parties and a decision made and communicated.
