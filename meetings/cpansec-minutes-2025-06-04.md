---
layout: page
toc: true
meeting_time: 2025-06-04 16:00 UTC
title: CPANSec bi-weekly minutes
---

## Agenda & Meeting Details 2025-06-04
- 2025-06-04 16:00 UTC on #cpansec-discussion on Matrix


## 15:30 UTC - Pre-meeting socializing
-   Socializing & getting up to speed before the meeting starts properly
-   Discuss organizing projects, swimlanes and issues (...)
-   Check and resolve technical (A/V) issues before the meeting starts
-   Come as you are!


## 16:04 UTC - Meeting start


## Welcome
-   Meeting chair: @sjn
-   Meeting scribe: @timlegge


### Attendees, absents & regrets
-   Attendees
    - @sjn, @thibaultduponchelle, @tux, @jjatria, @stigtsp, @timlegge
-   Partly attending
    - @robrwo, @toddr
-   Regrets 
    - …


### Approve previous meeting minutes
-   Previous meeting minutes was approved by @stigtsp and @thibaultduponchelle, and merged by @sjn
-   Note: Agenda & Minutes format is described in the [CPANSec meetings page](https://security.metacpan.org/meetings/#meeting-agendaminutes-format).


## Agenda


### Current matters & Ongoing vulnerabilities

#### CPAN Modules with vulnerable vendored (bundled/embedded) dependencies
- @stigtsp - We're following the CVE program rules when assigning CVEs
  - [ ] @robrwo - and @briandfoy investigating modules in CPAN::Audit for vulnerabilities
  - [ ] @robrwo - Ongoing work
  - @stigtsp - interesting to see that downstream reacts quickly
- @robrwo started documenting embedded dependencies for cpan-security-advisory repo
  - Brian's cpan-audit - some incomplete info - filling in the blanks and logging issues as found
  - libtomcrypt - and others seem to use commit id which makes it more work to track
  - @robrwo started adding issues to CNA
  - The downstream projects seem to pick things up quickly

#### CPAN Modules review
- [x] @thibaultduponchelle - Reviewing Filter::Crypto and public CPAN module using it
  - [x] @thibaultduponchelle @giterlizzi - Investigated functioning of Filter::Crypto
  - Encrypted module on CPAN - the author removed the encryption in the new version
  - cpansec recommends an update to the PAUSE rules to prohibit: 1. encrypted modules, 2. malware, 3. undocumented "phone home" etc.
    - [ ] @robrwo puts together a proposal for PAUSE rules - review other ecosystems
  - [x] @stigtsp & @robrwo - Contacted author of a CPAN module and PAUSE admins - action taken
  - [x] @thibaultduponchelle @robrwo and group - Agreed on policy - "Indecipherable blobs should not be allowed to be part of public CPAN upload"
  - [x] @sjn - Only one consumer of Filter::Crypto - now 0 (as of 4 June 2025)
- [x] Net::CIDR::Set taken over by @robrwo and patch submitted


#### PAUSE pen-testing
- [x] @stigstp @timlegge @leont @thibaultduponchelle - Addressed 2 weaknesses in PAUSE
  - [x] @thibaultduponchelle (+ help/review by others) - 2 fixes provided (privately) to PAUSE admins

### Operating changes
- @sjn - Proposal: Add RSS feeds to the matrix channel? Suggestions for channel admins:
   - [x] @sjn - Mastodon feed: https://fosstodon.org/@cpansec.rss
   - [x] @sjn - News feed: https://security.metacpan.org/feed.xml
   - [ ] @stigtsp - CVE announcements feed: @stigtsp - can be done as part of an automated CVE announcement process - @stigtsp is looking at this.
   - [ ] @stigtsp - CVE updates feed: Can hook right into the CVE.org database maybe
   - this would be useful as well
- [x] @stigtsp - good idea! We need a bot.
   - @sjn got access to add an RSS bot subscribed to the above feeds.
- @stigtsp, discussing merging CNA work more with cpan-security/triage, to avoid unhelpful barriers
   - Working on improving the processes

- The mastodon feed is slow (not busy) ask @sjn if you would like access
- [x] if @tux has time he will look at registering a bluesky account

### [Security Patch Tooling](https://github.com/orgs/CPAN-Security/projects/11/views/2)
- [x] @thibaultduponchelle - Security Patch Tooling POC
  - [x] @thibaultduponchelle - Demo POC during CPANSec meeting
  - [x] @thibaultduponchelle - Share POC repo/docs with whole CPANSec group
    - @thibaultduponchelle - presented a demo
      - Uses CPAN::Patches
      - Would like to use CPAN::Distropref
      - Should use common patches across modules, cpan tools and distributions
      - CPAN::Distropref is very flexiple in matching modules to apply
      - CPAN::Patches matches only one version
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
   - security.md, SBOM and valid cpanfile, cpansa and bus factor, cpan.org email
   - CPANTS has experimental support
   - look into "update your cpan module" month (ref @tux's checklist)
     - @robrwo interpreted this as a "security checklist" which is a bit too broad in scope, and overlaps with secure coding guidelines.
     - @robrwo was thinking of a trimmed down metadata/config/documentation security checklist


### [Security Information & Outreach](https://github.com/orgs/CPAN-Security/projects/12/views/3)
- [ ] @robrwo suggesting a regular blog series
  - blog posts smaller scope than monolithic documents/guides
  - different authors and topics including current news items
  - regular posts can get more attention
  - @sjn - working on blogging support
- @thibaultduponchelle - let's make it easier to post, 
- [ ] @sjn - let's add a new channel for smaller/faster blog posts "Blog posts" that have lower PR quality requirements
  - @sjn working on new templates for website to make this happen
- [ ] @robrwo compiling list of popular modules that need security policies
  - ongoing, but it looks like almost all of them

#### Recruitment
- [x] @thibaultduponchelle - inviting @jjatria to join
    - Success

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
- @stigtsp, issue with bounded max versions in CVE records (Mojolicious, cpanminus)
    - Issues updating MITRE issued CVEs
    - long standing vulnerabilities are a problem
- @stigtsp, Red Hat is discussing adoption of pre CNA CVEs with CNA Root Board, after MITRE rejected our request to adopt old in-scope CVEs
  - Rejected by mitre
  - will be raised at the board meeting of CVEs
- @stigtsp, @timlegge - Presentation of CNA work so far
    - @stigtsp - 30 CVE identifiers reserved, and 24 published in our database, per now
- @stigtsp - We need more help from others in the triage group:
    - [X] Contact @timlegge, @stigtsp - Analysing vulnerabilities
    - [ ] Contact @timlegge, @stigtsp - Integrating CVE process more with triage
- @robrwo - CNA/CPANSec workflow description needed from CVE reservation to disclosure
    - [ ] (Volunteer needed) - Write a guide/workflow doc, including details on how embargoes work
    - @sjn - could this be turned into a tabletop exercise?
- @stigtsp - guided CVE writeup-sessions at PTS and at regular times otherwise
    - [ ] @stigtsp and @timlegge prepare a dummy scenario
- @stigtsp - Tried to reach out to ENISA (EUVD) now a couple of times to discuss contingency/options, but no answer yet.
    - [x] @sjn had a meeting coming up and will ask
       - Comms folk are super busy, please give them more time; It's also ok to send a reminder.
- @stigtsp - @garu has emailed a list of old perl CVEs to RH for reassignment to our CNA, pending
  - mitre declined
- @stigtsp - Can someone look at the cpansa-feed, it's broken for a while now :-(
    - [ ] - @stigtsp will try to look at this Soon™
- @robrwo asked on Matrix about ways to track issues to triage/research before CVEs


### [Secure by Default](https://github.com/orgs/CPAN-Security/projects/15/views/2)

#### TLS/HTTPS/CSPRNG/DSA in core
- [ ] @leont - share ongoings & blockers
   - [ ] @leont - a minimal XS wrapper around libopenssl
   - @toddr - should we explore simpler options, like wrapping libcurl? or even calling `/usr/bin/curl`
      - @toddr - some license issues to be aware of (which is another argument to "Just use curl(1)")
 - no update since PTS

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
- No news on the above items
- @sjn to meet with Alpha-Omega today

#### Eclipse ORC WG
- @sjn - Misc. ongoing activities FAQ
- no update

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
  - e.g. require downstream entities to appoint a community liaison that we can interact with
- @sjn had a good discussion with Patricia Aas
- has notes on the requirements from a commercial point of view - but focus on getting government support

### [Authentication & Trusted Publishing](https://github.com/orgs/CPAN-Security/projects/3/views/2)
- [ ] (Volunteers/tuits/funding needed - this topic is available for adoption!)
- @timlegge - rstuf seems promising

### [Transparency Logs & Trusted Distribution](https://github.com/orgs/CPAN-Security/projects/2/views/2)
- [ ] (Volunteers/tuits/funding needed - this topic is available for adoption!)


## Any Other Business
- [ ] @robrwo methods for notifying multiple maintainers of security issues as part of Perl ecosystem (RT or some kind of cpan.org mailing list)


### Upcoming events and deadlines
- [ ] (Norway) [Internet Governance Forum 2025](https://www.intgovforum.org/) - Monday 2025-06-23 … Saturday 2025-06-28 in Lillestrøm, Norway; (Registration closes June 8th)
    - @sjn is confirmed to go
- [ ] (USA) [TPRC 2025](https://www.perl.com/article/get-ready-for-the-2025-perl-and-raku-cce/) - Friday 2025-06-27 … Sunday 2025-06-29 in Greenville, SC, USA (CfP is closed)
    - @toddr goes
- [ ] (Netherlands) [OpenSSF Community Day Europe](https://events.linuxfoundation.org/openssf-community-day-europe/) - 2025-08-28 - Amsterdam, Netherlands (CfP is closed)
- [ ] (Croatia) [EuroBSDCon 2025](https://events.eurobsdcon.org/2025/) - Thursday 2025-09-25 … Sunday 2025-09-28 in Zagreb, Croatia; ([CfP is open](https://events.eurobsdcon.org/2025/cfp); Deadline: 2025-06-21)
- [ ] (Germany) [All Systems Go](https://all-systems-go.io/) - Sept. 30th - Oct. 1st 2025, Berlin ([CfP is open](https://cfp.all-systems-go.io/all-systems-go-2025/cfp); Deadline: 2025-06-13)
- [ ] (Belgium) OpenSSF EU Policy Summit - 2025-10-30, in Ghent, Belgium;
- [ ] (World) [CPAN 30 year anniversary](https://github.com/neilb/history-of-cpan/blob/master/history.md#the-cpan-years) - Sunday 2025-10-26
- [ ] (USA) [Open Source Security Con](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/co-located-events/open-source-securitycon/) - Monday 2025-11-10, Atlanta, Georgia ([CfP is open](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/co-located-events/cfp-colocated-events/) until 2025-06-30)

## Next meeting date, time and location
- Next meeting is Wednesday 2025-06-18 @ 16:00UTC in #cpansec-discussion on Matrix (18:00 Europe/Amsterdam)


## 17:00 UTC - Meeting end


## 18:19 UTC - End
