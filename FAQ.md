# Frequently Asked Questions (FAQ) about the CF Conventions

This page covers many of the most common questions asked about the Climate and Forecast conventions (and Standard Names). If you have a question that isn't on this list, please ask it of the CF-metadata mail list, so that the CF community can respond. We will use that list as the basis for additional content for this set of questions.

The questions are organized by topic. Click on any question to go to its answer.

------------

# Contents

## CF Background

This section includes general background about the CF conventions.

* [What are the CF conventions, and what do they include?](#what)
* [What are the principles of the CF conventions?](#principles)
* [Why did we want yet another netCDF convention?](#why)
* [Who manages the CF conventions?](#who)
* [How long has CF been around? Is it mature?](#when_started) 
* [How does CF relate to other conventions (especially COARDS and netCDF)?](#related_conventions)

## Working with the CF Convention

* [Do the CF conventions stand alone?](#standalone)
* [How do I ask questions about CF?](#ask)
* [How do I propose a change?](#propose)
* [What is the process for accepting a change?](#change_process)
* [When are changes added to the CF Convention?](#when_updated)

## Rich technical questions about CF

These questions address big picture concepts included in CF.

* [What are Discrete Sampling Geometries? Do I need to worry about them?](#dsg)
* [My file was written using an earlier version of CF. Is it still compliant?](#version_compliance)

## CF Standard Names

General and specific information about purpose and mechanisms of standard names

* [What are the components of a standard name?](#stdnames_components)
* [How can I find the standard name I need?](#stdnames_find)
* [How do I ask for a new standard name?](#stdnames_ask)
* [What is the structure of a good standard name?](#stdnames_structure)
* [Are there common standard name phrases that get re-used?](#stdnames_phrases)
* [What can be described in a standard name?](#stdnames_facets)
* [What shouldn't be described in a standard name?](#stdnames_nonos)
* [What is the official list of standard names?](#stdnames_official)
* [Are there mappings of standard names to other vocabularies?](#stdnames_mappings)

## CF and COARDS Units (UDUNITS)

These questions are not strictly part of CF, but CF depends on this understanding.

* [What does it mean that a standard name _{?}_ has to be in canonical units?](#canonical)
* [Why does CF use UDUNITS as its standard?](#udunits_why)
* [How do I specify units in CF?](#cf_units)
* [Are there other good resources about UDUNITS?](#udunits_refs)

## Maintaining the CF standard

This section is about the meta-question of procedures involved to update CF standards documentation.

* [Who physically maintains the standards documentation?](#who_docs)
* [Where is the documentation stored?](#where_docs)
* [Can I fork (get a copy of) the repository?](#access_docs)
* [How can I submit suggested changes?](#update_docs)

------------

# Questions and Answers

## CF background

<a name="what"></a>
### What are the CF conventions, and what do they include?
The conventions for CF (Climate and Forecast) metadata are designed to promote the processing and sharing of files created with the NetCDF API. The conventions define metadata that provide a definitive description of what the data in each variable represents, and the spatial and temporal properties of the data. This enables users of data from different sources to decide which quantities are comparable, and facilitates building applications with powerful extraction, regridding, and display capabilities.

<a name="principles"></a>
### What are the principles of the CF conventions?
Principles of CF include self-describing data (no external tables needed for understanding); metadata equally readable by humans and software; and focusing on existing needs, with minimum redundancy and maximum simplicity.

<a name="why"></a>
### Why did we want yet another netCDF convention?
The existing conventions were (and are) typically much less robust for describing the syntax and semantics of netCDF data. The motivation for developing CF was the need for extra features not found in netCDF or COARDS. These include conventions for grid-cell boundaries, horizontal grids other than latitude-longitude, recording common statistical operations, standardised identification of physical quantities, non-spatiotemporal axes, climatological statistics and data compression. 

<a name="who"></a>
### Who manages the CF conventions?
The CF conventions are maintained by volunteers, led by a Governance Panel and assisted by the Conventions Committee and Standard Names Committee. (See [CF Governance](http://cfconventions.org/governance).) Changes to the conventions are proposed and settled by the community, using the [CF-Metadata Mailing List](http://mailman.cgd.ucar.edu/pipermail/cf-metadata/) and [CF Metadata Trac site](http://kitt.llnl.gov/trac). Many of the principles of CF operations follow the proposals at these [proposals for governance](http://cfconventions.org/cf2_whitepaper_final).

<a name="when_started"></a>
### How long has CF been around? Is it mature?
Work began on CF in 2001 and [Version 1.0](http://cfconventions.org/1.0) was released in October 2003. Now at Version 1.6, it has been used for tens of thousands of distinct netCDF products, has an active discussion list with hundreds of participants, and is a mature technical specification. Because it is community-supported and community-driven, turnaround on questions and changes can take a little time, but are generally thoroughly considered.

<a name="related_conventions"></a>
### How does CF relate to other conventions (especially COARDS and netCDF)?
CF is a convention built on top of the netCDF standard, and it generalizes and extends the netCDF [COARDS conventions](http://ferret.wrc.noaa.gov/noaa_coop/coop_cdf_profile.html). The information in netCDF and COARDS is not duplicated in CF, and CF is designed to be entirely compatible with the COARDS extension: Where COARDS is adequate, CF does not provide an alternative, while all of CF's extensions to COARDS are optional and provide new functionality. 

## Working with the CF Convention

<a name="standalone"></a>
### Do the CF conventions stand alone?
Not entirely; because CF is a netCDF convention, it assumes the netCDF standard is being followed. It also is based on the netCDF convention called the [COARDS conventions](http://ferret.wrc.noaa.gov/noaa_coop/coop_cdf_profile.html) (named for their sponsor, the Cooperative Ocean/Atmosphere Research Data Service), developed in 1995.  And it relies on the UDUNITS system of specifying units (see <a href="#udunits">CF and COARDS units</a> below). 

CF does not replicate the information from these other standards and conventions, so to adhere to CF you have to become familiar with the other specifications as well.

Aside from those references, a CF principle is to be self-contained. So for example the CF Standard Names attempt to be as general and well-defined as possible, so the reader does not have to access outside sources to understand the terms.

<a name="ask"></a>
### How do I ask questions about CF?
Questions about the CF standard, including its Standard Names list, may be asked at the [CF-Metadata Mailing List](http://mailman.cgd.ucar.edu/pipermail/cf-metadata/). You are encouraged to check this FAQ, and visit the [mail archives](http://mailman.cgd.ucar.edu/pipermail/cf-metadata), to see if your question has already been asked. CF community members usually respond within a day to simple questions, but allow more time if you have an advanced technical topic.

<a name="propose"></a>
### How do I propose a change?
Changes to the CF standard and the Standard Names are generally proposed first on the [CF-Metadata Mailing List](http://mailman.cgd.ucar.edu/pipermail/cf-metadata/). See [How do I ask for a new standard name?](#stdnames_ask) to learn more about changes to the Standard Names list.

A change to the CF standard itself will often be discussed in more detail on the [CF Metadata Trac site](http://kitt.llnl.gov/trac), where the explicit change being requested can be refined.

<a name="change_process"></a>
### What is the process for accepting a change?
The community discusses requests for changes via the mail list and trac site, and may ask questions or recommend changes. If no one raises objections or concerns about the change (as modified to address any issues) for a specified period of time, it is considered accepted. The moderators of the list typically make a final statement of acceptance once that stage has been reached.

<a name="when_updated"></a>
### When are changes added to the CF Convention?
Changes to the CF Convention itself are grouped into major releases. Because the proposed changes are visible to the community pending the final release of the convention, major releases may take as long as a year or more to finalize, but users may choose to follow the proposed new language in advance of the release date.

## Rich technical questions about CF

<a name="dsg"></a>
### What are Discrete Sampling Geometries? Do I need to worry about them?
Discrete Sampling Geometries, addressed in Section 9 of the CF Conventions, were added to offer greater efficiency and clarity for storing a collection of 'features' in a single file. We can define a feature by example for now: it can be a point, a time series, a trajectory, a profile, a time series (of) profile(s), or a trajectory (of) profile(s)

<a name="version_compliance"></a>
### My file was written using an earlier version of CF. Is it still compliant?
The compliance is determined by the version number you define in the `Conventions` attribute within each file. If your file complies with the specifications of the CF version in the `Conventions` attribute, it stays in compliance with CF even as newer versions of the CF Conventions are released. As a general rule, tools that work with files following the CF convention should be backward-compatible with earlier versions. 

An effort is made to avoid changing specific aspects of previous versions of the CF Conventions, though occasionally this is not possible.

## CF Standard Names

<a name="stdnames_components"></a>
### What are the components of a standard name?
_ -- name, modifiers, required attributes, additional columns_
A CF standard name attribute 

<a name="stdnames_find"></a>
### How can I find the standard name I need?


<a name="stdnames_ask"></a>
### How do I ask for a new standard name?


<a name="stdnames_structure"></a>
### What is the structure of a good standard name?


<a name="stdnames_phrases"></a>
### Are there common standard name phrases that get re-used?


<a name="stdnames_facets"></a>
### What can be described in a standard name?
_ -- different descriptive categories_

<a name="stdnames_nonos"></a>
### What shouldn't be described in a standard name?


<a name="stdnames_official"></a>
### What is the official list of standard names?
_ -- what are the services and how are they different_

<a name="stdnames_mappings"></a>
### Are there mappings of standard names to other vocabularies?


<a name="udunits"></a>
## CF and COARDS Units (UDUNITS)

<a name="canonical"></a>
### What does it mean that a standard name _{?}_ has to be in canonical units?


<a name="udunits_why"></a>
### Why does CF use UDUNITS as its standard?


<a name="cf_units"></a>
### How do I specify units in CF?
_ -- how to build and use CF-compatible units_

<a name="udunits_refs"></a>
### Are there other good resources about UDUNITS?



## Maintaining the CF standard

<a name="who_docs"></a>
### Who physically maintains the standards documentation?


<a name="where_docs"></a>
### Where is the documentation stored?


<a name="access_docs"></a>
### Can I fork (get a copy of) the repository?


<a name="update_docs"></a>
### How can I submit suggested changes?


