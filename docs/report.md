---
layout: page
title: Report Security Issue
toc: true
---

> Update: The CPANSec vulnerability contact email address has changed to [cpan-security@security.metacpan.org](mailto:cpan-security@security.metacpan.org)

## I've found a vulnerability in Perl

The Perl project takes security issues seriously.
Please refer to the [Perl security report handling policy](https://perldoc.perl.org/perlsecpolicy) for a detailed description on how to report issues to the Perl security team

The CPAN Security Group does not handle security issues in Perl, with the exception of dual-life core modules.
We will coordinate with the Perl security team if necessary.


## I've found malware on CPAN

Please contact our security team on [cpan-security@security.metacpan.org](mailto:cpan-security@security.metacpan.org) privately, with the following information:

- Distribution name, version, and download URL
- Description of malicious behavior
- Relevant logs, packet capture, code lines, screenshots or other context

Examples of malware reports include: typo squatting, dependency confusion, exfiltration of private data, code obfuscation, outbound connections to malicious command and control servers, etc.


## I've found signs of a compromised CPAN account

Please contact the PAUSE admins on [pause-admin@perl.org](mailto:pause-admin@perl.org) privately, with the following information:

- CPAN id (PAUSE login)
- Any evidence of the account being compromised


## I've found a vulnerability in a distribution on CPAN

If you believe you have found a security vulnerability in a distribution on CPAN, please follow the [Coordinated vulnerability disclosure](https://en.wikipedia.org/wiki/Coordinated_vulnerability_disclosure) model.

It's important that you **do not** post information about it on:
- bug trackers, like RT or GitHub
- social media or chat channels, like IRC or Mastodon
- mailing lists or discussion forums

### Step 1: Prepare a Report

Please provide a detailed description of the steps required to reproduce the vulnerability.

The following information is required:

- Distribution name, version and download URL
- Proof of concept code, or a description on how to reproduce
- Logs, code lines, screenshots and other context if relevant

Please ensure any sensitive data such as passwords, authentication tokens, or personal data is not included in the report.

Also consider proposing a date for public disclosure, this is usually 30 days or longer.

If you do not want to be publicly credited as the reporter of the vulnerability, then you should indicate that in your report.

### Step 2: Contact the Maintainer

Check the distribution for a security policy that advises how to report a security vulnerability.
It is usually a file called `SECURITY.md`, or there may be a section in the `README` or main module documentation.

If there is no security policy, look in the `README` or main module documentation for an email address of the current maintainer (who may be different from the original author).
You can also check [MetaCPAN](https://metacpan.org/) to see who uploaded the latest version.

Send the vulnerability report to the distribution maintainer by email or other private channels as outlined in the security policy.
You can CC our team on [cpan-security@security.metacpan.org](mailto:cpan-security@security.metacpan.org) on the report if you would like us to help in triaging the issue, register CVE identifiers, or for any other reason.

When maintainers receive a vulnerability report, they will usually need some time to:

- Confirm the problem and assess severity;
- Check the code to find any potential similar problems;
- Prepare fixes and coordinate a release.

Please allow for some time for maintainers and potential downstream distributions to coordinate fixes before going public.
It is not unusual for authors to request extensions to any proposed disclosure date.


#### If the Maintainer is unresponsive

If the maintainer is unresponsive, or you are concerned that the issue is not being handled, or for other reasons, then please send the report to [cpan-security@security.metacpan.org](mailto:cpan-security@security.metacpan.org) so that we can coordinate with maintainers and relevant community members directly.

If you wish that we keep your identity private, please state this in the first line of your email to us.
You do not need to provide any rationale.


### Step 3: Disclosure

When disclosure has been agreed by the parties, or if details of the vulnerability have otherwise been made public, the CPAN Security Group will take following actions:

1. Add a public record to CPAN vulnerability databases
2. Register a CVE number, if relevant
