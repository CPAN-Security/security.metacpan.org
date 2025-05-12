[comment]: # (Compile this presentation with the command below)
[comment]: # (mdslides pts2024-sbom-intro.md --include ../media)
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


## CPAN Security and Sustainability in light of the EU Cyber Resilience Act

German Perl Workshop 2025

Salve J. Nilsen

🐘 Mastodon — @sjn\@chaos.social

Note:

* This talk is more about _the future_ of open source communities, than the present


[comment]: # (!!!)

### (Not a lawyer)


[comment]: # (||| data-auto-animate)

### (Not a ~lawyer~)
* (Also, not an "authority")


[comment]: # (||| data-auto-animate)

### (Not a ~lawyer~)
* (Also, not an ~"authority"~)
* I'm a _volunteer_


[comment]: # (!!! data-auto-animate)

### Cyber Resilience Act – ★ – 10th Dec 2024


[comment]: # (||| data-auto-animate)

[Article 71(2)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#071.002 'This Regulation shall apply from 11 December 2027. However, Article 14 shall apply from 11 September 2026 and Chapter IV (Articles 35 to 51) shall apply from 11 June 2026.'

### Cyber Resilience Act – ★ – 10th Dec 2024

* Into effect: **December 10th 2024**
* Main obligations: **December 11th 2027**
* Reporting obligations: **September 11th 2026**

<div style="font-size: large;">

> * Council adoption [announcement](https://www.consilium.europa.eu/en/press/press-releases/2024/10/10/cyber-resilience-act-council-adopts-new-law-on-security-requirements-for-digital-products/) – 2024-10-10
> * Obligations apply from… – [Article 71(2)]

</div>


[comment]: # (||| data-auto-animate)

## CRA TL;DR

1. Shift responsibility to the Manufacturer
2. Make security updates free
3. Add CE marking on products with software
4. Importers and Distributors become liable
5. Securing the software supply chain is mandatory
6. Risk-based security in products
7. Open Source is affected
8. Maintaining a Software Bill of Materials is mandatory
9. All products are affected

[comment]: # (||| data-auto-animate)

## CRA is a…

* A **product legislation**, intended to…
* …ensure _Products with Digital Elements_ are safe before placement on the market
* …with the intention to **increase the general Cybersecurity across Europe**

Note:


[comment]: # (|||)

## CRA applies to…

* **Manufacturers**…
  * …placing _Products with Digital Elements_ on the EU market
  * …in the course of a _commercial activity_

<div style="font-size: large;">

> * Background: [Recital 15](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=17)
> * Placing on the market: [Article 3 (21)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=140)

</div>

Note:


[comment]: # (|||)

## Products with Digital Elements are…

* Connected devices,
* Non-tangible digital products,
* […their] remote data processing solutions,
* […and] _related systems and services needed for operation_

<div style="font-size: large;">

> * Background: [Recital 9](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=10)
> * Product with Digital Elements: [Article 3 (1), (4), (6), (7)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=136)

</div>

Note:

* routers, cameras, fridges, toys, etc.
* apps or any device that is connected to the network
* Anything which has software may be affected!


[comment]: # (|||)

## CRA **does not** apply to...

* Software that is purely _part of a service_*
* Software that is covered by other regulation
* Software that is Open Source*

<div style="font-size: large;">

> * [Recital 12](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=13)
> * [Recital 18](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=21)

</div>


Notes:

*  NIS2, AI Act, Medical device regulations, DORA (Fintech)


[comment]: # (!!!)

## Five "Roles"

* Manufacturer
* Distributor, Importer, Market Authorities
* Open Source Software Steward


[comment]: # (||| data-auto-animate)

## ~Five~ Six "Roles"

* Manufacturer
* Distributor, Importer, Market Authorities
* Open Source Software Steward
* Open Source Developers*


[comment]: # (||| data-auto-animate)

## Six "Roles"

* Manufacturer
* Distributor, Importer, Market Authorities ❌
* Open Source Software Steward
* Open Source Developers*


[comment]: # (||| data-auto-animate)

## Six "Roles"

* Manufacturer 🔍
* Distributor, Importer, Market Authorities ❌
* Open Source Software Steward
* Open Source Developers*

[comment]: # (||| data-auto-animate)

[Article 3]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_3 'Definitions'

## Manufacturer

* A natural or legal person who…
    * …**develops or manufactures** products with digital elements, or
    * …**has** products **designed, developed or manufactured**, and
    * …**markets them under its name** or trademark,
    * …whether for payment, monetisation or free of charge

<div style="font-size: large;">

> * [Article 3] (12)
> * [Article 3] (13)

</div>

[comment]: # (|||)

[Article 28(1)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#028.001 'Manufacturer states that cybersecurity requirements in [Annex I] has been demonstrated'
[Article 28(4)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#028.004 'Manufacturer assumes responsibility for compliance'
[Annex I]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#anx_I 'Essential Cybersecurity Requirements'


### Obligations of Manufacturers<br> — Conformance

![CE Mark](media/280px-Conformité_Européenne.png)


* Place a CE mark on the product
    * …stating cybersecurity requirements have been demonstrated
* Manufacturer assumes responsibility for compliance

<div style="font-size: large;">

> * [Article 28(1)] - …stating that cybersecurity requirements in [Annex I] has been demonstrated
> * [Article 28(4)] - Assume responsibility for compliance
> * [Annex I] - Cybersecurity requirements

</div>


Note:

* "I am following EU Law"
* "Presumption of Conformance" when following EU Standards

[comment]: # (|||)

[Annex I, Part I]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#d1e47-68-1 'Cybersecurity requirements relating to the properties of products with digital elements'
[Annex III]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#anx_III 'Important products'
[Annex IV]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#anx_IV 'Critical products'

### Obligations of Manufacturers<br> — Conformance

[Article 7]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_7 'Important products'
[Article 8]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_8 'Critical products'
[Article 27]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_27 'Presumption of conformity'
[Article 32]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#art_32 'Conformity assessment procedures'

* Default: Self-assessment
* Open Source: Self-assessment
* Important:
   * Follow harmonized standards -> Presumption of conformance
   * 3rd-party assessment
* Critical: EU certification

<div style="font-size: large">

> * [Article 32] - Conformity assessment procedures
> * [Article 7] - Important products
> * [Article 8] - Critical products
> * [Article 27] - Presumption of conformance
> * [Annex I, Part I] - Cybersecurity requirements
> * [Annex III] - Important products (Class I and II) examples
> * [Annex IV] - Critical products examples

</div>


Note:

* Self-assessment for most cases (~90%)
* "Presumption of Conformance" when following EU Standards
* Important I: Browsers; ID management; Virus scanners; Network management systems; OSes
* Important II: Hypervisors; Firewalls; Tamper-resistant microcontrollers
* Critical: Smartcards; Smart metering systems;

[comment]: # (|||)

[Article 13(8)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.008 'Manufacturers shall ensure vulnerabilities are handled for 5 years'
[Article 13(9)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.009 'Manufacturers shall make security updates available for 10 years or longer'

### — Support period

* Default is 5 years; Can be longer or shorter
* Security fixes must remain available for 10 years after issuing

<div style="font-size: large;">

> * [Article 13(8)] - Vulnerabilities are handled for 5 years
> * [Article 13(9)] - Security updates available for 10 years

</div>


[comment]: # (|||)

[Annex I, Part I]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#d1e47-68-1 'Cybersecurity requirements relating to the properties of products with digital elements'
[Annex VII]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#anx_VII 'Content of the Technical Documentation'

### — Build & Dependencies

* Identify and document vulnerabilities and components contained in products
* Describe how the product is put together

<div style="font-size: large;">

> * [Annex I, Part I] (1) – Design and develop products with appropriate levels of cybersecurity
> * [Annex VII] 2 (a) – Describe how software components build on or feed into each other and integrate

</div>


[comment]: # (|||)

[Recital (22)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_22 'Submission of SBOMs for Open Source projects'
[Annex I, Part II]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#d1e143-68-1 'Vulnerability handling requirements'

### — Produce SBOMs

* Produce SBOMs upon request by regulators
* At minimum, top-level dependencies

<div style="font-size: large;">

> * [Recital (22)] – Market surveillance authorities can request SBOMs
> * [Annex I, Part II] (1) – identify and document […] components […] by drawing up a software bill of materials

</div>

Note:

* "covering at the very least the top-level dependencies of the products" – is a trap!

[comment]: # (|||)

[Recital (65)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#rct_65 'Notify of severe incidents or actively exploited vulnerabilities'
[Article 13(1)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.002 'Manufacturers shall ensure products are developed in accordance with essential cybersecurity requirements'
[Article 13(2)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.002 'Manufacturers shall undertake a cybersecurity risk assessment'
[Article 13(5)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.005 'Manufacturers shall exercise due diligence when integrating components, including FOSS'
[Article 13(6)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.006 'Manufacturers shall share relevant code or documentation with the supplier or maintainer of the component'
[Annex I, Part I]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#d1e47-68-1 'Cybersecurity requirements relating to the properties of products with digital elements'


### — No Vulnerabilities

* Product is **secure by default**, and **secure by design**
* Product has **no known vulnerabilities**
* 😍 Exercise **due diligence** when integrating **third party components**
* 😍 **Report vulnerabilities** to the Manufacturer or **Open Source maintainer**

<div style="font-size: large;">

> * [Article 13(1)] – Develop in accordance with essential cybersecurity requirements
> * [Annex I, Part I] (2) (a) – without known exploitable vulnerabilities
> * [Article 13(5)] – Exercise due diligence when integrating, including FOSS
> * [Article 13(6)] – Share relevant code or documentation with the supplier or maintainer of the component
> * [Recital (65)] – Notify of severe incidents or actively exploited vulnerabilities

</div>

Note:

* Due diligence – to avoid or fix the components that compromise security


[comment]: # (|||)

[Article 13(8)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.008 'Manufacturers shall ensure vulnerabilities are handled for 5 years'
[Annex I, Part I]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#d1e47-68-1 'Cybersecurity requirements relating to the properties of products with digital elements'
[Annex I, Part II]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#d1e143-68-1 'Vulnerability handling requirements'

### — Offer timely security updates

* Make security updates available for the duration of the support period
* Ensure vulnerabilities can be addressed through security updates

<div style="font-size: large;">

> * [Article 13(8)] – Vulnerabilities are handled for 5 years
> * [Annex I, Part II] – Vulnerability handling requirements
> * [Annex I, Part I] (2) (c) – vulnerabilities addressed through security updates

</div>


Note:

* Address vulnerabilities _in a timely manner_


[comment]: # (|||)

[Article 13(15)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.015 'Manufacturers shall ensure that their products is identifiable'
[Article 13(16)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.016 'Manufacturers shall indicate their name and identification'
[Article 13(17)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#013.017 'Manufacturers shall designate a single point of contact for reporting vulnerabilities'
[Article 14(1)]:https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202402847#014.001 'A manufacturer shall notify any actively exploited vulnerability contained in the product that it becomes aware of'

### — More! 

* Manufacturer is clearly identified
* Single point of contact
* Product has a unique ID
* Take part in the EU early warning notification regime
* …

<div style="font-size: large;">

> * [Article 13(16)] – Manufacturer name
> * [Article 13(17)] – Single point of contact
> * [Article 13(15)] – Product ID
> * [Article 14(1)] – Notify of exploited vulnerabilities

</div>


[comment]: # (!!!)

## Six "Roles"

* Manufacturer 🔍
* Distributor, Importer, Market Authorities ❌
* Open Source Software Steward
* Open Source Developers*


[comment]: # (||| data-auto-animate)

## Six "Roles"

* Manufacturer ✅
* Distributor, Importer, Market Authorities ❌
* Open Source Software Steward 🔍
* Open Source Developers*


[comment]: # (||| data-auto-animate)

## Open Source Software Steward





[comment]: # (!!!)

## Six "Roles"

* Manufacturer ✅
* Distributor, Importer, Market Authorities ❌
* Open Source Software Steward 🔍
* Open Source Developers*


[comment]: # (||| data-auto-animate)

## Six "Roles"

* Manufacturer ✅
* Distributor, Importer, Market Authorities ❌
* Open Source Software Steward ✅
* Open Source Developers* 🔍


[comment]: # (||| data-auto-animate)

## Open Source Developers

* CRA doesn't really talk about Open Source **Developers**


[comment]: # (|||)

### Obligations to Open Source Developers<br> – Status Quo

* CRA **does not apply** to Developers that...
    * contribute code to projects they are **not responsible for**
    * are **not monetising** the product
    * make a product that is ultimately **not intended for commercial activities**

<div style="font-size: large;">

> * [Recital (18)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=20))
> * [Recital (19)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=22))

</div>


[comment]: # (|||)

### – With an Open Source Steward

* CRA **applies voluntarily** if the Developer decides...
    * their product **is ultimately intended** for commercial activities

<div style="font-size: large;">

> * [Recital (19)](https://www.europarl.europa.eu/doceo/document/TA-9-2024-0130_EN.pdf#page=22)

</div>

[comment]: # (|||)

## Six "Roles"

* Manufacturer ✅
* Distributor, Importer, Market Authorities ❌
* Open Source Software Steward ❌
* Open Source Developers 🔍


[comment]: # (||| data-auto-animate)

## Six "Roles"

* Manufacturer ✅
* Distributor, Importer, Market Authorities ❌
* Open Source Software Steward ❌
* Open Source Developers ✅


[comment]: # (!!! data-auto-animate)

## How will this affect Open Source?


[comment]: # (||| data-auto-animate)

Note:

* "Optional" isn't really an option any more
    * Some fields are actually _required_


[comment]: # (||| data-auto-animate)


Note:


[comment]: # (||| data-auto-animate)


[comment]: # (|||)



[comment]: # (|||)



[comment]: # (||| data-auto-animate)


[comment]: # (|||)

## For discussion

* It's a mess
* It's up to volunteers to improve it
* ~"If it ain't broke, don't fix it"~
* Don't be a bystander


Note:

* "Permissionless Innovation"
* "Being a Good Open Source Citizen"
* We already know that being a bystander doesn't work – better to step up instead!


[comment]: # (!!!)

## Questions & Comments


[comment]: # (!!!)

# Thanks!

Salve J. Nilsen

🐘 Mastodon — @sjn\@chaos.social

🦆🦆
