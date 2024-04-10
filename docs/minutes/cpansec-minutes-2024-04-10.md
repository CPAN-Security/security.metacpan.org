----
layout: page
toc: true
meeting_time: April 10th 2024, 17:00 UTC
title: Minutes 2024-04-10
----

## Meeting details

*   **Time**: on {{ page.meeting_time | date_to_string: "ordinal", "US" }}, at {{ page.meeting_time | date: "%H:%M %Z" }}. ([Other timezones](https://www.timeanddate.com/worldclock/meetingdetails.html?{{ page.meeting_time | date: "year=%Y&month=%m&day=%d&hour=%H&min=%M&sec=0" }}&p1=256&p2=233&p3=1129&p4=250&p5=187); [iCal download](https://www.timeanddate.com/scripts/ics.php?type=meet&p1=256&p2=233&p3=1129&p4=250&p5=187&{{ page.meeting_time | date: "year=%Y&month=%m&day=%d&hour=%H&min=%M&sec=0" }}))
*   **Duration**: 1 hour, timeboxed. We start 30min earlier for introductions/socializing.
*   **Location**: On TPRF's Slack server, in #cpan-security, w/video.


## 16:30 UTC – Pre-meeting socializing

## 17:00 UTC – Meeting start

### Welcome

*   Meeting chair: @oalders
*   Meeting secretary: @sjn


### Attendees, absents & regrets

*   Attendees
    *   @oalders, @sjn, @ingydotnet, @stigtsp
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
    *   @oalders – had a meeting with TPRF on this. No progress.


### Previous vulnerabilities

*   @sjn – Above list useful for highlighting ongoing efforts, for a blog post or PTS presentation.

*   CVE-2022-48623 - https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2022-48623
    *   The Cpanel::JSON::XS package before 4.33 for Perl performs out-of-bounds accesses in a way that allows attackers to obtain sensitive information or cause a denial of service.
*   CVE-2023-52431 - https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2023-52431
    *   The Plack::Middleware::XSRFBlock package before 0.0.19 for Perl allows attackers to bypass a CSRF protection mechanism via an empty form value and an empty cookie (if signed cookies are disabled).
*   CVE-2021-47156 - https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-47156
    *   The Net::IPAddress::Util module before 5.000 for Perl does not properly consider extraneous zero characters in an IP address string, which (in some situations) allows attackers to bypass access control that is based on IP addresses.
*   CVE-2013-7488 - https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2013-7488
    *   perl-Convert-ASN1 (aka the Convert::ASN1 module for Perl) through 0.27 allows remote attackers to cause an infinite loop via unexpected input.
*   CVE-2021-47154 - https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-47154
    *   The Net::CIDR::Lite module before 0.22 for Perl does not properly consider extraneous zero characters at the beginning of an IP address string, which (in some situations) allows attackers to bypass access control that is based on IP addresses.
*   CVE-2018-25099 - https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2018-25099
    *   In the CryptX module before 0.062 for Perl, gcm\_decrypt\_verify() and chacha20poly1305\_decrypt\_verify() do not verify the tag.
*   CVE-2021-47157 - https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-47157
    *   The Kossy module before 0.60 for Perl allows JSON hijacking because of X-Requested-With mishandling.
*   CVE-2013-4184 - https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2013-4184
    *   Perl module Data::UUID from CPAN version 1.219 vulnerable to symlink attacks
*   CVE-2020-36829 - https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-36829
    *   The Mojolicious module before 8.65 for Perl is vulnerable to secure\_compare timing attacks that allow an attacker to guess the length of a secret string. Only versions after 1.74 are affected.
*   CVE-2018-25100 - https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2018-25100
    *   The Mojolicious module before 7.66 for Perl may leak cookies in certain situations related to multiple similar cookies for the same domain. This affects Mojo::UserAgent::CookieJar.
*   CVE-2020-36827 - https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-36827
    *   The XAO::Web module before 1.84 for Perl mishandles < and > characters in JSON output during use of json-embed in Web::Action.
*   CVE-2014-3230 - https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2014-3230
    *   The libwww-perl LWP::Protocol::https module 6.04 through 6.06 for Perl, when using IO::Socket::SSL as the SSL socket class, allows attackers to disable server certificate validation via the (1) HTTPS\_CA\_DIR or (2) HTTPS\_CA\_FILE environment variable.
*   CVE-2021-47208 - https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-47208
    *   The Mojolicious module before 9.11 for Perl has a bug in format detection that can potentially be exploited for denial of service.
*   CVE-2021-47155 - https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-47155
    *   The Net::IPV4Addr module 0.10 for Perl does not properly consider extraneous zero characters in an IP address string, which (in some situations) allows attackers to bypass access control that is based on IP addresses.
*   CVE-2019-6977 - https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-6977
    *   gdImageColorMatch in gd\_color\_match.c in the GD Graphics Library (aka LibGD) 2.2.5, as used in the imagecolormatch function in PHP before 5.6.40, 7.x before 7.1.26, 7.2.x before 7.2.14, and 7.3.x before 7.3.1, has a heap-based buffer overflow. This can be exploited by an attacker who is able to trigger imagecolormatch calls with crafted image data.


### Ongoing and updated vulnerabilities

*   CVE-2013-4407 - https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2013-4407
    *   HTTP::Body::Multipart in the HTTP-Body 1.08, 1.17, and earlier module for Perl uses the part of the uploaded file's name after the first "." character as the suffix of a temporary file, which makes it easier for remote attackers to conduct attacks by leveraging subsequent behavior that may assume the suffix is well-formed.
    *   @stigtsp – This fix was thought to be real, but it wasn't. Some Linux distros (Debian, Gentoo) patched independently anyway, but many didn't. Version 1.23 has been fixed. Work ongoing for fixing confusion and communication breakdowns.

*   @timlegge working on blogpost laying out this work and why we're doing it.
*   @stigtsp – Shared that he is looking into ongoing PAUSE issues, @andk intends to share info eventually.


### Operating changes

*   @sjn – Proposal: New project for ongoing CVE visibility work
    *   @timlegge - no problems with this
    *   @sjn - useful for visibility and budgeting and fundraising
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
