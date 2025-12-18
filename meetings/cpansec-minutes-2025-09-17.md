---
layout: simple
toc: true
meeting_time: 2025-09-17 18:00 UTC
title: CPANSec bi-weekly minutes
---

## Agenda & Meeting Details 2025-09-17

## 17:30 UTC - Pre-meeting socializing
-   Socializing & getting up to speed before the meeting starts properly
-   Discuss organizing projects, swimlanes and issues (...)
-   Check and resolve technical (A/V) issues before the meeting starts
-   Come as you are!

## 18:00 UTC - Meeting start

### Welcome
-   Meeting chair:
-   Meeting scribe:

### Attendees, absents & regrets
-   Attendees @robrwo, @sjn
-   Partly attending @leon
-   Regrets @timlegge @tib

### Approve previous meeting minutes

## Agenda

### Current matters & Ongoing vulnerabilities
- JSON::XS and related vulns patched, coordinated releases

#### PAUSE
- [x] @tib Completed the 2 hardening fixes (already said on July meeting) on PAUSE, chased admins: they said they will merge and deploy soon
- [x] @tib Pentesting PAUSE: completed all things around forms (upload, create user, etc…). No vulnerability found
- [ ] @robrwo PAUSE rules update stalled

### New method of generating agenda
- https://github.com/orgs/CPAN-Security/projects/12 "For discussion" column
- evolving, need to think if Tasks to make this easier
- Needs issues from other projects/repos

### Separate meetings for projects/teams?

### CPAN Modules with vulnerable vendored (bundled/embedded) dependencies
- @robrwo stalled

### security.metacpan.org website
- [Header and teaser images for news and blog posts](https://github.com/CPAN-Security/security.metacpan.org/pull/186)
- Other blog posts

### CPAN::Meta v3 and SBOM
- https://github.com/CPAN-Security/perl-SBOM-Examples
- metadata is not usually installed
  - @sjn suggests raising issue for CPAN::Meta spec for Toolchain Gang
  - help CPAN maints create source SBOMs and make it easier for build tools
    like cpan/cpanminus etc can output SBOMs or use a tool too
   - @sjn explained different types of SBOMs (source v build)

### Document CNA Workflow
- @robrwo

### Security policies

#### Address blockers to adding security policies
- https://github.com/CPAN-Security/security.metacpan.org/issues/189 @robwo
  - Desire for a simpler, tiny policy
  - Dual-life modules
  - Projects with multiple maintainers who cannot agree
  - @tobyink had mentioned to @robrwo that people may not see separate doc vs inside POD
    - @leon considers this a feature: force users to see latest document
    - [need tools to extract metadata and show users community documentation](https://github.com/CPAN-Security/security.metacpan.org/issues/190)
      - but needs metadata saved somewhere on install
      - we need to limit scope: this is a security policy
  - @sjn points out that users are interested in the *promises* from a policy
  - @leon points out that we don't really know what authors actually need
  - @robrwo to elaborate on these issues, perhaps create sub-issues, and communicate with P5P about dual-life

#### Add Support and Security Considerations sections
- https://github.com/CPAN-Security/security.metacpan.org/issues/174
- More SBOM-friendly. Mainly reorganising.
- @robrwo has been separately thinking about relation of module POD to Security Policies
  - Need to document various "community health" documents and recommended POD sections

#### Popular modules without sec policies
- https://github.com/CPAN-Security/security.metacpan.org/issues/165
- @robrwo requested 100+ dists add policieS, about 15% added them
- stalled

### Social Media
- @sjn
- CVE announcements should have short versions but fits into 180 chars as an output and auto-published on bluesky/masto/reddit/perlmonks
