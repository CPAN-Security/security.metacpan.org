---
layout: page
title: Pre-Release Disclosure
toc: true
---


The CPAN Security Working Group (CPAN-SEC) receives and handles reports of
undisclosed vulnerabilities to be able to assist the community in preparing
patches, coordinating with authors and reporters, and preparing public
announcements.

This includes access to embargoed pre-release vulnerability information provided
by external sources contingent on the understanding that we will not disclose
this information prior to the public announcement date of the vulnerability.

Members on the cpan-security@perl.org mailing list need to agree to the
following:

1. The information that you obtain as part of the pre-release notification is
not to be shared with anyone besides;
   - cpan-security@perl.org members
   - The Perl security team
   - The authors or security team of affected packages
   - The sender and recipients of the original notification email 

   Information should be kept [[TLP:RED]](https://www.cisa.gov/news-events/news/traffic-light-protocol-tlp-definitions-and-usage)

2. All discussion about the pre-release information is to be handled through
private channels such as the cpan-security@perl.org mailing list. This
information is not to be discussed on public channels such as IRC, Mastodon, or
similar.

3. Patches or PoCs are not to be kept on public GIT or CPAN repos available to
anyone else, or similar. Testing of patches must be in a staged private
environment isolated to your system. These patches should only be made available
publicly after the public release date of the vulnerability.

4. The deployment of the patches and/or mitigations for pre-release
vulnerabilities is NOT permitted to any system during the embargo, with the
exception of CRITICAL vulnerabilities that threaten the integrity of PAUSE, CPAN
or MetaCPAN.

Members of the cpan-security@perl.org mailing list need to accept these terms by
replying to this agreement. (Preference “I acknowledge this document”).

The CPAN Security Working Group <[cpan-security@perl.org](cpan-security@perl.org)>

------------------

Based on: [https://wiki.gentoo.org/wiki/Project:Security/Pre-Release-Disclosure](https://wiki.gentoo.org/wiki/Project:Security/Pre-Release-Disclosure) (CC-BY-SA-4.0)
