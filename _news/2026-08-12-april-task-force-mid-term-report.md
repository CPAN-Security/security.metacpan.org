---
layout: single
title: April Task Force report 1 (Q1)
excerpt: April Task Force has been at work for three months, and here are some achievements of note.
authors:
    - cpansec
    - sjn
    - oalders
toc: true
date: 2026-08-12 22:00:00 +0200
collection: news
tags: cpan security April task force CNA LLM AI
author_profile: true
header:
  overlay_image: /assets/images/header/SJN08081.JPG
  teaser: assets/images/teaser/SJN08081.JPG
  overlay_filter: 0.6
  caption: "Photo credit: [@sjn](https://github.com/sjn)"
---

# April Task Force report 1

In the funding application, we committed to "front-load" our activities to the first three months in the six-month funding period.
This first quarter of the period is now done, and here follows an report of some of our activities, both completed and ongoing.



{% figure caption:"Photo: Stian Kristoffersen; Editing: Salve J. Nilsen; In picture, from left: Paul Johnson, Stig Palmquist, Leon Timmermans, Robert Rothenberg, Salve J. Nilsen, Timothy Legge, and Olaf Alders." %}
![April Task Force group picture](/media/april-task-force-workshop-group-picture.jpg)
{% endfigure %}



# April Task Force - mid-term report

…

## Success stories

- Debian project have been very good at applying/fixing the published CVE
- 158 CVEs published since the beginning of the project (May 11th)
  **HOW MANy FIXES WERE RELEASED?**
- Dedicated time for working on important security issues 


## Identified new issues

- CVE Triage and follow-up is now clearly an issue limited mainly by access to human resources
  - This is especially important as these issues have to be solved in a maintainer- and community first

# Notes - done, ongoing & pending

## Group activites

### done

- Kick-off workshop in Oslo

### ongoing

- Weekly standup-meetings
- Participate in SEIRs weekly meetings
- …

### pending

- Prepare for bulk vulnerability submission


## stigo

### done

- Initial AI-support tooling discovery, verification based on real-world usage and experience
- Initial pipeline for triaging, verifying, and creating CVEs
- Mechanical AI-hallucination mitigations, and info leak mitigations
- Large fuzzing and triage passes on critical modules and perl5.

### ongoing


- Work on general public agent skills to make local models capable at finding vulns
- "Vulnerable Pattern in Perl/CPAN" documentation, eventually for publication
- Work on AI attack mitigations in discovery process
- Support give maintainers access to model-generated structured raw data & UI for vuln tracking, possibly aligned with other non-vendor security communities like rustsec
  - Current methods don't scale, and are too heavily dependent on email.
  - Current method also doesn't give a good context overview and does not help with both clarity, communicating remaining work, and building and maintaining trust
- Statistics gathering tooling (possibly integrated with the above)
- Explore and develop a "Full disclosure" crisis plan
  - "patch proxy" use cases
- Analysis of Community interaction blockers/bottlenecks

### pending

- Other crisis plans
  - NOC evaporation
  - PAUSE supply chain attack
- General supply-chain security crisis planning
  - promped by CPAN.org email situation
- …

## sjn

### done

- kick-off organizing
- budgeting & planning
- …

### ongoing

- Reseach around Steward Cooperative organizational patterns
- Custom CPAN Steward organization template (articles of association, bylaws, business model, etc.)
- Minimal-compliance membership requirements for Maintainers, Admins and Organizers


### pending

- …

## oalders

### done

-  https://www.olafalders.com/2026/07/21/how-to-deprecate-a-cpan-module/
- Fixed bugs preventing MetaCPAN authors from updating their contact information
  - Fixed OAUTH logins
  - Fixed Profile update bug
- Fixed and merged CVE patches in libwww-perl org
- https://github.com/Perl-Toolchain-Gang/HTTP-Tiny/pull/36 "Strip auth headers on cross-origin redirects"
- Working to try resolve @cpan.org mail forwarding issues

## rrwo

### done

- CNA work: Triage of many issues/author contact/CVE publishing
- CNA FAQ (w/sjn)
- Default discosure dates decision
- Guide: Security Reports for CPAN Authors
- Guide: CPAN Author’s Guide to Random Data for Security
- Contributed to fixes/hardening
  - DBI
  - HTTP::Date
  - Mojolicious::Plugin::Statsd (taken over maint)
  - Catalyst::View::Wkhtmltopdf (taken over maint)
  - Crypt::SaltedHash (taken over maint/deprecated)
  - Net::CIDR::Set (taken over maint)
  - Net::Statsd::Lite and Net::Statsd::Tiny (own modules)
  - Plack::App::Prerender (own module)
- Published Crypt::Passphrase::SaltedHash as replacement for Crypt::SaltedHash
- Blog post about common issues with statsd clients

### ongoing

- Blog article w/sgo on use of rand
- Automation policy and dist tools
- Improvements for Perl documentation

### pending

- Security policy prompt injection (w/sgo)
- Tests for outdated email addresses in .mailmap used in distribution
- Perl::Critic tests for presense of rand() in modules
- Extracting Perl::Critic rules from common findings
- Blog articles on common issues that we have found

## leont

### done

- Perl verifier for sigstore

### ongoing

- Perl signer for sigstore
- Supporting team members with C issues (including perl itself)

### pending

- TUF client for Perl sigstore implementation
- TLS implementation suitable for inclusion in core
- Securing :utf8 input layer


## About the CPAN Security Group

The CPAN Security Group (CPANSec) is a group of volunteers from the Perl community who work to support the security of the Perl ecosystem through education and outreach, security analysis of open source Perl distributions on CPAN, and support for fixing security vulnerabilities. CPANSec was founded at the Perl Toolchain Summit 2023 in Lyon, France.


## About the Perl and Raku Foundation

The Perl and Raku Foundation (TPRF) is a volunteer-led 501(c)(3) non-profit dedicated to advancing the Perl and Raku programming languages. The foundation provides financial, legal, and organizational stewardship that keeps both languages freely available and actively developed — funding core maintenance and development grants, producing community conferences, and supporting shared infrastructure and user groups.

## Links

- CPAN Security Group: [https://security.metacpan.org](https://security.metacpan.org)
- The Perl and Raku Foundation: [https://www.perlfoundation.org](https://www.perlfoundation.org)
- Alpha-Omega: [https://alpha-omega.dev](https://alpha-omega.dev)



# Appendix – Published CVEs

- [CVE-2022-4988](https://lists.security.metacpan.org/cve-announce/msg/39948817/): Alien::FreeImage versions through 1.001 for Perl contains several vulnerable libraries
- [CVE-2026-5084](https://lists.security.metacpan.org/cve-announce/msg/39930303/): WebDyne::Session versions through 2.075 for Perl generates the session id insecurely
- [CVE-2026-6146](https://lists.security.metacpan.org/cve-announce/msg/39948955/): Amazon::Credentials versions through 1.2.0 for Perl uses rand to generate encryption keys
- [CVE-2026-7010](https://lists.security.metacpan.org/cve-announce/msg/39952806/): HTTP::Tiny versions before 0.093 for Perl do not validate CRLF in HTTP request lines or control field header values
- [CVE-2026-5089](https://lists.security.metacpan.org/cve-announce/msg/39981051/): YAML::Syck versions before 1.38 for Perl has an out-of-bounds read
- [CVE-2026-8368](https://lists.security.metacpan.org/cve-announce/msg/39974665/): LWP::UserAgent versions before 6.83 for Perl leak Authorization and Proxy-Authorization headers on cross-origin redirects
- [CVE-2026-8463](https://lists.security.metacpan.org/cve-announce/msg/40006926/): Crypt::Argon2 versions from 0.017 before 0.031 for Perl perform a heap out-of-bounds read in argon2_verify on empty encoded input
- [CVE-2026-8500](https://lists.security.metacpan.org/cve-announce/msg/40028987/): Web::Passwd versions through 0.03 for Perl is vulnerable to RCE
- [CVE-2026-46474](https://lists.security.metacpan.org/cve-announce/msg/40093229/): Trog::TOTP versions before 1.006 for Perl generate secrets using rand
- [CVE-2026-8454](https://lists.security.metacpan.org/cve-announce/msg/40079077/): Imager::File::GIF versions through 1.002 for Perl allow a heap out of bounds (OOB) write on crafted multi-frame GIF files
- [CVE-2026-8503](https://lists.security.metacpan.org/cve-announce/msg/40079348/): Apache::Session::Generate::SHA256 versions before 1.3.19 for Perl create insecure session ids
- [CVE-2026-8612](https://lists.security.metacpan.org/cve-announce/msg/40072903/): WWW::Mechanize::Cached versions before 2.00 for Perl deserialize cached HTTP responses from a world-writable on-disk cache, enabling local response forgery and code execution
- [CVE-2026-8669](https://lists.security.metacpan.org/cve-announce/msg/40083214/): Imager versions through 1.030 for Perl allow a heap out of bounds (OOB) write on crafted multi-frame GIF files
- [CVE-2026-8700](https://lists.security.metacpan.org/cve-announce/msg/40104301/): Crypt::DSA versions before 1.20 for Perl generate seeds using rand
- [CVE-2026-8704](https://lists.security.metacpan.org/cve-announce/msg/40104289/): Crypt::DSA versions through 1.19 for Perl use 2-args open, allowing existing files to be modified
- [CVE-2026-46719](https://lists.security.metacpan.org/cve-announce/msg/40120407/): Net::Statsd::Lite versions before 0.9.0 for Perl allowed metric injections
- [CVE-2026-46720](https://lists.security.metacpan.org/cve-announce/msg/40147598/): Net::Statsd::Tiny versions before 0.3.8 for Perl allowed metric injections
- [CVE-2026-8507](https://lists.security.metacpan.org/cve-announce/msg/40149247/): Crypt::OpenSSL::PKCS12 versions through 1.94 for Perl have out of bound (OOB) write flaws
- [CVE-2026-8721](https://lists.security.metacpan.org/cve-announce/msg/40149249/): Crypt::OpenSSL::PKCS12 versions through 1.94 for Perl truncates passwords with embedded NULLs
- [CVE-2026-8788](https://lists.security.metacpan.org/cve-announce/msg/40160561/): Net::Statsd::Lite versions through 0.10.0 for Perl allowed metric injections
- [CVE-2026-5090](https://lists.security.metacpan.org/cve-announce/msg/40218729/): Template::Plugin::HTML versions through 3.102 for Perl allows HTML and JavaScript to be injected
- [CVE-2026-47372](https://lists.security.metacpan.org/cve-announce/msg/40252126/): Crypt::SaltedHash versions through 0.09 for Perl generate insecure random values for salts
- [CVE-2026-47373](https://lists.security.metacpan.org/cve-announce/msg/40249915/): Crypt::SaltedHash versions through 0.09 for Perl is susceptible to timing attacks
- [CVE-2026-46473](https://lists.security.metacpan.org/cve-announce/msg/40278181/): Authen::TOTP versions before 0.1.1 for Perl generate secrets using rand
- [CVE-2026-5091](https://lists.security.metacpan.org/cve-announce/msg/40281889/): Catalyst::Plugin::Authentication versions through 0.10024 for Perl is susceptible to timing attacks
- [CVE-2026-8376](https://lists.security.metacpan.org/cve-announce/msg/40396161/): Perl versions through 5.43.10 have a heap buffer overflow when compiling regular expressions with a repeated fixed string on 32-bit builds
- [CVE-2026-42496](https://lists.security.metacpan.org/cve-announce/msg/40396459/): Archive::Tar versions before 3.08 for Perl extract symlinks with attacker controlled targets outside the extraction directory
- [CVE-2026-42497](https://lists.security.metacpan.org/cve-announce/msg/40396457/): Archive::Tar versions before 3.08 for Perl extract hardlinks to attacker controlled paths outside the extraction directory
- [CVE-2026-46740](https://lists.security.metacpan.org/cve-announce/msg/40427980/): Mojolicious::Plugin::Statsd versions through 0.04 for Perl allowed metric injections
- [CVE-2026-8647](https://lists.security.metacpan.org/cve-announce/msg/40428065/): Crypt::ScryptKDF versions through 0.010 for Perl uses insecure random number source when no CSPRNG module is available
- [CVE-2026-9538](https://lists.security.metacpan.org/cve-announce/msg/40396448/): Archive::Tar versions before 3.10 for Perl allow memory exhaustion via attacker controlled entry size field in tar header
- [CVE-2025-15649](https://lists.security.metacpan.org/cve-announce/msg/40434380/): IO::Uncompress::Unzip versions before 2.215 for Perl propagate uncaught exception when parsing zip header with malformed DOS date
- [CVE-2026-48959](https://lists.security.metacpan.org/cve-announce/msg/40434381/): IO::Uncompress::Unzip versions before 2.220 for Perl allow CPU exhaustion via per-byte read loop in fastForward
- [CVE-2026-48961](https://lists.security.metacpan.org/cve-announce/msg/40434383/): IO::Compress versions from 2.207 before 2.220 for Perl ship a zipdetails CLI tool that crashes with undefined subroutine on Info-ZIP Unix Extra Field with 8-byte UID or GID
- [CVE-2026-48962](https://lists.security.metacpan.org/cve-announce/msg/40434385/): IO::Compress versions before 2.220 for Perl can execute arbitrary code in File::GlobMapper via an attacker-controlled output glob
- [CVE-2026-8450](https://lists.security.metacpan.org/cve-announce/msg/40435207/): HTTP::Daemon versions before 6.17 for Perl allow OS command injection via send_file()
- [CVE-2026-41565](https://lists.security.metacpan.org/cve-announce/msg/40477993/): CryptX versions before 0.088_001 for Perl have a stack buffer overflow in four AEAD decrypt_verify helpers
- [CVE-2026-9658](https://lists.security.metacpan.org/cve-announce/msg/40473423/): Plack::Middleware::Security::Common versions before 0.13.1 for Perl did not block header injections in request paths
- [CVE-2026-8594](https://lists.security.metacpan.org/cve-announce/msg/40542383/): Text::LineFold versions through 2019.001 for Perl duplicate the output based on the number of special break characters
- [CVE-2026-8796](https://lists.security.metacpan.org/cve-announce/msg/40571630/): Sereal::Decoder versions before 5.005 for Perl allow heap out-of-bounds read via crafted input
- [CVE-2026-8722](https://lists.security.metacpan.org/cve-announce/msg/40684837/): Net::Async::Statsd::Client versions through 0.005 for Perl allow metric injections
- [CVE-2026-9334](https://lists.security.metacpan.org/cve-announce/msg/40653179/): Cpanel::JSON::XS versions before 4.41 for Perl allow type confusion via duplicate object keys when dupkeys_as_arrayref is enabled
- [CVE-2026-9516](https://lists.security.metacpan.org/cve-announce/msg/40653165/): Cpanel::JSON::XS versions before 4.41 for Perl allow denial of service via UTF-8 BOM prefixed input when a decode filter callback throws
- [CVE-2026-46739](https://lists.security.metacpan.org/cve-announce/msg/40702251/): Net::Statsd versions before 0.13 for Perl allow metric injections
- [CVE-2026-46741](https://lists.security.metacpan.org/cve-announce/msg/40702581/): Etsy::StatsD versions through 1.002002 for Perl allow metric injections
- [CVE-2026-49940](https://lists.security.metacpan.org/cve-announce/msg/40702749/): Net::CIDR::Set versions through 0.20 for Perl accept non-ASCII IP addresses and netmasks
- [CVE-2026-49941](https://lists.security.metacpan.org/cve-announce/msg/40702781/): Net::CIDR::Set versions through 0.20 for Perl did not validate IP addresses
- [CVE-2026-49942](https://lists.security.metacpan.org/cve-announce/msg/40702816/): Net::CIDR::Set versions through 0.20 for Perl did not validate network masks
- [CVE-2026-8829](https://lists.security.metacpan.org/cve-announce/msg/40702610/): HTML::Entities versions before 3.84 for Perl read freed heap memory in _decode_entities
- [CVE-2026-10879](https://lists.security.metacpan.org/cve-announce/msg/40729086/): DBI versions before 1.648 for Perl have a heap overflow when preparsing SQL statements with more than 9 binders
- [CVE-2026-11362](https://lists.security.metacpan.org/cve-announce/msg/40729465/): DataDog::DogStatsd versions through 0.07 for Perl allow metric injections from event tags
- [CVE-2026-9270](https://lists.security.metacpan.org/cve-announce/msg/40729463/): DataDog::DogStatsd versions through 0.07 for Perl allow metric injections
- [CVE-2026-10725](https://lists.security.metacpan.org/cve-announce/msg/40751319/): Protocol::HTTP2 versions through 1.12 for Perl is vulnerable to a HTTP/2 Bomb
- [CVE-2009-10007](https://lists.security.metacpan.org/cve-announce/msg/40832427/): Catalyst::Plugin::Authentication versions before 0.10_027 for Perl is susceptible to session fixation attacks
- [CVE-2026-9698](https://lists.security.metacpan.org/cve-announce/msg/40831067/): DBI versions before 1.648 for Perl saved errors in a limited-sized buffer
- [CVE-2026-50637](https://lists.security.metacpan.org/cve-announce/msg/40877431/): Metrics::Any::Adapter::Statsd versions before 0.04 for Perl does not protect against metric injections
- [CVE-2026-50638](https://lists.security.metacpan.org/cve-announce/msg/40877425/): Metrics::Any::Adapter::DogStatsd versions before 0.04 for Perl does not protect against metric injections
- [CVE-2026-50639](https://lists.security.metacpan.org/cve-announce/msg/40877417/): Metrics::Any::Adapter::SignalFx versions before 0.04 for Perl does not protect against metric injections
- [CVE-2017-20240](https://lists.security.metacpan.org/cve-announce/msg/40929601/): Crypt::PBKDF2 versions before 0.261630 for Perl are vulnerable to timing attacks
- [CVE-2026-9638](https://lists.security.metacpan.org/cve-announce/msg/40932643/): Crypt::PBKDF2 versions before 0.261630 for Perl generate insecure random values for salts
- [CVE-2026-9641](https://lists.security.metacpan.org/cve-announce/msg/40933040/): Crypt::PBKDF2 versions before 0.261630 for Perl have a weak default algorithm and number of iterations
- [CVE-2026-11526](https://lists.security.metacpan.org/cve-announce/msg/41004664/): GD versions before 2.86 for Perl allow OS command injection and file overwrite via a 2-arg open() of filename arguments in _make_filehandle
- [CVE-2026-11527](https://lists.security.metacpan.org/cve-announce/msg/41004660/): Config::IniFiles versions before 3.001000 for Perl allow OS command injection and file overwrite via a 2-arg open() of the -file argument in _make_filehandle
- [CVE-2026-11832](https://lists.security.metacpan.org/cve-announce/msg/41020603/): Dancer2::Plugin::Auth::OAuth versions before 0.22 for Perl default to a predictable nonce
- [CVE-2026-12087](https://lists.security.metacpan.org/cve-announce/msg/41020451/): Socket versions before 2.041 for Perl have an out-of-bounds heap read
- [CVE-2026-12205](https://lists.security.metacpan.org/cve-announce/msg/41004653/): Crypt::DSA versions before 1.21 for Perl reused the nonce across signatures, leading to private-key recovery
- [CVE-2026-9692](https://lists.security.metacpan.org/cve-announce/msg/41104631/): Mojolicious::Sessions::Storable versions through 0.05 for Perl generate session ids insecurely
- [CVE-2026-9265](https://lists.security.metacpan.org/cve-announce/msg/41138733/): Crypt::OpenSSL::PKCS12 versions before 1.96 for Perl permits a heap OOB read in print_attribute UTF8STRING path
- [CVE-2026-11373](https://lists.security.metacpan.org/cve-announce/msg/41192983/): Net::Statsite::Client versions through 1.1.0 for Perl allow metric injections
- [CVE-2026-9733](https://lists.security.metacpan.org/cve-announce/msg/41220991/): Mojolicious::Plugin::Web::Auth::OAuth2 versions through 0.17 for Perl have an insecure default state parameter
- [CVE-2026-12844](https://lists.security.metacpan.org/cve-announce/msg/41398142/): List::SomeUtils::XS versions before 0.59 for Perl have a heap buffer overflow in the pairwise function
- [CVE-2026-11625](https://lists.security.metacpan.org/cve-announce/msg/41305966/): Bytes::Random::Secure versions through 0.29 for Perl share internal state across forked processes
- [CVE-2026-11702](https://lists.security.metacpan.org/cve-announce/msg/41306002/): Bytes::Random::Secure::Tiny versions through 1.011 for Perl share internal state across forked processes
- [CVE-2026-13593](https://lists.security.metacpan.org/cve-announce/msg/41396070/): CSS::Minifier::XS versions before 0.14 for Perl have a memory leak when the entire document is minified away
- [CVE-2026-13758](https://lists.security.metacpan.org/cve-announce/msg/41398101/): CryptX versions before 0.088_001 for Perl compare AEAD authentication tags in non-constant time in the streaming decrypt_done path
- [CVE-2026-56017](https://lists.security.metacpan.org/cve-announce/msg/41396063/): JavaScript::Minifier::XS versions before 0.16 for Perl crash with a NULL pointer dereference when the first meaningful token of the input is a slash
- [CVE-2026-56018](https://lists.security.metacpan.org/cve-announce/msg/41396069/): JavaScript::Minifier::XS versions before 0.16 for Perl leak memory on every call to minify(), allowing unbounded memory growth
- [CVE-2026-13766](https://lists.security.metacpan.org/cve-announce/msg/41412649/): DBIx::QuickORM versions before 0.000026 for Perl allow SQL injection via unquoted SQL identifiers
- [CVE-2026-57079](https://lists.security.metacpan.org/cve-announce/msg/41412301/): Net::BitTorrent versions through 2.0.1 for Perl write files outside the download directory via path traversal in peer-supplied metadata
- [CVE-2026-57080](https://lists.security.metacpan.org/cve-announce/msg/41412302/): Net::BitTorrent versions through 2.0.1 for Perl allow remote memory exhaustion via an uncapped peer-wire message-length prefix
- [CVE-2026-57081](https://lists.security.metacpan.org/cve-announce/msg/41412306/): Net::BitTorrent versions through 2.0.1 for Perl allow remote memory exhaustion via deeply nested bencoded input
- [CVE-2026-57082](https://lists.security.metacpan.org/cve-announce/msg/41412310/): Net::BitTorrent versions through 2.0.1 for Perl generate the MSE Diffie-Hellman private key with a non-cryptographic PRNG
- [CVE-2025-15646](https://lists.security.metacpan.org/cve-announce/msg/41446255/): HTML::Gumbo versions before 0.19 for Perl disclose heap memory via type confusion
- [CVE-2026-56016](https://lists.security.metacpan.org/cve-announce/msg/41439279/): CGI::Session::ID::md5 versions before 4.49 for Perl generate predictable session ids from low-entropy sources
- [CVE-2026-56015](https://lists.security.metacpan.org/cve-announce/msg/41502163/): Net::IP::LPM versions through 1.10 for Perl allow a heap out-of-bounds read via an unbounded prefix length
- [CVE-2026-12740](https://lists.security.metacpan.org/cve-announce/msg/41533128/): Plack::Middleware::OAuth versions through 0.10 for Perl do not support the OAuth 2.0 state parameter
- [CVE-2026-12746](https://lists.security.metacpan.org/cve-announce/msg/41532951/): Dancer2::Plugin::Auth::OAuth::Provider versions before 0.23 for Perl do not support the OAuth 2.0 state parameter
- [CVE-2026-14570](https://lists.security.metacpan.org/cve-announce/msg/41542402/): Crypt::DSA versions before 1.22 for Perl draw the DSA signing nonce and private key from a biased random generator, leading to private-key recovery
- [CVE-2026-13705](https://lists.security.metacpan.org/cve-announce/msg/41572386/): Imager versions before 1.032 for Perl have a heap out-of-bounds read in the bundled Imager::File::SGI reader via a 16-bit RLE literal run in read_rgb_16_rle
- [CVE-2026-13708](https://lists.security.metacpan.org/cve-announce/msg/41572486/): Imager::File::JPEG versions before 1.003 for Perl leak heap memory when reading a JPEG with repeated APP13 markers in i_readjpeg_wiol
- [CVE-2026-14803](https://lists.security.metacpan.org/cve-announce/msg/41564627/): Mojo::JSON versions before 9.47 for Perl allow memory exhaustion via unbounded recursion in the pure-Perl decoder
- [CVE-2011-10043](https://lists.security.metacpan.org/cve-announce/msg/41608305/): Module::Load versions before 0.22 for Perl allow arbitrary modules outside of @INC to be loaded
- [CVE-2026-14380](https://lists.security.metacpan.org/cve-announce/msg/41625527/): DBI versions before 1.650 for Perl are vulnerable to code injection via caller-influenced Profile
- [CVE-2026-14740](https://lists.security.metacpan.org/cve-announce/msg/41625532/): DBI versions before 1.650 for Perl read one byte out-of-bounds in preparse when deleting an initial SQL comment
- [CVE-2026-14895](https://lists.security.metacpan.org/cve-announce/msg/41625636/): String::Util versions before 1.36 for Perl are susceptible to a regular expression denial of service
- [CVE-2026-7017](https://lists.security.metacpan.org/cve-announce/msg/41618211/): HTTP::Tiny versions before 0.095 for Perl forward credential headers to cross-origin redirect targets
- [CVE-2026-14454](https://lists.security.metacpan.org/cve-announce/msg/41637674/): Imager versions before 1.033 for Perl treat unsigned EXIF IFD entry counts as signed
- [CVE-2026-13221](https://lists.security.metacpan.org/cve-announce/msg/41780104/): Perl versions through 5.43.9 produce silently incorrect regular expression matches when an alternation of more than 65535 fixed string branches is compiled into a trie in Perl_study_chunk
- [CVE-2026-57432](https://lists.security.metacpan.org/cve-announce/msg/41780102/): Perl versions through 5.43.10 have an integer overflow in S_measure_struct leading to an out-of-bounds heap read in pack and unpack
- [CVE-2026-57433](https://lists.security.metacpan.org/cve-announce/msg/41780100/): Storable versions before 3.41 for Perl have a signed integer overflow when deserializing a crafted SX_HOOK record
- [CVE-2026-58101](https://lists.security.metacpan.org/cve-announce/msg/41792358/): Crypt::OpenSSL::X509 versions before 2.1.3 for Perl allow denial of service via NULL pointer dereference
- [CVE-2026-58102](https://lists.security.metacpan.org/cve-announce/msg/41792355/): Crypt::OpenSSL::X509 versions before 2.1.3 for Perl allow a heap out-of-bounds read via a long certificate extension OID in hv_exts
- [CVE-2026-14739](https://lists.security.metacpan.org/cve-announce/msg/41625530/): DBI versions before 1.650 for Perl have a heap overflow when preparsing SQL statements with an extreme number of placeholders
- [CVE-2026-15043](https://lists.security.metacpan.org/cve-announce/msg/41805128/): DBI::SQL::Nano versions from 1.42 before 1.651 for Perl have inverted &lt;= and &gt;= SQL operators on text
- [CVE-2026-15392](https://lists.security.metacpan.org/cve-announce/msg/41813967/): DBD::File versions before 1.651 for Perl do not ensure the table file is not a symlink to an untrusted location
- [CVE-2026-15747](https://lists.security.metacpan.org/cve-announce/msg/41816171/): Mojolicious versions from 4.59 before 9.48 for Perl expose a stable representation of the session CSRF token to a BREACH compression oracle
- [CVE-2026-60081](https://lists.security.metacpan.org/cve-announce/msg/41813962/): DBI::ProfileData versions before 1.651 for Perl do not limit the path index
- [CVE-2026-60082](https://lists.security.metacpan.org/cve-announce/msg/41813803/): DBI versions before 1.651 for Perl do not enforce statement handle consistency with the row
- [CVE-2026-13397](https://lists.security.metacpan.org/cve-announce/msg/41876834/): HTML::Bare versions through 0.04 for Perl will hang in an infinite loop when parsing malformed attributes
- [CVE-2026-13401](https://lists.security.metacpan.org/cve-announce/msg/41876829/): XML::Bare versions through 0.53 for Perl will hang in an infinite loop when parsing malformed attributes
- [CVE-2026-13713](https://lists.security.metacpan.org/cve-announce/msg/41898719/): YAML::Syck versions before 1.47 for Perl allow a use-after-free and double-free via an anchor node freed while still on the parser value stack
- [CVE-2026-3031](https://lists.security.metacpan.org/cve-announce/msg/41877012/): Image::EPEG versions through 0.15 for Perl embeds an unsupported version of the Epeg library
- [CVE-2026-57073](https://lists.security.metacpan.org/cve-announce/msg/41876832/): HTML::Bare versions through 0.04 for Perl have an unbounded character lookahead
- [CVE-2026-57074](https://lists.security.metacpan.org/cve-announce/msg/41876806/): XML::Bare versions through 0.53 for Perl have an unbounded character lookahead
- [CVE-2026-57075](https://lists.security.metacpan.org/cve-announce/msg/41898720/): YAML::Syck versions before 1.47 for Perl allow an out-of-bounds read via a signed-char lookup-table index in syck_base64dec
- [CVE-2026-57076](https://lists.security.metacpan.org/cve-announce/msg/41898718/): YAML::Syck versions before 1.47 for Perl allow a heap use-after-free via an anchor name reused as an anchors-table key in syck_hdlr_add_anchor
- [CVE-2026-57077](https://lists.security.metacpan.org/cve-announce/msg/41898716/): YAML::Syck versions before 1.47 for Perl allow an out-of-bounds read via an unbounded newline scan in newline_len
- [CVE-2026-13082](https://lists.security.metacpan.org/cve-announce/msg/41903267/): GD::SecurityImage versions through 1.75 for Perl use rand to generate secrets
- [CVE-2026-13410](https://lists.security.metacpan.org/cve-announce/msg/41903084/): Dancer::Plugin::Auth::Google versions through 0.07 for Perl have TLS verification disabled
- [CVE-2026-14741](https://lists.security.metacpan.org/cve-announce/msg/41907585/): HTTP::Date versions before 6.08 for Perl allow CPU exhaustion via polynomial regex backtracking in parse_date
- [CVE-2026-9537](https://lists.security.metacpan.org/cve-announce/msg/41907805/): Mojo::JWT versions before 1.02 for Perl verify HMAC signatures with a non-constant-time string comparison
- [CVE-2026-13577](https://lists.security.metacpan.org/cve-announce/msg/41975698/): Dancer2 versions through 2.1.0 for Perl generate insecure session ids when CSPRNG modules are unavailable
- [CVE-2026-16235](https://lists.security.metacpan.org/cve-announce/msg/41975671/): Crypt::Password versions through 0.28 for Perl generate insecure random values for salts
- [CVE-2026-64193](https://lists.security.metacpan.org/cve-announce/msg/41989543/): Net::DNS versions through 1.55 for Perl allow remote execution injection via EDNS EXTENDED ERROR
- [CVE-2026-64194](https://lists.security.metacpan.org/cve-announce/msg/41989541/): Net::DNS versions through 1.55 for Perl allow Denial of Service via deep DNS compression pointer chains
- [CVE-2026-6656](https://lists.security.metacpan.org/cve-announce/msg/41975673/): Crypt::Password versions through 0.28 for Perl are susceptible to timing attacks
- [CVE-2026-59139](https://lists.security.metacpan.org/cve-announce/msg/42021850/): Data::ReqRep::Shared versions before 0.05 for Perl allow an out-of-bounds read via an unvalidated arena offset and length in reqrep_recv_locked
- [CVE-2026-59140](https://lists.security.metacpan.org/cve-announce/msg/42021863/): Data::SortedSet::Shared versions before 0.03 for Perl allow an out-of-bounds read via unvalidated node indices in the rank and min/max query paths
- [CVE-2026-59141](https://lists.security.metacpan.org/cve-announce/msg/42021851/): Data::RadixTree::Shared versions before 0.02 for Perl allow an out-of-bounds read via unvalidated node and arena indices in rdx_find_locked
- [CVE-2026-59142](https://lists.security.metacpan.org/cve-announce/msg/42021871/): Data::HashMap::Shared versions before 0.14 for Perl allow an out-of-bounds read via an unvalidated arena offset and length in shm_str_copy
- [CVE-2026-59143](https://lists.security.metacpan.org/cve-announce/msg/42021873/): Data::RoaringBitmap::Shared versions before 0.02 for Perl allow an out-of-bounds read via an unvalidated container offset and cardinality in rb_contains_locked
- [CVE-2026-59144](https://lists.security.metacpan.org/cve-announce/msg/42021859/): Data::RingBuffer::Shared versions before 0.04 for Perl allow a stack buffer overflow via an unvalidated elem_size in ring_read_seq
- [CVE-2026-59145](https://lists.security.metacpan.org/cve-announce/msg/42021860/): Data::Intern::Shared versions before 0.02 for Perl allow an out-of-bounds read via unvalidated slot, reverse and arena indices in si_idx_find
- [CVE-2026-59146](https://lists.security.metacpan.org/cve-announce/msg/42021865/): Data::SpatialHash::Shared versions before 0.02 for Perl allow out-of-bounds reads and writes via unvalidated bucket, link and free-list indices in sph_walk_cell and sph_alloc_slot
- [CVE-2026-59147](https://lists.security.metacpan.org/cve-announce/msg/42021870/): Data::DisjointSet::Shared versions before 0.02 for Perl allow out-of-bounds reads and writes via an unvalidated parent index in dsu_find
- [CVE-2026-64613](https://lists.security.metacpan.org/cve-announce/msg/42021879/): Data::Buffer::Shared versions before 0.05 for Perl create a world-readable mmap backing file and open it without O_NOFOLLOW
- [CVE-2026-64614](https://lists.security.metacpan.org/cve-announce/msg/42021881/): Data::Deque::Shared versions before 0.06 for Perl create a world-readable mmap backing file and open it without O_EXCL or O_NOFOLLOW
- [CVE-2026-64615](https://lists.security.metacpan.org/cve-announce/msg/42021883/): Data::Graph::Shared versions before 0.04 for Perl create a world-readable mmap backing file and open it without O_EXCL or O_NOFOLLOW
- [CVE-2026-64616](https://lists.security.metacpan.org/cve-announce/msg/42021887/): Data::NDArray::Shared versions before 0.02 for Perl create a world-readable mmap backing file and open it without O_EXCL or O_NOFOLLOW
- [CVE-2026-64617](https://lists.security.metacpan.org/cve-announce/msg/42021889/): Data::PubSub::Shared versions before 0.07 for Perl create a world-readable mmap backing file and open it without O_EXCL or O_NOFOLLOW
- [CVE-2026-65061](https://lists.security.metacpan.org/cve-announce/msg/42021891/): Data::ReqRep::Shared versions before 0.05 for Perl create a world-readable mmap backing file and open it without O_EXCL or O_NOFOLLOW
- [CVE-2026-65062](https://lists.security.metacpan.org/cve-announce/msg/42021893/): Data::SortedSet::Shared versions before 0.03 for Perl create a world-readable mmap backing file and open it without O_EXCL or O_NOFOLLOW
- [CVE-2026-65063](https://lists.security.metacpan.org/cve-announce/msg/42021895/): Data::RadixTree::Shared versions before 0.02 for Perl create a world-readable mmap backing file and open it without O_EXCL or O_NOFOLLOW
- [CVE-2026-65064](https://lists.security.metacpan.org/cve-announce/msg/42021897/): Data::HashMap::Shared versions before 0.14 for Perl create a world-readable mmap backing file and open it without O_EXCL or O_NOFOLLOW
- [CVE-2026-65065](https://lists.security.metacpan.org/cve-announce/msg/42021898/): Data::RoaringBitmap::Shared versions before 0.02 for Perl create a world-readable mmap backing file and open it without O_EXCL or O_NOFOLLOW
- [CVE-2026-65066](https://lists.security.metacpan.org/cve-announce/msg/42021901/): Data::RingBuffer::Shared versions before 0.04 for Perl create a world-readable mmap backing file and open it without O_EXCL or O_NOFOLLOW
- [CVE-2026-65067](https://lists.security.metacpan.org/cve-announce/msg/42021903/): Data::Intern::Shared versions before 0.02 for Perl create a world-readable mmap backing file and open it without O_EXCL or O_NOFOLLOW
- [CVE-2026-65068](https://lists.security.metacpan.org/cve-announce/msg/42021902/): Data::SpatialHash::Shared versions before 0.02 for Perl create a world-readable mmap backing file and open it without O_EXCL or O_NOFOLLOW
- [CVE-2026-65069](https://lists.security.metacpan.org/cve-announce/msg/42021905/): Data::DisjointSet::Shared versions before 0.02 for Perl create a world-readable mmap backing file and open it without O_EXCL or O_NOFOLLOW
- [CVE-2026-13089](https://lists.security.metacpan.org/cve-announce/msg/42052459/): OIDC::Lite versions through 0.12.1 for Perl allow ID Token signature verification bypass via a token-controlled algorithm allowlist in verify
- [CVE-2026-16634](https://lists.security.metacpan.org/cve-announce/msg/42095832/): TOML::XS versions before 0.06 for Perl bundle an unsupported and vulnerable version of tomlc99
- [CVE-2026-58586](https://lists.security.metacpan.org/cve-announce/msg/42102486/): Image::WebP versions through 0.2 for Perl bundle a vulnerable version of libwebp
- [CVE-2026-16766](https://lists.security.metacpan.org/cve-announce/msg/42125074/): Catalyst::View::Wkhtmltopdf versions before 0.6.1 for Perl allow shell command injection (RCE) via PDF render options
- [CVE-2026-17552](https://lists.security.metacpan.org/cve-announce/msg/42180319/): Plack::App::Prerender versions before 0.3.0 for Perl can proxy to an arbitrary host via unvalidated REQUEST_URI concatenation in call




*[CNA]:       CNA – CVE Numbering Authority – an organization authorized to reserve and assign CVE numbers to vulnerabilities found within the organization's scope.
*[CPAN]:      CPAN – the Comprehensive Perl Archive Network – the primary Open Source package ecosystem for publishing library components (modules) for the Perl programming language. It's the first of its kind, in continuous operation since 1995!
*[CPANSec]:   CPANSec – the CPAN Security Group – a group of security-conscious volunteers, working on improving the Perl and CPAN ecosystems security posture.
*[CVE]:       CVE – Common Vulnerabilities and Exposures – a numeric identifier for publicly disclosed cybersecurity vulnerabilities. The CVE catalogue is managed by the MITRE corporation for the benefit of the global cybersecurity community, and with help from many CNA organizations.
*[Fediverse]: Fediverse – The Federated Universe – a collection of independently run social networking services that can communicate with each other for sharing status updates, multimedia files and other data.
*[HTML]:      HTML – Hyper Text Markup Language
*[IRC]:       IRC – Internet Relay Chat – one of the earliest distributed chat systems. Still in active use in many Open Source communities, including the ones related to CPAN and Perl!
*[OpenSSF]:   OpenSSF – Open Source Security Foundation – the Linux Foundation's effort to sustainably secure the development, maintenance, release, and consumption of Open Source Software. See openssf.org for more info.
*[OSS]:       OSS – Open Source Software – software published with a license that allows freedom to use, learn, improve and share it's source code.
*[PAUSE]:     PAUSE – the Perl AUthors Upload SErver – the publishing back-end for Perl package authors who wish to publish on CPAN.
*[PyPI]:      PyPI – Python Package Index
*[RSS]:       RSS – RDF Site Summary – a simple syndication standard for allowing users to subscribe to website updates.
*[SBOM]:      SBOM – Software Bill of Materials – a common machine-readable set of standards for storing and communicating metadata
*[SEIR]:      SEIR – Open Source Security Engineers in Residence – an Alpha-Omega and Linux Foundation program to create a global, community-driven network of security engineers dedicated to strengthening the open-source ecosystem.
*[TPRF]:      TPRF – The Perl and Raku Foundation – a volunteer-led non-profit foundation dedicated to advancing the Perl and Raku programming languages. See perlfoundation.org for more info.
*[Upriver]:   Upriver - a module on CPAN that has dependencies published on CPAN. The more dependencies, the further upriver it is considered.
*[VCS]:       VCS – Version Control System
*[XS]:        XS – the Perl XS (External Subs) language – the default Foreign Function Interface (FFI) for making available C-level library functions for use in Perl code. See the perldoc.perl.org/perlxs for more info.
