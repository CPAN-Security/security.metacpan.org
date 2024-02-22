# CPANsec tooling

## Scope

One of the goals of the CPAN Security Working Group is to help end-users in
understanding security hazards and supply all that is needed to have enough
information to make sane decisions.

Security threads are often hard to understand and sometimes hidden in parts
of the system that are not very obvious. To identify possible threads there
are CVEs, RHSAs, RHBAs, GHSAs and many more that can be used to see if your
software may have known vulnerabilities.

To get an index of the toolchain and software stack, you might need an SBOM
(Software Bill of Materials).

## Goal

Given security issues are complex and end-users (from our perspective) will
wonder what they should do to act on a given report, I think we should do our
best to not only report issues to end-users, but whenever possible, given a
SBOM pass on an advice on what action should be taken to be "safe" again.

Tooling is the issue to the end user. Assume we will be able to generate an
SBOM (or at least have tools to help the end-user generate one), the next
step should be to take that user by the hand and use our knowledge and CVE
database to suggest changes.

With the available tooling, gather as much information needed to make sane
decisions in what to do to make your software/package/release as safe as
possible and law-conformant.

Create tooling that will recommend and suggest changes to be made or what
parts of the software should be updated or replaces, what requirements are
to be added, changed or removed and so forth.

Given how e.g. Devel::PPPort works in helping module authors to be backward
compatible, maybe work on something similar where the script can spew tons
on what could/should be changed.

## Tooling

### SBOM creation

???

### Vulnerability explaining

#### [Net::CVE](https://metacpan.org/release/Net-CVE)

Fetch CVE (Common Vulnerabilities and Exposures) information from cve.org

#### [Net::OSV](https://metacpan.org/release/Net-OSV)

Search known vulnerabilities on the Open Source Vulnerabilities Database (OSV)

#### [Net::NVD](https://metacpan.org/release/Net-NVD)

Query CVE data from NIST's NVD (National Vulnerability Database)

### Vulnerability identification

#### [Test::CVE](https://metacpan.org/release/Test-CVE)

Test distribution/file/folder against known CVE's

### [CPAN::Audit](https://metacpan.org/release/CPAN-Audit)

Audit CPAN distributions for known vulnerabilities

## References and links

https://cve.org
https://cve.mitre.org/cve/search_cve_list.html
https://www.cvedetails.com/
https://github.com/advisories/
https://access.redhat.com/errata/
https://access.redhat.com/security/
