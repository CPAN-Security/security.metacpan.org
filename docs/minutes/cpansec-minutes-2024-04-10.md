---
layout: page
toc: true
meeting_time: April 10th, 2024 17:00 UTC
title: Minutes 2024-04-10
---

## Meeting details

*   **Time**: on {{ page.meeting_time | date_to_string: "ordinal", "US" }}, at {{ page.meeting_time | date: "%H:%M %Z" }}. ([Other timezones](https://www.timeanddate.com/worldclock/meetingdetails.html?{{ page.meeting_time | date: "year=%Y&month=%m&day=%d&hour=%H&min=%M&sec=0" }}&p1=187&p2=233&p3=250&p4=1129&p5=256); [iCal download](https://www.timeanddate.com/scripts/ics.php?type=meet&p1=187&p2=233&p3=250&p4=1129&p5=256&{{ page.meeting_time | date: "year=%Y&month=%m&day=%d&hour=%H&min=%M&sec=0" }}))
*   **Duration**: 1 hour, timeboxed. We start 30min earlier for introductions/socializing.
*   **Location**: On TPRF's Slack server, in #cpan-security, w/video.


## 16:30 UTC – Pre-meeting socializing

## 17:00 UTC – Meeting start

### Welcome

*   Meeting chair: @oalders
*   Meeting secretary: @sjn


### Attendees, absents & regrets

*   Attendees
    *   @oalders, @sjn, @ingydotnet, @stigtsp, @timlegge
*   Regrets
    *   @perlpunk, tmode
*   Absents
    *   …


### Approve previous meeting minutes

*   Previous meeting minutes were approved in PR#56 by @ingydotnet, @oalders and @timlegge


### Quick summary of current work

1.  [CPAN Metadata & Software Bills of Materials](https://github.com/orgs/CPAN-Security/projects/1)
    *   @sjn – Had a chat with S. Springett about supplychain-sbom.md, glossary and reading list. Got a little feedback, and aim to continue the conversation after CDX 1.6 is out.
    *   @sjn – Attended two OpenSSF meetings to see what they work on.
2.  [CPAN Privacy and Compliance](https://github.com/orgs/CPAN-Security/projects/9)
    *   …
3.  [CPAN Provenance & Supply Chain Security](https://github.com/orgs/CPAN-Security/projects/3)
    *   …
4.  [CPAN Security Outreach & Information](https://github.com/orgs/CPAN-Security/projects/12)
    *   …
5.  [CPAN Security Patch Tooling](https://github.com/orgs/CPAN-Security/projects/11)
    *   …
6.  [CPAN Software Composition Analysis](https://github.com/orgs/CPAN-Security/projects/6)
    *   …
7.  [CPAN Transparency Logs](https://github.com/orgs/CPAN-Security/projects/2)
    *   …
8.  [CPAN Vulnerability Index](https://github.com/orgs/CPAN-Security/projects/10)
    *   …
9.  [CPANSec Governance, Policy & Funding](https://github.com/orgs/CPAN-Security/projects/7)
    *   @sjn – Budget draft at [https://cryptpad.fr/sheet/#/2/sheet/edit/mEL6BAfL7I7ptOzMlx6q4NiI/](https://cryptpad.fr/sheet/#/2/sheet/edit/mEL6BAfL7I7ptOzMlx6q4NiI/)
    *   @sjn – Clarity around tasks and mandate. @sjn proposes a discussion on this at PTS


### Ongoing and updated vulnerabilities

*   CVE-2013-4407 - https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2013-4407
    *   HTTP::Body::Multipart in the HTTP-Body 1.08, 1.17, and earlier module for Perl uses the part of the uploaded file's name after the first "." character as the suffix of a temporary file, which makes it easier for remote attackers to conduct attacks by leveraging subsequent behavior that may assume the suffix is well-formed.
    *   @stigtsp – This fix was thought to be real, but it wasn't. Some Linux distros (Debian, Gentoo) patched independently anyway, but many didn't. Version 1.23 has been fixed. Work ongoing for fixing confusion and communication breakdowns.

*   @timlegge working on blog post laying out this work and why we're doing it.
*   @stigtsp – Shared that he is looking into ongoing PAUSE issues, @andk intends to share info eventually.


### Operating changes

*   @sjn – Proposal: New project for ongoing CVE visibility work
    *   @timlegge - no problems with this
    *   @sjn - useful for visibility and budgeting and fund-raising
    *   Vote: Unanimously **in favor**.
*   @sjn – Proposal: New project for getting upstream to discover and accept security patches that already are being applied downstream.
    *   @stigtsp - This should include efforts on \_finding\_ patches downstream.
    *   @stigtsp - This project requires separate efforts on reporting/outreach and finding patches.
    *   @timlegge - Given we're all volunteers, this may be quite a bit of work.
    *   @sjn - this may be good for helping in recruitment too.
    *   Vote: Unanimously **in favor**.
*   @sjn – Proposal: Decide on Code of Conduct. Let's use the same as TPRF
    *   Vote: Unanimously **in favor**.
*   @stigtsp – Re-evaluating if CPANSec should be a CNA
    *   @timlegge - to find out what's involved


### Upcoming events and deadlines

1.  PTS in two weeks!


### Elect next meeting chair and secretary

*   Chair: TBD at PTS
*   Secretary: TBD at PTS


### Next meeting date, time and location

*   Next meeting is in-person at PTS. New online meeting date will be decided then.


## 18:00 UTC – Meeting end

## 18:30 UTC – End
