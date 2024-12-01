# StarJacking
## Rationale
Make people prefer a module because of manipulated popularity. See [StarJacking](https://checkmarx.com/blog/starjacking-making-your-new-open-source-package-popular-in-a-snap/)

While a known topic, checking CPAN for "StarJacking" was mainly ported to attention thanks to experiments from Eugene Rojavski ([EUGENER](https://metacpan.org/author/EUGENER))

## How to choose what CPAN module to depend on?
CPAN is an ocean, where it's sometimes difficult to make a decision about the best module to use. 

Some lists are available like [Task::Kensho](https://metacpan.org/pod/Task::Kensho), [Awesome Perl](https://github.com/hachiojipm/awesome-perl) or [Awesome Perl](https://github.com/uhub/awesome-perl) (again) but they definitely don't cover all needs.

Naming of modules can also help, for instance `Mojo::*` modules should be, by convention, mainly using other `Mojo` inner circle modules as dependencies. `*::Tiny` are generally smaller alternative to other modules of the same purpose, etc...

Most of the time and when possible, choice will go on modules and authors that have established "reputation". This reputation gives them authority on a topic, and trust of users in term of security.

On top of that, some indicators of quality (build reports and known problems) and activity (maintainance) can be taken into account.

## Popularity indicators in CPAN
Beyond reputation (module and/or author), MetaCPAN provides some popularity indicators for CPAN modules:
- ++
![plusplus](../media/starjacking/plusplus.png)

- [river](https://neilb.org/2015/04/20/river-of-cpan.html) position
![river](../media/starjacking/river.png)

## Quality indicators in CPAN
Some other indicators can help in the choice but give more informations about *quality*:
- Issues
![Issues](../media/starjacking/issues.png)
- CPANTesters
![CPAN Testers](../media/starjacking/testers.png)
- Bus factor
![Bus factor](../media/starjacking/bus.png)

Interpretation of indicators "issues" and "bus factor" is debatable.

## Types of attacks
Link popular repository:
- "StarJacking" - Attach very popular github repository to module

Craft fake popularity:
- "PlusPlusJacking" - Manipulate ++ indicator
- "RiverJacking" - Manipulate river score

## StarJacking ![Stars](../media/starjacking/stars.png)
StarJacking refers to the trust that VCS stars provides to a module. 

Reusing popularity of another project, unrelated to the module, 
and exploiting the non-verification of the link (metadatas) in order make a module falsely popular.

Other ecosystems like PyPI and NPM are well impacted by this problem.

Like other ecosystems, we can attach "metadatas" (repository, website, issue tracker...) to CPAN packages.

It has to be done directly in the release metadatas.

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

Read [CPAN add link to version control system](https://perlmaven.com/how-to-add-link-to-version-control-system-of-a-cpan-distributions) for more about how to set metadatas.

CPAN metadatas are effectively un-verified.

PyPI now implements a mecanism for this matter with [Project Metadatas Verifications](https://docs.pypi.org/project_metadata/#verified-details):

![PyPI verified](../media/starjacking/pypi-verified.png)

Or it can warns you about metadatas informations being "unverified":

![PyPI unverified](../media/starjacking/pypi-unverified.png)

Back to (Meta)CPAN, the outcome is that GitHub/Gitlab/... numbers are almost invisible in MetaCPAN. For instance, for a module with more than 200 stars in GitHub:

![GitHub numbers in MetaCPAN](../media/starjacking/metacpan-side.png)

Only issues are visible, but how issues help in StarJacking?

Still, we can get more details on metadatas by hovering **Repository**:

![GitHub Metadatas in CPAN](../media/starjacking/github.png)


As a conclusion, CPAN is not impacted even though CPAN modules can lie on their metadatas.

It's because GitHub popularity is not strongly enough propagated to (Meta)CPAN, so lying on metadatas (in particular repository) does not bring any real advantage over other modules.

## PlusPlusJacking ![PlusPlus](../media/starjacking/plusplus.png)
MetaCPAN package popularity uses an independant indicator, the "++" (PlusPlus).


++ are sent by other CPAN authors.

Manipulation of PlusPlus score is possible but not cheap: it require creation of several spammy authors.

And creations of authors requires a [request](https://pause.perl.org/pause/query?ACTION=request_id) and [manual acceptance](https://www.nntp.perl.org/group/perl.modules/2024/11/msg105533.html) by CPAN admins.

## RiverJacking ![River](../media/starjacking/river.png)
The river score appears next to module name in several places:

![River score](../media/starjacking/riverscore.png)

River can be manipulated, by just making fake modules depends on the module.

Improving river score of a module is relatively cheap (possible with one single author with multiple modules).

In practice, it would only require to reference module as a dependency in downstream packages.

Example with a `Makefile.PL`:
```
use ExtUtils::MakeMaker;

my %WriteMakefileArgs = (
    NAME             => 'River::Jacking::Downstream',

    ...

    PREREQ_PM => {
        'River::Jacking'              => '0', # < HERE
    },

    ...
);

WriteMakefile(%WriteMakefileArgs);
```

## Conclusion
CPAN is not vulnerable to StarJacking, because VCS stars are not helping popularity of a module in (Meta)CPAN.

Manipulating popularity via other CPAN in-house indicators is possible but not always cheap.

The very social nature of CPAN (manual acceptance of new users, code reviews of new modules) makes it difficult overall to exploit.

## Resources 
- [StarJacking](https://checkmarx.com/blog/falling-stars/)
- [PyPI security](https://www.youtube.com/watch?v=ZvNuHKDyQXc)
- [PyPI details verification](https://docs.pypi.org/project_metadata/#verified-details)
- [PyPI trusted publishing](https://docs.pypi.org/trusted-publishers/)
