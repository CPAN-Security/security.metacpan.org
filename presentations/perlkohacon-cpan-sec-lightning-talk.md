[comment]: # (Compile this presentation with the command below)
[comment]: # (mdslides perlkohacon-cpan-sec-lightning-talk.md --include ../media)
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

This is an introduction!

Note:

Hei! I'm <NAME> and I'm here to introduce the CPAN Security Working Group to you


[comment]: # (!!!)

## CPAN-SEC

* Made @ **Perl Toolchain Summit** 2023 in Lyon, France
* We care about **security on CPAN**!

Note:

Established in April this year at the Perl Toolchain Summit in Lyon, France



[comment]: # (!!!)

## What do we care about?

Note:

This is an introduction and a **call for participation**!

Here are some of the things we care about!


[comment]: # (|||)

### CPAN Vulnerability Index

👉 **Audit** and track vulnerabilities

Note:

Improve security awareness by standardizing and publishing CPAN package vulnerabilities in relevant indices (our own, or CVE, or other). Possibly register as a CVE Numbering Authority.


[comment]: # (|||)

### CPAN Provenance & Supply Chain Security

👉 Establish a **trusted publishing infrastructure**

Note:

Establish a trusted publishing infrastructure and tooling, with inspiration from `in-toto.io` and "Salsa" (`SLSA`). 


[comment]: # (|||)

### CPAN Software Bills of Materials

👉 **SBOM** creation and verification

Note:

Support risk analysis and management by writing tooling for managing standard SBOM objects like OWASP CycloneDX or SPDX, and do this by using existing and new CPAN metadata.


[comment]: # (|||)

### CPAN Transparency Logs

👉 Tooling for **third-party monitoring** of&nbsp;package&nbsp;changes

Note:

Write tooling for monitoring package updates and integrity checking of metadata using tools like `sigstore` or `sigsum`, or take inspiration from `transparency.dev`.


[comment]: # (|||)

### CPAN Security Patch Tooling

👉 Tooling for CPAN Distro security patches to enable **high-priority updates**

Note:

Enable high-priority updates of CPAN packages, by developing tooling for publishing and applying third-party security patches to CPAN distributions with non-responsive authors.


[comment]: # (|||)

### CPAN Security Outreach & Information

👉 Security and **incident communication** through relevant&nbsp;media&nbsp;channels

Note:

Keep different information channels (websites, social media) up-to-date and relevant with info on incidents, best practices and other documentation.


[comment]: # (|||)

### And more!

* 👉 Software Composition Analysis
* 👉 CPAN-SEC Governance, Policy & Funding
* 👉 Rich Metadata & Dependencies
* 👉 Privacy and Compliance

Note:

And more!

* Analyze dependencies for known vulnerabilities
* Establish constructive rules, playbooks, governance, policy, and funding channels
* Improve interoperability with non-CPAN package indices
* Track legal and privacy issues around CPAN metadata, and compliance with regulations


[comment]: # (!!!)

## Why now?

* **Increased demands from upcoming laws** on supply chain security and metadata
    * US [EO 14028](https://www.whitehouse.gov/briefing-room/presidential-actions/2021/05/12/executive-order-on-improving-the-nations-cybersecurity/) _Improving the Nation’s Cybersecurity_
    * EU [NIS2 Directive](https://digital-strategy.ec.europa.eu/en/policies/nis2-directive) &amp; [Cyber Resilience Act](https://digital-strategy.ec.europa.eu/en/library/cyber-resilience-act)
* **Raise community awareness** on security topics
* CPAN is in the dependency trees of _many_ businesses, so it's high time we **get our ducks in&nbsp;a&nbsp;row**&nbsp;🦆🦆

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


[comment]: # (!!!)

### Who are we?

**garu**, **haarg**, **ingy**, **klapperl**, **leont**, **oalders**, **reneeb**, **sam**, **sjn**, **stigo**, **timlegge**, **Tux**, …and others!


Note:

Breno, Graham, Ingy, Andreas, Leon, Olaf, Renée, Sam, Salve, Stig, Tim, Merijn, …and others!


[comment]: # (!!!)

### PTS Picture Proof

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
* …Have **tuits to spare**?
* …Have a **security commons** aware employer?
* …Enjoy getting your **ducks in a row**? 🦆🦆

Note:

* Do you have a **security background** or care about the toolchain?
* Do you have **time to volunteer**?
* Is your employer willing to **dedicate a percentage of your time** to improve our security commons?

We need volunteers!


[comment]: # (!!!)

### Find us!

ircs://irc.perl.org#cpan-security

https://security.metacpan.org/

mailto:cpan-security@perl.org


Note:

We're on the web, IRC, mail and eventually on other places.


[comment]: # (!!!)

# Thanks!

* Salve J. Nilsen

🦆🦆🦆🦆🦆🦆


Note:

Thanks!
