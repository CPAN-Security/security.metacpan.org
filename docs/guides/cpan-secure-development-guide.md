---
layout: page
toc: true
author: Salve J. Nilsen
mastodon: { username: sjn, instance: chaos.social }
title: CPAN Author's Guide to Secure Software Development
description: A guide for CPAN distribution authors to writing secure code, by the CPAN Security Group
---

## Document status: ⚠️  DRAFT

> [!CAUTION]
> What you see here is a DRAFT of the `CPAN Author's Guide to Secure Software Development` by the CPAN Security Group (CPANSec).
> As long as this document is in DRAFT, all of the points and ideas below are open to revision, deletion or amending – by you!
>
> - Contribute on Github: [https://github.com/CPAN-Security/security.metacpan.org/blob/cpan-author-guide/docs/guides/cpan-author-guide.md](https://github.com/CPAN-Security/security.metacpan.org/blob/cpan-author-guide/docs/guides/cpan-author-guide.md)
> - Discuss on IRC: [ircs://ssl.irc.perl.org:7062/#cpan-security](ircs://ssl.irc.perl.org:7062/#cpan-security)
> - Discuss on Matrix: [https://matrix.to/#/#cpansec:matrix.org](https://matrix.to/#/#cpansec:matrix.org)


## The need for Secure Software Development on CPAN

As of December 2024, we have new guidelines and legislation introduced in the EU ([NIS2](../readinglist.md#nis2) and the [Cyber Resilience Act](../readinglist.md#cra)), with US equivalents ([EO 14028](../readinglist.md#eo14028)), introducing new requirements regarding software security.
These requirements are directed at many businesses and institutions to raise the baseline level of security in the software they produce and in sectors they operate.
A substantial part of these depend on software published on CPAN.
This means there is now a greater need for CPAN distributions to take their security posture into account.

To help in this shift, CPANSec has put together several [guides](./) intended to assist any developers publishing on CPAN to improve their distributions and code.


### _Secure by Design_ and _Secure by Default_

1. EU Cyber Resilience Act, [Annex I, Part I](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#anx_I)
    * A good illustration of what is expected from CPAN users
1. [CISA's Secure by Design Pledge](https://www.cisa.gov/securebydesign/pledge)


## Improving your distribution


### Keep your security metadata up-to-date

1. Read the [CPAN::META::Spec](https://metacpan.org/pod/CPAN::Meta::Spec), and
    - [ ] make sure all relevant fields are correct and up-to-date
1. Ensure also that your list of requirements (dependencies) is
    - [ ] complete, up-to-date, and correct
        - This also means unused (zombie) requirements are removed
        - This includes security issues in embedded/included and transitive dependencies
        - This also means reducing assumed (phantom) dependencies to none, by making them explicit
        - …
    - [ ] take into account any security issues
        - …


### Share your security metadata

1. Communicate your policies and details around security issues
   - [ ] Add a [security.txt](https://securitytxt.org/) file to your project website
   - [ ] Add a [distribution security policy](security-policy-for-authors.md) to your distribution
   - [ ] Add the same to your project repository ([Github instructions](https://docs.github.com/en/code-security/getting-started/adding-a-security-policy-to-your-repository))


### Add security tests to your code

1. Learn how to use [perltaint](https://perldoc.perl.org/perlsec#Laundering-and-Detecting-Tainted-Data) to detect and defang input from untrusted sources
   - [ ] Add [tests for taintedness](https://metacpan.org/pod/Test::Taint) to your codebase, to verify that your code actually handles untrusted input as expected
1. Check out CPANSec's [guide to vulnerability testing](vulnerability-testing.md)


* See also:
    * [OWASP Authorization Testing Automation Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Testing_Automation_Cheat_Sheet.html)

### Practice symbol import discipline

- [ ] Use [App::perlimports](https://www.olafalders.com/2024/04/15/getting-started-with-perlimports/) to get a better idea o what symbols you are using


### Reduce the amount transitive dependencies

1. The more modules you depend on, the larger the attack surface you may have to defend
    - [ ] If necessary, help your upstream maintainers to trim down their dependency graph


### Ensure your project is sustainable

1. Have at least one other trusted co-maintainer
    - [ ] Add a co-maintainer in PAUSE
1. Have a succession plan
    - [ ] Describe who among your co-maintainers will take over your project if you become permanently unavailable
1. Communicate who are your contributors, co-maintainers and successors clearly through common channels
    - [ ] Keep an up-to-date list of co-maintainers and contributors in your repository, e.g. in an 'Acknowledgements' or 'Contributors' section in the documentation
    - [ ] Add a `CONTRIBUTING.md` file, to make it easier for both new and old contributors to help


### Select an appropriate Open Source license

1. Ensure you license is commonly used
    - [ ] Pick an OSI-approved Open Source license, and
    - [ ] add it both to your project repository and other metadata


## Improving your code

### Use a secure Random Number Generator

1. Read the [CPAN Author’s Guide to Random Data for Security](random-data-for-security.md), and
    - [ ] Check and fix your code for any of the bad practices mentioned there


### Use safe cryptographic algorithms

> [!NOTE]
> TODO


### Use certificates correctly

> [!NOTE]
> TODO


### Use secure authentication

> [!NOTE]
> TODO

* See also:
    * [OWASP Password Storage Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html)
    * [OWASP Authentication Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html)


## Further reading {#more}

1. Perl's [perlsec](https://perldoc.perl.org/perlsec) documentation
1. OpenSSF [Open Source Best Practices Badge](https://www.bestpractices.dev/en) program
    * Try to at least achieve a [passing badge](https://www.bestpractices.dev/en/criteria/0).
    * (You can also see how well [other Perl projects](https://www.bestpractices.dev/en/projects?q=perl) do in this regard!)
1. SEI CERT [Secure Perl Coding Standard](https://wiki.sei.cmu.edu/confluence/display/perl/SEI+CERT+Perl+Coding+Standard)
1. [NIST Secure Software Development Framework](https://csrc.nist.gov/projects/ssdf)
1. [CISA Product Security Bad Practices guide](https://www.cisa.gov/resources-tools/resources/product-security-bad-practices)
    * …on [Github Discussions](https://github.com/cisagov/bad-practices/discussions)
1. [OWASP Cheat Sheet Series](https://cheatsheetseries.owasp.org/)


## License and use of this document

* Version: 0.6.1
* License: [CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/deed)
* Copyright: © Salve J. Nilsen <sjn@oslo.pm>, Some rights reserved.

You may use, modify and share this file under the terms of the [CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/deed) license.


## Acknowledgements

* Salve J. Nilsen (main author)
