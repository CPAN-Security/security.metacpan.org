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

