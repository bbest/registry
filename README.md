IOOS Service Registry at NGDC
=============================

The Service Registry (aka the registry) provides the master list of data sets available via DMAC data access services.  The registry is the official record of what is included in U.S. IOOS.  The service registry is hosted and operated by NGDC and provides a web based discovery interface for IOOS data.    

TODO: Describe the layout using the figure below (Harvestors, XSLT, ncISO, WAF, Metrics and Tools, Geoportal)
TODO: Include a section on the Geoportal including examples of querying the server that are listed here. https://geo-ide.noaa.gov/wiki/index.php?title=ESRI_Geoportal#IOOS_WAFs

TODO: Decide where the master list of Geoportal collection UUIDs will be hosted.  Currently on the wiki page above AND on the github.com/ioos/catalog repo.  Pick one as master. https://github.com/ioos/catalog/blob/master/uuid.csv

  
![Registration process](https://raw.github.com/ioos/registry/master/doc/images/IOOS%20Harvest%20Process.png)

![Registeration Process Workflow](https://raw.github.com/ioos/registry/master/doc/images/IoosWorkFlow20140312.png)


IOOS Service Registration Pathway
=================================

1. Submit an email to ioos.Catalog@noaa.gov and include the service URL (or WAF location), point of contact and service affilitation.
2. The servicThe status of the service will be manually changed from "submitted" to "approved".e URL is manually added to the Service Registry [collection source table] (https://www.ngdc.noaa.gov/docucomp/collectionSource/list?&layout=fluid).  It is listed as "submitted"  
3. The "submitted" service metadata will be automatically harvested into a [test Web Accessible Folder (WAF)} (http://www.ngdc.noaa.gov/metadata/published/test/NOAA/IOOS/).  
4. If successfully harvested, the test WAF is populated with an ISO metadata record by 0715.  The WAF is manually checked to verify the harvest has been successful.  The service status is changed from "submitted" to "approved" in the collection source table.  
5. The [production WAF}(http://www.ngdc.noaa.gov/metadata/published/NOAA/IOOS/) in EMMA is automatically populated on day 3 (day after the status has been changed to "approved ") by 0715.  
6. The [NGDC Geoportal] (http://www.ngdc.noaa.gov/geoportal/catalog/main/home.page) automatically harvests records from the WAF by 0900. 
7. The [IOOS Catalog](http://catalog.ioos.us/) will automatically harvest records from the NGDC Geoportal every 8 hours.  

*  Other addtional pathways to consider for registering new data using the issues in this repository.  Is this feasible?

ESRI Geoportal
=

[Master UUID list](https://github.com/ioos/registry/blob/master/uuid.csv)
=

IOOS WAF Search Examples: 

Date Search Example: Search within the PacIOOS WAF for records with start date 2009-02-01 to end date 2012-02-01 with JSON response: PacIOOS DateSearchExample Link
Decoded Parameters: rid=local&ridName=NOAA's Geophysical Data Center&searchText=startDate:[1800-01-01 TO 2012-02-01] AND endDate:[2009-02-01 TO 2100-01-01] AND sys.siteuuid:"{68FF11D8-D66B-45EE-B33A-21919BB26421}"&start=1&max=10&orderBy=relevance&maxSearchTimeMilliSec=10000&f=pjson

Keyword Example: Search within the PacIOOS WAF for keywords 'sea_water_salinity' with JSON response: PacIOOS KeywordExample Link
Decoded Parameters: rid=local&ridName=NOAA's Geophysical Data Center&searchText=keywords: sea_water_salinity AND sys.siteuuid:"{68FF11D8-D66B-45EE-B33A-21919BB26421}"&start=1&max=1000&orderBy=relevance&maxSearchTimeMilliSec=10000&f=pjson

Geographic Search Example: Search within the PacIOOS WAF for metadata records within -164.9246,16.6012,-149.4899,25.3959 with JSON response: PacIOOS GeoExample Link
Decoded Parameters: rid=local&ridName=NOAA's Geophysical Data Center&searchText=sys.siteuuid:"{68FF11D8-D66B-45EE-B33A-21919BB26421}"&start=1&max=1000&orderBy=relevance&spatialRel=esriSpatialRelWithin&bbox=-164.9246,16.6012,-149.4899,25.3959&maxSearchTimeMilliSec=10000&f=pjson

Multi-Criteria Example: Search within the PacIOOS WAF for metadata records with all of the above with JSON response: PacIOOS MultiExample Link
Decoded Parameters: rid=local&ridName=NOAA's Geophysical Data Center&rids=local&searchText=keywords: sea_water_salinity AND endDate:[2009-02-01 TO 2100-01-01] AND startDate:[1800-01-01 TO 2012-02-01] AND sys.siteuuid:"{68FF11D8-D66B-45EE-B33A-21919BB26421}"&start=1&max=1000&orderBy=relevance&spatialRel=esriSpatialRelWithin&bbox=-164.9246,16.6012,-149.4899,25.3959&maxSearchTimeMilliSec=10000&f=pjson

WMS Example: Search within the PacIOOS WAF for metadata records with a WMS service endpoint with GeoRSS response: PacIOOS WMSExample Link
Decoded Parameters: rid=local&ridName=NOAA's Geophysical Data Center&rids=local&searchText=wms.resource.url:* AND sys.siteuuid:"{68FF11D8-D66B-45EE-B33A-21919BB26421}"&start=1&max=1000&orderBy=relevance&maxSearchTimeMilliSec=10000&f=georss

WCS Example: Search within the PacIOOS WAF for metadata records with a WCS service endpoint with html response: PacIOOS WCSExample Link
Decoded Parameters: rid=local&ridName=NOAA's Geophysical Data Center&rids=local&searchText=wcs.resource.url:* AND sys.siteuuid:"{68FF11D8-D66B-45EE-B33A-21919BB26421}"&start=1&max=1000&orderBy=relevance&maxSearchTimeMilliSec=10000&f=html

SOS Example: Search within the PacIOOS WAF for metadata records with an SOS service endpoint with html response: PacIOOS SOSExample Link
Decoded Parameters: rid=local&ridName=NOAA's Geophysical Data Center&rids=local&searchText=sos.resource.url:* AND sys.siteuuid:"{68FF11D8-D66B-45EE-B33A-21919BB26421}"&start=1&max=1000&orderBy=relevance&maxSearchTimeMilliSec=10000&f=html

OPeNDAP Example: Search within the PacIOOS WAF for metadata records with a OpenDAP service endpoint with html response: PacIOOS OPeNDAPExample Link
Decoded Parameters: rid=local&ridName=NOAA's Geophysical Data Center&rids=local&searchText=odp.resource.url:* AND sys.siteuuid:"{68FF11D8-D66B-45EE-B33A-21919BB26421}"&start=1&max=1000&orderBy=relevance&maxSearchTimeMilliSec=10000&f=html


The [Master uuid document](https://github.com/ioos/registry/blob/master/uuid.csv)

GeoPortal CSW Documentation
=

NGDC CSW Service Endpoint
http://www.ngdc.noaa.gov/geoportal/csw
The examples below must be made as an XML POST request.

PacIOOS WAF
=
WMS Search Example:
<?xml version="1.0"?>	
<csw:GetRecords xmlns:csw="http://www.opengis.net/cat/csw/2.0.2" version="2.0.2" service="CSW" resultType="results" 
outputSchema="http://www.isotc211.org/2005/gmd" startPosition="1" maxRecords="1000">
  <csw:Query typeNames="csw:Record" xmlns:ogc="http://www.opengis.net/ogc" xmlns:gml="http://www.opengis.net/gml">
  <csw:ElementSetName>full</csw:ElementSetName> 
  <csw:Constraint version="1.1.0">
  <ogc:Filter>
    <ogc:And>
      <ogc:PropertyIsEqualTo>
        <ogc:PropertyName>sys.siteuuid</ogc:PropertyName>
        <ogc:Literal>{68FF11D8-D66B-45EE-B33A-21919BB26421}</ogc:Literal>
      </ogc:PropertyIsEqualTo>
      <ogc:PropertyIsLike wildCard="*" escape="\" singleChar="?"> 
        <ogc:PropertyName>apiso:ServiceType</ogc:PropertyName>
        <ogc:Literal>*wms*</ogc:Literal>
      </ogc:PropertyIsLike>
    </ogc:And> 
  </ogc:Filter> 
</csw:Constraint> 
</csw:Query>
</csw:GetRecords>

WCS Search Example:
=
<?xml version="1.0"?>	
<csw:GetRecords xmlns:csw="http://www.opengis.net/cat/csw/2.0.2" version="2.0.2" service="CSW" resultType="results" 
outputSchema="http://www.isotc211.org/2005/gmd" startPosition="1" maxRecords="1000">
  <csw:Query typeNames="csw:Record" xmlns:ogc="http://www.opengis.net/ogc" xmlns:gml="http://www.opengis.net/gml">
  <csw:ElementSetName>full</csw:ElementSetName> 
  <csw:Constraint version="1.1.0">
  <ogc:Filter>
    <ogc:And>
      <ogc:PropertyIsEqualTo>
        <ogc:PropertyName>sys.siteuuid</ogc:PropertyName>
        <ogc:Literal>{68FF11D8-D66B-45EE-B33A-21919BB26421}</ogc:Literal>
      </ogc:PropertyIsEqualTo>
      <ogc:PropertyIsLike wildCard="*" escape="\" singleChar="?"> 
        <ogc:PropertyName>apiso:ServiceType</ogc:PropertyName>
        <ogc:Literal>*wcs*</ogc:Literal>
      </ogc:PropertyIsLike>
    </ogc:And> 
  </ogc:Filter> 
</csw:Constraint> 
</csw:Query>
</csw:GetRecords>

OPeNDAP Search Example:
=
<?xml version="1.0"?>	
<csw:GetRecords xmlns:csw="http://www.opengis.net/cat/csw/2.0.2" version="2.0.2" service="CSW" resultType="results"
outputSchema="http://www.isotc211.org/2005/gmd" startPosition="1" maxRecords="1000">
  <csw:Query typeNames="csw:Record" xmlns:ogc="http://www.opengis.net/ogc" xmlns:gml="http://www.opengis.net/gml">
  <csw:ElementSetName>full</csw:ElementSetName> 
  <csw:Constraint version="1.1.0">
  <ogc:Filter>
    <ogc:And>
      <ogc:PropertyIsEqualTo>
        <ogc:PropertyName>sys.siteuuid</ogc:PropertyName>
        <ogc:Literal>{68FF11D8-D66B-45EE-B33A-21919BB26421}</ogc:Literal>
      </ogc:PropertyIsEqualTo>
      <ogc:PropertyIsLike wildCard="*" escape="\" singleChar="?"> 
        <ogc:PropertyName>apiso:ServiceType</ogc:PropertyName>
        <ogc:Literal>*opendap*</ogc:Literal>
      </ogc:PropertyIsLike>
    </ogc:And> 
  </ogc:Filter> 
</csw:Constraint> 
</csw:Query>
</csw:GetRecords>

SOS Search Example:
=
<?xml version="1.0"?>	
<csw:GetRecords xmlns:csw="http://www.opengis.net/cat/csw/2.0.2" version="2.0.2" service="CSW" resultType="results"
outputSchema="http://www.isotc211.org/2005/gmd" startPosition="1" maxRecords="1000">
  <csw:Query typeNames="csw:Record" xmlns:ogc="http://www.opengis.net/ogc" xmlns:gml="http://www.opengis.net/gml">
  <csw:ElementSetName>full</csw:ElementSetName> 
  <csw:Constraint version="1.1.0">
  <ogc:Filter>
    <ogc:And>
      <ogc:PropertyIsEqualTo>
        <ogc:PropertyName>sys.siteuuid</ogc:PropertyName>
        <ogc:Literal>{68FF11D8-D66B-45EE-B33A-21919BB26421}</ogc:Literal>
      </ogc:PropertyIsEqualTo>
      <ogc:PropertyIsLike wildCard="*" escape="\" singleChar="?"> 
        <ogc:PropertyName>apiso:ServiceType</ogc:PropertyName>
        <ogc:Literal>*sos*</ogc:Literal>
      </ogc:PropertyIsLike>
    </ogc:And> 
  </ogc:Filter> 
</csw:Constraint> 
</csw:Query>
</csw:GetRecords>

ISO Date Modified Search
=
<csw:GetRecords xmlns:csw="http://www.opengis.net/cat/csw/2.0.2" version="2.0.2" service="CSW" resultType="results" startPosition="1" maxRecords="11" outputSchema="http://www.isotc211.org/2005/gmd"> <csw:Query typeNames="csw:Record" xmlns:ogc="http://www.opengis.net/ogc" xmlns:gml="http://www.opengis.net/gml" > 
<csw:ElementSetName>full</csw:ElementSetName> 
<csw:Constraint version="1.1.0"> 
  <ogc:Filter>
    <ogc:And>
      <ogc:PropertyIsGreaterThan> 
      <ogc:PropertyName>apiso:modified</ogc:PropertyName> <ogc:Literal>2011-09-30</ogc:Literal>
      </ogc:PropertyIsGreaterThan> 
      <ogc:PropertyIsLessThan> 
      <ogc:PropertyName>apiso:modified</ogc:PropertyName> <ogc:Literal>2011-10-02</ogc:Literal>
      </ogc:PropertyIsLessThan> 
    </ogc:And>
  </ogc:Filter>
</csw:Constraint> 
</csw:Query> 
</csw:GetRecords> 

* How long does it take for a service to show up in a WAF after it is approved?
   * A new service should show up within 24 hours after it is approved.

* Is the harvesting process manual or automatic?
   * Harvesting runs automatically every night. 

* When does tne metadata harvest take place?
   * The metadata should be in the test WAF by 0715 on day 2.  DEFINE WHAT THIS MEANS.
   * 
* What is the relationship between the Service Registry and the [IOOS Catalog](http://catalog.ioos.us)? 
   * A web based catalog of IOOS services and datasets, available at  ....

* What is the relationship between the IOOS Service Registry and data.gov, GEOSS, and other national or international catalog efforts?
* What is the difference between a data set and data service?
   * TODO: Ask for input from the group.














# Old Material

IOOS Catalog Registration Process from EDM Wiki

The IOOS Catalog provides access to data from observing system platforms and data services. Take these steps to include your data and services in the catalog.
The Process

Use a Sensor Observation Service (SOS), Web Map Service (WMS), Unidata's THREDDS or ERDDAP to provide access to your data.
Review your metadata and add/update content as appropriate - Guidance for IOOS Data Providers
After updating your metadata, you may register your service by sending an email to ioos.catalog@noaa.gov.
provide Service Endpoint URL, Service Type, IOOS Region
The IOOS Registry/Catalog/Viewer team will add your service to Collection Source Table.
Then your service will be tested, the translated metadata will be reviewed and change requests may be sent back. Once the service is approved routine harvesting will begin.
Upon harvest ISO 19115-2 compliant metadata records are generated and a copy of the individual records are stored and assessed at EMMA.
The individual records are also loaded into the NGDC instance of the ESRI Geoportal Server.
The data or service is added to the IOOS Data Catalog and System Viewer
The service is added to the NOAA GEO-IDE Unified Access Framework catalog hosted here. Discussion item?
THREDDS Data Servers

Upgrade to a version of THREDDS with ncISO support (v >= 4.2.?)
Enable the ncISO service documented here.
For THREDDS based services, we require your NetCDF files and THREDDS metadata follow CF conventions and the Attribute Conventions for Dataset Discovery. Additional global attributes within the files are allowed, but the ACDD conventions are the minimal requirements for automatic generation of ISO 19115-2 metadata documents.
If your data contains in situ observations we recommend using the Climate and Forecast Conventions (9v.16 or later) Discrete Sampling Geometries.
OGC Sensor Observation Service

For SOS based services, we recommend the GetCapabilities document include metadata documented here.
A stylesheet is available for translating the Sensor Observation Service capabilities document into ISO 19139. Comments or suggestions for improvements should be addressed to EMMA email support.
