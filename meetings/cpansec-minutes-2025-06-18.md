---
layout: page
toc: true
meeting_time: 2025-06-18 16:00 UTC
title: CPANSec bi-weekly minutes
---

[TOC]

## Agenda & Meeting Details 2025-06-18
- 2025-06-18 16:00 UTC on #cpansec-discussion on Matrix


## 15:40 UTC - Pre-meeting socializing
-   Socializing & getting up to speed before the meeting starts properly
-   Discuss organizing projects, swimlanes and issues (...)
-   Check and resolve technical (A/V) issues before the meeting starts
-   Come as you are!


## 16:08 UTC - Meeting start


## Welcome
-   Meeting chair: @stigtsp
-   Meeting scribe: @sjn


### Attendees, absents & regrets
-   Attendees
    - @sjn, @robrwo, stigtsp, @haraldjoerg
-   Partly attending
    - …
-   Regrets 
    - @thibaultduponchelle, @leont


### Approve previous meeting minutes
-   Previous meeting minutes was approved by @robrwo and @thibaultduponchelle, and merged by @sjn
-   Note: Agenda & Minutes format is described in the [CPANSec meetings page](https://security.metacpan.org/meetings/#meeting-agendaminutes-format).


## Agenda


### Current matters & Ongoing vulnerabilities

#### CPAN Modules with vulnerable vendored (bundled/embedded) dependencies
- [ ] @robrwo - and @briandfoy investigating modules in CPAN::Audit for vulnerabilities
- [ ] @robrwo started documenting embedded dependencies for cpan-security-advisory repo
  - Brian's cpan-audit - some incomplete info - filling in the blanks and logging issues as found
    - @stigtsp - can we simplify somehow the info to help downstream users of our data?
    - @robrwo - let's start with keeping track of modules who have embedded/phantom deps
    - @sjn - this can be solved by embedding an SBOM, let's discuss
  - libtomcrypt - and others seem to use commit id which makes it more work to track
  - [ ] @robrwo started adding issues to CNA
    - The downstream projects seem to pick things up quickly
  - [ ] @robrwo: Brian is unhappy that CNA assigns separate CVE for embedded vulns, but that is standard policy. 
    - Unsure if this will cause a conflict with data where dists have multiple CVEs for same issue. 
    - CPAN::Audit::DB is now flagging embedded issues that authors might not be aware of too.
  - @stigsp referred @robrwo (via Matrix) to look at https://salsa.debian.org/security-tracker-team/security-tracker/-/blob/master/data/embedded-code-copies    

#### CPAN Modules review
- [ ] @stigtsp - Encrypted module on CPAN - the author removed the encryption in the new version
  - CPANSec recommends an update to the PAUSE rules to prohibit: 1. encrypted modules, 2. malware, 3. undocumented "phone home" etc.
  - [ ] @robrwo puts together a proposal for PAUSE rules - review other ecosystems
    - https://github.com/andk/pause/issues/569
    - little progress


### Operating changes
- @sjn - Proposal: Add RSS feeds to the matrix channel? Suggestions for channel admins:
   - [ ] @stigtsp - CVE announcements feed: @stigtsp - can be done as part of an automated CVE announcement process - @stigtsp is looking at this.
     - no progress
   - [ ] @stigtsp - CVE updates feed: Can hook right into the CVE.org database maybe
     - no progress
- @robrwo/@stigtsp/@timlegge We need a place to post patches when CVEs are published
   - add a "/patches" section to security.metacpan.org website or a separate repo?
     - especially for cases when authors do not release fixes
     - we want consistent patches to be used
     - it should work with Security Patch Tooling
- @stigtsp - we may need to be careful about mixing triage and CVE processes
  - mixing may reveal some conflicts of interest; let's think about this
  - [ ] @stigtsp - investigates (maybe with @timlegge & @thibaultduponchelle?)


### [Security Patch Tooling](https://github.com/orgs/CPAN-Security/projects/11/views/2)
- [x] PoC done by @thibaultduponchelle
- [ ] (Volunteers/tuits/funding needed - this topic is now available for adoption!)
- [ ] @tux - @garu is putting together a minimal spec
- [x] @tux waits for @garu to finish the new format for be digested by Test::CVE - Checked, ✔ Works again!


### [Metadata & Software Bills of Materials](https://github.com/orgs/CPAN-Security/projects/1/views/2)

#### CPAN::Meta::Spec, Requirements and PURLs
- @sjn and @leont discussed at PTS, decided to
  - [ ] @sjn - put together a detailed proposal
  - no update

#### CycloneDX 1.7 Sustainability fields
- @sjn - Ongoing: project- & ecosystem-supplied status fields.
  - @sjn - interesting discussions around exploring relationships between this spec and LF's security-insights.yml spec
  - no update


### [Compliance, Guidance & Standards](https://github.com/orgs/CPAN-Security/projects/9/views/2)

#### CPAN Author's Security Policy Guidelines
- [ ] @stigtsp - Minimal (TLDR) version of policy wanted
   - @stigtsp - example proposal sent to @timlegge
   - no update
- [ ] @tux - Team document template wanted; Help needed
   - [ ] @timlegge has started on something; happy to discuss with @tux; PR in the works
   - @robrwo - not so much a different kind of doc as possible different way to report vuln
  - no update
- [ ] @robrwo mini-project to encourage the popular modules to add a security policy for a list
   - Sounds like a good idea
   - security.md, sbom and valid cpanfile, cpansa and busfactor, cpan.org email
   - cpants has experimental support
   - look into "update your cpan module" month (ref @tux's checklist)
     - @robrwo interpreted this as a "security checklist" which is a bit too broad in scope, and overlaps with secure coding guidelines.
     - @robrwo was thinking of a trimmed down metadata/config/documentation security checklist
- [ ] @sjn mentioned RFC 2350 to @robrwo but @robrwo unsure how this fits in w/security policy has not looked at it in detail


### [Security Information & Outreach](https://github.com/orgs/CPAN-Security/projects/12/views/3)
- [ ] @robrwo suggesting a regular blog series
  - blog posts smaller scope than monolithic documents/guides
  - different authors and topics including current news items
  - regular posts can get more attention
  - @sjn - working on blogging support
- @thibaultduponchelle - let's make it easier to post, 
- [ ] @sjn - let's add a new channel for smaller/faster blog posts "Blog posts" that have lower PR quality requirements
  - @sjn working on new templates for website to make this happen
    - still ongoing work
- [ ] @robrwo compiling list of popular modules that need security policies
  - ongoing, but it looks like almost all of them
- [ ] @stigtsp - write 2-3 articles about why using `rand()` is bad
  - [ ] working on two examples on how to attack `rand()`
    - GPU brute force attacks, and …
    - `rand()` rainbow tables ("randbow")
    - what does "don't roll your own crypto" actually _mean_? (this includes "clever" use of `rand()`!)
    - there are also some more clever (mathematical) attacks to be aware of

#### Recruitment

#### New Guide needed: PackageURL
- [ ] @sjn - We need a comprehensive PackageURL guide that answers/covers all relevant use cases
    - Non-perl project uses perl executable provided by packaging system // plenv // build-perl // ActiveState // etc.
    - Non-perl project uses a tool provided on CPAN
    - Non-perl project uses a vendored/included tool written in Perl
    - Perl project not on CPAN uses a CPAN module found on CPAN
    - Perl project found on CPAN uses a CPAN module found on CPAN
    - Perl project not found on CPAN uses a CPAN module not found on CPAN, but a DarkPAN
    - etc.
- @sjn - No progress


### [CNA & Vulnerability Index](https://github.com/orgs/CPAN-Security/projects/10/views/2)

#### CNA Organization
- @stigtsp, @timlegge - Presentation of CNA work so far
    - @stigtsp - 26 CVE identifiers reserved, and 30 published in our database, per now
- @stigtsp - We need more help from others in the triage group:
    - [ ] Contact @timlegge, @stigtsp - Integrating CVE process more with triage
- [ ] @robrwo - CNA/CPANSec workflow description needed from CVE reservation to disclosure
    - [ ] (Volunteer needed) - Write a guide/workflow doc, including details on how embargos work
    - @sjn - could this be turned into a tabletop excercise?
- [ ] @stigtsp - guided CVE writeup-sessions at PTS and at regular times otherwise
    - @stigtsp and @timlegge prepare a dummy scenario
- [x] @garu has emailed a list of old perl CVEs to RH for reassigment to our CNA, pending
    - mitre declined
- [ ] @stigtsp - Can someone look at the cpansa-feed, it's broken for a while now :-(
    - @stigtsp will try to look at this Soon™
- @robrwo asked on Matrix about ways to track issues to triage/research before CVEs
- [x] @stigtsp - Raised issue about unbounded max versions to the OSS CNA Forum
- [ ] @robrwo - we need a kanban to track vulnerability workflow
    - @sjn tries to make it happen; @stigtsp assists w/workflow
- [ ] @stigtsp has also re-raised an issue re: adoption of CVEs
    - issue has been promoted to the CVE board


### [Secure by Default](https://github.com/orgs/CPAN-Security/projects/15/views/2)

#### TLS/HTTPS/CSPRNG/DSA in core
- [ ] @leont - share ongoings & blockers
   - [ ] @leont - a minimal XS wrapper around libopenssl
   - @toddr - should we explore simpler options, like wrapping libcurl? or even calling `/usr/bin/curl`
      - @toddr - some license issues to be aware of (which is another argument to "Just use curl(1)")
 - no update since PTS

### [Organization, Governance & Funding](https://github.com/orgs/CPAN-Security/projects/7/views/2)

#### Funding drive
- @sjn - who is open (or willing to commit) to do funded work? (e.g. X days per week)
    - [x] @stigtsp 1d/w
    - [x] @robrwo 0d/w
    - [x] @leont 1d/w
    - [x] @garu 1d/w
    - [ ] @ferki (contact @sjn!)
    - [ ] @stevan (? - please contact @sjn - lead supplied by @mickeyn)
    - [ ] Others? (contact @sjn!)
- [ ] @sjn - Explore options with Ovid's company
- [ ] @sjn - Talk with prospective companies to look for opportunities
- [ ] @sjn - Organize fundraiser's coordinator meeting w/Olaf & Stuart (delayed)
- [ ] @sjn - Investigate pre-project funding chances with NUUG foundation
- [ ] @sjn - New project overview in the works: https://cryptpad.fr/sheet/#/2/sheet/edit/vazHpOmoK6bM-qKo7WRpzq6U/
- @sjn to meet with Alpha-Omega today

#### Eclipse ORC WG
- @sjn - No updates

#### CPAN Steward org
- @sjn - Discussions on TPRF slack #cpansec-steward; Mostly @sjn making noise;
    - Contributors who care about governance needed; Please reach out to @sjn
- [ ] @sjn - Initiate conversation with RedHat re: their thoughts on the Steward role
- @sjn - Do we know anyone who is in contact with ActiveState?
- @sjn - other downstream businesses & entities
  - SuSE - (possible contact: ?)
  - Debian - (possible contact: ilu)
  - ActiveState - (possible contact: Jan Dubois?)
  - Red Hat - ?
  - etc.
- @sjn - do we need to think about a policy on how to interact with downstream manufacturers and stewards?
  - e.g. require downstream entities to appoint a community liason that we can interact with
- has notes on the requirments from a comercial point of view - but focus on getting government support


### [Authentication & Trusted Publishing](https://github.com/orgs/CPAN-Security/projects/3/views/2)
- [ ] (Volunteers/tuits/funding needed - this topic is available for adoption!)


### [Transparency Logs & Trusted Distribution](https://github.com/orgs/CPAN-Security/projects/2/views/2)
- [ ] (Volunteers/tuits/funding needed - this topic is available for adoption!)


## Any Other Business
- [ ] @robrwo methods for notifying multiple maintainers of security issues as part of Perl ecosystem (RT or some kind of cpan.org mailing list)
  - @robrwo - no movement on this; no response from RT
  - @robrwo - GitHub has something in this regard
  - @stigtsp - a separate list for notification to vendors is also needed
  - [ ] @toddr can help find out if this is a feature that can be enabled in RT via the TPRF deal

### Upcoming events and deadlines
- [ ] (Norway) [Internet Governance Forum 2025](https://www.intgovforum.org/) - Monday 2025-06-23 … Saturday 2025-06-28 in Lillestrøm, Norway; (Registration closes June 8th)
    - @sjn is confirmed to go
- [ ] (USA) [TPRC 2025](https://www.perl.com/article/get-ready-for-the-2025-perl-and-raku-cce/) - Friday 2025-06-27 … Sunday 2025-06-29 in Greenville, SC, USA (CfP is closed)
    - @toddr goes
- [ ] (Netherlands) [OpenSSF Community Day Europe](https://events.linuxfoundation.org/openssf-community-day-europe/) - 2025-08-28 - Amsterdam, Netherlands (CfP is closed)
- [ ] (Croatia) [EuroBSDCon 2025](https://events.eurobsdcon.org/2025/) - Thursday 2025-09-25 … Sunday 2025-09-28 in Zagreb, Croatia; ([CfP is open](https://events.eurobsdcon.org/2025/cfp); Deadline: 2025-06-21)
    - @stigtsp is going
- [ ] (Germany) [All Systems Go](https://all-systems-go.io/) - Tuesday 2025-09-30 … Wednesday 2025-10-01 2025, Berlin ([CfP is open](https://cfp.all-systems-go.io/all-systems-go-2025/cfp); Deadline: 2025-06-13)
- [ ] (Sweden) [Nordic Software Security Summit](https://nsss.se) - Thursday 2025-10-02 … Friday 2025-10-03 in Stockholm
- [ ] ~~(Belgium) OpenSSF EU Policy Summit - 2025-10-30, in Ghent (Not confirmed)~~
- [ ] (World) [CPAN 30 year anniversary](https://github.com/neilb/history-of-cpan/blob/master/history.md#the-cpan-years) - Sunday 2025-10-26
- [ ] (USA) [Open Source Security Con](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/co-located-events/open-source-securitycon/) - Monday 2025-11-10, Atlanta, Georgia ([CfP is open](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/co-located-events/cfp-colocated-events/) until 2025-06-30)

## Next meeting date, time and location
- Next meeting is Wednesday 2025-07-02 @ 16:00UTC in #cpansec-discussion on Matrix (18:00 Europe/Amsterdam)


## 17:14 UTC - Meeting end


## 18:15 UTC - End
