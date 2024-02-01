# Thoughts around NIS2 and CRA

- Redirect Liability for Open Source software towards separate companies (Send the devs to a separate LLC)
- Copyleft (reciprocal) licenses have a greater chance of fostering a culture for sending improvements upstream
- Non-copyleft (non-reciprocal) software with changes may be more expensive to fix internally, than if you use copyleft software and make an effort to send your changes upstream.
- With the CE mark introduction, FOSS developers may get a proper income stream for their software. "No, I will not put a CE mark on the release, unless you pay for the audit and the liability transfer."


# Thoughts around SBOM

- The notion of "lifecycles" need to _explicitly_ include Open Source ecosystem patterns
- From an open source ("volunteer-developed") perspective, it is _not_ OK to use wildly different terminology to describe the same things, and to use the same terminology to describe different things across the interop landscape. This means that a common glossary/ontology
- Open Source ecosystems have a couple packaging patterns that need to be represented correctly
    - without upstream dependencies
    - with upstream dependencies that are resolved at (post publishing/republishing) build time, e.g. by a developer
    - with upstream dependencies that are resolved at (post publishing, pre republishing) repackaging time, e.g. by a packager or re-packager
    - with upstream dependencies that are resolved at (pre publishing) packaging time, and therefore included/embedded in the published package, e.g. by an open source author.
    - with with upstream dependencies that are resolved dynamically at runtime, e.g. a framework auto-updating plugins.
- SBOM Perspective is skewed, and too business/product centric.
    - Content modifications (applied security or interop patches)
    - Dependency modifications (applied security dependency fixes)
    - Metadata modifications (added packaging step metadata, or corrections)

- Data- and process-centric perspectives are not user friendly
    - instead, use tems that are descriptive from a role-centric perspective

- Open Source software is "second-party software". "First-party software" is "my software". "Second-party software" is "our software", "Third-party software" is "their software"
    - Second-party software is a major source of "unknown" dependencies today
    - Much of this comes from a combination of institutional upgrade fear
- With >80% of all software depending on volunteer efforts in Open Source communities, it's much more important to do things that makes it easier for these to participate
    - ISO and ECMA standards aren't that useful (they are for another audience)
    - Ease of implemenation and technical elegance ("fun stuff") is much more important!
    - Double work is wasted work. Who wants two standards for SBOMs? Whatever is blocking these communities from converging, MUST be removed. Any reasons for this blockage is insignificant against the need for lowering the bar of participation for volunteer communities out there.
        - This probably with establishing a comprehensive ontology (common terminology) for the whole SBOM field, and have each party commit to implement it in their standards.
    - Open Source ecosystems must be shown – in obvious terms – that they are a core component for any software lifecycle that SBOMs intend to be used in. [Picture of a "life cycle" from CDX]
        - From a roles perspective, these life cycles must include _all_ activities that are done in Open Source ecosystems: Owner, Author, Custodian, Packager, Patcher, Curator, Publisher, Developer, Tester, Builder, Deployer, SecOps, Consumer, and Auditor.
    - While having SBOMs for documenting dependency resolution, there is also the other side of this coin – way to specify dependencies! Many ecosystems are myopic in this regard too.
        - Using Package URLs for specifying service dependencies might be a step forward here? E.g. <pkg:service/ntp>, <pkg:service/smtp> can be enough for an OS provider to do service discovery and communicate it's resolution for use in a software build or deployment SBOM


## Needed

1. A plan for converging and eventually merging SBOM standards
    1.  ...or at minimum, a common standard taxonomy, to make interoperability easier.
    2.  ...including instructions on what fields are intended to be used for, and how to disambiguate between them when there is medt for it
2. Open Source Software lifecycles need to be featured much more prominently, do that businesses that are unfamiliar with it (or suffer from a limited business-centric perspective of it) may get a clear indication of what the need to learn function as constructive participants when interacting with open source developers.
    1. Ref. CycloneDX' "Authoritative guide to SBOM" 
3. Open source components are not "third party components" in the traditional "product-centric" sense. Instead, they need to be treated and communicated as living projects, where community resources and channels are presented as core features on par with project name and version number.
4. Project naming is not solved
    1. Purls are useful for specifying resolved dependencies
    2. Purls are less useful for specifying required dependencies, since the same component may be found on lots of different ecosystems
    3. Specifying per-ecosystem requirements can quickly become tedious! This is especially true for platform-agnostic software
5. To ensure authoritative component metadata is available in an ecosystem independent manner, we need a standard way to look for SBOMs. Filesystem location would be ideal, since we cannot assume network connectivity during a build process.
    1. Also, a common filesystem directory schema for storing, reusing, verifying, and referring to SBOM objects recursively, so component reuse doesn't introduce metadata duplication
  
SBOM communities MUST start educating users about open source ecosystems too

Ecosystem developers don't see the point in working on this


## How are transitive dependencies introduced?

* Include after publish (Download)
* Embed before publish
* Depend (Use & resolve)
* Patch (Modify)
* Assumed present (Implied)

## Why are dependencies introduced?

* Use (add functionality or features)
* Extend (add and modify functionality)
* Transpose to a new language ecosystem (FFI)
* Build, compile, link
* Test, check or verify
* Package, re-package, patch
* Sign
* Document, translate
* Manage, support with Dev tasks
* Publish

## What can depended upon?

* Code
* Services (Cron, NTP, SMTP)
* Runtime environments (container, virtual machines)
* System resources (ram, disk, inodes, threads, processes, hw devices)

# Presentation

## Cover Page / Intro
## About me
## Why ask if "SBOMs can become a first class citizen in Open Source Ecosystems?"
Because...
Software composition analysis
Vulnerability detection
...becomes easier with up-to-date authoritative information
## Example: CPAN
## CPAN's upstreams
## The river of CPAN
## CPAN's downstreams
## Who manages this?
## Open Source Volunteers
Not a "third party" but a SECOND party!
What agreement? Check your open source license!
They are, in fact, your unpaid colleagues
## Reactions
"Freeloader says what?"
"What's in it for me?"
"This is not my problem"
"We already keep track of this, why do we need another way?"
"Can this be used for creating reproducible builds?"
## What do these volunteers need?
Motivation, Engagement, O(fun)
Context and reasons
Something that is a joy to work with
Targeted documentation
If it's not fun it interesting: Money
## An Open Source perspective
Please do not waste Volunteer time
Please do not assume they will come just because you made something
## An Ecosystem perspective
Please do not take them for granted
## Standards

## Interoperability
Universal package identification - YES
Universal dependency resolution - YES
SBOM standards convergence - NOW
## Coordination

## Money

## Can SBOM become a first class citizen in Open Source Ecosystems?
