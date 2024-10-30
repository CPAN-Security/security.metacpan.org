## Meeting details

* 2024-10-02 17:00 UTC on #cpansec-discussion on Matrix

## 16:30 UTC – Pre-meeting socializing

*   Discuss organizing projects, swimlanes and issues (...)

## 17:00 UTC – Meeting start

### Welcome

*   Meeting chair: @timlegge
*   Meeting secretary: @tux & #team

### Attendees, absents & regrets

*   Attendees
    * @sjn
    * @stigtsp
    * @tux
    * @timlegge
*   Partly Absent
    * @garu

### Approve previous meeting minutes

*   Previous meeting minutes was approved by @sjn, @timlegge, & @stigtsp

### Quick summary of current work

1.  [CPAN Metadata & Software Bills of Materials](https://github.com/orgs/CPAN-Security/projects/1)
    *   …
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
    *   …

### TLS/HTTPS in core
*   Neither @BooK nor @leont present, so no updates

### German Sovereign Tech fund is open for applications
*   @sjn - stalled: work is registered in a spreadsheet
*   @sjn - had a chat with STF at #OSSummit
*   @sjn summarizes results - a company involvement (or any other business or institution) would smooth things. Ovid said he could help

### Ongoing vulnerabilities
*   @tux checked a possible candidate for a CVE in the Unicode area of perl CORE with p5p. No further action required
*   https://github.com/mojolicious/mojo/pull/1791 needs triage to see if this is a vulnerability. @stigtsp is working on a PR that addresses this

### Secure by Default
*   @stigtsp - Fedora started with patched cpanm
*   @timlegge & @stigtsp work on other distros
*   A blog-post is being worked on collectively

### Eclipse ORC WG
*   @sjn - short report about recent movements
    Horizontal standards workstream had it's first kickoff meeting.

### CycloneDX 1.7 Sustainability fields
*   @sjn - short report about WG progress: Bi-weekly meetings ongoing. Meetings are published on youtube

### CPAN Meta Requirements and PURLs
*   @sjn - stalled

### POSIX::2008 vulnerabilities
*   @stigtsp - Need  to create CVEs for https://github.com/briandfoy/cpan-security-advisory/blob/master/cpansa/CPANSA-POSIX-2008.yml

### SBOM/Supply Chain
*   @sjn - short report from #OSSummit in Vienna. @sjn met lots of people from OpenSSF and others, with many interesting conversations. Good trip!
*   @garu will try to start a (or more) module(s) around SBOM

### CNA Update
*   Still not enough people involved
*   @timlegge - locations need to be set for resources
*   @timlegge - what's needed? Tim will write a blog post with information for getting involved

### Manpower / Recruitment
*   @tux - This project needs more manpower. People currently are not enough available and those who do actual work might get overloaded. The project is too important to peter out
*   @sjn - how may STF funding help? This funding may help with involving people who aren't willing to volunteer
*   @sjn - do we need a comunity-manager? Vienna conversations may have triggered helpers
*   @sjn - possible recruitment opportunities during LPW

### CPANSA feed
*   @garu will work on stabilizing this week

### Upcoming events and deadlines

**Outreach** is important and needs to continue

1. PgDay Lowlands: @tux attended and talked to a lot of people. No real feedback on security issues. Lots of thoughts about setting up secure databases/encryption
1. [All Systems Go](https://all-systems-go.io/) - Sept. 25-26th, Berlin - @stigtsp attended and reports
1. [London Perl Workshop](https://act.yapc.eu/lpw2024/) - Saturday 26th October 2024 - we have two items in the agenda!

### Operating changes
*   @sjn - prefer 16:00 UTC because of clashes with other meetings

### Misc
*   @timlegge finally (his words) released stuff marginally related to CPANSec (a new release of Module::Signature and Crypt::OpenPGP)

### Next meeting date, time and location
*   Next meeting is 2024-10-16 (16 Oct 2024) @ 16:00UTC in #cpansec-discussion on Matrix (18:00 Europe/Amsterdam)
