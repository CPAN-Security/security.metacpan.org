---
layout: post
published: True
toc: true
title: "Add a security policy to your distributions"
date: 2025-01-05 17:15:00 +0000
tags: authors guides cpan modules security
author: Robert Rothenberg
excerpt: "Adding a SECURITY or SECURITY.md file to your Perl distributions will let people know wow to contact the maintainers if they find a security issue with your software..."
---

Adding a `SECURITY` or `SECURITY.md`  file to your Perl distributions will let people know:

1. How to contact the maintainers if they find a security issue with your software
2. What software will be supported for security issues

The contact point is very important for modules that have been around for a long time and have had several authors over the years.
When there is a long list of maintainers, it's not clear who to contact.

You don't want people reporting security vulnerabilities in public on the RT or GitHub issues for your project, nor do you want a post on IRC, Reddit or social media about it.

If your software is on GitHub, you can set up [private vulnerability reporting](https://docs.github.com/en/code-security/security-advisories/working-with-repository-security-advisories/configuring-private-vulnerability-reporting-for-a-repository).
GitLab has a similar system.

Otherwise, a single email address is acceptable. An alias that forwards to all of the maintainers or at the very least, a single maintainer who has agreed to that role will work.

It's also important to realise as a maintainer that you are not on your own when you receive a vulnerability report.
You are welcome and even encouraged to reach out to CPANSec for assistance triaging and fixing the issue, as well as handling notifications and reporting.

The supported software version may seem obvious, but it's important to spell out:
will you be updating only the latest version? What versions of Perl will you support?
If your module uses or embeds other libraries, how will they be supported?

Fortunately it is not difficult to write a security policy.  The [CPAN Security Group](https://security.metacpan.org/) (CPANSec) has written [Guidelines for Adding a Security Policy to Perl Distributions](https://security.metacpan.org/docs/guides/security-policy-for-authors.html). (Note: I am one of the authors of that document.)

The guidelines include a template for a Perl distribution with a single author that you can use as a basis for your distributions.  There is also [Software::Security::Policy](https://metacpan.org/pod/Software::Security::Policy) that will be integrated with build tools in the future to help generate one.

We'd like more people to use the document and provide feedback to CPANSec to improve the advice, and perhaps add alternative templates.

You don't even have to release a new version of your modules immediately.
Just adding a `SECURITY.md` file in the root of the GitHub repo will be helpful enough.

This was originally posted on [blogs.perl.org](https://blogs.perl.org/users/robert_rothenberg/2025/01/add-a-security-policy-to-your-distributions.html).
