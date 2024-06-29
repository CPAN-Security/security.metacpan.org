----

## Open Source project life-cycle stages

1. (default) – The project is maintained (bus factor is not 0 and does not need to change)
1. NEEDHELP – The project is understaffed, and requires additional co-maintainers for sustainable and continued development (bus factor is not 0, but too low)
1. HANDOFF – The project owner is looking for someone to take over the project (bus factor is 1 and about to become 0)
1. ADOPTME – The project is abandoned, or the owner has been confirmed to be unresponsive, so the project is now available for adoption (bus factor is 0)
1. NOXFER – The project is prevented from being transferred to new owners (bus factor is not relevant)
1. CUSTODY – This project is under custodianship (bus factor is 0 and may benefit from a new maintainer)
1. DONE – The project is considered "Done", and while it is maintained, no further development is needed or expected (bus factor is 1 or higher)
1. DEPRECATED – The project owner recommends that this project is not to be used (bus factor is 0)
1. UNMAINTAINED – This project is not actively maintained (bus factor is 1 or higher)
1. CASUAL – This project is only maintained on a casual basis (bus factor is 1 or higher)


### For consideration

1. FORK – This project claims to be an API-compatible fork of another project


## Are you… a Manufacturer, Steward or Author?

```mermaid
graph TB
    start-here(Start here) --> involved{Involved<br>with OSS<br>products?}
    involved  -->|No| not-relevant-for-you(This chart isn't<br>relevant for you)
    involved -->|Yes| contributing{Contributing<br>unpaid to OSS?}
    contributing  -->|No| monetised{Monetizing<br>the product?}
    contributing -->|Yes| cra-is-out-of-scope(CRA is out-of-scope)
    monetised -->|Yes| cra-manufacturer(CRA Manufacturer)
    monetised -->|No| is-legal-entity{legal person,<br> but not a natural<br>person?}
    is-legal-entity -->|Yes| intended-commercial-use{Is product<br>intended for<br>commerial use?}
    is-legal-entity -->|No| cra-is-out-of-scope
    intended-commercial-use -->|No| cra-is-out-of-scope
    intended-commercial-use -->|Yes| product-supporter{Providing<br>support for OSS<br>products?}
    product-supporter -->|Yes| cra-oss-steward(CRA Open-Source Steward)
    product-supporter -->|No| cra-is-out-of-scope

    %% Based on the flowchart made by Maarten Aertsen (NLNetLabs) found at

    %% https://blog.nlnetlabs.nl/what-i-learned-in-brussels-the-cyber-resilience-act/

    %% Original flowchart © Maarten Aertsen <maarten@nlnetlabs.nl>
    %% License: CC0 1.0 Universal
    %% Adapted to Mermaid and modified by Salve J. Nilsen <sjn@oslo.pm>
```


