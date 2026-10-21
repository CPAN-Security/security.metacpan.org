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
    * Implication: Software update services depending on OSS need to be kept secure for 5+5 years.
* Product has no known exploitable vulnerabilities while available on the EU market.
    * Implication: Products must be capable of being updated for the entire support period.
* Product metadata (including an SBOM) have to be complete, correct and not misleading.
    * Implication: Products metadata need to be kept up-to-date with changes in upstream projects. E.g. changes in ownership, names, version numbers or schemas, etc.
* Vulnerabilities discovered and/or their fixes to be shared with upstream providers. ([Article 13(6)])
    * Implication: There should be someone upstream to receive, improve and apply these fixes.
* Manufacturers are responsible for the _entirety_ of their product security. ([FAQ 4.1.1], [FAQ 4.3.6])
    * Implication: This _includes_ open source components used.
* Manufacturers are expected to exercise _Due Diligence_ when integrating components, after having performed a cybersecurity risk assessment. ([Article 13], [Article 14])
    * Implication: Depending on the number of products, their remote data processing solutions and their risk profiles, the _Due Diligence_ burden may cover _hundreds_, or _thousands_ of FOSS components.
* Market Surveillance Authorities may carry out an evaluation of the product and it's compliance, and if corrective action is not sufficient, require the product to be withdrawn or recalled from the market, or issue fines. ([Article 52], [Article 54])
    * Implication: If the Manufacturer doesn't have all ducks in a row, and a vulnerability in one of their products is discovered and exploited, this may quickly become expensive.

## Scope of the CRA

What products are in scope of the CRA is beyond this article, but much can be learned from the [CRA Guidance] (e.g. [CRA Guidance chapter 2]) and the [CRA FAQ] (e.g. [CRA FAQ 1.1.2]))

In summary, the CRA applies to _both_ digital and physical products, and their remote data processing solutions (e.g. services that the app needs to function as expected), placed on the EU market in the course of a commercial activity.

_This include Phone apps, their server components, and any other services used to keep the product updated and secure_.


# Implications and expectations for Open Source communities

From the few samples above, we should expect that businesses using Open Source somewhere in their product, are likely to be unwilling, incapable of becoming and remaining compliant without at least _a minimum of assistance_ from the FOSS projects and communities they rely on.

Correspondingly, Open Source project maintainers, service administrators and community organizers are forced into making a [Hobson's Choice].

1. Either project maintainers take steps to demonstrate their project is _intended for use in the course of a commercial activity_,
1. or they do not – and thereby risk a (possibly significant) subset of their users software are forced to switch to alternatives that allow them to become or remain compliant with the CRA.

## Choosing to help with compliance

The CRA has envisioned a novel legal category – The Open Source Software Steward – who has the purpose or objective to systematically providing support on a sustained basis for the development of FOSS. (See [Article 24] and [CRA Guidance chapter 3].3).

As the CPAN community has no function or entity that is both willing, competent and capable of taking upon themselves this role, it makes sense to explore other alternatives.

# OSS Ecosystem Steward

One alternative, is to create a community-owned non-profit co-operative, specifically set up to be able to support the people that in this ecosystem that are affected by the implications of the CRA.

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
In these cases, we should set in place support mechanisms that allow people to do these tasks anyway – for example by donating enough to enable new life choices, like working one weekday (20% FTE) on Open Source.
This, and the fact that many of are contributing to FOSS as a way to take a break from corporate and for-profit life, means we should not look to support these communities on a for-profit basis.

Instead, we operate on a non-profit basis, and operate in ways where we both can support the "too boring" work ourselves, without introducing the features of corporate life many of us seek to avoid.

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

Additionally, an Ecosystem would do well to be set up as a _European Cooperative_ ([Societas cooperativa Europaea (SCE)]), in order to operate under a single EEA-wide set of rules and principles, and to allow the moving of the Stewards headquarters to a legislation where the Steward is more likely to succeed in it's non-profit mission.

# Business model

The OSS Ecosystem Steward operates with three revenue sources, and expects multiple expenses with a focus on 1) Operating the Steward in a surplus-generating manner, so it can offer support to it's members and it's related communities.





# References

* [(EU) Regulation 2024/2847 (Cyber Resilience Act)]
* [CRA FAQ] (original source)
* [CRA FAQ - linkable copy] (by the Open Regulatory Working Group, [ORCWG])
* [CRA Guidance]
* [ORCWG]
* [Hobson's Choice]
* [Societas cooperativa Europaea (SCE)]



[(EU) Regulation 2024/2847 (Cyber Resilience Act)]:https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=OJ:L_202402847 '(EU) Regulation 2024/2847 (Cyber Resilience Act)'

[CRA FAQ]:https://digital-strategy.ec.europa.eu/en/library/cyber-resilience-act-implementation-frequently-asked-questions 'FAQs on the CRA implementation'
[FAQ 1.1.2]:https://cra.orcwg.org/faq/official/faq_1-1-2/ "What is a product with digital elements? Are stand-alone software or firmware products with digital elements?"
[FAQ 4.1.1]:https://cra.orcwg.org/faq/official/faq_4-1-1/ "What does the CRA require of the manufacturer's cybersecurity risk assessment?"
[FAQ 4.3.6]:https://cra.orcwg.org/faq/official/faq_4-3-6/ 'How should vulnerabilities in integrated components be addressed and remedied?'

[CRA Guidance]:https://digital-strategy.ec.europa.eu/en/library/commission-publishes-new-guidance-support-timely-cyber-resilience-act-implementation 'Commission guidance on the application of the Cyber Resilience Act (CRA)'
[CRA Guidance chapter 2]:https://cra.orcwg.org/official-guidance/#sct_2 'CRA Guidance Chapter 2: Scope'
[CRA Guidance chapter 3]:https://cra.orcwg.org/official-guidance/#sct_3 'CRA Guidance Chapter 3: Free and open-source software'

[ORCWG]:https://orcwg.org/
[ORCWG FAQ]:https://cra.orcwg.org/
[ORCWG copy of the official CRA FAQ]:https://cra.orcwg.org/faq/
[ORCWG copy of the official CRA Guidance]:https://cra.orcwg.org/faq/

[Hobson's Choice]:https://en.wikipedia.org/wiki/Hobson%27s_choice "A Hobson's choice is a free choice in which only one thing is actually offered. The term is often used to describe an illusion that choices are available. The best known example is «I'll give you a choice: take it or leave it», wherein «leaving it» is strongly undesirable."
[Societas cooperativa Europaea (SCE)]:https://en.wikipedia.org/wiki/Societas_cooperativa_Europaea 'A special cooperative entity, that may be set up and operate throughout the European Economic Area, allowing the to move their headquarters freely from one member state to another.'

