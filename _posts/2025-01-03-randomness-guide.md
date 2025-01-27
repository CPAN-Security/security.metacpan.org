---
layout: post
published: True
toc: true
title: "CPAN Author's Guide to Random Data for Security"
date: 2025-01-03 15:30:00 +0000
tags: authors guides cpan modules security random randomness urandom cryptography
author: Robert Rothenberg
excerpt: "Any secret token that allows someone to access a resource or perform an action should be generated with a secure random number generator..."
---

Any secret token that allows someone to access a resource or perform an action should be generated with a secure random
number generator.  Perl's built-in [rand](https://perldoc.perl.org/functions/rand) function is not suitable for this:
it is seeded by only 32-bits (4 bytes), and the output can be predicted easily.

There are many modules on CPAN with random number generators. Which ones should you use?

We have added a
[CPAN Author’s Guide to Random Data for Security](https://security.metacpan.org/docs/guides/random-data-for-security.html).
This recommends a few modules that are generaly portable, easy to use and have good defaults.
