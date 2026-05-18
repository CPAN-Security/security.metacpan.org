---
layout: single
published: false
toc: true
title: "CPANSec CNA and CVE Frequently Asked Questions (FAQ)"
date: 2025-01-05 18:15:00 +0000
tags: faq cna cve
author: rrwo, sjn
---

## CPANSec CNA and CVE Frequently Asked Questions (FAQ)

[TOC]

### Organization

#### What is the CPAN Security Group (CPANSec)?

The CPAN Security Group (CPANSec) is a group of volunteers from the Perl community who work to support the security of the Perl ecosystem
through education and outreach, security analysis of open source Perl distributions on CPAN, and support for fixing security vulnerabilities.

#### How is CPANSec related to the Perl and Raku Foundation (TPRF)?

The Perl and Raku Foundation](https://perlfoundation.org) is a community organisation that supports the Perl and Raku languages and community.

CPANSec is a distinct group from TPRF.

#### How is CPANSec related to P5P?

The [Perl 5 Porters](https://lists.perl.org/list/perl5-porters.html) (P5P) is a mailing list of people in the Perl community who take an interest in mainting and growing the Perl language.

While some of the people who maintain the Perl language are members of CPANSec, they are two entirely different groups.

#### CPANSec is a CNA. What is a CNA?

A CNA is a CVE Numbering Authority that is authorised by the CVE Program to assign CVE IDs to security vulnerabilities and publish them within their areas.

A team of CPANSec members operates the [CNA for the CPAN and Perl ecosystems](https://security.metacpan.org/2025/02/25/cpansec-is-cna-for-perl-and-cpan).

#### What is the CVE Program? What is a CVE?

The [CVE Program](https://www.cve.org/) is an international, community-driven effort to identify and catalog publicly disclosed vulnerabilities.

A CVE (Common Vulnerability Enumeration) is an numeric identifier for publicly disclosed vulnerabilities.
It allows different groups to use the same ID when discussing vulnerabilities.

Publishing a CVE is aa way of alerting downstream users (distributors, system administrators, and software developers) that the software has a vulnerability. They can take steps to fix the issue (such as upgrading to a fixed version) or to mitigate the issue (such as changing the configuration or how the software is used to limit the effects vulnerability).

#### What is the April Task Force?

The April Task Force is a CPANSec project founded in April 2026 by members of CPANSec and the [Perl Toolchain Community](https://perltoolchainsummit.org/pts2026).

The aim of the project is to develop and use specialialised tools to identify security vulnerabilities in the Perl ecosystem.
This includes LLM-based security analysis tools.
When vulnerabilities are found, they are handed to the CPANSec CNA, who will contact authors and encourage them to fix vulnerabilities.

#### How is the April Task Force related to the Perl and Raku Foundation?

The Perl and Raku Foundation (TPRF) is the fiscal host of the project.

#### Who funds the April Task Force?

This task force is funded through a grant from Linux Foundation, through the [Alpha-Omega project](https://alpha-omega.dev/)

#### Who decides what the task force works on?

Within the scope of the grant, the task force members work autonomuously.

We do prioritise modules that are popular (using various metrics) or widely used (including legacy modules that may still be in use), or upriver modules with many dependencies.

#### What is the criteria for assigning a CVE number?

If the members of CPANSec investigating a reported issue consider it to be a security vulnerability, then we assign a CVE number.

If the vendor (module maintainers) consider something to be a security vulnerability in their software, and request a CVE from CPANSec, then we will assign a CVE number.

#### What is a security vulnerability?

Security vulnerabilities are considered anything that allows users to execute unauthorised code, access unauthorised resources, or to have an adverse impact on accessibility, integrity or performance of a system.

#### How do you go from a vulnerability report to a CVE?

We triage the report to verify that there is a vulnerability, in much the same way that one verifies bug reports (although taking precautions to protect systems from damage).

We check to ensure that the issue is with the reported module, and not a dependency. If the dependency is not Perl-related, then it is out of CPANSec's scope, although we may forward the report to the appropriate maintainer or CNA. (Note that in some cases, there may still be a CVE for code that has an insecure dependency.)

We check to ensure that the reported issue is not a duplicate of an existing CVE.

Otherwise, we will reserve a CVE. (We may assign it an earlier year if the issue has been reported publicly before.)

We will contact the maintainers, if they have not already been contacted, to notify them of the report and CVE, as well as the planned disclosure date.

Eventually the report will be published, as an upload of metadata about the report to MITRE, and email announcements to our [CVE Announcement List](https://lists.security.metacpan.org/cve-announce/) and to other security lists, as well as to the maintainers.

See the [CNA Vulnerability to Fix and Disclosure Workflow](https://security.metacpan.org/docs/cve-workflow) for the process that we follow.

#### Why does CPANSec issue CVEs for older vulnerabilities that have been fixed?

Again, the purpose of a CVE is to alert users of an issue. Some users may not have upgraded their software to newer release that fixes an issue. By publishing the CVE, we are alerting downstream users that the software they are using may need to be upgraded, patched or adjusted.

#### But P5P didn't agree that this was worth a CVE at the time...

CPANSec may have decided an older issue was still a vulnerability and should have a CVE.

#### Why does CPANSec issue CVEs for embedded vulnerabilities that don't affect the module?

If a distribution contains a copy of a third-party library with a known vulnerability, then that needs to be identified as an issue to be resolved, even if the Perl modules in that distribution do not make use of the vulnerable feature.

#### Why does CPANSec issue multiple CVEs for the same module version?

A module may have distinct vulnerabilities that need to be identified sepatately. Distinct vulnerabilities will have distinct effects and mitigations. And it is possible that the vulnerabilities are not all fixed in the same release.

### Validity and severity

#### The documentation already warns users about the issue. Why is it a CVE?

Unsafe defaults are not considered acceptable, because they are often unchanged when software is used in production.

#### The module author doesn't agree that this is a vulnerability. Now what?

We encourage module authors to push back on reports they do not agree with. We might wrong about something.

But if CPANSec can verify that the software has a vulnerability, then a CVE will be issued.

#### This issue has been known for years. Why is a CVE being issued now?

There are many security issues that are "known" by people who have experience with a piece of software, but rarely written down and available to everyone.
Or when they are written down in bug reports, they are often overlooked.

Publishing a CVE alerts users about an issue they need to fix.

#### The CVE is for 2025, but this bug was first documented in 2014. Why won't you change it?

The CVE number was reserved for the year that we believe the vulnerability was first reported. (This may be in a bug tracker or mailing list or block post.)
Once the number has been shared outside of the CNA (to the module authors, for example) or published, it cannot be changed.

Sometimes as a result of publication, people contact the CNA to identify earlier reports. We will update the CVE record to reflect additional information.

#### Do CVEs make the Perl community look bad?

Issuing CVEs shows that we care about security enough to evaluate projects for security vulnerabilities, and to notify users about issues that may require upgrades, patches or other mitigation.

#### A module has an unfixed CVE. Why is it still on CPAN?

Nothing is removed from CPAN unless it contains malware or violates copyright.

Sometimes modules have open CVEs because the maintainers do not agree with the issue, or that issue is worth fixing, or because the software is abandoned.

But having the module available means that someone else can take over maintenance or fork the module, or apply a patch to that version.

#### A module has an unfixed CVE. Is it safe to use it?

That depends on the vulnerability.

CVEs are often published with mitigation advice or patches that you can apply.

If the vulnerability is for a feature that you are not using, then it may not be relevant.
However, you need to guard your systems against feature creep where you eventually start using it.

### Process & Community concerns

#### I've just received a vulnerability report. What do I do?

Don't panic.

If you no longer maintain the module, or are unable to make changes, contact CPANSec.

If you need help understanding the report, or making changes, contact CPANSec.

#### I've received a report from someone outside of CPANSec. What do I do?

Anyone can submit a security report to you. But you (as the maintainer) have the right to disclose this to anyone.
We recommend that you disclose this to CPANSec, so that we can assist in triage, fixing, and assigning CVEs.

#### The reporter is asking me for money!

If you have not offered a bug bounty, then you don't have to pay them.

#### Who can submit vulnerabilities to the CPANSec CNA?

Anyone can.

CPAN authors and maintainers are encouraged to.

#### You can't tell me what to do!

That's true. We're not telling you what to. We're telling you about vulnerabilities, and offering advice to fix them.

You don't have to follow follow our advice or cooperate with us in any way.

But we will still publish CVEs by the advised date.

#### But I am not in the EU (or US or India or China)....

CPANSec is not affiliated with any government agency.

While members of CPANSec will often discuss specific regulatory regimes as a reason to improve the security of software, they are not the defining reason.

Software security is important because it protects people: in much of the world, nearly everything in a peoples' lives and the things they use and rely on are processed through software.

#### This is a hobby, and you are ruining the fun!

We understand that much of the software on CPAN is written and maintained by volunteers in their spare time.
We understand that a growing queue of bug reports for a side project can be overwhelming.
And we understannd that people have other obligations, and more important things in their lives than maintaining software they wrote for fun 15 years ago.

If you need assistance, please reach out to us.

We may ask for maintenance permissions to release an update the software, if you agree.

#### Telling me to fix a vulnerability is stressful!

You don't have to fix anything.

If you are too busy, or physically or mentally unable to fix the software, then let us know that you are unable to. (You don't need to tell us why.)

We may ask for maintenance permissions to release an update the software, if you agree.

#### Telling me that you are going to publish a CVE for my module is coercive!

The purpose of a CVE is to notify users that the software should be upgraded, or that they should take steps to minimise the security issues.

If no fix is released, then we will publish the CVE to protect users.
We do not embargo vulnerabilities for unreasonably long periods of time.

If you do not agree that this is a vulnerability, let us know why.

#### Why are you giving me a 14-day deadline to fix it?

You have no "deadline" for fixing security vulnerabilities.
CPANSec policy is to publish vulnerabilities at 14 days after the maintainer is notified, unless there are compelling reasons for a longer embargo on publishing.
(For example, we may want to coordinate releases of fixes for multiple modules, or the result of publishing the vulnerability may be dire enough to ensuring that fixes are available first.)

We may publish vulnerabilities sooner if they have already been disclosed, for example, by the maintainers of a module (including a commit or pending release in a software repository),
or by a user in a public forum (including the issue tracker or pull requests for a module).

If we are unable to contact any maintainers, then we may disclose the vulnerability sooner.

Note that the 14-day embargo has emerged from a consensus in the security community that issues discovered with LLMs are essentially public, since anyone using these tools can find them.
The 14-day window is a compromise that allows maintainers (many of whom are volunteers working in their spare time) to fix issues without waiting too long for duplicate reports to be submitted,
or malicious people to take advantage of unfixed vulnerabilities.

#### I don't maintain this module anymore.

If we've written to you, then please respond that you do not maintain the module and are unwilling to update it.

Some members of CPANSec might volunteer to take on maintenance, just to release a fix.
In some cases, they may also mark the module as "deprecated" if we believe the module is no longer suited for it's purpose, or there are better solutions.

#### But this module has been deleted from CPAN

Deleted modules reside on BackPAN and are still available for those who are still using them. We will still publish security advisories for them.

#### Can I subscribe to receive notificastions about new vulnerabilities?

Yes. Visit [CVE Announcement List](https://lists.security.metacpan.org/cve-announce/), follow the link for more information and fill in the form to subscribe.

### Tooling & AI Models

#### What tools does the April Task Force and CPANSec use?

We may use a variety of LLM models, fuzzers, and other security analysis tools, as well as unsophisticated tools such as grep and awk.

#### Can I opt out having my modules analysed by the April Task Force?

No.

You have published your modules with the source code under the terms of an open source license on CPAN.
There are no open source licenses that restrict the analysis of software.

We understand that authors have concerns about "AI" tools appropriating their work.
There is a grey area between a system that can analyse code for bugs, and writing code to reproduct the bugs or recommending fixes (which is generative).

The LLM tools are already available, and people will be using them to analyse open source code.
There is nothing preventing someone from making their own mirror of CPAN and having their private LLM tools analyse that code.
And there is nothing preventing those people from misusing vulnerabilities that they have found, rather than publishing them.

A goal of the April Task Force is to use the same technologies to identify and fix vulnerabilities.

#### Can I opt out having my modules analysed by LLMs and other data miners?

No.

See the above discussion.

CPAN and MetaCPAN do block badly behaved robots (especially since metacpan.org itself is meant for people, not bots).
But ultimately we (CPAN and mirrors) cannot control what some does with a module once they have downloaded it.
