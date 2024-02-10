---
layout: page
title: Report Security Issue
toc: true
---

## I've found a vulnerability in Perl

The Perl project takes security issues seriously. Please refer to the [Perl
security report handling policy](https://perldoc.perl.org/perlsecpolicy) for a
detailed description on how to report issues to the Perl security team. 

The CPAN Security WG does not handle security issues in Perl, with the exception
of dual-life core modules. We will coordinate with the Perl security team if
necessary.


## I've found malware on CPAN

Please contact our security team on
[cpan-security@perl.org](mailto:cpan-security@perl.org) privately, with the
following information:

- Distribution name, version, and download URL
- Description of malicious behavior
- Relevant logs, packet capture, code lines, screenshots or other context

Examples of malware reports include: typo squatting, dependency confusion,
exfiltration of private data, code obfuscation, outbound connections to
malicious command and control servers, etc.


## I've found a vulnerability in a distribution on CPAN

If you believe you have found a security vulnerability in a distribution on
CPAN, please follow the [Coordinated vulnerability
disclosure](https://en.wikipedia.org/wiki/Coordinated_vulnerability_disclosure)
model.

It's important that you **do not** post information about it on:
- bug trackers, like RT or GitHub
- social media or chat channels, like IRC or Mastodon
- mailing lists or discussion forums


### Step 1: Prepare a Report

Please provide a detailed description of the steps required to reproduce the
vulnerability.

The following information is useful:
- Distribution name, version and download URL (required)
- Proof of concept code, or a description on how to reproduce
- Logs, code lines, screenshots and other context if relevant

Also consider proposing a date for public disclosure, this is usually 30 days or
longer.


### Step 2: Contact the Author

Send the vulnerability report to the distribution author by email or other
private channels. You can CC our team on
[cpan-security@perl.org](mailto:cpan-security@perl.org) on the report if you
would like us to help in triaging the issue, register CVE identifiers, or for
any other reason.

The authors email address is usually available in the documentation, or on their
page on [metacpan.org](https://metacpan.org).

When authors receive a vulnerability reports, they will usually need some time
to:

- Confirm the problem and assess severity
- Check the code to find any potential similar problems
- Prepare fixes and coordinate a release

Please allow for some time for authors and potential downstream distributions to
coordinate fixes before going public. It is not unusual for
authors to request extentions to any proposed disclosure date.


#### If the Author is unresponsive

> If the author is unresponsive, or you are concerned that the issue is not being
> handled, or for other reasons, then please send the report to
> [cpan-security@perl.org](mailto:cpan-security@perl.org) so we can coordinate
> with authors and relevant community members directly.
>
> If you wish that we keep your identity private, please state this in the first line of the
> email to us. You do not need to provide any rationale.


### Step 3: Disclosure

When disclosure has been agreed by the parties, or if details of the
vulnerability has otherwise been made public, the CPAN Security WG will take
following actions:

1. Add a public record to CPAN vulnerability databases
2. Register a CVE number, if relevant

