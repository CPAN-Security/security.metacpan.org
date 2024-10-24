----
layout: page
title: CPAN Author's Secure Coding Guide
description: A security guide for CPAN Distribution Authors
toc: true
----

## Document status: ⚠️  DRAFT

> [!CAUTION]
> What you see here is a DRAFT of the `CPAN Author's Security Guide` by the CPAN Security Group (CPANSec).
> As long as this document is in DRAFT, all of the points and ideas below are open to revision, deletion or amending – by you!
>
> - Contribute on Github: [https://github.com/CPAN-Security/security.metacpan.org/blob/cpan-author-guide/docs/cpan-author-guide.md](https://github.com/CPAN-Security/security.metacpan.org/blob/cpan-author-guide/docs/cpan-author-guide.md)
> - Discuss on IRC: [ircs://ssl.irc.perl.org:7062/#cpan-security](ircs://ssl.irc.perl.org:7062/#cpan-security)
> - Discuss on Matrix: [https://matrix.to/#/#cpansec:matrix.org](https://matrix.to/#/#cpansec:matrix.org)

## Learn the basics

* Read the [perlsec](https://perldoc.perl.org/perlsec) page to familiarize yourself with Perl's security features
* Read the OpenSSF [Open Source Best Practices Badge](https://www.bestpractices.dev/en) program, and try to at least achieve a [passing badge](https://www.bestpractices.dev/en/criteria/0). (You can also see how well [other Perl projects](https://www.bestpractices.dev/en/projects?q=perl) do in this regard!)

# Write code that is _Secure by Design_

* [CISA's Secure by Design Pledge](https://www.cisa.gov/securebydesign/pledge)


## Keep your security metadata up-to-date

* Read the [CPAN::META::Spec](https://metacpan.org/pod/CPAN::Meta::Spec) and make sure all relevant fields are correct and up-to-date

## Share your security metadata

* Add a [security.txt](https://securitytxt.org/) file to your project website
* Add a [security policy](https://docs.github.com/en/code-security/getting-started/adding-a-security-policy-to-your-repository#adding-a-security-policy-to-your-repository) to your Github project

## Add security tests to your code

* Add [tests for taintedness](https://metacpan.org/pod/Test::Taint) to your codebase

## Practice symbol import discipline

* Use [App::perlimports](https://www.olafalders.com/2024/04/15/getting-started-with-perlimports/) to get a better idea of what symbols you are using.

## Reduce the amount transitive dependencies

* The more modules you depend on, the larger the attack surface you'll have to defend.

## Ensure you have trusted co-maintainers

* Add a co-maintainer in PAUSE

## Have a succession plan

* Describe who among your co-maintainers will take over your project if you become unavailable

## Select an appropriate Open Source license

* Pick an OSI-approved Open Source license, and add it both to your project repo and other metadata.


# Relevant documentation and guides

* SEI CERT [Secure Perl Coding Standard](https://wiki.sei.cmu.edu/confluence/display/perl/SEI+CERT+Perl+Coding+Standard)
* [NIST Secure Software Development Framework](https://csrc.nist.gov/projects/ssdf)
* [CISA Product Security Bad Practices guide](https://www.cisa.gov/resources-tools/resources/product-security-bad-practices)


## License and use of this document

* Version: 0.5.1
* License: [CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/deed)
* Copyright: © Salve J. Nilsen <sjn@oslo.pm>, Some rights reserved.

You may use, modify and share this file under the terms of the [CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/deed) license.
