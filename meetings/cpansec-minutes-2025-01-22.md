---
layout: page
toc: true
meeting_time: 2025-01-22 16:00 UTC
title: Minutes 2025-01-22
---

## Agenda & Meeting Details

* 2025-01-22 16:00 UTC on #cpansec-discussion on Matrix

## 15:30 UTC – Pre-meeting socializing

*   Socializing & getting up to speed before the meeting starts properly
*   Discuss organizing projects, swimlanes and issues (...)

## 16:05 UTC – Meeting start

### Welcome

*   Meeting chair: @timlegge
*   Meeting scribe: @sjn

### Attendees, absents & regrets

*   Attendees
    * @sjn, @timlegge, @tux, @stigtsp
*   Regrets
    * @thibaultduponchelle, @robrwo

### Approve previous meeting minutes
*   Previous meeting minutes was approved by @timlegge and @robrwo, and merged by @sjn


### Quick summary of current work (Grouped by project)
, 
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
8.  [CPAN Vulnerability Index](https://github.com/orgs/CPAN-Security/projects/10)
    *   …
9.  [CPANSec Governance, Policy & Funding](https://github.com/orgs/CPAN-Security/projects/7)
    *   …
10. [CPAN Secure by Default](https://github.com/orgs/CPAN-Security/projects/15)
    *   …
11. [CPAN Software Composition Analysis](https://github.com/orgs/CPAN-Security/projects/6)
    *   …

### TLS/HTTPS/CSPRNG/DSA in core
- No real news. From the PSC minutes: "We briefly touched on feedback on our preliminary plan for TLS in core, suggesting that an even simpler approach may be possible. We will pick this back up in a future call."

### Funding drive
- @sjn will work on that after FOSDEM - will need to know who is open to do (funded) work
    - @stigtsp 1d/w
    - Explore options with Ovid's company
    - @sjn is contact point with regard to funding

### Ongoing vulnerabilities
- @timlegge - @robrwo working on RNG-related ongoing issues; CVE's to be registered by CPANSec CNA when it's active

### Author guide to generating random values for security
- @tux - is a separate version needed for generating passwords? Related? Subsection? (Creating, Storing)
    - We'll see how the random-data-for-security.md doc evolves, and adopt
    - Expand on the curated lists of modules with both positive and negative recommendations

### CPAN Author's Security Policy Guidelines
- @timlegge - @leont's Dist::Zilla plugin in the works
- @stigtsp - Minimal (TLDR) version of policy wanted
- @tux - Team document template wanted; Help needed

### CPAN Meta Spec, Requirements and PURLs
- @sjn - picking up CPAN::Meta::Spec after FOSDEM
- @stigtsp - PURLs add to CVEs

### NIS2 consultation
- @sjn - meeting with ENISA scheduled next week

### Eclipse ORC WG
- @sjn - preparations for workshop Jan 30th in Brussels

### CycloneDX 1.7 Sustainability fields
- @sjn - Meeting with @simbabque to prepare addition of mental health fields to spec

### SBOM/Supply Chain
- @sjn - currently preparing FOSDEM SBOM devroom talk about this
- @tux - we need tools for working with SBOMs. *correct* SBOMs.

### CPAN Steward org
- @sjn - had a meeting with @leont; started the process for setting up a WG on TPRF.
    - No progress yet.

### CNA Update
- @stigtsp and @timlegge have "finished" most of the homework and will submit this week
- @timlegge - Need to take https://github.com/CPAN-Security/security.metacpan.org/blob/main/docs/cna-disclosure-policy.md out of draft

### Recruitment
- @sjn - CPANSec stickers for FOSDEM done, ordered and received!

### Perl Toolchain Summit 2025
- @tux - Topic ideas are already being discussed in #pts on irc.perl.org.
    - Looks like one hot topic will be CPAN Testers, which is currently very broken
- @tux - 3rd-wave voting ends 2025-01-31
- @sjn - Create document on what issues need to be decided on/discussed at PTS

### Testing & Kwalitee?
- @tux - This is a topic to discuss in the next many meetings

### Other
- @sjn - IRC notifications working again; Please give feedback on usability/noise
- @tux - contacted author of Kwalitee w.r.t. `SECURITY.md`, `CONTRIBUTING.md` : all are added to website
- @tux - promised to start on `CVE.SKIP` like support in Test::CVE, but nothing happened yet
- @sjn - LF/OpenSSF survey about cybersecurity awareness around CRA. Please participate: https://www.research.net/r/MRB33VK

### Upcoming events and deadlines
1. [FOSDEM Fringe 2025](https://fosdem.org/2025/fringe/) - Friday January 31st, Brussels
    * Related: [EU Open Source Week](https://opensourceweek.eu/)
1. [FOSDEM 2025](https://fosdem.org/2025/) - 2025-02-(01-02), Brussels - three relevant devrooms!
1. [PTS 2025](https://perltoolchainsummit.org/pts2025/) - Thursday 2025-05-01 … Sunday 2025-05-04 in Leipzig, Germany
1. [gpw2025](https://act.yapc.eu/gpw2025/) - 2025-05-(12-14) in Munich, Germany.
1. TPRC in North America - should any of us propose a talk?

### Operating changes
*   (none)

### Next meeting date, time and location
*   Next meeting is Wednesday 2025-02-05 @ 16:00UTC in #cpansec-discussion on Matrix (17:00 Europe/Amsterdam)

## 16:59 UTC – Meeting end

## 17:00 UTC – End
