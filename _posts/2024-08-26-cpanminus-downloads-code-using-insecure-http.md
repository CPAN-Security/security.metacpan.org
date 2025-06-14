---
layout: single
published: True
toc: true
title: "App::cpanminus downloads code using insecure HTTP"
date: 2024-08-26 00:00:00 +0000
category: news
tags: cve
author: Stig Palmquist
excerpt: "CVE-2024-45321: In its default configuration cpanminus uses insecure HTTP to download and install code from CPAN. This results in a CWE-494 weakness, enabling code execution for network attackers."
---

[App::cpanminus](https://metacpan.org/pod/App::cpanminus) (`cpanm`) is a popular
and lighweight alternative to the official CPAN client for downloading and
installing Perl modules from CPAN.

## CVE-2024-45321

In its default configuration cpanminus uses insecure HTTP to download and
install code from CPAN.

The lack of a secure HTTPS default results in a [CWE-494: Download of Code
Without Integrity Check](https://cwe.mitre.org/data/definitions/494.html)
weakness, enabling code execution for network attackers.


## Mitigations

There is currently no patch available upstream yet. Users can mitigate with
one of the following options.

### Option 1: Set a HTTPS mirror

The easiest way is to configure cpanminus to use a HTTPS mirror using the
`--from` command-line argument. This can be configured as a CLI option,
replacing DISTNAME in the command below with the name of the distribution
you want to install:

```sh
$ cpanm --from https://www.cpan.org DISTNAME
```

Alternatively, you can set the `--from` option via the `PERL_CPANM_OPT`
environment variable:

```
$ export PERL_CPANM_OPT="--from https://www.cpan.org"
```
And use cpanm as you normally would.

> Please note that setting a `--from` option will disable support for
> downloading old releases from BackPan and development (TRIAL) releases.

### Option 2: Patch the cpanm executable

Another option is to patch the `http://` endpoints in the executable. This
retains support for BackPan and TRIAL-releases.

> `App::cpanminus` is distributed as a fatpacked executable with
> dependencies minified and inlined, so a `.patch` file is not convenient.

To patch the executable, you can run the following oneliner:

```sh
$ perl -pi -E 's{http://(www\.cpan\.org|backpan\.perl\.org|cpan\.metacpan\.org|fastapi\.metacpan\.org|cpanmetadb\.plackperl\.org)}{https://$1}g' /path/to/cpanm
```

### Option 3:  Use an alternative client

- [CPAN.pm](https://metacpan.org/dist/CPAN) (`cpan`) 2.35 or later will use HTTPS with certificate verification if TLS support is available  
- [App::cpm](https://metacpan.org/pod/App::cpm) (`cpm`) uses HTTPS sources by default

### Note on LWP::UserAgent

It was [reported](https://github.com/Perl/docker-perl/issues/169) to docker-perl
that cpanminus will fail at downloading from https sources if LWP::UserAgent is
installed without LWP::Protocol::https.

If you encounter errors like `LWP will support https URLs if the
LWP::Protocol::https module is installed.`, you can pass `--no-lwp` as a command
line argument, or apply an additional patch to the executable:

```sh
$ perl -pi -E 's{try_lwp=>1}{try_lwp=>0}g' /path/to/cpanm 
```

This will disable LWP::UserAgent support, use `curl`, `wget` or `HTTP::Tiny`
instead.


## Links

- [NVD - CVE-2024-45321](https://nvd.nist.gov/vuln/detail/CVE-2024-45321)
- [miyagawa/cpanminus#611: Securing Perl: cpanm HTTPS + verify_SSL + verify signatures?](https://github.com/miyagawa/cpanminus/issues/611)
- [miyagawa/cpanminus#674: make cpanm secure by default](https://github.com/miyagawa/cpanminus/pull/674)
- [Perl/docker-perl#167: generate: hotpatch bin/cpanm to use HTTPS endpoints](https://github.com/Perl/docker-perl/pull/167)

## Changes
- 2024-08-27: Add reference to CVE-2024-45321, add excerpt, fix typos, add note about CPAN.pm version.
- 2024-08-27: Minor rewording for the `--from` cpanm option explanation.
- 2024-10-02: Add note about LWP::UserAgent and `--no-lwp` workaround
- 2025-06-12: Remove "through 1.7047" from title, since 1.7048 was released without a fix
