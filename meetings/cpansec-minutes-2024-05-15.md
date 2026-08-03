---
layout: single
toc: true
meeting_time: May 15th, 2024 17:00 UTC
title: Minutes 2024-05-15
---
## Meeting details

*   **Time**: on {{ page.meeting_time | date_to_string: "ordinal", "US" }}, at {{ page.meeting_time | date: "%H:%M %Z" }}. ([Other timezones](https://www.timeanddate.com/worldclock/meetingdetails.html?{{ page.meeting_time | date: "year=%Y&month=%m&day=%d&hour=%H&min=%M&sec=0" }}&p1=256&p2=250&p3=233&p4=1129&p5=187); [iCal download](https://www.timeanddate.com/scripts/ics.php?type=meet&p1=256&p2=250&p3=233&p4=1129&p5=187&{{ page.meeting_time | date: "year=%Y&month=%m&day=%d&hour=%H&min=%M&sec=0" }}))
*   **Duration**: 1 hour, timeboxed. We start 30min earlier for introductions/socializing.
*   **Location**: On TPRF's Slack server, in #cpan-security, w/video.


## 16:30 UTC – Pre-meeting socializing

## 17:00 UTC – Meeting start

### Welcome

*   Meeting chairs: @timlegge, @tux
*   Meeting secretary: @sjn

### Attendees
*   @tux
*   @sjn
*   @timlegge (left early)
*   @stigtsp
*   @book (arrived late)
*   @leont (arrived late)

### Regrets
*   @tinita
*   @oalders

### Absents


### Approve previous meeting minutes

*   Previous meeting minutes were approved in PR#65 by @oalders, @timlegge and @stigtsp

### Quick summary of current work

1.  [CPAN Metadata & Software Bills of Materials](https://github.com/orgs/CPAN-Security/projects/1)
2.  [CPAN Privacy and Compliance](https://github.com/orgs/CPAN-Security/projects/9)
3.  [CPAN Provenance & Supply Chain Security](https://github.com/orgs/CPAN-Security/projects/3)
4.  [CPAN Security Outreach & Information](https://github.com/orgs/CPAN-Security/projects/12)
    *   @sjn – Set up project: CVE Registration
    *   @stigtsp – New public Matrix channel thanks to @ingy and @stigtsp, on [https://matrix.to/#/#cpansec-discussion:matrix.org](https://matrix.to/#/#cpansec-discussion:matrix.org)
        *   Moderation rules and permanent setup on matrix.perl.org on the way
        *   @ingy and @stigtsp run and pay for the servers
        *   @ingy, @stigtsp and @tinita and @ilmari are moderators
    *   @stigtsp – Should we propose updates to perlsec and perlsecpolicy docs in time for 5.40.\*?
        *   What's written looks good; we could add some info on CPANSec
    *   @stigtsp – new project for "CPAN Secure by Default" (vote: unanimous in favor)
    *   @sjn – CoC to be added
5.  [CPAN Security Patch Tooling](https://github.com/orgs/CPAN-Security/projects/11)
6.  [CPAN Software Composition Analysis](https://github.com/orgs/CPAN-Security/projects/6)
7.  [CPAN Transparency Logs](https://github.com/orgs/CPAN-Security/projects/2)
8.  [CPAN Vulnerability Index](https://github.com/orgs/CPAN-Security/projects/10)
9.  [CPANSec Governance, Policy & Funding](https://github.com/orgs/CPAN-Security/projects/7)
    *   @sjn – Charter simplification committed
10.  CPAN CVE Registration
11.  CPAN Secure by Default


### Ongoing and updated vulnerabilities

*   None were discussed


### Operating changes

*   @timlegge – CNA progress update
    *   @stigtsp and @timlegge has discussed a little, I have done a little research but not much change.  Hope to contact the CVE folks next week to initiate the process
*   @sjn – Clarify the purpose of the mailing list. Who may join? What may (not) be discussed? How do we accept new signups? How do we decide if someone must leave? How do we change who gets to decide the above? Communicate this to the Perl NOC folks
    *   @stigtsp – Applications to internal lists are coming in.
    *   @stigtsp puts together draft rules.
    *   @sjn wants to add joining instructions to the charter under the "how to join" heading.
*   @sjn (or @book, if he can come) – HTTPS/TLS-out-of-the-box project for perl5.42. PSC mentioned @leont may want to lead the project as a CPANSec thing? (need confirmation)
    *   We'll also need to decide who is our single point of contact to PSC.
    *   can we manage a review of options
    *   if so, add a project under our GitHub
    *   is there grant money to fund something like this?
    *   PSC wants to have suggestions by September
    *   Long term commitment/fail graceful implementation required
    *   Official commitment CPANSec is confirmed.
        *   @BooK takes the project management job, with commitment to complete the whole project by PSC's deadline
        *   @leont maps out implementation options
    *   Progress reports during bi-weekly meetings
*   @stigtsp – securing cpanm has slow progress
    *   @miyagawa is onboard
*   @tux - Test::CVE
    *   docs improvements / illustrations in progress


### Upcoming events and deadlines

1.  @sjn – TPRF community representatives meeting Friday May 17th @ 17:30 UTC
2.  [Open Source Summit Europe](https://events.linuxfoundation.org/open-source-summit-europe/), Vienna – September 16-20, 2024
3.  [Nordic Software Security Summit](https://www.dfkompetens.se/utbildning/nordic-software-security-summit-2024/), Stockholm – September 23-24, 2024
4.  [London Perl and Raku Workshop 2024](https://act.yapc.eu/lpw2024/) – Saturday 26th October 2024
5.  German STF funding accepting applications "in the second quarter of 2024".

### Elect next meeting chair and secretary

*   Chair: @oalders
*   Secretary: @sjn

### Next meeting date, time and location

*   Next meeting is June 5th @ 16:00 UTC on TPRF Slack #cpan-security channel

## 18:00 UTC – Meeting end

## 18:30 UTC – End
