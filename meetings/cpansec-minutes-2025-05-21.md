---
layout: page
toc: true
meeting_time: 2025-05-21 16:00 UTC
title: CPANSec bi-weekly minutes
---

[TOC]

## Agenda & Meeting Details 2025-05-21
- 2025-05-21 16:00 UTC on #cpansec-discussion on Matrix


## 15:30 UTC - Pre-meeting socializing
-   Socializing & getting up to speed before the meeting starts properly
-   Discuss organizing projects, swimlanes and issues (...)
-   Check and resolve technical (A/V) issues before the meeting starts
-   Come as you are!


## 16:04 UTC - Meeting start


## Welcome
-   Meeting chair: @tux
-   Meeting scribe: @sjn


### Attendees, absents & regrets
-   Attendees
    - @sjn, @toddr, @robrwo, @stigtsp, @haraldjoerg, @tux
-   Partly attending
    - @leont, @thibaultduponchelle
-   Regrets 
    - @timlegge


### Approve previous meeting minutes
-   Previous meeting minutes was approved by @stigtsp and @thibaultduponchelle, and merged by @sjn
-   Note: Agenda & Minutes format is described in the [CPANSec meetings page](https://security.metacpan.org/meetings/#meeting-agendaminutes-format).


## Agenda


### Current matters & Ongoing vulnerabilities

#### XML::LibXML
- [x] @tux - XML::LibXML touches CVE issues in Alien
  - @stigtsp - probably not a CVE for the CPAN module
  - @tux - no maintainer found yet; the issue wasn't in libxml

#### BSON::XS - vulnerable deps
- [x] @stigtsp - CVE created
  - CVE-2025-40906

#### FCGI
- [x] @stigtsp - CVE created
  - CVE-2025-40907

#### CVE details for Debian
- [x] @stigtsp - Mojolicious CVE correction
- [x] @rrwo - posted summary of rand-related issues
- [ ] @timlegge - waiting on CVEs/disclosure for 2? other issues from that batch- 

#### CPAN Modules with vulnerable vendored (bundled/embedded) dependencies
- @robrwo - Ongoing work
  - @tux - Do we have any written down procedures/guidelines for this?
  - @robrwo - No guidelines exist
- @stigtsp - We're following the CVE program rules when assigning CVEs
- [ ] @robrwo - and @briandfoy investigating modules in CPAN::Audit for vulnerabilities
  - @robrwo - help needed!


### Operating changes
- @sjn - Proposal: Add RSS feeds to the matrix channel? Suggestions for channel admins:
   - Mastodon feed: https://fosstodon.org/@cpansec.rss
   - News feed: https://security.metacpan.org/feed.xml
   - CVE announcements feed: @stigtsp - can be done as part of an automated CVE announcement process
   - CVE updates feed: Can hook right into the CVE.org database maybe
- [ ] @stigtsp - good idea! We need a bot.


### [Metadata & Software Bills of Materials](https://github.com/orgs/CPAN-Security/projects/1/views/2)

#### CPAN::Meta::Spec, Requirements and PURLs
- @sjn and @leont discussed at PTS, decided to
  - [ ] @sjn - put together a detailed proposal

#### CycloneDX 1.7 Sustainability fields
- @sjn - Ongoing: project- & ecosystem-supplied status fields.
  - @sjn - interesting discussions around exploring relationships between this spec and LF's security-insights.yml spec

#### Common Lifecycle Enumeration project
- [ ] @sjn - Can we provide a list of lifecycle events that we have encountered?
  - e.g. last project maintainer dies; a project decides to shut down, but disallows adoption (e.g. DBIC); a project reboots with new contributors (e.g. CPAN Testers); a project is adopted, and gets a new maintainer; a project is forked and published under a new name; a project is made "Dual life"; a project is removed from "Dual life" status; A project gets is initial publication; a project releases it's first stable (production-ready) release; Project moved from single maintainer to group, or vice versa; Repository move; etc.
  - [ ] @sjn - organize brain-storming session. who should join?


### [Compliance, Guidance & Standards](https://github.com/orgs/CPAN-Security/projects/9/views/2)

#### CPAN Author's Security Policy Guidelines
- [ ] @stigtsp - Minimal (TLDR) version of policy wanted
   - @stigtsp - example proposal sent to @timlegge
- [ ] @tux - Team document template wanted; Help needed
   - [ ] @timlegge has started on something; happy to discuss with @tux; PR in the works
   - @robrwo - not so much a different kind of doc as possible different way to report vuln
- [ ] @robrwo mini-project to encourage the popular modules to add a security policy
for a list
   - Sounds like a good idea
   - security.md, sbom and valid cpanfile, cpansa and busfactor, cpan.org email
   - cpants has experimental support
   - look into "update your cpan module" month (ref @tux's checklist)
     - @robrwo interpreted this as a "security checklist" which is a bit too broad in scope, and overlaps with secure coding guidelines
       was thinking of a trimmed down metadata/config/documentation security checklist
   - [x] @robrwo contacts manwar to see if he'd like to help with outreach
     - Abandoned
     

### [Security Information & Outreach](https://github.com/orgs/CPAN-Security/projects/12/views/3)
- [ ] @robrwo suggesting a regular blog series
  - blog posts smaller scope than monolithic documents/guides
  - different authors and topics including current news items
  - regular posts can get more attention
  - @sjn - working on blogging support
- @thibaultduponchelle - let's make it easier to post, 
- [ ] @sjn - let's add a new channel for smaller/faster blog posts "Blog posts" that have lower PR quality requirements

#### Recruitment
- [ ] @thibaultduponchelle - inviting @jjatria to join
- [x] @sjn - @haraldjoerg invited, and he showed up. Welcome! :-)

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
    - @stigtsp - 33 CVE identifiers reserved, and 20 published in our database, per now
- @stigtsp - We need more help from others in the triage group:
    - [x] @garu onboarded
    - [ ] Contact @timlegge, @stigtsp - Analysing vulnerabilities
    - [ ] Contact @timlegge, @stigtsp - Integrating CVE process more with triage
- @robrwo - CNA/CPANSec workflow description needed from CVE reservation to disclosure
    - [ ] (Volunteer needed) - Write a guide/workflow doc, including details on how embargos work
    - @sjn - could this be done as a tabletop excercise?
- @stigtsp - guided CVE writeup-sessions at PTS and at regular times otherwise
    - [ ] @stigtsp and @timlegge prepare a dummy scenario
    - [x] @garu got an intro to the CVE process; learned a lot that could be improved
- @stigtsp - Tried to reach out to ENISA (EUVD) now a couple of times to discuss contingency/options, but no answer yet.
- @stigtsp - @garu has emailed a list of old perl CVEs to RH for reassigment to our CNA, pending
- @stigtsp - Can someone look at the cpansa-feed, it's broken for a while now :-(
    - [x] - @garu started looking at this at PTS2025 
    - [ ] - @stigtsp will try to look at this Soon™


### [Secure by Default](https://github.com/orgs/CPAN-Security/projects/15/views/2)

#### TLS/HTTPS/CSPRNG/DSA in core
- [ ] @leont - share ongoings & blockers
   - [ ] @leont - a minimal XS wrapper around libopenssl
   - @toddr - should we explore simpler options, like wrapping libcurl? or even calling `/usr/bin/curl`
      - @toddr - some license issues to be aware of (which is another argument to "Just use curl(1)")


### [Organization, Governance & Funding](https://github.com/orgs/CPAN-Security/projects/7/views/2)

#### Funding drive
- [ ] @sjn - who is open (or willing to commit) to do funded work? (e.g. X days per week)
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

#### Eclipse ORC WG
- @sjn - Misc. ongoing activities FAQ

#### CPAN Steward org
- @sjn - Discussions on TPRF slack #cpansec-steward; Mostly @sjn making noise;
    - Contributors who care about governance needed; Please reach out to @sjn
- [ ] @sjn - Initiate conversation with RedHat re: their thoughts on the Steward role
- @sjn - Do we know anyone who is in contact with ActiveState?
- @sjn - other downstream businesses & entities
  - SuSE - (possible contact: ?)
  - Debian - (possible contact: ilu)
  - ActiveState - (possible contact: Jan Dubois?)
  - etc.
- @sjn - do we need to think about a policy on how to interact with downstream manufacturers and stewards?
  - e.g. require downstream entities to appoint a community liason that we can interact with
  - e.g. 


### [Security Patch Tooling](https://github.com/orgs/CPAN-Security/projects/11/views/2)
- [ ] @thibaultduponchelle - Security Patch Tooling POC
  - [x] @thibaultduponchelle - Implement POC (CPM + Patching + Patches)
  - [ ] @thibaultduponchelle - Demo POC during CPANSec meeting
  - [ ] @thibaultduponchelle - Share POC repo/docs with whole CPANSec group
    - @thibaultduponchelle - demo next time!
- [ ] (Volunteers/tuits/funding needed - this topic is now available for adoption!)
- @tux - @garu is putting together a minimal spec


### PAUSE Pentesting/Hardening
- [x] @thibaultduponchelle @stigtsp @leont @timlegge - Provide fixes to reported issues
  - [x] @thibaultduponchelle - Provide fix to GHSA-6qr9-7rvm-5fj9
  - [x] @thibaultduponchelle - Provide fix to GHSA-fvmw-3mp8-v8q9


### [Authentication & Trusted Publishing](https://github.com/orgs/CPAN-Security/projects/3/views/2)
- [ ] (Volunteers/tuits/funding needed - this topic is available for adoption!)


### [Transparency Logs & Trusted Distribution](https://github.com/orgs/CPAN-Security/projects/2/views/2)
- [ ] (Volunteers/tuits/funding needed - this topic is available for adoption!)


## Any Other Business
- @stigtsp shared some info around security issues in the Mojolicious project
- [ ] @robrwo methods for notifying multiple maintainers of security issues as part of Perl ecosystem (RT or some kind of cpan.org mailing list)


### Upcoming events and deadlines
- [x] (Germany) [GPW 2025](https://act.yapc.eu/gpw2025/) - Monday 2025-05-12 … Wednesday 2025-05-14 in Munich, Germany. ([CfP is open](https://act.yapc.eu/gpw2025/cfp.html))
    - @sjn went. One talk given, and one panel contributed, and one lightening talk performed.
- [ ] (Norway) [Internet Governance Forum 2025](https://www.intgovforum.org/) - Monday 2025-06-23 … Saturday 2025-06-28 in Lillestrøm, Norway; (Registration closes June 1st)
    - @sjn intends to go
- [ ] (USA) [TPRC 2025](https://www.perl.com/article/get-ready-for-the-2025-perl-and-raku-cce/) - Friday 2025-06-27 … Sunday 2025-06-29 in Greenville, SC, USA ([CfP is open](https://www.papercall.io/tprcgsp2025); Deadline: 2025-03-15)
    - @toddr goes
- [ ] (Netherlands) [OpenSSF Community Day Europe](https://events.linuxfoundation.org/openssf-community-day-europe/) - 2025-08-28 - Amsterdam, Netherlands ([CFP is open](https://events.linuxfoundation.org/openssf-community-day-europe/program/cfp/); Deadline Monday 2025-05-26)
- [ ] (Croatia) [EuroBSDCon 2025](https://events.eurobsdcon.org/2025/) - Thursday 2025-09-25 … Sunday 2025-09-28 in Zagreb, Croatia; ([CfP is open](https://events.eurobsdcon.org/2025/cfp); Deadline: 2025-06-21)
- [ ] (Germany) [All Systems Go](https://all-systems-go.io/) - Sept. 30th - Oct. 1st 2025, Berlin ([CfP is open](https://cfp.all-systems-go.io/all-systems-go-2025/cfp); Deadline: 2025-06-13)
- [ ] (Belgium) OpenSSF EU Policy Summit - 2025-10-30, in Ghent, Belgium;
- [ ] (World) [CPAN 30 year anniversary](https://github.com/neilb/history-of-cpan/blob/master/history.md#the-cpan-years) - Sunday 2025-10-26


## Next meeting date, time and location
- Next meeting is Wednesday 2025-06-05 @ 16:00UTC in #cpansec-discussion on Matrix (18:00 Europe/Amsterdam)


## 17:04 UTC - Meeting end


## 18:19 UTC - End
