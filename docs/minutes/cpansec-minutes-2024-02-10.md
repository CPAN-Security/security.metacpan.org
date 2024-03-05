---
layout: page
---

# Minutes 2024-02-10

Meeting was on Saturday February 10th 2024, at 15:00 UTC, on the TPRF Slack server, in the #cpan-security channel.


## Attendees, absents & regrets

- Attendees
    - @oalders, @tux, @timlegge, @leont, @stigtsp, @sjn
- Regrets
    - @hydahy, @tinita


## Quick summary of current work

1. [CPAN Metatata & Software Bills of Materials](https://github.com/orgs/CPAN-Security/projects/1)
    - @tux – Create a guide with advice on what to do when they learn they have a vulnerability.
    - @sjn – Reported from FOSDEM and a FOSDEM Fringe SBOM workshop he attended.
2. [CPAN Privacy and Compliance](https://github.com/orgs/CPAN-Security/projects/9)
3. [CPAN Provenance & Supply Chain Security](https://github.com/orgs/CPAN-Security/projects/3)
4. [CPAN Security Outreach & Information](https://github.com/orgs/CPAN-Security/projects/12)
5. [CPAN Security Patch Tooling](https://github.com/orgs/CPAN-Security/projects/11)
6. [CPAN Software Composition Analysis](https://github.com/orgs/CPAN-Security/projects/6)
7. [CPAN Transparency Logs](https://github.com/orgs/CPAN-Security/projects/2)
8. [CPAN Vulnerability Index](https://github.com/orgs/CPAN-Security/projects/10)
    - @stigtsp – Reported on his conversation with Mickey. Work on exposing CVE data on MetaCPAN is ongoing. An API endpoint is already up (created at PTS 2023).
    - @stigtsp – Github actions not available not for converting CPAN::Audit vulns to @garu's new format; Looking for alternatives
    - @stigtsp – Registering CVE identifiers for older unpublished vulnerabilities, to communicate security updates that may haven't been applied downstream
9. [CPAN-SEC Governance, Policy & Funding](https://github.com/orgs/CPAN-Security/projects/7)
    - @sjn – TPRF is looking for someone to lead the application project. @sjn and @oalders have been contacted.

## Ongoing vulnerabilities

- @stigtsp – libwww-perl DoS vuln probably not in scope, we recommend making it public.

## Operating changes

- Change of name: CPAN Security Group (short: CPANSec) – 2 voted in favor, 4 abstained

## Upcoming events and deadlines

1. TPRF Community Representatives meeting 2023-02-16 @ 17:30 UTC on TPRF Slack
2. PTS 2024 ([April 25-28 2024 in Lisbon, Portugal](https://blogs.perl.org/users/book/2024/02/announcing-the-perl-toolchain-summit-in-2024.html), organized by @garu, @book, @elbeho and @neilb)
3. German Sovereign Tech Fund, Application deadline in Q2 2024

## Next meeting date, organizer & secretary

- Time: Feb 24th 2024, at 15:00 UTC on TPRF Slack
- Organizer: @oalders
- Secretary: @timlegge
