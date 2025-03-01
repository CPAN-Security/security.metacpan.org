---
layout: page
toc: true
meeting_time: 2024-12-11 16:00 UTC
title: Minutes 2024-12-11
---

## Agenda & Meeting Details

* 2024-12-11 16:00 UTC on #cpansec-discussion on Matrix

## 15:30 UTC – Pre-meeting socializing

*   Socializing & getting up to speed before the meeting starts properly
*   Discuss organizing projects, swimlanes and issues (...)

## 16:03 UTC – Meeting start

### Welcome

*   Meeting chair: @stigtsp, @sjn
*   Meeting secretary: @sjn

### Attendees, absents & regrets

*   Attendees
    * @sjn, @robrwo, @stigtsp, @timlegge
*   Regrets
    * @thibaultduponchelle, @tux

### Approve previous meeting minutes

*   Previous meeting minutes was approved by @tux, @sjn and merged by @sjn


### 2024 Retrospective
*   @stigtsp – Lots of good activities this year! TLS in Core, CNA work; Good to see new faces!
    * One more win: Familiarity with how the CVE process actually works, and how we can use this to improve security on CPAN and in general
    * We've also learned more about the CPAN security landscape, including how SBOMs and CVEs are going to eventually interact
    * Working on these issues has been surprisingly meaningful, and having a "slow-moving" and low-volume ecosystem turns out to be a great benefit, allowing us to focus on more things we care about
    * PAUSE security exploration has also been interesting. Security reviews turns out to be a productive activity, and we should do this on other projects too.
*   @timlegge – We've had some wins related to cpanm  following the work at PTS in Lisbon, including having fixes added to misc. distributions
    * We've learned a little about common failure modes and security issues, giving us an idea of where we may put in effort forward
*   @robrwo – Exploring CPAN code has also revealed issues, and the usefulness of static code analysis tools.
    * Writing guides has been good, and we should do more; and possibly turning these into blogposts for general consumption.
*   @sjn – In my work around SBOMs, metadata and the CRA, I've found that quite a few appreciate to speak with someone involved in supply-chain security.


### Funding drive
*   @sjn – can be skipped
    * [German Sovereign Tech fund](https://www.sovereign.tech/programs/fund)
    * [GitHub Secure Open Source Fund](https://resources.github.com/github-secure-open-source-fund/) deadline Jan 7th
    * Alpha-Omega

### Ongoing vulnerabilities
*   @robrwo – Several reported by @robrwo to CPANSec list on 3 Dec but no CVEs requested. These are still under embargo

#### POSIX::2008 vulnerabilities
* @robrwo - progress!
   * < 0.24 assigned CVE-2024-55564
   * < 0.04 no CVE applied for yet

### CPAN Author's Security Policy Guidelines
*   @robrwo - The [guide is now published and online](https://security.metacpan.org/docs/guides/security-policy-for-authors.html)!
    * Needs more Examples, e.g. multi-author projects
    * Tools for generating them and adding them to distributions (depends on CPAN Meta?)
    * MetaCPAN support https://github.com/metacpan/metacpan-web/issues/3246
    * Kwalitee/CPANTS

### Author guide to generating random values for security
*   @robrwo – Guide to be started together with @stigtsp

### CPAN Steward org
*   @sjn - Proposing that CPANSec makes a bid to become it

### 2025 Forecast
*   @sjn – The CRA is in effect, and this has massive implications for us, security on CPAN, and open source in general
*   @sjn – Some important milestones we'll have to work towards in the next year includes:
    * Make CPAN dependencies fully featured, supporting cross-ecosystem dependencies, service dependencies and more. This probably includes finding ways to use Package URLs when specifying requirements.
    * Find ways to make CPAN tooling to support Package URLs, so others can correctly state their requirements on CPAN packages, and that external ecosystems (e.g. Deb or RPM package indices) and databases (e.g. MITRE CVE) can refer to CPAN packages in an ecosystem-independent way.
    * Introduce SBOMs into the CPAN toolchain and services, so businesses and other users can comply with regulation without too much cost
    * Find a way to make CPANSec's work sustainable. We expect a large increase in activity as a consequence of the Cyber Resilience Act coming into effect Dec 10th 2024. This may include the possiblity as setting up CPANSec as a Steward on behalf of the CPAN ecosystem.
    * In the first few months, we'll have to look into ways to help the Perl/CPAN toolchain community get up to speed on the the coming consequences of the CRA, in such a way that necessary decisions can be made. A natural deadline for this is the PTS in Leipzig in May.

### Upcoming events and deadlines
1. [FOSDEM Fringe 2025](https://fosdem.org/2025/fringe/) - Friday January 31st, Brussels
    * Related: [EU Open Source Week](https://opensourceweek.eu/)
1. [FOSDEM 2025](https://fosdem.org/2025/) - February 1-2, Brussels - three relevant devrooms!
1. [PTS 2025](https://perltoolchainsummit.org/pts2025/) - Thursday May 1st to Sunday May 4th 2025 in Leipzig, Germany

### Operating changes
*   (none)

### Next meeting date, time and location
*   Next meeting is Friday 2025-01-08 (8 Jan 2025) @ 16:00UTC (17:00 Europe/Amsterdam) in #cpansec-discussion on Matrix

## 17:03 UTC – Meeting end

## 17:30 UTC – End
