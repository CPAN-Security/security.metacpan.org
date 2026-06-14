---
layout: single
published: true
toc: true
title: "Security Reports for Module Maintainers"
date: 2025-01-05 18:15:00 +0000
tags: cpan module authors bug triage
authors:
  - robrwo
---

## Receiving Reports

Don't panic.

A vulnerability report is a bug report, but it is for a bug that may allow
users to execute unauthorised code, access unauthorised resources, or
to have an adverse impact on the system.

The first thing you should do is acknowledge receipt of the report,
ideally copying the CPAN Security Group [cpan-security@security.metacpan.org](mailto:cpan-security@security.metacpan.org)
if the notification is not from us or copied to us.

If you no longer maintain the module, indicate that in your reply. (Also consider
[marking your module for adoption](https://neilb.org/2013/08/07/adoptme.html).)
If there is a different maintainer, then refer the reporter to that maintainer, and ideally copy them on the report.

CPANSec will usually provide you with CVE numbers for the vulnerabilities in the report,
and indicate a disclosure date, usually 14 days from the date that the report was sent to you.
You do not have to release a fix before that date,
but if you are unable to release a fix before that date,
and believe that publishing the vulnerability before a fix is released will endanger users, then notify CPANSec as soon as possible.

You do not have to honour the embargo time.
You may choose to disclose the issue before that date.
Also note that mentioning the issue in a public issue tracker, pull request or commit counts as disclosure.
In some cases CPANSec may opt to publish the CVE sooner if it has already been disclosed publicly.

However, there may be cases where the security issue affects multiple modules that are well-known to share a common code base.
When this happens, we may arrange for coordinated disclosure where multiple module authors release fixes at the same time.

The next step is to triage the issue.
This is done is much the same way you would triage the bug reports,
but taking precautions to protect systems from potential side effects of the reported bugs.

If you cannot confirm the issue, then please reply to the reporter indicating that.
The reporter may respond with additional information.

If you confirm the bug but do not believe it to be a security issue, then please reply to the reporter indicating why.
(For example, if there is no realistic way that a user can trigger the condition.)

If you have been sent a patch to fix the bug, then this is only a suggested fix.
You do not need to apply this patch, although CPANSec may publish this patch along with the vulnerability if it is unfixed.
If there is a problem with that patch, then please notify CPANSec.

When you release a module with a fix, please indicate the CVE numbers in the change log.
(If the report contains other codes such as [CWE](https://cwe.mitre.org) or [CAPEC](https://capec.mitre.org) numbers, you do not need to include those in the change log. These are used for classifying vulnerability reports, but are not considered useful for software developers.)

If there are multiple vulnerabilities in the report, you do not need to fix them in the same release.
It is acceptable to release separate versions with fixes for different vulnerabilities.

When you have released a fix, please notify CPANSec so that we can publish or update the CVE.

If you need further information, please see the [CPANSec CNA and CVE Frequently Asked Questions](/docs/cna-faq).

## Submitting Reports

If you have received a vulnerability report from someone unaffiliated with CPANSec, or found one while working on your module, then please notify us at [cpan-security@security.metacpan.org](mailto:cpan-security@security.metacpan.org).

CPANSec can assign a CVE number, and publish the vulnerability report with the [CVE Program](https://www.cve.org).

By proactively submitting security reports to CPANSec, you can save us time and effort in issuing a retroactive CVE after a release, and to alert downstream users of your module that they need to upgrade their software
or make changes to mitigate the effects of a vulnerability.

CPANSec can also assist you with fixing the vulnerability, if you want assistance.