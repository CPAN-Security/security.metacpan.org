---
layout: single
toc: true
meeting_time: 2026-02-19 16:00 UTC
title: CPANSec bi-weekly minutes
---

## Agenda

- 2026-02-19 @ 16:00 UTC.

## Attending

- @sjn, @stigtsp, @robrwo, @timlegge

- Regrets @leont

## Minutes

- @stigtsp
  - CVE workflow
    - Working on alternative workflow tools for CVE based on YAML that is easier to use than Vulnogram
    - Allows possible bulk updates

  - @sjn @robrwo
    - Questions about posting links to CVEs in Mastodon, BlueSky etc.
    - There is no RSS available for the CVE announcement list
    - @sjn suggests a custom emitter that produces content suitable for manual cut&paste (max 280 chars) for now. API auto-posting can come later

  - @timlegge
    - Suggests that a copy of published CVEs should be kept in a public git repo
    - This should be a file copy, not clone of CNA repo, with sanity checks to ensure CVEs public
    - @robrwo notes that we host patches from CNA repo on CPANSec website, and could host CVEs there as well
    - @stigtsp MITRE has a public git repo, so this may be unnecessary

  - @robrwo
    - Working on CVE Workflow documentation
    - CVE "style guide" that could be incorporated into @stigtsp's cna tool

- @timlegge
  - OpenSSF Vulnerability Disclosure WG
    - AI slop is leading to many groups getting rid of bug bounties
    - WG is working on best practices to deal with slop
    - WG working on a survey of maintainers
      - time that users spend on open source projects?
      - are they paid for working on open source?
      - can they deal with AI reports?

- Discussions of vulnerabilties
  - Details omitted from agenda.

  - @sjn
    - Suggested improving vulnerability disclosure process with time, phases and well-publiched steps.

  - @robrwo
    - Experimental triage repo unused, should be deleted @stiptsp
    - Give triage list members access to the CNA repo, and use that for issue tracking
    - Create a kanban

- @sjn
  - Perl Toolchain Summit (PTS)
    - Focusing on EU Cyber Resiliance Act (CRA) steward organisation
    - Need to decide what the org looks like and set it up so it can be formally created
    - CPANSec would be a member, but separate from the stweard org
    - We have funding (via TPRF's budget) that we can choose to use to help fund a third room at PTS
    - we have to get the EU CRA to work for CPAN, we *have* to update the META spec to fully update the dependency graph.
    - @sjn calls for volunteers! This is critically important.

- @stigtsp
  - CPAN pURLs
    - Spec does not support selector use case we need for CVEs (author/version constraints)
    - Work in process
    - @sjn calls for volunteers to finish the work ASAP.

- @sjn
  - TPRF funding
  - @stiptsp
    - Suggestion for sending message to the mailing list with a short budget
    - Goal: put together a formal decision-making process for CPANSec

- @robrwo
  - We need tools for accessing community documentation (license, security policy, etc)
  - Meta spec/tools for downloading and showing these documents
  - Possible PTS project

- @stigstp
  - Demo of `cna` tool https://github.com/CPAN-Security/cna-tool
