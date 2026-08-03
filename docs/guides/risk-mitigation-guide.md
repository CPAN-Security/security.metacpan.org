---
layout: single
title: CPAN Risk Mitigation Guide
toc: true
---

# Document status: ⚠️  DRAFT

## CPAN Dependency Risk Mitigation

This guide is *INFORMATIONAL* and should be considered as a continuously developing document. Please ensure you [check this document](https://security.metacpan.org/docs/risk-assessment-guide.md) regularly for updates.

Corrections or improvements to this text can be filed in the [security.metacpan.org issue tracker](https://github.com/CPAN-Security/security.metacpan.org/issues). Pull requests are also welcome.


## Assessing risk in the CPAN ecosystem

Please see our [CPAN Risk Assessment Guide](risk-assessment-guide.md).


# Mitigating risk in the CPAN ecosystem

## For component projects published on CPAN

1. Consider availability for adoption when owner is unresponsive and distribution is made available for adoption via the [ADOPTME](https://metacpan.org/author/ADOPTME) facility on PAUSE/CPAN
2. Consider availability for assisting when owner is looking for co-maintainer support, via the [NEEDHELP](https://metacpan.org/author/NEEDHELP) facility on PAUSE/CPAN
3. Consider the availability for hand-off when owner is looking for someone to take over the distribution, via the [HANDOFF](https://metacpan.org/author/HANDOFF) facility on PAUSE/CPAN
4. Look for funding options for the projects in question
5. Update the required version for dependencies when included modules implement security fixes


## For CPAN ecosystems themselves, including PAUSE, MetaCPAN and any other supporting systems.

1. Fund ongoing security improvement work, via the Perl and Raku Foundation, or through the relevant projects themselves.


## See Also

1. See https://neilb.org/adoption/ for a better list of candidates for adoption
if you are open for taking responsibility beyond your direct dependency requirements.
2. [How to adopt a CPAN distribution](https://metacpan.org/about/faq#howtoadoptadistribution)
3. [The PAUSE Operating Model](https://pause.perl.org/pause/query?ACTION=pause_operating_model)
4. Blog post: [How will NIS2 affect the supply chain security approach?](https://www.ey.com/en_pl/law/nis2-supply-chain-security)


# Legislative background

## NIS2

* Article 21(2)(d); (⚠️  unconfirmed)
* Article 22; (⚠️  unconfirmed)
    * Recitals (90), (91); (⚠️  unconfirmed)
* For internal risk assessments
    * Recital (85); (⚠️  unconfirmed)
