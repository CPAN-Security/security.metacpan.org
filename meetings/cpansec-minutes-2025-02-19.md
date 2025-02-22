---
layout: page
toc: true
meeting_time: 2025-02-19 17:00 UTC
title: Minutes 2025-02-19
---

## Meeting Details
* 2025-02-19 17:00 UTC on #cpansec-discussion on Matrix

## 16:30 UTC – Pre-meeting socializing
*   Socializing & getting up to speed before the meeting starts properly
*   Discuss organizing projects, swimlanes and issues (...)

## 17:05 UTC – Meeting start

### Welcome
*   Meeting chair: @timlegge
*   Meeting scribe: @sjn

### Attendees, absents & regrets
*   Attendees
    * @sjn, @leont, @thibaultduponchelle, @stigtsp
*   Regrets
    * @tux, @robrwo

### Approve previous meeting minutes
*   Previous meeting minutes was approved by @timlegge, @stigtsp, @leont and @thibaultduponchelle, and merged by @sjn

### Quick summary of current work (Grouped by project)
1.  [CPAN Metadata & Software Bills of Materials](https://github.com/orgs/CPAN-Security/projects/1)
    *   …
2.  [CPAN Privacy and Compliance](https://github.com/orgs/CPAN-Security/projects/9)
    *   …
3.  [CPAN Provenance & Supply Chain Security](https://github.com/orgs/CPAN-Security/projects/3)
    *   …
4.  [CPAN Security Outreach & Information](https://github.com/orgs/CPAN-Security/projects/12)
    *   …
5.  [CPAN Security Patch Tooling](https://github.com/orgs/CPAN-Security/projects/11)
    *   …
6.  [CPAN Software Composition Analysis](https://github.com/orgs/CPAN-Security/projects/6)
    *   …
7.  [CPAN Transparency Logs](https://github.com/orgs/CPAN-Security/projects/2)
    *   …
8.  [CPAN CNA & Vulnerability Index](https://github.com/orgs/CPAN-Security/projects/10)
    *   …
9.  [CPANSec Governance, Policy & Funding](https://github.com/orgs/CPAN-Security/projects/7)
    *   …
10. [CPAN Secure by Default](https://github.com/orgs/CPAN-Security/projects/15)
    *   …
11. [CPAN Software Composition Analysis](https://github.com/orgs/CPAN-Security/projects/6)
    *   …

### TLS/HTTPS/CSPRNG/DSA in core
- @leont - no progress

### Funding drive
- [] @sjn – who is open to do (funded) work? (contact @sjn)
    - @stigtsp 1d/w
    - @leont 
- [] @sjn - Explore options with Ovid's company

### Ongoing vulnerabilities
- [] @timlegge - @robrwo working on RNG-related ongoing issues; CVE's to be registered by CPANSec CNA when it's active
- [x] @timlegge - Crypt::Random release
- [] @timlegge - Crypt::Bcrypt issues around password length

### Author guide to generating random values for security
- [x] Crypt::SysRandom to be added, but fine to go

### CPAN Author's Security Policy Guidelines
- [] @stigtsp - Minimal (TLDR) version of policy wanted
- [] @tux - Team document template wanted; Help needed
- [x] @leont - Dist::Zilla plugin created

### CPAN Meta Spec, Requirements and PURLs
- [] @sjn - started on writing an overview of issues to be resolved before PTS
- [] @sjn - picking up CPAN::Meta::Spec after FOSDEM
- [] @sjn - need to push GDT's update to spec

### NIS2 consultation
- [x] @sjn - new meeting 2025-02-18; ENISA appreciates the feedback

### Eclipse ORC WG
- [] @sjn - Lots of progress on the [FAQ](https://github.com/orcwg/cra-hub/blob/main/faq.md) and [Inventory](https://github.com/orcwg/cra-hub/blob/main/inventory.md) docs, with lots of issues created.

### CycloneDX 1.7 Sustainability fields
- [] @sjn - starting on the final stretch - project- & ecosystem-supplied status fields.

### SBOM/Supply Chain
- [] @tux - we need tools for working with SBOMs. *correct* SBOMs.
- [] @thibaultduponcelle - wants some feedback on his starjacking text (good enough to merge or drop?)
  - @sjn and @thibaultduponcelle - chat about this (set up meeting)
  
### CPAN Steward org
- [] @sjn - Discussions on TPRF slack #cpansec-steward; Mostly @sjn making noise; Contributors needed.
  - [x] @elbeho and @markov invited; @markov shared lots of good insights
  - [x] @sjn met also w/others in his environment, and that care about Open Source-friendly project ownership structures & bylaws
  - [x] General invite sent out on [Mastodon](https://chaos.social/@sjn/114008648429337137)
  - [x] Forum for discussing this has been set up on the TPRF slack: #cpansec-steward; please reach out if you need invites!
- [x] should we set up a separate project for this, or use Governance/Policy/Funding? - no
- [] @sjn has been asked by BSI and FSFE to help with perspectives and questions for a questionnaire. Discussions around this happens in #cpansec-steward on the TPRF Slack

### CNA Update
- [x] @timlegge - CNA disclosure published thanks to @sjn's help
- [] @sjn - Should CPANSec follow the [Node community's example](https://nodejs.org/en/blog/vulnerability/upcoming-cve-for-eol-versions) of issuing CVEs for EOL-versions of Perl? - not discussed
- [] @stigtsp - updates from MITRE to be announced
  - [] @timlegge - contact DAVEM, TONYC

### Recruitment
- [] @sjn - look at the next events for opportunities

### Perl Toolchain Summit 2025
- [] @sjn - Create document on what CPANSec-relevant issues need to be decided on/discussed at PTS

### Other
- [] @stigtsp - CVE portal setup
- [] @stigtsp - domain name; we're using metacpan.org branding, but also own the cpansec.org domain. What to do with this?

### Upcoming events and deadlines
1. [x] (Belgium) [FOSDEM Fringe 2025](https://fosdem.org/2025/fringe/) - Friday January 31st, Brussels
1. [x] (Belgium) [FOSDEM 2025](https://fosdem.org/2025/) - 2025-02-(01-02), Brussels - three relevant devrooms!
1. [] (Germany) [PTS 2025](https://perltoolchainsummit.org/pts2025/) - Thursday 2025-05-01 … Sunday 2025-05-04 in Leipzig, Germany
1. [] (Germany) [GPW 2025](https://act.yapc.eu/gpw2025/) - Monday 2025-05-12 … Wednesday 2025-05-14 in Munich, Germany. ([CfP is open](https://act.yapc.eu/gpw2025/cfp.html))
1. [] (USA) [TPRC 2025](https://www.perl.com/article/get-ready-for-the-2025-perl-and-raku-conference/) - Friday 2025-06-27 … Sunday 2025-06-29 in Greenville, SC, USA ([CfP is open](https://www.papercall.io/tprcgsp2025); Deadline: 2025-03-15)
1. [] (Norway) [Sikkerhetfesivalen 2025](https://sikkerhetsfestivalen.no/) - Monday 2025-08-25 … Wednesday 2025-08-27 in Lillehammer, Norway. ([CfP is open](https://sikkerhetsfestivalen.no/alle-nyheter/2024/11/22/hvordan-skape-et-vinnende-foredrag-for-sikkerhetsfestivalen-2025); Deadline: 2025-03-03)

### Operating changes
- @sjn - Published the [CPANSec meeting calendar](https://calendar.google.com/calendar/u/0/embed?src=e4630horojrd4ivirjbfi7t0haqvcssd@import.calendar.google.com) on Google, via our [perl.social](https://perl.social) Friendica account calendar. This calendar is public! Reach out to @sjn to get access to update it.
  - perl.social seems a bit unreliable :-( - maybe use another shared calendar solution? (e.g. cryptpad?)

### Next meeting date, time and location
* Next meeting is Wednesday 2025-03-12 @ 17:00UTC in #cpansec-discussion on Matrix (17:00 Europe/Amsterdam)

## 18:14 UTC – Meeting end

## 18:15 UTC – End
