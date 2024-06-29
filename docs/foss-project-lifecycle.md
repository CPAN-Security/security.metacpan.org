----

## Open Source project life-cycle stages

1. ACTIVE – The project is maintained (default state)
  * (bus factor is more than 0)
  * (bus factor does not need to change)
1. NEEDHELP – The project is understaffed, and requires additional co-maintainers for sustainable and continued development
  * (bus factor is more than 0)
  * (bus factor is too low)
1. HANDOFF – The project owner is looking for someone to take over the project
  * (bus factor is 1)
  * (bus factor is about to reduce to 0)
1. ADOPTME – The project is abandoned, or the owner has been confirmed to be unresponsive, and therefore available for adoption
  * (bus factor is 0)
1. NOXFER – The project is prevented from being transferred to new owners
  * (bus factor is not relevant)
1. CUSTODY – This project is under custodianship
  * (bus factor is 0)
  * (project may needs a trusted maintainer)
1. DONE – The project is considered "Done", and while it is maintained, no further development is needed or expected
  * (bus factor is 1 or higher)
1. DEPRECATED – The project owner recommends that this project is not to be used
  * (bus factor is 0)
1. UNMAINTAINED – This project is not actively maintained
  * (bus factor is 1 or higher)
1. CASUAL – This project is only maintained on a casual basis
  * (bus factor is 1 or higher)
1. NEEDFUNDING – This project needs funding
  * (bus factor is 1 or higher)
  * (workload is unsustainable with only a volunteer-level commitment)
1. NEEDSUPPORT – This project needs non-funding support
  * (bus factor is 1 or higher)
  * (project growth and sustainability is hindered by lack of non-code contributions)


## Other project states/claims

1. Intended for commercial use (EU CRA signal for OSS Stewards)
1. Registered OSS Steward


### For consideration

1. FORK – This project claims to be an API-compatible fork of another project

```mermaid
graph TB
    %% Life-cycle stages
```


