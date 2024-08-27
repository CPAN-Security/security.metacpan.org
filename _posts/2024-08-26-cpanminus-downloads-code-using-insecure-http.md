---
layout: post
published: True
toc: true
title: "App::cpanminus through 1.7047 downloads code using insecure HTTP"
date: 2024-08-26 00:00:00 +0000
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
`--from` option.

> Setting the `--from` option disables support for downloading old
> releases from BackPan and development (TRIAL) releases.

This can be configured as a CLI option:

```sh
$ cpanm --from https://www.cpan.org Mojolicious
```

Or set in the `PERL_CPANM_OPT` environment variable:

```
$ export PERL_CPANM_OPT="--from https://www.cpan.org"
```


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

- [CPAN.pm](https://metacpan.org/dist/CPAN) (`cpan`) will use HTTPS sources if TLS support is available  
- [App::cpm](https://metacpan.org/pod/App::cpm) (`cpm`) uses HTTPS sources by default

## Links

- [NVD - CVE-2024-45321](https://nvd.nist.gov/vuln/detail/CVE-2024-45321)
- [miyagawa/cpanminus#611: Securing Perl: cpanm HTTPS + verify_SSL + verify signatures?](https://github.com/miyagawa/cpanminus/issues/611)
- [miyagawa/cpanminus#674: make cpanm secure by default](https://github.com/miyagawa/cpanminus/pull/674)
- [Perl/docker-perl#167: generate: hotpatch bin/cpanm to use HTTPS endpoints](https://github.com/Perl/docker-perl/pull/167)

## Changes
- 2024-08-27: Add reference to CVE-2024-45321, add excerpt, fix typos
