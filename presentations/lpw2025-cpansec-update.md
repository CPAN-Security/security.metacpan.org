[comment]: # (Compile this presentation with the command below)
[comment]: # (mdslides lpw2025-cpansec-update.md --include ../media)
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

# An update on CPANSec

José Joaquín Atria

@jjatria@mastodon.cloud

Note:

Hei! I'm <NAME> and I'm here to introduce the CPAN Security Working Group to you

[comment]: # (!!!)

## What?

* Est. at **Perl Toolchain Summit** 2023 in Lyon 🇫🇷
* We work on & care for **Security on CPAN**
* We are [the CVE Numbering Authority for Perl and CPAN][cna]

We've published [46 CVEs](https://lists.security.metacpan.org/cve-announce/)

[cna]: https://security.metacpan.org/2025/02/25/cpansec-is-cna-for-perl-and-cpan.html

Note:

Established in April 2023 year at the Perl Toolchain Summit in Lyon, France

[comment]: # (!!!)

## In-Scope Security Topics

Note:

Here are some of the things we care about!

[comment]: # (|||)

### Security Outreach & Information

👉 Facilitating **responsible/coordinated disclosure** between authors, reporters and users.

Note:

Keep different information channels (websites, social media) up-to-date and relevant with info on incidents, best practices and other documentation.

VINCE – Vulnerability Information and Coordination Environment

Topics not under embargo are discussed on IRC

[comment]: # (|||)

### Vulnerability Index

👉 **Audit** and track vulnerabilities

Note:

Improve security awareness by standardizing and publishing CPAN package vulnerabilities in relevant indices (our own, or CVE, or other).

[comment]: # (|||)

### Provenance & Supply Chain Security

👉 Establish secure CPAN downloads

* Secure-by-default CPAN clients
* [The Update Framework][tuf] on CPAN

[tuf]: https://theupdateframework.io/

Note:

* TLS support in all CPAN clients
    * CPAN.pm, cpanm, etc.

* Implement [The Update Framework][tuf] in CPAN
    * Repository signatures ("is this from CPAN?")
    * Author signatures ("is this from AUTHOR?")

[tuf]: https://theupdateframework.io/

We want to make TLS in cpan clients on by default, with cert verification on

Looking at getting The Update Framework (pypi has some implementation of this) as a supported, this is in addition to TLS

The TUF spec supports repo and author signing

TUF mitigates attacks that the current PGP signed CHECKSUMS implementation is vulnerable to, like replay attacks and downgrade attacks,

[comment]: # (|||)

### Metadata & Software Bills of Materials

👉 **SBOM** creation and verification

* For compliance with the [Cyber Resilience Act][cra]

[cra]: https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=OJ:L_202402847

Note:

* CPAN PackageURL in spec 🚧
* PackageURL-enabled CPAN tooling
* SBOM-enabled CPAN tooling

Support risk analysis and management by writing tooling for managing standard SBOM objects like OWASP CycloneDX or SPDX, and do this by using existing and new CPAN metadata.

Improve interoperability with non-CPAN package indices

[comment]: # (|||)

### Transparency Logs

👉 Tooling for **third-party monitoring** of&nbsp;package&nbsp;changes

Note:

* Sigstore for CPAN

Write tooling for monitoring package updates and integrity checking of metadata using tools like `sigstore` or `sigsum`, or take inspiration from `transparency.dev`.

[comment]: # (|||)

### Security Patch Tooling

👉 Apply high-priority security patches on CPAN

Note:

Enable high-priority updates of CPAN packages, by developing tooling for publishing and applying third-party security patches to CPAN distributions with non-responsive authors.

[comment]: # (|||)

### Privacy and Compliance

👉 Inform on relevant regulations and compliance

* We maintain a growing [reading list]

[reading list]: https://security.metacpan.org/docs/readinglist.html

Note:

Still lots to do!

[comment]: # (|||)

### Software Composition Analysis

👉 Promote and create tooling for detecting known vulnerabilities

Note:

* Analyze dependencies for known vulnerabilities

[comment]: # (|||)

### Governance, Policy & Funding

👉 Rules and funding channels for sustainable security work

Note:

* Pre-Release Disclosure Agreement
* Charter 🚧
* CPAN Supply chain overview 🚧

* Establish constructive rules, playbooks, governance, policy, and funding channels for security work that is needed.

[comment]: # (|||)

### And more!

👉The security landscape is evolving, so must CPAN!

* Perl and CPAN is in use **everywhere**
* New security demands from market authorities and others

Note:

And more!

Let's have an organization in place that can help improve our security landscape as we discover new vulnerabilities and issues!
Sometimes, response time is of the essence, and that means someone has to be there to respond.

Interoperability – Perl and CPAN is part of a larger Open Source landscape!

[comment]: # (|||)

### Join us!

Do you…

* …work with & **care about security**?
* …have **spare tuits**?
* …have a **security commons** aware employer?
* …enjoy getting your **ducks in a row**? 🦆🦆🦆

Note:

* Do you have a **security background** or care about the Toolchain?
* Do you have **time to volunteer**?
* Is your employer willing to **dedicate a percentage of your time** to improve our security commons?

We need volunteers!

[comment]: # (!!!)

### Find us!

https://security.metacpan.org/

[https://matrix.to/#/#cpansec-discussion:matrix.org](https://matrix.to/#/#cpansec-discussion:matrix.org)

[https://fosstodon.org/@cpansec](https://fosstodon.org/@cpansec)

[ircs://ssl.irc.perl.org:7062/#cpan-security](ircs://ssl.irc.perl.org:7062/#cpan-security)


mailto:cpan-security@security.metacpan.org

Note:

We're on the web, Matrix, Mastodon, IRC, mail and eventually on other places.

[comment]: # (!!!)

# Thanks!

Come talk to me!

(I've got stickers)

🦆🦆🦆🦆

Note:

Thanks!
