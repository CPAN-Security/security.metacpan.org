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
  - working on alternative workflow tools for CVE based on YAML
  - easier to use than Vulnogram
  - possible bulk updates

  - @sjn @robrwo
    - questions about posting links to CVEs in Mastodon, BlueSky etc.
    - there is no RSS available for the CVE announcement list
    - @sjn suggests a custom emitter that produces content suitable for manual cut&paste (max 280 chars) for now. API auto-posting can come later

  - @timlegge
    - a copy of published CVEs should be kept in a public git repo
    - this should be a file copy, not clone of CNA repo, with sanity checks to ensure CVEs public
    - but MITRE has a public git repo

  - @robrwo
    - working on CVE Workflow documentation
    - CVE "style guide" thaat could be incorporated into @stigtsp's cna tool

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
    - suggested improving vulnerability disclosure process with time, phases and well-publiched steps.

  - @robrwo
    - experimental triage repo unused, should be deleted @stiptsp
    - give triage list members access to the CNA repo, and use that for issue tracking
    - create a kanban

- @sjn
  - Perl Toolchain Summit (PTS)
    - focusing on EU Cyber Resiliance Act (CRA) steward organisation
    - need to decide what the org looks like and set it up so it can be formally created
    - CPANSec would be a member, but separate from the stweard org
    - We have funding (via TPRF's budget) that we can choose to use to help fund a third room at PTS
    - we have to get the EU CRA to work for CPAN, we *have* to update the META spec to fully update the dependency graph.
    - @sjn calls for volunteers! This is critically important.

- @stigtsp
  - CPAN pURLs
    - spec does not support selector use case we need for CVEs (author/version constraints)
    - work in process
    - @sjn calls for volunteers to finish the work ASAP.

- @sjn
  - TPRF funding
  - @stiptsp
    - suggestion for sending message to the mailing list with a short budget
    - Goal: put together a formal decision-making process for CPANSec

- @robrwo
  - we need tools for accessing community documentation (license, security policy, etc)
  - meta spec/tools for downloading and showing these documents
  - possible PTS project

- @stigstp
  - demo of cna tool https://github.com/CPAN-Security/cna-tool
