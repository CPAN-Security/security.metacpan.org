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

