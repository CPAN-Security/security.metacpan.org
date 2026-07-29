---
layout: single
published: true
toc: true
title: "17 reality checks for securing our open source commons infrastructure"
date: 2026-02-15 17:15:00 +0000
collection: blog
tags: authors guides cpan modules security "open source" cra steward "cyber resilience act" principles
author: sjn
author_profile: true
excerpt: "17 reality checks for interacting with the open source software projects – and people – you depend on, to help secure the digital commons you (and everyone) depends on"
---

## Unpaid volunteers have become critical for managing business risk. Why?

{: .align-right style="max-width: 38%; margin: 0 0 1em 2em !important;"}
> [!NOTE]
> **Who is the intended audience?**
> * Market authorities, Compliance officers, Regulators.
> * CEO, CTO, CIO, CISO, other management.
> * OSPO, Procurement, Legal staff.

With the main body of the EU Cyber Resilience Act (CRA) coming into effect in December 2027, cybersecurity is expected to become an important requirement of all CE-marked products placed on the EU market.
One of the first steps in preparing for the CRA, will relate to mapping out the software dependencies of these products, and ensure that each dependency is _taken care of appropriately_.
The vast majority (70-90%, according to [Linux Foundation](https://www.linuxfoundation.org/blog/blog/a-summary-of-census-ii-open-source-software-application-libraries-the-world-depends-on)) of these dependencies are Open Source Software (OSS) components, and many of these are likely to get increased scrutiny from manufacturers in order to reduce security-related risks in their products.

{: .align-right style="max-width: 38%; margin: 0 0 1em 2em !important;"}
> [!TIP]
> **How do I know _who I am relying on_?**
> * OSS Components have projects, which have maintainers, contributors and communities.
> * Communities may consist of contributors working for Businesses, unpaid Volunteers or others.

This means there is a need for all affected businesses to come to terms with their role in these OSS ecosystems, and what the rules of engagement are in the particular communities they depend on.
Cultural misalignment with the communities one relies on may lead to alienating the same people who take care of parts of the software you use.

Let's first look at what problem needs to be solved, then describe the context it needs to be solved in, and finally look at a short check-list that can assist one towards good solutions.


## Performing _Due Diligence_ while depending on volunteers

{: .align-right style="max-width: 38%; margin: 0 0 1em 2em !important;"}
> [!TIP]
> **What is _Due Diligence_ and _Due Care_?**
> *Due Care* describes *the actions a competent, reasonable and prudent person is expected to perform* during an event.
> *Due Diligence* describes *the preparations this competent, reasonable and prudent person has to do in order to succeed* acting with Due Care.

When a serious incident happens or a critical vulnerability is discovered, we are expected to conduct ourselves with the _Due Care_ of a competent person in a similar situation – and likewise, we are expected to have prepared for this with _Due Diligence_.

So when an integrator or manufacturer performs their _Due Diligence_, there are a number of steps they may consider when volunteers are involved:

* Start with ensuring the software _under your own control_ lives up to your own expectations. This should include an overview of your software's dependency graph.
* Take a hard look at what Open Source projects and communities you depend on, and keep track of this information in your software's SBOM documents.
* Perform a risk assessment of these, to determine which ones require attention first, second, and so on.
* With this assessment in hand, take steps to address or mitigate any issues you have identified – this is your _Due Diligence_.

The details of these steps are outside the scope of this article.
Though while the details are likely to depend on the software and circumstances unique to you, it's reasonably safe to assume you may encounter a few common scenarios:

* A significant number of components in your software's digital infrastructure are Open Source projects.
    * This means you _may_ have a real influence in improving the compliance and sustainability of these, without having to bear the full cost of this responsibility.
* As long as you take into account licensing terms and ways of working for each component project, you are very likely to find ways to lower any risks associated with using these components.
* If all the "low-hanging fruits" have been addressed or mitigated (by yourself, or others), you may still wish to find ways of improving the security posture of any given project, by reaching out and supporting them or related ecosystem support organizations.
    * Long-term sustainability is also a security concern; Is the project being taken care of for the expected life-time of your products or services?
* And as a last resort, you always have the option to adopt, create a private or a public fork, or to migrate or re-implement.

Whatever path you choose, please note that _no "gratis" options remain_.
Either you take upon yourself the full cost of maintenance, or you share this cost with others by using and supporting Open Source software.

To help you navigate this, here are some useful "Free and Open Source community _reality checks_".

## 17 _Reality checks_ about Open Source communities

### 1. Most of everyone's digital infrastructure is in the digital commons

The Open Source components, their communities, and the ecosystems your business uses as a digital bedrock, are produced in the open – to a large extent with volunteer effort.
If you rely on these in any substantial way, then you rely on _volunteers_.
Take a moment to **let this fact sink in** so you completely realize the implications.

* You have externalized costs that shouldn't be externalized.
* You are not alone in having these costs.
* This digital infrastructure is still useful and valuable, even after assuming your share of the maintenance costs.




### 2. There is no unified Open Source community

While a few Open Source communities are well-known (and therefore somewhat safe to assume are well-organized and well-resourced), you're likely to find these on the left side of the power law graph.
Expect a substantial portion of your dependencies are found in the "long tail" part of the power law graph.
Check your assumptions on how to interact with these, and take into account their needs and ways of working when you do interact.
Each project has its own community, culture, priorities and habits.


### 3. Open Source was never free

The cost of creating and maintaining your infrastructure was never free.
The cost for you was always _externalized_, meaning that you benefited from other people's investments of time and attention.
While assuming this will always remain the case is reckless, there's time for your organization to adapt and learn – the infrastructure is still maintained collaboratively while you get your budgets and organization in order.

Your experiences and resources are still welcome, and are likely to offer cheaper and less risky solutions than anything you might gain from switching to an alternative or by rewriting your digital foundation.

In the meantime, learning by doing works well: Your experiences and resources are still welcome, and are likely to offer cheaper and less risky solutions than anything you might gain from switching to commercial alternatives or by attempting a rewrite of your digital foundation.


### 4. Not all Open Source projects are your _third party_ suppliers

You have almost certainly no contracts with the Open Source communities you rely on, which means they are not your commercial suppliers.
Still, you might depend on their software in critical code-paths and for business-critical applications, so treating them as "third party suppliers" may be inadvisable.

A more constructive approach is to consider them as your "Open Source colleagues", "voluntary second-party suppliers", or "digital infrastructure partners" and treat them accordingly.

Assume that you both have a genuine interest in the correctness, security, resiliency, reliability and usefulness of their code, and therefore that you have common goals and good reasons to collaborate.

If you decide to think of them as a "third party supplier" despite this fact, then please accept that they still have no reason to treat you as a valued customer: It costs them literally nothing to ignore you.

Ask yourself – "Why should they care about me?" – You are not part of their community of "second parties", you are just an incidental "third party" bystander, who does nothing to contribute or support their project.

You are already getting their software gratis, and they are already absorbing the cost of maintaining it – the same costs you already have externalized.


### 5. Most Open Source maintainers are not motivated by pay

Instead, they _enjoy_.
They may find joy in learning, helping, playing or just creating something they can _be proud of_, or just _finish_.
Whatever their intrinsic motivation is, they spend their one irreplaceable, non-refundable resource on it: their time and attention.
And when they encounter others with the same or similar interests and willingness to spend time and tuits, they may discover they created a fertile ground for friendships to develop.
If you bring a transactional mindset into this fertile ground, the others will rightfully look at you as someone who says "If I give you $100, will you be my friend?"


### 6. Your own Open Source bedrock is supported by _you_

You may be relying on thousands, if not tens of thousands of components and their maintainers and communities.
Interacting with all of them may seem daunting, but fortunately isn't necessary.
You can manage this by prioritizing which projects to support by performing a risk assessment of your own application dependency graph.
The outcome of this risk assessment also hints at how you can support these projects.
If you require project predictability, reliability or responsiveness from the communities on the top of your list, you can look for ways to encourage this behavior where it is needed.
This may require you to invest in fostering trust in these communities, so they may continue providing a safe and secure foundation for your business for the full life-time of your applications.

1. Look for ways to strengthen the communities where their need is the greatest – not only in the large and "important" parts of your infrastructure, but also the smaller ones who have communities that may be resource-starved or crumbling.
2. If a component is valuable to you, then you need to take care of it accordingly, regardless of whether it is Open Source or not.
3. While this goes on, you retain the freedom to contribute and verify under the terms of their Open Source license.


### 7. Open Source maintainers also have to live

After work, family, sleep and recreation, there may not be much time left to work on Open Source.
This may be different if the maintainer has the resources to set aside dedicated time, like working for an employer who is interested in the well-being of the project, or if the maintainer uses the project itself as recreation or a safe-space.
If the demands to their project becomes too great (e.g. due to popularity), any changes to their way of working needs to happen on their terms.


### 8. Some Open Source work is extremely boring

And boring work tends to get no volunteers.
Usually, this isn't a problem, until someone feels it is.
Do you feel the problem?

Then it's your time to volunteer.
Problems aren't fixed by bystanders.


### 9. Your dependency graph is your reliance graph

{: .align-right style="max-width: 38%; margin: 0 0 1em 2em !important;"}
> [!TIP]
> **What is a dependency graph?**
> * A dependency is a software component that is required for another software component to function as expected.
> * Example: A component for using a network protocol; A remote service the application uses; Data describing the sorting rules or time-zones used.
> * Dependencies may themselves have dependencies, and these again have their own dependencies, and so on.
> When we follow these, we map out a _dependency graph_.


### 10. Your Open Source Supply Chain is itself part of your dependency graph

{: .align-right style="max-width: 38%; margin: 0 0 1em 2em !important;"}
> [!TIP]
> **What is an OSS Supply Chain?**
> The software components you depend on are distributed to you in any of a number of channels.
> * Your libraries and modules may be used directly through the tooling made available though your programming language ecosystem.
> * These libraries may also be vetted, fixed, re-packaged and made available through any number of OS distributions, like Linux, FreeBSD and many others.
> * These package and OSes may also be made available in convenient virtual machine images or containers.
> The security, reliability, support terms, interoperability commitments, update cadence, responsiveness and risk appetite will differ depending on where in the supply chain you choose to get your software from.


_OSS Supply Chains and ecosystems are themselves OSS projects_, and due to historical reasons, _they are silos_.
Therefore one can say the same of their security posture – they are inward-looking and .
The work necessary for improving this also requires time and attention from their respective communities.
This may require efforts toward the adoption of technologies like PURL or other SBOM-related standards, to enable you to create a complete cross-ecosystem map of your dependencies.
More importantly, the success, availability and prevalence of these standards are term-setting for your expenses to become compliant.


### 11. New regulations are already putting a disproportionate burden on Open Source ecosystems and communities

These communities are often central in setting the terms for what solutions may be considered "easy to adopt" by users, businesses and manufacturers in order for them to become compliant.
This means there's a need for Open Source Software communities and ecosystems to be "first and earliest in class", on pain of manufacturers balkanizing the security landscape by "inventing their own wheels", or buying into third-party "solutions" that expose them to new forms of risk.
Preventing this requires resources and attention that currently aren't available for the term-supplying OSS ecosystems and projects out there.


### 12. Support isn't guaranteed, and neither is responsiveness

Open Source maintainers most commonly share their projects for personal reasons, and not for commercial reasons.
If commercial expectations are to be met, then the businesses requiring these need to ramp up their level of support of the projects themselves, or find other ways to get the required guarantees.


### 13. Open Source projects thrive on goodwill and contributions, not assessments and analysis




### 14. Open Source ROI is too high, and everyone knows it

An article by Hoffmann, Nagle & Zhou, _The Value of Open Source Software_ (Harvard Business School Working Paper 24-038, January 2024), revealed that the projects they analyzed had an estimated investment of 4.15 Billion USD, and that this lead to an estimated value of 8.8 Trillion USD.
While this isn't the same as putting a dollar into a machine and getting 2000 dollars back, it *is* closer to getting an average of 99.95% rebate on the software one is using to create this value.
While this "rebate" exists by design (and a consequence of the OSS license language), this has led to public outcry regarding the risks coming from these projects not being supported in a sustainable manner.
What you should ask is «How much less than a 99.95% rebate can my business live comfortably with?»


### 15. Open Source Security doesn't improve in a vacuum

If your venture relies on an Open Source component's security, you are now a stakeholder in its project health, sustainability and continued capability to respond to discovered vulnerabilities and incidents.


### 16. Many maintainers don't like the thought of receiving money for something they _enjoy_




### 17. The median Open Source project size is 1 (one)




## Summary


### Acknowledgements

Gratitude go out to the following contributors:

- @lizmat
- @leejo


*[SBOM]: Software Bill of Materials – a standard machine-readable file that describes what an application or a component is made of, license terms and other metadata.
*[CRA]: Cyber Resilience Act – a EU product law that, starting in 2027, requires CE-marked products with digital elements also have good cybersecurity.
*[OSS]: Open Source Software – Software published under the terms of a license that adheres to the Open Source Definition, as described on opensource.org/osd
*[OSPO]: Open Source Program Office – a business section with responsibility for coordinating efforts around license compliance, OSS developer relations and corporate guidelines for use of and contributing to Free and Open Source Software.
*[PURL]: PackageURL – a standard for referring to software packages in a ecosystem-agnostic way.
*[FOSS]: Free and Open Source Software – Software published under the terms of a license that adheres to the Free Software Definition, as described on gnu.org/philosophy/free-sw
*[tuits]: A unit of attention - Stemming from the pun «I'll do it when I get a round tuit (around to it)»
