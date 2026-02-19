---
layout: single
published: true
toc: true
title: "17 reality checks for securing our open source commons infrastructure"
date: 2026-02-15 17:15:00 +0000
collection: blog
tags: authors guides cpan modules security "open source" cra steward "cyber resilience act" principles
author: sjn
excerpt: "17 reality checks for interacting with the open source software projects – and people – you depend on, to help secure the digital commons you (and everyone else) depends on"
---

## Unpaid volunteers has become critical for managing business risk. Why?

{: .align-right style="max-width: 38%; margin: 0 0 1em 2em !important;"}
> [!NOTE]
> **Who is the intended audience?**
> * Market authorities, Compliance officers, Regulators.
> * CEO, CTO, CIO, CISO, other management.
> * OSPO, Procurement, Legal staff.

With the first bits of the EU Cyber Resilience Act (CRA) coming into effect in 2026, cybersecurity is required to become a important aspect of developing products with digital elements.
One of the first steps in preparing for the CRA, will relate to mapping out product dependencies, and ensure that each one of these are _taken care of appropriately_.
The vast majority (70-90%, according to [Linux Foundation](https://www.linuxfoundation.org/blog/blog/a-summary-of-census-ii-open-source-software-application-libraries-the-world-depends-on)) of these dependencies are Open Source Software (OSS) components, and many of these are likely to get increased scrutiny from manufacturers in order to reduce security-related risks in their products.

{: .align-right style="max-width: 38%; margin: 0 0 1em 2em !important;"}
> [!TIP]
> **How do I know _Who_ I am relying on?**
> * OSS Components have Projects, which have Maintainers, Contributors and Communities.
> * Communities may consist of Contributors working for Businesses, unpaid Volunteers or others.

This means there is a need for all affected businesses to come to terms with their role in these OSS ecosystems, and what the rules of engagement are in the particular communities they depend on.
Missteps may lead to alienating the maintainers businesses rely on - how can this be avoided?

Let's first look at what problem needs to be solved, then describe the context it needs to be solved in, and finally look at a short check-list that can assist one towards good solutions.


## Performing _due diligence_ work involving volunteers?

{: .align-right style="max-width: 38%; margin: 0 0 1em 2em !important;"}
> [!TIP]
> **What is _Due Diligence_ and _Due Care_?**
> _Due Care_ is about _the actions a reasonable and prudent person is expected to do_ during a security incident, and _Due Diligence_ is about _the preparations to make for this person to succeed_.

When and serious incident happens or a critical vulnerability is discovered, we are expected to conduct ourselves with _Due Care_ – and before the emergency develops, to have prepared for this with _Due Diligence_.

So when an integrator or manufacturer performs _Due Diligence_, there are a number of steps worth adopting when volunteers are involved:

* Start with ensuring the software under their own control lives up their own expectations.
* Take a hard look at what open source communities they depend on, and keep track of this information in their SBOM documents.
* Perform a risk assessment of these, to determine which ones require attention first.
* With this assessment in hand, take steps to address or mitigate any issues you have identified – this is your _Due Diligence_.

What these steps entail in detail, is outside of the scope of this article. Though while the details are likely to depend on the software and circumstances unique to you, it's reasonably safe to assume you may encounter a few common scenarios:

* A significant number of component in your digital infrastructure are Open Source projects. This means you may have a real influence in improving these, without having to bear the full cost of this responsibility.
* As long as licensing terms and ways of working are taken into account for each component project, you very likely to find ways to lower any risks associated with using these components.
* If all the "low-hanging fruits" have been addressed or mitigated (by yourself, or others), you may still find ways to improve the project's total security posture indirectly by reaching out and supporting relevant ecosystem support organizations.
* And as a last resort, you have always the option to adopt, create a private or a public fork, or to migrate or re-implement.

Whatever path you choose, please note that there are no "gratis" options any more.


## 17 reality checks about open source communities

### 1. Most of everyone's digital infrastructure is in the commons

The Open Source components, their communities, and the ecosystems your business uses as a digital bedrock, are produced in the open – almost exclusively with volunteer effort.
If you rely on these in any substantial way, then you rely on _volunteers_.
Take a moment to **let this fact sink in** so you completely realize its implications.

### 2. There is no unified Open Source community

While a few Open Source communities are well-known, and therefore somewhat safe to assume, well-organized and well-resourced, you're likely to find these on the left side of the power law graph.
Expect a substantial portion of your dependencies are found in the "long tail" part of the power law graph.
Check your assumptions on how to interact with these, and take into account their needs and ways of working when you do interact.

### 3. Open Source was never free

The cost of creating and maintaining your infrastructure was never free.
The cost for you was always _externalized_, meaning that you benefited from other people's investments of time and attention.
While assuming this will always be the case is reckless, there's no need to despair – the infrastructure is still maintained collaboratively.
Your experiences and resources are still welcome, and is likely to offer cheaper and less risky solutions than anything you might gain from switching to an alternative or by rewriting your digital foundation.

### 4. Not all Open Source are your _third party_ suppliers

You have almost certainly no contracts with the Open Source communities you rely on, and means they are not your commercial suppliers.
Instead, consider them as your "Open Source colleagues", "voluntary second-party suppliers", or "digital infrastructure partners" and treat them accordingly.
Assume that you both have a genuine interest in the correctness, resiliency, reliability and usefulness of their code, and therefore that you have common goals and good reasons to collaborate.
If you decide to think of them as a "third party supplier" despite this fact, then please accept that they have no reason to treat you differently.
Ask yourself – "Why should they care about you?" – You are not part of their community of "second parties", you are just an incidental "third party" user who does not contribute back.
You are already getting their software for free, and they are already absorbing the cost of maintaining it, that you have already externalized.

### 5. Your own Open Source bedrock is stabilized and supported by _you_

You may be relying on thousands, if not tens of thousands of components and their maintainers and communities; Interacting with all of them is daunting, if not impossible – therefore, prioritize (perform a risk assessment), and look for – and promote – predictability, reliability and responsiveness in the communities on the top of your list.
This is to foster trust in these communities, so they may continue providing a safe and secure foundation for your business.
In the meantime, you retain the freedom to verify this, due to them publishing under the terms of an open source license.
Look for ways to strengthen the communities where their need is the greatest – not only in the large and "important" parts of your infrastructure, but also the smaller ones who have communities that may be resource-starved or crumbling.
If a component is valuable to you, then you need to take care of it accordingly.
Regardless of whether it is Open Source or not.

### 6. Open Source Maintainers aren't motivated by pay

Instead, they _enjoy_.
They may be learning, helping, playing or just creating something they can _be proud of_, or that they may _complete_.
Whatever their intrinsic motivation is, they spend their one irreplaceable, non-refundable resource on it: their time and attention.
And when they encounter others with the same or similar interests, they may discover they made a fertile ground for friendships to develop.
If you bring a transactional mindset into this, they will rightfully look at you as someone who says "If I give you $100, will you be my friend?"

### 7. Open Source Maintainers also have to live

After work, family, sleep and recreation, there may not be much time left to work on Open Source.
This may be different if the Maintainer has set aside dedicated time, they work for an employer who is interested in the well-being of the project, or if the Maintainer uses the project itself as recreation or a safe-space.
If the demands to their project becomes too great (e.g. due to popularity), any changes to their way of working needs to happen on their terms.


### 8. Some Open Source work is extremely boring

And boring work tends to get no volunteers. 


### 9. Your Open Source Supply Chains are part of your dependency graph

{: .align-right style="max-width: 38%; margin: 0 0 1em 2em !important;"}
> [!TIP]
> **What is a dependency graph?**

> * A dependency is a software component that is required for another software component to function as expected.
> * Example: A component for using a network protocol; A remote service the application uses; Data describing the sorting rules or time-zones used.
> * Dependencies may themselves have dependencies, and these again have their own dependencies, and so on.
> When we follow these, we map out a _dependency graph_.

_OSS Supply Chains and ecosystems are themselves OSS projects_, and due to historical reasons, _they are silos_.
Therefore one can say the same of their security posture – they are inward-looking and in silos.
The work necessary for improving this also requires time and attention from their respective communities.
This may require efforts toward the adoption of technologies like PURL or other SBOM-related standards, to enable you to create a complete cross-ecosystem map of your dependencies.
More importantly, the success, availability and prevalence of these standards are term-setting for your expenses to become compliant.

### 10. New regulations are already putting a disproportionate burden on Open Source ecosystems and communities

These communities are often central in setting the terms for what solutions may be considered "easy to adopt" by users, businesses and manufacturers in order for them to become compliant.
This means there's a need for Open Source Software communities and ecosystems be "first and earliest in class", at the pain of manufacturers start balkanizing the security landscape by "inventing their own wheels", or buying into third-party "solutions" that exposes them to new forms of risk.
Preventing this requires resources and attention that currently aren't available for the term-supplying OSS ecosystems and projects out there.

### 11. Support isn't guaranteed, and neither is responsiveness

Open Source Maintainers


### 12. Open Source projects thrive on goodwill and contributions, not assessments and analysis


### 13. Open Source ROI is too high, and everyone knows it


### 14. Open Source Security doesn't improve in a vacuum


### 15. Many maintainers don't like the thought of receiving money for something they _enjoy_


### 16. The median Open Source project size is 1


### 17. –


## Summary


### Acknowledgements

Gratitude go out to the following contributors:

- @lizmat
- @leejo


*[SBOM]: Software Bill of Materials – a standard machine-readable file that describes what an application or a component is made of, license terms and other metadata.
*[CRA]: Cyber Resilience Act – a EU product law that, starting in 2027, requires CE-marked products with digital elements also have good cybersecurity.
*[OSS]: Open Source Software – Software published under the terms of a license that adheres to the Open Source Definition, as described on opensource.org/osd .
*[OSPO]: Open Source Program Office – a business section with responsibility for coordinating efforts around license compliance, OSS developer relations and corporate guidelines for use of and contributing to Free and Open Source Software.
*[PURL]: PackageURL – a standard for referring to software packages in a ecosystem-agnostic way.
*[FOSS]: Free and Open Source Software – Software published under the terms of a license that adheres to the Free Software Definition, as described on gnu.org/philosophy/free-sw .
