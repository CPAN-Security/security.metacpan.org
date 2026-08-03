---
layout: single
published: true
toc: false
title: "CPAN Author's Guide to Random Data for Security"
date: 2025-01-03 15:30:00 +0000
collection: blog
tags: authors guides cpan modules security random randomness urandom cryptography
author: robrwo
excerpt: "Any secret token that allows someone to access a resource or perform an action should be generated with a secure random number generator..."
header:
  overlay_image: /assets/images/header/SJN07450.JPG
  teaser: assets/images/teaser/SJN07450.JPG
  overlay_filter: 0.6
  caption: "Photo credit: [@sjn](https://github.com/sjn)"
---

Any secret token that allows someone to access a resource or perform an action should be generated with a secure random
number generator.  Perl's built-in [rand](https://perldoc.perl.org/functions/rand) function is not suitable for this:
it is seeded by only 32-bits (4 bytes), and the output can be predicted easily.

There are many modules on CPAN with random number generators. Which ones should you use?

We have added a
[CPAN Author’s Guide to Random Data for Security](https://security.metacpan.org/docs/guides/random-data-for-security.html).
This recommends a few modules that are generally portable, easy to use and have good defaults.
