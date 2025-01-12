---
layout: page
toc: true
meeting_time: 2025-01-08 16:00 UTC
title: Minutes 2025-01-08
---

## Agenda & Meeting Details

* 2025-01-08 16:00 UTC on #cpansec-discussion on Matrix

## 15:30 UTC – Pre-meeting socializing

*   Socializing & getting up to speed before the meeting starts properly
*   Discuss organizing projects, swimlanes and issues (...)

## 16:05 UTC – Meeting start

### Welcome

*   Meeting chair: @sjn
*   Meeting secretary: @tux & @stigtsp

### Attendees, absents & regrets

*   Attendees
    * @sjn, @robrwo. @tux, @leont, @timlegge, @stigtsp
*   Regrets
    * …

### Approve previous meeting minutes
*   Previous meeting minutes was approved by @timlegge and @robrwo, and merged by @sjn


### Quick summary of current work (Grouped by project)
, 
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
- @leont - Worked on BearSSL & OpenSSL
  - cleaning up Crypt::OpenSSL/Net::SSLeay (and to a lesser extent, IO::Socket::TCP/IO::Socket::SSL) is required but tedious.
- @sjn - is funding wanted/useful?

### Funding drive
- [German Sovereign Tech fund](https://www.sovereign.tech/programs/fund)
- [GitHub Secure Open Source Fund](https://resources.github.com/github-secure-open-source-fund/) deadline Jan 7th
- Alpha-Omega
- @sjn will work on that after FOSDEM - will need to know who is open to do (funded) work
    - @stigtsp 1d/w

### Ongoing vulnerabilities
- @robrwo - POSIX::2008 CVE-2024-55564 already added for &lt; v0.24, not for &lt; v0.04
    - @robrwo - Net::OAuth released with fix, CVE-2025-22376
    - WWW::OAuth released with fix based on fix to Net::OAuth, CVE request by @robrwo
    - Several modules waiting for ack from authors or 20/30 Jan to req CVEs and disclosure
- @tux - SQLite CVE was closed in [CPANSA DB](https://metacpan.org/release/BDFOY/CPANSA-DB-20250104.001/source/Changes#L7)

### Author guide to generating random values for security
- @robrwo - Guide is published
   - Link posted on security.metacpan.org front page
   - No feedback received
   - Crypt::URandom (the main module recommended) still has issues to be worked on.
   - Maybe promote it on blogs.perl.org by late Jan
   - PR for Perl to change docs for recommended modules
- @stigtsp - summarizing this work is useful/positive

### CPAN Author's Security Policy Guidelines
- @robrwo - Online
  - Out of draft
  - @robrwo posted about it on blogs.perl.org. That post, and a link to original guidelines posted by briandfoy on Reddit.
  - 65 distributions on CPAN have a SECURITY.md as of 7 Jan
  - [Issue raised in MetaCPAN](https://github.com/metacpan/metacpan-web/issues/3246) to highlight the document like it does README, LICENSE etc
  - Most important: we are getting feedback
- @tux - Software::Security::Policy::Individual - do we need ::Team (or other name)?
  - team policies to be documented: active teams, active groups, active Github projects with more maintainers but no single person to address for vulnerabilities (hidden Github security issues)
  - discussed also different ideas about how templates will evolve.

### CPAN Meta Spec, Requirements and PURLs
- @sjn - plan on raising haarg's points at this week's TC54-TG3 meeting (Thursday Jan 9th)
   - Expecting that the proposed "lib" schema may be postponed
   - Help with spec work is needed!
- @sjn - new metadata
   - @leont will come up with a plan

### NIS2 consultation
- @sjn - finishing work on NIS2 consultation tonight; Deadline Jan 9th

### Eclipse ORC WG
- @sjn - moved org to Github, set up a Slack server for comms.

### CycloneDX 1.7 Sustainability fields
- @sjn - moving forward with the Project needs enumeration; Latest addition: mental health first aider.

### SBOM/Supply Chain
- @sjn - nothing to report

### CPAN Steward org
- @sjn - has plans to explore the creation of a not-for-profit cooperative
    - @leont - I want to help!

### CNA Update
- @stigtsp - all works as planned, small tasks to finish (homework)
   - We're a vulnerability coordinator! 
   - @stigtsp and @timlegge have a little homework to do as the next step
   - Next steps should be known by end of January

### Recruitment
- @sjn - makes CPANSec stickers for FOSDEM
  - T-Shirts/sweaters/hoodies for PTS?

### Perl Toolchain Summit 2025
- @tux - Third wave of voting is open. @tux, @leont, @garu, @stigtsp, and @robrwo are already invited, @sjn, @timlegge, and @thibaultduponchelle are likely to be invited too (as it stands)

### Other
- @sjn - trying to get IRC Notifications working again (pending an issue in…)
- @stigtsp - great experience with cross-distro cooperation at #38c3 in Hamburg.
- @tux will contact author of Kwalitee w.r.t. SECURITY.md, CONTRIBUTING.md
- @tux will suggest something like CVE.SKIP file for [Test::CVE](https://metacpan.org/release/Test-CVE)
- @stigtsp - the metacpan folks are awesome!

### Upcoming events and deadlines
1. [FOSDEM Fringe 2025](https://fosdem.org/2025/fringe/) - Friday January 31st, Brussels
    * Related: [EU Open Source Week](https://opensourceweek.eu/)
1. [FOSDEM 2025](https://fosdem.org/2025/) - 2025-02-(01-02), Brussels - three relevant devrooms!
1. [PTS 2025](https://perltoolchainsummit.org/pts2025/) - Thursday 2025-05-01 … Sunday 2025-05-04 in Leipzig, Germany
1. [gpw2025](https://act.yapc.eu/gpw2025/) - 2025-05-(12-14) in Munich, Germany.


### Operating changes
*   (none)

### Next meeting date, time and location
*   Next meeting is Friday 2025-01-22 (22 Jan 2025) @ 16:00UTC in #cpansec-discussion on Matrix (17:00 Europe/Amsterdam)

## 17:27 UTC – Meeting end

## 17:30  UTC – End
