---
title: Vulnerability handling in open source software ecoystems
layout: page
toc: true
---

# Notes on «Open Source: Scenario Based Discussion»

These are notes for the «ENISA Workshop on "vulnerability handling in the context of open source software"».
Source document is available in the [CPANSec-GPF](https://github.com/CPAN-Security/CPANSec-GPF/blob/main/events/DG-CONNECT-tabletop-2025-01-29/Open-Source%20Discussion%20Scenario%2029Jan.docx) repo (private).

## Meeting details

* When: 2025-01-29, 14:00 – 17:00 CET (Brussels & online participation);
* Where: Physical Location: DG CONNECT (Rue de la Loi 51, Brussels);


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

> * A vulnerability is discovered in liblzma (used in XZ Utils) and disclosed on a public platform.

> * News reaches both CISA and the Foundations via an industry blog and social media.

> * ENISA and CSIRTs become aware through European vendor alerts.


### Incident Day (Hours 3-6)


> * CISA starts a coordination channel, involving key open-source contributors, and industry partners.

> * Open-Source Foundations contributors start analyzing the vulnerability and propose tactical fixes.

> * ENISA focuses on understanding the scope

1. (@tux) On CPAN, we talk about the river concept.
   * Up-river is CORE, which has huge impact on every module on CPAN, downriver might have less impact.
1. (@tux) A scope might be small initially, but when a release has many direct and/or indirect dependencies, that scope might explode.
   * (`ExtUtils::MakeMaker`, `Test::Simple`, `Moose`, `DBI`, …).
   * As a consequence, you might have to deal with many authors.

> * ENISA contacts Open-Source Foundations requesting more information as part of the CNW secretariat.


### Incident Day +1

> * Mainstream Media report on the vulnerability including outages in critical infra worldwide. (US and EU affected)

> * Affected vendors in EU and US start reporting issues directly to Open-Source Foundations

> * An intermediate fix is proposed and shared with stakeholders.

> * CISA leads downstream impact analysis for U.S.-based users and infrastructures, while ENISA does the same for the EU via the CNW. CyCLoNE is actively monitoring.

> * Coordinated announcements are drafted, clarifying the status, patch availability, and mitigation steps.


### Incident Week +1

> * Fixes are released, and impacted parties are notified via established communication channels.

> * The vulnerability is marked resolved, but follow-ups are scheduled to evaluate the response.


### Incident Week +4

> * A joint post-mortem is conducted by key open-source contributors.

> * Lessons learned are documented, focusing on improving coordination, grapevine mechanisms, and vendor engagement practices.


## Discussion-Based Conduct

## Proposed Questions for Discussion

### 1. Incident Awareness and Notification

> 1.1. How do we improve the informal (grapevine mechanism) to ensure faster information sharing between open-source communities, CSIRTs and agencies like CISA and ENISA?


### 2. Initial response

> 2.1. How can the open-source community streamline communication with agencies during the critical first hours of an incident?

> 2.2. What systems or processes are needed to reduce duplication of effort when multiple parties are working on the same issue?

> 2.3. What processes we should set up to support the reporting until the ENISA’s CRA reporting platform is available?

1. (@tux) A process to set-up might involve a cross-product info-sharing workforce, where e.g. Perl folk find the cause, and the Go people find the solution and the python people write up the explanation (shuffle the languages to your preference).
      * The focus would be purely technical.


### 3. Coordination and Communication

> 3.1 Should CISA take the lead in coordinating the exchange of information with ENISA instead of the open-source foundations themselves?

> 3.2 What tools (e.g., Slack channels, shared dashboards) are most effective for cross-border and cross-industry collaboration?

> 3.3 How do we ensure that vendors and other impacted parties don’t overwhelm open-source maintainers during the incident response?

> 3.4 Should ENISA and CISA coordinate with the open-source community before producing LTTs for public use?


### 4. Incident Mitigation and Industry-Wide Fixing


> 4.1 How can CISA and ENISA ensure that their downstream impact analysis results are effectively communicated to upstream open-source contributors?

> 4.2 What steps can be taken to prioritize fixes for the most critical users (e.g., critical infrastructure)?


### 5. Post-Mortem and Feedback Loops

> 5.1 What methods can be used to collect lessons learned without overburdening open-source contributors?

> 5.2 How can post-mortem insights inform better CRA compliance mechanisms and reporting processes?


### 6. Future Preparedness

> 6.1 _How can the open-source groups participate in simulations or drills to prepare for future incidents?_


> 6.2 _What role can automation play in identifying and escalating critical vulnerabilities for coordinated response?_

