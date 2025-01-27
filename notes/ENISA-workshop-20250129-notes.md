---
title: Vulnerability handling in open source software ecoystems
layout: page
toc: true
---

# Notes on «Open Source: Scenario Based Discussion»

These are notes for the «ENISA Workshop on "vulnerability handling in the context of open source software"».
Source document is available in the [CPANSec-GPF](https://github.com/CPAN-Security/CPANSec-GPF/blob/main/events/DG-CONNECT-tabletop-2025-01-29/Open-Source%20Discussion%20Scenario%2029Jan.docx) repo (private).

## Meeting details

When: 2025-01-29, 14:00 – 17:00 CET (Brussels & online participation);
Where: Physical Location: DG CONNECT (Rue de la Loi 51, Brussels);


## Proposed Specifications

### Objective
### Participants
### Structure
### Key Focus Areas

1. (@tux) w.r.t. communication gaps and explore roles, I guess it would be good to address timelines and expected response times for communication gaps and roles.
1. (@tux) TimeZones are a major PITA and people can be on holiday.
1. (@tux) For CPAN there are no rules on what to do on critical CVEs when maintainers can temporary not be reached (illness, holiday, family business, whatever)

# Setting the Scene & Expectations


## SQ: Cross-Border Communication & Coordination Mechanisms

1. (@tux) I think that EU based open-source teams are a great idea. See later notes

## Open-Source Community Challenges in Incident Response

1. (@tux) In resource constraints and delays due to volunteer-driven contributions, it is worth mentioning that in team-managed projects (CORE, toolchain,DBI, Mojolicious, ...) that no single team member is expected to have complete knowledge on all focus areas in the project.
   * The area that is vulnerable might require a certain team member, which may or may not be available.


## CRA Compliance Expectations and Gaps



# Scenario-Based discussion


## Simulated Incident Timeline

### Incident Day (Hour 0-2)
### Incident Day (Hours 3-6)

1. ENISA focuses on understanding the scope

1. On CPAN, we talk about the river concept.
   * Up-river is CORE, which has huge impact on every module on CPAN, downriver might have less impact.
1. A scope might be small initially, but when a release has many direct and/or indirect dependencies, that scope might explode.
   * (`ExtUtils::MakeMaker`, `Test::Simple`, `Moose`, `DBI`, …).
   * As a consequence, you might have to deal with many authors.

### Incident Day +1
### Incident Week +1
### Incident Week +4


## Discussion-Based Conduct

## Proposed Questions for Discussion

### Initial response

2.3 A process to set-up might involve a cross-product info-sharing workforce,
where e.g. Perl folk find the cause, and the Go people find the solution and the
python people write up the explanation (shuffle the languages to your preference)
The focus would be purely technical.
