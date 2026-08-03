---
layout: single
title: CPAN Risk Assessment Guide
toc: true
---

# Document status: ⚠️  DRAFT

## CPAN Dependency Risk Assessment

This guide is *INFORMATIONAL* and should be considered as a continuously developing document. Please ensure you [check this document](https://security.metacpan.org/docs/risk-assessment-guide.md) regularly for updates.

Corrections or improvements to this text can be filed in the [security.metacpan.org issue tracker](https://github.com/CPAN-Security/security.metacpan.org/issues). Pull requests are also welcome.


# Assessing risk in the CPAN ecosystem

## Methodology and Reading materials

* [CHAOSS Community metrics](https://opensource.com/article/22/11/community-metrics)
* [PAUSE Operating Model](https://pause.perl.org/pause/query?ACTION=pause_operating_model) with [commentary](http://neilb.org/2013/08/07/adoptme.html)
* The [Deming Principles](https://www.uthsc.edu/its/business-productivity-solutions/lean-uthsc/deming.php) on managing quality.
* The [NIST Cybersecurity Framework 2.0](https://www.nist.gov/cyberframework), and related [Cybersecurity Supply Chain Risk Management Practices for Systems and Organizations](https://csrc.nist.gov/pubs/sp/800/161/r1/final) guidelines.
* The EO 14028 [Software Security in Supply Chains](https://www.nist.gov/itl/executive-order-14028-improving-nations-cybersecurity/software-security-supply-chains) guide
* …


## Assessment recommendations

These items apply to all dependencies that use CPAN as a publishing and/or distribution channel.
This also applies to modules that are re-packaged for other native packaging ecosystems (e.g. Debian DPKG or AlmaLinux RPM), though some recommendations may be different for packages that are distributed there.


### Security

1. Dependencies are up-to-date, and automated mechanisms to check for updates are in place and regularly checking
2. Tests include an automated vulnerability check (e.g. using [CPAN::Audit](https://metacpan.org/pod/CPAN::Audit) or [Test::CVE](https://metacpan.org/pod/Test::CVE)) that are executed regularly
3. Dependencies and related metadata are made available in a vendor-neutral SBOM format


### Sustainability

1. Project completeness — Look for signs of documents and other artifacts that are commonly expected in open source projects. E.g.: `README`, `LICENSE`, `Changes` and `CONTRIBUTING` files; A public source code repository; A public bug tracker; A community communications channel.
2. Upstream placement in the [River of CPAN](https://neilb.org/2015/04/20/river-of-cpan.html) — An indication of this can be found on MetaCPAN's reverse dependency list ([example](https://metacpan.org/dist/Test-Simple/requires)).
3. Bus-factor — How many active developers with indexing permissions exist? You can find this out on MetaCPAN ([example](https://metacpan.org/dist/Test-Simple) in left column).
4. Advocacy visibility — Is the project (or one of it's reverse dependencies) actively mentioned in social media or common community channels?
5. Funding options — Does the project offer low-effort ways for users to donate to it? E.g. [Ko-fi](https://ko-fi.com/) or [Paypal](https://www.paypal.com/donate/buttons) donation links, or maybe even ~~[Github Sponsors](https://github.com/sponsors)~~, or ~~[Tidelift](https://tidelift.com/)~~
6. Collaboration metrics — Forum activity; Issue triage and responsiveness; Merge requests.


### Community responsiveness

1. Number of old unmerged pull-requests
2. Number of open and stale issues
3. Forum availability and searchability
4. Availability of support from other community members


### Project infrastructure

1. Relevant, well-developed and functional test-suite
2. Active use of Software Composition Analysis tools
3. …


### Coding practices

1. Correct and updated dependency list, that takes known vulnerabilities into account
    * Author
    * Build
    * Test
    * Runtime
2. Avoid compiled code from untrusted sources
3. Avoid code generation at build time, test time or runtime
    * Code generators can be exploited too
4. Avoid build and test plugins
    * Plugins may be enabled unintentionally, and thereby create difficult-to-detect attack vectors
5. Developer focus on code understandability
    * Obscure or difficult-to-understand code makes exploit detection more difficult, and therefore a better target for attackers
6. …


# Mitigating risk in the CPAN ecosystem

See the [CPAN Risk Mitigation Guide](risk-mitigation-guide.md).

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


# Reading list

* [Interoperable EU Risk Management Framework](https://www.enisa.europa.eu/publications/interoperable-eu-risk-management-framework), (published 2022-12)
