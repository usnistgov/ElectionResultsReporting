# **NIST SP 1500-100 Election Results Reporting Common Data Format Specification Version 1.0**

This is a placeholder for a GitHub pages version of the NIST SP 1500-100 specification for an interoperable common data format for election results reporting. Thus far, Section 2 on geopolitical geography has been created from the Word version. The specification documentation in Word and PDF is currently located at the GitHub repository [https://github.com/usnistgov/ElectionResultsReporting](https://github.com/usnistgov/ElectionResultsReporting).

## Table of Contents

<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Acknowledgements](#acknowledgements)
	- [Executive Summary](#executive-summary)
- [1 Introduction](#1-introduction)
	- [1.1	Purpose](#11-purpose)
	- [1.2	Audience](#12-audience)
	- [1.3	Motivation and methodology](#13-motivation-and-methodology)
	- [1.4	Document Structure](#14-document-structure)
- [2 Background: Geopolitical Geography](#2-background-geopolitical-geography)
	- [2.1 The Primary Types of Geopolitical Geography](#21-the-primary-types-of-geopolitical-geography)
		- [2.1.1 Governmental-based Geography](#211-governmental-based-geography)
		- [2.1.2 Political-based Geography](#212-political-based-geography)
		- [2.1.3 Administrative-based Geography](#213-administrative-based-geography)
	- [2.2 Linking the Geopolitical Geographies Together](#22-linking-the-geopolitical-geographies-together)
	- [2.3 Geopolitical Geography in the UML Model and XML Schema](#23-geopolitical-geography-in-the-uml-model-and-xml-schema)

<!-- /TOC -->

## Acknowledgements
The authors wish to thank their colleagues of the National Institute of Standards and Technology VVSG-Interoperability Public Working Group, who
reviewed drafts of this document and contributed to its technical content.  The authors gratefully acknowledge and appreciate the following
contributors for their keen and insightful assistance with developing this specification:

* Kenneth Bennett, Office of Registrar-Recorder /County Clerk, Los Angeles
* Lauren Massa-Lochridge, Independent Researcher
* Benjamin Rice, Dominion Voting
* Thomas Connolly, New York State Board of Elections
* Neal McBurnett, ElectionAudits
* John Sebes, OSET Foundation
* Art Greisser, Prometheus Computing
* John McCarthy, Verified Voting
* Paul Stenbjorn, Election Information Services
* Chris Jerdonek, Elections Commission, City and County of San Francisco
* Janet Modrow, Florida Division of Elections
* Beth Ann Surber, Office of the Secretary of State, West Virginia
* Arthur Keller, University of California
* Justin Moore, Google
* David Tarrent, Bureau of Elections, Michigan
* Jared Marcotte, The Turnout
* Tammy Patrick, Bipartisan Policy Institute
* David Webber, Horizon Industries

In addition to the above acknowledgments, the authors also gratefully acknowledge and appreciate the National Institute of Standards and Technology's
Mary Brady, James Foti, and Joshua Franklin, for their exceptional contributions in helping to improve the content of the publication.  
And finally, the authors also gratefully acknowledge and appreciate the significant contributions from individuals and organizations in the
public and private sectors, whose thoughtful and constructive comments improved the overall quality, thoroughness, and usefulness of this publication.

## Executive Summary
This publication is a specification for a common data format (CDF) for pre-election setup information and post-election results reporting.  The format, known as the Election Results Common Data Format Specification, is comprehensive and detailed in its coverage of election results-related data and at the same time very flexible, able to accommodate election scenarios used throughout the United States.  This publication contains a UML (Unified Modeling Language) model, a derived XML (eXtensible Markup Language) schema, usage information and guidance, and background information.

This specification provides a common data interchange format for election data used in voting systems across U.S. jurisdictions. Using this specification, pre-election and post-election data can be published in a common, well-understood format. The format accommodates highly detailed election results data and is sufficiently flexible to accommodate many different types of contests and political structures.

This specification provides manufacturers of election management systems (EMS) and managers of election jurisdictions with standard methods for importing and exporting election data, thereby increasing interoperability among election devices and reducing the need to create software to translate between proprietary formats.  Interoperable data will reduce costs to election jurisdictions by reducing the complexity in election management and offering jurisdictions more choice in election equipment.

This specification is geared towards the following audiences:

*	Election officials,
*	Voting equipment manufacturers,
*	Election-affiliated organizations, and
*	Election analysts and the general public.

The format accommodates three different election scenarios:

**Pre-election**.  The period prior to an election, for reporting pre-election data from a jurisdiction but not yet complete information about any election.

**Election**.  The period during which an election is being conducted and election results reports are produced.  The reports include aggregated results data or more detailed, precinct-level reporting, depending on the capabilities of the reporting jurisdiction.

**Post-election**.  The period after the close of polls when more detailed election results reports are produced with options for precinct reporting, type of ballot, and type of device.

The XML schema associated with this specification is derived from a UML model that defines the types, structure, and interrelationships of geopolitical geography across the U.S.  The model was designed to accommodate multiple types of contests and their many variations, and to provide the capability to report on these contests from higher aggregate levels down to very fine levels of detail, including:

* Reporting by precinct and splits of precincts;
*	Reporting by ballot type, e.g., absentee, election day; and
*	Reporting by device type and specific voting device.

The UML model can be re-used and modified to meet the needs of other planned common data format specifications for voting devices such as electronic pollbooks and ballot marking devices.

<br>

# 1	Introduction
This publication is a specification for an XML-based (eXtensible Markup Language) common data format (CDF) for exchanging pre-election and post-election data from voting systems used for managing elections and tabulating election results across states and territories of the United States.  The format serves as a basic export of election information from an election management system (EMS) and as a means for combining election data from different EMSs or transferring election data between EMSs.  It defines common exchange methods between distributed voting places and central offices as well as from election offices to news media and the general public. These common exchange methods promote interoperability and eliminate the need for proprietary formats.
This specification includes a data model in UML (Unified Modeling Language) that specifies and defines the data involved in pre-election setup and post-election results reporting.  The XML format is derived from the UML model.

The primary features of this specification are:

*	Major data elements and their attributes and associations are fully defined in a UML data model;
*	The data model can be used to generate data formats (e.g., XML, JSON (JavaScript Object Notation)) for today’s election systems as well as for future election systems;
*	Election data and results can be reported at flexible levels from highly aggregated to very detailed;
*	Detailed reporting includes by device type, by type of ballot, and by geopolitical geographies including precinct and split precinct;
*	Geopolitical units of geography can be specified in a flexible manner to mirror reporting structures used across states and counties and cities;
*	Major elements such as contests, geopolitical units, and parties include the capability to support multiple types of identifiers and cross-references; and
*	Detailed instructions for implementation and use of the XML schema are included.

<br>

## 1.1	Purpose
The purpose of this specification is to provide a comprehensive, flexible, and interoperable pre-election setup and post-election results reporting XML format for manufacturers to integrate into their voting equipment and for election offices, the media, and other groups to use in their own software.  The advantages of using this specification include:

*	Election results can be reported directly from election offices in this format regardless of voting system manufacturer, thus enabling interoperability;
*	The need for custom software and custom reporting formats is greatly reduced;
*	Jurisdictions that use multiple versions of EMSs and tabulators can more easily combine and transfer information between systems; and
*	Consistency in election results reports across different voting systems, jurisdictions, and states, will make reporting on election performance, e.g., for the EAC (Election Assistance Commission) election administration and voting survey (EAVS) and other election analyses, easier and more accurate.

<br>

## 1.2	Audience
The intended audience of this specification includes election officials, manufacturers and developers, as well as others in the election community including the general public.  Election results reporting is deceptively complex, thus some background in election administration or technology is useful in understanding the material in this specification.

<br>

## 1.3	Motivation and methodology
This specification was motivated primarily to reduce the inherent complexity for U.S. election officials in collecting and publishing election data, especially on election night when time frames are tight and there are more opportunities for error and a greater need for automation.  The process of reporting election results is a highly complicated activity that occurs over several different time frames and in multiple scenarios.  The equipment involved and data produced often do not interoperate, adding more complexity to the process.  Additionally, there are sometimes significant variations among different jurisdictions within a state as well among the states themselves in the way they perform election results reporting.

NIST and a community of U.S. election officials, analysts, and voting system manufacturers investigated reporting scenarios and their associated geopolitical geographies throughout the United States and in existing and emerging voting systems.  Further study included evaluation of other XML schemas associated with U.S. elections, including:

*	The State of Florida XML schema for election results reporting [4],
*	The Pew Voting Information Project XML schema version 3.0 [5],
*	The OASIS Election Markup Language (EML) XML schema version 7.0 [6], and
*	Schemas created by the Associated Press.

From this analysis, three use cases were developed for election results reporting:

1.	Pre-election – election data that is known ahead of the election; basically an export from an EMS of the contests, candidates, ballot initiatives, information about offices, and the geopolitical geographies associated with the reporting jurisdiction;

2.	Election night – reporting of election results either summarized by contest and jurisdiction or broken down by individual reporting units such as precincts, and associated formats, either as updates or corrections to previous reports or as internal intermediate reports within a state or county; and

3.	Post-election – updates and the final results compiled during the post-election canvass.

A UML data model was subsequently generated to define the data associated with the use cases and to show the relationship and organization of the data elements.  Finally, an XML schema was generated from the UML data model.  The XML schema defines the rules of the XML format.

The advantages of using a UML data model as an intermediate step to generating an XML schema include (1) that the model is independent of the concrete XML format or other potential formats that could be derived and (2) relationships between data elements are easier to correctly define and visualize when they are independent of any specific data format.  If changes are needed to the XML format, one can make changes to the UML model and generate a new version of the format.
Note that this specification addresses U.S. governmental elections and is not intended for use “as is” in other types of elections or in other countries.  However, the specification was written with the intention that it be adaptable to other election environments.

<br>

## 1.4	Document Structure
Section 2 starts with an overview of geopolitical geographies such as counties, districts, and precincts, describing how they are categorized, how they interrelate, and how election results are tied to them.  Section 3 contains an overview of the three use cases for election results reporting and the UML data model that implements the use cases.  Section 4 contains documentation for the XML schema that is derived from the UML model.  Section 5 describes how to use the major features of the schema.  

The appendices include references, definitions, acronyms, and instructions for downloading the files associated with this specification.

<br>

# 2 Background: Geopolitical Geography
This section provides an overview of the geopolitical geography in the United States as it relates to elections and election results reporting, and serves to provide background for how geopolitical geography is implemented in the UML model and XML schema that are described in sections 3 through 5.  Knowledge of what constitutes geopolitical geography and how it is interrelated and used in elections provides the underpinning for understanding the complexities of election results reporting.  

<br>

## 2.1 The Primary Types of Geopolitical Geography
The primary types of geopolitical geography include those geographies that run elections such as states, counties, and cities, as well as the many types of electoral districts that are tied to contests, precincts, and various other geographical units associated with political boundaries.  Generally, the media and election analysts wish to obtain voting results broken out by these units, thus the process of running an election includes associating contests and vote counts with these units so that they can be ultimately reported.

Ballot counts and vote counts for contests can be associated with a variety of different types of geopolitical geography, ranging from aggregated counts associated with a county or state down to more detailed counts associated with a precinct and breakdowns of a precinct.  Precincts are generally the smallest unit of geopolitical geography, and in many states, there is generally one polling place per precinct.  Precincts can be thought of as the bricks or building blocks that compose all other geopolitical geography.

Geopolitical geography can often be quite complex in that some are hierarchical, others overlap, and still others change their boundaries regularly, sometimes several times within a year.  Changes to city and district boundaries affect precinct boundaries, splitting them into multiple parts (called split precincts), with each part requiring distinct ballot styles.  

The following sections break down geopolitical geography into three primary types and show how the geographies interrelate.  These three types are:

1. Governmental-based geography,
2. Political-based geography, and
3. Administrative-based geography.

<br>

### 2.1.1 Governmental-based Geography
Governmental-based geography refers to entities that (1) run elections and (2) are well-established and do not change over time, with the exception of some cities.   For many states, the governmental-based geography is hierarchical, as shown in Figure 1.  This can be categorized as follows:

- States,
- Counties,
- Cities,
- American Indian Reservations,
- Towns and Townships, and
- Other Civil Divisions.

Nearly all states have counties, although some use different words to describe them, e.g., parishes for Louisiana and boroughs for Alaska.   Townships occur in 20 states and adhere to county boundaries.   In the six New England states, townships run the election process and there is no county government, thus election results are reported directly to the state. Municipalities (cities, towns, or villages) in Michigan, Minnesota, and Wisconsin also run their elections, but report their information to the county, which then reports to the state.  Other civil divisions include boroughs as used in Connecticut, New Jersey, Pennsylvania, and other states; New York City's boroughs are treated as counties.

<div class="text-center" markdown="1">
<img src="Figures/Governmental-based-geographies.png" height="400"/>

**Figure 1: Governmental-based Geographies**
</div>

Governmental-based geographies are associated with offices that are elected jurisdiction-wide (such as for Governor, County Clerk, Supervisor, Treasurer, Assessor, Highway Commissioner, etc.) and thus do not require different ballot style areas within the geography for those offices, i.e., all voters in the jurisdiction vote for the office.  
Governmental-based geographies do not cross the lines of the precincts that compose them; however cities can change their boundaries through annexations and, in some states, city boundaries can also cross county boundaries. Thus, changes to city boundaries may result in crossing the boundaries of one or more precincts, creating split precincts and requiring a distinct ballot style per split precinct.   

<br>

### 2.1.2 Political-based Geography
Political-based geographies are those that tend to be population-based and therefore may change with each U.S. Census every 10 years in a process known as re-districting.  Political-based geographies are generally known as electoral districts, where people are elected to an office that has jurisdiction within a specific geography, e.g., a U.S. Congressional district.

<div class="text-center" markdown="1">
<img src="Figures/Political-based-geographies.png" height="450"/>

**Figure 2: Political-based Geographies**
</div>

Figure 2 shows the most common political-based geographies as they interrelate with the governmental-based geographies.  Political-based geographies can be categorized as follows:

- U.S. Congressional districts;
- State senate or upper-house districts;
- State house or lower-house districts (in some states, several state house districts combine to form a state senate district);
- County electoral districts;
- City electoral districts (sometimes called Wards); and
- Numerous other forms of electoral districts.

Because electoral districts can change as they are re-drawn, political-based geographies will often divide precincts, creating split precincts and requiring a distinct ballot style per split precinct.   

<br>

### 2.1.3 Administrative-based Geography
Administrative-based geographies are called thus because their boundaries are determined via election or civil administration.  Administrative-based geographies include precincts and their various types such as wards, combined precincts, and split precincts.  They can be very small, sometimes only applying to several streets or houses or even only a single house along a street. They can involve territory that is non-contiguous in itself, e.g., for some of the taxing and special districts.  They can change a number of times throughout a given year, even daily in some cases.  Figure 3 shows the basic administrative-based geographies, which can be categorized as follows:

1. Election administrative areas;
	- Precincts, split precincts, combined precincts, wards;
	- Polling places, vote centers;
	- Various other ballot style areas;
2. Taxing districts, e.g., fire, water, sewer, transit, school, police, hospital, utilities; and
3. Special districts, i.e., unique areas brought together for a referendum.

<div class="text-center" markdown="1">
<img src="Figures/Administrative-based-geographies.png" height="500"/>

**Figure 3: Administrative-based Geographies**
</div>

<br>

## 2.2 Linking the Geopolitical Geographies Together
As an example of administrative-based geographies and their relationship to political-based and governmental-based geographies, Figure 4 shows the wards and precincts that make up the city of Cambridge, MA, and Figure 5 shows how the wards and precincts in the city compose the U.S. Congressional electoral districts [7].  The wards are implemented as collections of precincts.  In general, it is preferred that electoral districts are composed of whole precincts.

<div class="text-center" markdown="1">
<img src="Figures/2013_WardsPrecincts-v2.png" height="500"/>

**Figure 4: Ward and Precincts in Cambridge, MA.**
</div>

<div class="text-center" markdown="1">
<img src="Figures/2014_CongressDistricts-v2.png" height="500"/>

**Figure 5: Districts Overlaying Wards and Precincts in Cambridge, MA.**
</div>

In many states, the boundaries of electoral districts may crisscross the precinct boundaries, creating one or more split precincts, with a distinct ballot style per split precinct.  Depending on the number of districts and how often they cross the precinct boundaries, the resultant number of ballot styles created may grow substantially beyond the number of whole precincts.  It is possible sometimes that, despite best efforts, very low numbers of voters or even just one voter will require a district ballot style.

<div class="text-center" markdown="1">
<img src="Figures/Split-Precinct.png" height="450"/>

**Figure 6: Overlapping Non-hierarchical Electoral Districts**
</div>

As an example, Figure 6 shows two electoral districts that overlay a series of precincts.  Every time a precinct is not wholly contained within either of the districts, the precinct is split into however many pieces are necessary.  Figure 6 shows that a number of the precincts are split in different ways, e.g., Precinct 6 is split into two pieces.

Precinct 6 will thus require two distinct ballot styles, one for each of the splits.  To correctly tabulate the votes in the different electoral districts, it will be necessary to know which split of Precinct 6 is contained within each of the two electoral districts.

Precincts can be split as well by changes to the other administrative-based geographies. Adding to the complexity, a number of states now use combined precincts and vote centers on election night, which associate multiple precincts with one polling place.  This means that for a vote center handling multiple precincts that themselves may be split, there can be potentially many different ballot styles in use at the vote center, with each voting device needing to display any one of the ballots.  This adds further complexity and places additional demands on election jurisdictions on their ability to manage and report details of votes on election night and post-election [8].

To make this situation more manageable, some states/counties prefer over time to heal split precincts by combining them with other precincts or generally redrawing the precinct boundaries so that the number of ballot styles is reduced and election management and reporting is less complicated.

<br>

## 2.3 Geopolitical Geography in the UML Model and XML Schema
The previous discussion served to show that there are different types of geopolitical geography that overlap each other or behave hierarchically, resulting sometimes in very complex maps and many small geopolitical units that require distinct, different ballot styles.  Election officials may spend considerable time in managing this complexity.

Furthermore, each state and sometimes county or city will manage elections differently, using combinations of units such as combined precincts or wards, with specific rules about how the associated contests operate.  When one combines (a) the complexities of geopolitical geography with (b) the different election rules employed in the U.S. states and territories, one sees that running an election can be an extremely complicated endeavor.  Election results reporting mirrors this complexity.

It is important to note that the different geographies form relationships much like a lattice, in which objects can be related in non-hierarchical ways.  The UML model and XML schema implement geopolitical geography in this way using an object that can be linked with other objects depending on the type of geopolitical geography.  In the UML model, this object is referred to as the GpUnit (short for Geopolitical Unit) class, and in the XML schema it is called the `<GpUnit>` element.  GpUnits can model a district, or county, or precinct, etc., and can be linked to each other to mirror the real-world geopolitical geography of the reporting jurisdiction.

GpUnits can be linked hierarchically when modeling jurisdictional geographies.  To model a jurisdiction that runs/reports on elections, the lowest-level GpUnits, i.e., precincts, will be children of the election-running GpUnit, say a city or county or state.  

District GpUnits need to be linked to the precinct and/or split precinct GpUnits that compose them. The precincts and split precincts thus link the jurisdictional and district GpUnits together, as shown below in Figure 7 (and described in greater detail in section 5.2).  The wards are the children of the combined precincts, and so forth on up to the state.  The precincts and split precincts are also the children of the districts that they compose.  

<div class="text-center" markdown="1">
<img src="Figures/Containment.png" height="400"/>

**Figure 7 - GpUnit Structural Hierarchies**
</div>
