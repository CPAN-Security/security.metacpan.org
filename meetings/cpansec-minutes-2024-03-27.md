---
layout: single
toc: true
meeting_time: March 27th, 2024 17:00 UTC
title: Minutes 2024-03-27
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
    *   @sjn
    *   @timlegge (left early)
    *   @stigtsp
    *   @oalders
    *   @petek (left early)
*   Regrets
*   Absents

### Approve meeting minutes

*   Previous meeting minutes, up to and including 2024-03-13 was approved in PR#55 by @garu, @oalders and @sjn

*   These minutes to be approved in PR#56


### Quick summary of current work

1.  [CPAN Metadata & Software Bills of Materials](https://github.com/orgs/CPAN-Security/projects/1)
    *   @sjn - Meeting with Steve Springett (OWASP/CycloneDX) next week, about @sjn's supply chain SBOM roles document
    *   @sjn - Started planning proposals for metadata changes + SBOM at PTS
    *   @sjn - To start SBOM intro presentation
2.  [CPAN Privacy and Compliance](https://github.com/orgs/CPAN-Security/projects/9)
3.  [CPAN Provenance & Supply Chain Security](https://github.com/orgs/CPAN-Security/projects/3)
4.  [CPAN Security Outreach & Information](https://github.com/orgs/CPAN-Security/projects/12)
    *   @sjn - Update "how to report" page with contact info for PAUSE admins (ref. [https://pause.perl.org/pause/query?ACTION=pause\_04about#credits](https://pause.perl.org/pause/query?ACTION=pause_04about#credits))
    *   @timlegge - Write a blog post about ongoing CVE registration efforts with @stigtsp
5.  [CPAN Security Patch Tooling](https://github.com/orgs/CPAN-Security/projects/11)
6.  [CPAN Software Composition Analysis](https://github.com/orgs/CPAN-Security/projects/6)
7.  [CPAN Transparency Logs](https://github.com/orgs/CPAN-Security/projects/2)
8.  [CPAN Vulnerability Index](https://github.com/orgs/CPAN-Security/projects/10)
9.  [CPANSec Governance, Policy & Funding](https://github.com/orgs/CPAN-Security/projects/7)
    *   @sjn - Update charter to make user security issues with PAUSE out-of-scope, and refer these to pause-admin@perl.org. If the PAUSE folks would like to invite us at some point, we can update the charter again.
        *   Information around recent PAUSE account compromises has been lacking, and which would be great to have improved.
        *   Review basic opsec on PAUSE systems, it needs to be up-to-speed before we consider working on TUF. RJBS is working on PAUSE-in-the-cloud.
        *   CPAN ecosystem trust is also at stake.
        *   @ingy contacts NEILB to see if we (CPANSec) can help somehow
        *   @stigtsp found some removed dists: [https://github.com/batchpause/PAUSE-git/commit/32f55d453cef4abaed76ddcf454130569b342734](https://github.com/batchpause/PAUSE-git/commit/32f55d453cef4abaed76ddcf454130569b342734)
    *   @oalders, @timlegge, @leont and @sjn - Met on 2023-03-22 about budget that can be used for fundraising. Initial summary is at [https://cryptpad.fr/code/#/2/code/edit/ot0NCG1yLcqELuwiqZ2tZD2l/](https://cryptpad.fr/code/#/2/code/edit/ot0NCG1yLcqELuwiqZ2tZD2l/)


### Ongoing vulnerabilities

*   Two ongoing vulnerabilities being resolved.

### Operating changes

*   None.

### Upcoming events and deadlines

1.  PTS 2024-04-25 to 2024-04-28

### Elect next meeting chair and secretary

*   Chair: @oalders
*   Secretary: @sjn

### Next meeting date, time and location

*   Next meeting is April 10th 2024, 17:00 UTC in #cpan-security on TPRF Slack.

## 18:00 UTC – Meeting end

## 18:30 UTC – End
