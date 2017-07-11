---
layout: cover
title: "NIST SP 1500-100 Election Results Reporting CDF Specification"
description: "SP 1500-100”
---

<section class="home home-title" markdown="1">

# Election Results Reporting Home

This is a placeholder for a MarkDown version of the NIST SP 1500-100 specification.  Thus far, Section 2 on geopolitical geography has been created from the Word version.

</section>

<section class="home home-about" markdown="1">
<div class="section-container" markdown="1">
<div class="section-content" markdown="1">


## Background: Geopolitical Geography

This section provides an overview of the geopolitical geography in the United States as it relates to elections and election results reporting, and serves to provide background for how geopolitical geography is implemented in the UML model and XML schema that are described in sections 3 through 5.  Knowledge of what constitutes geopolitical geography and how it is interrelated and used in elections provides the underpinning for understanding the complexities of election results reporting.  

## The Primary Types of Geopolitical Geography

The primary types of geopolitical geography include those geographies that run elections such as states, counties, and cities, as well as the many types of electoral districts that are tied to contests, precincts, and various other geographical units associated with political boundaries.  Generally, the media and election analysts wish to obtain voting results broken out by these units, thus the process of running an election includes associating contests and vote counts with these units so that they can be ultimately reported.

Ballot counts and vote counts for contests can be associated with a variety of different types of geopolitical geography, ranging from aggregated counts associated with a county or state down to more detailed counts associated with a precinct and breakdowns of a precinct.  Precincts are generally the smallest unit of geopolitical geography, and in many states, there is generally one polling place per precinct.  Precincts can be thought of as the bricks or building blocks that compose all other geopolitical geography.

Geopolitical geography can often be quite complex in that some are hierarchical, others overlap, and still others change their boundaries regularly, sometimes several times within a year.  Changes to city and district boundaries affect precinct boundaries, splitting them into multiple parts (called split precincts), with each part requiring distinct ballot styles.  

The following sections break down geopolitical geography into three primary types and show how the geographies interrelate.  These three types are:

1. Governmental-based geography,
2. Political-based geography, and
3. Administrative-based geography.

### Governmental-based Geography

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

### Political-based Geography

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

### Administrative-based Geography

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

## Linking the Geopolitical Geographies Together

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

## Geopolitical Geography in the UML Model and XML Schema

The previous discussion served to show that there are different types of geopolitical geography that overlap each other or behave hierarchically, resulting sometimes in very complex maps and many small geopolitical units that require distinct, different ballot styles.  Election officials may spend considerable time in managing this complexity.

Furthermore, each state and sometimes county or city will manage elections differently, using combinations of units such as combined precincts or wards, with specific rules about how the associated contests operate.  When one combines (a) the complexities of geopolitical geography with (b) the different election rules employed in the U.S. states and territories, one sees that running an election can be an extremely complicated endeavor.  Election results reporting mirrors this complexity.

It is important to note that the different geographies form relationships much like a lattice, in which objects can be related in non-hierarchical ways.  The UML model and XML schema implement geopolitical geography in this way using an object that can be linked with other objects depending on the type of geopolitical geography.  In the UML model, this object is referred to as the GpUnit (short for �Geopolitical Unit�) class, and in the XML schema it is called the <GpUnit> element.  GpUnits can model a district, or county, or precinct, etc., and can be linked to each other to mirror the real-world geopolitical geography of the reporting jurisdiction.

GpUnits can be linked hierarchically when modeling jurisdictional geographies.  To model a jurisdiction that runs/reports on elections, the lowest-level GpUnits, i.e., precincts, will be children of the election-running GpUnit, say a city or county or state.  

District GpUnits need to be linked to the precinct and/or split precinct GpUnits that compose them. The precincts and split precincts thus link the jurisdictional and district GpUnits together, as shown below in Figure 7 (and described in greater detail in section 5.2).  The wards are the children of the combined precincts, and so forth on up to the state.  The precincts and split precincts are also the children of the districts that they compose.  

<div class="text-center" markdown="1">
<img src="Figures/Containment.png" height="400"/>

**Figure 7 - GpUnit Structural Hierarchies**
</div>

</div>
</div>
</section>s
