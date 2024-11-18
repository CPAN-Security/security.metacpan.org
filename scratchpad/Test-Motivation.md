# Testing vulnerabilities

One of the first questions that are asked is "why should I test?", which is
impossible to answer without the question "what should be tested?".

With the Cyber Resilience Act (CRA) it is important to realize that those who
release a product for (re)sale, are responsible for adding documentation about
possible vulnerabilities of their own part of the release as well as for the
software that is included from third parties or the software it runs on.

With that in mind, those who create the release should know about possible
CVEs and other vulnerabilities *before* doing the release.

With worldwide available resources that store information about known CVEs
and have extra information available on to what versions those vulnerabilities
apply, it is possible to check if those weaknesses might apply to this release.

## An example

Consider a new perl module you want to release to CPAN that implements the
API to a Xyzzy database. That will likely be DBD::Zyzzy requiring (at least)
DBI and libxyzzy.so

If your new interface requires DBI version 1.00 because the API uses
`$sth->{Statement}` (added in 1.00 on 1998-08-14), you have to tell the
build infrastructure to fail if DBI is not installed, or if the installed
version of DBI is less than 1.00. This can be done in `Makefile.PL`, `BuildPL`,
or `cpanfile`, by adding a "require" rule.

Feature-wise, that will do, but now the fact that critical vulnerabilities
that were fixed in DBI since version 1.00 are now completely ignored by the
release being prepared, so that when DBD::Xyzzy is installed on a system that
has DBI-1.00 installed is now inherently vulnerable to all unfixed issues.

If CVE resources would have been checked, a better option would have been to
require version 1.643 even if the API itself does not require this version for
its features. If 1.00 is required, `CVE-2020-14393`, `CVE-2020-14392`,
`CVE-2019-20919`, `CPANSA-DBI-2014-01`, `CVE-2014-10402`, `CVE-2014-10401`,
`CVE-2013-7491`, and `CVE-2013-7490` would all be open for attackers.

This process may explode if the release requires Foo, which requires Bar and
Baz, requiring Fooble and optionally Grumble::DE and so on and so on.

Likely the release depends on more than just a single module or library, and
knowing about every single fixed or open CVE should be a guide towards a much
safer release where "No known CVEs at time of distribution" is a welcome
addition to the release notes!

## What can be tested

One can only test what is declared for the software of the release itself or
its direct and indirect dependencies. If some other software is fetched runtime
from an unknown source, there is no control over what version is fetched and/or
the trustworthyness of that sofware.

The CPANSec group tries to make a toolset available that analyses a current
release folder, digging through known locations of declarations of requirements
and checking these against known vulnerability resources.

## Conclusion

Your code might be safe, but if it depends on other things that you do not have
direct control over, your release might be vulnerable.
