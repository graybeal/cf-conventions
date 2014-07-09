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

* [What is the purpose of the standard name?](#stdnames_purpose)
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

* [If my variable has a standard name, must it have the corresponding canonical units?](#canonical)
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
Discrete Sampling Geometries, addressed in Section 9 of the CF Conventions, were added to offer greater efficiency and clarity for storing a collection of 'features' in a single file. Here we define a feature by example: it can be a point, a time series, a trajectory, a profile, a time series (of) profile(s), or a trajectory (of) profile(s). All of these can be stored in CF-compliant netCDF files, but there was no consistent way to do so and people and programs could not leverage the features in the files.

You don't have to worry about Discrete Sampling Geometries, or DSGs, in order to be CF-compliant. If you have data that correspond to one of these feature types, you can read the the Discrete Sampling Geometry section to learn how to represent those data so that others can fully leverage them. (Note: The `feature_type attribute` is reserved for files that represent a Discrete Sampling Geometry.)

<a name="version_compliance"></a>
### My file was written using an earlier version of CF. Is it still compliant?
The compliance is determined by the version number you define in the `Conventions` attribute within each file. If your file complies with the specifications of the CF version in the `Conventions` attribute, it stays in compliance with CF even as newer versions of the CF Conventions are released. As a general rule, tools that work with files following the CF convention should be backward-compatible with earlier versions. 

An effort is made to avoid changing specific aspects of previous versions of the CF Conventions, though occasionally this is not possible.

## CF Standard Names

<a name="stdnames_purpose"></a>
### What is the purpose of the standard name?
The purpose of the standard name is to make it possible for a computer to decide if the named variable is likely to be meaningfully comparable to another named variable. It is expected that researchers will review the specifics of variables, particularly their long_name and source attributes, to assess whether they are truly interoperable; but variables with different standard names are highly unlikely to be directly comparable.

<a name="stdnames_components"></a>
### What are the components of a standard name?
A CF standard name is a unique text string, part of which is associated in the CF Standard Names table to other attributes. 

The text string is made up of two parts: the name (from the CF Standard Names table), and optionally, following the name and one or more blanks, a standard name modifier. The name contains no white space (underscores separate the words, in practice) and identifies the physical quantity. The modifier is used to describe a quantity which is related to another variable with the modified standard name. Details are provided in the convention section on [Standard Name](http://cfconventions.org/1.6.html#standard-name), and examples of modifiers are given in [Appendix C](http://cfconventions.org/1.6.html#standard-name-modifiers). 

Several attributes are required for every standard name: the canonical units, which are *typical* units of the physical quantity, and the description, which clarifies related quantities and meanings of the standard name (but is not strictly a definition per se). Older standard names may not have a description. 

In addition, standard names that come from certain sources may have GRIB parameter code(s) and/or AMIP identifiers; these are not generally required.

<a name="stdnames_find"></a>
### How can I find the standard name I need?
To find standard names that describe your data, open up the latest Standard Name table (as HTML, XML, or PDF) and search through it for words typically used for your data. (Because standard names contain no blanks, you may want to search for one word at a time, or even part of a word, rather than a full phrase like "air temperature".) If you can not find any matches, you can browse the table to see the kinds of names that exist -- names strongly lean toward environmental modeling and observation data, especially in atmosphere and ocean science.

If you can't find any matches, send an email to the CF-Metadata list describing your variables. (See the [question on asking for a new standard name](#stdnames_ask).)

<a name="stdnames_ask"></a>
### How do I ask for a new standard name?
You ask for a new standard name by sending an email to the [CF-Metadata Mailing List](http://mailman.cgd.ucar.edu/pipermail/cf-metadata/). You should sign up to the mailing list before sending your email, so you can follow the discussion of your request.

In the email specify the following for each standard name you want to request:
* its name
* its description
* its canonical units

Use other examples from the Standard Names table to model your request, or review past requests in the mail list archives.

<a name="stdnames_structure"></a>
### What is the structure of a good standard name?
A good standard name will typically include several characteristics that, together, characterize your variable. Common characteristics (or *facets*) include (with examples in parentheses):
* medium or realm of the entity (land, or sea_ice)
* a transformation component (flux, or concentration_of)
* a substance (sea_water, or carbon)
* a state, qualifying the substance or process (atomic, or frozen)
* a quantity being measured

The order is not rule-based; the goal is to make the name as clear and natural as possible. So an example standard name with most of the above is mole_concentration_of_atomic_nitrogen_in_air (quantity-transformation-state-substance-medium).

<a name="stdnames_phrases"></a>
### Are there common standard name phrases that get re-used?
Yes, there are phrases and patterns that reappear in different names. If you have to build a lot of standard names for different types of variables, some existing analyses may be helpful; send a note to the CF-Metadata list for guidance. If you are creating just a few standard names, it will be easiest to send an initial request using your best guess for the names; the list will perform the needed comparison to existing usage.

<a name="stdnames_facets"></a>
### What can be described in a standard name?
A comprehensive list of the standard name facets, based on a SWEET mapping and subsequent re-analysis, is:


  |  |  |   
 --- | --- | --- | ---  
Surface | Source | Scientific Component | Medium/Realm 
Transformation | Vector Component | Coordinate | Role 
Spectral Band | Energy | Substance | State 
expressed as (Substance or Property) | Fraction | Salinity | Temperature
Quantity | with respect to | defined by | ratio of
ratio to | (product) and | Process | Model 
difference from | difference to | Angle | at (Surface or Condition)
in (Substance or Realm) | into | out of | 
to | from  | reflected by | over
above | below | accumulated in | Statistics 
Condition | assuming (Condition) | due to | excluding  
for  | by | reported on | Artifact State


<a name="stdnames_nonos"></a>
### What shouldn't be described in a standard name?
The standard name should not include:
* the details of the measurement process by which the observed quantity was obtained
* mathematical transformations such as addition, multiplication, and averaging (these are handled by cell_methods)
* specialized terms that are not meaningful to a broad scientific audience, unless widely used and agreed on by the community of origin
* acronyms

<a name="stdnames_official"></a>
### What is the official list of standard names?
_ -- what are the services and how are they different_

<a name="stdnames_mappings"></a>
### Are there mappings of standard names to other vocabularies?


<a name="udunits"></a>
## CF and COARDS Units (UDUNITS)

<a name="canonical"></a>
### If my variable has a standard name, must it have the corresponding canonical units?


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


