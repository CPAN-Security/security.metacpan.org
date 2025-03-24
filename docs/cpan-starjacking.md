---
title: CPAN StarJacking
toc: true
author: Thibault Duponchelle
---
## Rationale
StarJacking[^1] is an undertaking to make people prefer a module because of manipulated popularity.

While a known topic, checking CPAN for "StarJacking" was mainly the result of the attention drawn to it thanks to experiments[^2] by Eugene Rojavski ([EUGENER](https://metacpan.org/author/EUGENER)).

## How to choose what CPAN module to depend on?
CPAN has such a huge collection of modules available it's sometimes difficult to make a decision about the best one to use.

There are curated lists of recommendations available, like the [Task::Kensho](https://metacpan.org/pod/Task::Kensho) project, @hachiojipm's [Awesome Perl](https://github.com/hachiojipm/awesome-perl) list, and @uhub's [Awesome Perl](https://github.com/uhub/awesome-perl) (again). While these lists are quite useful for assisting in the selection and procurement process, they cannot cover all needs.

Module namespaces may also help, for instance the `Mojo::*` module namespace should, by convention, mainly using contain `Mojo` inner circle modules.
Similarly, `*::Tiny` modules should, by convention, be smaller alternative to other modules of the same purpose.

Most of the time and when possible, users will choose modules and authors that have an established "reputation".
This reputation gives them authority on a topic, and the trust of users in term of security.

On top of that, some indicators of quality (build reports, known issues) and activity (maintenance) may be taken into account.

### Popularity indicators
Beyond reputation (module and/or author), MetaCPAN provides some popularity indicators for CPAN modules:

| Indicator  | Example                                        | Notes |
| ---------- | +--------------------------------------------+ | +---- |
| ++         | ![plusplus](../media/starjacking/plusplus.png) |       |
| River      | ![River](../media/starjacking/river.png)       | [River of CPAN](https://neilb.org/2015/04/20/river-of-cpan.html) position |

### Quality indicators
Some other indicators can help in the choice but give more informations about *quality*:

| Indicator   | Example                                           | Notes |
| ----------- | +-----------------------------------------------+ | ----- |
| Issues      | ![Issues](../media/starjacking/issues.png)        |       |
| CPANTesters | ![CPAN Testers](../media/starjacking/testers.png) |       |
| Bus factor  | ![Bus factor](../media/starjacking/bus.png)       |       |


## StarJacking ![Stars](../media/starjacking/stars.png)
StarJacking refers to the trust that VCS stars provide to a module.

By reusing the popularity of another project, unrelated to the module,
and exploiting the non-verification of the link (metadata),
an attacker can make a module appear much more popular than it actually is.

Other ecosystems like PyPI and npm are also impacted by this problem.

Like many other programming language ecosystems, we can attach "metadata"
such as a public repository, website and issue tracker URLs to CPAN packages.

It has to be done directly in the release metadata.

Example of using resources metadata pointing to a popular project, for instance in `META.yml`
```
META_MERGE   => {
    resources => {
        repository => {
            type => 'git',
            url  => 'https://github.com/popular/lot-of-stars.git',
            web  => 'https://github.com/popular/lot-of-stars',
        },
        bugtracker => {
            web => 'https://github.com/popular/lot-of-stars-and-tickets',
        },
    },
},
```

Read [CPAN add link to version control system](https://perlmaven.com/how-to-add-link-to-version-control-system-of-a-cpan-distributions) for more about how to set the metadata.

CPAN metadata is effectively unverified.

PyPI now implements a mechanism for verifying metadata with [Project Metadata Verifications](https://docs.pypi.org/project_metadata/#verified-details):

> ![PyPI verified](../media/starjacking/pypi-verified.png)

Or it can warn you about metadata information being "unverified":

> ![PyPI unverified](../media/starjacking/pypi-unverified.png)

Back to MetaCPAN, the outcome is that GitHub/Gitlab/...  numbers are almost invisible in MetaCPAN.
For instance, for a module with more than 200 stars in GitHub:

> ![GitHub numbers in MetaCPAN](../media/starjacking/metacpan-side.png)

Only issues are visible, but how can issues help in StarJacking?

Still, we can get more details on metadata by hovering over **Repository**:

> ![GitHub Metadata in CPAN](../media/starjacking/github.png)

As a conclusion, CPAN is not impacted even though CPAN modules can provide inaccurate or incorrect metadata.

It's because GitHub's popularity is not strongly enough propagated to MetaCPAN, so lying on metadata (in a particular repository) does not bring any real advantage over other modules.

## PlusPlusJacking ![PlusPlus](../media/starjacking/plusplus.png)
MetaCPAN package popularity uses an independant indicator, the "++" (PlusPlus).

++ are sent by other CPAN authors.

Manipulation of a PlusPlus score is arguably possible but not straightforward, as it requires the registration of several new accounts, which is a human-reviewed process.

And creations of authors requires a [request](https://pause.perl.org/pause/query?ACTION=request_id) and [manual acceptance](https://www.nntp.perl.org/group/perl.modules/2024/11/msg105533.html) by CPAN admins.

## RiverJacking ![River](../media/starjacking/river.png)
The river score appears next to the module name in several places:

> ![River score](../media/starjacking/riverscore.png)

The river score audience is mostly the maintainers.

The calculation is made externally to PAUSE and MetaCPAN.

## Conclusion
CPAN is highly unlikely to be vulnerable to StarJacking because VCS stars are not a factor in how the popularity of a module is determined on MetaCPAN.

Manipulating popularity via other CPAN in-house indicators is possible but not easy to implement.

The very social nature of CPAN (manual acceptance of new users, code reviews of new modules) makes it difficult overall to exploit.

### Further reading
- MITRE's classification: [CAPEC-693: StarJacking](https://capec.mitre.org/data/definitions/693.html)
- [PyPI security](https://www.youtube.com/watch?v=ZvNuHKDyQXc) (video)
- [PyPI details verification](https://docs.pypi.org/project_metadata/#verified-details)
- [PyPI trusted publishing](https://docs.pypi.org/trusted-publishers/)

-----

*[VCS]: Version Control System
*[CPAN]: Comprehensive Perl Archive Network
*[PyPI]: Python Package Index

[^1]: For a great introduction, see the article [StarJacking – Making Your New Open Source Package Popular in a Snap](https://checkmarx.com/blog/starjacking-making-your-new-open-source-package-popular-in-a-snap/) by _Tzachi Zornstein_, published on _Checkmarx_ on 2022-04-19.
[^2]: This work was published in the article [Falling Stars](https://checkmarx.com/blog/falling-stars/) by _Eugene Rojavski_, published on _Checkmarx_ on 2024-11-18.
