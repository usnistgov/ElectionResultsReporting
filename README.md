# Voting - NIST Special Publication 1500-100 Election Results Reporting Common Data Format Specification Versions 1 and 2

This repository contains the NIST Special Publication 1500-100 Version 1.0 and Version 2.0 Election Results Reporting Common Data Format (CDF) Specification Versions 1 and 2 and associated JSON and XML schemas and other supporting files. Version 1.0 supports XML; Version 2.0 contains improvements to the usability of the specification, adds additional data items, and supports JSON as well as XML. The specifications are being used in various U.S. states and counties, and by organizations including AP and Google both internationally and internationally.

The specifications are located as follows:

- [Version 1](https://github.com/usnistgov/ElectionResultsReporting/tree/version1)
- [Version 2](https://github.com/usnistgov/ElectionResultsReporting/tree/version2)

Google has also created a very informative documentation site, located at:

[https://developers.google.com/elections-data/reference/](https://developers.google.com/elections-data/reference/)

Both versions of the specification support the following election scenarios:

1. Pre-election.  The period prior to an election, for reporting pre-election data from a jurisdiction.


2. Election.  The period(s) when voting is being conducted and election results reports are being produced.  The reports could include aggregated results data or more detailed, precinct-level reporting, depending on the capabilities of the reporting jurisdiction.


3. Post-election.  The period after the close of polls when more detailed election results reports are produced with options for precinct reporting, type of ballot, and type of device.


The JSON and XML schemas associated with this specification are derived from a UML model that defines the types, structure, and interrelationships of geopolitical geography across the U.S. This model was designed to accommodate multiple types of contests and their many variations, and to provide the capability to report on these contests from higher aggregate levels down to very fine levels of detail, including:

- Reporting by precinct, splits of precincts, voting centers, and other geographic localities;

- Reporting by various ballot type, e.g., absentee, election day, early voting; and

- Reporting by by finer levels of detail such as device type and specific devices, batch, and dropbox.


Please contact [John Wack](mailto:john.wack@nist.gov) or [John Dziurlaj](mailto:john@hiltonroscoe.com) for questions and more information.

