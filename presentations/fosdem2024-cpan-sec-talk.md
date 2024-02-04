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

## About me

<<<<<<< HEAD:presentations/fosdem2024-cpan-sec-presentation.md
* Salve J. Nilsen, from Oslo, Norway
* Developer, 25+ years with the Perl and CPAN ecosystems & communities
* Currently volunteering for the **CPAN Security Working Group**
* Offering a **Supply Chain** perspective
=======
* Est. at **Perl Toolchain Summit** 2023 in Lyon 🇫🇷
* Work & care for **Security on CPAN**!
>>>>>>> main:presentations/fosdem2024-cpan-sec-talk.md

Note:


[comment]: # (|||)

### Why ask the question?

- Get an end-to-end overview of provenance
- Reduce false positives in downstream security tooling
- Ensure actionable information is available

[comment]: # (|||)

### PTS 2023

![Group picture showing PTS 2023 pariticipants](media/pts-group-picture-PTS2023.jpeg)

Note:

<<<<<<< HEAD:presentations/fosdem2024-cpan-sec-presentation.md
=======
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

* #TODO – TLS support in all CPAN clients (cpanpm, cpanm, etc)
* #TODO – Implementing "The Update Framework" in CPAN
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
>>>>>>> main:presentations/fosdem2024-cpan-sec-talk.md


[comment]: # (|||)

### Privacy and Compliance

<<<<<<< HEAD:presentations/fosdem2024-cpan-sec-presentation.md

Note:


[comment]: # (|||)

### Vulnerability Index

Note:


[comment]: # (|||)

### Provenance & Supply Chain Security


Note:

[comment]: # (|||)

### Metadata & Software Bills of Materials


Note:


[comment]: # (|||)

### Transparency Logs


Note:


[comment]: # (|||)

### Security Patch Tooling


Note:



[comment]: # (|||)

### Security Outreach & Information



Note:



[comment]: # (|||)

### Software Composition Analysis


Note:


[comment]: # (|||)

### Governance, Policy & Funding


Note:


[comment]: # (|||)



Note:

[comment]: # (!!!)

## New security demands


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

Note:



[comment]: # (!!!)

### Find us!

<<<<<<< HEAD:presentations/fosdem2024-cpan-sec-presentation.md
=======
ircs://ssl.irc.perl.org:7062/#cpan-security

https://security.metacpan.org/

mailto:cpan-security@perl.org

>>>>>>> main:presentations/fosdem2024-cpan-sec-talk.md

Note:



[comment]: # (!!!)

# Questions & Comments

[comment]: # (!!!)

# Thanks!

* Salve J. Nilsen
* Mastodon: @sjn@chaos.social

🦆🦆


Note:

Thanks!
