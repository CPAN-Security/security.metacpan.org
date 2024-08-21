---
layout: page
title: Open Source project life-cycle states and indicators
description: A proposed list of states and their indicators one can find an Open Source project in
toc: true
mermaid: true
---

## Document status: ⚠️  DRAFT

> [!CAUTION]
> What you see here is a DRAFT of an Open Source project life-cycle conditions overview, by the CPAN Security Group (CPANSec).
> As long as this document is in DRAFT, all of the points and ideas below are _suggestions_, and open to revision, deletion or amending – by you!
>
> - Contribute on Github: [https://github.com/CPAN-Security/security.metacpan.org/tree/lifecycle/docs/foss-project-lifecycle.md](https://github.com/CPAN-Security/security.metacpan.org/tree/lifecycle/docs/foss-project-lifecycle.md)
> - Discuss on IRC: [ircs://ssl.irc.perl.org:7063/#cpan-security](ircs://ssl.irc.perl.org:7063/#cpan-security)
> - Discuss on Matrix: [https://matrix.to/#/#cpansec:matrix.org](https://matrix.to/#/#cpansec:matrix.org)


## Table of life-cycle states

States in **bold** already exist on CPAN.

| State        | Maint = 0 | Maint = 1 | Maint >= 1 | Maint needs increase | Maint is declining | Response time | Submitter  |
| ------------ | --------- | --------- | ---------- | -------------------- | ------------------ | ------------- | ---------- |
| **NEEDHELP** | no        | YES       | YES        | YES                  | no                 | LOW           | Maintainer |
| **HANDOFF**  | no        | YES       | no         | YES                  | YES                | LOW           | Maintainer |
| **ADOPTME**  | YES       | no        | no         | YES                  | no                 | NONE          | Ecosystem  |
| CUSTODY      | YES       | no        | no         | YES                  | no                 | LOW           | Ecosystem  |
| ACTIVE       | no        | YES       | YES        | no                   | no                 | OK            | Maintainer |
| DONE         | no        | YES       | YES        | no                   | no                 | LOW           | Maintainer |
| UNMAINTAINED | no        | YES       | YES        | no                   | no                 | NONE          | Maintainer |
| CASUAL       | no        | YES       | YES        | no                   | no                 | LOW           | Maintainer |
| NEEDFUNDING  | no        | YES       | YES        | no                   | no                 | LOW           | Maintainer |
| NEEDSUPPORT  | no        | YES       | YES        | no                   | no                 | LOW           | Maintainer |
| **NOXFER**   | no        | YES       | YES        | no                   | no                 | NONE          | Ecosystem  |
| COMPROMISED  | YES       | YES       | YES        | no                   | no                 |               | Ecosystem  |
| DISCOURAGED  | YES       | YES       | YES        | no                   | no                 | NONE          | Ecosystem  |
| DELISTED     | YES       | YES       | YES        | no                   | no                 | NONE          | Ecosystem  |


### State indicators

1. ACTIVE – The project is maintained (default state)
    * (number of maintainers is higher than 0)
    * (number of maintainers does not need to change)
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
1. NOXFER – The project is prevented from being transferred to new maintainers (Ref: [PAUSE-2017](#references))
    * The project has been prevented from being adopted, but may still be forked
    * (number of maintainers is not relevant)
1. CUSTODY – This project is under custodianship
    * The project is deemed as important for the ecosystem, and needs a trusted maintainer
    * (number of maintainers is 0)
1. DONE – The project is considered "Done", and while it is maintained, no further development is needed or expected
    * (number of maintainers is 1 or higher)
    * (number of maintainers does not need to change)
1. DEPRECATED – The project maintainer recommends that this project is not to be used
    * (number of maintainers is 0)
    * (number of maintainers does not need to change)
1. UNMAINTAINED – This project is not actively maintained (Ref: [UNMAINTED-2023](#references))
    * Response time expectations should be none
    * (number of maintainers is 1 or higher)
    * (number of maintainers does not need to change)
1. CASUAL – This project is only maintained on a casual basis (Ref: [CASUAL-2016](#references))
    * Response time expectations should be low
    * (number of maintainers is 1 or higher)
    * (number of maintainers does not need to change)
1. NEEDFUNDING – This project needs funding
    * Workload is unsustainable with only a volunteer-level commitment
    * (number of maintainers is 1 or higher)
    * (number of maintainers does not need to change)
1. NEEDSUPPORT – This project needs non-funding support
    * Project growth and sustainability is hindered by lack of non-code contributions
    * Examples: Branding development; Code security audit; Event organizing; Documentation writing;
    * (number of maintainers is 1 or higher)
    * (number of maintainers does not need to change)
1. COMPROMISED
    *  
1. DISCOURAGED
    *  
1. DELISTED
    * Removed from the ecosystem index for some reason
1. DUAL
    * Equivalent to the P5P special user on CPAN (Ref: [PAUSE-2017](#references))
    * Used to specify modules that are both published as part of the core language, and through a language ecosystem

### List of Support Types

When a project signals they NEEDSUPPORT, this can imply any of a number of activities are needed assistance with.

1. Brand Development
    * Strategy
    * Implementation
    * Hosting & legal
1. Bug or issue triage
1. Outreach & marketing
    * Article writing
    * Podcast hosting or participation
    * Conference presentations
    * SoMe presence
1. Code review
    * Security review
    * Development process
    * Maintainability
1. Documentation
    * Completeness
    * Consistency and Voice
    * User or Stakeholder Relevance
    * Indexing, Findability & SEO
    * Internationalization/I18N
    * Localization/L10N and Translation (Ref: [CHAOSS-2020](#references))
1. Community management & development
    * Governance development
    * Culture & conduct
    * Diversity, Equity, Inclusion
    * Forum management, moderation and support
    * Outreach & recruitment
1. Technical infrastructure and hosting
    * Email
    * Chat forum
    * DNS
    * Other hosted community services
1. Event organizing
    * Conferences, Meetups, Hackathons or other gatherings for knowledge-sharing
    * Online events, webinars or classes/training
    * Socializing
1. Industry/Stakeholder/OSPO assistance
1. Fundraising
1. Media relations
1. Security contact
1. Course/training material development
1. Open Source Steward (EU Cyber Resilience Act)
1. Legal counsel
    * License conflict resolution
    * License enforcement
1. Mentorship (Ref: [MSFTOSS-2024](#references))
    * Security
    * Governance
    * Outreach & Communication
1. Skill & contribution gaps compensation (Ref: [MSFTOSS-2024](#references))
    * Language
    * Technology/platform
    * Specialized skills
1. User Interface, User Experience, and Accessibility (Ref: [CHAOSS-2020](#references))


## Other project states, claims and metadata

1. Intended for commercial use (EU CRA signal for OSS Stewards)
1. Registered OSS Steward


### For consideration

1. FORK – This project claims to be an API-compatible fork of another project
1. CE_DECLARATION – A URL, linking to declaration of conformance to the EU Cyber Resilience Act, as required in CRA Annex II, point 6; and Chapter III, Article 28; and in Chapter II Article 13(20).
1. CE_DOCUMENTATION – A URL linking to supporting information and instructions (CRA Annex II, point 8)
1. CE_CONFORMITY_BODY – A URL pointing to the Conformity Assessment Body where this component has been registered (CRA Article 22(4) and Article 58(1))
1. CE_SUPPORT_END_DATE – The date for when the support for the component expires (Annex II, point 7)


## License and use of this document

* Version: 0.1.0
* License: [CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/deed)
* Copyright: © Salve J. Nilsen <sjn@oslo.pm>, Some rights reserved.

You may use, modify and share this file under the terms of the [CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/deed) license.


### Acknowledgements

Several people have been involved in the development of this document

* Salve J. Nilsen (main author)
* Georg Link


## References

* (SJN-2022) [What kind of non-technical "nice-to-haves" you would expect to see in a healthy #OpenSource #FLOSS community?](https://chaos.social/@sjn/109343732566572015, Published 2022-11-14.
* (CHAOSS-2020) CHAOSS [Types of Contributions](https://chaoss.community/?p=3432), First created 2020-02-20.
* (arXiv:2408.06723v1) [Sustaining Maintenance Labor for Healthy Open Source Software Projects through Human Infrastructure: A Maintainer Perspective](https://arxiv.org/pdf/2408.06723), Published 2024-08-13.
* (MSFTOSS-2024) [5 things we learned from sponsoring a sampling of our open source dependencies](https://opensource.microsoft.com/blog/2024/06/27/5-things-we-learned-from-sponsoring-a-sampling-of-our-open-source-dependencies/), Published 2024-06-27.
* (NEILB-2016) [It takes a community to raise a CPAN module](http://neilb.org/2016/02/13/it-takes-a-community.html), Published 2016-02-13.
* (PAUSE-2017) [The PAUSE Operating Model](https://pause.perl.org/pause/query?ACTION=pause_operating_model) Version 2 (section 4.5), published 2017-10-27.
* (UNMAINTED-2016) [![No Maintenance Intended](http://unmaintained.tech/badge.svg)](http://unmaintained.tech/), Published 2016-01-13.
* (CASUAL-2023) [![Casual Maintenance Intended](https://casuallymaintained.tech/badge.svg)](https://casuallymaintained.tech/), Published 2023-09-25.
