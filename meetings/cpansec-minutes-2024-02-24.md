---
layout: page
toc: true
meeting_time: February 24th, 2024 15:00 UTC
title: Minutes 2024-02-24
---

# Meeting Minutes 2024-02-24

For additions or corrections, please reply to invitation mail or contact the meeting organizer ([@oalders](https://github.com/oalders)) or their secretary ([@timlegge](https://github.com/timlegge)).
Meeting minutes will be added below in this document.

* **Time**: on February 24, 2024, at 15:00 UTC. [Other timezones](https://www.timeanddate.com/worldclock/meetingdetails.html?year=2024&month=2&day=24&hour=15&min=0&sec=0&p1=187&p2=233&p3=250&p4=1129&p5=256), and [iCal download](https://www.timeanddate.com/scripts/ics.php?type=meet&p1=187&p2=233&p3=250&p4=1129&p5=256&year=2024&month=2&day=24&hour=15&min=0&sec=0)
* **Duration**: 1 hour, timeboxed. We start 30min earlier for introductions/socializing.
* **Location**: On TPRF's Slack server, in #cpan-security, w/video. Browser client (Chrome) is available and works.

This meeting happens regularly, typically every other Saturday at 15:00 UTC.


## 14:30 UTC – Pre-meeting socializing

1. No agenda :-)
2. If you're a newcomer, please come early so you can introduce yourself, and we ourselves!

## 15:00 UTC – Meeting begin

### Welcome – @sjn

* @sjn welcomed all in @oalders absence
* @timlegge took minutes
* Attendees: @stigtsp, @tux, @sjn, @ingy, @timlegge, Tina Müller
* Regrets: @oalders

### Approve previous meeting minutes

* This was missed and should be done at the next meeting

### Quick summary of current work

1. [CPAN Metadata & Software Bills of Materials](https://github.com/orgs/CPAN-Security/projects/1)
    - @sjn update - CPAN package url merged in spec - owasp channel for packageurl discussions created - upcoming spec extension for version ranges.
    - Soon we can use it to specify depends and requirements (including outside cpan).
    - pkgurl is necessary for SBOMs to refer to depends in a standard way.
    - Question from @ingy regarding SBOM and alien - @sjn yes you can specify external dependencies - including github releases but not general things like DNS service
    - @tux discussed reporting on generated SBOM - people need to see example outputs for understanding how to get there – @sjn docs are WIP
2. [CPAN Privacy and Compliance](https://github.com/orgs/CPAN-Security/projects/9)
3. [CPAN Provenance & Supply Chain Security](https://github.com/orgs/CPAN-Security/projects/3)
4. [CPAN Security Outreach & Information](https://github.com/orgs/CPAN-Security/projects/12)
    * @sjn SBOM draft branch is describing SBOM information as a WIP.
    * @sjn looking at the language that other groups are using and the terms in use. Proposing some new naratives. Eg "3rd party components" should be called "2nd party" for opensource components
    * @tux - advise to end users about the issues, you might be vulnerable - how SBOM helps, how to fix software, give users a path
    * @tina muller maintains a script to extract SBOM data from a package at suse
        * [openSUSE devel:languages:perl](https://build.opensuse.org/project/show/devel:languages:perl)
        * [All CPAN packages starting with A](https://build.opensuse.org/project/show/devel:languages:perl:CPAN-A)
    * @sjn: get metadata from a CPAN package to get the dependencies for use in determining dependencies, etc.
    * @stigtsp: are distro packaging details in scope for SBOM security for us?
        * @sjn yes becasue the packageurl is necessary to allow us to find the items.
5. [CPAN Security Patch Tooling](https://github.com/orgs/CPAN-Security/projects/11)
6. [CPAN Software Composition Analysis](https://github.com/orgs/CPAN-Security/projects/6)
7. [CPAN Transparency Logs](https://github.com/orgs/CPAN-Security/projects/2)
8. [CPAN Vulnerability Index](https://github.com/orgs/CPAN-Security/projects/10)
9. [CPANSec Governance, Policy & Funding](https://github.com/orgs/CPAN-Security/projects/7)
    - @sjn reach out if you are interested in the discussion of the decisions and charter
        - @sjn WIP: simple majority for most things, charter changes require more agreement (add particulars)

### Ongoing Discussions

1. SBOM generation (PAUSE, Dist::Zilla, both?)
    - @sjn some things at the author level, some tooling is needed and will likely be used as well as pause and metacpan (final pkg url).
    - @sjn volunteered to provide a session to demonstrate/discuss what is required in an SBOM file
2. Moving to cpan-security-advisory YAML format v2 (brian d foy email)
    - @tux had a discussion with brian regarding the use of his Test module.
    - @stigtsp question on how to consume the data
    - @tux is open to changing the module to an api versus the data direct from brian's repo.
    - @tux is looking ta the RedHat advisory and the formats of the data - it is a work in progress.
    - @tux would like to read the info and give back the information is a standard format in the future.  Net::CVE gives you everything you need to interact.
    - @sjn - end users want the specific line number and file that a vulnerability is found in to help find out whether they are vulnerable
3. Group Name (last meeting's change)
    - @garu discussed on IRC - surprised by the group name change- should we change (working group is a well known group).
    - Should we change the group name back.
    - Table it till the next meeting.
4. Adding CVEs to CPANSA- vulns that are missing them
    - @stigtsp gone through the CPANSA database registered 2 CVEs for old vulnerabilities - Debian follows the CVE database.  3 Mojolicious vulnerabilities and others that need CVEs (until 2020, should maybe also include 2018).
    - Deciding if we should have our own vuln identifiers or use CVEs
    - @stigtsp - initial discussion was to have our own ID - thinking we simply use the CVE database for everything we know.
    - Possibly a temp ID?  The IDs int he CPANSA ids have been changing over time.
    - CVEs are the well known identifier.
    - Go forward with CVE untill we need something else?
5. Checking if we can get crypto functions into core
    - @stigtsp - does anyone know if this has been proposed?  Getting the verification functions would be ideal for TUF and similar
6. CVE advisories to MetaCPAN pages for distributions
    - @stigtsp - nothing new but hope to get some things added to the pages
7. Discuss the TUF implementation briefly
    - @stigtsp - tuf implements repo and author signing - proper signing with attack mitigations - started looking at it but no progress - we need a CPAN implementation - for pause to do repo signing and possibly author.
    - sjn: is CycloneDX related?
    - @ingy - high level implementation is not large (maybe) - increases the profile and credibility of Perl and would be a good thing.
    - @sjn - can @ingy and @stigtsp put together something in a project for what we need to do - will be very important for funding, etc.

### Ongoing vulnerabilities

1. Vince issue is being transfered to GitHub
    - @stigtsp - not a vulnerability that really affects us (much)

### Operating changes

1. Proposal to use CC-BY-SA-4.0 as a content license in CPANSec for general web site content
    - @timlegge, @stigtsp, @sjn vote to use CC-BY-SA-4.0
    - ingy abstain
    - motion carried
    - @stigtsp - we should scheck that CC-BY-SA-4.0 is compatible for vulnerability info
2. Vince Portal Access
    - Requesters need to have signed the pre-release-disclosure.md
    - One current requester who has not signed

### Upcoming events and deadlines

1. [Perl Toolchain Summit](https://perltoolchainsummit.org/pts2024/) - Lisbon, Portugal end of April 2024.

### Elect the next meeting's organizer and their secretary

- @sjn - Organize
- @timlegge - Secretary

Next meeting is Wed March 13th @ 17:00UTC on TPRF Slack.

## 16:30 UTC – Meeting end

1. Post-meeting hangout :-)
2. If you're a newcomer, please hang out a little extra if you have any questions or concerns!
3. Feedback on meeting execution. Should something be improved for the next one?
4. Next meeting's organizer (or their secretary) sends the invitation email!

## 16:40 UTC – End
