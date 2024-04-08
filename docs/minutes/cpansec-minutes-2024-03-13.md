---
layout: page
---

# Minutes 2024-03-13

* **Time**: on March 13th 2024, at 17:00 UTC.
* **Duration**: 1 hour, timeboxed. We start 30min earlier for introductions/socializing.
* **Location**: On TPRF's Slack server, in #cpan-security, w/video.

## 16:30 UTC – Pre-meeting socializing

Salve J. Nilsen (@sjn) started the Huddle

## 17:00 UTC – Meeting start

### Welcome

- Meeting chair: Salve J. Nilsen (@sjn)
- Meeting secretary: Timothy Legge (@timlegge)

### Attendees, absents & regrets

#### Attendees
- Ingy döt Net (@ingydotnet)
- Salve J. Nilsen (@sjn)
- Timothy Legge (@timlegge)
- Tina Müller (@perlpunk)
- Stig Palmquist (@stigtsp)
- Breno G. de Oliveira (@garu)
- Olaf Alders (@oalders)

#### Regrets
- Peter Krawczyk
- José Joaquín Atria

#### Absents
  -

### Approve previous meeting minutes

- [cpansec-minutes-2024-01-06](cpansec-minutes-2024-02-06.md)
- [cpansec-minutes-2024-01-20](cpansec-minutes-2024-01-20.md)
- [cpansec-minutes-2024-02-10](cpansec-minutes-2024-02-10.md)
- [cpansec-minutes-2024-02-24](cpansec-minutes-2024-02-24.md)

Motion to approve all four minutes from @sjn

*Minutes Approved*

### Quick summary of current work

1. [CPAN Metadata & Software Bills of Materials](https://github.com/orgs/CPAN-Security/projects/1)
    - …
2. [CPAN Privacy and Compliance](https://github.com/orgs/CPAN-Security/projects/9)
    - @sjn - Cyber Resiliance Act (EU) information added.
    - @sjn - CE Mark - exemptions around OpenSource software (rules in place)
    - Review [reading list](https://security.metacpan.org/docs/readinglist.html) for details
3. [CPAN Provenance & Supply Chain Security](https://github.com/orgs/CPAN-Security/projects/3)
    - @sjn - Reading list completed
4. [CPAN Security Outreach & Information](https://github.com/orgs/CPAN-Security/projects/12)
    - @sjn – Website updates
    - @sjn the SBOM webpages are giving a good overview of what needs to be added to CPAN/METACPAN
    - @stigtsp - Replied to brian d foy and github discussion around adding support for Perl
    - @sjn and @stigtsp have joined the OpenSSF slack. Invite was added to the IRC channel
5. [CPAN Security Patch Tooling](https://github.com/orgs/CPAN-Security/projects/11)
    - Discussion of the use of CVE id versus homegrown number.
    - @garu - expressed concern if the CVE numbers go away we would have a problem.
    - there is no reason we cannot have a local ID to be used (that was somewhat assumed previously - how to manage)
    - @timlegge (post meeting minute update) if I remember correctly we planned to primarily reference the CVE but did not discount the need for an internal identifier
    - Deferred to PTS discussion
6. [CPAN Software Composition Analysis](https://github.com/orgs/CPAN-Security/projects/6)
    - …
7. [CPAN Transparency Logs](https://github.com/orgs/CPAN-Security/projects/2)
    - @sjn - OpenSSF has quite a bit of info on this topic
8. [CPAN Vulnerability Index](https://github.com/orgs/CPAN-Security/projects/10)
    - @stigtsp - Public facing Vulnerability Index. - possibly chat at PTS
9. [CPANSec Governance, Policy & Funding](https://github.com/orgs/CPAN-Security/projects/7)
    - @sjn: German Sovereign Tech fund are [open for applications](https://www.sovereigntechfund.de/programs/applications). Minimum amount to apply for is €150k. Check out their [example application form](https://www.sovereigntechfund.de/public/files/stf_blank_application_form.pdf) to see what they need from us.
   - @oalders - what could be funded.  How to size - what would they fund?
   - @sjn - scope is pretty wide - 2FA for pause, TUF (eg), improving security anywhere in opensource.
   - Trying to schedule a meeting - what kind of things we could/should do and a rough order of magnitude of the work (time, dollars, etc)
   - @timlegge - to look for a time for a meeting next week

### Ongoing vulnerabilities

- HTTP::Body (marked fixed by mistake) - @stigtsp and Torsten Raudssus (@getty) discussed and a patch has been proposed
- Session Token Bug @stigtsp discussed with Leon Timmermans (@leont) in January - some issues when passed to C code
- Two ongoing items are under discussion in closed communication
- stigtsp and timlegge are working on the old vulnerabilities (as listed in CPAN::Audit) to have CVEs issued as required

### Operating changes

- @stigtsp – Matrix channel coordination / workload
- the triage should be coordinated to make sure that things are communicated.
- @stigtsp - possibly look at trying to break down by who is interested in certain areas.  A project meeting for those interested in law and policy for example.
- Meeting minutes are approved on github PR in the future.

### Upcoming events and deadlines

1. [Perl Toolchain Summit 2024](https://perltoolchainsummit.org/pts2024/) in Lisbon, Portugal – April 25-28.
2. German Sovereign Tech Fund is open for applications now (deadline is “Spring 2024”)

### Elect next meeting chair and secretary

- Next meeting chair: @oalders
- Next meeting secretary: @sjn

### Next meeting date, time and location

- Next meeting is March 27 @ 17:00UTC on TPRF Slack.

## 18:07 UTC – Meeting end

## 18:30 UTC – End
