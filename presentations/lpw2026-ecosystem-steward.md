[comment]: # (Compile this presentation with the command below)
[comment]: # (mdslides lpw2026-ecosystem-steward.md --include ../media)
[comment]: # (...or by running the Makefile with "make")
[comment]: # (mdslides can be installed from https://github.com/dadoomer/markdown-slides/)

[comment]: # (THEME = solarized)

[comment]: # (minScale: 0.4)
[comment]: # (maxScale: 2.0)
[comment]: # (controls: true)
[comment]: # (width: "1440")
[comment]: # (height: "810")
[comment]: # (help: true)
[comment]: # (progress: true)
[comment]: # (controlsBackArrows: "true")

[Recital (21)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_21 'Voluntary security attestation programs for Open Source projects'
[Recital (117)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_117 '[…] establish voluntary security attestation programmes for assessing the conformity of products with digital elements qualifying as free and open-source software […]'
[Article 3]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_3 'Definitions'
[Article 13(6)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.006 'Manufacturers shall share relevant code or documentation with the supplier or maintainer of the component'
[Article 13(8)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.008 'Manufacturers shall ensure vulnerabilities are handled for 5 years'
[Article 13(9)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.009 'Manufacturers shall keep security updates available for 10 years after they are issued, or for the rest of the support period, whichever is longer'
[Article 24]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_24 'Obligations of open-source software stewards'
[Article 25]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_25 'Security attestations of free and open-source software, for conformity assessment'
[Article 64(4)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#064.004 'Supplying incorrect, incomplete or misleading information may be fined up to 5M EUR or 1% of global turnover'
[Annex I, Part I]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#d1e47-68-1 'Cybersecurity requirements relating to the properties of products with digital elements'
[CRA FAQ 4.1.1]:https://cra.orcwg.org/faq/official/faq_4-1-1/ "What does the CRA require of the manufacturer's cybersecurity risk assessment?"
[Hobson's Choice]:https://en.wikipedia.org/wiki/Hobson%27s_choice "A Hobson's choice is a free choice in which only one thing is actually offered."
[Rochdale Principles]:https://en.wikipedia.org/wiki/Rochdale_Principles 'The Rochdale Principles, also known as the seven co-operative principles.'
[Societas cooperativa Europaea (SCE)]:https://en.wikipedia.org/wiki/Societas_cooperativa_Europaea 'A special cooperative entity, that may be set up and operate throughout the European Economic Area, allowing them to move their headquarters freely from one member state to another.'
[The OSS Ecosystem Steward]:https://security.metacpan.org/docs/ecosystem-steward.html 'A proposal for a community-owned, non-profit co-operative acting as the CRA Open Source Software Steward for an entire ecosystem'



## The OSS Ecosystem Steward

London Perl Workshop 2026

Salve J. Nilsen

(CPANSec, Oslo.pm)

🐘 Mastodon — @sjn\@chaos.social


Note:

[comment]: # (!!! data-auto-animate)

## The concept, in three sentences


[comment]: # (||| data-auto-animate)

## The concept, in three sentences

1. A **maintainers' co-op**, owned by the people who look after the ecosystem's projects, services and communities.


[comment]: # (||| data-auto-animate)

## The concept, in three sentences

1. A **maintainers' co-op**, owned by the people who look after the ecosystem's projects, services and communities.
1. **Companies buy attestations** from it, showing the projects they rely on are secure and compliant – and that money sustains the community.


[comment]: # (||| data-auto-animate)

## The concept, in three sentences

1. A **maintainers' co-op**, owned by the people who look after the ecosystem's projects, services and communities.
1. **Companies buy attestations** from it, showing the projects they rely on are secure and compliant – and that money sustains the community.
1. **Maintainers keep full control**, and get the resources needed to do compliance work.


[comment]: # (!!! data-auto-animate)

## Cyber Resilience Act - December 11, 2027


[comment]: # (||| data-auto-animate)

## Cyber Resilience Act - December 11, 2027

Manufacturers are responsible for the security of _every_ component in their products


[comment]: # (||| data-auto-animate)

## Cyber Resilience Act - December 11, 2027

Manufacturers are responsible for the security of _every_ component in their products

- …including the Open Source ones


[comment]: # (||| data-auto-animate)

## Cyber Resilience Act - December 11, 2027

Manufacturers are responsible for the security of _every_ component in their products

- …including the Open Source ones
- …and the remote data processing solutions they rely on (phone apps, servers, APIs)


[comment]: # (||| data-auto-animate)

## Cyber Resilience Act - December 11, 2027

Manufacturers are responsible for the security of _every_ component in their products

- …including the Open Source ones
- …and the remote data processing solutions they rely on (phone apps, servers, APIs)

No transfer of liability – it stays with the manufacturer ([CRA FAQ 4.1.1])


[comment]: # (!!! data-auto-animate)

## What reaches upstream


[comment]: # (||| data-auto-animate)

## What reaches upstream

- Support period matching expected use, e.g. 5 years ([Article 13(8)])


[comment]: # (||| data-auto-animate)

## What reaches upstream

- Support period matching expected use, e.g. 5 years ([Article 13(8)])
- Security updates available for 10 years ([Article 13(9)])


[comment]: # (||| data-auto-animate)

## What reaches upstream

- Support period matching expected use, e.g. 5 years ([Article 13(8)])
- Security updates available for 10 years ([Article 13(9)])
- No known exploitable vulnerabilities ([Annex I, Part I])


[comment]: # (||| data-auto-animate)

## What reaches upstream

- Support period matching expected use, e.g. 5 years ([Article 13(8)])
- Security updates available for 10 years ([Article 13(9)])
- No known exploitable vulnerabilities ([Annex I, Part I])
- Correct and current metadata, e.g. SBOMs ([Article 64(4)])


[comment]: # (||| data-auto-animate)

## What reaches upstream

- Support period matching expected use, e.g. 5 years ([Article 13(8)])
- Security updates available for 10 years ([Article 13(9)])
- No known exploitable vulnerabilities ([Annex I, Part I])
- Correct and current metadata, e.g. SBOMs ([Article 64(4)])
- Fixes shared with upstream – someone has to receive them ([Article 13(6)])


[comment]: # (||| data-auto-animate)

## What reaches upstream

- Support period matching expected use, e.g. 5 years ([Article 13(8)])
- Security updates available for 10 years ([Article 13(9)])
- No known exploitable vulnerabilities ([Annex I, Part I])
- Correct and current metadata, e.g. SBOMs ([Article 64(4)])
- Fixes shared with upstream – someone has to receive them ([Article 13(6)])

…and due diligence on _hundreds_ or _thousands_ of components


[comment]: # (!!! data-auto-animate)

## A [Hobson's Choice] for maintainers


[comment]: # (||| data-auto-animate)

## A [Hobson's Choice] for maintainers

- **Accept** – demonstrate the project is _intended for commercial use_


[comment]: # (||| data-auto-animate)

## A [Hobson's Choice] for maintainers

- **Accept** – demonstrate the project is _intended for commercial use_
  - …and take on boring, tedious compliance work


[comment]: # (||| data-auto-animate)

## A [Hobson's Choice] for maintainers

- **Accept** – demonstrate the project is _intended for commercial use_
  - …and take on boring, tedious compliance work
- **Decline** – and risk users being forced to switch away


[comment]: # (||| data-auto-animate)

## A [Hobson's Choice] for maintainers

- **Accept** – demonstrate the project is _intended for commercial use_
  - …and take on boring, tedious compliance work
- **Decline** – and risk users being forced to switch away
  - …with security consequences for everyone


[comment]: # (||| data-auto-animate)

## A [Hobson's Choice] for maintainers

- **Accept** – demonstrate the project is _intended for commercial use_
  - …and take on boring, tedious compliance work
- **Decline** – and risk users being forced to switch away
  - …with security consequences for everyone

Goal: make accepting **realistic and fair**


[comment]: # (!!! data-auto-animate)

## The Open Source Software Steward


[comment]: # (||| data-auto-animate)

## The Open Source Software Steward

A new legal category in the CRA ([Article 3], [Article 24])


[comment]: # (||| data-auto-animate)

## The Open Source Software Steward

A new legal category in the CRA ([Article 3], [Article 24])

- …_systematically_ supporting Open Source intended for commercial use


[comment]: # (||| data-auto-animate)

## The Open Source Software Steward

A new legal category in the CRA ([Article 3], [Article 24])

- …_systematically_ supporting Open Source intended for commercial use
- …ensuring the viability of those projects


[comment]: # (||| data-auto-animate)

## The Open Source Software Steward

A new legal category in the CRA ([Article 3], [Article 24])

- …_systematically_ supporting Open Source intended for commercial use
- …ensuring the viability of those projects

Works well for a foundation with _tens or hundreds_ of projects


[comment]: # (!!! data-auto-animate)

## Why CPAN is different


[comment]: # (||| data-auto-animate)

## Why CPAN is different

- _Tens of thousands_ of projects, and a long tail of transitive dependencies


[comment]: # (||| data-auto-animate)

## Why CPAN is different

- _Tens of thousands_ of projects, and a long tail of transitive dependencies
- No existing organisation willing and able to be the Steward


[comment]: # (||| data-auto-animate)

## Why CPAN is different

- _Tens of thousands_ of projects, and a long tail of transitive dependencies
- No existing organisation willing and able to be the Steward
- A _laissez-faire_ tradition


[comment]: # (||| data-auto-animate)

## Why CPAN is different

- _Tens of thousands_ of projects, and a long tail of transitive dependencies
- No existing organisation willing and able to be the Steward
- A _laissez-faire_ tradition
- A fiercely independent culture


[comment]: # (||| data-auto-animate)

## Why CPAN is different

- _Tens of thousands_ of projects, and a long tail of transitive dependencies
- No existing organisation willing and able to be the Steward
- A _laissez-faire_ tradition
- A fiercely independent culture

**How do we introduce a Steward to an entire ecosystem _on the community's terms_?**


[comment]: # (!!! data-auto-animate)

## Design criteria


[comment]: # (||| data-auto-animate)

## Design criteria

- Non-profit, community-owned, democratically governed


[comment]: # (||| data-auto-animate)

## Design criteria

- Non-profit, community-owned, democratically governed
- Free to join, leave and rejoin


[comment]: # (||| data-auto-animate)

## Design criteria

- Non-profit, community-owned, democratically governed
- Free to join, leave and rejoin
- Minimum obligations – membership is the marker of viability


[comment]: # (||| data-auto-animate)

## Design criteria

- Non-profit, community-owned, democratically governed
- Free to join, leave and rejoin
- Minimum obligations – membership is the marker of viability
- Operate as a business – not dependent on donations


[comment]: # (||| data-auto-animate)

## Design criteria

- Non-profit, community-owned, democratically governed
- Free to join, leave and rejoin
- Minimum obligations – membership is the marker of viability
- Operate as a business – not dependent on donations
- Support the forgotten and "hidden" dependencies


[comment]: # (||| data-auto-animate)

## Design criteria

- Non-profit, community-owned, democratically governed
- Free to join, leave and rejoin
- Minimum obligations – membership is the marker of viability
- Operate as a business – not dependent on donations
- Support the forgotten and "hidden" dependencies
- Members stay **fully in control** of their projects


[comment]: # (!!! data-auto-animate)

## A **community-owned** non-profit co-operative


[comment]: # (||| data-auto-animate)

## A **community-owned** non-profit co-operative

Owned by those who opt in:


[comment]: # (||| data-auto-animate)

## A **community-owned** non-profit co-operative

Owned by those who opt in:

- **Project maintainers** – where manufacturers' biggest compliance costs are


[comment]: # (||| data-auto-animate)

## A **community-owned** non-profit co-operative

Owned by those who opt in:

- **Project maintainers** – where manufacturers' biggest compliance costs are
- **Service administrators** – the infrastructure everyone relies on


[comment]: # (||| data-auto-animate)

## A **community-owned** non-profit co-operative

Owned by those who opt in:

- **Project maintainers** – where manufacturers' biggest compliance costs are
- **Service administrators** – the infrastructure everyone relies on
- **Community organisers** – where trust and skills are built


[comment]: # (!!! data-auto-animate)

## A community-owned **non-profit** co-operative


[comment]: # (||| data-auto-animate)

## A community-owned **non-profit** co-operative

_Dugnad_ – helping your neighbours improve the commons


[comment]: # (||| data-auto-animate)

## A community-owned **non-profit** co-operative

_Dugnad_ – helping your neighbours improve the commons

Some work is too boring to find volunteers for


[comment]: # (||| data-auto-animate)

## A community-owned **non-profit** co-operative

_Dugnad_ – helping your neighbours improve the commons

Some work is too boring to find volunteers for

- Members are not hired, and get no wage


[comment]: # (||| data-auto-animate)

## A community-owned **non-profit** co-operative

_Dugnad_ – helping your neighbours improve the commons

Some work is too boring to find volunteers for

- Members are not hired, and get no wage
- …they are **co-owners receiving donations** – up to 20% FTE (one weekday)


[comment]: # (||| data-auto-animate)

## A community-owned **non-profit** co-operative

_Dugnad_ – helping your neighbours improve the commons

Some work is too boring to find volunteers for

- Members are not hired, and get no wage
- …they are **co-owners receiving donations** – up to 20% FTE (one weekday)
- …and any surplus goes to members, non-members, or reinvestment


[comment]: # (||| data-auto-animate)

## A community-owned **non-profit** co-operative

_Dugnad_ – helping your neighbours improve the commons

Some work is too boring to find volunteers for

- Members are not hired, and get no wage
- …they are **co-owners receiving donations** – up to 20% FTE (one weekday)
- …and any surplus goes to members, non-members, or reinvestment

The General Assembly decides the disbursement formula


[comment]: # (!!! data-auto-animate)

## A community-owned non-profit **co-operative**


[comment]: # (||| data-auto-animate)

## A community-owned non-profit **co-operative**

Following the seven [Rochdale Principles]:

- Voluntary and open membership
- Democratic member control
- Member economic participation
- Autonomy and independence
- Education, training and information
- Co-operation among co-operatives
- Concern for community


[comment]: # (||| data-auto-animate)

## A community-owned non-profit **co-operative**

Following the seven [Rochdale Principles]:

- Voluntary and open membership
- Democratic member control
- Member economic participation
- Autonomy and independence
- Education, training and information
- Co-operation among co-operatives
- Concern for community

Set up as a European Cooperative Society ([Societas cooperativa Europaea (SCE)])


[comment]: # (!!! data-auto-animate)

## Voluntary Security Attestations (VSAs)


[comment]: # (||| data-auto-animate)

## Voluntary Security Attestations (VSAs)

A claim **issued by the maintainer**, **signed by the Steward**


[comment]: # (||| data-auto-animate)

## Voluntary Security Attestations (VSAs)

A claim **issued by the maintainer**, **signed by the Steward**

- …about a project's viability and intended use in products


[comment]: # (||| data-auto-animate)

## Voluntary Security Attestations (VSAs)

A claim **issued by the maintainer**, **signed by the Steward**

- …about a project's viability and intended use in products
- …covering specific releases, valid for a limited time


[comment]: # (||| data-auto-animate)

## Voluntary Security Attestations (VSAs)

A claim **issued by the maintainer**, **signed by the Steward**

- …about a project's viability and intended use in products
- …covering specific releases, valid for a limited time
- …and a receipt for the manufacturer's contribution to the project


[comment]: # (||| data-auto-animate)

## Voluntary Security Attestations (VSAs)

A claim **issued by the maintainer**, **signed by the Steward**

- …about a project's viability and intended use in products
- …covering specific releases, valid for a limited time
- …and a receipt for the manufacturer's contribution to the project

The CRA opens for this ([Recital (21)], [Recital (117)], [Article 25])

⚠️ **No delegated act published yet – this part is speculation**


[comment]: # (!!! data-auto-animate)

## How VSAs are issued


[comment]: # (||| data-auto-animate)

## How VSAs are issued

1. Steward announces itself and its signing identity


[comment]: # (||| data-auto-animate)

## How VSAs are issued

1. Steward announces itself and its signing identity
1. Manufacturer finds it depends on a project, and **pays an enrolment fee**


[comment]: # (||| data-auto-animate)

## How VSAs are issued

1. Steward announces itself and its signing identity
1. Manufacturer finds it depends on a project, and **pays an enrolment fee**
1. Maintainer **may choose** to join, and declares the Steward in the project's metadata


[comment]: # (||| data-auto-animate)

## How VSAs are issued

1. Steward announces itself and its signing identity
1. Manufacturer finds it depends on a project, and **pays an enrolment fee**
1. Maintainer **may choose** to join, and declares the Steward in the project's metadata
1. Maintainer attests to compliance and viability


[comment]: # (||| data-auto-animate)

## How VSAs are issued

1. Steward announces itself and its signing identity
1. Manufacturer finds it depends on a project, and **pays an enrolment fee**
1. Maintainer **may choose** to join, and declares the Steward in the project's metadata
1. Maintainer attests to compliance and viability
1. Steward reaffirms and **signs the VSA**, on a recurring schedule


[comment]: # (||| data-auto-animate)

## How VSAs are issued

1. Steward announces itself and its signing identity
1. Manufacturer finds it depends on a project, and **pays an enrolment fee**
1. Maintainer **may choose** to join, and declares the Steward in the project's metadata
1. Maintainer attests to compliance and viability
1. Steward reaffirms and **signs the VSA**, on a recurring schedule
1. Subscribing manufacturers **receive signed VSAs**


[comment]: # (||| data-auto-animate)

## How VSAs are issued

1. Steward announces itself and its signing identity
1. Manufacturer finds it depends on a project, and **pays an enrolment fee**
1. Maintainer **may choose** to join, and declares the Steward in the project's metadata
1. Maintainer attests to compliance and viability
1. Steward reaffirms and **signs the VSA**, on a recurring schedule
1. Subscribing manufacturers **receive signed VSAs**
1. Market surveillance authority audits – and **verifies the VSAs**


[comment]: # (!!! data-auto-animate)

## For manufacturers


[comment]: # (||| data-auto-animate)

## For manufacturers

Due diligence asks:


[comment]: # (||| data-auto-animate)

## For manufacturers

Due diligence asks:

- **Intended for commercial use?** – vulnerability handling, responsive maintainers, current metadata


[comment]: # (||| data-auto-animate)

## For manufacturers

Due diligence asks:

- **Intended for commercial use?** – vulnerability handling, responsive maintainers, current metadata
- **Viable and sustained?** – governance, long-term commitments, funding options in use


[comment]: # (||| data-auto-animate)

## For manufacturers

Due diligence asks:

- **Intended for commercial use?** – vulnerability handling, responsive maintainers, current metadata
- **Viable and sustained?** – governance, long-term commitments, funding options in use

Signed VSAs answer both – funded by the enrolment fee, sustained by the subscription


[comment]: # (!!! data-auto-animate)

## For the community


[comment]: # (||| data-auto-animate)

## For the community

Members receive **recurring donations**, per the disbursement formula


[comment]: # (||| data-auto-animate)

## For the community

Members receive **recurring donations**, per the disbursement formula

At the General Assembly, members:

- …propose disbursement formulas
- …vote on which one to use
- …elect the board


[comment]: # (||| data-auto-animate)

## For the community

Members receive **recurring donations**, per the disbursement formula

At the General Assembly, members:

- …propose disbursement formulas
- …vote on which one to use
- …elect the board

Leaving? Just change the Steward in your project's metadata


[comment]: # (!!! data-auto-animate)

## Membership criteria


[comment]: # (||| data-auto-animate)

## Membership criteria

- Maintainer, service administrator or community organiser


[comment]: # (||| data-auto-animate)

## Membership criteria

- Maintainer, service administrator or community organiser
- Non-profit or volunteer basis


[comment]: # (||| data-auto-animate)

## Membership criteria

- Maintainer, service administrator or community organiser
- Non-profit or volunteer basis
- Project in use by a manufacturer, upstream of one, or serving the community


[comment]: # (||| data-auto-animate)

## Membership criteria

- Maintainer, service administrator or community organiser
- Non-profit or volunteer basis
- Project in use by a manufacturer, upstream of one, or serving the community
- Meets the "light-touch" Steward obligations


[comment]: # (||| data-auto-animate)

## Membership criteria

- Maintainer, service administrator or community organiser
- Non-profit or volunteer basis
- Project in use by a manufacturer, upstream of one, or serving the community
- Meets the "light-touch" Steward obligations
- Committed to long-term care, succession and sunset plans


[comment]: # (||| data-auto-animate)

## Membership criteria

- Maintainer, service administrator or community organiser
- Non-profit or volunteer basis
- Project in use by a manufacturer, upstream of one, or serving the community
- Meets the "light-touch" Steward obligations
- Committed to long-term care, succession and sunset plans
- Takes part in issuing VSAs


[comment]: # (!!! data-auto-animate)

## Funding model


[comment]: # (||| data-auto-animate)

## Funding model

1. **Public funding** – until established


[comment]: # (||| data-auto-animate)

## Funding model

1. **Public funding** – until established
1. **Enrolment fees** – paid once by manufacturers


[comment]: # (||| data-auto-animate)

## Funding model

1. **Public funding** – until established
1. **Enrolment fees** – paid once by manufacturers
1. **VSA subscriptions** – recurring


[comment]: # (||| data-auto-animate)

## Funding model

1. **Public funding** – until established
1. **Enrolment fees** – paid once by manufacturers
1. **VSA subscriptions** – recurring

Goal: **no donations or public funding needed** in the long run


[comment]: # (!!! data-auto-animate)

## Next steps


[comment]: # (||| data-auto-animate)

## Next steps

- EU Commission publishes the [Article 25] delegated act


[comment]: # (||| data-auto-animate)

## Next steps

- EU Commission publishes the [Article 25] delegated act
- Draft the SCE bylaws – legal, tax and antitrust questions


[comment]: # (||| data-auto-animate)

## Next steps

- EU Commission publishes the [Article 25] delegated act
- Draft the SCE bylaws – legal, tax and antitrust questions
- Founding members: ≥3 legal entities, in ≥2 EEA countries


[comment]: # (||| data-auto-animate)

## Next steps

- EU Commission publishes the [Article 25] delegated act
- Draft the SCE bylaws – legal, tax and antitrust questions
- Founding members: ≥3 legal entities, in ≥2 EEA countries
  - TPRF, Vienna.pm, Mongueurs de Perl, Oslo.pm have responded


[comment]: # (||| data-auto-animate)

## Next steps

- EU Commission publishes the [Article 25] delegated act
- Draft the SCE bylaws – legal, tax and antitrust questions
- Founding members: ≥3 legal entities, in ≥2 EEA countries
  - TPRF, Vienna.pm, Mongueurs de Perl, Oslo.pm have responded
  - Blockers: funding, a business model, GA decisions


[comment]: # (||| data-auto-animate)

## Next steps

- EU Commission publishes the [Article 25] delegated act
- Draft the SCE bylaws – legal, tax and antitrust questions
- Founding members: ≥3 legal entities, in ≥2 EEA countries
  - TPRF, Vienna.pm, Mongueurs de Perl, Oslo.pm have responded
  - Blockers: funding, a business model, GA decisions
- Fundraising for the SCE's starting capital


[comment]: # (!!! data-auto-animate)

## How you can help


[comment]: # (||| data-auto-animate)

## How you can help

- Read the proposal: [The OSS Ecosystem Steward]


[comment]: # (||| data-auto-animate)

## How you can help

- Read the proposal: [The OSS Ecosystem Steward]
- Send comments and concerns


[comment]: # (||| data-auto-animate)

## How you can help

- Read the proposal: [The OSS Ecosystem Steward]
- Send comments and concerns
- Does your Perl community have a legal entity? Become a founding member!


Note:


[comment]: # (!!!)

# Thanks!

Salve J. Nilsen

🐘 Mastodon — @sjn\@chaos.social

🦆🦆

