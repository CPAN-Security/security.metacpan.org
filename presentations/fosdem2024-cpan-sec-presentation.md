[comment]: # (Compile this presentation with the command below)
[comment]: # (mdslides fosdem2024-cpan-sec-presentation.md --include ../media)
[comment]: # (...or by running the Makefile with "make")
[comment]: # (mdslides can be installed from https://github.com/dadoomer/markdown-slides/)

[comment]: # (THEME = solarized)

[comment]: # (minScale: 0.2)
[comment]: # (maxScale: 4.0)
[comment]: # (controls: true)
[comment]: # (width: "960")
[comment]: # (height: "700")
[comment]: # (help: true)
[comment]: # (progress: true)
[comment]: # (controlsBackArrows: "true")


# CPAN Security Working Group

Introduction & Update

Note:

Hei! I'm <NAME> and I'm here to introduce the CPAN Security Working Group to you


[comment]: # (!!!)

## CPAN-SEC

* Est. at **Perl Toolchain Summit** 2023 in Lyon 🇫🇷
* Work & care for **Security on CPAN**!

Note:

Established in April last year at the Perl Toolchain Summit in Lyon, France

[comment]: # (|||)

### PTS 2023

![Group picture showing PTS 2023 pariticipants](media/pts-group-picture-PTS2023.jpeg)

Note:

* (Almost) everyone at the 2023 Perl Toolchain Summit


[comment]: # (!!!)

## In-Scope Security Topics

Note:

Here are some of the things we care about!


[comment]: # (|||)

### Security Outreach & Information

👉 Facilitating **responsible/coordinated disclosure** between authors, reporters and users.

* We register CVEs and **notify** stakeholders; **coordinate** and triage vuln reports; **help** authors and reporters, so **vulns don't get ignored**
* CVE-2023-7101 **Spreadsheet::ParseExcel** (RCE affecting Barracuda Email Appliances)
* CVE-2024-23525 & CVE-2024-22368 **Spreadsheet::ParseXLSX**
* Pre-release coordination via cpan-security@perl.org, and tools like CC/VINCE


Note:

Keep different information channels (websites, social media) up-to-date and relevant with info on incidents, best practices and other documentation.

VINCE – Vulnerability Information and Coordination Environment

Topics not under embargo are discussed on IRC


[comment]: # (|||)

### Vulnerability Index

👉 **Audit** and track vulnerabilities

* #TODO

Note:

Improve security awareness by standardizing and publishing CPAN package vulnerabilities in relevant indices (our own, or CVE, or other).


[comment]: # (|||)

### Provenance & Supply Chain Security

👉 Establish a Secure CPAN Downloads

* TLS support in all CPAN clients (cpanpm, cpanm, etc)
* Implementing "The Update Framework" in CPAN
    * Repository signatures (yes this is from CPAN)
    * Author signatures (yes this is from AUTHOR)


Note:

We want to make TLS in cpan clients on by default, with cert verfiicaton on

Looking at getting The Update Framework (pypi has some implementation of this) as a supported, this is in addition to TLS

The TUF spec supports repo and author signing

TUF mitigates attacks that the current PGP signed CHECKSUMS implemetation is vulnerable to, like replay attacks and downgrade attacks,


[comment]: # (|||)

### Metadata & Software Bills of Materials

👉 **SBOM** creation and verification

* #Ongoing – CPAN PackageURL in spec
* #TODO – PackageURL-enabled CPAN tooling
* #TODO – SBOM-enabled CPAN tooling

Note:

Support risk analysis and management by writing tooling for managing standard SBOM objects like OWASP CycloneDX or SPDX, and do this by using existing and new CPAN metadata.

Improve interoperability with non-CPAN package indices


[comment]: # (|||)

### Transparency Logs

👉 Tooling for **third-party monitoring** of&nbsp;package&nbsp;changes

* #TODO – Sigstore for CPAN

Note:

Write tooling for monitoring package updates and integrity checking of metadata using tools like `sigstore` or `sigsum`, or take inspiration from `transparency.dev`.


[comment]: # (|||)

### Security Patch Tooling

👉 Tooling for CPAN Distro security patches to enable high-priority updates

* #TODO

Note:

Enable high-priority updates of CPAN packages, by developing tooling for publishing and applying third-party security patches to CPAN distributions with non-responsive authors.


[comment]: # (|||)

### Privacy and Compliance

👉 Share information around CPAN metadata, GDPR, CRA, PLD, and NIS2 compliance guides and other relevant regulations.

* #Ongoing – CPAN-SEC Reading List

Note:

Still lots to do!


[comment]: # (|||)

### Software Composition Analysis

👉 Promote and create tooling for detecting known vulnerabilities.

* #TODO

Note:

* Analyze dependencies for known vulnerabilities


[comment]: # (|||)

### Governance, Policy & Funding

👉 Governance, Policy & Funding

* Pre-Release Disclosure Agreement
* #Ongoing – Charter
* #Ongoing – CPAN Supply chain overview

Note:

* Establish constructive rules, playbooks, governance, policy, and funding channels for security work that is needed.


[comment]: # (|||)

### And more!

👉The security landscape is evolving, so must CPAN!

* Perl and CPAN is in use **everywhere**
* New security demands from authorities
* Old "workarounds" and "conveniences" are not acceptable any more
* Interoperability across ecosystem boundraries

Note:

And more!

Let's have an organization in place that can help improve our security landscape as we discover new vulnerabilities and issues!
Sometimes, response time is of the essence, and that means someone has to be there to respond.

Interoperability – Perl and CPAN is part of a larger Open Source landscape!


[comment]: # (!!!)

## New security demands

* **Increased demands from upcoming laws** on supply chain security and metadata
    * US [EO 14028](https://www.whitehouse.gov/briefing-room/presidential-actions/2021/05/12/executive-order-on-improving-the-nations-cybersecurity/) _Improving the Nation’s Cybersecurity_
    * EU [NIS2 Directive](https://digital-strategy.ec.europa.eu/en/policies/nis2-directive) &amp; [Cyber Resilience Act](https://digital-strategy.ec.europa.eu/en/library/cyber-resilience-act)
* **Raise community awareness** on security topics
* **Show** that CPAN authors are **getting their ducks in&nbsp;a&nbsp;row**&nbsp;🦆🦆🦆🦆

Note:

Why?
* Increased demand from upcoming laws

EU NIS2 Directive 2022/2555
* Applies to producers of software used by EU institutions that manage **critical infrastructure**
* To be implemented in local law by October 2024

EU Cyber Resilience Act
* CE certification of software used in and with **internet-connected devices**
* Expected to be implemented by July 2025

US Executive Order 14028
* "on Improving the Nation’s Cybersecurity"
* For anyone working with or selling to the US federal government
* In effect as of May 2021

Also: Raise awareness on impact and responsibility around security on CPAN

Also: This is a massive trust-building exercise!

[comment]: # (!!!)

### Who are we?

**garu**, **haarg**, **ingy**, **jjatria**, **klapperl**, **leont**, **oalders**, **petek**, **reneeb**, **sam**, **sjn**, **stigo**, **timlegge**, **Tux**, …and others!


Note:

With varying levels of involvement, we're…

Breno, Graham, Ingy, José, Andreas, Leon, Olaf, Pete, Renée, Sam, Salve, Stig, Tim, Merijn, …and others!


[comment]: # (!!!)

### CPAN-SEC WG

![Group picture showing stigo, ingy, sjn, leont, tux and garu](media/cpan-sec-group-picture-PTS2023.jpeg)

Note:
* Stig
* Ingy
* Salve
* Leon
* Merijn
* Breno

[comment]: # (!!!)

### Join us!

Do you…

* …Work with & **care about security**?
* …Have **spare tuits**?
* …Have a **security commons** aware employer?
* …Enjoy getting your **ducks in a row**? 🦆🦆🦆🦆

Note:

* Do you have a **security background** or care about the toolchain?
* Do you have **time to volunteer**?
* Is your employer willing to **dedicate a percentage of your time** to improve our security commons?

We need volunteers!


[comment]: # (!!!)

### Find us!

ircs://ssl.irc.perl.org:7062/#cpan-security

https://security.metacpan.org/

mailto:cpan-security@perl.org


Note:

We're on the web, IRC, mail and eventually on other places.


[comment]: # (!!!)

# Questions & Comments

[comment]: # (!!!)

# Thanks!

* Salve J. Nilsen

🦆🦆🦆🦆🦆🦆


Note:

Thanks!
