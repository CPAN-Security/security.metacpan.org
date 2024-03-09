----
layout: page
title: CPAN Author's Security Guide
toc: true
----

> [!CAUTION]
> ## Document status: ⚠️  DRAFT
> What you see here is a DRAFT of the `CPAN Author's Security Guide` by the CPAN Security Group (CPANSec).
> As long as this document is in DRAFT, all of the points and ideas below are open to revision, deletion or amending – by you!
>
> - Contribute on Github: [https://github.com/CPAN-Security/security.metacpan.org/blob/main/docs/glossary.md](https://github.com/CPAN-Security/security.metacpan.org/blob/main/docs/cpan-author-guide.md)
> - Discuss on IRC: [ircs://ssl.irc.perl.org:7062/#cpan-security](ircs://ssl.irc.perl.org:7062/#cpan-security)

## Learn the basics

* Read the [perlsec](https://perldoc.perl.org/perlsec) page to familiarize yourself with Perl's security features

## Keep your security metadata up-to-date

* Read the [CPAN::META::Spec](https://metacpan.org/pod/CPAN::Meta::Spec) and make sure all relevant fields are correct and up-to-date

## Share your security metadata

* Add a [security.txt](https://securitytxt.org/) file to your project website
* Add a [security policy](https://docs.github.com/en/code-security/getting-started/adding-a-security-policy-to-your-repository#adding-a-security-policy-to-your-repository) to your github project


## Add security tests to your code

* Add [tests for taintedness](https://metacpan.org/pod/Test::Taint) to your codebase
