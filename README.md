# Voting - Election Results Reporting CDF Specifications

This repository contains the NIST Special Publication 1500-100 Version 1.0 and Version 2.0 election results reporting common data format (CDF) specifications and associated JSON and XML schemas and other files that are being created by NIST and collaborators. Version 1.0 supports XML and has been used both in the U.S. and internationally.  Version 2.0 was created to improve the usability of the specification, to add additional data items, and to support JSON.  The version 2.0 specification is complete and awaiting final publishing by NIST.

The specifications are located as follows:

- [Version 1](https://github.com/usnistgov/ElectionResultsReporting/tree/version1)
- [Version 2](https://github.com/usnistgov/ElectionResultsReporting/tree/version2)

An HTML version is being developed at https://pages.nist.gov/ElectionResultsReporting/. Google has also created a a very informative documentation site, located at:

[https://developers.google.com/elections-data/reference/](https://developers.google.com/elections-data/reference/)

Both versions of the specification support the following election scenarios:

1. Pre-election.  The period prior to an election, for reporting pre-election data from a jurisdiction.


2. Election.  The period(s) when voting is being conducted and election results reports are being produced.  The reports could include aggregated results data or more detailed, precinct-level reporting, depending on the capabilities of the reporting jurisdiction.


3. Post-election.  The period after the close of polls when more detailed election results reports are produced with options for precinct reporting, type of ballot, and type of device.


The JSON and XML schemas associated with this specification are derived from a UML model that defines the types, structure, and interrelationships of geopolitical geography across the U.S. This model was designed to accommodate multiple types of contests and their many variations, and to provide the capability to report on these contests from higher aggregate levels down to very fine levels of detail, including:

- Reporting by precinct and splits of precincts;

- Reporting by ballot type, e.g., absentee, election day; and

- Reporting by device type and specific voting device.


Please contact [John P. Wack](mailto:john.wack@nist.gov) for questions and more information.

