---
layout: page
title: CPAN Author's Secure Coding Guide
description: A security guide for CPAN Distribution Authors
toc: true
---

## Document status: ⚠️  DRAFT

> [!CAUTION]
> What you see here is a DRAFT of the `CPAN Author's Security Guide` by the CPAN Security Group (CPANSec).
> As long as this document is in DRAFT, all of the points and ideas below are open to revision, deletion or amending – by you!
>
> - Contribute on Github: [https://github.com/CPAN-Security/security.metacpan.org/blob/guides/docs/guides/cpan-author-guide.md](https://github.com/CPAN-Security/security.metacpan.org/blob/guides/docs/guides/cpan-author-guide.md)
> - Discuss on IRC: [ircs://ssl.irc.perl.org:7062/#cpan-security](ircs://ssl.irc.perl.org:7062/#cpan-security)
> - Discuss on Matrix: [https://matrix.to/#/#cpansec:matrix.org](https://matrix.to/#/#cpansec:matrix.org)

## Learn the basics

1. Read the [perlsec](https://perldoc.perl.org/perlsec) page to familiarize yourself with Perl's security features
1. Read the OpenSSF [Open Source Best Practices Badge](https://www.bestpractices.dev/en) program, and
    * Try to at least achieve a [passing badge](https://www.bestpractices.dev/en/criteria/0).
    * (You can also see how well [other Perl projects](https://www.bestpractices.dev/en/projects?q=perl) do in this regard!)

# Write code that is _Secure by Design_

* [CISA's Secure by Design Pledge](https://www.cisa.gov/securebydesign/pledge)


## Keep your security metadata up-to-date

1. Read the [CPAN::META::Spec](https://metacpan.org/pod/CPAN::Meta::Spec) and make sure all relevant fields are correct and up-to-date
1. Ensure also that your list of dependencies is complete and correct

## Share your security metadata

1. Add a [security.txt](https://securitytxt.org/) file to your project website
1. Add a [distribution security policy](https://github.com/CPAN-Security/security.metacpan.org/blob/cpan-author-guide/docs/guides/security-policy-for-authors.md) to your distribution.
   1. Add the same to your project repository ([Github instructions](https://docs.github.com/en/code-security/getting-started/adding-a-security-policy-to-your-repository)).

## Add security tests to your code

1. Learn how to use [perltaint](https://perldoc.perl.org/perlsec#Laundering-and-Detecting-Tainted-Data) to detect and defang input from untrusted sources
1. Add [tests for taintedness](https://metacpan.org/pod/Test::Taint) to your codebase, to verify that your code actually handles untrusted input as expected

## Practice symbol import discipline

1. Use [App::perlimports](https://www.olafalders.com/2024/04/15/getting-started-with-perlimports/) to get a better idea of what symbols you are using.

## Reduce the amount transitive dependencies

1. The more modules you depend on, the larger the attack surface you may have to defend.

## Ensure your project is sustainable

1. Have at least one other trusted co-maintainer
    * You can add a co-maintainer in PAUSE
1. Have a succession plan
    * Describe who among your co-maintainers will take over your project if you become permanently unavailable

## Select an appropriate Open Source license

* Pick an OSI-approved Open Source license, and add it both to your project repo and other metadata.


# Relevant documentation and guides

* SEI CERT [Secure Perl Coding Standard](https://wiki.sei.cmu.edu/confluence/display/perl/SEI+CERT+Perl+Coding+Standard)
* [NIST Secure Software Development Framework](https://csrc.nist.gov/projects/ssdf)
* [CISA Product Security Bad Practices guide](https://www.cisa.gov/resources-tools/resources/product-security-bad-practices)


## License and use of this document

* Version: 0.5.2
* License: [CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/deed)
* Copyright: © Salve J. Nilsen <sjn@oslo.pm>, Some rights reserved.

You may use, modify and share this file under the terms of the [CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/deed) license.
