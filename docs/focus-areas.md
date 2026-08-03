---
author: tux
toc: true
layout: single
---
# CPANSec focus areas

The three major areas are

 * Law
 * Information-gathering
 * Tooling & reporting

This document tries to create a map of where people may find themselves
best-fit to help.

## Law

Gather knowledge on laws and regulations. Find out what the prerequisites
are for our own goals and present that piece-meal to the rest of the group
either in layman worded documentation, action lists, or modules.

One of the focus-points in this part is how to set up an SBOM, what to put
in there, what not to put in there and huw to structure it.

## Information-gathering

Find out where vital information lives and combine that into information
sources that can be used in tooling. Sources are e.g. CVE databases, OS
distribution vulnerability mailing list, -communities, and -websites.

One of the focus points in this part is generating a CPANSA feed where all
known vulnerabilities that touch (modules on) CPAN or CORE, so modules
like Test::CVE can use it in analysing distributions.

## Tooling & reporting

Anything that will help end-users be aware of possible vulnerabilities.
The scope is *not* to ship a bag of tools that actually fix issues, but
report possible weeknesses and how - if possible - the end-user themselves
could take action to fix their distribution.

Tooling will also be required in SBOM generation

## Map
```
 +-------------------------+-------------------------+-------------------------+
 | Law                     | Information             | Reporting               |
 +-------------------------+-------------------------+-------------------------+
 +-----------------------------------------------------------------------------+
 | Networking with people                                                      |
 +-----------------------------------------------------------------------------+
      +--------------------+                         +---------+
      | SBOM               |                         | SBOM    |
      +--------------------+                         +---------+
                         +---------------------------------------------------+
                         | CVE, NVD, OSV, RHSA, ...                          |
                         +---------------------------------------------------+
                +----------------------------+
                | CNA                        |
                +----------------------------+
                                   +---------------------------------+
                                   | CPANSA                          |
                                   +---------------------------------+
```
