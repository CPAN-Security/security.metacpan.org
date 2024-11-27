# CPAN dependency confusion
## Rationale 
Take advantage of a wrongly configured setup that resolve to public module in place of expected private/local version, because of one of the following reasons:
- Local module is not installed at time of running CPAN client
- Public CPAN version is preferred to local
- Using a CPAN repository (proxy) that can be confused

This type of vulnerability is presented in [Dependency Confusion](https://medium.com/@alex.birsan/dependency-confusion-4a5d60fec610) by [Alex Birsan](https://medium.com/@alex.birsan)

## Background
"Dependency confusion" takes advantage of mixing (semi-)private modules with public CPAN modules.

In Perl ecosystem, it could be one or more of the following options:
- Using a "DarkPAN" along with CPAN
- Using a "GreyPAN" along with CPAN
- Mixing manual installs (`make install`, "blib install"...) along with CPAN

See [About the various PANs](https://www.olafalders.com/2019/02/19/about-the-various-pans/) for details about DarkPAN and GreyPAN.

An attacker can "claim" a public namespace, install a high version (to take precedence in index over a smaller local version) and wait for vulnerable setups to install (and execute) their newly uploaded module.

## General about CPAN dependency management
### The mirror versus the indexer
The notions of "mirror" and "indexer":
- "mirror" - where module tarballs are stored
- "indexer" - translate module to path and version

These notions are not always well differenciated and their meaning heavily depends the CPAN client. For instance, from a pool (urllist), `CPAN.pm` will use only one mirror for both index and download of modules. On the other hand, `cpanm` will use MetaDB as index in priority and mirrors to download, and these notions are well decoupled. 

Not all indexers are equals: 02packages only contains latest version of each module, making it [difficult to specify more complex constraints](https://github.com/miyagawa/Carmel/issues/55) (pinned or ranges).

### General characteristics about CPAN/PAUSE and installers
- Module installs are ([often](https://blogs.perl.org/users/shoichi_kaji1/2017/03/make-your-cpan-module-static-installable.html)) "dynamic" (= some dependencies are only known at install)
- Claiming namespace is case insensitive but index/install is case sensitive (important for TypoSquatting or confusions attacks based on modules/filenames collisions)

### Installer are not zealous
#### "leafs" vs "requirements"
CPAN installers treats differently a "leaf" versus a "requirement".

Specifying a module as a "leaf", e.g. `cpanm Requirement` is different from having it specified as a dependency (Makefile.PL/Build.PL, META.*, cpanfile...)

- When explicitely targetting to install `Requirement`, `cpanm` (and others) will install latest, upgrading the module if present
- When `Requirement` module is specified as a dependency, `cpanm` will not upgrade module if installed version satisfies the constraints

Installing with `cpanm --installdeps .` will not install anything:
1. Requirement@0.01
2. cpanm --installdeps .
3. Requirement@0.01

But `cpanm Requirement` will update `Requirement`:
1. Requirement@0.01
2. cpanm Requirement
3. Requirement@0.02

Note: This is not specific to CPAN ecosystem, for instance `pip` and `gem` are behaving the same.

#### `--skip-satisfied`
But `cpanm Requirement` will update `Requirement`:
1. Requirement@0.01
2. cpanm --skip-satisfied Requirement
3. Requirement@0.01
 
## Simulations
### Setup
For these tests, I'm recreating a setup with mix of private and public modules.

As a commodity, it is presented as a `cpanfile`:
```
requires 'PrivateAndPublicGreaterCPAN', '0';
requires 'Private', '0';
requires 'Public', '0';
requires 'PrivateAndPublicGreaterLocal', '0';
```

It simulates a complex setup where installer has to install sometimes local requirements and sometimes remote ones. 

Specifying requirements in Makefile.PL, Build.PL or META.json/META.yml achieves the same and was used in some cases (e.g. CPAN/CPANPLUS)

On DarkPAN:
```
PrivateAndPublicGreaterCPAN@0.03
Private@0.01
PrivateAndPublicGreaterLocal@0.02
```

On CPAN:
```
PrivateAndPublicGreaterCPAN@0.04
Public@0.12
PrivateAndPublicGreaterLocal@0.01
```

`Private` is only present on DarkPAN, `Public` is only present on CPAN.

`PrivateAndPublicGreaterCPAN` and `PrivateAndPublicGreaterLocal` are requirements that can be "confused" (= if install ends up with `PrivateAndPublicGreaterCPAN@0.04` and/or `PrivateAndPublicGreaterLocal@0.02`) 

GreyPAN/DarkPAN was simulated with the following tools:
- [pinto](https://metacpan.org/dist/Pinto) either targetted via HTTP `http://0.0.0.0:8000/` or `file:///data/darkpan` for `cpanm`, `cpm`, `carton`, `carmel` and `cpan`
- [CPAN::Mini](https://metacpan.org/dist/CPAN-Mini) for `cpanplus` (cpanplus index fetch incompatible with pinto)
- [StratoPAN](https://stratopan.com/)/[JFrog Artifactory](https://jfrog.com/artifactory/) for CPAN artifact manager proxy

## Dependency confusion when local is inexistent
### Unsafe
- Specifying private requirements in Makefile.PL, Build.PL, META.* or cpanfile/cpmfile is unsafe. Doing manual installs (via EUMM/MB or `cpanm tarball`) then relying on requirements being already satisfied (and CPAN client not being "zealous") to not install anything public is risky, to say the less.

### Safe
- Do not specify private requirements in Makefile.PL, Build.PL, META.* or cpanfile/cpmfile. Specifying requirements is technically not required for runtime. Suboptimal because it makes dependencies implicit and shift right the verification of requirements.
- Use reserved namespaces (`_Underscore::Trick` or `UN_DESCORE::Trick`) that can not resolve to public modules

Also `Local::*` but as of today only reserved "by convention", see [Do not index Local::* (nor Local)](https://github.com/andk/pause/pull/541)

## Dependency version confusion between PANs
### Unsafe
#### cpanm --mirror
- It keeps resolving first via public indexer (has no information about DarkPAN versions)
- It only "appends" so beware mirrors installed first via `PERL_CPANM_OPT`
- Order is important

e.g.:
- Problem with "appends": `PERL_CPANM_OPT="--mirror https://cpan.org" cpanm --mirror-only --mirror http://darkpan.local --installdeps .`
- Problem with "indexer": `cpanm --mirror http://darkpan.local --mirror https://cpan.org --installdeps .`
- Problem with "ordering": `cpanm --mirror-only --mirror https://cpan.org --mirror http://darkpan.local --installdeps .`

#### cpanfile/cpanm
- `mirror ""` and `mirror =>` directives from cpanfile are (silently) ignored by cpanm (!)

```
# WRONG with cpanm

mirror "https://darkpan.local/";

requires 'PublicAndPrivateGreaterCPAN', '0',
  mirror => 'https://darkpan.local/',
  dist => 'USER/PublicAndPrivateGreaterCPAN-0.03.tar.gz';
```

#### cpanfile/carton
- per req `mirror =>` alone (without `dist =>`) is silently ignored by carton
- per file `mirror ""` is not used for index by carton
- `PERL_CARTON_MIRROR="https://pause.local/" carton install` - safe but error prone (mirror is not explicited in requirements file)

#### cpanfile/carmel
- carmel is "experimental"
- per req `mirror =>` / `dist =>` is [not supported](https://github.com/miyagawa/Carmel/issues/72)
- per file `mirror ""` feature is [not stable](https://github.com/miyagawa/Carmel/issues/55) and behaviour [not decided yet](https://github.com/miyagawa/Carmel/pull/92)

### Safe
- `cpanm --from` - but requires full sync DarkPAN or to differenciate private and public cpanfile(s)
- `unset PERL_CPANM_OPT cpanm --mirror-only --mirror darkpan --mirror cpan` - beware order of mirrors
- `unset PERL_CPANM_OPT cpanm --mirror-index file:///data/02packages --mirror darkpan --mirror cpan` - beware order of mirrors
- `unset PERL_CPANM_OPT cpanm --cascade-search --mirror-index file:///data/02packages --mirror darkpan --mirror cpan` - beware order of mirrors
- `cpm --no-default-resolvers --resolver darkpan --resolver cpan` 
- carton/cpanfile `mirror =>` AND `dist =>` - pinned version and storage
- carton/cpanfile `url =>` - pinned url
- CPAN urllist (but with `pushy_https` disabled) - use index of first mirror, fallback for download
- CPANPLUS `hosts` - use index of first mirror, fallback for download

Carton pinning with `url =>`:
```
requires 'Private', '0',
  url => 'https://darkpan.local/authors/id/U/US/USER/Private-0.01.tar.gz';
```

## Deployment and lockfiles
Lockfiles mostly refers to *deployment* phase that is out of scope of this document.

`carton --deployment` and  `carton --cached` are not vulnerable, because the use dumped/recreated local index with local artefacts.

## CPAN Artifacts Repositories
### JFrog Artifactory
JFrog is known to be vulnerable (internally) to this dependency confusion attacks with other ecosystems.

Since JFrog Artifactory does not support CPAN as first class citizen but only "proxy" CPAN (as in "HTTP proxy"), CPAN is not vulnerable via this artifact repository manager.

### StratoPAN
Not affected, not doing fallback on public CPAN.

## Mitigations
Beyond technical CPAN client/options recommendations exposed earlier, sharing some more "shift left" guards and explicit security advices.

### PAUSE operational model 
The way CPAN and PAUSE work, and the very "social" nature of this ecosystem makes it very difficult to attack CPAN via dependency confusions. 

1. New authors don't get immediate account but are approved by an admin. With a priori approval like this, automatic creation of fake accounts is hence not possible.
2. New uploads are not following an a priori control but publicly reviewed. Malware code can be spotted and claiming namespace with bad intention would be very likely reported rapidly. 

In this context, it sounds difficult for an attacker/malware module to go unnoticed and exploit dependency confusion.

### Isolate private requirements
- Use different files for private and public requirements (`cpanfile.private` / `cpanfile`)
- Do not specify private requirements in Makefile.PL, Build.PL, META.* or cpanfile/cpmfile

Both previous solutions are not optimal

### Naming
#### Scoping like NPM
Remediation for NPM ecosystem mentions [scoping](https://docs.npmjs.com/threats-and-mitigations#by-typosquatting--dependency-confusion) (naming packages like `@my-company/my-module`).
A scope guarantees [protection of all names under it](https://docs.npmjs.com/package-scope-access-level-and-visibility) but also [can be tied to a registry](https://docs.npmjs.com/cli/v7/using-npm/scope#associating-a-scope-with-a-registry).
 
CPAN operating model works differently and has no such scopes. Technically, being the first person to publish module offers FIRST COME permissions on the module name. Though it does not recusively protect all names under it, it effectively protects the fully qualified name forever. 

Doing this ("placeholding") for private modules is an option, but it would be very unwise and very egoist to do that, effectively polluting CPAN namespace only for the sake of personal needs.
Beyond these considerations, what you need is only to publish once (a very small version that never will interfer with your local versioning) to claim the namespace. Remember, it's not a scope. Claiming `Module` does not protect `Module::Foo` nor `Module::Bar`.

The module [install](https://metacpan.org/pod/install) somewhat fills this use case, like gem [bundle](https://rubygems.org/gems/bundle) in rubygems.

#### Reserved namespaces
Use reserved namespaces that can't resolve to public things:
- `_Underscore::Trick` or `UN_DESCORE::Trick`
- `Local::*` but as of today only reserved "by convention", see [Do not index Local::* (nor Local)](https://github.com/andk/pause/pull/541)

From [PAUSE Naming Modules - Local::](https://pause.perl.org/pause/query?ACTION=pause_namingmodules#Local) and [The Perl Module Library (perlmodlib)](https://perldoc.perl.org/perlmodlib#Guidelines-for-Module-Creation)

## Resources 
- [Hacking with gems](https://www.youtube.com/watch?v=zEBReauO-vg) (2013)
- [Dependency Confusion](https://medium.com/@alex.birsan/dependency-confusion-4a5d60fec610) (2021)
- [Distribution Confusion in PyPi](https://stiankri.substack.com/p/distribution-confusion-in-pypi) (2023)
- [cpanm](https://metacpan.org/pod/App::cpanminus)
- [cpm](https://metacpan.org/pod/App::cpm)
- [CPANPLUS](https://metacpan.org/dist/CPANPLUS) 
- [CPAN](https://metacpan.org/pod/CPAN)
- [Carton](https://metacpan.org/dist/Carton)
- [Carmel](https://metacpan.org/dist/Carmel)
- [Module::CPANfile](https://metacpan.org/pod/Module::CPANfile)
- [CPAN::Meta::Spec](https://metacpan.org/pod/CPAN::Meta::Spec)
- [Pinto](https://metacpan.org/dist/Pinto/view/bin/pinto)
- [CPAN::Mirror::Tiny](https://metacpan.org/release/SKAJI/CPAN-Mirror-Tiny-0.32/view/lib/CPAN/Mirror/Tiny.pm)
- [PerlRocks](https://github.com/gugod/perlrocks)
- [Carl](https://github.com/skaji/Carl)
- [anton](https://github.com/tokuhirom/anton)
- [x_static_install](https://blogs.perl.org/users/shoichi_kaji1/2017/03/make-your-cpan-module-static-installable.html)
- [CPAN always tries file:// first](https://metacpan.org/pod/CPAN#The-urllist-parameter-has-CD-ROM-support)
- [CPANPLUS Can I use local mirror](https://perl.mines-albi.fr/perl5.6.1/site_perl/5.6.1/CPANPLUS/FAQ.html#can%20i%20use%20a%20local%20mirror%20(such%20as%20a%20cd),%20but%20fall%20back%20to%20a%20public%20mirror%20if%20my%20files%20are%20out%20of%20date)
- [CPAN::Mirror::Tiny - How to install modules from DarkPAN](https://metacpan.org/pod/CPAN::Mirror::Tiny#How-can-I-install-modules-in-my-DarkPAN-with-cpanm-%2F-cpm%3F)
- [Addressing CPAN vulnerabilities related to checksums](https://blogs.perl.org/users/neilb/2021/11/addressing-cpan-vulnerabilities-related-to-checksums.html)
- [Signature Verification Vulnerabilities in CPAN.pm, cpanminus and CPAN::Checksums](https://blog.hackeriet.no/cpan-signature-verification-vulnerabilities/)
- [Article about minicpan](http://www.stonehenge.com/merlyn/LinuxMag/col42.html)

