---
layout: page
title: CPAN Risk Assessment Guide
toc: true
---

# Document status: ⚠️  DRAFT

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

1. Dependencies are up-to-date, and automated mechanisms to check for updates are in place and regularly checking
2. Tests include an automated vulnerability check (e.g. using [CPAN::Audit](https://metacpan.org/pod/CPAN::Audit) or [Test::CVE](https://metacpan.org/pod/Test::CVE)) that are executed regularly
3. Dependencies and related metadata are made available in a vendor-neutral SBOM format


### Sustainability

1. Project completeness — Look for signs of documents and other artefacts that are commonly expected in open source projects. E.g.: `README`, `LICENSE`, `Changes` and `CONTRIBUTING` files; A public source code repository; A public bugtracker; A community communications channel.
2. Upstream placement in the [River of CPAN](https://neilb.org/2015/04/20/river-of-cpan.html) — An indication of this can be found on MetaCPAN's reverse dependency list ([example](https://metacpan.org/dist/Test-Simple/requires)).
3. Bus-factor — How many active developers with indexing permissions exist? You can find this out on MetaCPAN ([example](https://metacpan.org/dist/Test-Simple) in left column).
4. Advocacy visibility — Is the project (or one of it's reverse dependencies) actively mentioned in social media or common community channels?
5. Funding options — Does the project offer low-effort ways for users to donate to it?E.g. [Ko-fi](https://ko-fi.com/) or [Paypal](https://www.paypal.com/donate/buttons) donation links, or maybe even ~~[Github Sponsors](https://github.com/sponsors)~~, or ~~[Tidelift](https://tidelift.com/)~~
6. Collaboration metrics — Forum activity; Issue triage and responsiveness; Merge requests.


### Community responsiveness

1. Number of old unmerged pull-requests
2. Number of open and stale issues
3. Forum availability and searchability
4. Availability of support from other community members


### Project infrastructure

1. Relevant, well-developed and functional test-suite
2. …


## Options for risk mitigation

1. Consider availability for adoption when owner is unresponsive and distribution is made available for adoption via the [ADOPTME](https://metacpan.org/author/ADOPTME) facility on PAUSE/CPAN
2. Consider availability for assisting when owner is looking for co-maintainer support, via the [NEEDHELP](https://metacpan.org/author/NEEDHELP) facility on PAUSE/CPAN
3. Consider the availability for handoff when owner is looking for someone to take over the distribution, via the [HANDOFF](https://metacpan.org/author/HANDOFF) facility on PAUSE/CPAN


## See Also

1. See https://neilb.org/adoption/ for a better list of candidates for adoption
if you are open for taking responsibility beyond your direct dependency requirements.
2. [How to adopt a CPAN distribution](https://metacpan.org/about/faq#howtoadoptadistribution)
3. [The PAUSE Operating Model](https://pause.perl.org/pause/query?ACTION=pause_operating_model)
