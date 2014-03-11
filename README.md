registry
========

The service registry provides the master list of U.S. IOOS data providers and IOOS data web services that provide data in U.S. IOOS DMAC-compliant means.  The registry is the official record of what is included in U.S. IOOS.  

The service registry is hosted and operated by NGDC.  To submit your service to the registry, contact the IOOS Program at ioos.catalog@noaa.gov

IOOS Service Registration
The IOOS Catalog Registration Process on NOAA EDM Wiki:  https://geo-ide.noaa.gov/wiki/index.php?title=IOOS_Catalog_Registration_Process

Registration Process Image from Anna Milan: https://drive.google.com/file/d/0B0uvBG1lfvfMd1ZtTWR4UUY2Q2M/edit?usp=sharing

Service Registry FAQs: 

How is a service submitted to the registry?  An email with the service url, point of contact and organization should be sent to ioos.catalog@noaa.gov

How long does it take for a service to show up in a WAF after it is approved?
A new service should show up within 24 hours after it is approved.

Is the harvesting process manual or automatic?
Harvesting runs automatically every night. 

When does tne metadata harvest take place?
The metadata should be in the test WAF by 0715 on day 2.  

The 









A web based catalog of IOOS services and datasets, available at http://catalog.ioos.us

The IOOS Catalog registration process is described here: https://geo-ide.noaa.gov/wiki/index.php?title=IOOS_Catalog_Registration_Process

Here's the sequence of events to get data loaded in to the catalog:

Register new data service URL at the NGDC Collection Source table - Day 1, manual
Test metadata harvest happens - by 7:15 am on Day 2, automatic
Approval of new data service check status in EMMA - Day 2, manual
WAF is populated with new ISO record - Day 3 by 7:15 am, automatic
Geoportal harvests records from WAF - Day 3 by 9 am, automatic
IOOS Catalog queries Geoportal for all IOOS service URLs -?
IOOS Catalog harvests from individual services and generates dataset records. - ?
After a service URL is approved, steps 4 and 5 occur daily at the same time.




Old Material

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
