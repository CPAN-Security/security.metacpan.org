# Security Policy

Ideally, there would be a separate `SECURITY` `SECURITY.md` or `SECURITY.pod` file in
the distribution that outlines the security policy in more detail.

Note that `SECURITY.txt` or `security.txt` is discouraged, as that is
often associated with https://securitytxt.org/ which has a different purpose.

A minimal security policy should discuss

1. How to report a security vulnerability

   At the bare minimum, it should provide a current package
   maintainer's email address (or ideally an alias that forwards to
   multiple authors), or a bug reporting system that supports special
   handling of security issues.

   Some examples,

   > Security vulnerabilties can be reported by e-mail to the current
   > project maintainers at <fobar@example.com>.
   >
   > Please include as may details, including code samples, so that we
   > can reproduce the issue.

   or [1]

   > Security vulnerabilities can be reported via our GitHub
   > repository at https://example.github.com/foobar. On the
   > "Advisories" page you can click on the "Report a vulnerability"
   > button.

   Add note about also copying cpan-security on the notification if
   the security issue is a 0-day vulnerability or is otherwise urgent.

   For example

   > If this is a 0-day vulnerability that is actively being
   > exploited, then please copy the report to the CPAN Security Group
   > at <cpan-security@perl.org>.

   Advise users on what to expect in terms of a response.  If there is
   a formal vulnerability workflow than refer to that section of the
   document.

   A recommendation that after a certain amount of time not hearing
   from the author(s), to report to cpan-security@perl.org.

   For example

   > We will aim to acknowledge to your security report within 72 hours.
   > However, this project is maintained by a small group of
   > volunteers.  If you have not heard back from the maintainers
   > within 72 hours (three days), then please forward the report to
   > the CPAN Security Group at <cpan-security@perl.org>.
   >
   > Please note that the initial response to your report will be an
   > acknowledgement, with a possible query for more information. It
   > will not necessarily include any fixes for the issue.

   Also note on what conditions you may forward the security issue to
   other people. For example,

   > The project maintainers may forward this issue to the security
   > contacts for other projects where we believe it is relevant to
   > them. This may include embedded libraries or prerequisite modules
   > or system libraries, or downstream software that uses this
   > software.
   >
   > We may also forward this issue to the CPAN Security Group.

   It is important to advise users not to report security
   vulnerabilities in public, e.g.

   > Please *do not* use the public issue reporting system on RT for
   > reporting security vulnerabilities.
   >
   > Please do not disclose the security vulnerability in public. That
   > includes blogs, social media, forums, or conferences.

   Note: many modules include a "BUGS" section in their POD that
   describes how to report a bug.  These sections should include a
   subsection that advises how to safely report security issues, and
   should refer readers to the `SECURITY` document.

2. What software this policy applies to.

   What software, and what are considered security issues in the
   software, and what are not considered security issues, refer to
   Usage section below.

   For example,

   > This security policy applies to the Foo-Bar perl5 distribution.
   >

   > Any security vulnerabilities in Foo-Bar are covered by this
   > policy.
   >
   > Security vulnerabilities are considered anything that allows
   > users to execute unauthorised code, access unahtorised resources,
   > or to have an adverse impact on accessibility or performance of a
   > system.
   >
   > Security vulnerabilities in upstream software (embedded
   > libraries, prerequisite modules or system libraries, or in Perl),
   > are not convered by this policy.
   >
   > Security vulnerabilities in downstream software (any software
   > that uses Foo-Bar, or plugins to Foo-Bar thar are not included
   > with the Foo-Bar distribution) is not covered by this policy.
   >
   > However, vulnerabilities in upstream software that can affect
   > Foo-Bar, or where Foo-Bar can be used to exploit vulnerabilities
   > in other software (upstream or downstream), are considered
   > vulnerabilities of Foo-Bar, and are covered by this policy.

3. What versions of the software of the software will be supported for
   security fixes.

   For example,

   > Security fixes will only be applied to the latest version of
   > Foo-Bar.
   >
   > Note that the Foo-Bar project only supports major versions of Perl
   > released in the past ten (10) years, even though Foo-Bar will run
   > on older versions of Perl. If a security fix requires us to
   > increase the minimum version of Perl that is supported, then we
   > may do that.

   or,

   > For security vulnerabilities, we will only guarantee support the
   > last two major versions of Foo-Bar. As of this release, that is
   > v1.4.x and v1.6x.

   Note: modules with a section on supported software versions should
   refer readers to the `SECURITY` document if the supported versions
   for security fixes are different.

4. Usage

   A discussion of issues specific to the software that may be unsafe
   if used carelessly, e.g.

   > The "foo" method only validates that filenames passed to it
   > exist.  It cannot determine whether it should process those
   > files.  You should ensure that arbitrary filenames are not passed
   > to it, and should validate any external data that is used for
   > generating the filename.

   It is acceptable to refer readers to specific sections of the
   module POD rather than duplicate content.

   It is also worth noting how it works with prerequisites, for example,

   > This software uses the zlib library for accessing gzip-encoded
   > streams and files. The minimum requirement is zlib v1.2. However,
   > there may be security vulnerabilties and you should use v1.2.13
   > or newer.

   or

   > The distribution metadata specifies minimum versions of
   > prerequisites that are required for Foo-Bar to work. However,
   > some of these prerequisites may have security vulnerabilities,
   > and you should ensure that you are using up-to-date versions of
   > these prerequisites.
   >
   > Where security vulnerabilities are known, the metadata may
   > indicate newer versions as recommended.

5. Workflow

   Larger projects may have a vulnerability workflow, e.g. see
   [Perl security report handling policy](perlsecpolicy)

6. Notes

[1] https://docs.github.com/en/code-security/security-advisories/working-with-repository-security-advisories/configuring-private-vulnerability-reporting-for-a-repository
