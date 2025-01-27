# Notes on Open Source: Scenario Based Discussion

## Proposed Specifications

### Key Focus Areas

w.r.t. communication gaps and explore roles, I guess it would be good to address
timelines and expected response times for communication gaps and roles.

TimeZones are a major PITA and people can be on holiday.

For CPAN there are no rules on what to do on critical CVEs when maintainers can
temporary not be reached (illness, holiday, family business, whatever)

## Setting the Scene

I think that EU based open-source teams are a great idea. See later notes

## Open-Source Community Challenges

### Information Needed

In resource constraints and delays due to volunteer-driven contributions, it is
worth mentioning that in team-managed projects (CORE, toolchain,DBI, Mojolicious,
...) that no single team member is expected to have complete knowledge on all
focus areas in the project. The area that is vulnerable might require a certain
team member, which may or may not be available.

## Scenario-Based discussion

### Incident Day (Hours 3-6)

ENISA focuses on understanding the scope

On CPAN, we talk about the river concept. Up-river is CORE, which has huge impact
on every module on CPAN, downriver might have less impact.

A scope might be small initially, but when a release has many direct and/or
indirect dependencies, that scope might explode. (ExtUtils::MakeMaker,
Test::Simple, Moose, DBI, ...). As a consequence, you might have to deal with
many authors.

## Proposed Questions for Discussion

### Initial response

2.3 A process to set-up might involve a cross-product info-sharing workforce,
where e.g. Perl folk find the cause, and the Go people find the solution and the
python people write up the explanation (shuffle the languages to your preference)
The focus would be purely technical.
