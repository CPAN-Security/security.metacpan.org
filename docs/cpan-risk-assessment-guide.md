---
layout: page
title: CPAN Risk Assessment Guide
toc: true
---

## CPAN Dependency Risk Assessment

This guide is *INFORMATIONAL* and should be considered as a continuously developing document. Please ensure you [check this document](https://security.metacpan.org/docs/risk-assessment-guide.md) regularly for updates.

Corrections or improvements to this text can be filed in the [security.metacpan.org issue tracker](https://github.com/CPAN-Security/security.metacpan.org/issues). Pull requests are also welcome.


## Recommended methodology

For this check-list, we take inspiration from the following sources.

* https://opensource.com/article/22/11/community-metrics
* http://neilb.org/2013/08/07/adoptme.html
* …


## Recommended check-list

These items apply to all dependencies that use CPAN as a publishing and/or distribution channel. This also applies to modules that are re-packaged for other native packaging ecosystems (e.g. Debian APT or RedHat RPM), though some recommendations may be different for packages that are distributed there.

### Security

1. Dependencies are up-to-date
2. Tests include an automated vulnerability check (e.g. using CPAN::Audit)
3. Dependencies and related metadata are made available in a vendor-neutral SBOM format
4. …


### Sustainability

1. Project completeness
2. Upstream placement in the "River of CPAN"
3. Bus-factor
4. Advocacy visibility
5. Funding options
6. Collaboration metrics
7. …

### Responsiveness

1. Number of old unmerged pull-requests
2. Number of open and stale issues
3. Forum availability and searchability
4. Availability of support from other community members
5. …

### Infrastructure

1. Well-developed and functional test-suite
2. Source code repository availability
3. Author availability
4. Distribution signatures
5. …


## Options for risk mitigation

1. Consider availability for adoption when owner is unresponsive and distribution is made available for adoption via the [ADOPTME](https://metacpan.org/author/ADOPTME) facility on PAUSE/CPAN
2. Consider availability for assisting when owner is looking for co-maintainer support, via the [NEEDHELP](https://metacpan.org/author/NEEDHELP) facility on PAUSE/CPAN
3. Consider the availability for handoff when owner is looking for someone to take over the distribution, via the [HANDOFF](https://metacpan.org/author/HANDOFF) facility on PAUSE/CPAN


## See Also

1. See https://neilb.org/adoption/ for a better list of candidates for adoption
if you are open for taking responsibility beyond your direct dependency requirements.
2. [How to adopt a CPAN distribution](https://metacpan.org/about/faq#howtoadoptadistribution)
