# CRA Questions

> [!NOTE]
> Assumptions and confidence levels are the author's (Salve J. Nilsen, @sjn), as of 2024-02-27.

## Dependencies

* Does the CRA make demands about _all_ transitive dependencies, at any arbitrary depth? (Assumption: YES, 85%)
    - e.g. If a transitive dependency of a "product with digital components" the CRA applies to depends on something supplied by the OS packaging system (e.g. a cryptographic library like libopenssl), do we continue looking down the dependency rabbit-hole even further? (Assumption: YES, )
    - How about other types of dependencies?
        - Author (development environment)
        - Build (build dependencies & tooling)
        - Test (test/verification dependencies)
        - Runtime (plugin, execution or in-memory dependencies)

## CE Mark

* What does The CE mark _mean_ when it applies to software?
    * "I, the author, am conforming to EU law, including the CRA" (Assumption: YES, 85%)
    * Which EU laws is one expected to conform to, when applying a CE mark?
        * CRA (Assumption: YES, 99%)
        * NIS2 (Assumption: YES, 90%)
        * Fintech-specific laws (Assumption: YES, 40%)
        * ...
* What does the CE mark apply to?
    * A specific product with digital components, that is put on the EU market (Assumption: YES, 99%)
    * An Open Source software project that is a component for (Assumption: )
    * A specific software release (Assumption: YES)
    * A package or other artifact that is produced from a release (Assumption: YES)
        * If it is built during the packaging process
        * If it the packaging does _not_ include a build step
        * If the release is modified/patched before packaging
    * What happens if an upstream open source component author claims "Version 1.25.0 of my package Foo::Bar is conforms to the CRA, so I'll put the CE mark on it"?

## Liability

* What does the liability picture for someone who has to do a vulnerability assessment of a product that contains _thousands_ of Open Source components look like?
* To which extent can component distributors or authors "accept" some of the liability?

## Metadata

* What are the concrete demands for metadata required for liable parties to actually live up to the obligations set by the CRA?
    * To which extent these metadata have to be up-to-date and authoritative (e.g. if a component author changes it's license, what happens?)
