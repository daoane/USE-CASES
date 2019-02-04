# Introduction to WP15 use cases

A fundamental facility to be achieved by EPOS as such will be the
ability for researchers to find data across domains and the primary
effort has therefore been concentrated around discovery use cases.
Typically, use cases describe a system from a user perspective and
dictate requirements for the system.

But in reality, use cases also need to be adjusted according to
technological possibilities, data availability, feasibility in the given
project framework and the level of ambition. In order to obtain the most
clear and realistic picture, a holistic approach has been chosen in the
current document taking into account the implications of the use cases
on the architectural choices. In general three or four levels of
discovery use cases have been defined.

This gradual approach is exemplified below on the basis of Borehole
related use cases.

For consistency sake each use case is identified by a 2 letters
identifier and an integer allowing identifying the use case level
concerned (ranging from 1 to 4).

## Use case level 1: Dataset discovery

The example below illustrates use case level 1 through the discovery of
borehole datasets from the UK in the INSPIRE geoportal (another example
could be provided in a machine to machine exchange). The main actor
searches for available borehole related datasets via a set of search
criteria. Search criteria and the information accompanying the search
results are limited to the generic type of metadata that is registered
on a dataset level such as title, contact person, online resources (web
services, web pages etc.), confidentiality, use restrictions, keywords
etc. The same applies for any other types of data.

The result of the search is a set of potential datasets matching the
user search criteria. Each of them is provided with a bounding box
corresponding to the geographical extent of the boreholes in the
database – not the boreholes themselves.

=> IMAGE 1 HERE

## Use case level 2: Simple feature view

Use cases level 2 are designed for providing the user with information
about the location of the individual data records in a dataset. This
means for example that the location of all boreholes in a borehole
dataset can be visually discovered. The typical scenario will be that
the main actor searches for e.g. boreholes in a geographic area with a
map showing their symbolised location. The user can then click an
individual borehole on the map and get some simple summary information
about that particular borehole.

=> IMAGE 2 HERE

## Use case level 3: Advanced feature discovery

This level of use case will allow the main actor to perform a search
using criteria specific for each data type and retrieve summary
information about the resulting features. An example could be that a
main actor searches for boreholes in a specific geographic area (e.g.
within a bounding box) being deeper than a certain value, that have been
drilled for a specific purpose and that have e.g. geophysical log data
associated. The result of such investigation would be a map showing only
those boreholes that fulfil the criteria and by clicking each of the
boreholes, summary information is displayed – also containing a link to
or information about how to get access to actual data such as
geophysical logs, geochemistry, sample descriptions, drill cores etc.

=> IMAGE 3 HERE

## Use case level 4: Advanced complex feature data access

This level of use case allows the main actor, once domain features are
identified to access in an interoperable manner to more detailed
information flows regarding those features. Those information flows will
be structured using shared semantic/data model. This will, in turn allow
those flows to be:

-   displayed to domain specialist using common tools

-   and/or ingested into more complex data processing solutions

The example below shows a borehole log structured description and a GUI
build on top of it

=> IMAGE 4 & IMAGE 5 HERE

# Borehole

use cases

## UC Bh.1: Borehole dataset discovery

<table>
  <thead>
    <tr class="header">
      <th><strong>Use Case Name/Topic</strong>: <em>Find borehole dataset concerning the Channel</em></th>
    </tr>
  </thead>
  <tbody>
    <tr class="odd">
      <td>
        <p><strong>Use case domain</strong>: This use case is:</p>
        <ul>
          <li>
            <p>Discipline-oriented, namely focusing on the discipline of: <em>geology</em></p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Use Case Description</strong></p>
        <p>Search and discover borehole datasets in a given area (ex: the southern part of the UK) so to find potential sources of information for a 3D modelling of groundwater reservoirs.</p>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Actors involved in the use case</strong></p>
        <ul>
          <li>
            <p>The scientist that uses EPOS GUI</p>
          </li>
          <li>
            <p>Machine to machine exchange supporting the underlying services requests and data exchange</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Priority</strong></p>
        <ul>
          <li>
            <p>High</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td><strong>Pre-conditions</strong></td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Flow of events – user view</strong></p>
        <ol type="1">
          <li>
            <p>User accesses the EPOS portal</p>
          </li>
        </ol>
        <ol type="1">
          <li>
            <p>User goes to the search page</p>
          </li>
          <li>
            <p>User draws a rectangle on a map ab Bh ove the Channel between France and England</p>
          </li>
          <li>
            <p>User types in “borehole” in a search field</p>
          </li>
          <li>
            <p>User press “search”</p>
          </li>
          <li>
            <p>User assesses the list of results</p>
          </li>
          <li>
            <p>User expands one item in the result list and reads more about the specific borehole dataset</p>
          </li>
          <li>
            <p>User clicks a link to “web site” and is redirected to a portal where the corresponding borehole dataset can be accessed, downloaded or purchased.</p>
          </li>
        </ol>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>System workflow – system view</strong></p>
        <ul>
          <li>
            <p>In order execute step 5, the EPOS front end sends a request to the EPOS ICS-C backend with a search request containing the bounding box and the search criteria “datatype = borehole”.</p>
          </li>
        </ul>
        <ul>
          <li>
            <p>The backend requests synonyms from a thesaurus and searches for borehole, well and drilling in EPOS metadata catalogue.</p>
          </li>
          <li>
            <p>A list of results is returned to the front end.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Post-conditions</strong></p>
        <ul>
          <li>
            <p>User should have gained access to one or more national portals or OGC web services containing borehole information in the relevant area.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td><strong>Extension Points</strong></td>
    </tr>
    <tr class="even">
      <td><strong>&lt;&lt;Used&gt;&gt; Use Cases</strong></td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Other Requirements</strong></p>
        <ul>
          <li>
            <p>All relevant datasets should be discoverable as “borehole datasets” no matter if they are named borehole, well or drilling datasets.</p>
          </li>
        </ul>
        <ul>
          <li>
            <p>Online resources need to be registered in the metadata records.</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

## UC Bh.2: Simple feature view of the Borehole Index

<table>
  <thead>
    <tr class="header">
      <th><strong>Use case name/topic</strong>: <em>Find and map borehole dataset in a specific part of Denmark</em></th>
    </tr>
  </thead>
  <tbody>
    <tr class="odd">
      <td>
        <p><strong>Use case domain</strong>: This use case is:</p>
        <ul>
          <li>
            <p>Discipline-oriented, namely focusing on the discipline of: <em>geology</em></p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Use case description</strong></p>
        <p>Map visualization of boreholes in Denmark.</p>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Actors involved in the use case</strong></p>
        <ul>
          <li>
            <p>The scientist that uses EPOS GUI</p>
          </li>
          <li>
            <p>Machine to machine exchange supporting the underlying services requests and data exchange</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Priority</strong></p>
        <ul>
          <li>
            <p>High</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Pre-conditions </strong></p>
        <ol type="1">
          <li>
            <p>User accesses the EPOS portal</p>
          </li>
        </ol>
        <ol type="1">
          <li>
            <p>User goes to the search page</p>
          </li>
          <li>
            <p>User draws a rectangle on a map in Denmark</p>
          </li>
          <li>
            <p>User types in “borehole” in a search field and presses “search”</p>
          </li>
          <li>
            <p>User assesses the list of results</p>
          </li>
          <li>
            <p>The Borehole Index being part of the results the user clicks a link to “view service” and is redirected to an EPOS viewer, where the corresponding map can be explored and queried</p>
          </li>
          <li>
            <p>The system displays the Borehole Index on the map with the corresponding symbology along with the possibility to query graphically each borehole.</p>
          </li>
        </ol>
      </td>
    </tr>
    <tr class="even">
      <td><strong>Flow of events – user view</strong></td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>System workflow – system view</strong></p>
        <ul>
          <li>
            <p>In order execute step 5, the EPOS front end sends a request to the EPOS ICS-C backend with a search request containing the bounding box and the search criteria “datatype = borehole”.</p>
          </li>
        </ul>
        <ul>
          <li>
            <p>The backend requests EPOS metadata catalogue and searches for ‘borehole’ and provides corresponding datasets including the Borehole Index.</p>
          </li>
          <li>
            <p>The GUI provides a cartographic interface with the ability to add the Borehole Index in it</p>
          </li>
        </ul>
        <p>Each borehole entry in the Borehole Index that is represented on the map (with a dedicated symbology) can be queried.</p>
        <ul>
          <li>
            <p>The GUI (via the ICS-C) provides the relevant interface to query from the Borehole Index content/service for feature information based on their geolocation</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Post-conditions</strong></p>
        <ul>
          <li>
            <p>User should have visualised Borehole Index entries in its area of interest</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td><strong>Extension Points</strong></td>
    </tr>
    <tr class="even">
      <td><strong>&lt;&lt;Used&gt;&gt; Use Cases</strong></td>
    </tr>
    <tr class="odd">
      <td><strong>Other Requirements</strong></td>
    </tr>
  </tbody>
</table>

## UC Bh.3: Advanced borehole feature discovery

<table>
  <thead>
    <tr class="header">
      <th><strong>Use case name/topic</strong>: <em>Find borehole in a specific area with specific search criteria</em></th>
    </tr>
  </thead>
  <tbody>
    <tr class="odd">
      <td>
        <p><strong>Use case domain</strong>: This use case is:</p>
        <ul>
          <li>
            <p>Discipline-oriented, namely focusing on the discipline of: <em>geology</em></p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Use case description</strong></p>
        <p>Search for boreholes in Denmark being more than 700 metres deep, drilled with the purpose of oil and gas exploration and having geophysical log data available</p>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Actors involved in the use case </strong></p>
        <ul>
          <li>
            <p>The scientist that uses EPOS GUI</p>
          </li>
          <li>
            <p>Machine to machine exchange supporting the underlying services requests and data exchange</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Priority</strong></p>
        <ul>
          <li>
            <p>High</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Pre-conditions</strong></p>
        <ul>
          <li>
            <p>Borehole Index features should have semantic harmonisation and common data model</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Flow of events – user view</strong></p>
        <ol type="1">
          <li>
            <p>User accesses the EPOS portal</p>
          </li>
        </ol>
        <ol type="1">
          <li>
            <p>User goes to the search page</p>
          </li>
          <li>
            <p>User draws a rectangle on a map in Denmark</p>
          </li>
          <li>
            <p>User types in “borehole” in a search field and presses “search”</p>
          </li>
          <li>
            <p>User assesses the list of results</p>
          </li>
          <li>
            <p>The Borehole Index being part of the results the users selects it and has the possibility to pass via the GUI dedicated search criteria values (depth, purpose, geophysical log available in that example)</p>
          </li>
          <li>
            <p>The system proposes the Borehole Index entries that matches those search criteria (either on a map or on a list)</p>
          </li>
          <li>
            <p>User expands one item in the result list and reads more about the specific Borehole Index entry (possibility zooms on it on a map).</p>
          </li>
          <li>
            <p>He gets the possibility to interact graphically in the GUI with that borehole description, download the Borehole Index entry of interest in various formats and access the geophysical log available in an interoperable manner.</p>
          </li>
        </ol>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>System workflow – system view</strong></p>
        <ul>
          <li>
            <p>In order execute step 5, the EPOS front end sends a request to the EPOS ICS-C backend with a search request containing the bounding box and the search criteria “datatype = borehole”.</p>
          </li>
        </ul>
        <ul>
          <li>
            <p>The backend requests EPOS metadata catalogue and searches for ‘borehole’ and provides corresponding datasets including the Borehole Index.</p>
          </li>
          <li>
            <p>A list of results is returned to the front end.</p>
          </li>
          <li>
            <p>The GUI (via the ICS-C) provides the relevant interface to query attributes from the Borehole Index content/service</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Post-conditions</strong></p>
        <ul>
          <li>
            <p>User should have gained access to one or more Borehole Index entries and their associated OGC web services containing borehole information</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td><strong>Extension Points</strong></td>
    </tr>
    <tr class="even">
      <td><strong>&lt;&lt;Used&gt;&gt; Use Cases</strong></td>
    </tr>
    <tr class="odd">
      <td><strong>Other Requirements</strong></td>
    </tr>
  </tbody>
</table>

## UC Bh.4: Advanced complex feature borehole data access

<table>
  <thead>
    <tr class="header">
      <th>
        <p><strong>Use case name/topic</strong>:</p>
        <p>Access to fully structured Borehole data flows available at NRI</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr class="odd">
      <td>
        <p><strong>Use case domain</strong>:</p>
        <ul>
          <li>
            <p>Discipline-oriented, namely focusing on the discipline of: <em>geology</em></p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Use case description</strong></p>
        <p>This Use Case is an extension of the previous one (Bh.3)</p>
        <p>Once a borehole (or set of boreholes) is identified in the BoreholeIndex, access to fully-fledged complex feature information flows available at data providers’ level. These flow provide maximum amount of information on a dedicated
          sub-topic in a harmonized way (geophysical logs, geological description, ground water level, rock geochemistry, pore gas chemistry, geotechnical information, …)</p>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Actors involved in the use case</strong></p>
        <ul>
          <li>
            <p>The scientist that uses EPOS GUI</p>
          </li>
          <li>
            <p>Machine to machine exchange supporting the underlying services requests and data exchange</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Priority</strong></p>
        <ul>
          <li>
            <p>TBD</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Pre-conditions</strong></p>
        <ul>
          <li>
            <p>Borehole associated data flows should have semantic harmonisation and common data model(s)</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Flow of events – user view</strong></p>
        <ol type="1">
          <li>
            <p>Identification of relevant Borehole Index entry(ies)</p>
          </li>
        </ol>
        <ol type="1">
          <li>
            <p>From the entry(ies) possibility to access to more data flows organised by ‘domains’</p>
          </li>
          <li>
            <p>Each data flow retrieved is available in a commonly agreed semantic/data model for further reuse either in EPOS GUI or user’s client application. For example borehole logs from various data providers could be visualised in a shared
              borehole log visualisation tool.</p>
          </li>
        </ol>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>System workflow – system view</strong></p>
        <ul>
          <li>
            <p>BoreholeIndex is structured so that information items allowing access to further information are clearly identified and typed to allow dereferencing of pointers to those additional information resources</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Post-conditions</strong></p>
        <ul>
          <li>
            <p>User should have gained access in an interoperable manner to structured information regarding the Borehole (s) of interest.</p>
          </li>
          <li>
            <p>Supplemental information flows retrieved being available according to an agreed semantic/model they are further processable by the user.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td><strong>Extension Points</strong></td>
    </tr>
    <tr class="even">
      <td><strong>&lt;&lt;Used&gt;&gt; Use Cases</strong></td>
    </tr>
    <tr class="odd">
      <td><strong>Other Requirements</strong></td>
    </tr>
  </tbody>
</table>

# Geohazard use cases

## UC Gh.1: Existing dataset discovery

<table>
  <thead>
    <tr class="header">
      <th><strong>Use Case Name/Topic</strong>: <em>Searching for existing geohazard maps and inventory datasets in a specific area (i.e. Northern Italy)</em></th>
    </tr>
  </thead>
  <tbody>
    <tr class="odd">
      <td>
        <p><strong>Use case domain</strong>: This use case is:</p>
        <ul>
          <li>
            <p>Discipline-oriented, namely focusing on the discipline of: <em>geology, engineering</em></p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Use Case Description</strong></p>
        <p>Searching for geohazards affecting a certain area (e.g. Lake Garda area) and, in particular, if geohazard maps or dataset inventories of specific natural hazards exist with the purpose of</p>
        <ul>
          <li>
            <p>exploring existing basic geothematic information,</p>
          </li>
        </ul>
        <ul>
          <li>
            <p>And/or do a research on a specific geohazard, in order to evaluate possible correlation with other geohazards or geological data.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Actors involved in the use case</strong></p>
        <ul>
          <li>
            <p>The scientist that uses EPOS GUI</p>
          </li>
        </ul>
        <ul>
          <li>
            <p>Machine to machine exchange supporting the underlying services requests and data exchange</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Priority</strong></p>
        <ul>
          <li>
            <p>High</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td><strong>Pre-conditions</strong></td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Flow of events – user view</strong></p>
        <ol type="1">
          <li>
            <p>User accesses the EPOS portal</p>
          </li>
        </ol>
        <ol type="1">
          <li>
            <p>User goes to the search page</p>
          </li>
          <li>
            <p>User draws a rectangle on a map bounding the area to be investigated (Lake Garda)</p>
          </li>
          <li>
            <p>User types in a search field a keyword also exploring the pre-defined keywords (i.e. geohazard, landslide, active faults, ground motion, etc.) related to different hazard types.</p>
          </li>
          <li>
            <p>User presses “search”</p>
          </li>
          <li>
            <p>User assesses the list of results also exploiting the potential semantic engine based on a thematic thesaurus framework.</p>
          </li>
          <li>
            <p>User expands one item in the results list and reads more about the specific maps and dataset inventory</p>
          </li>
          <li>
            <p>User clicks a link to “web site” and is redirected to a portal, where the corresponding maps and dataset can be explored.</p>
          </li>
        </ol>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>System workflow – system view</strong></p>
        <ul>
          <li>
            <p>In order to execute step 5, the EPOS front end sends a request to the EPOS ICS-C backend with a search request containing the bounding box and the search criteria “datatype = geohazard”.</p>
          </li>
        </ul>
        <ul>
          <li>
            <p>The backend requests synonyms (step 6) from a thesaurus and invokes a multiple search for geohazard, landslide, active faults, ground motion, engineering geology, sinkholes or seismicity towards the EPOS metadata catalogue.</p>
          </li>
          <li>
            <p>A list of results is returned to the front end.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Post-conditions</strong></p>
        <ul>
          <li>
            <p>The user should have gained access to one or more national portals or OGC web services containing geohazard or geothematic information in the relevant area, to explore in the detail the resources.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td><strong>Extension Points</strong></td>
    </tr>
    <tr class="even">
      <td><strong>&lt;&lt;Used&gt;&gt; Use Cases</strong></td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Other Requirements</strong></p>
        <ul>
          <li>
            <p>All relevant datasets should be discoverable as “geohazard datasets”; no matter if they are named Landslide, Rock falls, Active faults or Engineering geology, etc.</p>
          </li>
        </ul>
        <ul>
          <li>
            <p>Online resources need to be registered in the metadata records.</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

## UC Gh.2: Simple view of a geohazard information layer

<table>
  <thead>
    <tr class="header">
      <th><strong>Use case name/topic</strong>: <em>Finding, viewing and examining a specific hazard map at different scale in a specific area (e.g. a portion of territory of France).</em></th>
    </tr>
  </thead>
  <tbody>
    <tr class="odd">
      <td>
        <p><strong>Use case domain</strong>: This use case is:</p>
        <ul>
          <li>
            <p>Discipline-oriented, namely focusing on the discipline of: <em>geology, engineering</em></p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Use case description</strong></p>
        <p>Find, view and consult the active faults map available in a portion of the French territory; with the purpose of exploring the specific sought information (geohazard layer) directly in the EPOS portal, by searching on the map view
          services.</p>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Actors involved in the use case</strong></p>
        <ul>
          <li>
            <p>The scientist that uses EPOS GUI</p>
          </li>
          <li>
            <p>Machine to machine exchange supporting the underlying services requests and data exchange</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Priority</strong></p>
        <ul>
          <li>
            <p>High</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td><strong>Pre-conditions</strong></td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Flow of events – user view</strong></p>
        <ol type="1">
          <li>
            <p>User accesses the EPOS portal</p>
          </li>
        </ol>
        <ol type="1">
          <li>
            <p>User goes to the search page</p>
          </li>
          <li>
            <p>User draws a rectangle on a map in the specific area to be investigated (portion of French territory)</p>
          </li>
          <li>
            <p>User types in a search field a keyword also exploring the pre-defined keywords (i.e. geohazard, landslide, active faults, ground motion, etc.) related to the different hazard types.</p>
          </li>
          <li>
            <p>User expands one item in the result list and reads more about the specific hazard map or dataset inventory.</p>
          </li>
        </ol>
        <p>User clicks a link to “view service” and is redirected to an EPOS viewer, where the corresponding map can be explored and queried, or to the web service capabilities to have direct access to the resources.</p>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>System workflow – system view</strong></p>
        <ul>
          <li>
            <p>In order to execute step 4, the EPOS front end sends a request to the EPOS ICS-C backend with a search request containing the bounding box and the search criteria “datatype = active faults”.</p>
          </li>
        </ul>
        <ul>
          <li>
            <p>The backend requests synonyms (step 5) from a thesaurus and issues a search for active faults and also seismic faults, tectonic structures, seismicity, etc. towards the EPOS metadata catalogue.</p>
          </li>
          <li>
            <p>A list of results is returned to the front end as view services composition</p>
          </li>
          <li>
            <p>The GUI provides a cartographic interface with the ability to add the view service in it and query it</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Post-conditions</strong></p>
        <ul>
          <li>
            <p>User should have been able to visualise the geohazard information in a cartographic interface in its area of interest and been offered the possibility to access to OGC web services containing geothematic information in the relevant
              area.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td><strong>Extension Points</strong></td>
    </tr>
    <tr class="even">
      <td><strong>&lt;&lt;Used&gt;&gt; Use Cases</strong></td>
    </tr>
    <tr class="odd">
      <td><strong>Other Requirements</strong></td>
    </tr>
  </tbody>
</table>

## UC Gh.3: Multiple querying of geohazard information layers

<table>
  <thead>
    <tr class="header">
      <th><strong>Use case name/topic</strong>: <em>Finding, viewing, overlapping and examining two or more specific geohazard maps, at different scale, in a defined area (e.g. cross-border area between Italy and Slovenia).</em></th>
    </tr>
  </thead>
  <tbody>
    <tr class="odd">
      <td>
        <p><strong>Use case domain</strong>: This use case is:</p>
        <ul>
          <li>
            <p>Discipline-oriented, namely focusing on the discipline of: <em>geology, engineering</em></p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Use case description</strong></p>
        <p>Crossing two or more geohazard information layers, in order to find any matches.</p>
        <p>For example overlap landslide data with InSAR ground motion data in a specific cross-border zone, as between Italy and Slovenia. The intersection of more information layers allows to perform a comparative geohazard analysis</p>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Actors involved in the use case</strong></p>
        <ul>
          <li>
            <p>The scientist that uses EPOS GUI</p>
          </li>
          <li>
            <p>Machine to machine exchange supporting the underlying services requests and data exchange</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Priority</strong></p>
        <ul>
          <li>
            <p>Medium</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Pre-conditions</strong></p>
        <ul>
          <li>
            <p>All the hazard inventories and maps must be “queryable”</p>
          </li>
          <li>
            <p>The data should have semantic harmonisation and common data model</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Flow of events – user view</strong></p>
        <ol type="1">
          <li>
            <p>User accesses the EPOS portal</p>
          </li>
        </ol>
        <ol type="1">
          <li>
            <p>User goes to the search page</p>
          </li>
          <li>
            <p>User draws a rectangle on a map in the specific area to be investigated (cross-border area between Italy and Slovenia)</p>
          </li>
          <li>
            <p>User types in a search field a specific keyword in order to explore the existing geo-hazard maps and inventories.</p>
          </li>
          <li>
            <p>User expands one item in the result list and reads more about the specific hazard map or dataset inventory.</p>
          </li>
          <li>
            <p>The user selects two or more hazard layers in order to load them in a viewer/client.</p>
          </li>
          <li>
            <p>The user is able to compare data and perform a comparative analysis, using specific geo-spatial functionalities.</p>
          </li>
        </ol>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>System workflow – system view</strong></p>
        <ul>
          <li>
            <p>In order to execute step 4, the EPOS front end sends a request to the EPOS ICS-C backend with a search request containing the bounding box and the search criteria “datatype = landslide&amp;InSAR”.</p>
          </li>
        </ul>
        <ul>
          <li>
            <p>The backend requests synonyms (step 5) and issues a search for landslide and also InSAR data towards the EPOS metadata catalogue to collect related view service.</p>
          </li>
          <li>
            <p>The list of web services will be charged in a client system in order to perform comparative analysis.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Post-conditions</strong></p>
        <p>User should have gained access to OGC web services containing geothematic information in the relevant area with a common semantic (data model)</p>
      </td>
    </tr>
    <tr class="odd">
      <td><strong>Extension Points</strong></td>
    </tr>
    <tr class="even">
      <td><strong>&lt;&lt;Used&gt;&gt; Use Cases</strong></td>
    </tr>
    <tr class="odd">
      <td><strong>Other Requirements</strong></td>
    </tr>
  </tbody>
</table>

# Geological multi-scale map use cases

## UC Gm.1: dataset discovery

<table>
  <thead>
    <tr class="header">
      <th><strong>Use Case Name/Topic</strong>: <em>Find geological maps datasets at different scale in France</em></th>
    </tr>
  </thead>
  <tbody>
    <tr class="odd">
      <td>
        <p><strong>Use case domain</strong>: This use case is:</p>
        <ul>
          <li>
            <p>Discipline-oriented, namely focusing on the discipline of: <em>geology</em></p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Use Case Description</strong></p>
        <p>Find the geological map available as bedrock or surface information, or some specific geothematic maps (i.e. geophysics gravimetry) datasets in the central part of France to have potential basic information to build a geological model or
          to explore geologic information rather a specific research domain.</p>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Actors involved in the use case</strong></p>
        <ul>
          <li>
            <p>The scientist that uses EPOS GUI</p>
          </li>
          <li>
            <p>Machine to machine exchange supporting the underlying services requests and data exchange</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Priority</strong></p>
        <ul>
          <li>
            <p>High</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td><strong>Pre-conditions</strong></td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Flow of events – user view</strong></p>
        <ol type="1">
          <li>
            <p>User accesses the EPOS portal</p>
          </li>
        </ol>
        <ol type="1">
          <li>
            <p>User goes to the search page</p>
          </li>
          <li>
            <p>User draws a rectangle on a map in central France</p>
          </li>
          <li>
            <p>User types in a search field a keyword also exploring the pre-defined keywords (i.e. map, bedrock, surface, quaternary deposits, geophysic, etc.)</p>
          </li>
          <li>
            <p>User press “search”</p>
          </li>
          <li>
            <p>User assesses the list of results also exploiting the potential semantic engine based on a thematic thesaurus framework.</p>
          </li>
          <li>
            <p>User expands one item in the result list and reads more about the specific maps dataset</p>
          </li>
          <li>
            <p>User clicks a link to “web site” and is redirected to a portal, where the corresponding map dataset can be explored or downloaded.</p>
          </li>
        </ol>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>System workflow – system view</strong></p>
        <ul>
          <li>
            <p>In order execute step 5, the EPOS front end sends a request to the EPOS ICS-C backend with a search request containing the bounding box and the search criteria “datatype = bedrock”.</p>
          </li>
        </ul>
        <ul>
          <li>
            <p>The backend requests synonyms (step 6) from a thesaurus and issues a search for bedrock, geologic map, geologic structure or lithology towards the EPOS metadata catalogue.</p>
          </li>
          <li>
            <p>A list of results is returned to the front end.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Post-conditions</strong></p>
        <ul>
          <li>
            <p>User should have gained access to one or more national portals or OGC web services containing geological information in the relevant area.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td><strong>Extension Points</strong></td>
    </tr>
    <tr class="even">
      <td><strong>&lt;&lt;Used&gt;&gt; Use Cases</strong></td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Other Requirements</strong></p>
        <ul>
          <li>
            <p>All relevant datasets should be discoverable as “geological map datasets” no matter if they are named bedrock, geologic map, geologic structure or lithology, etc.</p>
          </li>
        </ul>
        <ul>
          <li>
            <p>Online resources need to be registered in the metadata records.</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

## UC Gm.2: Simple maps view

<table>
  <thead>
    <tr class="header">
      <th><strong>Use case name/topic</strong>: <em>Find and view geological map at multiple scale in a specific part of Denmark</em></th>
    </tr>
  </thead>
  <tbody>
    <tr class="odd">
      <td>
        <p><strong>Use case domain</strong>: This use case is:</p>
        <ul>
          <li>
            <p>Discipline-oriented, namely focusing on the discipline of: <em>geology</em></p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Use case description</strong></p>
        <p>Find, view and consult the geological map information available in a part of the Denmark to have potential basic information to build a geological model or to explore geologic information rather a specific research domain.</p>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Actors involved in the use case</strong></p>
        <ul>
          <li>
            <p>The scientist that uses EPOS GUI</p>
          </li>
          <li>
            <p>Machine to machine exchange supporting the underlying services requests and data exchange</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Priority</strong></p>
        <ul>
          <li>
            <p>High</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td><strong>Pre-conditions</strong></td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Flow of events – user view</strong></p>
        <ol type="1">
          <li>
            <p>User accesses the EPOS portal</p>
          </li>
        </ol>
        <ol type="1">
          <li>
            <p>User goes to the search page</p>
          </li>
          <li>
            <p>User draws a rectangle on a map in the specific part of Denmark</p>
          </li>
          <li>
            <p>User types in a search field a keyword also exploring the pre-defined keywords (i.e. map, bedrock, surface, quaternary deposits, geophysic, etc)</p>
          </li>
          <li>
            <p>User press “search”</p>
          </li>
          <li>
            <p>User assesses the list of results also exploiting the potential semantic engine based on a thematic thesaurus framework.</p>
          </li>
          <li>
            <p>User expands one item in the result list and reads more about the specific maps dataset</p>
          </li>
          <li>
            <p>User clicks a link to “view service” and is redirected to a viewer, where the corresponding map dataset can be explored and queried graphically.</p>
          </li>
        </ol>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>System workflow – system view</strong></p>
        <ul>
          <li>
            <p>In order execute step 5, the EPOS front end sends a request to the EPOS ICS-C backend with a search request containing the bounding box and the search criteria “datatype = bedrock”.</p>
          </li>
        </ul>
        <ul>
          <li>
            <p>The backend requests synonyms (step 6) from a thesaurus and issues a search for bedrock, geologic map, geologic structure or lithology towards the EPOS metadata catalogue.</p>
          </li>
          <li>
            <p>A list of results is returned to the front end as view services composition</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Post-conditions</strong></p>
        <ul>
          <li>
            <p>User should have gained access to OGC web services containing geological information in the relevant area.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td><strong>Extension Points</strong></td>
    </tr>
    <tr class="even">
      <td><strong>&lt;&lt;Used&gt;&gt; Use Cases</strong></td>
    </tr>
    <tr class="odd">
      <td><strong>Other Requirements</strong></td>
    </tr>
  </tbody>
</table>

## UC Gm.3: Advanced geological feature discovery

<table>
  <thead>
    <tr class="header">
      <th><strong>Use case name/topic</strong>: <em>Find geological features in a specific cross-border part between Italy and France, to search a specific lithology.</em></th>
    </tr>
  </thead>
  <tbody>
    <tr class="odd">
      <td>
        <p><strong>Use case domain</strong>: This use case is:</p>
        <ul>
          <li>
            <p>Discipline-oriented, namely focusing on the discipline of: <em>geology</em></p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Use case description</strong></p>
        <p>Find geological features appearing on geological maps at a given scale (ex: at 1:500,000 scale) in a specific cross-border part between Italy and France, to search for a specific lithology or metamorphic facies; the purpose will be to
          analyse specific seismic response or a specific composition in a certain area, where geo-tectonic studies could be performed.</p>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Actors involved in the use case</strong></p>
        <ul>
          <li>
            <p>The scientist that uses EPOS GUI</p>
          </li>
          <li>
            <p>Machine to machine exchange supporting the underlying services requests and data exchange</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Priority</strong></p>
        <ul>
          <li>
            <p>Medium</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Pre-conditions</strong></p>
        <ul>
          <li>
            <p>The geological map features should have semantic harmonisation and common data model</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Flow of events – user view</strong></p>
        <ol type="1">
          <li>
            <p>User accesses the EPOS portal</p>
          </li>
        </ol>
        <ol type="1">
          <li>
            <p>User goes to the search page</p>
          </li>
          <li>
            <p>User draws a rectangle on a map in central France</p>
          </li>
          <li>
            <p>User types in a search field a keyword also exploring the pre-defined keywords (i.e. map, bedrock, surface, quaternary deposits, geophysic, etc.)</p>
          </li>
          <li>
            <p>User press “search”</p>
          </li>
          <li>
            <p>User assesses the list of results also exploiting the potential semantic engine based on a thematic thesaurus framework.</p>
          </li>
          <li>
            <p>The Geologic Feature Index being part of the results the users selects it and has the possibility to pass via the GUI dedicated search criteria values (lithology,…)</p>
          </li>
          <li>
            <p>The system proposes the Geologic Feature Index entries that matches those search criteria (either on a map or on a list)</p>
          </li>
          <li>
            <p>User expands one item in the result list and reads more about the specific Geologic Feature Index entry (possibility zooms on it on a map).</p>
          </li>
          <li>
            <p>He gets the possibility to interact graphically in the GUI with that borehole description, download the Geologic Feature Index entry of interest in various formats and access the webservice providing it.</p>
          </li>
        </ol>
      </td>
    </tr>
    <tr class="odd">
      <td><strong>System workflow – system view</strong></td>
    </tr>
    <tr class="even">
      <td><strong>Post-conditions</strong></td>
    </tr>
    <tr class="odd">
      <td><strong>Extension Points</strong></td>
    </tr>
    <tr class="even">
      <td><strong>&lt;&lt;Used&gt;&gt; Use Cases</strong></td>
    </tr>
    <tr class="odd">
      <td><strong>Other Requirements</strong></td>
    </tr>
  </tbody>
</table>

# 3D/4D Model use cases

## UC Mo.1:3D/4D Model dataset discovery

<table>
  <thead>
    <tr class="header">
      <th><strong>Use case name/topic</strong>: <em>Find 3D/4D Models datasets available in a given area</em></th>
    </tr>
  </thead>
  <tbody>
    <tr class="odd">
      <td>
        <p><strong>Use case domain:</strong></p>
        <ul>
          <li>
            <p>Discipline-oriented, namely focusing on the discipline of: geology</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Use case description:</strong></p>
        <p>Explore and discover available 3D models datasets in a given area: “As a scientist I want to use the EPOS Portal so that I can easily discover and browse available 3D models datasets.”</p>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Actors involved in the use case:</strong></p>
        <ul>
          <li>
            <p>The scientist that uses EPOS GUI</p>
          </li>
          <li>
            <p>Machine to machine exchange supporting the underlying services requests and data exchange</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Priority: (must have, should have, nice to have)</strong></p>
        <ul>
          <li>
            <p>High</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Pre-conditions:</strong></p>
        <ul>
          <li>
            <p>3D/4D Models should be described using a common semantic. This description should be exchanged using agreed technologies</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Flow of events:</strong> – user view</p>
        <ol type="1">
          <li>
            <p>User accesses the EPOS portal</p>
          </li>
        </ol>
        <ol type="1">
          <li>
            <p>User goes to the search page</p>
          </li>
          <li>
            <p>User draws a rectangle on a map above a given area</p>
          </li>
          <li>
            <p>User types in “3D model” in a search field</p>
          </li>
          <li>
            <p>User press “search”</p>
          </li>
          <li>
            <p>User assesses the list of results</p>
          </li>
          <li>
            <p>User expands one item in the result list and reads more about the specific 3D/4D Models dataset. User clicks a link to “web site” and is redirected to a portal where the corresponding 3D/4D models dataset can be accessed can be
              downloaded or purchased.</p>
          </li>
        </ol>
      </td>
    </tr>
    <tr class="odd">
      <td><strong>System workflow: tbd</strong></td>
    </tr>
    <tr class="even">
      <td><strong>Post-conditions:</strong> tbd</td>
    </tr>
    <tr class="odd">
      <td><strong>Extension Points: tbd</strong></td>
    </tr>
    <tr class="even">
      <td><strong>« Used » Use Cases: tbd</strong></td>
    </tr>
    <tr class="odd">
      <td><strong>Other Requirements: tbd</strong></td>
    </tr>
    <tr class="even">
      <td><strong>(to be filled in by WP7) After the interview: tbd</strong></td>
    </tr>
  </tbody>
</table>

## UC Mo.2: Simple Feature View of the Model Index

<table>
  <thead>
    <tr class="header">
      <th><strong>Use case name/topic</strong>: <em>Find and map 3D/4D models dataset in a given area.</em></th>
    </tr>
  </thead>
  <tbody>
    <tr class="odd">
      <td>
        <p><strong>Use case domain</strong>: This use case is:</p>
        <ul>
          <li>
            <p>Discipline-oriented, namely focusing on the discipline of: <em>geology</em></p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Use case description</strong></p>
        <p>Visualization of available 3D/4D Models in a given area.</p>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Actors involved in the use case</strong></p>
        <ul>
          <li>
            <p>The scientist that uses EPOS GUI</p>
          </li>
          <li>
            <p>Machine to machine exchange supporting the underlying services requests and data exchange</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Priority</strong></p>
        <ul>
          <li>
            <p>High</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Pre-conditions</strong></p>
        <ul>
          <li>
            <p>3D/4D Models should be described using a common semantic. This description should be exchanged using agreed technologies</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Flow of events – user view</strong></p>
        <ol type="1">
          <li>
            <p>User accesses the EPOS portal</p>
          </li>
        </ol>
        <ol type="1">
          <li>
            <p>User goes to the search page</p>
          </li>
          <li>
            <p>User draws a rectangle on a map in Denmark</p>
          </li>
          <li>
            <p>User types in “3D model” in a search field and presses “search”</p>
          </li>
          <li>
            <p>User assesses the list of results</p>
          </li>
          <li>
            <p>The 3D/4D Model Index being part of the results the user clicks a link to “view service” and is redirected to an EPOS viewer, where the corresponding map can be explored and queried graphically.</p>
          </li>
        </ol>
      </td>
    </tr>
    <tr class="odd">
      <td><strong>System workflow – system view</strong></td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Post-conditions</strong></p>
        <ul>
          <li>
            <p>User should have visualised locatable 3D/4D Model Index entries in its area of interest</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td><strong>Extension Points</strong></td>
    </tr>
    <tr class="even">
      <td><strong>&lt;&lt;Used&gt;&gt; Use Cases</strong></td>
    </tr>
    <tr class="odd">
      <td><strong>Other Requirements</strong></td>
    </tr>
  </tbody>
</table>

## UC Mo.3:Advanced 3D/4D Model feature discovery

<table>
  <thead>
    <tr class="header">
      <th>
        <p><strong>Use case name/topic:</strong></p>
        <p>Find a 3D/4D Model corresponding to various search criterias</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr class="odd">
      <td>
        <p><strong>Use case domain:</strong></p>
        <ul>
          <li>
            <p>Discipline-oriented, namely focusing on the discipline of: geology</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Use case description:</strong></p>
        <p>Targeted filtering and search based on 3D/4D Model descriptive information allowing access to descriptive information on 3D/4D Models.</p>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Actors involved in the use case:</strong></p>
        <ul>
          <li>
            <p>The scientist that uses EPOS GUI</p>
          </li>
          <li>
            <p>Machine to machine exchange supporting the underlying services requests and data exchange</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Priority: (must have, should have, nice to have)</strong></p>
        <ul>
          <li>
            <p>High</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Pre-conditions:</strong></p>
        <ul>
          <li>
            <p>3D/4D Models shall be described using a common semantic. This description shall be exchanged using agreed technologies</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Flow of events: – user view</strong></p>
        <ol type="1">
          <li>
            <p>User accesses the EPOS portal</p>
          </li>
        </ol>
        <ol type="1">
          <li>
            <p>User goes to the search page</p>
          </li>
          <li>
            <p>User draws a rectangle on a map in Germany</p>
          </li>
          <li>
            <p>User types in “3D Model” in a search field and presses “search”</p>
          </li>
          <li>
            <p>User assesses the list of results</p>
          </li>
          <li>
            <p>The Model Index being part of the results the users selects it and has the possibility to pass via the GUI dedicated search criteria values (purpose, type, …)</p>
          </li>
          <li>
            <p>The system proposes the Model Index entries that matches those search criteria (either on a map or on a list)</p>
          </li>
          <li>
            <p>User expands one item in the result list and reads more about the specific Model Index entry (possibility zooms on it on a map, access to a graphical representation of that specific 3D model for preview)</p>
          </li>
          <li>
            <p>He gets the possibility to interact graphically in the GUI with that Model description, download the Model Index entry of interest in various formats and access to more information on the Model in an interoperable manner.</p>
          </li>
        </ol>
      </td>
    </tr>
    <tr class="odd">
      <td><strong>System workflow: tbd</strong></td>
    </tr>
    <tr class="even">
      <td><strong>Post-conditions: tbd</strong></td>
    </tr>
    <tr class="odd">
      <td><strong>Extension Points: tbd</strong></td>
    </tr>
    <tr class="even">
      <td><strong>« Used » Use Cases: tbd</strong></td>
    </tr>
    <tr class="odd">
      <td><strong>Other Requirements: tbd</strong></td>
    </tr>
    <tr class="even">
      <td><strong>(to be filled in by WP7) After the interview: tbd</strong></td>
    </tr>
  </tbody>
</table>

## UC Mo.4: Advanced Model complex feature download

<table>
  <thead>
    <tr class="header">
      <th>
        <p><strong>Use case name/topic:</strong></p>
        <p>Access to full 3D/4D Model download made available by NRI</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr class="odd">
      <td>
        <p><strong>Use case domain:</strong></p>
        <ul>
          <li>
            <p>Discipline-oriented, namely focusing on the discipline of: <em>geology</em></p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Use case description:</strong></p>
        <p>This Use Case is an extension of the previous one (Mo.3).</p>
        <p>Once a Model is identified, download of this one uniquely identifiable 3D model in an interoperable manner</p>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Actors involved in the use case:</strong></p>
        <ul>
          <li>
            <p>The scientist that uses EPOS GUI</p>
          </li>
          <li>
            <p>Machine to machine exchange supporting the underlying services requests and data exchange</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Priority:</strong> (must have, should have, nice to have)</p>
        <ul>
          <li>
            <p>TBD</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Pre-conditions:</strong></p>
        <ul>
          <li>
            <p>3D/4D Model shall be structured in a shared semantic and common data model(s) and shall be exchanged using agreed technologies</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Flow of events:</strong> – user view</p>
        <ol type="1">
          <li>
            <p>Identification of relevant Model Index entry(ies)</p>
          </li>
        </ol>
        <ol type="1">
          <li>
            <p>From the entry(ies) possibility to download the Model itself.</p>
          </li>
          <li>
            <p>The Model being described in a commonly agreed semantic/data model it could be further reused (ex: user’s client applications, EPOS GUI…).</p>
          </li>
        </ol>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>System workflow: tbd</strong></p>
        <ul>
          <li>
            <p>ModelIndex is structured so that information items allowing access to further information is clearly identified and typed to allow dereferencing of pointer to additional information resource.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Post-conditions: tbd</strong></p>
        <ul>
          <li>
            <p>User should have gained access in an interoperable manner to structured information regarding the Model (s) of interest.</p>
          </li>
          <li>
            <p>The Model being available according to an agreed semantic/model it is further processable by the user.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td><strong>Extension Points: tbd</strong></td>
    </tr>
    <tr class="even">
      <td><strong>« Used » Use Cases: tbd</strong></td>
    </tr>
    <tr class="odd">
      <td><strong>Other Requirements: tbd</strong></td>
    </tr>
    <tr class="even">
      <td><strong>(to be filled in by WP7) After the interview: tbd</strong></td>
    </tr>
  </tbody>
</table>

# Mineral Resources use cases

## UC Mr.1: Mineral Resources dataset discovery

<table>
  <thead>
    <tr class="header">
      <th><strong>Use case name/topic</strong>: <em>Find Mineral Resources datasets available in a given area</em></th>
    </tr>
  </thead>
  <tbody>
    <tr class="odd">
      <td>
        <p><strong>Use case domain:</strong></p>
        <ul>
          <li>
            <p>Discipline-oriented, namely focusing on the discipline of: geology</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Use case description:</strong></p>
        <p>Explore and discover available mineral resources datasets in a given area: “As a scientist I want to use the EPOS Portal so that I can easily discover and browse available mineral resources datasets.”</p>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Actors involved in the use case:</strong></p>
        <ul>
          <li>
            <p>The scientist that uses EPOS GUI</p>
          </li>
          <li>
            <p>Machine to machine exchange supporting the underlying services requests and data exchange</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Priority: (must have, should have, nice to have)</strong></p>
        <ul>
          <li>
            <p>High</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Pre-conditions:</strong></p>
        <ul>
          <li>
            <p>The content of the Minerals4EU metadata catalogue should be accessible through the TCS.</p>
          </li>
          <li>
            <p>Mineral resource datasets should be described using a common semantic by means of the Gemet keyword “Mineral resources” in the metadata entries.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Flow of events – user view</strong></p>
        <ol type="1">
          <li>
            <p>User accesses the EPOS portal</p>
          </li>
        </ol>
        <ol type="1">
          <li>
            <p>User goes to the search page</p>
          </li>
          <li>
            <p>User draws a rectangle on a map above a given area</p>
          </li>
          <li>
            <p>User types in “mineral resources” in a search field</p>
          </li>
          <li>
            <p>User press “search”</p>
          </li>
          <li>
            <p>User assesses the list of results</p>
          </li>
          <li>
            <p>User expands one item in the result list and reads more about the specific mineral resources dataset. User clicks a link to “web site” and is redirected to a portal where the corresponding mineral resources dataset can be accessed can
              be downloaded or purchased.</p>
          </li>
        </ol>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>System workflow – system view</strong></p>
        <ul>
          <li>
            <p>The EPOS front end issues a request to the metatdata catalogue for metadata records where the keyword « Mineral resources » occur.</p>
          </li>
        </ul>
        <ul>
          <li>
            <p>A list of metadata records is returned to the front end.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td><strong>Post-conditions:</strong></td>
    </tr>
    <tr class="odd">
      <td><strong>Extension Points:</strong></td>
    </tr>
    <tr class="even">
      <td><strong>« Used » Use Cases:</strong></td>
    </tr>
    <tr class="odd">
      <td><strong>Other Requirements:</strong></td>
    </tr>
    <tr class="even">
      <td><strong>(to be filled in by WP7) After the interview:</strong></td>
    </tr>
  </tbody>
</table>

## UC Mr.2: Simple Feature View of the Mineral Resources Index

<table>
  <thead>
    <tr class="header">
      <th><strong>Use case name/topic</strong>: <em>Find mineral resource with a given commodity in a given area.</em></th>
    </tr>
  </thead>
  <tbody>
    <tr class="odd">
      <td>
        <p><strong>Use case domain</strong>: This use case is:</p>
        <ul>
          <li>
            <p>Discipline-oriented, namely focusing on the discipline of: <em>geology</em></p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Use case description</strong></p>
        <p>Find occurrences of a specific commodity (e.g. Copper) in a given area.</p>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Actors involved in the use case</strong></p>
        <ul>
          <li>
            <p>The scientist that uses EPOS GUI</p>
          </li>
          <li>
            <p>Machine to machine exchange supporting the underlying services requests and data exchange</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Priority</strong></p>
        <ul>
          <li>
            <p>High</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Pre-conditions</strong></p>
        <ul>
          <li>
            <p>Mineral resource information should be stored in a common data model.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Flow of events – user view</strong></p>
        <ol type="1">
          <li>
            <p>User accesses the EPOS portal</p>
          </li>
        </ol>
        <ol type="1">
          <li>
            <p>User goes to the search page</p>
          </li>
          <li>
            <p>User chooses “Mineral Resources” theme</p>
          </li>
          <li>
            <p>User draws a rectangle on a map in France</p>
          </li>
          <li>
            <p>User chooses “Copper” from a dropdown list of commodities and presses “search”</p>
          </li>
          <li>
            <p>User assesses the list of results</p>
          </li>
          <li>
            <p>User inspects results on the map and on the list and clicks a given mineral occurrence.</p>
          </li>
          <li>
            <p>User is presented with detail information about the selected mineral occurrence</p>
          </li>
        </ol>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>System workflow – system view</strong></p>
        <ul>
          <li>
            <p>The EPOS front end issues a request to a backend service that queries the mineral resources index with the given search parameters (bounding box and commodity).</p>
          </li>
        </ul>
        <ul>
          <li>
            <p>The back end returns a list of results to the front end.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td><strong>Post-conditions</strong></td>
    </tr>
    <tr class="odd">
      <td><strong>Extension Points</strong></td>
    </tr>
    <tr class="even">
      <td><strong>&lt;&lt;Used&gt;&gt; Use Cases</strong></td>
    </tr>
    <tr class="odd">
      <td><strong>Other Requirements</strong></td>
    </tr>
  </tbody>
</table>

# Active seismic experiments use cases

## UC As.1: Discovery of datasets from active seismic experiments

<table>
  <thead>
    <tr class="header">
      <th><strong>Use Case Name/Topic</strong>: <em>Find datasets from active seismic experiments in a defined area</em></th>
    </tr>
  </thead>
  <tbody>
    <tr class="odd">
      <td>
        <p><strong>Use case domain</strong>: This use case is:</p>
        <ul>
          <li>
            <p>Discipline-oriented, namely focusing on the discipline of: <em>geophysics, geology, geosciences general</em></p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Use Case Description</strong></p>
        <p>Search and discover datasets that contain data from active seismic surveys and experiments in a defined area to get an overview over the extent of existing information that could be integrated into a new study.</p>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Actors involved in the use case</strong></p>
        <ul>
          <li>
            <p>The scientist who uses the EPOS web portal</p>
          </li>
          <li>
            <p>Machine to machine exchange supporting the underlying services requests and data exchange</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td><strong>Priority</strong></td>
    </tr>
    <tr class="odd">
      <td><strong>Pre-conditions</strong></td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Flow of events – user view</strong></p>
        <ol type="1">
          <li>
            <p>User accesses the EPOS web portal</p>
          </li>
        </ol>
        <ol start="8" type="1">
          <li>
            <p>User proceeds to the search page</p>
          </li>
          <li>
            <p>User supplies coordinates, a bounding box/polygon or a place name.</p>
          </li>
          <li>
            <p>User types in “seismic line” in a search field</p>
          </li>
          <li>
            <p>User presses “search”</p>
          </li>
          <li>
            <p>User assesses the list of results</p>
          </li>
          <li>
            <p>User expands one item in the result list and reads more about the specific dataset</p>
          </li>
          <li>
            <p>User clicks a link to “web site” and is redirected to a portal where the corresponding data can be obtained.</p>
          </li>
        </ol>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>System workflow – system view</strong></p>
        <ul>
          <li>
            <p>In order to execute step 5, the EPOS front end sends a request to the EPOS ICS-C backend with a search request containing a bounding box and the search criteria “datatype = seismic line”.</p>
          </li>
        </ul>
        <ul>
          <li>
            <p>The backend requests synonyms from a thesaurus and searches for active seismics, seismic reflection, wide-angle seismics, refraction seismic experiment (others?) in EPOS metadata catalogue.</p>
          </li>
          <li>
            <p>A list of results is returned to the front end.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Post-conditions</strong></p>
        <ul>
          <li>
            <p>The user should have gained access to one or more data portals that provide access to the desired data sets.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td><strong>Extension Points</strong></td>
    </tr>
    <tr class="even">
      <td><strong>&lt;&lt;Used&gt;&gt; Use Cases</strong></td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Other Requirements</strong></p>
        <ul>
          <li>
            <p>All relevant datasets should be discoverable as “datasets from active seismic experiments” no matter how they are called by the data provider.</p>
          </li>
        </ul>
        <ul>
          <li>
            <p>Online resources need to be registered in the metadata records.</p>
          </li>
          <li>
            <p>Certain data sets in the databases of (mainly) the geological surveys might be access restricted. This should be clearly visible in the result list.</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

## UC As.2: Simple feature view of the Active Seismics Index

<table>
  <thead>
    <tr class="header">
      <th><strong>Use case name/topic</strong>: <em>Find and map datasets in the defined area.</em></th>
    </tr>
  </thead>
  <tbody>
    <tr class="odd">
      <td>
        <p><strong>Use case domain</strong>: This use case is:</p>
        <ul>
          <li>
            <p>Discipline-oriented, namely focusing on the discipline of: <em>geophysics, geology, geosciences general</em></p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Use case description</strong></p>
        <p>Map visualization of the location of an individual dataset (points (e.g. VSP), lines (2D surveys - “profiles”) and polygons (3D surveys)) from active seismic experiments and which is an entry in the Active Seismics Index.</p>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Actors involved in the use case</strong></p>
        <ul>
          <li>
            <p>The scientist who uses the EPOS web portal</p>
          </li>
          <li>
            <p>Machine to machine exchange supporting the underlying services requests and data exchange</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td><strong>Priority</strong></td>
    </tr>
    <tr class="odd">
      <td><strong>Pre-conditions</strong></td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Flow of events – user view</strong></p>
        <ol type="1">
          <li>
            <p>User accesses the EPOS web portal</p>
          </li>
        </ol>
        <ol start="7" type="1">
          <li>
            <p>User proceeds to the search page</p>
          </li>
          <li>
            <p>User supplies coordinates, a bounding box/polygon or a place name.</p>
          </li>
          <li>
            <p>User types in “seismic line” in a search field</p>
          </li>
          <li>
            <p>User presses “search”</p>
          </li>
          <li>
            <p>User assesses the list of results</p>
          </li>
          <li>
            <p>The Active Seismics Index is part of the results. The user activates the dataset and is shown a map where the individual datasets can be explored and queried.</p>
          </li>
          <li>
            <p>The system displays the Active Seismics Index features on the map with the corresponding symbology along with the possibility to query graphically each mapped item.</p>
          </li>
        </ol>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>System workflow – system view</strong></p>
        <ul>
          <li>
            <p>In order to execute step 5, the EPOS front end sends a request to the EPOS ICS-C backend with a search request containing a bounding box and the search criteria “datatype = seismic experiment”.</p>
          </li>
        </ul>
        <ul>
          <li>
            <p>The backend requests synonyms from a thesaurus and searches for active seismics, reflections seismics, seismic experiment (others?) in EPOS metadata catalogue and displays the results (in line with UC As.1).</p>
          </li>
          <li>
            <p>The GUI provides a cartographic interface with the ability to display (any subset of) the Active Seismic Index. Each entry of the index is represented on the map as a feature (with a dedicated symbology) that can be queried. The
              features can be points in case of borehole seismics, lines in case of 2D seismics and polygons in case of 3D.</p>
          </li>
          <li>
            <p>The GUI (via the ICS-C) provides the relevant interface to query the Active Seismic Index content/service for feature information based on their geolocation.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Post-conditions</strong></p>
        <ul>
          <li>
            <p>The user has visualised all entries of the Active Seismics Index in the area of interest and retrieved additional information about certain, user-determined entries.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td><strong>Extension Points</strong></td>
    </tr>
    <tr class="even">
      <td><strong>&lt;&lt;Used&gt;&gt; Use Cases</strong></td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Other Requirements</strong></p>
        <ul>
          <li>
            <p>Certain data sets in the databases of (mainly) the geological surveys might be access restricted. This should be clearly reflected in the symbology.</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

## UC As.3: Advanced discovery of features in the Active Seismics Index and direct data access

<table>
  <thead>
    <tr class="header">
      <th><strong>Use case name/topic</strong>: <em>Find datasets that match geographic and other search/filter criteria and access the dataset of interest.</em></th>
    </tr>
  </thead>
  <tbody>
    <tr class="odd">
      <td>
        <p><strong>Use case domain</strong>: This use case is:</p>
        <ul>
          <li>
            <p><em>Discipline-oriented, namely focusing on the discipline of: geophysics, geology, geosciences general</em></p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Use case description</strong></p>
        <p>Search for a dataset from a seismic line/profile that at least partly intersects the defined area and that images the Earth’s crust to at least a defined depth (here assumed to be 5 km). Decide which datasets are of interests and get the
          data directly from the EPOS portal.</p>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Actors involved in the use case </strong></p>
        <ul>
          <li>
            <p>The scientist who uses the EPOS web portal</p>
          </li>
        </ul>
        <ul>
          <li>
            <p>Machine to machine exchange supporting the underlying services requests and data exchange</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td><strong>Priority</strong></td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>Pre-conditions</strong></p>
        <ul>
          <li>
            <p>The Active Seismics Index features should have semantic harmonisation and a common data model</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Flow of events – user view</strong></p>
        <ol type="1">
          <li>
            <p>User accesses the EPOS web portal</p>
          </li>
        </ol>
        <ol start="9" type="1">
          <li>
            <p>User proceeds to the search page</p>
          </li>
          <li>
            <p>User supplies coordinates, a bounding box/polygon or a place name.</p>
          </li>
          <li>
            <p>User types in “seismic line” in a search field</p>
          </li>
          <li>
            <p>User presses “search”</p>
          </li>
          <li>
            <p>User assesses the list of results</p>
          </li>
          <li>
            <p>Entries of the Active Seismics Index are part of the results. The user activates the dataset and is presented with an entry mask that presents additional criteria for refining the search or filtering the results of the previous
              search.</p>
          </li>
          <li>
            <p>The user enters “5 km” as the minimum “maximum depth of survey” and is presented with a list of entries from the Active Seismics Index that matches both this depth criterion and the geographic boundary criterion.</p>
          </li>
          <li>
            <p>The user can choose whether to map the results (cf. UC As.2) or click on a dataset and expand it (cf. UC As.1) to get more information.</p>
          </li>
          <li>
            <p>User expands one item in the result list and reads more about the specific Seismics Index entry (possibility zooms on it on a map).</p>
          </li>
          <li>
            <p>The user has option to directly access and download the desired dataset via the EPOS web portal.</p>
          </li>
        </ol>
      </td>
    </tr>
    <tr class="odd">
      <td>
        <p><strong>System workflow – system view</strong></p>
        <ul>
          <li>
            <p>A list of search results is returned to the front end.</p>
          </li>
        </ul>
        <ul>
          <li>
            <p>The GUI (via the ICS-C) provides the relevant interface to query attributes from the Seismics Index content/service.</p>
          </li>
          <li>
            <p>In order execute step 5, the EPOS front end sends a request to the EPOS ICS-C backend with a search request containing a bounding box and the search criteria “datatype = seismic experiment”.</p>
          </li>
          <li>
            <p>Basic search and display functions (map display; expand for full information) according to use cases As.1 and As.2.</p>
          </li>
          <li>
            <p>For step 7 and 8, the GUI provides a form that allows the user to refine the previous search or to filter the search results with the help of Active Seismics Index attributes. The front end then either sends a request with a refined
              search to the EPOS ICS-C backend and retrieves the new results or filters the previous results according to the new entries.</p>
          </li>
          <li>
            <p>The search/filter system has a function to translate certain values, since data sets will be in time or depth domain or consist of a combination of both (the latter could be treated as individual data sets). This can’t be done
              accurately for each data set. Average seismic velocities have to be assumed (or the user has to be given the choice to set the criteria).<br />
              =&gt; best would be if each data set would have a value in both, time and depth domains just for the search, but is this possible - DISCUSSION NEEDED!</p>
          </li>
          <li>
            <p>The EPOS web portal provides access to the data by establishing a download from the data provider. In case of data publications, this will most likely be a hard coded https request base on a doi. Geological surveys, others?<br />
              In case of restricted data sets, it provides a link to the data supplier for information on contact and conditions.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="even">
      <td>
        <p><strong>Post-conditions</strong></p>
        <ul>
          <li>
            <p>User should have retrieved seismic dataset(s) without the need to proceed to the individual data providers.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr class="odd">
      <td><strong>Extension Points</strong></td>
    </tr>
    <tr class="even">
      <td><strong>&lt;&lt;Used&gt;&gt; Use Cases</strong></td>
    </tr>
    <tr class="odd">
      <td><strong>Other Requirements</strong></td>
    </tr>
  </tbody>
</table>

## UC Bh.4: Not applicable

\| **Use case name/topic**: \|
\| ----------------------------------- \|
\| **Use case domain**: \|
\| **Use case description** \|
\| **Actors involved in the use case** \|
\| **Priority** \|
\| **Pre-conditions** \|
\| **Flow of events – user view** \|
\| **System workflow – system view** \|
\| **Post-conditions** \|
\| **Extension Points** \|
\| **\\&lt;\\&lt;Used>> Use Cases** \|
\| **Other Requirements** \|
