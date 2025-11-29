---
layout: single
published: false
toc: true
title: "17 reality checks for securing our open source commons infrastructure"
date: 2025-11-15 17:15:00 +0000
collection: blog
tags: authors guides cpan modules security "open source" cra steward "cyber resilience act" principles
author: sjn
excerpt: " reality checks for interacting with the open source software projects – and people – you depend on, to help secure the digital commons you (and everyone else) depends on"
---

## Unpaid volunteers has become critical for managing business risk. Why?

{: .align-right style="max-width: 38%; margin: 0 0 1em 2em !important;"}
> [!NOTE]
> **Who is the intended audience?**
> * Market authorities, Compliance officers, Regulators.
> * CEO, CTO, CIO, CISO, other management.
> * OSPO Staff.

With the first bits of the EU Cyber Resilience Act (CRA) coming into effect in 2026, cybersecurity is required to become a primary aspect of product development.
A major part of this activity will relate to mapping out product dependencies, and ensure that each and every one of these are taken care of appropriately.
The vast majority of these dependencies are likely to be Open Source Software (OSS) components, and many of these are likely to get increased scrutiny from manufacturers in order to reduce security-related risks in their products.

{: .align-right style="max-width: 38%; margin: 0 0 1em 2em !important;"}
> [!TIP]
> **How do I know _Who_ I am relying on?**
> * Components have Projects, which have Maintainers, Contributors and Communities.
> * Communities may include Contributors from Businesses like your own.
> * These are the people who your business rely on to find and fix bugs, vulnerabilities, and other issues.

The implication is that there is a need for all affected businesses to come to terms with their role in the ecosystem, and what the rules of engagement are in the particular communities they depend on.
Missteps may lead to alienating the maintainers businesses rely on - how can this be avoided?

Let's first look at what problem needs to be solved, then describe the context it needs to be solved in, and finally look at a short check-list that can assist one towards good solutions.


## Performing _due diligence_ work involving volunteers?

When and serious incident happens or a critical vulnerability is discovered, we are expected to conduct ourselves with reasonable _Due Care_ – and before the emergency develops, to have prepared for this with _Due Diligence_.

_Due Care_ is about _what actions a reasonable person is expected to do_ (e.g. in case of an emergency), and _Due Diligence_ is about _what preparations need to happen for this reasonable person to succeed_.
When an integrator or manufacturer prepares to act with _Due Care_, they may do any number of the following actions:

* Ensure the software under their own control lives up their expectations. If one doesn't have order in one's own house, one shouldn't assume 
* Take a hard look at what open source communities you depend on, and keep track of this information in their SBOMs.
* Perform a risk assessment of these, to determine which ones require attention first.
* With the assessment in hand, have another reading of this article, and with that in mind take the next steps to address or mitigate the issues you have identified – this is your _Due Diligence_.

What these steps may be are outside of the scope of this article, but while the details will depend heavily on the software and circumstances unique to you, it's reasonably safe to assume you may encounter some common tropes.

* These projects that are part of your infrastructure, are Open Source, meaning you have a real opportunity to contribute to improving it without having to bear the full cost of doing so.
* As long as you take into account the licenses, terms and ways of working for each component project, you very likely to find ways to lower any risks associated with using these components.


## 17 reality checks about open source security and communities

### 1. Most of everyone's digital infrastructure is in the commons

The Open Source components, their communities, and the ecosystems your business uses as a digital bedrock, are produced in the open and almost exclusively with volunteer effort.
If you rely on these in a substantial way, then you rely on _volunteers_.
**Let this fact sink in** so you completely realize its implications.

### 2. There is no unified Open Source community

While a few of these communities are well-known, and therefore somewhat safe to assume as well-organized and well-resourced, you'll find these on the left side of the power law graph.
Expect that a substantial portion of your dependencies are found in the "long tail" part of this graph.
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




### 8. Some Open Source work is extremely boring




### 9. Your Open Source Supply Chains are part of your dependency graph

{: .align-right style="max-width: 38%; margin: 0 0 1em 2em !important;"}
> [!TIP]
> **What is a dependency graph?**
> * A dependency is a software component that is required for another software component to function as expected.
> * Example: A component for using a network protocol; A remote service the application uses; Data describing the sorting rules or timezones used.
> * Dependencies may themselves have dependencies, and these again have their own dependencies, and so on.
> When we follow these, we map out a _dependency graph_.

These Supply Chains and ecosystems are themselves OSS projects, and due to historical reasons, _they are silos_.
Therefore one can say the same of their security posture – they are inward-looking and in silos.
The work necessary for improving this also requires time and attention from their respective communities.
This may require efforts toward the adoption of technologies like PURL or other SBOM-related standards, to enable you to create a complete cross-ecosystem map of your dependencies.
More importantly, the success, availability and prevalence of these standards are term-setting for your expenses to become compliant.

### 10. New regulations are already putting a disproportionate burden on Open Source ecosystems and communities

These communities are often central in setting the terms for what solutions may be considered "easy to adopt" by users, businesses and manufacturers in order for them to become compliant.
This means there's a need for Open Source Software communities and ecosystems be "first and earliest in class", at the pain of manufacturers start balkanizing the security landscape by "inventing their own wheels", or buying into third-party "solutions" that exposes them to new forms of risk.
Preventing this requires resources and attention that currently aren't available for the term-supplying OSS ecosystems and projects out there.

### 11. Support isn't guaranteed, and neither is responsiveness


### 12. Open Source projects thrive on goodwill and contributions, not assessments and analysis


### 13. Open Source ROI is too high, and everyone knows it


### 14. Open Source ROSI is unknown, because nobody …


### 15. Open Source Security doesn't improve in a vacuum


### 16. Many maintainers don't like the thought of receiving money for something they _enjoy_


### 17. The median Open Source project size is 1


## Summary





*[SBOM]: Software Bill of Materials – a standard machine-readable file that describes what an application or a component is made of.
*[CRA]: Cyber Resilience Act – a EU product law that, starting in 2027, requires CE-marked products with digital elements also have good cybersecurity.
*[OSS]: Open Source Software – Software published shared a license that adheres to the Open Source Definition, as described on opensource.org/osd .
*[OSPO]: Open Source Program Office – a business section with responsibility for coordinating efforts around license compliance, OSS developer relations and corporate guidelines for use of Open Source Software.
*[PURL]: PackageURL – a standard for referring to software packages in a ecosystem-agnostic way.
*[FOSS]: Free and Open Source Software – 
*[ROI]: Return on Investment – 
*[ROSI]: Return on Security Investment –
*[CISO]: Chief Information Security Officer –
*[CIO]: Chief Information Officer – 
*[CTO]: Chief Technology Officer – 
*[CEO]: Chief Executive Officer – 
