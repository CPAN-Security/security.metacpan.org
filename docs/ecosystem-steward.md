toc: true
markdown: true
---

# What is an OSS Ecosystem Steward?

An Open Source Software Ecosystem Steward, is a Steward organization as described in the EU Cyber Resilience Act [Article 24].
To make it capable of supporting an _ecosystem_ of project maintainers, service maintainers and community organizers, it is set up as a community-owned non-profit co-operative.
This is both ensure that the Steward is set up support relevant projects, services and communities in a fair way, but also have the option and capability to support other relevant entities, both in-ecosystem, upstream and downstream.


# Background: Cyber Resilience Act

When the [(EU) Regulation 2024/2847 (Cyber Resilience Act)] comes fully into effect on 11 December 2027, businesses wishing to be compliant are expected to perform a number of security-related tasks for each of their CE-marked products and their associated remote data processing solutions.

The full list of obligations are laid out in [Article 13], [Article 14], [Article 64], [Article 69], [Annex I, Part I], [Annex I, Part II], [Annex II], and [Annex VII].

Some highlights and implications that affect upstream communities:

* Product support period that matches with expected usage (eg. 5 years).
    * Implication: Any component used in the product or it's remote data processing solutions should be supported for the same period.
* Product vulnerability fixes kept available for 5 years after support period is over.
    * Implication: Software update services depending on OSS need to be kept secure for an _additional 5 years_, in total 10 years.
* Product has no known exploitable vulnerabilities while available on the EU market.
    * Implication: Products must be capable of being updated for the entire support period.
* Product metadata (including an SBOM) have to be complete, correct and not misleading.
    * Implication: Products metadata need to be kept up-to-date with changes in upstream projects. E.g. changes in ownership, names, version numbers or schemas, etc.
* Vulnerabilities discovered and/or their fixes to be shared with upstream providers. ([Article 13(6)])
    * Implication: There should be someone upstream to receive, improve and apply these fixes.
* Manufacturers are responsible for the _entirety_ of their product security. ([CRA FAQ 4.1.1], [CRA FAQ 4.3.6])
    * Implication: This _includes_ open source components used.
* Manufacturers are expected to exercise _Due Diligence_ when integrating components, after having performed a cybersecurity risk assessment. ([Article 13], [Article 14])
    * Implication: Depending on the number of products, their remote data processing solutions and their risk profiles, the _Due Diligence_ burden may cover _hundreds_, or _thousands_ of FOSS components.
* Market Surveillance Authorities may carry out an evaluation of the product and it's compliance, and if corrective action is not sufficient, require the product to be withdrawn or recalled from the market, or issue fines. ([Article 52], [Article 54])
    * Implication: If the Manufacturer doesn't have all ducks in a row, and a vulnerability in one of their products is discovered and exploited, this may quickly become expensive.

## Scope of the CRA

What products are in scope of the CRA is beyond this article, but much can be learned from the [CRA Guidance] (e.g. [CRA Guidance chapter 2]) and the [CRA FAQ] (e.g. [CRA FAQ 1.1.2]).

In summary, the CRA applies to _both_ digital and physical products, including any remote data processing solutions (e.g. services that the app needs to function as expected), that are placed on the EU market in the course of a commercial activity.

_This includes phone apps, their server components, and any other services used to keep the product updated and secure_.


# Implications and expectations for Open Source communities

From the few samples above, we should expect that businesses using Open Source somewhere in their products are likely to be unwilling, incapable or just don't have the required resources to become and remain compliant without at least _a minimum_ of assistance from the FOSS projects and communities they rely on.

Correspondingly, Open Source project maintainers, service administrators and community organizers are forced into making a [Hobson's Choice].

1. Either project maintainers take steps to demonstrate their project is _intended for use in the course of a commercial activity_,
1. or they do not – and thereby risk a (possibly significant) subset of their users are forced to switch to alternatives that allow them to become and remain compliant.

This is a choice that is made more difficult due to the security implications of declining, and the amount of boring and tedious work that comes with the accepting to help with compliance.

## Should OSS communities help with compliance?

The CRA has envisioned a novel legal category – The Open Source Software Steward – which has the purpose or objective to _systematically provide support on a sustained basis for the development of FOSS_. (See [Article 24] and [CRA Guidance chapter 3].3).

As the CPAN community has no function or entity that is both willing, competent and capable of taking upon themselves this role, it makes sense to explore other alternatives, so that those who wish to assist in the compliance work can get the opportunity to do so.

Furthermore, the long-term tradition in the CPAN community, is to operate in a _laissez-faire_ manner – letting each individual decide for themselves whether to act or not.


# OSS Ecosystem Steward

To allow everyone to _opt in_ on compliance work in a way that aligns with existing traditions and culture in our Open Source ecosystem, it makes to approach how this is done from a _first principles_ perspective.

As a result of this kind of deliberation, it makes sense to create an entirely new Steward organization, tailor-made to address the issues common for global, laissez-faire, distributed and heterogeneous communities of communities, like Perl and CPAN.

Let's set up an _OSS Ecosystem Steward_ — a community-owned non-profit co-operative, specifically set up to be able to support the people that in the ecosystem that are affected by the implications of the CRA, and wish to help improve our user's compliance situation.

Addressing the implications listed above should not be expected to be done on a volunteer basis, though.
This means that the Steward has to be capable of supporting it's stewarded communities also by directing enough funding so that even the "boring" and "tedious" work gets done.

## Community-owned

The project maintainers, service administrators and community organizers that _voluntarily decide to opt in_, get to become owners of their Ecosystem Steward.

* Maintainers – because it's the security posture of their FOSS projects (and resulting component releases) that are at the centre of the Manufacturer's concerns, and where the Manufacturers may find their greatest compliance-related expenses in their operational budgets.
* Administrators – because it's their services Manufacturers and Maintainers alike rely on to publish, identify, download, resolve, test, discuss and educate themselves about the software they rely on.
* Organizers – because there is no real Open Source without the gathering places, tutorial classes, meetings, conferences, workshops, summits, stands and similar venues for building networks of trust and support, that Community Organizers are dedicated to providing.

## Non-profit

Open Source relies heavily on a volunteer spirit and individual motivation to create something cool or make something cool happen.
In Norway, we call this volunteering spirit "Dugnad" or "Dugnadsånd" – the willingness to help your neighbour with improving something you both have in common.
Clean up the neighbourhood after a long winter.
Renovate the children's playground.
Or for your _digital neighbours_, contribute a fix for a vulnerability, or organize a conference, or run a service your _digital neighbours_ rely on.

These activities, so central to our communities' health, are almost exclusively done on a volunteer basis.
But sometimes there is work to be done, where it is difficult - even impossible - to find volunteers.
Sometimes work is "too boring".
In these cases, we should put in place support mechanisms that enable people to do these tasks anyway – for example by donating enough to facilitate new life choices, like working one weekday (20% FTE) on Open Source.
This, and the fact that many of are contributing to FOSS as a way to take a break from corporate and for-profit life, means we should _not_ look to support these communities on a for-profit basis.

Instead, we support them on a non-profit basis, and operate in ways where we both can support the "too boring" work ourselves, without introducing the features of corporate life many of us seek to recover from.

Fortunately, the CRA also encourages that OSS Stewards operate as a non-profit.

## Co-operative

A co-operative is a member-owned legal entity, set up so that any surplus gained from it's operation is used for the benefit of it's members.
A co-operative operates according to the set of seven ideals laid out in the [Rochdale Principles].

1. **Voluntary and open membership** – Co-operatives are voluntary organisations, open to all persons able to use their services and willing to accept the responsibilities of membership, without gender, social, racial, political or religious discrimination.
2. **Democratic member control** – Co-operatives are democratic organizations controlled by their members, who actively participate in setting their policies and making decisions. Men and women serving as elected representatives are accountable to the membership. In primary co-operatives members have equal voting rights (one member, one vote) and co-operatives at other levels are also organised in a democratic manner.
3. **Member economic participation** – Members contribute equitably to, and democratically control, the capital of their co-operative. At least part of that capital is usually the common property of the co-operative. Members usually receive limited compensation, if any, on capital subscribed as a condition of membership. Members allocate surpluses for any or all of the following purposes: developing their co-operative, possibly by setting up reserves, part of which at least would be indivisible; benefiting members in proportion to their transactions with the co-operative; and supporting other activities approved by the membership.
4. **Autonomy and independence** – Co-operatives are autonomous, self-help organizations controlled by their members. If they enter into agreements with other organizations, including governments, or raise capital from external sources, they do so on terms that ensure democratic control by their members and maintain their co-operative autonomy.
5. **Education, training, and information** – Co-operatives provide education and training for their members, elected representatives, managers and employees so they can contribute effectively to the development of their co-operatives. They inform the general public – particularly young people and opinion leaders – about the nature and benefits of co-operation.
6. **Cooperation among cooperatives** – Co-operatives serve their members most effectively and strengthen the co-operative movement by working together through local, national, regional and international structures.
7. **Concern for community** – Co-operatives work for the sustainable development of their communities through policies approved by their members.

Additionally, an Ecosystem Steward would do well to be set up as a _European Cooperative_ ([Societas cooperativa Europaea (SCE)]), in order to operate under a single EEA-wide set of rules and principles, and to allow the moving of the Stewards headquarters to a legislation where the Steward is more likely to succeed in it's non-profit mission.


# Surplus generating model

The OSS Ecosystem Steward operates with three revenue sources, and expects multiple expenses with a focus on

1) Operating the Steward in a surplus-generating manner, so it can
2) offer support to it's members, and it's related communities
3) in an ongoing and long-term sustainable manner, suitable for ensuring the security posture required for CRA Manufacturers products to remain compliant

## Revenue sources

1. Public support from funds dedicated to Open Source activities (e.g. the Sovereign Tech Agency fund, or other upcoming funds, possibly based on a similar model) – during a startup period
2. Enrollment and re-enrollment fees from Manufacturers
3. Voluntary Security Attestations, issued on a recurring basis (subscription)

Note: The Steward should NOT accept donations.
Instead, donations should be directed to other recipients in the community capable of accepting them.
Good donation recipients include Perl Monger groups local to the donor's operating regions, the TPRF, or projects or services the donor relies on, and are set up to receive donations.

## Expenses

1. Staff costs (4-9 FTE positions, including employer's taxes and vacation)
    1. 1-3 Software developers (membership & manufacturer management; donation management; attestation issuance; etc.)
    1. 1 Primary contact for member communities (member/developer relations and support)
    1. 1 Primary contact for manufacturers (sales and manufacturer enrollment support)
    1. 0-1 Primary contact for market authorities (legal)
    1. 0-1 Training & communications (member security awareness & training)
    1. 0-1 Treasurer & fundraising (CFO)
    1. 1 Executive (CEO)
1. Variable (income-dependent) operating expenses
    1. Other
1. Fixed operating expenses
    1. Accounting services
    1. Auditing services
    1. Hosting & computer services
    1. Insurances
    1. Legal services
    1. Contingencies & other expenses
1. Training, education and outreach expenses
    1. 4-6 Events visited, travel, lodging, food per employee
    1. 2 Internal events, venue, food, attendee travel & hotel
    1. Contingencies & other expenses
1. Board remuneration
    1. 4 board meetings x 5 board members x 2 hours
1. Re-investment into the Ecosystem Steward

The details of this budget are to be jointly proposed by the executive officer and treasurer are to be presented to the Board. The board may adjust it, and present the final budget for the General Assembly to vote on.

## Surplus

As a non-profit, any surplus has to be used on

1. Member support donations, in accordance with the disbursement formula decided by the General Assembly (GA).
2. Non-member support donations, in accordance with the disbursement formula decided by the GA.
3. Re-investment into the Steward, in accordance with the disbursement formula decided by the GA.

# Example budget

## Revenue

TBD


## Expenses

TBD


## Donations

TBD


# References

* [(EU) Regulation 2024/2847 (Cyber Resilience Act)]
* [CRA FAQ] (original source)
* [CRA FAQ - linkable copy] (by the Open Regulatory Working Group, [ORCWG])
* [CRA Guidance]
* [ORCWG]
* [Hobson's Choice]
* [Societas cooperativa Europaea (SCE)]


[(EU) Regulation 2024/2847 (Cyber Resilience Act)]:https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=OJ:L_202402847 '(EU) Regulation 2024/2847 (Cyber Resilience Act)'
[Regulation (EU) 2019/881, Article (48)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:32019R0881#art_48 'Request for a European cybersecurity certification scheme'

[EU Blue Guide]:https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=uriserv%3AOJ.C_.2022.247.01.0001.01.ENG&toc=OJ%3AC%3A2022%3A247%3ATOC 'The Blue Guide on the implementation of EU product rules (2022/C 247/01)'

[CC-BY-SA-4.0]:https://creativecommons.org/licenses/by-sa/4.0/deed 'Creative Commons Attrubution Sharealike 4.0 License'

[CISA-2023-4]:https://www.cisa.gov/resources-tools/resources/types-software-bill-materials-sbom 'CISA Types of Software Bill of Materials (SBOM)'
[CISA-2024-10]:https://www.cisa.gov/sites/default/files/2024-10/SBOM%20Framing%20Software%20Component%20Transparency%202024.pdf 'CISA Framing Software Component Transparency: Establishing a Common Software Bill of Materials (SBOM)'
[CSCRF]:https://www.sebi.gov.in/legal/circulars/aug-2024/cybersecurity-and-cyber-resilience-framework-cscrf-for-sebi-regulated-entities-res-_85964.html 'Cybersecurity and Cyber Resilience Framework (CSCRF) for SEBI Regulated Entities (REs)'
[TR-03183]:https://bsi.bund.de/dok/TR-03183 'TR-03183 Cyber Resilience Requirements for Manufacturers and Products, Part 2'
[NTIA-SBOM]:https://www.ntia.doc.gov/files/ntia/publications/sbom_minimum_elements_report.pdf#page=9 'NTIA Minimum Elements for a Software Bill of Materials (SBOM)'

[CRA FAQ]:https://digital-strategy.ec.europa.eu/en/library/cyber-resilience-act-implementation-frequently-asked-questions 'FAQs on the CRA implementation'
[CRA FAQ - linkable copy]:https://cra.orcwg.org/faq/official/ 'Linkable version of the Official CRA FAQ by the Open Regulatory Working Group (ORCWG)'
[CRA FAQ 1.1.2]:https://cra.orcwg.org/faq/official/faq_1-1-2/ "What is a product with digital elements? Are stand-alone software or firmware products with digital elements?"
[CRA FAQ 4.1.1]:https://cra.orcwg.org/faq/official/faq_4-1-1/ "What does the CRA require of the manufacturer's cybersecurity risk assessment?"
[CRA FAQ 4.3.6]:https://cra.orcwg.org/faq/official/faq_4-3-6/ 'How should vulnerabilities in integrated components be addressed and remedied?'

[CRA Guidance]:https://digital-strategy.ec.europa.eu/en/library/commission-publishes-new-guidance-support-timely-cyber-resilience-act-implementation 'Commission guidance on the application of the Cyber Resilience Act (CRA)'
[CRA Guidance chapter 2]:https://cra.orcwg.org/official-guidance/#sct_2 'CRA Guidance Chapter 2: Scope'
[CRA Guidance chapter 3]:https://cra.orcwg.org/official-guidance/#sct_3 'CRA Guidance Chapter 3: Free and open-source software'

[ORCWG]:https://orcwg.org/
[ORCWG FAQ]:https://cra.orcwg.org/
[ORCWG copy of the official CRA FAQ]:https://cra.orcwg.org/faq/
[ORCWG copy of the official CRA Guidance]:https://cra.orcwg.org/faq/

[Hobson's Choice]:https://en.wikipedia.org/wiki/Hobson%27s_choice "A Hobson's choice is a free choice in which only one thing is actually offered. The term is often used to describe an illusion that choices are available. The best known example is «I'll give you a choice: take it or leave it», wherein «leaving it» is strongly undesirable."
[Societas cooperativa Europaea (SCE)]:https://en.wikipedia.org/wiki/Societas_cooperativa_Europaea 'A special cooperative entity, that may be set up and operate throughout the European Economic Area, allowing the to move their headquarters freely from one member state to another.'
[Rochdale Principles]:https://en.wikipedia.org/wiki/Rochdale_Principles 'The Rochdale Principles, also known as the seven co-operative principles.'

[Recital (1)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_1 'Two major problems adding costs for users and society should be addressed'
[Recital (10)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_10 'CRA relevance for supply chains'
[Recital (15)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_15 'CRA applies to economic operators that have an intention to monetise a product'
[Recital (18)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_18 'Open Source Software Contributors'
[Recital (19)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_19 'Open Source Software Stewards, light-touch regulatory regime, and CE mark implications'
[Recital (20)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_20 'Open Source package managers considerations as "distributors"'
[Recital (21)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_21 'Voluntary security attestation programs for Open Source projects'
[Recital (22)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_22 'Submission of SBOMs for Open Source projects'
[Recital (24)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_24 'CRA relevance for the NIS2 directive'
[Recital (31)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_31 "Manufacturer's liability due to lack of security updates"
[Recital (34)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_34 'Exercise due diligence when integrating third-party components'
[Recital (37)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_37 'Software for testing purposes, alphas, betas'
[Recital (39)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_39 'Continued security updates'
[Recital (41)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_41 'Substantial modifications requires a new conformity assessment to be done'
[Recital (43)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_43 'Important products with digital elements'
[Recital (44)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_44 'Class I and Class II products'
[Recital (45)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_45 'Class II products are subject to mandatory third-party conformity assessment'
[Recital (56)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_56 'On the download and installation of security updates, and notification of end of support'
[Recital (57)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_57 'On the requirement to be able to get security updates separately from functionality updates'
[Recital (60)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_60 'Support period'
[Recital (61)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_61 'Support period'
[Recital (62)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_62 'Support period'
[Recital (63)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_63 'Point of contact'
[Recital (64)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_64 'Secure by default'
[Recital (65)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_65 'Notify of severe incidents or actively exploited vulnerabilities'
[Recital (77)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_77 'Manufacturers should facilitate vulnerability analysis by drawing up an SBOM, though they are not obliged to make it public'
[Recital (117)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_117 '[…] establish voluntary security attestation programmes for assessing the conformity of products with digital elements qualifying as free and open-source software […]'

[Chapter I]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#cpt_I 'General Provisions'
[Article 1]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_1 'Subject matter'
[Article 3]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_3 'Definitions'

[Chapter II]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#cpt_II 'Obligations of Economic Operators and Provisions in relation to Free and Open-Source Software'
[Article 1]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_1 'Subject Matter'
[Article 2]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_2 'Scope'
[Article 3]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_3 'Definitions'
[Article 7]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_7 'Important products'
[Article 8]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_8 'Critical products'
[Article 9]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_9 'Obligations of Manufacturers'
[Article 9(1)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_9.tit_1 'Stakeholder consultation'

[Chapter II]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#cpt_II 'Obligations of Economic Operators and Provisions in relation to Free and Open-Source Software'
[Article 13]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_13 'Obligations of Manufacturers'
[Article 13(1)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.001 'Manufacturers shall ensure products are developed in accordance with essential cybersecurity requirements'
[Article 13(2)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.002 'Manufacturers shall undertake a cybersecurity risk assessment'
[Article 13(5)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.005 'Manufacturers shall exercise due diligence when integrating components, including FOSS'
[Article 13(6)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.006 'Manufacturers shall share relevant code or documentation with the supplier or maintainer of the component'
[Article 13(8)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.008 'Manufacturers shall ensure vulnerabilities are handled for 5 years'
[Article 13(9)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.009 'Manufacturers shall make security updates available for 10 years or longer'
[Article 13(12)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.012 'Manufacturers shall before placing a product on the market, draw up technical documentation'
[Article 13(14)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.014 'Manufacturers shall ensure that procedures are in place for products to remain in conformity with this Regulation'
[Article 13(15)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.015 'Manufacturers shall ensure that their products is identifiable'
[Article 13(16)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.016 'Manufacturers shall indicate their name and identification'
[Article 13(17)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.017 'Manufacturers shall designate a single point of contact for reporting vulnerabilities'
[Article 13(18)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.018 'Manufacturers shall ensure products are accompanied by documentation listed in Annex II, and available for at least 10 years'
[Article 13(19)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.019 'Manufacturers shall shall clearly mark the end date of the support period'
[Article 13(20)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.020 'Manufacturers shall provide a copy of or the exact internet addrees to the EU declaration of conformity'
[Article 14]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_14 'Reporting obligations of manufacturers'
[Article 14(1)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#014.001 'A manufacturer shall notify any actively exploited vulnerability contained in the product that it becomes aware of'
[Article 14(2)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#014.002 'A manufacturer shall notify within 24 hours, 72 hours and 14 days'
[Article 14(3)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#014.003 'A manufacturer shall notify any severe incident having an impact on the security of the product that it becomes aware of'
[Article 14(8)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#014.008 'After becoming aware of an incident or vulnerability, the manufacturer shall inform the impacted users of the product, and about risk mitigation and any corrective measures that users can deploy'
[Article 15]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_15 'Voluntary reporting'
[Article 16]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_16 'Establishment of a single reporting platform'
[Article 17]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_17 'Other provisions related to reporting'
[Article 18]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_18 'Authorised representatives'
[Article 19]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_19 'Obligations of importers'
[Article 19(1)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#019.001 'Importers shall only place products on the market that comply with requirements in Annex I part I'
[Article 20]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_20 'Obligations of distributors'
[Article 21]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_21 'Cases in which obligations of manufacturers apply to importers and distributors'
[Article 22]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_22 'Other cases in which obligations of manufacturers apply'
[Article 23]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_23 'Identification of economic operators'
[Article 23(2)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#023.002 'Be able to present supplier information for 10 years'
[Article 24]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_24 'Obligations of open-source software stewards'
[Article 24(2)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#024.002 'Open-source software stewards'
[Article 25]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_25 'Security attestation of free and open-source software shall cooperate with the market surveillance authorities'
[Article 26]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_26 'Guidance'

[Chapter III]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#cpt_III 'Conformity of the product with digital elements'
[Article 27]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_27 'Presumption of conformity'
[Article 28]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_28 'EU declaration of conformity'
[Article 28(1)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#028.001 'Manufacturer states that cybersecurity requirements in [Annex I] has been demonstrated'
[Article 28(4)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#028.004 'Manufacturer assumes responsibility for compliance'
[Article 30]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_30 'Rules and conditions for affixing the CE marking'
[Article 30(3)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#030.003 'The CE marking shall be affixed before the product with digital elements is placed on the market'
[Article 32]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_32 'Conformity assessment procedures'

[Chapter IV]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#cpt_IV 'Notification of Conformity Assessment Bodies'
[Article 47]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_47 'Operational obligations of notified bodies'

[Chapter V]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#cpt_V 'Market Surveillance and Enforcement'
[Article 52]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_52 'Market surveillance and control of products'
[Article 52(3)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#052.003 'Market surveillance authorities shall also be responsible for carrying out market surveillance activities in relation to the obligations for open-source software stewards.'
[Article 52(11)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#052.011 'Market surveillance authorities shall inform consumers of where to submit complaints that could indicate non-compliance with this Regulation and facilitate reporting of vulnerabilities, incidents and cyber threats'
[Article 54]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_54 'Procedure concerning products presenting a significant cybersecurity risk'
[Article 54(1)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#054.001 '[If a market authority finds] sufficient reason to consider that a product, including its vulnerability handling, presents a significant cybersecurity risk, it shall carry out an evaluation of the product concerned in respect of its compliance with all the requirements laid down in this Regulation.'
[Article 54(5)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#054.005 '[If the economic operator does] not take adequate corrective action, the market surveillance authority shall take all appropriate provisional measures to prohibit or restrict that product from being made available, to withdraw it from that market or to recall it.'
[Article 58]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_58 'Formal non-compliance'

[Chapter VII]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#cpt_VII 'Confidentiality and Penalties'
[Article 64]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_64 'Penalties'
[Article 64(4)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#064.004 'Supplying incorrect, incomplete or misleading information may be fined up to 5M EUR or 1% of global turnover'
[Article 64(10)(b)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#064.010 'Rules on administrative fines shall not apply to Open Source Software Stewards'

[Chapter VIII]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#cpt_VIII 'Transitional and final provisions'
[Article 69]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_69 'Transitional provisions'
[Article 69(2)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#069.002 'Products placed on the market before 11 December 2027 shall be subject to this Regulation only if, from that date, those products are subject to a substantial modification.'
[Article 69(3)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#069.003 'Obligations laid down in Article 14 shall apply to all products that fall within the scope of this Regulation that have been placed on the market before 11 December 2027.'
[Article 71]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_71 'Entry into force and application'
[Article 71(2)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#071.002 'This Regulation shall apply from 11 December 2027. However, Article 14 shall apply from 11 September 2026 and Chapter IV (Articles 35 to 51) shall apply from 11 June 2026.'

[Annex I]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#anx_I 'Essential Cybersecurity Requirements'
[Annex I, Part I]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#d1e47-68-1 'Cybersecurity requirements relating to the properties of products with digital elements'
[Annex I, Part II]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#d1e143-68-1 'Vulnerability handling requirements'
[Annex II]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#anx_II 'Information and Instructions to the User'
[Annex III]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#anx_III 'Important products'
[Annex IV]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#anx_IV 'Critical products'
[Annex V]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#anx_V 'EU Declaration of Conformity'
[Annex VII]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#anx_VII 'Content of the Technical Documentation'
