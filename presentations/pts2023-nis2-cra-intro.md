[comment]: # (minScale: 0.5)
[comment]: # (maxScale: 4.0)
[comment]: # (controls: true)
[comment]: # (width: "90%")
[comment]: # (height: "90%")
[comment]: # (help: true)
[comment]: # (progress: true)
[comment]: # (controlsBackArrows: "hidden")


# NIS2 + CRA

* A short introduction to NIS2 and CRA
* Current concerns
* Ramifications
* Suggested actions


[comment]: # (!!!)

## What is NIS2?

**Network and Information Security Directive II 2022/2555**

\
*Directive on measures for a high common level of cybersecurity across the Union*

* Directive – applies to EU member states; requires transposing into national law
* Increase cybersecurity in general, across EU
* Adopted on **Nov 28, 2022**
* Must be implemented in national laws by **Oct 17, 2024**
* Applies to **many businesses** (more later)
* Many new & sensible security demands (security professionals are positive)

Claim: **Does NOT apply directly to Open Source projects**

\
Response: **Meaningless claim** – indirect consequences (more later)


[comment]: # (|||)

## NIS2 – What are the liabilities?

* Fines up to **€ 10,000,000** or **2% of global revenue** – whatever is higher
* Management liability (fines, jail)


[comment]: # (|||)

## NIS2 – Who does it apply to?

Essential and important entities (Annex II)

* …All Large and medium-sized companies in EU/EEA
* …All **Essential and important entities**, no matter size
* …Businesses not based, but offer services within EU

(est. 40,000 businesses in Germany alone)


[comment]: # (|||)

## NIS2 – What is demanded?

* …All-hazards approach to risk assessment of all relevant IT systems and components
* …Common policies on risk analysis, **incident handling**, **crisis management** & more
* …Common practices for Business continuity, **Supply-chain security**, cryptography, access control policies, multi-factor auth, etc.
* …Defined procedures for vulnerability handling, disclosure, incident notification, etc.
* …Define basic cyber hygiene practices (e.g. **secure by default**)
* …and more!


[comment]: # (|||)

## NIS2 – Supervision and audits?

* Essential entities should expect surprise audits (ex ante com


[comment]: # (|||)

## NIS2 – Sectors covered by the directive

|                                |                     |
| ------------------------------ | ------------------- |
| **Networks & communication**   | Energy              |
| **Banking & Financial**        | Water supply        |
| Healthcare                     | **Pharmaceuticals** |
| Waste management               | Postal              |
| Space                          | Chemicals           |
| Digital services, social media | Food                |
| Public administration          | & More…             |

([Full overview of entities](https://ec.europa.eu/newsroom/dae/redirection/document/72155))

[comment]: # (|||)

## NIS2 – References & Links

* EU Publication office’s [Summary of Directive (EU) 2022/2555](https://op.europa.eu/en/publication-detail/-/publication/21efc84b-bdeb-11ed-8912-01aa75ed71a1)
* NIS2 Directive (EU) 2022/2555 [full text](http://publications.europa.eu/resource/cellar/9b84d482-85bd-11ed-9887-01aa75ed71a1.0006.03/DOC_1)
* Article: [EU directive NIS2: Open source is the key to success](https://www.endian.com/company/news/eu-directive-nis2-open-source-is-the-key-to-success-269/)
* [High-level overview of affected sectors](https://ec.europa.eu/newsroom/dae/redirection/document/72155)
* [Deloitte analysis of NIS2 focus areas](https://www2.deloitte.com/se/sv/pages/risk/articles/key-focus-areas-for-nis2-compliance.html)


[comment]: # (!!!)

## What is CRA?

* Cyber Resiliency Act
* Regulation – applies directly to EU/EEA members
* About to be adopted, as of 2023-04
* Additional security requirements to hardware and software products and components ("digital elements")
* A "CE marking" of physical products, including it's software and it's Open Source dependencies
* Distinguishes between "critical products" (Class I) and "products" (Class II) – (Ref: CRA Annex III)


[comment]: # (|||)

## CRA – Applies to…

| Class I                        | Class II              |
| ------------------------------ | --------------------- | 
| Identity management systems    | Operating systems     |
| **Network management systems** | PKI infrastructure    |
| **Network monitoring**         | Firewalls, IDS        |
| Update/patch management        | & Much more!          |

[Source](https://blog.nlnetlabs.nl/open-source-software-vs-the-cyber-resilience-act/#products-critical-products-%E2%80%93-and-consequences)


[comment]: # (|||)

## CRA – Liability

* Maximum fines of €15,000,000
* …or 2.5% of annual turnover
* …whichever is highest of the two.


[comment]: # (|||)

## CRA – Requirements

* Any devices (hardware and software) must handle **essential cybersecurity requirements**
    * *Unclear what these are at the moment* – **TBD**
    * May include update- and notification components, supply-chain security
* If law applies, it requires business to do risk analysis self-assessment, according to published guidelines
* Law requires both risk assessment and documentation to show compliance
* Failing to do this risks Significant Fines.
* Open Source Software may or may not be part of this assessment
* Risk-averse businesses are likely to assess their OSS dependencies anyway!

\
Est. 92-98% of applications use OSS in their stack (sources differ)

\
Approx. 21% of security incidents are supply-chain attacks.


[comment]: # (|||)

## CRA – Current concerns

* Directive feedback periods are finished (Jan '23)
* Very few actual open source communities offered feedback
* Still some confusion on demarcation between "commercial" and "open source"

Assuming any direct ramifications are resolved.

**Our main problems are likely to be with the INDIRECT ramifications**.


[comment]: # (|||)

## CRA – Community ramifications 1/3

* Multiples of 10,000's (!!) of businesses will take a hard look at their Open Source dependencies

* Each will find they depend on 100's or 1000's of individual Open Source projects.

* Each project is likely to be judged on responsiveness, sustainability, security risks and more.

* Their meta-communities will be judged on Supply chain maturity and security, incident response procedures, tooling and infrastructure, and more.

* Security issues are likely to become very visible, quickly showing which communities are high-risk.

* Auditors and compliance officers are likely to function as demand-leaders for new requirements

* Insurance companies will make decisions based on what they learn as they explore the new security and liability landscape

[comment]: # (|||)

## CRA – Community ramifications 2/3

* On a technical side – increased demand for…
    * Tooling and support for **dependency management** (SBOM)
    * Tooling and support for **risk and security assessment**
    * Tooling for supporting documentation and risk assessment
* On a training & documentation side – increased demand for…
    * Clarity around project sustainability, decision-making and contribution methods
    * Clarity around governance, adoption and forking
    * Clear guides on how to identify responsible parties, if any
    * Updated FAQ's, HOWTO's and README's
* On a community & licensing side – increased demand for…
    * Clear guides on how to interact constructively with individual projects – "How to be a good Open Source citizen"
    * Clarity around liability regarding different licenses and their consequences
    * Clarity around governance and conflict resolution mechanisms


[comment]: # (|||)

## CRA – Meta-community ramifications 3/3

"Community of communities", e.g. "The Raku community"

* This is likely to require extensive capacity-building
    * Start fundraising. This will cost money no matter what we do.
    * Identify long-running tasks that demand funded work/no-one is willing to do volunteer for
    * Explore alternatives for funding meta-community work like above, and/or developer work that is relevant for stakeholders.
    * Establish recommended developer funding channels (e.g. tidelift.com)

[comment]: # (|||)

## CRA – Links and resources

* https://digital-strategy.ec.europa.eu/en/library/cyber-resilience-act
* The [Articles of the Cyber Resilience Act](https://www.european-cyber-resilience-act.com/Cyber_Resilience_Act_Articles_%28Proposal_15.9.2022%29.html) (complete law text)
* Bert Huber's excellent overview, [Part I](https://berthub.eu/articles/posts/eu-cra-secure-coding-solution/), [Part II](https://berthub.eu/articles/posts/eu-cra-practicalities/)
* EU source: https://ec.europa.eu/info/law/better-regulation/have-your-say/initiatives/13410-Cyber-resilience-act-new-cybersecurity-rules-for-digital-products-and-ancillary-services_en
* NLNet Labs excellent overview: https://blog.nlnetlabs.nl/open-source-software-vs-the-cyber-resilience-act/
* Eclipe Foundation's statement: https://eclipse-foundation.blog/2023/01/15/european-cyber-resiliency-act-potential-impact-on-the-eclipse-foundation/


[comment]: # (!!!)

# Possible consequences

What can we predict is likely to happen?


[comment]: # (|||)

## Business ramifications

* NIS2/CRA compliance is a major upcoming cost center (some est. 21% increase in development cost).
    * Cost savings are likely to be a major focus
    * "What existing tooling can we use?"

* Ways to **reduce the cost of managing large dependency trees**
    * Option 1: Use existing community infrastructure that helps them manage and improve the risk landscape
    * Option 2: Roll your own // in-house forks
    * Option 3: Reduce the number of communities to interact with


[comment]: # (|||)

## Community ramifications

* Increased focus on security is likely to reveal more bugs and a greater pressure on volunteers
* Community inaction may lead to active disengagement from users
* Perceived lack of professionalism may lead to reputation hits
* Lack of transparency around these processes will reduce trust in community and it's capabilities to manage the new reality
* If businesses choose to re-implement their stack, they may choose software ecosystems that offer superior security tooling, responsiveness, etc.


[comment]: # (!!!)

## Remedies

What can we do about this?


[comment]: # (|||)

## Remedy 1/5 – fact-finding

* Set up a project with the task to **research, enumerate and report** on ongoing and current issues with software, infrastructure, policy, and governance that must be addressed by the Perl/Raku/CPAN community members, TPRF or other (possibly funded) dedicated organizations.


[comment]: # (|||)

## Remedy 2/5 – funding

* Create **avenues for support & funding**, to offset existing risk of harassment, reduce likelihood of parallel work (waste). This includes offering well-published options for businesses who wish to fund cross-community efforts like this.

* Create avenues for **experts to receive funding** for solving tasks related to identified issues.

* Set up **statistics gathering** so we can get some real data on how many/who contacts TPRF, so this can be used as leads for further fund-raising.
 

[comment]: # (|||)

## Remedy 3/5 – guides

* Establish, publish and manage **clear and authoritative guides on how to stay informed** on incidents, practice responsible disclosure, and other common security-related issues and tasks.

* Offer **guides**, best practices and check-lists on **how to set up and manage a well-run Perl/Raku/CPAN application software life-cycle**.

[comment]: # (|||)

## Remedy 4/5 – liaisons

* Set up and **fund a dedicated security auditor & OSPO community liaison**, that also can help resolve ongoing issues businesses may have.


[comment]: # (|||)

## Remedy 5/5 – culture

* Lead, execute and **promote efforts to establish and maintain a long-term healthy culture for security culture** within our communities.
* Establish a yearly security summit, based on the model of PTS and similar events.
* Set up a Perl/Raku [CVE Numbering Authority](https://www.cve.org/PartnerInformation/ListofPartners), like many other large projects have done.


[comment]: # (!!!)

## Links and resources

* https://berthub.eu/articles/posts/eu-cra-secure-coding-solution/
* https://fosdem.org/2023/schedule/event/cyber_resilience/
* https://blog.nlnetlabs.nl/open-source-software-vs-the-cyber-resilience-act/

[comment]: # (!!!)

## Thank you!

Salve J. Nilsen (Oslo Perl Mongers)

Mastodon: @sjn\@chaos.social

Twitter: @sjoshuan
