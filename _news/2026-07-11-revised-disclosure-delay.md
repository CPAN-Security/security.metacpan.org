---
layout: single
toc: false
title: "CPANSec Has Revised Our Default Disclosure Dates"
date: 2026-07-15 10:00:00 +0100
collection: news
tags: cna cve embargo llm ai disclosure
authors:
  - cpansec
author_profile: false
header:
  overlay_image: /assets/images/header/SJN07451.JPG
  teaser: assets/images/teaser/SJN07974.JPG
  overlay_filter: 0.6
  caption: "Photo credit: [@sjn](https://github.com/sjn)"
---

At the [Perl Toolchain Summit in April 2026](https://perltoolchainsummit.org/pts2026/),
members of the CPANSec CNA discussed disclosure periods and decided to reduce the _default_ disclosure date ("embargo") for publishing vulnerabilities from 28 days to 14 days.

Some CPAN authors have expressed concerns about this change so we wanted to detail the reasons for this change:

- LLMs are accelerating vulnerability discovery, and many in the security
  community consider AI-discoverable issues to be effectively public already.
- This makes long embargoes riskier: users need timely information so they
  can mitigate, whether or not a fix is available upstream.
- Once we confirm a vulnerability, we assign a CVE identifier,
  notify the author, and set a planned disclosure date, after which the
  CVE is published.
- The default disclosure period is 14 days, but this is a recommendation,
  not a hard deadline.  Maintainers who need more time can request an
  extension, and we will work with them.

See [CPANSec Has Revised Our Default Disclosure Date](/docs/revised-disclosure-delay) for the full document.
