---
layout: page
title: Guidelines for Adding a Security Policy to Perl Distributions
description: A guide for including a Security Policy in a CPAN distribution is to advise users how to report security issues, and how these issues will be handled.
toc: true
---

## Document Status: ⚠️  DRAFT

> [!CAUTION]
> What you see here is a DRAFT of the Guidelines for Adding a Security Policy to Perl Distributions, by the CPAN Security Group (CPANSec).
> As long as this document is in DRAFT, all of the points and ideas below are _suggestions_, and open to revision, deletion or amending – by you!
>
> - Contribute on Github: [https://github.com/CPAN-Security/security.metacpan.org/tree/guides/docs/guides/security-policy-for-authors.md](https://github.com/CPAN-Security/security.metacpan.org/tree/guides/docs/guides/security-policy-for-authors.md)
> - Discuss on IRC: [ircs://ssl.irc.perl.org:7063/#cpan-security](ircs://ssl.irc.perl.org:7063/#cpan-security)
> - Discuss on Matrix: [https://matrix.to/#/#cpansec:matrix.org](https://matrix.to/#/#cpansec:matrix.org)

## Purpose

The purpose of including a Security Policy in a CPAN distribution is to advise users how to report security issues, and how these issues will be handled.


## Why should authors add a security policy?

A security policy tells users how to report security issues to the
project maintainer(s), how the maintainer(s) will respond, and what
software will be supported by them.


## Why should authors work with CPANSec?

The CPAN Security Group (CPANSec) a forum for coordinating and
assisting in resolving security issues found on CPAN.  This includes:

- Assisting authors and third-party developers in dealing with
  vulnerabilities and general security advisories related to
  distributions indexed on Perl’s package ecosystem, CPAN;

- Acting as a trusted intermediator for reporting potential security
  vulnerabilities to distributions, including managing and responsible
  disclosure of embargoed security information for a reasonable amount
  of time pertaining non-core distributions on CPAN, and communication
  with package managers and distribution channels;

- Sharing and documenting best security practices to authors and
  users;

See the [CPANSec Charter](https://security.metacpan.org/docs/charter.html)
for more information.


## The format of the security policy

The security policy should be a text document with minimal formatting
that can be read without a specialised reader, with the name
`SECURITY-POLICY` and a suffix to indicate the markup (`.md` for
markdown, `.pod` for POD or optionally `.txt`).

More complex markup formats like HTML are not recommended.

The name `SECURITY-POLICY` is intended to differentiate this from
`security.txt` which has a specific machine-readable format and has
a different function [4].

The file should have the following sections.

1. Abstract
   - A short one or two sentences that explain what this document is.
2. How to report a security vulnerability
   - How to contact the project maintainers, and what to expect as a response.
3. What this policy applies to
   - Which versions of the software are supported
4. Installation and usage issues
5. Workflow.


## Abstract

This is a short one or two sentences that explain what this document
is, e.g.

> This is the Security Policy for the Perl Foo-Bar distribution.

If the project has a web site, with this security policy posted on the
website, then you should refer to that URL, e.g.:

> The latest version of this Security Policy can be found on the
> Foo-Bar website at https://foobar.example.com/security-policy

(It is reasonable to link to the project's distribution page on
MetaCPAN, e.g. https://metacpan.org/dist/Foo-Bar.)

If your security policy is based on the advice of this document, then
you should mention that, along with the version:

> This text is based on the CPAN Security Group's Guidelines for
> Adding a Security Policy https://security.metacpan.org/docs/
> (version 0.1.3).

### Links from other module documentation

If the module documentation or `README` has a section on reporting
bugs, then wording should be added that refers users to the security
policy, for example (in POD):

    =head2 Reporting Security Vulnerabilities

    Security issues should not be reported on the bugtracker website.
    Please see F<SECURITY-POLICY.md> for instructions how to report
    security vulnerabilities


## How to report a security vulnerability

At the bare minimum, your security policy should provide a current
package maintainer's email address (or ideally an alias that forwards
to multiple maintainers, or a bug reporting system that supports
special handling of security issues).

It is important to refer to the current project maintainers, and not
the package authors, who for older packages may be different.

For example,

> Security vulnerabilities can be reported by e-mail to the current
> project maintainer(s) at <foobar@example.com>.
>
> Please include as many details as possible, including code
> samples or text cases, so that we can reproduce the issue.

or [1]

> Security vulnerabilities can be reported via our GitHub repository
> at https://example.github.com/foobar.  On the "Advisories" page you
> can click on the "Report a vulnerability" button.

or

> Security vulnerabilities can be reported via our GitLab repository a
> https://gitlab.com/foobarkeepers/foobar/issues.  When reporting the
> issue, please check the tickbox on the form labelled "This issue is
> confidential and should only be visible to team members".

We recommend that there be a *single point of contact*.  Do not
provide a list of multiple email addresses or web pages and ask that
users contact some or all of these addresses.

Please ensure that the security contact information is consistent with
distribution metadata, e.g. in the `META.json` file [3].

Add note about also copying CPANSec on the notification if help is
required triaging the issue, or if the issue is being actively
exploited.  CPANSec provides support to reporters and maintainers in
assessing the appropriate response, and in case the maintainer(s) are
unreachable.  For example

> If you would like any help with triaging the issue, or if the issue
> is being actively exploited, please copy the report to the CPAN
> Security Group (CPANSec) at <cpan-security@security.metacpan.org>.

It is important to advise users not to report security
vulnerabilities in public, e.g.

> Please *do not* use the public issue reporting system on RT or
> GitHub issues for reporting security vulnerabilities.
>
> Please do not disclose the security vulnerability in public forums
> until past any proposed date for public disclosure, or it has been
> made public by the maintainers or CPANSec.  That includes patches or
> pull requests.

You can also link to the CPANSec page

> For more information, see Report a Security Issue
> https://security.metacpan.org/docs/report.html on the CPANSec
> website.

### What to expect for a response

Advise users what to expect in terms of a response.  If there is a
formal vulnerability workflow then refer to that section of the
document.

Include a recommendation to report the issue to CPANSec after a
certain amount of time without a response from the author(s).  For
example

> The maintainer(s) aim to acknowledge your security report within
> three days (72 hours).  However, this project is maintained by a
> small group of volunteers in their spare time.  If you have not
> heard back from the maintainers within 72 hours, then please forward
> the report to CPANSec at <cpan-security@security.metacpan.org>.

It is reasonable that small projects with a single part time
maintainer cannot promise a response time.  An alternative might be

> The maintainer(s) aim to acknowledge your security report as soon as
> possible.  However, this project is maintained by a single person in
> their spare time, and they cannot guarantee a rapid response.  If you
> have not received a response from the them within a week, then
> please send a reminder to them and copy the report to CPANSec at
> <cpan-security@security.metacpan.org>.

Also add a note about the initial response:

> Note that the initial response to your report will be an
> acknowledgement, with a possible query for more information.  It
> will not necessarily include any fixes for the issue.

Also note on which conditions you may forward the security issue to
other people.  For example,

> The project maintainer(s) may forward this issue to the security
> contacts for other projects where we believe it is relevant.  This
> may include embedded libraries, system libraries, prerequisite
> modules or downstream software that uses this software.
>
> They may also forward this issue to CPANSec.

## What Software this Policy Applies to

This section discusses what software this applies to, and what are
considered security issues in the software, and what are not
considered security issues.  For example,

> Any security vulnerabilities in Foo-Bar are covered by this policy.
>
> Security vulnerabilities are considered anything that allows users
> to execute unauthorised code, access unauthorised resources, or to
> have an adverse impact on accessibility or performance of a system.
>
> Security vulnerabilities in upstream software (embedded libraries,
> prerequisite modules or system libraries, or in Perl), are not
> covered by this policy unless they affect Foo-Bar, or Foo-Bar can
> be used to exploit vulnerabilities in them.
>
> Security vulnerabilities in downstream software (any software that
> uses Foo-Bar, or plugins to it that are not included with the
> Foo-Bar distribution) are not covered by this policy.

### Which versions of this software are supported?

There should be a section or subsection that identifies which versions
of the software will be supported for security fixes.  For example,

> The maintainer(s) will only commit to releasing security fixes for
> the latest version of Foo-Bar.
>
> Note that the Foo-Bar project only supports major versions of Perl
> released in the past ten (10) years, even though Foo-Bar will run on
> older versions of Perl.  If a security fix requires us to increase
> the minimum version of Perl that is supported, then we may do so.

or,

> For security vulnerabilities, the maintainer(s) will only commit to
> supporting the last two major versions of Foo-Bar.  As of this
> release, that is v1.4.x and v1.6x.

## Installation and usage issues

This is an optional section.

It is also worth noting how it works with prerequisites, for example,

> This software uses the zlib library for accessing gzip-encoded
> streams and files.  The minimum requirement is zlib v1.2.  However,
> there may be security vulnerabilities and you should use v1.2.13 or
> newer.

or

> The distribution metadata specifies minimum versions of
> prerequisites that are required for Foo-Bar to work.  However, some
> of these prerequisites may have security vulnerabilities, and you
> should ensure that you are using up-to-date versions of these
> prerequisites.
>
> Where security vulnerabilities are known, the metadata may indicate
> newer versions as recommended.

Note that while security issues can occur due to unsafe defaults or
the misuse of software libraries, it is still worth adding a section
that highlights usage issues.  For example,

> The "foo" method only validates that filenames passed to it exist.
> It cannot determine whether it should process those files.  You
> should ensure that arbitrary filenames are not passed to it, and
> should validate any external data that is used for generating the
> filename.

It is acceptable to refer readers to specific sections of the module
documentation rather than duplicate content.

## Workflow

This is an optional section.

Larger projects, or projects maintained by organisations with their
own general security policies, may have a vulnerability workflow.
Where applicable, the workflow should be discussed, or a link provided
to that document.

For example, see [2].

## Examples

### Single Maintainer

An example security policy for a CPAN distribution with a single
maintainer that should cover most cases.

> This is the Security Policy for the Perl Foo-Bar distribution.
>
> The latest version of this Security Policy can be found on the
> Foo-Bar website at https://example.metacpan.org/dist/Foo-Bar
>
> # How to Report a Security Vulnerability
>
> Security vulnerabilities can be reported by e-mail to the current
> project maintainers at <foobar@example.com>.
>
> Please include as many details as possible, including code samples
> or test cases, so that we can reproduce the issue.
>
> If you would like any help with triaging the issue, or if the issue
> is being actively exploited, please copy the report to the CPAN
> Security Group (CPANSec) at <cpan-security@security.metacpan.org>.
>
> Please *do not* use the public issue reporting system on RT or
> GitHub issues for reporting security vulnerabilities.
>
> Please do not disclose the security vulnerability in public forums
> until past any proposed date for public disclosure, or it has been
> made public by the maintainers or CPANSec.  That includes patches or
> pull requests.
>
> For more information, see
> [Report a Security Issue](https://security.metacpan.org/docs/report.html)
> on the CPANSec website.
>
> ## Response to Reports
>
> We aim to acknowledge your security report as soon as possible.
> However, this project is maintained by a single person in their
> spare time, and we cannot guarantee a rapid response.  If you have
> not heard back from the maintainers within a week, then please send
> a reminder to the maintainer and copy the report to CPANSec at
> <cpan-security@security.metacpan.org>.
>
> Please note that the initial response to your report will be an
> acknowledgement, with a possible query for more information.  It
> will not necessarily include any fixes for the issue.
>
> The project maintainers may forward this issue to the security
> contacts for other projects where we believe it is relevant.  This
> may include embedded libraries or prerequisite modules or system
> libraries, or downstream software that uses this software.
>
> We may also forward this issue to the CPANSec if they have not
> already been copied on this.
>
> # Which Software this Policy Applies to
>
> Any security vulnerabilities in Foo-Bar are covered by this policy.
>
> Security vulnerabilities are considered anything that allows users
> to execute unauthorised code, access unauthorised resources, or to
> have an adverse impact on accessibility or performance of a system.
>
> Security vulnerabilities in upstream software (embedded libraries,
> prerequisite modules or system libraries, or in Perl), are not
> covered by this policy unless they affect Foo-Bar, or Foo-Bar can
> be used to exploit vulnerabilities in them.
>
> Security vulnerabilities in downstream software (any software that
> uses Foo-Bar, or plugins to it that are not included with the
> Foo-Bar distribution) are not covered by this policy.
>
> ## Supported Versions of Foo-Bar
>
> Security fixes will only be applied to the latest version of
> Foo-Bar.
>
> Note that the Foo-Bar project only supports major versions of Perl
> released in the past ten (10) years, even though Foo-Bar will run on
> older versions of Perl.  If a security fix requires us to increase
> the minimum version of Perl that is supported, then we may do so.
>
> # Installation and Usage Issues
>
> The distribution metadata specifies minimum versions of
> prerequisites that are required for Foo-Bar to work.  However, some
> of these prerequisites may have security vulnerabilities, and you
> should ensure that you are using versions of these prerequisites
> with no known relevant vulnerabilities (if not up-to-date versions).
>
> Where security vulnerabilities are known, the metadata may indicate
> newer versions as recommended.
>
> ## Usage
>
> Please see the software documentation for further information.

## References and Notes

1. (CodeSecAdvisory) https://docs.github.com/en/code-security/security-advisories/working-with-repository-security-advisories/configuring-private-vulnerability-reporting-for-a-repository
1. (PerlSecPolicy) [Perl security report handling policy](perlsecpolicy)
1. (CPANMetaSpec) [CPAN::Meta::Spec](https://metacpan.org/pod/CPAN::Meta::Spec)
1. (Securitytxt) https://securitytxt.org/


## License and use of this document

* Version: 0.1.7
* License: [CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/deed)
* Copyright: © Robert Rothenberg <rrwo@cpan.org>, Some rights reserved.

You may use, modify and share this file under the terms of the [CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/deed) license.


### Acknowledgements

Several people have been involved in the development of this document

* Robert Rothenberg (main author)
* Alexander Hartmaier
* Thibault Duponchelle
* Timothy Legge
* Stig Palmquist
* Salve J. Nilsen
