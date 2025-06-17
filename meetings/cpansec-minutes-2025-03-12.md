---
layout: single
toc: true
meeting_time: 2025-03-12 17:00 UTC
title: CPANSec bi-weekly minutes
---

[TOC]

## Agenda & Meeting Details 2025-03-12
- 2025-03-12 17:00 UTC on #cpansec-discussion on Matrix


## 16:30 UTC - Pre-meeting socializing
-   Socializing & getting up to speed before the meeting starts properly
-   Discuss organizing projects, swimlanes and issues (...)
-   Check and resolve technical (A/V) issues before the meeting starts
-   Come as you are!

## 17:00 UTC - Meeting start

## Welcome
-   Meeting chair: @timlegge
-   Meeting scribe: @sjn, @tux


### Attendees, absents & regrets
-   Attendees
    * @sjn, @tux, @thibaultduponcelle, @stigtsp, @timlegge, @atoomic
-   Regrets
    * @leont

### Approve previous meeting minutes
-   Previous meeting minutes was approved by @thibaultduponchelle and @timlegge, and merged by @sjn


## Special: How the new meeting agenda/minutes format works
- [x] @sjn - Introduces the new format for the agenda/minutes document
    - [x] @sjn - added the detailed format to [README.md](README)
    - TL;DR is below

### TL;DR
- [X] When an item (task, topic or event) is done, discussed or attended: Summarize and check the box
- [ ] When an item needs to be done/discussed/attended, add @names and notes, and leave box unchecked
- [X] When writing minutes from an agenda, let items, summaries and notes with checked boxes remain
- [X] When creating an agenda from the previous minutes, remove items, summaries and notes with checked boxes
    - Sub-items without checkboxes are summaries or notes to the previous item
- Items without checkboxes or @names are for information or finding volunteers
- [ ] Create tickets items are around for too long, or no-one volunteers


## Agenda

### [Metadata & Software Bills of Materials](https://github.com/orgs/CPAN-Security/projects/1/views/2)

#### CPAN::Meta::Spec, Requirements and PURLs
- [ ] @sjn - started on writing an overview of issues to be resolved before PTS
- [ ] @sjn - picking up CPAN::Meta::Spec after FOSDEM
- [ ] @sjn - need to push GDT's PURL update to it's spec

#### SBOM/Supply Chain
- [x] @tux - we need tools for working with SBOMs. *correct* SBOMs.
   - @sjn - @gdt has written some modules for generating CycloneDX 1.6 documents from CPAN Metadata: [SBOM::CycloneDX](https://github.com/giterlizzi/perl-SBOM-CycloneDX) and [App::CPAN::SBOM](https://github.com/giterlizzi/perl-App-CPAN-SBOM)
   - [ ] @sjn and @tux will check them out and comment on usability
- [ ] @thibaultduponcelle - wants some feedback on his starjacking text (good enough to merge or drop?)
   - [x] @sjn and @thibaultduponcelle - chat about this (set up meeting)
      - Had a quick chat. The starjacking study seemed good to @sjn; Let's add it.
      - [x] @thibaultduponcelle adds the starjacking study to the website repo
      - [ ] @sjn and @thibaultduponchelle will improve the docs, including professionalizing the format/layout

#### CycloneDX 1.7 Sustainability fields
- @sjn - starting soon on the final stretch - project- & ecosystem-supplied status fields.
  - [x] @sjn - Support indicator discussion ongoing with the Common Lifecycle Enumeration folks
  - [ ] @sjn - Discussion about how to communicate Ecosystem or other _Force Majeure_ events


### [Compliance, Guidance & Privacy](https://github.com/orgs/CPAN-Security/projects/9/views/2)

#### CPAN Author's Security Policy Guidelines
- [ ] @stigtsp - Minimal (TLDR) version of policy wanted
- [ ] @tux - Team document template wanted; Help needed
   - [ ] @timlegge has started on something; happy to discuss with @tux; PR in the works
- [ ] @sjn - Alternative documents needed for non-Europeans (requested by jnap)
   - @sjn can help with a CRA perspective


### [Security Outreach & Information](https://github.com/orgs/CPAN-Security/projects/12/views/3)

#### Recruitment
- [ ] @sjn - look at the next events for opportunities

#### Perl Toolchain Summit 2025
- [ ] @sjn - Create document on what CPANSec-relevant issues need to be decided on/discussed at PTS
    - Everyone, please add tasks!


### [CNA & Vulnerability Index](https://github.com/orgs/CPAN-Security/projects/10/views/2)

#### CNA Organization
- [x] @stigtsp, @timlegge - Presentation of CNA work so far
  - Discussions with other OSS CNAs last friday
    - Good discussion
    - Board update on CNAs
    - Discussion of CVE quality
    - Discussion of CVSS - almost always wrong
    - EOL is a challenge
    - Common Tooling would be good
  - Concerns about CVSS: we decided not to add CVSS to our CVEs for most cases
  - Discussion on changing CNA root from MITRE to RedHat
    - [X] Voted on changing CNA of last resort: Unanimous in favor of moving to Red Hat
  - Demo of processes we have in place so far
  - We need more help from others in the triage group:
    - [ ] @timlegge, @stigtsp - Analysing vulnerabilities
    - [ ] @timlegge, @stigtsp - Integrating CVE process more with triage


### [Governance, Policy & Funding](https://github.com/orgs/CPAN-Security/projects/7/views/2)

#### Funding drive
- @sjn - who is open (or willing to commit) to do funded work? (e.g. X days per week)
    - [x] @stigtsp 1d/w
    - [ ] @leont (? - please contact @sjn)
    - [ ] @garu (? - please contact @sjn)
    - [ ] Others? (contact @sjn!)
- [ ] @sjn - Explore options with Ovid's company

#### Eclipse ORC WG
- [ ] @sjn - Lots of progress on the [FAQ](https://github.com/orcwg/cra-hub/blob/main/faq.md) and [Inventory](https://github.com/orcwg/cra-hub/blob/main/inventory.md) docs, with lots of issues created.

#### CPAN Steward org
- @sjn - Discussions on TPRF slack #cpansec-steward; Mostly @sjn making noise;
    - [ ] @sjn - Contributors who care about governance needed
- @sjn has been asked by BSI and FSFE to help with perspectives and questions for a questionnaire.
    - [x] @sjn - first round of feedback submitted; second round started, deadline ultimo March
    - [ ] @sjn - Organize some discussions around the second round of feedback to BSI/FSFE, in #cpansec-steward

#### CRA Standardization on Vulnerability handling
- @sjn - The EU Commission has tasked CEN/CENELEC & ETSI with standardization around 41 different activities related to the Cyber Resilience Act. One of these is related to _Vulnerability handling_
    - I think we'd do well to try to contribute to especially this process, to ensure that the coming standards and guidelines for handling vulnerabilities are well-aligned with our (Open Source Ecosystems) particular needs.
    - [x] Volunteers needed! @sjn has too much to do, and this is important and may shape our workload for many years, depending on what we do (or don't do).
       - @stigtsp can join for a meeting, and take it from there
    - [ ] @all - Watch the [CEN/CENELEC introduction webinar on this matter](https://www.youtube.com/watch?v=KVr9zSZ0nUU) (Duration: 1h 20min; [Slides etc.](https://www.cencenelec.eu/news-and-events/events/2025/2025-03-10_webinar_cyber-resilience-act/))

#### PTS Funding
- @sjn - BooK has asked for help raising funds.
   - [x] @sjn - Pad for ongoing work: https://cryptpad.fr/pad/#/3/pad/edit/a8adbd63e478caf94037ffcd162c9612/
   - [ ] Volunteers needed

### [Secure by Default](https://github.com/orgs/CPAN-Security/projects/15/views/2)

#### TLS/HTTPS/CSPRNG/DSA in core
- [ ] @leont - share ongoings & blockers

#### Ongoing vulnerabilities
- [x] @timlegge - @robrwo working on RNG-related ongoing issues; CVE's to be registered by CPANSec CNA when it's active
   - Work is tracked in the CNA/CVE non-public repo
- [ ] @timlegge - Crypt::Bcrypt issues around password length


### [Provenance & Supply Chain Security](https://github.com/orgs/CPAN-Security/projects/3/views/2)
- [ ] (Volunteers/tuits/funding needed - this topic is available for adoption!)


### [Security Patch Tooling](https://github.com/orgs/CPAN-Security/projects/11/views/2)
- [ ] (Volunteers/tuits/funding needed - this topic is available for adoption!)
  - Possible candidates: @atoomic, @thibaultduponchelle


### [Software Composition Analysis](https://github.com/orgs/CPAN-Security/projects/6/views/2)
- [ ] (Volunteers/tuits/funding needed - this topic is available for adoption!)


### [Transparency Logs](https://github.com/orgs/CPAN-Security/projects/2/views/2)
- [ ] (Volunteers/tuits/funding needed - this topic is available for adoption!)



## Any Other Business
- [ ] @stigtsp - CVE portal setup report
- [ ] @stigtsp - domain name; we're using metacpan.org branding, but also own the cpansec.org domain. What to do with this? @stigtsp reports
- [ ] @stigtsp - Can someone look at the cpansa-feed, it's broken for a while now :-(
   - Volunteers needed! This is important.

### Upcoming events and deadlines
- [ ] (Sweden) [FOSS North](https://foss-north.se/2025/schedule.html) - Monday 2025-04-14 … Tuesday 2025-04-15 in Gothenburg, Sweden
    - @sjn participates
- [ ] (Germany) [PTS 2025](https://perltoolchainsummit.org/pts2025/) - Thursday 2025-05-01 … Sunday 2025-05-04 in Leipzig, Germany
    - @tux, @stigtsp, @leont, @garu ?, @sjn,  @thibaultduponcelle, @timlegge are going
- [ ] (Germany) [German Perl Workshop 2025](https://act.yapc.eu/gpw2025/) - Monday 2025-05-12 … Wednesday 2025-05-14 in Munich, Germany. ([CfP is open](https://act.yapc.eu/gpw2025/cfp.html))
    - @sjn is going, submitted a talk
- [ ] (Norway) [Internet Governance Forum 2025](https://www.intgovforum.org/) - Monday 2025-06-23 … Saturday 2025-06-28 in Lillestrøm, Norway; ([Call for Sessions](https://www.intgovforum.org/en/content/igf-2025-call-for-session-proposals))
    - @sjn may be going (TBD)
- [ ] (USA) [TPRC 2025](https://www.perl.com/article/get-ready-for-the-2025-perl-and-raku-conference/) - Friday 2025-06-27 … Sunday 2025-06-29 in Greenville, SC, USA ([CfP is open](https://www.papercall.io/tprcgsp2025); Deadline: 2025-03-15)
- [x] (Norway) [Sikkerhetfesivalen 2025](https://sikkerhetsfestivalen.no/) - Monday 2025-08-25 … Wednesday 2025-08-27 in Lillehammer, Norway. ([CfP is open](https://sikkerhetsfestivalen.no/alle-nyheter/2024/11/22/hvordan-skape-et-vinnende-foredrag-for-sikkerhetsfestivalen-2025))
    - Deadline passed; @sjn not likely to participate
- [ ] (Croatia) [EuroBSDCon 2025](https://events.eurobsdcon.org/2025/) - Thursday 2025-09-25 … Sunday 2025-09-28 in Zagreb, Croatia; ([CfP is open](https://events.eurobsdcon.org/2025/cfp); Deadline: 2025-06-21)
- [ ] (Belgium) OpenSSF EU Policy Summit - 2025-10-30, in Ghent, Belgium;
- [ ] (World) [CPAN 30 year anniversary](https://github.com/neilb/history-of-cpan/blob/master/history.md#the-cpan-years) - Sunday 2025-10-26



## Operating changes
- [x] @sjn - Since perl.social is dead, we have a new [CPANSec meeting calendar](https://calendar.google.com/calendar/u/0/embed?src=691584e3db7d0a877b43482fc996eaae9984cf8ba0b769d5d00d042a32f9c66e@group.calendar.google.com) on Google. This calendar is public! Reach out to @sjn to have him update it. He'll do that until we find a suitable shared solution.
- @sjn - investigates alternatives
   - [x] @sjn - Cryptpad investigated, and not usable for calendar stuff. [New calendar URL set up directly in google calendar](https://calendar.google.com/calendar/u/0/embed?src=691584e3db7d0a877b43482fc996eaae9984cf8ba0b769d5d00d042a32f9c66e@group.calendar.google.com) by @sjn, and added to the meetings page.
   - [x] @sjn - New Mastodon account created on https://fosstodon.org/@cpansec - please subscribe!
- [x] @sjn - Create a list of common/shared CPANSec resources & contact points/people to a private repo on GitHub.
   - @sjn - Done; Please check it out (look for it on GitHub), and help keep it correct and up-to-date!


## Next meeting date, time and location
- Next meeting is Wednesday 2025-03-26 @ 17:00UTC in #cpansec-discussion on Matrix (17:00 Europe/Amsterdam)

## 18:10 UTC - Meeting end

## 18:10 UTC - End
