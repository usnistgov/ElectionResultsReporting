# Voting - Election Results Reporting CDF

## Specifications

- [Version 1](https://github.com/usnistgov/ElectionResultsReporting/tree/version1)
- [Version 2](https://github.com/usnistgov/ElectionResultsReporting/tree/version2)

## Voting - Election Results Reporting CDF Version 1.0 Specification

This directory contains the NIST SP 1500-100 Version 1.0 election results reporting common data format (CDF) specification and associated files that are being created by NIST and collaborators. Version 1.0 is stable and has been used in 2016 and later elections, both in the U.S. and internationally.  Version 2 of the specification is underway; see the version2 branch of this repository.

A PDF of the version 1.0 specification is available in this repository.  An HTML version is being prepared at  [https://pages.nist.gov/ElectionResultsReporting/](https://pages.nist.gov/ElectionResultsReporting/).  Google has also created a a very informative documentation site for this specification, located at:

[https://developers.google.com/elections-data/reference/](https://developers.google.com/elections-data/reference/)

The SP 1500-100 version 1.0 specification is comprehensive and detailed in its coverage of election results-related data and at the same time very flexible, able to accommodate election scenarios used throughout the United States.  It contains a UML (Unified Modeling Language) model, a derived XML (eXtensible Markup Language) schema, usage information and guidance, and background information.  Version 2.0 of this specification will expand on this by including support for JSON (JavaScript Object Notation).

The specification supports three different election scenarios:


1. Pre-election.  The period prior to an election, for reporting pre-election data from a jurisdiction.


2. Election.  The period(s) when voting is being conducted and election results reports are being produced.  The reports could include aggregated results data or more detailed, precinct-level reporting, depending on the capabilities of the reporting jurisdiction.


3. Post-election.  The period after the close of polls when more detailed election results reports are produced with options for precinct reporting, type of ballot, and type of device.


The XML schema associated with this specification is derived from a UML model that defines the types, structure, and interrelationships of geopolitical geography across the U.S. This model was designed to accommodate multiple types of contests and their many variations, and to provide the capability to report on these contests from higher aggregate levels down to very fine levels of detail, including:

- Reporting by precinct and splits of precincts;

- Reporting by ballot type, e.g., absentee, election day; and

- Reporting by device type and specific voting device.


Please contact [John P. Wack](mailto:john.wack@nist.gov) for questions and more information.

