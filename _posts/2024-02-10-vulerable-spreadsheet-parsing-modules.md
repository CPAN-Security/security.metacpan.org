---
layout: post
title: "Vulnerable Perl Spreadsheet Parsing modules"
published: True
toc: true
tags: cve timeline report
---

Between Dec 2023 and Jan 2024, vulnerabilities in Spreadsheet::ParseExcel and Spreadsheet::ParseXLSX were reported to the CPAN Security Working Group (CPANSec).
This document describes the timeline and analysis of events.

## CVE-2023-7101: Spreadsheet::ParseExcel arbitrary code execution vulnerability

Đình Hải Lê discovered an arbitrary code execution (ACE) vulnerability in the Perl module Spreadsheet::ParseExcel, version 0.65 and earlier.
An attacker, exploiting this vulnerability, would craft an Excel file containing malicious code encoded as a number format string, which is executed when the file is parsed by Spreadsheet::ParseExcel.
Basically, untrusted data is passed to the Perl `eval` function enabling arbitrary code execution.

A detailed write up of the vulnerability and Proof of Concept (PoC) is available at https://github.com/haile01/perl_spreadsheet_excel_rce_poc

It was allegedly used by UNC4841, a China-backed threat actor, to compromise Barracuda Email Security Gateway (ESG) appliances, and is considered a root cause for CVE-2023-7102.
(https://www.barracuda.com/company/legal/esg-vulnerability)


## CVE-2024-22368: Spreadsheet::ParseXLSX denial of service vulnerability

Đình Hải Lê discovered a DoS vulnerability in Spreadsheet::ParseXLSX, version 0.27 and earlier, enabling denial of service attacks via out-of-memory bugs when parsing a crafted XLSX file.

Basically, an attacker could create a spreadsheet file and set a merged cell to include all possible cells in the spreadsheet.
Because of the way vulnerable versions of Spreadsheet::ParseXLSX parsed the file, it would allocate huge amounts of ram to track the merged cell.
Simply uploading a simple spreadsheet to a web application using the vulnerable module would cause a denial of service as all memory on the server was used. 

A detailed write up of the vulnerability and PoC is available at https://github.com/haile01/perl_spreadsheet_excel_rce_poc/blob/main/parse_xlsx_bomb.md .

It is not known whether this vulnerability was used to cause a denial of service on a production server.

## CVE-2024-23525: Spreadsheet::ParseXLSX XML external entity attack vulnerability

An Pham discovered a XML external entity injection (XXE) vulnerability in Spreadsheet::ParseXLSX version 0.29 and earlier, enabling an attacker to interact with the system 

This is a classic XML external entity (XXE) injection vulnerability, in which the attacker can cause the vulnerable code to include data (or a file) that should not be available, by simply instructing the XML parser to load external data.
The PoC also includes an example that would cause a DoS.

Configuring an XML parser to allow loading external entities is dangerous and should never be the default.

A detailed write up of the vulnerability and PoC is available at ttps://gist.github.com/phvietan/d1c95a88ab6e17047b0248d6bf9eac4a

# Timeline

## October 2022 to June 2023

On October 23rd, Đình Hải Lê (https://github.com/haile01) started to investigate the Spreadsheet::ParseExcel module after noticing that `eval` was called in the source code.

On October 26th, Đình Hải Lê was able to successfully create a PoC for both the Arbitrary Code Execution (ACE) vulnerability in Spreadsheet::ParseExcel (CVE-2023-7101) and the out-of-memory Denial of Service (DoS) vulnerability in Spreadsheet::ParseXLSX (CVE-2024-22368).

On November 17th, Đình Hải Lê attempted to contact the last maintainer to release a version of Spreadsheet::ParseExcel regarding the ACE vulnerability and attempted to contact the author of Spreadsheet::ParseXLSX regarding the out-of-memory DoS vulnerability.

Unfortunately neither contact attempt succeeded.

On March 15th, the Initial PoC was published on Github by Đình Hải Lê.

On June 20th, Đình Hải Lê submitted both bugs to huntr.com.
huntr.com supports an open source vulnerability disclosure program, where any member of the public can report vulnerabilities found in repositories on GitHub.com.
huntr follows a responsible disclosure program as documented at https://huntr.com/guidelines/.

On June 21st, the PoC published by Đình Hải Lê was referenced by a huntr.com representative in an issue logged in two Github repositories (Spreadsheet::ParseExcel and Spreadsheet::ParseXLSX) as:

    https://github.com/doy/spreadsheet-parsexlsx/issues/103 
    https://github.com/jmcnamara/spreadsheet-parseexcel/issues/7

Unfortunately, there is no indication that the owners of either the Spreadsheet::ParseExcel git repository or the Spreadsheet::ParseXLSX git repository saw either of the issues.

In addition, there were no issues logged at https://github.com/runrig/spreadsheet-parseexcel, which was the GitHub repository referenced in version 0.65 of the Spreadsheet::ParseExcel module on MetaCPAN, nor were any issues logged on Request Tracker, the traditional issue tracker for Perl modules, https://rt.cpan.org/Dist/Display.html?Queue=Spreadsheet-ParseExcel or https://rt.cpan.org/Public/Dist/Display.html?Name=Spreadsheet-ParseXLSX.
December 2023

    At some point between the time CVE-2023-7101 was discovered, and the time it was fixed, malicious threat actors used the vulnerability to compromise an undisclosed number of Barracuda Email Security Gateways.
At this time no one has provided the exact timing of the compromise.

On December 21st, Barracuda pushed patches to all Barracuda Email Security Gateway (ESG) appliances to fix CVE-2023-7102.

On December 22nd,  Barracuda pushed patches to previously compromised ESGs (https://www.barracuda.com/company/legal/esg-vulnerability).

On December 24th, Mandiant (a Google owned Incident Response company) issued  CVE-2023-7101 and published a related disclosure, MNDT-2023-0019.
(https://github.com/mandiant/Vulnerability-Disclosures/blame/master/2023/MNDT-2023-0019.md).

On December 27th, the Cybersecurity and Infrastructure Security Agency (CISA) emailed all prior maintainers of the Spreadsheet::ParseExcel module.

On December 28th, the CISA forwarded the email to the CPAN Security Working Group mailing list.
CPANSec then took the following steps during the next 24 hours:

    CPANSec reached out to a former maintainer, John McNamara, who still had primary permissions (FIRSTCOME) which would allow him to release an updated version.
    McNamara released version Spreadsheet::ParseExcel 0.66 which included a patch provided by Daniel Ruoso (https://github.com/ruoso) that resolved the issue.
    CPANSec notified the oss-security mailing list, and downstream distributions like Alpine Linux, Arch Linux, NixOS and Debian.
Note that Debian already had a patch on the way when we reached out.


## January 2024

On January 2nd, Michael Daum released version Spreadsheet::ParseXLSX version 0.28 with fixes for the DoS vulnerability CVE-2024-22368.
The CPANSec requests a CVE identifier from MITRE.

On January 9th, MITRE publishes their analysis of CVE-2024-22368

On January 10th, CPANSec notifies the oss-security mailing list

On January 17th, Michael Daum released another update to Spreadsheet::ParseXLSX version 0.30 with fixes for a XXE attack vulnerability CVE-XXX. CPANSec requests a CVE identifier.
CVE-2024-23525 was issued on January 17th, 2024 for the XXE vulnerability.

On January 18th, CPANSec notifies oss-security mailing list and Michael Daum released Spreadsheet::ParseXLSX version 0.31 which referenced CVE-2024-23525 which had been fixed in version 0.30.


# Responsible Disclosure

Based on the information provided by Đình Hải Lê, and publicly available information, it appears that Đình Hải Lê and/or other parties followed a responsible disclosure process.
Attempts to contact the previous maintainers were followed by a reasonable waiting period before the PoC was published.
After the PoC was published huntr.com also attempted to contact the previous maintainers.
Resolution

After CVE-2023-7101 was issued, a patch to fix the vulnerability was written by Daniel Ruoso (https://github.com/ruoso) and submitted as a pull request to the GitHub repository.
Often, in the case of modules with absent or unresponsive maintainers (Appendix A), a patch could languish requiring a user to apply the patch manually.
However, in this case the CPANSec asked the module's FIRSTCOME (appendix A) author John McNamara (JMCNAMARA)  to release a patched version.
JMCNAMARA had been copied on the notification by CISA and was engaged in the conversation making the resolution faster than in might have otherwise been.

The DoS vulnerability in Spreadsheet::ParseXLSX (CVE-2024-22368) was patched by Michael Daum (NUDDLEGG).
Daum  was made the new owner after contacting the previous module owner (DOY) and volunteering to maintain the module.
Daum released version 0.28 on January 2nd, 2024 to resolve the issue.

The XML external entity (XXE) injection vulnerability in Spreadsheet::ParseXLSX (CVE-2024-23525) was patched by Michael Daum and version 0.30 was released on January 17th, 2024 to resolve the issue and a final version 0.31 to reference the CVE number on January 18th, 2024.


# Appendix A

## CPAN

The Comprehensive Perl Archive Network (CPAN) is the world's oldest Open Source language ecosystem and publishing platform.
Having existed since 1995, it has seen and been part of the massive success of the Internet.
It is used today by developers and businesses globally, with more than 14000 developers publishing their Open Source components on CPAN.


## CPAN Security Group

The CPAN Security Group (CPANSec) is a newly formed group stemming from the Perl Toolchain community.
One of its goals is to attempt to facilitate the resolution of security issues with CPAN modules.
Depending on whether the maintainer is active or not, this can be a simple matter of reaching out to a maintainer.
In other cases, it may take considerable time to either contact the maintainer or work with Pause to grant COMAINT to another maintainer.

Regardless, the goal is to have vulnerabilities resolved quickly.
To that end, the CPANSec is attempting to increase its profile so that reporters of security vulnerabilities are able to reach someone who can help, even if the maintainer is not responsive.

CPANSec can be found at https://security.metacpan.org/.

## CPAN Module Maintainers

### FIRSTCOME

Perl follows a "first-come" process for assigning ownership of a module.
The first person to upload the named module is granted FIRSTCOME permissions.
That person is able to release new versions or transfer permissions to another CPAN author or grant co-maintenance permissions (COMAINT) to one or more CPAN authors.
Only the FIRSTCOME permission allows an author to transfer ownership or grant permissions to a new co-maintainer, though the PAUSE admins can also grant COMAINT if it is deemed appropriate.

### COMAINT

The COMAINT permission allows a CPAN author to issue a release of the module.

## Absent/Unresponsive Maintainers

As with many Open Source projects, maintainers can come and go over time.
Just because a new version of the module has not been released in some time it does not mean the maintainer is absent.
Some modules are "functionally complete" and unless something changes there may be no need for a new version to be released.

Absent maintainers however can sometimes be determined by looking at the release history of modules that they have released.
If the maintainer has not released any new or updated modules in several years, they may be absent.

CPAN signals absent maintainers by using the special users NEEDHELP, HANDOFF and ADOPTME, as documented in the PAUSE Operating Model, https://pause.perl.org/pause/query?ACTION=pause_operating_model.

In the case of both Spreadsheet::ParseExcel and Spreadsheet::ParseXLSX the maintainers who released the last version appear to have been absent and had not signaled that they needed help or that the modules were up for adoption.

### NEEDHELP

Assigning COMAINT permissions to the special CPAN user NEEDHELP says that the owner is happy to give co-maint to anyone interested in helping with the module, but plans to retain ownership.

### HANDOFF

Assigning COMAINT to the special CPAN user HANDOFF is a way for the current owner of a module to flag that they're happy for someone else to take over ownership of the module.
One still needs to ask the owner to adopt the module.

### ADOPTME

Assigning COMAINT permission to the ADOPTME user flags that a module is open to takeover.
If the owner is ADOPTME, it can also indicate a deceased author.
ADOPTME as co-maintiner can indicate a non-responsive author, or an author who has explicitly added ADOPTME.
