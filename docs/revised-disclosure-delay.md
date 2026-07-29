---
layout: single
published: true
toc: true
title: "CPANSec Has Revised Our Default Disclosure Dates"
date: 2026-07-15 10:00:00 +0100
tags: cna cve embargo llm ai disclosure
authors:
  - cpansec
  - robrwo
  - sjn
  - stigtsp
  - timlegge
---

# CPANSec Has Revised Our Default Disclosure Dates

## Summary (TL;DR)

- LLMs are accelerating vulnerability discovery, and many in the security
  community consider AI-discoverable issues to be effectively public already.
- This makes long embargoes riskier: users need timely information so they
  can mitigate, whether or not a fix is available upstream.
- Once we confirm that a vulnerability exists and is in our scope, we assign a CVE identifier,
  notify the author, and set a planned disclosure date, after which the
  CVE is published.
- The default disclosure period is 14 days, but this is a recommendation,
  not a hard deadline.  Maintainers who need more time can request an
  extension, and we will work with them.

---

## Long embargos are becoming short disclosure delays

At the [Perl Toolchain Summit in April 2026](https://perltoolchainsummit.org/pts2026/), members of the CPANSec CNA discussed disclosure periods and decided to reduce the _default_ planned disclosure date ("embargo") for publishing vulnerabilities from 28 days to 14 days.

The feedback from some CPAN authors about this change has not always been positive, so we wanted to write down in detail why we have made this change.

This decision is driven by changes in the technology used for security research.
The availability of cheap computing power and security scanning tools such as large language models (LLMs) have made vulnerability discovery faster and more accessible.

LLMs are useful tools for identifying common patterns across large amounts of documents.
The availability of source code, reference websites, books, blogs and forums online as a training corpus means that when used for vulnerability scanning, they can identify common patterns associated with security flaws, and they can combine multiple flaws into exploitable vulnerabilities.
The technology has improved, and with the aid of additional tools to run specialised scans and guard against mistakes, they can produce useful vulnerability reports.

But the public nature of these tools means that anyone using these tools to find vulnerabilities can find them.
If someone has already found a bug, then anyone else using those tools can find that bug.
The security community consensus is that these vulnerabilities are "public" [\[1\]](#references) [\[2\]](#references) [\[3\]](#references).

There are consequences to this change.

### LLM-generated security reports are a reality

Whether we like it or not, the source code of many open source projects have been ingested by LLMs, and people are using those LLMs to discover security and bugs.

### Long embargos for vulnerabilities about open source projects are problematic

If the availability of this technology means that reports are public, then attackers have access to this too.

In response, some projects have decided to remove embargoes for LLM-generated reports, notably the [Linux Kernel](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=36d49bba19f2c19c933d13b25dcf4eb607a030b3) .

But publishing a vulnerability immediately is unfair to many open source developers,
when many of them are volunteers who maintain projects in their spare time.

However, it is also unfair to delay notifying users about steps they can take to protect themselves, especially when attackers might already know about these vulnerabilities.

A consensus in the security community is leaning towards a shorter disclosure delay of 14-days that gives most open source developers a chance to release a fix, e.g. [\[4\]](#references).

## Perl and CPANSec

The Perl ecosystem (like other open-source ecosystems) is not a single project, but a community of multiple projects and multiple users.
CPANSec needs to support the authors *and* the users.
And CPANSec needs the *trust* of the authors and users.

When we confirm that a vulnerability exists, we will assign a CVE identifier before contacting authors.

The default disclosure date is 14-days from the time we contact authors is usually enough time to fix most issues.
That provides a good balance between giving authors enough time to fix a release and giving users timely information that they can use.
When there are multiple issues, or more complex issues, we will suggest more time.

When we reach out to module authors about a security issue, we will notify them of this policy, with the *planned* disclosure date.
Authors can and should always request more time when needed, and we will work with them.

When issues require more time, then authors should request that we delay the disclosure date.

We also offer to provide assistance, including proof-of-concept scripts and suggested patches.

CPANSec's workflow is outlined in more detail at [https://security.metacpan.org/docs/cve-workflow.html](https://security.metacpan.org/docs/cve-workflow.html).
A FAQ about our CNA process is at [https://security.metacpan.org/docs/cna-faq.html](https://security.metacpan.org/docs/cna-faq.html).

If a fix has been released before the planned date, then we will publish a CVE that refers to the fixed version.

If we have not received a response from the author, we may post issues about a vulnerability on the module issue tracker or pull request as part of the disclosure process.

## CPAN Authors

Our [advice](https://security.metacpan.org/docs/guides/maintainer-security-reports.html) is "Don't panic" and also "Don't be ashamed".
We understand.
A lot of us are perfectionists and place some pride into our work.
Security issues and other bugs can sting.

Asking authors to fix security issues and publishing security advisories about their modules is not in any way about threats, coercion, or public shaming.
Nobody has done anything wrong, and this is in no way a criticism or comment about anyone's skills as a programmer.

Our goal is to improve the security of the ecosystem (which includes downstream users, not just the project's developers),
and we need *your* help.

First and foremost, please make sure your contact email address is correct and reachable, both in your modules and on PAUSE.
If you previously have used a [cpan.org email forward address](https://security.metacpan.org/2026/06/14/cpan.org-email-forwarding-shutdown.html), please change it to something that actually reaches you.

It is also worth finding other authors that you trust to have co-maintenance rights to your module.
This means that you will have collaborators who can help fix security issues.

Next, add a [security policy](https://security.metacpan.org/docs/guides/security-policy-for-authors.html) with a single point of contact.
Source repositories like GitHub support setting up [private security advisory reporting form](https://docs.github.com/en/code-security/security-advisories/working-with-repository-security-advisories/configuring-private-vulnerability-reporting-for-a-repository),
that allows people to create private issues and forks which you and your collaborators can work on.

If you do not want to maintain a module anymore, flag this by handing maintenance to [ADOPTME](https://neilb.org/2013/08/07/adoptme.html).
You'll still have maintenance rights but another author will be able to take it over.
You can also announce this in other forums to find interested authors who might take the module over.

If the module is no longer suitable for use, then you release a last version that marks it as [deprecated](https://neilb.org/2015/01/17/deprecated-metadata.html) and update the documentation accordingly, ideally with recommended alternatives.

If you use a code repository with an issue tracker such as GitHub, ensure that MetaCPAN isn't linking to a separate queue in RT. Your [module metadata](https://metacpan.org/pod/CPAN::Meta::Spec#resources) and documentation should point to the correct issue tracker.

## References

[1] Linus Torvalds, [Linux 7.1-rc4](https://lkml.org/lkml/2026/5/17/896), Linux Kernel Mailing List, 2026-05-17.

[2] Jeremy Stanley, [Coordinated Disclosure in the LLM Age](https://www.openwall.com/lists/oss-security/2026/04/28/15), Open Source Software Security Mailing List, 2026-04-26.

[3] Filippo Valsorda, [Vulnerability Reports are not Special Anymore](https://words.filippo.io/vuln-reports/), 2026-06-23.

[4] Greg Dahlman, [Re: Coordinated Disclosure in the LLM Age](https://www.openwall.com/lists/oss-security/2026/04/28/19), Open Source Software Security Mailing List, 2026-04-28.
