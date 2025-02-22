# Thoughts around NIS2, CRA and PLD

- Redirect Liability for Open Source software towards separate companies (Send the devs to a separate LLC)
- Copyleft (reciprocal) licenses have a greater chance of fostering a culture for sending improvements upstream
- Non-copyleft (non-reciprocal) software with changes may be more expensive to fix internally, than if you use copyleft software and make an effort to send your changes upstream.
- With the CE mark introduction, FOSS developers may get a proper income stream for their software. "No, I will not put a CE mark on the release, unless you pay for the audit and the liability transfer."

- With the requirements from these laws, we should be able to make a few assumptions and predict the following timeline
    - The laws will force institutions to get a better-converging-on-complete picture of their software stacks, and their Open Source dependencies
        - If they don't do this, they risk fines due to requirements in the NIS2 Directive and the Cyber Resilience Act
    - The same institutions will have to make their software stacks trivially updatable (e.g. roll them into a CI/CD pipeline)
        - If they don't make it easier to apply security updates, they risk fines due to the Product Liability Directive
    - With these two assumptions in place, we can assume the following consequences
        - Demands for backwards compatibility will be reduced
        - Any ecosystems that don't make it easy for users to implement these things, risk abandonment
        - Demands for interoperable tooling will increase
        - Demands for secure supply-chain infrastructure will increase
        - Demands for Unambiguous software identification will increase
        - Demands for 
    - 


# Thoughts around SBOM

- Any notion of "life-cycles" need to _explicitly_ include Open Source ecosystem patterns
- From an open source ("volunteer-developed") perspective, it is _not_ OK to use wildly different terminology to describe the same things, and to use the same terminology to describe different things across the interoperability landscape. This means that a common glossary/ontology is needed.
- Open Source ecosystems have a couple packaging patterns that need to be represented correctly
    - without upstream dependencies
    - with upstream dependencies that are resolved at (post publishing/republishing) build time, e.g. by a developer
    - with upstream dependencies that are resolved at (post publishing, pre republishing) repackaging time, e.g. by a packager or re-packager
    - with upstream dependencies that are resolved at (pre publishing) packaging time, and therefore included/embedded in the published package, e.g. by an open source author.
    - with with upstream dependencies that are resolved dynamically at runtime, e.g. a auto-updating application plugins.
- SBOM Perspective is skewed, and too business/product-centric.
    - Content modifications (applied security or interoperability patches)
    - Dependency modifications (applied security dependency fixes)
    - Metadata modifications (added packaging step metadata, or corrections)

- Data- and process-centric perspectives are not user friendly
    - instead, use terms that are descriptive from a role-centric perspective

- Open Source software is "second-party software". "First-party software" is "my software". "Second-party software" is "our software", "Third-party software" is "their software"
    - Second-party software is a major source of "unknown" dependencies today
    - Much of this comes from a combination of institutional upgrade fear
- With >80% of all software depending on volunteer efforts in Open Source communities, it's much more important to do things that makes it easier for these to participate
    - ISO and ECMA standards aren't that useful at this time. These standards are still under development, so any standardization at this time is just song-and-dance for a corporate/low-competence audience.
    - Ease of implementation and technical elegance ("fun stuff") is much more important!
    - Double work is wasted work. Who wants two-tree standards for SBOMs? Whatever is blocking these communities from converging, MUST be removed. Any reasons for this blockage is insignificant against the need for lowering the bar of participation for volunteer communities out there.
        - This probably with establishing a comprehensive ontology (common terminology) for the whole SBOM field, and have each party commit to implement it in their standards.
    - Open Source ecosystems must be shown – in obvious terms – that they are a core component for any software life-cycle that SBOMs intend to be used in. [Picture of a "life cycle" from CDX]
        - From a roles perspective, these life cycles must include _all_ activities that are done in Open Source ecosystems: Owner, Author, Custodian, Packager, Patcher, Curator, Publisher, Developer, Tester, Builder, Deployer, SecOps, Consumer, and Auditor.
    - While having SBOMs for documenting dependency resolution, there is also the other side of this coin – way to specify dependencies! Many ecosystems are myopic in this regard too.
        - Using Package URLs for specifying service dependencies might be a step forward here? E.g. <pkg:service/ntp>, <pkg:service/smtp> can be enough for an OS provider to do service discovery and communicate it's resolution for use in a software build or deployment SBOM

## Needed

1. A plan for converging and eventually merging SBOM standards
    1.  ...or at minimum, a common standard taxonomy, to make interoperability easier.
    2.  ...including instructions on what fields are intended to be used for, and how to disambiguate between them when there is need for it
2. Open Source Software life-cycles need to be featured much more prominently, do that businesses that are unfamiliar with it (or suffer from a limited business-centric perspective of it) may get a clear indication of what the need to learn function as constructive participants when interacting with open source developers.
    1. Ref. CycloneDX' "Authoritative guide to SBOM" 
3. Open source components are not "third party components" in the traditional "product-centric" sense. Instead, they need to be treated and communicated as living projects, where community resources and channels are presented as core features on par with project name and version number.
4. Project naming is not solved
    1. Purls are useful for specifying resolved dependencies
    2. Purls are less useful for specifying required dependencies, since the same component may be found on lots of different ecosystems
    3. Specifying per-ecosystem requirements can quickly become tedious! This is especially true for platform-agnostic software
5. To ensure authoritative component metadata is available in an ecosystem independent manner, we need a standard way to look for SBOMs. File-system location would be ideal, since we cannot assume network connectivity during a build process.
    1. Also, a common file-system directory schema for storing, reusing, verifying, and referring to SBOM objects recursively, so component reuse doesn't introduce metadata duplication
  
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
* System resources (ram, disk, inodes, threads, processes, hw devices, networking)

# Presentation

## Cover Page / Intro
## About me
## Why ask if "SBOMs can become a first class citizen in Open Source Ecosystems?"
Because...
Software composition analysis
Vulnerability detection
...becomes easier with up-to-date authoritative information
- End-to-end overview of provenance
- Reduce false positives of downstream tooling by making authoritative information available throughout each link in the supply chain
- Help create actionable information that takes Open Source communities into account
- Open Source is for enabling people who care
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



# Tobie Langel's CRA Steward TODO

## General topics

- CRA reading group
- Building support documentation (glossary, collecting references, etc.)
- How to ensure effective participation in the EU standardization process
- How to provide input to the EU Commission in general (and about product categorisation in particular)
- CRA impact on Open Source Stewards / foundations
- CRA impact on open source consumers (SMEs / enterprise / OSPOs)
- CRA impact on single-vendor open source

## Technical topics

- Standards for identifiers (CPEs), version numbers, end-of-live status & dates, referencing (transitive) dependencies, etc
- Standards for releases, recall, EOL
- Secure by design
- Open source supply chain security
- Vulnerability handling
- Software lifecycle; including post EOL vulnerabilities

# Salve's additions

## General topics

- CRA reading group
  - Suggestion: CPANSec's reading list: https://security.metacpan.org/docs/readinglist.html
- Building support documentation (glossary, collecting references, etc.)
  - Suggestion: CPANSec's glossary: https://security.metacpan.org/docs/glossary.html

- CRA impact on Open Source Stewards / foundations
  - Question: To what extent is "code-hosting" a requirement? The CRA's formulation seems to be somewhat allowing of different models of operation; And since the CPAN predates the Perl Foundation by several years (and has always been operating independently), I'm wondering if the "code-hosting" requirement for this forum is a bit too strict...

- Addition: Fully and separately enumerate CRA impact on different entities having roles throughout the supply-chain; e.g. Language ecosystem providers; OS packaging providers; Container registries;
- Addition: Clarify to which extent the "Importer" role in CRA applies to FOSS supply-chain entities
- Addition: Clarify to which extent the "Distributor" role in the CRA applies to FOSS supply-chain entities
- Addition: Clarify how and which of the 40 EU standardization bodies / processes affect OSS Stewards
- Addition: Create an overview of existing communities that have created (or are in the process of creating) relevant standards, resources or guides.

## Technical topics

- Addition: How to ensure FOSS project sustainability information becomes a requirement, and is communicated throughout the supply-chain


## Introducing SBOMs into the supply chain

- Wanted: standardized locations for SBOMs (local/user/system/service path, or a URL to a TEA service)
- Regime: SBOM fragments composition. "Let the end user assemble everything from what they are provided"
  - Our task: Help contributors provide their metadata
    - Help Maintainers & Manufacturers
    - Help Language ecosystems
    - Help Package ecosystems
    - Help Stewards
- Needed: new "native" fields
  - List of new fields that are *required* to be "inlined" into existing metadata regime
  - A standard way to specify associated "Source SBOM" files that are included in a CPAN distro provided by the Maintainer (or upstream Manufacturer)
    - Manufacturer fields (CRA)
    - Maintainer fields (CRA)
  - A standard way to specify associated "Ecosystem SBOM" files that are provided by the ecosystem
    - SBOM download location
    - Assigned Open Source Steward (CRA)
    - Due Diligence Attestation (CRA)
  - A standard way to
- Needed: ways to "complete" the CPAN corner of the dependency graph
  - Specify out-of-ecosystem dependencies
  - Specify "vendored" dependencies
  - Specify service dependencies
  - Specify requirements to help downstream packagers map these onto their own ecosystem
- Needed: ways to help verify is an installation is complete, not tampered with, and does not contain unexpected output
  - Introduce hashes to package manifests & lockfiles
- Needed: SBOM recommendations/standardization
  - Standardized location to help with project/user/system/service level discovery of SBOMs
  - Guidelines on how to perform SBOM fragments composition


