---
layout: page
toc: true
meeting_time: 2024-11-27 17:00 UTC
title: Minutes 2024-11-27
---

## Meeting details

* 2024-11-27 17:00 UTC on #cpansec-discussion on Matrix

## 15:30 UTC – Pre-meeting socializing

*   Socializing & getting up to speed before the meeting starts properly
*   Discuss organizing projects, swimlanes and issues (...)

## 16:00 UTC – Meeting start

### Welcome

*   @thibaultduponchelle joined :)
*   Meeting chair: @timlegge
*   Meeting secretary: @sjn & @tux

### Attendees, absents & regrets

*   Attendees
    * @sjn, @stigtsp, @tux, @timlegge, @garu, @robrwo
*   Regrets
    * @thibaultduponchelle (joined later), @leont

### Approve previous meeting minutes
*   Previous meeting minutes was approved @timlegge, @thibaultduponchelle merged by @sjn

### Mailing List
*   @stigstp - Discuss recent issues with our mailing lists being public instead of being private
    * @stigtsp - presented taken actions and open issues
    * @sjn - taken decisions should be properly communicated - @stigtsp will start a writeup, @sjn will review
    * means of advertising will be discussed in the upcomming days

### Quick summary of current work (Grouped by project)

1.  [CPAN Metadata & Software Bills of Materials](https://github.com/orgs/CPAN-Security/projects/1)
    *   …
2.  [CPAN Privacy and Compliance](https://github.com/orgs/CPAN-Security/projects/9)
    *   …
3.  [CPAN Provenance & Supply Chain Security](https://github.com/orgs/CPAN-Security/projects/3)
    *   …
4.  [CPAN Security Outreach & Information](https://github.com/orgs/CPAN-Security/projects/12)
    *   New and existing documentation being discussed in relation to open subjects
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
*   @leont implemented BearSSL and is now fighting IO::Socket::SSL. @BooK & @leont are not present to explain

### German Sovereign Tech fund
*   @sjn - no work done; @garu's personal application was rejected: more feedback on why would be welcome
*   @sjn gives more background information and mentions @stuart's work

### Ongoing vulnerabilities
*   @stigtsp - No movement around Mojo's secure token/secrets issues; Volunteers needed
    * @garu has plans
*   @stigtsp - One more vuln known, needs a volunteer; @timlegge may take a look

### CPAN Author's Security Policy Template/Guidelines
*   @robrwo - working on initial draft - review required
*   @sjn mentions already written documents - maybe merge or restructure
*   new ideas are tossed and proposed by @stigtsp
*   @sjn - issue of setting up security email aliases for dists that go to authors + CPAN sec. May be a good topic for PTS

### Eclipse ORC WG
*   @sjn - Workshop planned in December in Amsterdam (spec Steward roles)

### NIS2 consultation
*   @sjn - Comments to chapter 5 (Supply chains) submitted together with OpenSSF, FSFE, NLnet Labs and GitHub
    * This group is likely to have a meeting with ENISA in December
*   @sjn - Chapter 3 (Incident response) and chapter 6 (Secure software development) comments being worked on.
    * @abraxxa, @robrwo and some of the folks at Hackeriet have contributed

### Perl Toolchain Summit 2025
*   @tux - Date is set to 2024-05-01 … 2024-05-04

### CycloneDX 1.7 Sustainability fields
*   @sjn - ongoing; currently working on a taxonomy of non-funding support. Currently slowish

### CPAN Meta Requirements and PURLs
*   @sjn - No news

### POSIX::2008 vulnerabilities
*   @stigtsp - Probably best to register a CVE

### SBOM/Supply Chain
*   @sjn - minor tweaks; working on connecting fields with metadata sources. First PR received

### CNA Update
*   @timlegge - Mitre confirmed receipt of the CNA request form and will be reviewed soon.

### Recruitment
*   We could use more visibility. We could learn from Raku

### Other
*   Discussion about a matrix of security-related items for CPAN releases
*   @stigtsp Meeting with tib and Stian next week about Tibs research
    * tib and @timlegge look into PAUSE pentesting

### Upcoming events and deadlines
1. [FOSDEM Fringe 2025](https://fosdem.org/2025/fringe/) - Friday January 31st, Brussels
    * Related: [EU Open Source Week](https://opensourceweek.eu/)
1. [FOSDEM 2025](https://fosdem.org/2025/) - February 1-2, Brussels - three relevant devrooms!
1. [PTS 2025](https://perltoolchainsummit.org/pts2025/) - Most likely date: first week of May

### Operating changes
*   None

### Next meeting date, time and location
*   Next meeting is Wednesday 2024-12-11 @ 16:00UTC in #cpansec-discussion on Matrix (17:00 Europe/Amsterdam)

## 17:20 UTC – Meeting end

## 17:20 UTC – Post-meeting socializing end
