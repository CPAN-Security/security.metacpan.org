---
layout: page
title: CPAN Risk Assessment Guide
toc: true
---

Welcome to the CPAN Security Working Group's guide for CPAN Dependecy Risk Assessment.

This guide is *INFORMATIONAL* and should be considered as a continuously developing document. Please ensure you [check this document](https://security.metacpan.org/docs/risk-assessment-guide.md) regularly for updates.

Corrections or improvements to this text can be filed in the [security.metacpan.org issue tracker](https://github.com/CPAN-Security/security.metacpan.org/issues). Pull requests are also welcome.

## Recommended methodology

For this check-list, we take inspiration from the following sources.

* https://opensource.com/article/22/11/community-metrics
* 


## Recommended check-list

These items apply to all dependencies that use CPAN as a publishing and/or distribution channel. This also applies to modules that are re-packaged for other native packaging ecosystems (e.g. Debian APT or RedHat RPM), though some recommendations may be different for packages that are distributed there.

### Sustainability

1. Project completeness
2. Upstream placement in the "River of CPAN"
3. Bus-factor
4. Advocacy visibility
5. Funding options
6. Collaboration metrics
7. …

### Responsiveness

1. Unmerged pull-requests
2. Open and stale issues
3. Forum availability and searchability
4. …

### Security infrastructure

1. Well-developed and functional test-suite
2. Source code repository availability
3. Author availability
4. Object signatures
5. …

