# Guidelines for Adding a Security Policy to Perl Distributions

The purpose of including a Security Policy in a CPAN distribution is
to advise users how to report security issues, and how these issues
will be handled.

Version: 0.1.4

Status: ⚠️ DRAFT

## The format of the security policy

The security policy should be a text document with minimal formatting,
either as a plain text `SECURITY-POLICY` file, a markdown
`SECURITY-POLICY.md` file, or a POD format `SECURITY-POLICY.pod` file.

(Using `SECURITY.txt` or `security.txt` is discouraged, as that is
often associated with https://securitytxt.org/ which has a different
purpose.)

The project's `README` file and module documentation should have
sections that refers users to the security policy document, especially
in the bug reporting sections.

The file should have the following sections.

1. Abstract

   A short one or two sentences that explain what this document is.

2. How to report a security vulnerability

   How to contact the project maintainers, and what to expect as a reponse.

3. What this policy applies to

   Which versions of the software are supported

4. Installation and usage issues

5. Workflow.

## Abstract

This is a short one or two sentences that explain what this document
is, e.g.

> This is the Security Policy for the Perl 5 Foo-Bar distribution.

If the project has a web site, with this security policy posted on the
website, then you should refer to that URL, e.g.:

> The latest version of this Security Policy can be found on the
> Foo-Bar website at https://foobar.example.com/security-policy

(It is reasonable to link to the project's distribution page on
MetaCPAN, e.g. https://metacpan.org/dist/Foo-Bar.)

If your security policy is based on the advise of this document, then
you should mention that, along with the version:

> This text is based on the CPAN Security Group's Guidelines for
> Adding a Security Policy https://security.metacpan.org/docs/
> (version 0.1.3).

## How to report a security vulnerability

At the bare minimum, it should provide a current package maintainer's
email address (or ideally an alias that forwards to multiple
maintainers, or a bug reporting system that supports special handling
of security issues).

It is important to refer to the current project maintainers, and not
the package authors, who for older packages may be different.

For example,

> Security vulnerabilties can be reported by e-mail to the current
> project maintainer(s) at <fobar@example.com>.
>
> Please include as many details as possible, including code
> samples, so that we can reproduce the issue.

or [1]

> Security vulnerabilities can be reported via our GitHub repository
> at https://example.github.com/foobar.  On the "Advisories" page you
> can click on the "Report a vulnerability" button.

We recommend that there be a *single point of contact*.  Do not
provide a list of multiple email addresses or web pages and ask that
users contact some or all of these addresses.

Please ensure that the security contact information is consistent with
distribution metadata, e.g. in the `META.json` file [3].

Add note about also copying cpan-security on the notification if
the security issue is a 0-day vulnerability or is otherwise urgent.
For example

> If this is a 0-day vulnerability that is actively being exploited,
> please copy the report to the CPAN Security Group (CPANSec) at
> <cpan-security@security.metacpan.org>.

It is important to advise users not to report security
vulnerabilities in public, e.g.

> Please *do not* use the public issue reporting system on RT or
> GitHub issues for reporting security vulnerabilities.
>
> Please do not disclose the security vulnerability until it has been
> made public by the maintainers or CPANSec.  That includes blogs,
> social media, forums, or conferences.

### What to expect for a response

Advise users what to expect in terms of a response.  If there is a
formal vulnerability workflow then refer to that section of the
document.

Include a recommendation to report the issue to CPANSec after a
certain amount of time without a response from the author(s).  For
example

> The maintainer(s) aim to acknowledge to your security report within
> 72 hours (three days).  However, this project is maintained by a
> small group of volunteers in their spare time.  If you have not
> heard back from the maintainers within 72 hours, then please forward
> the report to CPANSec at <cpan-security@security.metacpan.org>.

It is reasonable that small projects with a single part time
maintainer cannot promise a response time.  An alternative might be

> The maintainer(s) aim to acknowledge your security report as soon as
> possible.  However, this project is maintained by a single person in
> their spare time, and they cannot guarantee a rapid reponse.  If you
> have not received a response from the them within a week, then
> please send a reminder to them and copy the report to CPANSec at
> <cpan-security@security.metacpan.org>.

Also add a note about what the initial response:

> Note that the initial response to your report will be an
> acknowledgement, with a possible query for more information.  It
> will not necessarily include any fixes for the issue.

Also note on which conditions you may forward the security issue to
other people.  For example,

> The project maintainer(s) may forward this issue to the security
> contacts for other projects where we believe it is relevant.  This
> may include embedded libraries or prerequisite modules or system
> libraries, or downstream software that uses this software.
>
> They may also forward this issue to CPANSec if they have not
> already been copied on this.

## What Software this Policy Applies to

This section discusses what software this applies to, and what are
considered security issues in the software, and what are not
considered security issues.  For example,

> Any security vulnerabilities in Foo-Bar are covered by this policy.
>
> Security vulnerabilities are considered anything that allows users
> to execute unauthorised code, access unahtorised resources, or to
> have an adverse impact on accessibility or performance of a system.
>
> Security vulnerabilities in upstream software (embedded libraries,
> prerequisite modules or system libraries, or in Perl), are not
> convered by this policy.
>
> Security vulnerabilities in downstream software (any software that
> uses Foo-Bar, or plugins to it that are not included with the
> Foo-Bar distribution) are not covered by this policy.
>
> However, vulnerabilities in upstream software that can affect
> Foo-Bar, or where Foo-Bar can be used to exploit vulnerabilities in
> other software (upstream or downstream), are considered
> vulnerabilities of Foo-Bar, and are covered by this policy.

### Which versions of this software are supported?

There should be a section or subsection that identifies which versions
of the software will be supported for security fixes.  For example,

> The maintainer(s) will only commit to releasing security fixes for
> the latest version of Foo-Bar.
>
> Note that the Foo-Bar project only supports major versions of Perl
> released in the past ten (10) years, even though Foo-Bar will run on
> older versions of Perl.  If a security fix requires us to increase
> the minimum version of Perl that is supported, then we may do that.

or,

> For security vulnerabilities, the maintainer(s) will only commit to
> supporting for the last two major versions of Foo-Bar.  As of this
> release, that is v1.4.x and v1.6x.

## Installation and usage issues

It is also worth noting how it works with prerequisites, for example,

> This software uses the zlib library for accessing gzip-encoded
> streams and files.  The minimum requirement is zlib v1.2.  However,
> there may be security vulnerabilties and you should use v1.2.13 or
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

Larger projects, or projects maintained by organisations with their
own general security policies, may have a vulnerability workflow.
Where applicable, the workflow should be discussed, or a link provided
to that document.

For example, see [2].

## Examples

### Single Maintainer

An example security policy for a CPAN distribution with a single
maintainer that should cover most cases.

> This is the Security Policy for the Perl 5 Foo-Bar distribution.
>
> The latest version of this Security Policy can be found on the
> Foo-Bar website at https://example.metacpan.org/dist/Foo-Bar
>
> # How to Report a Security Vulnerability
>
> Security vulnerabilties can be reported by e-mail to the current
> project maintainers at <fobar@example.com>.
>
> Please include as many details as possible, including code samples,
> so that we can reproduce the issue.
>
> If this is a 0-day vulnerability that is actively being exploited,
> then please copy the report to the CPAN Security Group (CPANSec) at
> <cpan-security@security.metacpan.org>.
>
> Please *do not* use the public issue reporting system on RT or
> GitHub issues for reporting security vulnerabilities.
>
> Please do not disclose the security vulnerability before it has been
> made public by the maintainers or CPANSec.  That includes blogs,
> social media, forums, or conferences.
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
> convered by this policy.
>
> Security vulnerabilities in downstream software (any software that
> uses Foo-Bar, or plugins to it that are not included with the
> Foo-Bar distribution) are not covered by this policy.
>
> However, vulnerabilities in upstream software that can affect
> Foo-Bar, or where Foo-Bar can be used to exploit vulnerabilities in
> other software (upstream or downstream), are considered
> vulnerabilities of Foo-Bar, and are covered by this policy.
>
> ## Supported Versions of Foo-Bar
>
> Security fixes will only be applied to the latest version of
> Foo-Bar.
>
> Note that the Foo-Bar project only supports major versions of Perl
> released in the past ten (10) years, even though Foo-Bar will run on
> older versions of Perl.  If a security fix requires us to increase
> the minimum version of Perl that is supported, then we may do that.
>
> # Installation and Usage Issues
>
> The distribution metadata specifies minimum versions of
> prerequisites that are required for Foo-Bar to work.  However, some
> of these prerequisites may have security vulnerabilities, and you
> should ensure that you are using up-to-date versions of these
> prerequisites.
>
> Where security vulnerabilities are known, the metadata may indicate
> newer versions as recommended.
>
> ## Usage
>
> Please see the software documentation for further information.

## Notes

[1] https://docs.github.com/en/code-security/security-advisories/working-with-repository-security-advisories/configuring-private-vulnerability-reporting-for-a-repository

[2] [Perl security report handling policy](perlsecpolicy)

[3] [CPAN::Meta::Spec](https://metacpan.org/pod/CPAN::Meta::Spec)
