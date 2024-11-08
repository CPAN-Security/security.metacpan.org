---
layout: page
toc: true
meeting_time: 2024-10-30 16:00 UTC
title: Minutes 2024-10-30
---

## Meeting details

* 2024-10-30 16:00 UTC on #cpansec-discussion on Matrix

## 16:10 UTC – Meeting start

### Welcome

*   Meeting chair: @timlegge
*   Meeting secretary: @sjn

### Attendees, absents & regrets

*   Attendees
    * @timlegge
    * @sjn
    * @tux
    * @stigtsp
    * @garu

### Approve previous meeting minutes

*   Previous meeting minutes was approved by @sjn, @timlegge

### Quick summary of current work

1.  [CPAN Metadata & Software Bills of Materials](https://github.com/orgs/CPAN-Security/projects/1)
    *   stalled
2.  [CPAN Privacy and Compliance](https://github.com/orgs/CPAN-Security/projects/9)
    *   stalled
3.  [CPAN Provenance & Supply Chain Security](https://github.com/orgs/CPAN-Security/projects/3)
    *   nothing to do
4.  [CPAN Security Outreach & Information](https://github.com/orgs/CPAN-Security/projects/12)
    *   @stigtsp took over the active ticket
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

### TLS/HTTPS in core
*   @timlegge - Intends to join next PSC meeting to check progress
*   @stigtsp - how will certs be handled? Also, let's get cryptographic primitives and secure RNG into core at the same time. @stigtsp will create tickets on https://github.com/Perl/perl5/issues (with optional help from @tux)


### German Sovereign Tech fund
*   @garu applied for funding! Let's hope this goes well. @oalders too!
*   @garu and @sjn to create a roadmap for SBOM implementation
*   @garu also interested in adding cpansa to OSV

### Ongoing vulnerabilities
*   @stigtsp - investigating one possible upcoming issue

### Secure by Default
*   @stigtsp - not much movement; PRs and updates to current efforts (cpanm and mojo) have been submitted; We're hoping for their maintainers to resolve the issues raised in these.
*   @garu - Let's remember to update relevant CVE's and issue recommendations for tooling use.
*   @charsbar is working on MFA for PAUSE! We wish him success in his work.

### Eclipse ORC WG
*   @sjn - Almost no progress in the WG. Exploring options.

### Perl Toolchain Summit 2025
*   @garu - invitations have begun
*   @stigtsp, @sjn - looking for new candidates to invite: Rob would be a good candidate
*   @tux (first wave) will put @stigtsp, @sjn, and @timlegge on the invite list for the second wave

### CycloneDX 1.7 Sustainability fields
*   @sjn - ongoing

### CPAN Meta Requirements and PURLs
*   @sjn - stalled

### POSIX::2008 vulnerabilities
*   @stigtsp - No movement. Need to create CVEs for https://github.com/briandfoy/cpan-security-advisory/blob/master/cpansa/CPANSA-POSIX-2008.yml

### SBOM/Supply Chain
*   @sjn - Talked about metadata at LPW; Slides published; Talk expected to repeated at NUUG meeting November, and possibly at FOSDEM.
*   @stigtsp - happy with sjn's talk!

### CNA Update
*   @timlegge Review information to be submitted for CNA
    * https://cryptpad.fr/sheet/#/2/sheet/edit/trimcHA8T3+Q3c1Sj9Cnz1LA/
    * See also current PRs
*   @timlegge - Missing data:
    * Finalize and merge disclosure text
    * Public POC for CVE Website at cve.org. Requested contact address: cna@perl.org
    * Advisory Location; TODO: likely a git repo or mailing list

### Recruitment
*   @tux - @rrwo, @jjatria, @tib were positive

### CPANSA feed
*   @garu - old feed fixed, new feed underway.
*   @garu - looking into exporting to a more recent [OSV](https://osv.dev) format
*   @sjn - is OpenVEX useful for this?
*   @garu - reviewing workflow process

### Other
*   @stigtsp - invite Kairo to talk about rsTUF at next meeting

### Upcoming events and deadlines
1. [Norwegian Unix Users Group](https://nuug.no), Monthly meeting 2024-11-12, Oslo, Norway - @sjn gives his metadata/supply chain talk again
1. [FOSDEM Fringe 2025](https://fosdem.org/2025/fringe/) - Friday January 31st, Brussels
1. [FOSDEM 2025](https://fosdem.org/2025/) - February 1-2, Brussels - three devrooms!
1. [PTS 2025](https://perltoolchainsummit.org/pts2025/) - Most likely date: last weekend of April or first week of May

### Operating changes
*   @sjn - Is 17:00 a better meeting time post-DST? – no

### Next meeting date, time and location
*   Next meeting is Friday 2024-11-15 (15 Nov 2024) @ 16:00 UTC in #cpansec-discussion on Matrix (17:00 Europe/Amsterdam)

## 17:30 UTC – Meeting end

## 17:30 UTC – End
