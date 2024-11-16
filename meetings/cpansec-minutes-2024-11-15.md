---
layout: page
toc: true
meeting_time: 2024-11-15 16:00 UTC
title: Minutes 2024-11-15
---

## Meeting details

* 2024-11-15 16:08 UTC on #cpansec-discussion on Matrix

## 15:30 UTC – Pre-meeting socializing

*   Socializing & getting up to speed before the meeting starts properly
*   Discuss organizing projects, swimlanes and issues (...)

## 16:00 UTC – Meeting start

### Welcome

*   @thibaultduponchelle joined :)
*   Meeting chair: @timlegge
*   Meeting secretary: @sjn & @tux

### Attendees, absents & regrets

*   Attendees
    * @sjn, @stigtsp, @tux, @thibaultduponchelle, @timlegge
*   Regrets
    * @robrwo

### Approve previous meeting minutes

*   Previous meeting minutes was approved by @sjn, @timlegge, @tux, @garu

### Quick summary of current work (Grouped by project)

1.  [CPAN Metadata & Software Bills of Materials](https://github.com/orgs/CPAN-Security/projects/1)
    *   stalled
2.  [CPAN Privacy and Compliance](https://github.com/orgs/CPAN-Security/projects/9)
    *   stalled
3.  [CPAN Provenance & Supply Chain Security](https://github.com/orgs/CPAN-Security/projects/3)
    *   nothing to do
4.  [CPAN Security Outreach & Information](https://github.com/orgs/CPAN-Security/projects/12)
    *   @stigtsp took over the active ticket
    *   @tux will write some introduction to the use/need of Test::CVE, @timlegge will review
5.  [CPAN Security Patch Tooling](https://github.com/orgs/CPAN-Security/projects/11)
    *   @sjn - using distroprefs as a model for this has come up recently. shall we move forward?
    *   @thibaultduponchelle will look into distroprefs support for cpanm and friends
6.  [CPAN Software Composition Analysis](https://github.com/orgs/CPAN-Security/projects/6)
    *   @thibaultduponchelle takes one of the tickets
7.  [CPAN Transparency Logs](https://github.com/orgs/CPAN-Security/projects/2)
    *   …
8.  [CPAN Vulnerability Index](https://github.com/orgs/CPAN-Security/projects/10)
    *   …
9.  [CPANSec Governance, Policy & Funding](https://github.com/orgs/CPAN-Security/projects/7)
    *   …


### TLS/HTTPS/CSPRNG/DSA in core
*   @robrwo, @stigtsp - CSPRNG and DSA should be in-scope (they suggest and hope)
*   @timlegge - @leont has had progress
    * @leont and @timlegge met with PSC
    * Current proposal is to 
        * Create a new wrapper module in core
        * Add cleaned up fork of Net::SSLeay and IO::Socket::SSL core modules
    * @leont published a new module: Crypt::Bear
*   @stigtsp - how are we handling the CA cert package in core?
    * @timlegge - Current plan is to use the system CA store (with override possible)
*   @thibaultduponchelle - some work ongoing RNG in CORE; much discussion;
    * Discussion also twirls around how secure the RNG is w.r.t the usage environment (gaming, encryption, …)

### German Sovereign Tech fund
*   @sjn - no work done; no response re: @garu's application

### Ongoing vulnerabilities
*   @stigtsp - Critical PAUSE vuln fixed quickly by andk https://github.com/andk/pause/security/advisories/GHSA-3j5w-wmwq-p6cw
*   @stigtsp - No movement around Mojo's secure token/secrets issues; Volunteers needed
*   @stigtsp - One more vuln known, needs a volunteer; @timlegge may take a look

### Secure by Default
*   @stigtsp - HTTP::Tiny 0.090 merged into Perl CORE, using system cacerts instead of Mozilla::CA

### CPAN Author's Security Policy Template/Guidelines
*   @robrwo - working on initial draft

### Eclipse ORC WG
*   @sjn - Nothing to report
*   @sjn - NIS2 implementing act hearing ongoing; @sjn is contributing

### Perl Toolchain Summit 2025
*   Date still is not set.  Negotiations are still ongoing

### CycloneDX 1.7 Sustainability fields
*   @sjn - ongoing; currently working on a taxonomy of non-funding support

### CPAN Meta Requirements and PURLs
*   @sjn - recent work has been in preparation of an update on this

### POSIX::2008 vulnerabilities
*   No news.

### SBOM/Supply Chain
*   @sjn - minor tweaks; working on connecting fields with metadata sources

### CNA Update
*   @timlegge - New mailing lists infrastructure set up via "simplelists.com"
*   @stigtsp - three volunteers; courses with Mitre upcoming; good progress in preparations.

### Recruitment
*   New members! Thibault Duponchelle (tib, @thibaultduponchelle) and Robert Rothenberg (rrwo, @robrwo)

### CPANSA feed
*   Working again

### Other
*   Discussion about a matrix of security-related items for CPAN releases

### Upcoming events and deadlines
1. [Norwegian Unix Users Group](https://nuug.no), Monthly meeting 2024-11-12, Oslo, Norway - @sjn gave a talk (in Norwegian). Slides and link to video published
1. [FOSDEM Fringe 2025](https://fosdem.org/2025/fringe/) - Friday January 31st, Brussels
    * Related: [EU Open Source Week](https://opensourceweek.eu/)
1. [FOSDEM 2025](https://fosdem.org/2025/) - February 1-2, Brussels - three relevant devrooms!
1. [PTS 2025](https://perltoolchainsummit.org/pts2025/) - Most likely date: first week of May

### Operating changes
*   (none)

### Next meeting date, time and location
*   Next meeting is Friday 2024-11-28 (28 Nov 2024) @ 16:00UTC in #cpansec-discussion on Matrix (17:00 Europe/Amsterdam)

## 17:20 UTC – Meeting end

## 17:20 UTC – End
