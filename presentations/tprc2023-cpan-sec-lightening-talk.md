[comment]: # (Compile this presentation with the command below)
[comment]: # (mdslides tprc2023-cpan-sec-lightening-talk.md --include media)
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


# CPAN Security WG

This is an introduction!

Note:

Yay! We care about security on CPAN! :-D


[comment]: # (!!!)

## CPAN-SEC

* We care about **security on CPAN**!
* Made @ **Perl Toolchain Summit** 2023 in Lyon, France

Note:

Established in April at the PTS 2023 in Lyon, France

I'm here to give you an introduction and a **call for participation**!


[comment]: # (!!!)

## What do we care about?

Note:

Here are some of the things we care about!


[comment]: # (|||)

### CPAN Vulnerability Index

**Auditing** and tracking vulnerabilities

Note:

Standardization and publishing of CPAN package vulnerabilities in relevant indexes (our own, or CVE or whatever). Also consider registering as a CNA (CVE Numbering Authority) 


[comment]: # (|||)

### CPAN Provenance & Supply Chain Security

Establishing a **trusted publishing infrastructure**

Note:

Establishing a trusted publishing infrastructure, including tooling and integration with in-toto.io and SLSA. 


[comment]: # (|||)

### CPAN Software Bills of Materials

**SBOM** creation and verification

Note:

Tooling for creating and managing standard SBOM objects like OWASP CycloneDX and SPDX, using existing CPAN metadata, with the purpose of supporting risk analysis and management


[comment]: # (|||)

### CPAN Transparency Logs

Tooling for **third-party monitoring of updates** to ecosystem packages

Note:

Tooling for monitoring updates, but also integrity checking of metadata using tools like sigstore


[comment]: # (|||)

### CPAN Security Patch Tooling

Tooling for CPAN Distro security patches to enable **high-priority updates**.

Note:

Develop tooling for publishing and applying third-party security patches to CPAN distributions that have non-responsive authors, to enable high-priority updates to CPAN packages.


[comment]: # (|||)

### CPAN Security Outreach & Information

Security and **incident communication** through relevant&nbsp;media&nbsp;channels

Note:

Keeping the different security information channels and documentaion up-to-date and relevant info on incidents, best practices and usage documentation. Websites, social media and more.


[comment]: # (|||)

### And more!

* Software Composition Analysis
* CPAN-SEC Governance, Policy & Funding
* Rich Metadata & Dependencies
* Metadata Privacy and Compliance

Note:

* Tooling for analyzing deps for known vulnerabilities
* Working group rules, project management, funding
* Improve integration with non-CPAN package indices like RPM, apt etc.
* Tracking legal and privacy issues around CPAN metadata, and compliance with GDPR, NIS2, and other regulations


[comment]: # (!!!)

## Why now?

* Upcoming regulations in EU ([NIS2](https://digital-strategy.ec.europa.eu/en/policies/nis2-directive), [CRA](https://digital-strategy.ec.europa.eu/en/library/cyber-resilience-act)) and the US ([Executive Order 14028](https://www.whitehouse.gov/briefing-room/presidential-actions/2021/05/12/executive-order-on-improving-the-nations-cybersecurity/)) make demands to software supply chain security
* CPAN is used by _many_ so we need to get our ducks in&nbsp;a&nbsp;row

Note:

* NIS2
    * Directive (EU) 2022/2555 (NIS2)
    * Must be implemented by 17 October 2024
    * Software used by EU institutions that manage critical infrastructure
* CRA
    * Cyber Resilience Act
    * Must be implemented by July 2025 (estimated)
    * CE certification of software used in and with internet-connected devices in the EU market
* EO-14028
    * Executive Order on Improving the Nation’s Cybersecurity
    * Issued May 12, 2021
    * Applies to all federal agencies and businesses or contractors that work with or sell to the Federal Government


[comment]: # (!!!)

### Who are we?

**garu**, **haarg**, **ingy**, **klapperl**, **leont**, **oalders**, **reneeb**, **sam**, **sjn**, **stigo**, **timlegge**, **Tux**, …and others!


Note:

Breno, Graham, Ingy, Andreas, Leon, Olaf, Renée, Sam, Salve, Stig, Tim, Merijn, …and others!


[comment]: # (!!!)

### PTS Picture proof

![Group picture showing stigo, ingy, sjn, leont, tux and garu](media/cpan-sec-group-photo-lyon-2023.jpeg)

Note:
* **stigo** (Stig)
* **ingy** (Ingy)
* **sjn** (Salve)
* **leont** (Leon)
* **Tux** (Merijn)
* **garu** (Breno)



[comment]: # (!!!)

### Join us!

Do you…

* …Work with & **care about security**?
* …Have **tuits to spare**?
* …Have a **responsible** employer?

Note:

Do you have time to volunteer?

Check with your employer, and ask if they are willing to dedicate a percentage of your time on supply-chain security!


[comment]: # (!!!)

### Where to find us

ircs://irc.perl.org#cpan-security

https://security.metacpan.org/

mailto:cpan-security@perl.org

Note:

Ingy or Olaf is at this conference too!

WIP: Presence in other channels, including the Fediverse! (Not Twitter, though)


[comment]: # (!!!)

# Thanks!

* Olaf Alders
* Salve J. Nilsen (slides)

Note:

Thanks!
