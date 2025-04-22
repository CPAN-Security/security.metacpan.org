---
layout: page
toc: true
meeting_time: 2025-04-09 17:00 UTC
title: CPANSec bi-weekly minutes
---

[TOC]

## Agenda & Meeting Details 2025-04-09
- 2025-04-09 17:00 UTC on #cpansec-discussion on Matrix


## 16:30 UTC - Pre-meeting socializing
-   Socializing & getting up to speed before the meeting starts properly
-   Discuss organizing projects, swim lanes and issues (...)
-   Check and resolve technical (A/V) issues before the meeting starts
-   Come as you are!

## 17:04 UTC - Meeting start

## Welcome
-   Meeting chair: @sjn
-   Meeting scribe: @timlegge


### Attendees, absents & regrets
-   Attendees
    - @robrwo, @timlegge, @Tux, @stigtsp. @sjn
-   Regrets
    - @thibaultduponchelle

### Approve previous meeting minutes
-   Previous meeting minutes was approved by @thibaultduponchelle and merged by @sjn


## Agenda

### Current matters

### Operating changes
- [x] @sjn - Proposal for a new project on Gh: **Security Audits & Code Reviews**
    - Useful & critical to perform for core infrastructure, code, projects and modules
    - Also, something we can raise funding for
    - @sjn will put a project on github
- [x] @sjn - Should we drop the "Software Composition Analysis" part of [Software Composition Analysis & Vulnerability Detection](https://github.com/orgs/CPAN-Security/projects/6/views/2)?
    - Lets park the SCA and Vulnerability Testing
    - SCA is only useful as long as SBOM quality is low/non-existant. Better to focus on this!
    - Vulnerability Detection is still useful; Merge it into another project?
- [x] @sjn - A few projects renamed for clarity!
    - Compliance, Guidance & Standards
    - Organization, Governance & Funding
    - Authentication & Trusted Publishing
    - Transparency Logs & Trusted Distribution

    - No issue with renamed projects

### [Metadata & Software Bills of Materials](https://github.com/orgs/CPAN-Security/projects/1/views/2)

#### CPAN::Meta::Spec, Requirements and PURLs
- [ ] @sjn - picking up CPAN::Meta::Spec after FOSDEM
- [x] @sjn - need to push GDT's PURL update to it's spec
   - @stigtsp - Some delays in adding it to CVEs

#### SBOM/Metadata on CPAN
- [x] @tux - we need tools for working with SBOMs. *correct* SBOMs.
   - @sjn - @gdt has written some modules for generating CycloneDX 1.6 documents from CPAN Metadata: [SBOM::CycloneDX](https://github.com/giterlizzi/perl-SBOM-CycloneDX) and [App::CPAN::SBOM](https://github.com/giterlizzi/perl-App-CPAN-SBOM)
   - [x] @sjn and @tux will check them out and comment on usability
   - We skip this work for now

#### CycloneDX 1.7 Sustainability fields
- @sjn - Ongoing: project- & ecosystem-supplied status fields.
   - @sjn - Certain ecosystem-sourced project statuses are taken out of scope for now; They may be added at a later version of the spec.


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
   - @robrwo -  the doc is best practice not specific to countries etc.
- [x] @robrwo issue with the license of the resulting security policies
   - should we change from CC0 to BSD0?
      - Some discussion of licensing - @rrwo will change to BSD0
- @robrwo mini-project to encourage the popular modules to add a security policy
   - See https://metacpan.org/favorite/leaderboard for a list
   - @timlegge - Sounds like a good idea
   - security.md, sbom and valid cpanfile, cpansa and busfactor, cpan.org email
   - cpants has experimental support
   - look into "update your cpan module" month (ref @tux's checklist)
   - [ ] @robrwo - will contact manwar to see if he'd like to help with outreach

### [Security Information & Outreach](https://github.com/orgs/CPAN-Security/projects/12/views/3)

#### Recruitment
- N/A

#### Perl Toolchain Summit 2025
- @sjn - Create document on what CPANSec-relevant issues need to be decided on/discussed at PTS
    - Everyone, please add tasks to the PTS wiki!
    - [ ] @stigtsp - Better tooling for CNA CVE
    - [ ] @stigtsp and tim - Intro to CNA CVE (onboarding?)
    - [ ] @stigtsp - Show CVEs on MetaCPAN
    - [ ] ? - Show security policies on MetaCPAN
    - [ ] @stigtsp - Better feed for Test::CVE and friends
    - [ ] @sjn - CPAN::Meta update
        - Complete the dependency graph
        - Allow linking to SBOM documents that are passed along the distro
        - Discuss which new required metadata fields need to go into the CPAN::Meta::Spec, and which should go into SBOMs
    - [ ] @sjn - Open discussion: CPANSec as an OSS Steward
        - Present purpose and regulatory requirements
        - Discuss and decide on community aligned principles to be enshrined in the Charter
        - Who are the founding stakeholder groups?
    - [ ] @tux - DBI on how to use tooling to improve security there

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

#### StarJacking Study
- [x] @thibaultduponchelle - CPAN StarJacking study
   - [x] Ready. Merge? Yes!


### [CNA & Vulnerability Index](https://github.com/orgs/CPAN-Security/projects/10/views/2)

#### CNA Organization
- [x] @stigtsp, @timlegge - Presentation of CNA work so far
  - @stigtsp - 8 CVE identifiers reserved, and 14 published in our database, per now
    - Check out our announcement mailing list on https://lists.security.metacpan.org
    - Q&A about daily procedures; @stigtsp shared what he knows
- @stigtsp - We need more help from others in the triage group:
  - [ ] Contact @timlegge, @stigtsp - Analysing vulnerabilities
  - [ ] Contact @timlegge, @stigtsp - Integrating CVE process more with triage
- @robrwo - CNA/CPANSec workflow description needed from CVE reservation to disclosure
  - [ ] (Volunteer needed) - Write a guide/workflow doc, including details on how embargos work
- @stigtsp - guided CVE writeup-sessions at PTS and at regular times otherwise
  - [ ] @stigtsp and @timlegge prepare a dummy scenario


### [Secure by Default](https://github.com/orgs/CPAN-Security/projects/15/views/2)

#### TLS/HTTPS/CSPRNG/DSA in core
- [ ] @leont - share ongoings & blockers
   - [x] @sjn - should we take this item out of the agenda?
      - Lets leave till after PTS
- [ ] @stigtsp and others add Todo tasks to the project board, so we don't forget what "Secure by Default" entails

#### Ongoing vulnerabilities
- [x] @timlegge - Crypt::Bcrypt issues around password length
   - [x] @sjn - should we take this item out of the agenda?
   - Lets remove from agenda if the docs reference the limitation


### [Organization, Governance & Funding](https://github.com/orgs/CPAN-Security/projects/7/views/2)

#### Funding drive
- [ ] @sjn - who is open (or willing to commit) to do funded work? (e.g. X days per week)
    - [x] @stigtsp 1d/w
    - [x] @robrwo 0d/w
    - [ ] @leont (? - please contact @sjn)
    - [ ] @garu (? - please contact @sjn)
    - [ ] Others? (contact @sjn!)
- [ ] @sjn - Explore options with Ovid's company
- [ ] @sjn - Talk with prospective companies to look for opportunities
- [ ] @sjn - Organize fundraiser's coordinator meeting w/Olaf & Stuart (delayed)
- [ ] @sjn - Investigate pre-project funding chances with NUUG foundation
- [ ] @sjn - New project overview in the works: https://cryptpad.fr/sheet/#/2/sheet/edit/vazHpOmoK6bM-qKo7WRpzq6U/

#### Eclipse ORC WG
- @sjn - Misc. ongong activities
    - [x] "CRA Mondays" announced
    - [x] FAQ working groups created; @sjn contributes

#### CPAN Steward org
- @sjn - Discussions on TPRF slack #cpansec-steward; Mostly @sjn making noise;
    - [ ] Contributors who care about governance needed; Please reach out to @sjn


### [Security Patch Tooling](https://github.com/orgs/CPAN-Security/projects/11/views/2)
- [ ] (Volunteers/tuits/funding needed - this topic is available for adoption!)
   - Possible candidates:
     - [ ] @atoomic
     - [x] @thibaultduponchelle volunteers!
- @thibaultduponchelle - Initiated some preliminary discussions around CPAN Patch tooling.

### [Authentication & Trusted Publishing](https://github.com/orgs/CPAN-Security/projects/3/views/2)
- [ ] (Volunteers/tuits/funding needed - this topic is available for adoption!)

### [Software Composition Analysis & Vulnerability Detection](https://github.com/orgs/CPAN-Security/projects/6/views/2)
- [ ] (Volunteers/tuits/funding needed - this topic is available for adoption!)

### [Transparency Logs & Trusted Distribution](https://github.com/orgs/CPAN-Security/projects/2/views/2)
- [ ] (Volunteers/tuits/funding needed - this topic is available for adoption!)
- [x] We decided to close this project; Will reopen if someone volunteers

## Any Other Business
- [x] @stigtsp - domain name; we're using metacpan.org branding, but also own the cpansec.org domain. What to do with this? @stigtsp reports
   - @sjn - Move it to separate org eventually
- [ ] @stigtsp - Can someone look at the cpansa-feed, it's broken for a while now :-(
   - [ ] (Volunteers needed) This is important.
      - (We hear some people are looking into this)
- @robrwo, @leont and others taking over some of ZEFRAM's modules
   - [x] (Volunteers needed) - Should we compile a list of security-related modules with contact info, maintenance status, with an eye towards keeping them maintained with multiple co-maints
- [ ] @robrwo methods for notifying multiple maintainers of security issues (RT or some kind of mailing list)

### Upcoming events and deadlines
- [ ] (Sweden) [FOSS North](https://foss-north.se/2025/schedule.html) - Monday 2025-04-14 … Tuesday 2025-04-15 in Gothenburg, Sweden
    - @sjn participates, intends to work on CRA stuff
- [ ] (Germany) [PTS 2025](https://perltoolchainsummit.org/pts2025/) - Thursday 2025-05-01 … Sunday 2025-05-04 in Leipzig, Germany
    - @tux, @stigtsp, @leont, @garu, @sjn, @thibaultduponcelle, @timlegge are going
- [ ] (Germany) [GPW 2025](https://act.yapc.eu/gpw2025/) - Monday 2025-05-12 … Wednesday 2025-05-14 in Munich, Germany. ([CfP is open](https://act.yapc.eu/gpw2025/cfp.html))
    - @sjn is going, one talk submitted
- [ ] (Norway) [Internet Governance Forum 2025](https://www.intgovforum.org/) - Monday 2025-06-23 … Saturday 2025-06-28 in Lillestrøm, Norway; ([Call for Sessions](https://www.intgovforum.org/en/content/igf-2025-call-for-session-proposals))
    - @sjn may be going (TBD)
- [ ] (USA) [TPRC 2025](https://www.perl.com/article/get-ready-for-the-2025-perl-and-raku-conference/) - Friday 2025-06-27 … Sunday 2025-06-29 in Greenville, SC, USA ([CfP is open](https://www.papercall.io/tprcgsp2025); Deadline: 2025-03-15)
- [ ] (Croatia) [EuroBSDCon 2025](https://events.eurobsdcon.org/2025/) - Thursday 2025-09-25 … Sunday 2025-09-28 in Zagreb, Croatia; ([CfP is open](https://events.eurobsdcon.org/2025/cfp); Deadline: 2025-06-21)
- [ ] (Belgium) OpenSSF EU Policy Summit - 2025-10-30, in Ghent, Belgium;
- [ ] (World) [CPAN 30 year anniversary](https://github.com/neilb/history-of-cpan/blob/master/history.md#the-cpan-years) - Sunday 2025-10-26


## Next meeting date, time and location
- Next meeting is Wednesday 2025-04-23 @ 16:00UTC in #cpansec-discussion on Matrix (18:00 Europe/Amsterdam)


## 18:23 UTC - Meeting end


## 18:25 UTC - End
