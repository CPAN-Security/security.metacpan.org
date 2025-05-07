---
layout: page
toc: true
meeting_time: 2025-05-07 16:00 UTC
title: CPANSec bi-weekly minutes
---

## Agenda & Meeting Details 2025-05-07
- 2025-05-07 16:00 UTC on #cpansec-discussion on Matrix


## 15:40 UTC - Pre-meeting socializing
-   Socializing & getting up to speed before the meeting starts properly
-   Discuss organizing projects, swimlanes and issues (...)
-   Check and resolve technical (A/V) issues before the meeting starts
-   Come as you are!

## 16:01 UTC - Meeting start

## Welcome
-   Meeting chair: @timlegge
-   Meeting scribe: @sjn

### Attendees, absents & regrets
-   Attendees
    - @timlegge, @sjn, @stigtsp, @toddr, @thibaultduponchelle, (@tux)
-   Regrets 
    -  @leont, @rrwo

### Approve previous meeting minutes
-   Previous meeting minutes was approved by @thibaultduponchelle and @stigtsp, and merged by @sjn

## Agenda

### Current matters

#### CPAN Testers
- [x] @tux - CPAN Testers work happening at PTS; We should contribute!
  - e.g. ask if CPAN Testers can add results of Test::CVE

#### XML::LibXML
- [ ] @tux - XML::LibXML touches CVE issues in Alien
  - @stigtsp - probably not a CVE for the CPAN module

#### BSON::XS - vulnerable deps
- [ ] @stigtsp - let's create a CVE


### Operating changes
- @sjn - Proposal: Add RSS feeds to the matrix channel? Suggestions for channel admins:
   - Mastodon feed: https://fosstodon.org/@cpansec.rss
   - News feed: https://security.metacpan.org/feed.xml
   - CVE announcements feed: @stigtsp - can be done as part of an automated CVE announcement process
   - CVE updates feed: Can hook right into the CVE.org database maybe
- [ ] @stigtsp - good idea!


### [Metadata & Software Bills of Materials](https://github.com/orgs/CPAN-Security/projects/1/views/2)

#### CPAN::Meta::Spec, Requirements and PURLs
- @sjn and @leont discussed at PTS, decided to
  - [ ] @sjn - put together a detailed proposal

#### CycloneDX 1.7 Sustainability fields
- @sjn - Ongoing: project- & ecosystem-supplied status fields.
  - @sjn - interesting discussions around exploring relationships between this spec and LF's security-insights.yml spec

### [Compliance, Guidance & Standards](https://github.com/orgs/CPAN-Security/projects/9/views/2)

#### CPAN Author's Security Policy Guidelines
- [ ] @stigtsp - Minimal (TLDR) version of policy wanted
- [ ] @tux - Team document template wanted; Help needed
   - [ ] @timlegge has started on something; happy to discuss with @tux; PR in the works
   - @robrwo - not so much a different kind of doc as possible different way to report vuln
- [ ] @sjn - Alternative documents needed for non-Europeans (requested by jnap)
   - @sjn - can help with a CRA perspective
   - @sjn - ORC WG FAQ may help
   - @robrwo - this may be misunderstanding of the purpose of the document
   - @robrwo - the doc is best practice not specific to countries etc.
- [ ] @robrwo mini-project to encourage the popular modules to add a security policy
   - See https://metacpan.org/favorite/leaderboard for a list
   - Sounds like a good idea
   - security.md, sbom and valid cpanfile, cpansa and busfactor, cpan.org email
   - cpants has experimental support
   - look into "update your cpan module" month (ref @tux's checklist)
     - @robrwo interpreted this as a "security checklist" which is a bit too broad in scope, and overlaps with secure coding guidelines
       was thinking of a trimmed down metadata/config/documentation security checklist
   - [ ] @robrwo contacts manwar to see if he'd like to help with outreach


### [Security Information & Outreach](https://github.com/orgs/CPAN-Security/projects/12/views/3)
- [ ] @robrwo suggesting a regular blog series
  - blog posts smaller scope than monolithic documents/guides
  - different authors and topics including current news items
  - regular posts can get more attention
- @thibaultduponchelle - let's make it easier to post, 
- [ ] @sjn - let's add a new channel for smaller/faster blog posts "Blog posts" that have lower PR quality requirements


#### Recruitment
- @thibaultduponchelle - inviting @jjatria to join


#### Perl Toolchain Summit 2025
- @sjn - Create document on what CPANSec-relevant issues need to be decided on/discussed at PTS
    - Everyone, please add tasks to the PTS wiki!
    - [X] @stigtsp and @tux - Better tooling for CNA CVE (Started)
    - [ ] @stigtsp and @timlegge - Intro to CNA CVE (onboarding?)
      - Tim will write something
    - [ ] @stigtsp - Show CVEs on MetaCPAN
      - We started at PTS. Mickey, Garu, Jordan etc got involved
    - [ ] @stigtsp (+@timlegge, +@garu) - Help with perlsecpolicy
      - @toddr - started exploring ways to clarify the processes around vulnerability disclosures, etc.
    - [ ] @stigtsp - Talk about "CVE?"
    - [ ] ? - Show security policies on MetaCPAN
    - [ ] @stigtsp and @tux - Better feed for Test::CVE and friends
    - [x] @sjn - CPAN::Meta update
        - [ ] Complete the dependency graph
        - [ ] Allow linking to SBOM documents that are passed along the distro
        - [ ] Discuss which new required metadata fields need to go into the CPAN::Meta::Spec, and which should go into SBOMs
        - [ ] metadata for vulnerability reporting (email or url)
        - [x] @sjn - met up with @leont (see above)
    - [x] @sjn - Open discussion: CPANSec as an OSS Steward
        - [ ] @sjn - Present purpose and regulatory requirements
        - [ ] @sjn - Discuss and decide on community aligned principles to be enshrined in the Charter
        - [ ] @sjn - Who are possible founding stakeholder groups?
        - [x] @sjn - had several one-on-one conversations
    - [ ] @tux - DBI on how to use tooling to improve security there
    - [x] @tux - discuss errors from gcc-14 (-Wno-error=...) and gcc15 (C23)
    - [x] @thibaultduponchelle and @tux
      - [ ] @thibaultduponchelle - Test::Smoke - Deprecate PerlIO/Stdio dual testing;
    - [x] @thibaultduponchelle - Discuss patching facilities during smoke
      - [x] @thibaultduponchelle - Look at patchup.pl, define spec (smokecurrent.patches, patches/)
      - [ ] @thibaultduponchelle - Implementation
    - [x] @thibaultduponchelle PAUSE - Review the operating model - Merged https://github.com/andk/pause/pull/551, https://github.com/andk/pause/pull/550, https://github.com/andk/pause/pull/541
    - [x] @thibaultduponchelle CPANSec - Maybe some CPAN installer patch tooling discussion
      - [x] @thibaultduponchelle - Discussion with @tinita about cpan-meta 
      - [x] @thibaultduponchelle - Pair with @nicolas, braimstorm with @leont, @toddr
      - [ ] @thibaultduponchelle - Implement POC cpm + CPAN::DistroPrefs and present to CPANSec
    - [x] @thibaultduponchelle - Maybe some PAUSE pentesting? 
      - [x] @thibaultduponchelle - Owner of 2 GHSA in PAUSE + follow-up LEONT merge request
    - [ ] @sjn and @tux - create an SBOM from Perl's Configure

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
    - @stigtsp - 8 CVE identifiers reserved, and 14 published in our database, per now
- @stigtsp - We need more help from others in the triage group:
    - [ ] Contact @timlegge, @stigtsp - Analysing vulnerabilities
    - [ ] Contact @timlegge, @stigtsp - Integrating CVE process more with triage
- @robrwo - CNA/CPANSec workflow description needed from CVE reservation to disclosure
    - [ ] (Volunteer needed) - Write a guide/workflow doc, including details on how embargos work
- @stigtsp - guided CVE writeup-sessions at PTS and at regular times otherwise
    - [ ] @stigtsp and @timlegge prepare a dummy scenario
    - [ ] @garu got an intro to the CVE process; learned a lot that could be improved


### [Secure by Default](https://github.com/orgs/CPAN-Security/projects/15/views/2)

#### TLS/HTTPS/CSPRNG/DSA in core
- [ ] @leont - share ongoings & blockers
    - @leont - Lets leave till after PTS
    - @leont - considers creating a minimal XS wrapper around libopenssl
    - @toddr - should we explore simpler options, like wrapping libcurl? or even calling `/usr/bin/curl`

#### Ongoing vulnerabilities


### [Organization, Governance & Funding](https://github.com/orgs/CPAN-Security/projects/7/views/2)

#### Funding drive
- [ ] @sjn - who is open (or willing to commit) to do funded work? (e.g. X days per week)
    - [x] @stigtsp 1d/w
    - [x] @robrwo 0d/w
    - [x] @leont 1d/w
    - [ ] @garu (? - please contact @sjn)
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


### [Security Patch Tooling](https://github.com/orgs/CPAN-Security/projects/11/views/2)
- @thibaultduponchelle - PTS discussions mentioned above.


### [Authentication & Trusted Publishing](https://github.com/orgs/CPAN-Security/projects/3/views/2)
- [ ] (Volunteers/tuits/funding needed - this topic is available for adoption!)


### [Transparency Logs & Trusted Distribution](https://github.com/orgs/CPAN-Security/projects/2/views/2)
- [ ] (Volunteers/tuits/funding needed - this topic is available for adoption!)


## Any Other Business
- [x] @stigtsp - Can someone look at the cpansa-feed, it's broken for a while now :-(
   - [ ] - @garu started looking at this at PTS2025 
      - (We hear some people are looking into this)
- @stigtsp shared some info around security issues in the Mojolicious project
- [ ] @robrwo methods for notifying multiple maintainers of security issues as part of Perl ecosystem (RT or some kind of cpan.org mailing list)
- @toddr - What can the TPRF help with?
   - (open discussion on certain security issues)
   - @tux is happy 

### Upcoming events and deadlines
- [x] (Germany) [PTS 2025](https://perltoolchainsummit.org/pts2025/) - Thursday 2025-05-01 … Sunday 2025-05-04 in Leipzig, Germany
    - @tux, @stigtsp, @leont, @garu, @sjn, @thibaultduponcelle, @timlegge, @toddr went
- [ ] (Germany) [GPW 2025](https://act.yapc.eu/gpw2025/) - Monday 2025-05-12 … Wednesday 2025-05-14 in Munich, Germany. ([CfP is open](https://act.yapc.eu/gpw2025/cfp.html))
    - @sjn is going, one talk and one panel submitted
- [ ] (Norway) [Internet Governance Forum 2025](https://www.intgovforum.org/) - Monday 2025-06-23 … Saturday 2025-06-28 in Lillestrøm, Norway; ([Call for Sessions](https://www.intgovforum.org/en/content/igf-2025-call-for-session-proposals))
    - @sjn may be going (TBD)
- [ ] (USA) [TPRC 2025](https://www.perl.com/article/get-ready-for-the-2025-perl-and-raku-cce/) - Friday 2025-06-27 … Sunday 2025-06-29 in Greenville, SC, USA ([CfP is open](https://www.papercall.io/tprcgsp2025); Deadline: 2025-03-15)
    - @toddr goes
- [ ] (Croatia) [EuroBSDCon 2025](https://events.eurobsdcon.org/2025/) - Thursday 2025-09-25 … Sunday 2025-09-28 in Zagreb, Croatia; ([CfP is open](https://events.eurobsdcon.org/2025/cfp); Deadline: 2025-06-21)
- [ ] (Germany) [All Systems Go](https://all-systems-go.io/) Sept. 30th - Oct. 1st 2025, Berlin - [CfP is open until June 13](https://cfp.all-systems-go.io/all-systems-go-2025/cfp).
- [ ] (Belgium) OpenSSF EU Policy Summit - 2025-10-30, in Ghent, Belgium;
- [ ] (World) [CPAN 30 year anniversary](https://github.com/neilb/history-of-cpan/blob/master/history.md#the-cpan-years) - Sunday 2025-10-26


## Next meeting date, time and location
- Next meeting is Wednesday 2025-05-21 @ 16:00UTC in #cpansec-discussion on Matrix (18:00 Europe/Amsterdam)


## 17:18 UTC - Meeting end


## 17:18 UTC - End
