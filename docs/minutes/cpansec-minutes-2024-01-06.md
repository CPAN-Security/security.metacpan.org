---
layout: page
permalink: /docs/minutes/
---
# Minutes 2024-01-06

Meeting was on Saturday January 6th, 2024, at 12:00 UTC.


### Attendees & regrets

- Present: @stigtsp, @petek, @sjn, @timlegge
- Regrets: @leont, @tux, @jjatria, @oalders

### Quick summary of current work

1. [CPAN Metadata & Software Bills of Materials](https://github.com/orgs/CPAN-Security/projects/1)
    - @sjn - CPAN Supply-chain overview ongoing
    - @sjn - PackageURL discussion ongoing
2. [CPAN Transparency Logs](https://github.com/orgs/CPAN-Security/projects/2)
    - @stigtsp – CPAN snapshots & checksums prototype ongoing
3. [CPAN Provenance & Supply Chain Security](https://github.com/orgs/CPAN-Security/projects/3)
    - @stigtsp – Propose cpanm default to https
4. [CPAN Rich Metadata & Dependencies](https://github.com/orgs/CPAN-Security/projects/4)
    - @sjn – Outreach to #debian-perl (WIP)
5. [CPAN Software Composition Analysis](https://github.com/orgs/CPAN-Security/projects/6)
    - No activity
6. [CPAN-SEC Governance, Policy & Funding](https://github.com/orgs/CPAN-Security/projects/7)
    - @sjn – [Charter](https://security.metacpan.org/docs/charter.html)
        - Ongoing work
    - @stigsp – [Pre-Release Disclosure](https://security.metacpan.org/docs/pre-release-disclosure.html)
        - Out of draft
        - Privacy concerns around signing; To be discussed
        - Signing needs to be in sync with mailing list members (sync with perl-noc). @stigtsp looks into this.
        - Sign using a github commit.
    - @petek – TPRF and funding procedures
        - Small grants go via TPRF board. Meetings during the 3rd week of each month.
        - Large grants; TPRF can manage the funds. Earmarked funds will be handled by the TPRF treasurer. The Dancer project has a relevant charter (@petek will share).
7. [CPAN Privacy and Compliance](https://github.com/orgs/CPAN-Security/projects/9)
    - No activity
8. [CPAN Vulnerability Index](https://github.com/orgs/CPAN-Security/projects/10)
    - @stigtsp
        - bdfoy (CPAN::Audit author) has been invited to join us, unclear response.
        - Goal: create a website like [security.archlinux.org](https://security.archlinux.org). Work not begun.
9. [CPAN Security Patch Tooling](https://github.com/orgs/CPAN-Security/projects/11)
    - No activity
10. [CPAN Security Outreach & Information](https://github.com/orgs/CPAN-Security/projects/12)
    - @sjn – Proposal: "2024 – The CPAN year of «Secure by Default»"
        - 4 votes Aye, 0 votes Nay. We'll proceed with an announcement.
        - @petek & @sjn meet for text writing the coming week. @petek finds a suitable time to do this.

### Vulnerabilities

1. Spreadsheet::ParseExcel – CVE-2023-7101
    - Old known bug, high criticality, root cause of CVE-2023-7102
    - Responsive developer, produced a fix quickly
    - @timlegge & @stigtsp to write a post-mortem blog post
2. Spreadsheet::ParseXLSX – DoS/Memory bug
    - CVE id incoming
    - New maintainer for Spreadsheet::ParseXLSX found. Yay!
    - @timlegge: "PAUSE Operating Model's Takeover process is slow" – the reasons are understood from an ownership and community perspective, but it does present issue for timely resolution of security issues.
3. One more undisclosed vuln, through the VINCE portal
    - Info forthcoming depending on analysis

### Operating changes

1. Set up an end-to-end secure channel for discussing vulnerabilities
    - @stigtsp – We decide with a straw poll on IRC
        - Matrix channel set up, contact @stigtsp for invites
        - Signal channel set up, contact @stigtsp for invites
        - Invitiation requires signing the Pre Release Disclosure Agreement
2. Interaction with other related communities; and formalizing these relationships
    - @timlegge – VINCE Portal access granted.
        - @timlegge has been granted admin access, contact him for invites
        - Invitiation requires signing the Pre Release Disclosure Agreement

### Events and deadlines

1. FOSDEM, 2023-02-03 - 2023-02-04
    - Attendees we know of: @stigtsp, @sjn
2. PTS 2024 is TBA
3. German Tech Sovereignity Fund application deadline is TBA ("Spring 2024")


### Next meeting organizer & deputy

- @sjn; deputy is @stigtsp
