---
layout: page
toc: true
meeting_time: August 15th, 2024 16:00 UTC
title: Minutes 2024-08-15
---

## Meeting details

* August 15th, 2024 16:00 UTC on #cpansec-discussion on Matrix

### Welcome

*   Meeting chair: @timlegge
*   Meeting secretary: @sjn

### Attendees, absents & regrets

*   Attendees
    *  @sjn
    *  @stigtsp
    *  @tux
    *  @timlegge

### Approve previous meeting minutes

*   Previous meeting minutes was approved by @sjn, @tux and @timlegge

### Quick summary of current work
*   0.0.0.0 issue for chrome. https://vulcan.io/blog/0-0-0-0-day
*   @stigtsp - Could be worth checking CPAN modules for similar issues (Net:: namespace, etc.)
*   @stigtsp has made an unauthorized test release (on github) of `cpanminus` containing https patches from @garu and @atoomic for consideration in perl docker images
*   @tux and @timlegge are looking into getting access to more uncommon OS's and architectures for testing, please reach out if you can help!
*   @tux looks into giving @stigtsp access to some testing infrastructure for Perl.

### DBI security fixes
*   @tux is the new maintainer of DBI
*   Working on backlog of issues and CVEs/Vulnerabilities
*   CVE-2014-10401

### TLS/HTTPS in core
*   no news

### German Sovereign Tech fund is open for applications
*   @sjn - no progress

### Ongoing vulnerabilities
*   @stigtsp - POSIX::2008 no news

### Secure by Default
*   @stigtsp - no news

### Eclipse ORC WG
*   @sjn - ongoing conversations about OSS Stewards, though slow due to summer. Restart primo September.

### CycloneDX 1.7 Sustainability fields
*   @sjn has had progress around the CycloneDX SBOMs with project sustainability metadata. The #oss-sustainability project for CycloneDX 1.7 officially starts next week!

### CPAN Meta Requirements and PURLs
*   @sjn - no progress

### SBOM/Supply Chain
*   @sjn - misc updates ongoing

### CNA Update
*   @timlegge - Opened Disclosure https://cryptpad.fr/code/#/2/code/edit/w1A57hRtvBXHjLSLwWzDc4v9/ again - no progress
*   @timlegge - Still need to reach out to Stuart regarding what exactly the CNA would need to be successful

### Next meeting's agenda
*   Decide on a Standards of Conduct again

### Upcoming events and deadlines

1. [Open Source Summit Europe](https://events.linuxfoundation.org/open-source-summit-europe/) in Vienna, Austria - September 16-18 + 19-20 - Lots of people from OpenSSF + SBOM + Supply chain security communities - @sjn participates
1. [London Perl Workshop](https://act.yapc.eu/lpw2024/) - Saturday 26th October 2024 - @sjn and @leont has submitted talks

### Github Project issues

1. CPANSec Governance
    * 4 issues moved to Stalled
    * next meeting Decide for a Standards of Conduct
1. CPAN Vulnerability Index
    * 1 issues moved to Stalled
    * @stigtsp - need to do some considerations on this vs. CNA
1. Supplychain Security
    * No tickets exist!
    * @stigtsp - obvious problems have been prioritized. TUF and Sigstore issues are postponed
    * @timlegge added one task for research

We continue with this list in the next meeting!

### Operating changes
*   no operating changes

### Elect next meeting chair and secretary
*   Chair: #TBD
*   Secretary: #TBD

### Next meeting date, time and location
*   Next meeting is 29-08-2024 (29th Aug) @ 16:00UTC in #cpansec-discussion on Matrix
