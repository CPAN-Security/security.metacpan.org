---
layout: page
title: Open Source project life-cycle states and indicators
description: A proposed list of states and their indicators one can find an Open Source project in
toc: true
mermaid: true
---

## Document status: ⚠️  DRAFT

> [!CAUTION]
> What you see here is a DRAFT of an overview of Open Source project life-cycle conditions and needs, created by the CPAN Security Group (CPANSec).
> As long as this document is in DRAFT, all of the points and ideas below are _suggestions_, and open to revision, deletion or amending – by you!
>
> - Contribute on Github: [https://github.com/CPAN-Security/security.metacpan.org/tree/lifecycle/docs/foss-project-lifecycle.md](https://github.com/CPAN-Security/security.metacpan.org/tree/lifecycle/docs/foss-project-lifecycle.md)
> - Discuss on IRC: [ircs://ssl.irc.perl.org:7063/#cpan-security](ircs://ssl.irc.perl.org:7063/#cpan-security)
> - Discuss on Matrix: [https://matrix.to/#/#cpansec:matrix.org](https://matrix.to/#/#cpansec:matrix.org)

This document is background material and notes for the [CycloneDX OSS Sustainability WG](https://docs.google.com/document/d/1IZnHEwzz1N7LbChVkZTE_dfo3I2np8rULssq5I2wchM/edit).
In this project we try to help both OSS project's Maintainers communicate their needs and requirements, as well as help the share important information that may assist their user's _business continuity challenges_.


## Project Need Indicators

States in **bold** exist on CPAN.

| Needs        | Maint = 0 | Maint = 1 | Maint > 1 | Maint needs increase | Maint is declining | Response time | Claim source |
| :----------- | :-------: | :-------: | :-------: | :------------------- | :----------------- | :-----------: | :----------- |
| **NEEDHELP** | no        | YES       | YES       | YES                  | no                 | LOW           | Maintainer   |
| **HANDOFF**  | no        | YES       | no        | YES                  | YES                | LOW           | Maintainer   |
| **ADOPTME**  | YES       | no        | no        | YES                  | no                 | NONE          | Ecosystem    |
| NEEDFUNDING  | no        | YES       | YES       | no                   | no                 | LOW           | Maintainer   |
| NEEDSUPPORT  | no        | YES       | YES       | no                   | no                 | LOW           | Maintainer   |


1. NEEDHELP – The project is understaffed, and requires additional co-maintainers for sustainable and continued development. (Ref: [PAUSE-2017](#references))
    * (number of maintainers is higher than 0)
    * (number of maintainers is too low)
1. HANDOFF – The project maintainer is looking for someone to take over the project as a new maintainer (Ref: [PAUSE-2017](#references))
    * (number of maintainers is 1)
    * (number of maintainers is about to reduce to 0)
1. ADOPTME – The project is abandoned, or the project maintainer has been confirmed _beyond reasonable doubt_ to be unresponsive, and therefore the project is made available for adoption (Ref: [PAUSE-2017](#references))
    * The project needs a new maintainer
    * (number of maintainers is 0)
    * (number of maintainers is too low)
1. NEEDFUNDING – This project needs funding
    * Workload is unsustainable with only a volunteer-level commitment
    * (number of maintainers is 1 or higher)
    * (number of maintainers does not need to change)
1. NEEDSUPPORT – This project needs non-funding support
    * Project growth and sustainability is hindered by lack of non-code contributions
    * Examples: Branding development; Code security audit; Event organizing; Documentation writing;
    * (number of maintainers is 1 or higher)
    * (number of maintainers does not need to change)
    * See [Enumeration of NEEDSUPPORT items](#enumeration-of-needsupport-items) for examples

### Enumeration of NEEDSUPPORT items

When a project signals they NEEDSUPPORT, this can imply any of a number of activities are needed assistance with.

Needs in **bold** are found in [CHAOSS-2020](#references).

1. Project Branding
    * Brand Development and Strategy
    * Brand Management and Implementation
1. **Code Review**
    * Development process review
    * Maintainability review
    * Secure Code review (SCR)
1. **Code Writing** and development
    * **Bug Triage**
    * CI/CD configuration
    * Feature implementation
    * Internationalization/I18N
    * Test writing
1. **Community Building and Management**
    * Culture and conduct
    * Diversity, Equity, Inclusion
    * Forum management, moderation and support
    * Governance development
    * Recruitment and on-boarding
1. Content Creation
    * Audio or Video Editing
    * Podcast Hosting or Participation
    * **Writing Articles** / Blogging
    * Script writing
    * Creating Infographics
    * Writing Case studies / White papers
1. **Creative Work and Design**
    * Creative copywriting
    * Visual / graphic design
    * Animation / motion graphics
    * Photography / videography
    * Audio design
1. **Documentation Authorship**
    * Automation and Completeness
    * Consistency, Voice and Tone
    * Indexing, Discoverability, Keyword Analysis and SEO
    * **Localization/L10N and Translation**
    * Technical writing
    * User or Stakeholder Relevance
1. **Event Organizing**
    * Conferences, Meetups, Hackathons or other gatherings for social knowledge-sharing
    * Online events, webinars or classes/training
    * Program committee work
    * Social and networking events
1. **Financial Management**
    * Fund-raising
    * Grant management
1. **Legal Counsel**
    * License Conflict Resolution
    * License Enforcement
    * Trademark Defense
    * Trademark Registration
1. Mentorship (Ref: [MSFTOSS-2024](#references))
    * Code contribution
    * Documentation
    * Governance
    * Outreach and Communication
    * Security
1. Outreach
    * Content Strategy, Planning and Auditing
    * Industry/Stakeholder/OSPO Outreach and Assistance
    * **Marketing and Campaign Advocacy**
    * Media relations
    * Developer relations
    * **Public Relations - Interviews with Technical Press**
    * **Social Media Management** and presence
    * **Speaking at Events** and Conference Presentations
    * **Website Development**
1. Packaging
    * Adaptation new packaging ecosystems
    * Container assembly
    * Package maintenance
    * Release management
    * Tooling development
1. **Quality Assurance and Testing**
    * Test data creation
    * Increase code coverage
1. Software and systems design review
    * Review software architectural design patterns
    * Review virtualized infrastructure design patterns
    * Cryptography review
    * Threat modeling (privacy, safety, security)
    * API Modeling
    * Data Modeling
    * Dependency Review
    * Sustainability Review
1. **Security-Related Activities**
    * Hardening
    * Writing automated security tests
1. **Teaching and Tutorial Building**
    * Course/training material development
    * E-learning module development
1. Community infrastructure and hosting
    * Chat forum hosting
    * DNS and Email hosting
    * Test infrastructure (CI/CD) hosting
    * Other hosted community services
1. **Troubleshooting and Support**
    * **User Support and Answering Questions**
1. **User Interface, User Experience, and Accessibility**
    * UX/UI design
    * Web / Mobile design
    * Email & newsletter design
    * Accessibility audit

## Project Support Indicators

| Offers       | Maint = 0 | Maint = 1 | Maint > 1 | Maint needs increase | Maint is declining | Response time | Claim source |
| :----------- | :-------: | :-------: | :-------: | :------------------- | :----------------- | :-----------: | :----------- |
| MAINTAINED   | no        | YES       | YES       | no                   | no                 | OK            | Maintainer   |
| CASUAL       | no        | YES       | YES       | YES                  | no                 | LOW           | Maintainer   |
| DONE         | no        | YES       | no        | no                   | no                 | LOW           | Maintainer   |
| LEASTEFFORT  | no        | YES       | YES       | no                   | no                 | MINIMUM       | Maintainer   |
| DEPRECATED   | no        | YES       | no        | no                   | no                 | SECURITY      | Maintainer   |
| SECURITYONLY | no        | YES       | YES       | YES                  | no                 | SECURITY      | Maintainer   |
| SUPERSEEDED  | no        | YES       | YES       | no                   | no                 | NONE          | Maintainer   |
| UNMAINTAINED | no        | YES       | YES       | YES                  | no                 | NONE          | Maintainer   |


1. CASUAL – This project is only maintained on a casual basis (Ref: [CASUAL-2016](#references))
    * Response time expectations should be low
    * (number of maintainers is 1 or higher)
    * (number of maintainers increase may be desired)
1. DEPRECATED – The project maintainer recommends that this project is not to be used
    * (number of maintainers is 0)
    * (number of maintainers does not need to change)
1. DONE – The project is considered "Done", and while it is maintained, no further development is needed or expected
    * (number of maintainers is 1 or higher)
    * (number of maintainers does not need to change)
1. MAINTAINED – The project is maintained (default state)
    * (number of maintainers is higher than 0)
    * (number of maintainers increase may be desired)
1. SECURITYONLY – The project receives security fixes only
    * (number of maintainers is 1 or higher)
    * (number of maintainers increase may be desired)
1. SUPERSEEDED – This project is considered by the Maintainer have been replaced by another project
    * (number of maintainers is 0 or higher)
    * (number of maintainers does not need to change)
1. UNMAINTAINED – This project is not actively maintained (Ref: [UNMAINTED-2023](#references))
    * Response time expectations should be none
    * (number of maintainers is 1 or higher)
    * (number of maintainers increase may be desired)


## Project Ecosystem States

States in **bold** exist on CPAN.

| States       | Maint = 0 | Maint = 1 | Maint > 1 | Maint needs increase | Maint is declining | Response time | Claim source |
| :----------- | :-------: | :-------: | :-------: | :------------------- | :----------------- | :-----------: | :----------- |
| COMPROMISED  | no        | YES       | YES       | no                   | no                 | NONE          | Ecosystem    |
| CUSTODY      | YES       | no        | no        | YES                  | no                 | SECURITY      | Ecosystem    |
| DELISTED     | YES       | YES       | YES       | no                   | no                 | NONE          | Ecosystem    |
| DUAL         | no        | YES       | YES       | no                   | no                 | OK            | Ecosystem    |
| **NOXFER**   | no        | YES       | no        | no                   | no                 | NONE          | Ecosystem    |
| UNREACHABLE  | no        | YES       | YES       | no                   | no                 | ERROR         | Ecosystem    |
| UNRESPONSIVE | no        | YES       | YES       | no                   | no                 | NONE          | Ecosystem    |



### Project State Indicators

1. COMPROMISED – This project has a prevailing and substantial security compromise
    * Project has removed from the index due to security issues that have prevailed for a substantial time.
    * The project is expected to revert to its previous state after the offending issues have been resolved or mitigated.
    * (number of maintainers is not relevant)
1. CUSTODY – This project is under custodianship
    * The project is deemed as important for the ecosystem, and needs a trusted maintainer
    * (number of maintainers is 0)
1. DELISTED
    * The project has been removed from the ecosystem index due to extraordinary circumstances
    * The project is expected to revert to its previous state after the offending issues have been resolved or mitigated.
1. DUAL-LIFE – The project is a core component in the language, with updates published in the language ecosystem as well
    * This project is maintained by the language core team itself.
    * The project is both published as part of the core language, and through the language ecosystem.
    * Equivalent to the P5P special user on CPAN (Ref: [PAUSE-2017](#references))
1. NOXFER – The project is prevented from being transferred to new maintainers (Ref: [PAUSE-2017](#references))
    * The project maintainer has requested that this project is to be prevented from being adopted.
    * The project may still be forked under a new name.
    * (number of maintainers is not relevant)
1. UNREACHABLE – The project maintainers are not reachable
    * The project maintainer(s) has not been reachable through registered communication channels for a substantial time, due to reasons outside the control of the project.
        * e.g.: Expired domain, Email bounce, compromise/hijacked forums or channels, or other Forces Majeures beyond the Maintainer's control.
    * The project is expected to revert to its previous state after the offending issues have been resolved or mitigated.
    * (number of maintainers is not relevant)
1. UNRESPONSIVE – Project Maintainers are reachable but actively not engaging
    * The project maintainers(s) have not been responsive to ecosystem concerns for a substantial time, due to non-technical reasons.
        * e.g.: Maintainer does not respond to ecosystem concerns for personal reasons.
    * The project is expected to revert to its previous state after normal interaction resumes.


## Other project states, claims and metadata

1. Intended for commercial use (EU CRA signal for OSS Stewards)


### For consideration

1. CE_DECLARATION – A URL, linking to declaration of conformance to the EU Cyber Resilience Act, as required in Annex II, point 6; and Chapter III, Article 28; and in Chapter II Article 13(20).
1. CE_DOCUMENTATION – A URL linking to supporting information and instructions (Annex II, point 8)
1. CE_CONFORMITY_BODY – A URL pointing to the Conformity Assessment Body where this component has been registered (CRA Article 22(4) and Article 58(1))
1. CE_SUPPORT_END_DATE – The date for when the support for the component expires (Annex II, point 7)


## License and use of this document

* Version: 0.2.0
* License: [CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/deed)
* Copyright: © Salve J. Nilsen <sjn@oslo.pm>, Some rights reserved.

You may use, modify and share this file under the terms of the [CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/deed) license.


### Acknowledgements

Several people have been involved in the development of this document

* Salve J. Nilsen (main author)
* Georg Link


## References

* (SJN-2022) [What kind of non-technical "nice-to-haves" you would expect to see in a healthy #OpenSource #FLOSS community?](https://chaos.social/@sjn/109343732566572015), Published 2022-11-14.
* (CHAOSS-2020) CHAOSS [Types of Contributions](https://chaoss.community/?p=3432), First created 2020-02-20.
* (arXiv:2408.06723v1) [Sustaining Maintenance Labor for Healthy Open Source Software Projects through Human Infrastructure: A Maintainer Perspective](https://arxiv.org/pdf/2408.06723), Published 2024-08-13.
* (MSFTOSS-2024) [5 things we learned from sponsoring a sampling of our open source dependencies](https://opensource.microsoft.com/blog/2024/06/27/5-things-we-learned-from-sponsoring-a-sampling-of-our-open-source-dependencies/), Published 2024-06-27.
* (NEILB-2016) [It takes a community to raise a CPAN module](http://neilb.org/2016/02/13/it-takes-a-community.html), Published 2016-02-13.
* (PAUSE-2017) [The PAUSE Operating Model](https://pause.perl.org/pause/query?ACTION=pause_operating_model) Version 2 (section 4.5), published 2017-10-27.
* (UNMAINTED-2016) ![No Maintenance Intended](http://unmaintained.tech/badge.svg) [unmaintained.tech](http://unmaintained.tech/), Published 2016-01-13.
* (CASUAL-2023) ![Casual Maintenance Intended](https://casuallymaintained.tech/badge.svg) [casuallymaintained.tech](https://casuallymaintained.tech/), Published 2023-09-25.
