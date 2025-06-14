---
layout: single
toc: true
meeting_time: August 29th, 2024 16:00 UTC
title: Minutes 2024-08-29
---

## Meeting details

* August 29th, 2024 16:00 UTC on #cpansec-discussion on Matrix

### Welcome

*   Meeting chair: @sjn
*   Meeting secretary: All together

### Attendees, absents & regrets

*   Attendees
    *  @sjn, @timlegge, @stigtsp, @tux

### Approve previous meeting minutes
*   Previous meeting minutes was approved by @tux, @timlegge, @stigtsp

### Quick summary of current work
*   @tux - released DBI. CVE updates might be needed upstream
*   @tux - Ideas about distroprefs to be used for known CVE patches not integrated by maintainers: @tux will create a ticket and a short readme
*   @stigtsp - cpanm (cpanminus) vuln is kind off finished now, major distributions are following up already
*   @tux - Test::CVE is being used!

### Standards of Conduct
*   @sjn - TPRF has changed their SoC, should we follow suit? Discuss & decide.
*   Options are:
    1. https://github.com/tpf/soc/blob/main/Standards_of_Conduct.md
    2. https://openssf.org/community/code-of-conduct/
*   To update the current ticket prior to the next meeting
*   Vote at next meeting

### Vulnerability Index
*   @stigtsp - need to do some considerations on this vs. CNA
*   the CNA requires a public index of CVEs - some OSS projects use github for their index

### TLS/HTTPS in core
*   Neither @leont nor @book where present, so nothing to report

### German Sovereign Tech fund is open for applications
*   @sjn - We need volunteers to deal with this; No movement forward

### Ongoing vulnerabilities
*   @stigtsp - nothing public

### Secure by Default
*   @stigtsp - some thinking ongoing
*   @sjn - CPANSec BoF at LPW, with this on the agenda. Topic for exploration:
    * Balance between security and backwards compatibility
    * Deprecation of insecure services and tooling
    * Funding

### Eclipse ORC WG
*   @sjn - Formal start soon; FAQ gathering started
*   @sjn - meeting w/EU Commission next week

### CycloneDX 1.7 Sustainability fields
*   @sjn - CycloneDX Sustainability WG first meeting started. 
*   @sjn - Looking for anyone in the CPAN/Perl/Raku ecosystems who care about Sustainability - please reach out!
*   @sjn - @sjn's personal notes are on the [CPANSec website](https://github.com/CPAN-Security/security.metacpan.org/blob/lifecycle/docs/foss-project-lifecycle.md)
*   Started, first meeting was last week, another next week
*   @sjn stopped by the chaoss

### CPAN Meta Requirements
*   @sjn - No progress on [issue #40](https://github.com/Perl-Toolchain-Gang/CPAN-Meta-Requirements/issues/40) due to lacking tuits

### Package identification (PURLs)
*   @sjn - ECMA TC54-TG2 (Package URL) standardization work starting soon

### SBOM/Supply Chain
*   @sjn - Ongoing work

### CNA Update
*   @timlegge - only updated the CNA disclosure policy
*   Disclosure https://cryptpad.fr/code/#/2/code/edit/w1A57hRtvBXHjLSLwWzDc4v9/
*   Creating a CVE - https://cryptpad.fr/code/#/2/code/edit/qxOxnd6Tk9BS-w-eNMYYbpEj/
*   @timlegge to move this information to the github
*   missing some information on what to do when a CVE has been addressed

### Github Project issues

We're looking at [issues in the different projects](https://github.com/orgs/CPAN-Security/projects?query=sort:title-asc)

1. CPANSec Governance
    * 4 issues moved to Stalled
1. CPAN Vulnerability Index
    * 1 issues moved to Stalled
1. Supplychain Security
    * @stigtsp - obvious problems have been prioritized. TUF and Sigstore issues are postponed
1. CPAN Secure by Default
    * Our part of the cpanm secure by default is done

We continue with this list next meeting!

### Upcoming events and deadlines

1. [PostgreSQL Lowlands 2024 NL](https://kangaroot.net/events/pg-day-lowlands-2024-nl) - Fri 13 Sep 2024 - @tux will join
1. [Open Source Summit Europe](https://events.linuxfoundation.org/open-source-summit-europe/) in Vienna, Austria - September 16-18 + 19-20 - Lots of people from OpenSSF + SBOM + Supply chain security communities - @sjn is going
1. [All Systems Go](https://all-systems-go.io/) - Sept. 25-26th, Berlin
1. [London Perl Workshop](https://act.yapc.eu/lpw2024/) - Saturday 26th October 2024 - @sjn got his talk [accepted](http://act.yapc.eu/lpw2024/talk/7915), @tux got his LT [accepted](https://act.yapc.eu/lpw2024/talk/7922)

### Operating changes
*   Try finding ways to make it easier to attend the meetings (like not forgetting there is one)
*   @timlegge will look at setting up a sharable calendar
*   Skip electing next meeting chair/secretary from now on

~~### Elect next meeting chair and secretary~~
*   ~~Chair: #TBD~~
*   ~~Secretary: #TBD~~

### Next meeting date, time and location
*   Next meeting is 2024-09-12 (12th Sep) @ 17:00UTC (18:00 Amsterdam) in #cpansec-discussion on Matrix
