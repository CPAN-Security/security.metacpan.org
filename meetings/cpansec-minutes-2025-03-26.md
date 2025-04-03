---
layout: page
toc: true
meeting_time: 2025-03-26 17:00 UTC
title: CPANSec bi-weekly minutes
---

## Agenda & Meeting Details 2025-03-26
- 2025-03-26 17:00 UTC on #cpansec-discussion on Matrix


## 16:30 UTC - Pre-meeting socializing
-   Socializing & getting up to speed before the meeting starts properly
-   Discuss organizing projects, swimlanes and issues (...)
-   Check and resolve technical (A/V) issues before the meeting starts
-   Come as you are!

## 17:04 UTC - Meeting start

## Welcome
-   Meeting chair: @robrwo
-   Meeting scribe: @sjn


### Attendees, absents & regrets
-   Attendees
    * @sjn, @robrwo, @stigtsp, @thibaultduponchelle
-   Regrets
    * @timlegge

### Approve previous meeting minutes
-   Previous meeting minutes was approved by X, and merged by Y


## Agenda

### Current matters

### Operating changes
- [ ] @sjn - Proposal for a new project on Gh: **Security Audits & Reviews**
    - Useful & critical to perform for core infrastructure, code, projects and modules
    - Also, something we can raise funding for


### [Metadata & Software Bills of Materials](https://github.com/orgs/CPAN-Security/projects/1/views/2)

#### CPAN::Meta::Spec, Requirements and PURLs
- [ ] @sjn - picking up CPAN::Meta::Spec after FOSDEM
- [ ] @sjn - need to push GDT's PURL update to it's spec
   - @stigtsp - Some delays in adding it to CVEs

#### SBOM/Metadata on CPAN
- [ ] @tux - we need tools for working with SBOMs. *correct* SBOMs.
   - @sjn - @gdt has written some modules for generating CycloneDX 1.6 documents from CPAN Metadata: [SBOM::CycloneDX](https://github.com/giterlizzi/perl-SBOM-CycloneDX) and [App::CPAN::SBOM](https://github.com/giterlizzi/perl-App-CPAN-SBOM)
   - [ ] @sjn and @tux will check them out and comment on usability

#### CycloneDX 1.7 Sustainability fields
- @sjn - Ongoing: project- & ecosystem-supplied status fields.
   - @sjn - Certain ecosystem-sourced project statuses are taken out of scope for now; They may be added at a later version of the spec.


### [Compliance, Guidance & Privacy](https://github.com/orgs/CPAN-Security/projects/9/views/2)

#### CPAN Author's Security Policy Guidelines
- [ ] @stigtsp - Minimal (TLDR) version of policy wanted
- [ ] @tux - Team document template wanted; Help needed
   - [ ] @timlegge has started on something; happy to discuss with @tux; PR in the works
- [ ] @sjn - Alternative documents needed for non-Europeans (requested by jnap)
   - @sjn - can help with a CRA perspective
   - @sjn - ORC WG FAQ may help

### [Security Information & Outreach](https://github.com/orgs/CPAN-Security/projects/12/views/3)

#### Recruitment
- [x] @sjn - look at the next events for opportunities
   - @sjn will attend GPW and Foss North partly for this reason.

#### Perl Toolchain Summit 2025
- [ ] @sjn - Create document on what CPANSec-relevant issues need to be decided on/discussed at PTS
    - Everyone, please add tasks!
    - [ ] @stigtsp - Better tooling for CNA CVE
    - [ ] @stigtsp - Show CVEs on MetaCPAN
    - [ ] @stigtsp - Better feed for Test::CVE and friends

#### New Guide needed: PackageURL
- [ ] @sjn - We need a comprehensive PackageURL guide that answers/covers all relevant use cases
    - Non-perl project uses perl executable provided by packaging system // plenv // build-perl // ActiveState // etc.
    - Non-perl project uses a tool provided on CPAN
    - Non-perl project uses a vendored/included tool written in Perl
    - Perl project not on CPAN uses a CPAN module found on CPAN
    - Perl project found on CPAN uses a CPAN module found on CPAN
    - Perl project not found on CPAN uses a CPAN module not found on CPAN, but a DarkPAN
    - etc.

#### StarJacking Study
- [ ] @thibaultduponchelle - CPAN StarJacking study
   - [x] @garu @thibaultduponchelle - Checked riverjacking algo with Neil for faking high river score with one single author
   - [ ] Ready. Merge?



### [CNA & Vulnerability Index](https://github.com/orgs/CPAN-Security/projects/10/views/2)

#### CNA Organization
- [x] @stigtsp, @timlegge - Presentation of CNA work so far
  - @stigtsp - 18 CVE identifiers reserved, and 3 published in our database, per now
    - Check out our announcement mailing list on https://lists.security.metacpan.org
    - Q&A about daily procedures; @stigtsp shared what he knows
- @stigtsp - We need more help from others in the triage group:
  - [ ] Contact @timlegge, @stigtsp - Analysing vulnerabilities
  - [ ] Contact @timlegge, @stigtsp - Integrating CVE process more with triage
- @robrwo - CNA/CPANSec workflow description needed from CVE reservation to disclosure
  - [ ] (Volunteer needed) - Write a guide/workflow doc, including details on how embargos work


### [Governance, Policy & Funding](https://github.com/orgs/CPAN-Security/projects/7/views/2)

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
- [x] @sjn - New fundraising spreadsheet started. The previous one was a mess. WIP

#### Eclipse ORC WG
- [x] @sjn - Lots of progress on the [FAQ](https://github.com/orcwg/cra-hub/blob/main/faq.md) and [Inventory](https://github.com/orcwg/cra-hub/blob/main/inventory.md) docs, with lots of issues created.

#### CPAN Steward org
- @sjn - Discussions on TPRF slack #cpansec-steward; Mostly @sjn making noise;
    - Contributors who care about governance needed; Please reach out to @sjn
- @sjn has been asked by BSI and FSFE to help with perspectives and questions for a questionnaire.
    - [ ] @sjn - Organize some discussions around the second round of feedback to BSI/FSFE, in #cpansec-steward
       - Working document: https://cryptpad.fr/pad/#/2/pad/edit/-mzjtZPP8zZ3wNLmKRgvrN3s/

#### CRA Standardization on Vulnerability handling
- @sjn - The EU Commission has tasked CEN/CENELEC & ETSI with standardization around 41 different activities related to the Cyber Resilience Act. One of these is related to _Vulnerability handling_
    - I think we'd do well to try to contribute to especially this process, to ensure that the coming standards and guidelines for handling vulnerabilities are well-alligned with our (Open Source Ecosystems) particular needs.
    - [x] Volunteers needed! @sjn has too much to do, and this is imporant and may shape our workload for many years, depending on what we do (or don't do).
       - @stigtsp can join for a meeting, and take it from there
    - [ ] @all - Watch the [CEN/CENELEC introduction webinar on this matter](https://www.youtube.com/watch?v=KVr9zSZ0nUU) (Duration: 1h 20min; [Slides etc.](https://www.cencenelec.eu/news-and-events/events/2025/2025-03-10_webinar_cyber-resilience-act/))

#### PTS Funding
- @sjn - BooK has asked for help raiding funds.
   - [x] @sjn - Pad for ongoing work: https://cryptpad.fr/pad/#/3/pad/edit/a8adbd63e478caf94037ffcd162c9612/
   - [ ] Volunteers needed
- [x] @sjn - New project overview in the works: https://cryptpad.fr/sheet/#/2/sheet/edit/vazHpOmoK6bM-qKo7WRpzq6U/
   - @sjn - The goal is to get an overview _with_ possibility for prioritizing & voting
   - [x] Effort failed


### [Secure by Default](https://github.com/orgs/CPAN-Security/projects/15/views/2)

#### TLS/HTTPS/CSPRNG/DSA in core
- [ ] @leont - share ongoings & blockers

#### Ongoing vulnerabilities
- [ ] @timlegge - Crypt::Bcrypt issues around password length


### [Trusted Publishing & Authentication](https://github.com/orgs/CPAN-Security/projects/3/views/2)
- [ ] (Volunteers/tuits/funding needed - this topic is available for adoption!)


### [Security Patch Tooling](https://github.com/orgs/CPAN-Security/projects/11/views/2)
- [ ] (Volunteers/tuits/funding needed - this topic is available for adoption!)
  - Possible candidates: @atoomic, @thibaultduponchelle


### [Software Composition Analysis & Vulnerability Detection](https://github.com/orgs/CPAN-Security/projects/6/views/2)
- [ ] (Volunteers/tuits/funding needed - this topic is available for adoption!)


### [Trusted Distribution & Transparency Logs](https://github.com/orgs/CPAN-Security/projects/2/views/2)
- [ ] (Volunteers/tuits/funding needed - this topic is available for adoption!)


## Any Other Business
- [x] @stigtsp - CVE portal setup report - doing a mailing list instead
- [ ] @stigtsp - domain name; we're using metacpan.org branding, but also own the cpansec.org domain. What to do with this? @stigtsp reports
- [ ] @stigtsp - Can someone look at the cpansa-feed, it's broken for a while now :-(
   - [ ] (Volunteers needed) This is important.
      - (We hear some people are looking into this)
- @robrwo, @leont and others taking over some of ZEFRAM's modules
   - [ ] (Volunteers needed) - Should we compile a list of security-related modules with contact info, maintenance status, with an eye towards keeping them maintained with multiple co-maints
- [ ] @robrwo methods for notifying multiple maintainers of security issues (RT or some kind of mailing list)

### Upcoming events and deadlines
- [ ] (Sweden) [FOSS North](https://foss-north.se/2025/schedule.html) - Monday 2025-04-14 … Tuesday 2025-04-15 in Gothenburg, Sweden
    - @sjn participates
- [ ] (Germany) [PTS 2025](https://perltoolchainsummit.org/pts2025/) - Thursday 2025-05-01 … Sunday 2025-05-04 in Leipzig, Germany
    - @tux, @stigtsp, @leont, @garu, @sjn, @thibaultduponcelle, @timlegge are going
- [ ] (Germany) [GPW 2025](https://act.yapc.eu/gpw2025/) - Monday 2025-05-12 … Wednesday 2025-05-14 in Munich, Germany. ([CfP is open](https://act.yapc.eu/gpw2025/cfp.html))
    - @sjn is going
- [ ] (Norway) [Internet Governance Forum 2025](https://www.intgovforum.org/) - Monday 2025-06-23 … Saturday 2025-06-28 in Lillestrøm, Norway; ([Call for Sessions](https://www.intgovforum.org/en/content/igf-2025-call-for-session-proposals))
    - @sjn may be going (TBD)
- [ ] (USA) [TPRC 2025](https://www.perl.com/article/get-ready-for-the-2025-perl-and-raku-conference/) - Friday 2025-06-27 … Sunday 2025-06-29 in Greenville, SC, USA ([CfP is open](https://www.papercall.io/tprcgsp2025); Deadline: 2025-03-15)
- [ ] (Croatia) [EuroBSDCon 2025](https://events.eurobsdcon.org/2025/) - Thursday 2025-09-25 … Sunday 2025-09-28 in Zagreb, Croatia; ([CfP is open](https://events.eurobsdcon.org/2025/cfp); Deadline: 2025-06-21)
- [ ] (Belgium) OpenSSF EU Policy Summit - 2025-10-30, in Ghent, Belgium;
- [ ] (World) [CPAN 30 year anniversary](https://github.com/neilb/history-of-cpan/blob/master/history.md#the-cpan-years) - Sunday 2025-10-26




## Next meeting date, time and location
- Next meeting is Wednesday 2025-04-09 @ 17:00UTC in #cpansec-discussion on Matrix (17:00 Europe/Amsterdam)


## 18:10 UTC - Meeting end


## 18:10 UTC - End
