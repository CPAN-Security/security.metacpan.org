---
title: Workshop: Vulnerability handling in open source software ecosystems
layout: page
toc: true
---

## Notes on «Open Source: Scenario Based Discussion»

These are notes for the «ENISA Workshop on "vulnerability handling in the context of open source software"». Original document is available in the [CPANSec-GPF](https://github.com/CPAN-Security/CPANSec-GPF/blob/main/events/DG-CONNECT-tabletop-2025-01-29/Open-Source%20Discussion%20Scenario%2029Jan.docx) repo (private).

* To update this text, please use the [working document for collaborative editing](https://cryptpad.fr/code/#/2/code/edit/50GScuKt2Kr3zIsYxw29ZK3J/) on cryptpad.
    * This document will be periodically be synced with the [notes on github](https://github.com/CPAN-Security/security.metacpan.org/blob/enisa-workshop/notes/ENISA-workshop-20250129-notes.md).


### Meeting details

* When: 2025-01-29, 14:00 - 17:00 CET (Brussels & online participation)
* Where: Physical Location: DG CONNECT (Rue de la Loi 51, Brussels)


### References & Background reading

* CPANSec, Hackeriet and Gurusoft AS [Feedback on NIS2 Implementing Guidance](https://github.com/CPAN-Security/security.metacpan.org/blob/enisa-workshop/docs/consultations/Feedback-on-implementing-guidance-for-NIS-2-security-measures-chapters-3-and-5.pdf) for chapters 3 (Incident Handling) and 6 (Secure Software Practices)


### Proposed Specifications

1. 

#### Objective

1. 

#### Participants

1. 

#### Structure

1. 

#### Key Focus Areas

1. (@tux) w.r.t. communication gaps and explore roles, I guess it would be good to address timelines and expected response times for communication gaps and roles.
1. (@tux) TimeZones are a major PITA and people can be on holiday.
1. (@tux) For CPAN there are no rules on what to do on critical CVEs when maintainers can temporary not be reached (illness, holiday, family business, whatever)

## Setting the Scene & Expectations

1.

### SQ: Cross-Border Communication & Coordination Mechanisms

1. (@tux) I think that EU based open-source teams are a great idea. See later notes
2. (@abraxxa) It should read 'open-source communities' (plural!), as there is no single one!
3. (@abraxxa) Having identical or very similar procedures in the different communities would make interaction easier with less friction

### Open-Source Community Challenges in Incident Response

1. (@tux) In resource constraints and delays due to volunteer-driven contributions, it is worth mentioning that in team-managed projects (CORE, toolchain,DBI, Mojolicious, ...) that no single team member is expected to have complete knowledge on all focus areas in the project.
   * The area that is vulnerable might require a certain team member, which may or may not be available.
2. (@abraxxa) Not getting notified quickly and in private, most of the time through public media.

### CRA Compliance Expectations and Gaps

1. 

## Scenario-Based discussion

1. 

### Simulated Incident Timeline

1. 

#### Incident Day (Hour 0-2)

> * A vulnerability is discovered in liblzma (used in XZ Utils) and disclosed on a public platform.

1. 

> * News reaches both CISA and the Foundations via an industry blog and social media.

1. 

> * ENISA and CSIRTs become aware through European vendor alerts.

1. 


#### Incident Day (Hours 3-6)

> * CISA starts a coordination channel, involving key open-source contributors, and industry partners.

1. (@sjn) What is the benefit of starting another coordination channel, instead of using relevant existing ones? What problems are presumably addressed (or solved) by creating another one?
   * The limiting factor in a volunteer-centric ecosystem is _available attention_. How can we make this work in communities that have little-to-no available attention to dedicate to this?
   * Also, there are "key open source contributors". "The Open Source community" does not exist as an entity. Instead it should be looked upon as a community of communities (of communities!), where there usual rule is that cross-ecosystem cooperation is NOT DONE.
   * Assuming that such a channel can be made useful in such a milieu is quite optimistic. Maybe it's better to put resources into endutinh existing forums and channels are made sustainable?

> * Open-Source Foundations contributors start analyzing the vulnerability and propose tactical fixes.

1. (@abraxxa) our tooling for this step is non-existing for non-Perl dependencies at the moment. If multiple (open-source) communities can provide compatible SBOMs, a central entity could analyze the impact throughout all those communities.
1. (@sjn) Not all Open Source communities have a Foundation backing them, and not all Open Source Foundation are "code hosting" at all, or in a way where they can contribute in the way imagined above.
   * Better option: Recommend or assume a suitable dedicated Steward organization is created, that can assist in this type of work, and that can operate on a commercially sustainable (and possibly not-for-profit) basis.

> * ENISA focuses on understanding the scope

1. (@tux) On CPAN, we talk about the river concept.
   * Up-river is CORE, which has huge impact on every module on CPAN, downriver might have less impact.
1. (@tux + @abraxxa) The known scope might be small initially, but when a release is required by many other releases, either direct and/or indirect, that scope might explode.
   * (`ExtUtils::MakeMaker`, `Test::Simple`, `Moose`, `DBI`, …).
   * As a consequence, you might have to deal with many authors.
   * (@sjn) this means that in the case of OSS ecosystems, the ecosystem steward may need to be involved from the outset.

> * ENISA contacts Open-Source Foundations requesting more information as part of the CNW secretariat.

1. (@sjn) Open Source Foundations are _not the only type of organization that may need to be involved_ (See above comment about "Not all Open Source communities have a Foundation backing them").
1. (@sjn) In the case where a vulnerability is found, the relevant OSS Maintainer needs to have been contacted, (presumably _by the Steward_!).
   * THIS MAY NOT ALWAYS BE POSSIBLE OR SUCCESSFUL
   * If possible, a remedy/fix need to be produced ASAP, though this may NOT be feasible. Sometimes, downstream repackagers (e.g. Linux distributions) or container assemblers may apply fixes without the involvement or blessing of the upstream author/maintainer.


#### Incident Day +1

> * Mainstream Media report on the vulnerability including outages in critical infra worldwide. (US and EU affected)

1. (@sjn) Aren't there a few more steps that happen before media gets involved?
   * e.g. in the case of responsible disclosure

> * Affected vendors in EU and US start reporting issues directly to Open-Source Foundations

1. (@sjn) What does this mean? 

> * An intermediate fix is proposed and shared with stakeholders.

1. (@abraxxa) Those quick fixes turned out to not cover all attack vectors and/or introduce new bugs (= new attack vectors). This causes several parties to be conservative regarding installing available fixed versions.
2. (@abraxxa) Multiple release trees (major versions) might be affected while the fix is usually only quickly available for the newest one.

> * CISA leads downstream impact analysis for U.S.-based users and infrastructures, while ENISA does the same for the EU via the CNW. CyCLoNE is actively monitoring.

1. 

> * Coordinated announcements are drafted, clarifying the status, patch availability, and mitigation steps.

1. 


#### Incident Week +1

> * Fixes are released, and impacted parties are notified via established communication channels.

1. 

> * The vulnerability is marked resolved, but follow-ups are scheduled to evaluate the response.

1. 


#### Incident Week +4

> * A joint post-mortem is conducted by key open-source contributors.

1. (@abraxxa) In what format?

> * Lessons learned are documented, focusing on improving coordination, grapevine mechanisms, and vendor engagement practices.

1. 


### Discussion-Based Conduct

1. 


### Proposed Questions for Discussion

1. 


#### 1. Incident Awareness and Notification

> 1.1. How do we improve the informal (grapevine mechanism) to ensure faster information sharing between open-source communities, CSIRTs and agencies like CISA and ENISA?

1. 

> 1.2. What proactive steps can ENISA take to strengthen its relationship with European and and/or non-EU open-source contributors?

1. 


#### 2. Initial response

> 2.1. How can the open-source community streamline communication with agencies during the critical first hours of an incident?

1. 

> 2.2. What systems or processes are needed to reduce duplication of effort when multiple parties are working on the same issue?

1. (@abraxxa) giving access to the privately reported vulnerabilities to those parties with auto-notificiation

> 2.3. What processes we should set up to support the reporting until the ENISA’s CRA reporting platform is available?

1. (@tux) A process to set-up might involve a cross-product info-sharing workforce, where e.g. Perl folk find the cause, and the Go people find the solution and the python people write up the explanation (shuffle the languages to your preference).
   * The focus would be purely technical.
2. (@abraxxa) The CRA article 16 only talks about manufacturers, which are defined in article 3 as those who put a product on the market. Vulnerabilites are often found in components of those products, so most of the time the affected products have to be determined, not the other way round.

#### 3. Coordination and Communication

> 3.1 Should CISA take the lead in coordinating the exchange of information with ENISA instead of the open-source foundations themselves?

1. 

> 3.2 What tools (e.g., Slack channels, shared dashboards) are most effective for cross-border and cross-industry collaboration?

1. 

> 3.3 How do we ensure that vendors and other impacted parties don’t overwhelm open-source maintainers during the incident response?

1. (@abraxxa) see my answer on 2.2

> 3.4 Should ENISA and CISA coordinate with the open-source community before producing LTTs for public use?

1. 

#### 4. Incident Mitigation and Industry-Wide Fixing

> 4.1 How can CISA and ENISA ensure that their downstream impact analysis results are effectively communicated to upstream open-source contributors?

1. 

> 4.2 What steps can be taken to prioritize fixes for the most critical users (e.g., critical infrastructure)?

1. 

#### 5. Post-Mortem and Feedback Loops

> 5.1 What methods can be used to collect lessons learned without overburdening open-source contributors?

1. 

> 5.2 How can post-mortem insights inform better CRA compliance mechanisms and reporting processes?

1. 

#### 6. Future Preparedness

> 6.1 How can the open-source groups participate in simulations or drills to prepare for future incidents?

1. 

> 6.2 What role can automation play in identifying and escalating critical vulnerabilities for coordinated response?

1. (@abraxxa) SBOMs made available by each language package registry would enable that.
