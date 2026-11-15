

<!-- Start of picture text -->
IOOS GAR POD<br>Integrated Ocean<br>Observing System<br><!-- End of picture text -->

**Manual for Real-Time Oceanographic Data Quality Control Flags** 

**Version 1.2 June 2020** 

## **Document Validation** 



<!-- Start of picture text -->
Integrated Ocean<br>Observing System<br><!-- End of picture text -->



<!-- Start of picture text -->
US. IOOS Program Office Validation<br>~ 06/24/2020<br>Carl C. Gouldman, U.S. IOOS Program Director Date<br>QARTOD Project Manager Validation<br>Mh,(5 ( rh 06/24/2020<br>Kathleen Bailey, U.S. IOOS Project Manager Date<br>QARTOD Board of Advisors Validation<br>( Q. formas, 06/24/2020<br>anna O. Thomas, QARTOD Board of Advisors Chair Date<br><!-- End of picture text -->

ii 

## **Table of Contents** 

|**List of Tables ..................................................................................................................................... iii**|
|---|
|**Revision History ................................................................................................................................ iv**|
|**Endorsement Disclaimer .................................................................................................................... v**|
|**Request to Manual Users ................................................................................................................... v**|
|**Acknowledgements........................................................................................................................... vi**|
|**Acronyms and Abbreviations ............................................................................................................ vii**|
|**Document Purpose ......................................................................................................................... viii**|
|**Terms and Definitions ..................................................................................................................... viii**|
|**Background .......................................................................................................................................1**|
|Need for Flags.......................................................................................................................................... 1|
|Multiple Standards .................................................................................................................................. 1|
|Acceptance of Standards and Need for Flag Translators ........................................................................ 1|
|**QARTOD Data Flag Protocol ...............................................................................................................2**|
|Identification and Selection of an Existing Standard .............................................................................. 2|
|Definition of the Accepted Standard ...................................................................................................... 2|
|Advanced Flagging Schemes ................................................................................................................... 3|
|Primary Flags ........................................................................................................................................... 3|
|Implementation ....................................................................................................................................... 4|
|Application of Flags ................................................................................................................................. 5|
|**Summary ...........................................................................................................................................6**|
|**References .........................................................................................................................................7**|
|**Useful Links .......................................................................................................................................8**|
|**Appendix A.**<br>**QARTOD Data QC Flag Manual Team ...................................................................... A-1**|
|**List of Tables**|
|**Table 1**. Primary Level Flagging Standard...................................................................................................... 2|
|**Table 2.**QARTOD flagging definitions based on UNESCO 2013. ................................................................... 3|
|**Table 3**. Example of quality control tests and data processing history (IOC 54:V3). .................................... 3|
|**Table 4.**Example shows a two-tier flagging scheme (courtesy of the SIO CDIP team). ............................... 5|



iii 

## **Revision History** 

|**Date**|**Revision Description**|**Notes**|
|---|---|---|
|January2014|Original Document Published||
|May 2017|Revise cover page to include new IOOS and QARTOD logo.<br>Revise dates on_Document Validation_page and substitute new IOOS logo<br>(page ii).<br>Add statement requesting feedback from_Manual Users_(page v).<br>Update_Acknowledgements_to include version 1.1 team members (page vi).<br>Update_Acronyms and Abbreviations_(page vii).<br>Update definitions of real time and operator, add interoperable, quality<br>assurance, and quality control, alphabetize, and revise sentence structure<br>in_Terms and Definitions_(page viii).<br>Revise_Acceptance of Standards and Need for Flag Translators_to reflect<br>updated and additional manuals that have been developed (page 1).<br>Revise_Identification and Selection of an Existing Standard_(page 2).<br>Revise content in_Definition of the Accepted Standard_, adding paragraph and<br>table with data flags and descriptions; adjusted table numbering<br>accordingly (page 2).<br>Update content in_Advanced Flagging Schemes_(page 3).<br>Added section on_Implementation_(page 4)<br>Update content in_Applications of Flags_(page 6).<br>Update link to code repository in_Summary_(page 7).<br>Update Useful Links (page 9)<br>Update Version 1.1 Data Flags Manual Team members (pages A-1<br>through A-5).<br>Add appendix B: example of implementation code. (pages B-1 through<br>B-19.||
|June 2020|Revise cover page with new version number and date.<br>Revise signature page (page ii).<br>Revise email address for Manual Users (page v).<br>Update acknowledgements for Version 1.2 reviewers (page vi).<br>Add ERDDAP to update_Acronyms and Abbreviations_(page vii).<br>Add definitions of primary (formerly summary) and secondary flags to<br>_Terms and Definitions_(page viii).<br>Revise_Advanced Flagging Schemes_section of_QARTOD Data Flag Protocol_<br>(page 3).<br>Revise_Implementation_section of_QARTOD Data Flag Protocol_(page 4).<br>Revise_Summary_(page 6).<br>Update_References_(page 7).<br>Update_Useful Links_(page 8).<br>Update appendix A: Version 1.2 Data Flags Manual Team members<br>(page A-1).<br>Delete appendix B.||



iv 

## **Endorsement Disclaimer** 

**Mention of a commercial company or product does not constitute an endorsement by NOAA. Use of information from this publication for publicity or advertising purposes concerning proprietary products or the tests of such products is not authorized.** 

## **Request to Manual Users** 

**To gauge the success of the QARTOD project, it helps to be aware of groups working to utilize these QC tests. Please notify us of your efforts or intentions to implement QARTOD processes by sending a brief email to** **<u>qartod.board@noaa.gov</u> or posting a notice at** **<u>http://www.linkedin.com/groups?gid=2521409.</u>** 

v 

## **Acknowledgements** 

Thanks to all who assisted in the preparation of this document by providing content and reviewing drafts. Special thanks to the Data Management and Communications (DMAC) community members, especially Emilio Mayorga (NANOOS/University of Washington) for his significant support and contribution to the version 1.1 manual update, as well as his thoughtful insights about flag implementation. We are also grateful to Scripps Institution of Oceanography’s Coastal Data Information Program team for providing their data flagging example. We thank Luke Campbell (RPS Group) for sharing the CDL code as an example of data flag implementation in version 1.1 of this manual (removed in this updated version), and Doug Wilson and others at the NOAA Chesapeake Bay Office for supporting that implementation effort. 

We appreciate the careful review of version 1.2 by Darren Wright and Corey Olfe (University of California San Diego), Jessica Austin (Axiom Data Science), C.J. Pellerin (NOAA Chesapeake Bay Office), Mike Crowley and the high frequency radar surface current mapping team (Rutgers University), and Jorge Capella (Caribbean Regional Association for Coastal Ocean Observing/DMAC). We thank Felimon Gayanilo (Texas A&M University) and Micah Wengren (U.S. IOOS) for their suggestions. We acknowledge the favorable comments from Teresa Updyke (Old Dominion University) and Jorge Capella (University of Puerto Rico). 

We appreciate the efforts of all involved in arranging a code sprint at the University of Michigan in October 2019, and commend Jessica Austin, Jesse Lopez (Axiom Data Science), Andrew Reed, Cris Seaton (Woods Hole Oceanographic Institution), and Joe Smith (Cooperative Institute for Great Lakes Research – University of Michigan) for their participation in the QARTOD Library Implementation session, which consolidated multiple, distributed QARTOD GitHub libraries into a single IOOS organization Python repository. 

Appendix A contains the names and affiliations of all those who contributed to the original document and reviewed updated versions of this data QC flag manual. 

vi 

## **Acronyms and Abbreviations** 

|AOOS|Alaska Ocean Observing System|
|---|---|
|CARICOOS|Caribbean Regional Association for Coastal Ocean Observing|
|CDIP|Coastal Data Information Program|
|CDL|Common Data Language|
|CeNCOOS|Central and Northern California Ocean Observing System|
|CF|netCDF Climate and Forecast (CF) Metadata Conventions|
|CO-OPS|Center for Operational Oceanographic Products and Services|
|DCP|Data Collection Platform|
|DMAC|Data Management and Communications|
|ERDDAP|Environmental Research Division Data Access Program|
|GCOOS|Gulf of Mexico Coastal Ocean Observing System|
|GLOS|Great Lakes Observing System|
|GOOS|Global Ocean Observing System|
|IOC|Intergovernmental Oceanographic Commission|
|IOOS|Integrated Ocean ObservingSystem|
|MARACOOS|Mid-Atlantic Regional Association Coastal Ocean Observing System|
|MBARI|Monterey Bay Aquarium Research Institute|
|NANOOS|Northwest Association of Networked Ocean Observing Systems|
|NCDDC|National Coastal Data Development Center|
|NDBC|National Data Buoy Center|
|NERACOOS|Northeastern Regional Association of Coastal Ocean Observing Systems|
|netCDF|Network Common Data Form|
|NOAA|National Oceanic and Atmospheric Administration|
|NODC|National Oceanographic Data Center|
|NOS|National Ocean Service|
|PacIOOS|Pacific Islands Ocean Observing System|
|QARTOD|Quality-Assurance/Quality Control of Real-Time Oceanographic Data|
|QA|Quality Assurance|
|QC|QualityControl|
|RCOOS|Regional Coastal Ocean ObservingSystem|
|SCCOOS|Southern California Coastal Ocean Observing System|
|SECOORA|Southeast Coastal Ocean Observing Regional Association|
|SIO|Scripps Institution of Oceanography|
|UNESCO|United Nations Environmental, Scientific, and Cultural Organization|
|USACE|U.S. Army Corps of Engineers|
|WHOI|Woods Hole Oceanographic Institution|



vii 

## **Document Purpose** 

The U.S. Integrated Ocean Observing System (IOOS®) has issued Quality Assurance/Quality Control of Real-Time Oceanographic Data (QARTOD) manuals to be used for identifying the quality of oceanographic data in real-time. This data QC flag manual provides information to operators of ocean observing systems about the purpose and protocols of marking or flagging data, so that subsequent use of the data can be properly controlled by both users and automated processes. 

Please reference this document as: 

U.S. Integrated Ocean Observing System, 2020. Manual for the Use of Real-Time Oceanographic Data Quality Control Flags, Version 1.2. 24 pp. <u>https://doi.org/10.25923/w8y6-d298</u> 

## **Terms and Definitions** 

This manual contains several terms whose meanings are critical to those using the manual. These terms are included in the following table to ensure that the meanings are clearly defined. 

|**Data Quality Flag**|Data quality flag is metadata associated with a specific data point indicating the<br>results of one or more QC tests.|
|---|---|
|**Data Record**|A data record is one or more messages that form a coherent, logical, and<br>complete observation.|
|**Data User**|A data user is a middle or endpoint entity desiring information, but not<br>necessarily knowledgeable in methods used to obtain the information.|
|**Interoperable**|Interoperable means the ability of two or more systems to exchange and<br>mutually use data, metadata, information, or system parameters using<br>established protocols or standards.|
|**Operator**|Operators are individuals or entities who are responsible for collecting and<br>providing data.|
|**Quality Assurance**|QA involves processes that are employed with hardware to support the<br>generation of high quality data.|
|**Quality Control**|QC involves follow-on steps that support the delivery of high quality data and<br>requires both automation and human intervention.|
|**Real-Time**|Real-time means that: data are delivered without delay for immediate use; time<br>series extends only backwards in time, where the next data points are not<br>available; and sample intervals may range from a few seconds to a few hours<br>or even days, depending upon the sensor configuration.|
|**Primary Flag**|A primary flag is a single flag set to the worst case of all QC flags within the<br>data record.|
|**Secondary Flag**|A secondary flag records the results of a single QC test.|



viii 

_Data QC Flags Manual_ 

## **Background** 

#### **Need for Flags** 

Real-time oceanographic data are employed for a wide variety of applications and users. Some applications/users may require that only data of the highest quality be used, and others may seek an indication that a data point is questionable. Some users may prefer the delivery of all data, to be quality controlled using their own criteria. Successful use of the data will depend upon the knowledge, skills, and diligence of the user. Erroneous use of bad data or questionable/good data identified as bad can have serious consequences. For example, specific data points collected during a sudden increase in wind speed resulting from a localized summer thunderstorm may be outside expected wind speeds. However, the automated deletion of such data results in a loss of vital information concerning the weather event. 

Operators of observing systems may be best suited to determine the quality of their observations and to document their findings by generating metadata to accompany the observations. Information generated by software in real-time about the data quality is referred to as data quality flags, which become an embedded part of the output data stream. As such, the first value added by generating data quality flags is that the quality of the data has been considered at all—sometimes data flow without any evaluation of their quality. 

#### **Multiple Standards** 

The Intergovernmental Oceanographic Commission/United Nations Environmental, Scientific, and Cultural Organization (IOC/UNESCO) issued a document (hereafter referred to as IOC 54:V3) (UNESCO 2013) with seven examples of flag schemes. Other flag scheme examples exist, including those from the European Global Ocean Observing Systems DATA-MEQ Working Group (Pouliquen et al. 2011) and the National Oceanic and Atmospheric Administration (NOAA) National Ocean Service (NOS) Center for Operational Oceanographic Products and Services (CO-OPS) (Evans et al. 2003). Some flag schemes may simply assign a good or bad rating, which is sufficient for operators/users who desire only good data. At the other extreme, flag schemes can generate a detailed indication of why a data point has been flagged, which is helpful to those responsible for troubleshooting and repairing a sensor. 

#### **Acceptance of Standards and Need for Flag Translators** 

The U.S. IOOS QARTOD Project must accommodate a wide variety of operator QC capabilities. Most operators do not collect sufficient data to justify accepting only the best data and discarding lower quality data—all data can have value to some users. Some operators have highly evolved QC processes in place, and they are not inclined to replace those processes. Other operators may set a few rudimentary min/max thresholds to eliminate outlier data, which, without a flagging scheme, could be interpreted as a data gap. Operators may also have limited resources to implement additional processes/flags. 

Diversity in flag schemes is no different than that found worldwide in language, currency, engineering units, etc. One overarching standard may evolve over time, but meanwhile, a near-term solution is to create metadata translation tables to convert one standard to another. Both IOC 54:V3 and Schlitzer (2013) provide good examples of such translations. 

1 

_Data QC Flags Manual_ 

## **QARTOD Data Flag Protocol** 

#### **Identification and Selection of an Existing Standard** 

IOC 54:V3 was issued in 2013, shortly after the first QARTOD QC manual was published. A review of the various existing flag standards indicated that the standard suggested in early QARTOD manuals nearly matched the “Primary Level” scheme presented in IOC 54:V3. Rather than adhere to two nearly identical standards, QARTOD decided to adopt the IOC 54:V3 scheme and modify one existing QARTOD manual (dissolved oxygen, accomplished in April 2015) to conform to IOC 54:V3. 

#### **Definition of the Accepted Standard** 

The IOC 54:V3 Primary Level flagging standard (UNESCO 2013) is shown in table 1. 

**Table 1** . Primary Level Flagging Standard. 

|**Value**|**Primary-Level Flag Short Name**|**Definition**|
|---|---|---|
|1|Good|Passed documented required QC tests|
|2|Not evaluated, not available or<br>unknown|Used for data when no QC test performed or the<br>information on quality is not available|
|3|Questionable/suspect|Failed non-critical documented metric or<br>subjective test(s)|
|4|Bad|Failed critical documented QC test(s) or as<br>assigned by the data provider|
|9|Missing data|Used as place holder when data are missing|



QARTOD discourages use of the _Flag 2 Not Evaluated_ flag, as this violates the very first of the _Seven QARTOD Data Management Laws_ , which is that “every real-time observation distributed to the ocean community must be accompanied by a quality descriptor” (NOAA 2009). 

Further, QARTOD slightly expands the definition of the Flag 3 value to be “Suspect or Of High Interest” to emphasize the importance of retaining the human element within the QC process for such values. The full QARTOD flagging definitions table is given in table 2. 

2 

_Data QC Flags Manual_ 

**Table 2.** QARTOD flagging definitions based on UNESCO (2013). 

|**Flag**|**Description**|
|---|---|
|Pass=1|Data have passed critical real-time quality control tests and are deemed adequate for<br>use as preliminary data.|
|Not evaluated=2|Data have not been QC-tested, or the information on quality is not available.|
|Suspect or<br>Of High Interest=3|Data are considered to be either suspect or of high interest to data providers and users.<br>They are flagged suspect to draw further attention to them by operators.|
|Fail=4|Data are considered to have failed one or more critical real-time QC checks. If they are<br>disseminated at all, it should be readily apparent that they are not of acceptable quality.|
|Missing data=9|Data are missing; used as a placeholder.|



#### **Advanced Flagging Schemes** 

In IOC 54:V3, a secondary flag scheme is proposed, but only the primary level is fully described. Likewise, the U.S. IOOS QARTOD Project adopts only the primary level flags but encourages the use of secondary level flags for additional documentation that may be of use to operators and data users. Secondary level flags may be closely related to a specific sensor and consequently more challenging to translate to another standard. Several examples of such flags are taken from IOC 54:V3 and expanded in table 3. 

**Table 3** .  Example of quality control tests and data processing history (IOC 54:V3). 

|Globallyimpossible value(exceeds low or high thresholds)|
|---|
|Monthlyclimatologystandard deviation test(exceeds warningor failure thresholds)|
|Excessive spike check(exceeds warningor failure, low or high thresholds)|
|Excessive offset/bias when compared to a reference data set (exceeds warning or<br>failure, low or high thresholds)|
|Unexpected X/Y ratio (e.g., chemical stoichiometry or property-property X to T, S,<br>density, amongothers)|
|Excessive spatialgradient orpattern check(“bullseyes”)|
|Below detection limit of method|



#### **Primary Flags** 

Operators may generate primary flags for the convenience of data users. A primary flag is set to the highestlevel (worst case) flag found in the detailed tests outlined in QARTOD data quality manuals, such as U.S. IOOS (2019). For example, if any tests generate a _Flag 4 Bad_ flag, then the primary flag is set to _4 Bad_ . This provides a simple check that users can invoke when they require only a basic level of QC. QARTOD does not require use of the primary flag, but does strongly recommend it. U.S. IOOS does require the eleven Regional Associations (RAs) to provide a primary flag. 

3 

_Data QC Flags Manual_ 

#### **Implementation** 

Variable-specific QARTOD tests are identified as required, strongly recommended, and suggested. These groupings have been vetted by the variable-specific communities through the extensive QARTOD manual review process, and they inform the broad swath of capabilities that can exist within each community. The required tests are considered to provide the minimum level of QC and should be relatively easy to implement. However, it is recognized that in some instances even a required test may not be applicable. For example, in the QARTOD _Manual for Real-Time Quality Control of Water Level Data_ (U.S. IOOS 2016), the Location Test is required, but many fixed water level gauges don’t provide a location in the data stream; therefore, the Location Test cannot be performed. In cases where the operator has a defensible reason to exclude a required test, the reason should be provided in the metadata associated with the station. 

QARTOD does not dictate the methods operators use to implement data QC flags. Individual bits representing the five identified flag values (tables 1 and 2) may be set, making data masking an easy task. More likely, operators will identify a character string that can detect more than the five values found in tables 1 and 2. Operators are encouraged to provide code that can be used to read data and metadata, including these QC flags. 

IOOS uses existing community standards to the maximum extent possible (e.g., QARTOD, Climate and Forecast [CF], Attribute Conventions for Data Discovery [ACDD], Environmental Research Division Data Access Program [ERDDAP], etc.). In February 2020, the ERDDAP project team proposal to the CF governance committee to add QARTOD-inspired standard names to CF was accepted (see <u>https://github.com/cf-convention/cf-conventions/issues/216). The full set of CF standard names available</u> to identify QARTOD flag ancillary variables can be found in the CF Standard Name Table v72 at <u>http://cfconventions.org/Data/cf-standard-names/72/build/cf-standard-name-table.html. The search tool</u> can be employed to find quality-related flag variable names. Implementation of these standardized flag names are further described, and an example is provided, in the IOOS Metadata Profile Version 1.2 at <u>https://ioos.github.io/ioos-metadata/ioos-metadata-profile-v1-2.html - quality-controlqartod. Further</u> documentation of IOOS QARTOD and other QC tests, implemented in Python with notebook examples, have been developed by the community and are shared at https://github.com/ioos/ioos_qc and <u>https://ioos.github.io/ioos_qc/.</u> 

An advanced character string flagging scheme can be found in a Scripps Institution of Oceanography (SIO) Coastal Data Information Program (CDIP) Thematic Real-Time Environmental Distributed Data Services (THREDDS) server that hosts the CDIP netCDF data sets (http://thredds.cdip.ucsd.edu/thredds/catalog.html). Table 4 shows the two-tier IOC flagging used by CDIP: waveFlagPrimary holds the IOC-recommended primary level values, and waveFlagSecondary holds additional information as assigned by CDIP QC routines, based on both the data type and sensor type (a Datawell directional Waverider). 

The formatting and use of flags and other metadata, either through automated interoperability methods or human use, continue to evolve. Further information and training on metadata standards and other topics can be found on page 8 in the _Useful Links_ section of this manual. 

4 

_Data QC Flags Manual_ 

**Table 4.** Example shows a two-tier flagging scheme (courtesy of the SIO CDIP team). 



<!-- Start of picture text -->
{ @ Web | thredds.cdip.ucsd.edu/thredds/dodsC/cdip/archive/071p1/071p1_d17.nc.html<br>© waveFlagPrimary: Array of 8 bit Bytes [waveTime = 0..22608]<br>waveTime:|0:1:22608<br>long_name: primary wave QC flag<br>_Fillvalue: -127<br>valid min: 1<br>valid max: 9<br>flag_values: 1, 2, 3, 4, 9<br>flag_meanings: good not_evaluated questionable bad missing<br>reference: Ocean Data Standards, UNESCO 2013 - IOC Manuals and Guides, 54, Volume 3 Version 1<br>ancillary variables: waveFlagSecondary<br>© waveFlagSecondary: Array of 8 bit Bytes [waveTime = 0..22608]<br>waveTime:|0:1:22608<br>long_name: secondary wave QC flag<br>_Fillvalue: -127 |<br>valid min: @<br>valid max: 11<br>flag_values: 8, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11 J<br>flag_meanings: unspecified sensor issues Hsout_of_range Tpout_of_range Taout_of_range<br>elevatedhf_transmissioncheck factors Hs spike Ta spike low freq energy spike excessivelow freq energy ,<br>errors fixed hf_transmission_errorspresent<br><!-- End of picture text -->

#### **Application of Flags** 

QC flags provide necessary information to those who may use the data to make important decisions in realtime. The data and the metadata (including QC flag settings) provided in real-time should be archived exactly as they were delivered to users. Therefore, data records containing QC flags set in real-time should retain those flags permanently. Operators should have a high degree of confidence in the assigned QC flags. Postprocessed records may yield a different finding, but these records should not overwrite the real-time records. 

However, there are limited instances where it is acceptable to change a real-time flag. In some cases, QC tests operate on a data point that may be one or more cycles old. For example, a spike check might use data points at N-2 and N0 to examine data point N-1. In this case, the flag for the QC test on the data point N0 should be set to “ _2 Not evaluated, not available, or unknown_ .” After receipt of the subsequent data point, N0 becomes N-1, the spike test can be applied, and the flag can be changed as necessary. Operators and users must understand that some tests operate over several data points, and the determination of primary flags must also take this into consideration. The situation highlights the importance of users (both machine-to-machine and end users) evaluating the QC flags for several time-steps backward. 

5 

_Data QC Flags Manual_ 

## **Summary** 

There are a wide variety of applications for and users of real-time oceanographic data. The quality of those data is dependent upon many factors, including the ability to apply QC flags to real-time data streams. This QC flag manual has been compiled considering multiple QC flagging schemes that have been documented by various sources. The flagging standard suggested in early QARTOD manuals nearly matched the “Primary Level” scheme presented in IOC 54:V3. Therefore, QARTOD has accepted the IOC 54:V3 scheme as its data QC flag protocol. 

Although content for this manual is drawn from many sources, it is primarily intended to support the existing QARTOD QC manuals—not to address all data flagging schemes. Guidance provided in this manual, like that in other QARTOD manuals, also considers that operators have different skill levels and resources with which to apply QC flags. Some operators already employ advanced flagging schemes, while others use basic thresholds to flag outlier data. 

U.S. IOOS DMAC operators implementing QARTOD QC tests maintain a code repository at <u>https://github.com/ioos/ioos_qc</u> and https://ioos.github.io/ioos_qc/, where others may find or post examples of code in use. Such leveraging of developed code is strongly encouraged and appreciated. 

Each QC manual is envisioned as a dynamic document and will be posted on the QARTOD website at <u>https://ioos.noaa.gov/project/qartod/. This process allows for QC manual updates as technology</u> development occurs for both upgrades of existing sensors and new sensors. 

6 

_Data QC Flags Manual_ 

## **References** 

- Evans, M., French, G., and Bethem, T., 2003. Information Systems Branch PORTS Uniform Flat File Format (PUFFF) NOAA/NOS/CO-OPS, Silver Spring, Maryland. 32 pp. 

   - <u>http://tidesandcurrents.noaa.gov/publications/pufff4.pdf</u> 

- NOAA, 2009. Fifth Workshop on the QA/QC of Real-Time Oceanographic Data. November 16-19, 2009. 136 pp. Omni Hotel, Atlanta, Georgia. 

   - <u>https://cdn.ioos.noaa.gov/media/2019/05/QARTODVReport_Final2.pdf</u> 

- Paris. Intergovernmental Oceanographic Commission of UNESCO, 2013. Ocean Data Standards, Vol.3: Recommendation for a Quality Flag Scheme for the Exchange of Oceanographic and Marine Meteorological Data. (IOC Manuals and Guides, 54, Vol. 3.) 12 pp. (English.)(IOC/2013/MG/54-3) <u>http://www.nodc.noaa.gov/oceanacidification/support/MG54_3.pdf</u> 

- Pouliquen, S., 2011. Recommendations for in-situ data Real Time Quality Control. 23 pp. <u>http://eurogoos.eu/download/reference_documents_/rtqc.pdf</u> 

- Schlitzer, R., 2013. Ocean Quality Flag Schemes and Mapping between Them, Version 1.4. Alfred Wegener Institute for Polar and Marine Research, Bremerhaven, Germany. 18 pp. <u>http://odv.awi.de/fileadmin/user_upload/odv/misc/ODV4_QualityFlagSets.pdf</u> 

- U.S. Integrated Ocean Observing System, 2016. Manual for Real-Time Quality Control of Water Level Data Version 2.0: A Guide to Quality Control and Quality Assurance of Water Level Observations. 46 pp. <u>https://doi.org/10.7289/V5QC01Q7</u> 

- U.S. Integrated Ocean Observing System, 2019. Manual for Real-Time Quality Control of In-Situ Surface Wave Data Version 2.1: A Guide to Quality Control and Quality Assurance of In-Situ Surface Wave Observations. 70 pp. https://doi.org/10.25923/7yc5-vs69 

7 

_Data QC Flags Manual_ 

## **Useful Links** 

U.S. IOOS Website <u>https://ioos.noaa.gov/project/qartod/</u> 

Ocean Data Standards Pilot Project <u>http://www.oceandatastandards.org/</u> 

Hydrographic Data Formats <u>https://cchdo.github.io/hdo-assets/documentation/manuals/pdf/90_1/chap4.pdf</u> 

CF Conventions and Metadata <u>http://cfconventions.org/</u> 

Data Buoy Cooperation Panel Meta-T Pilot Project <u>https://marinemetadata.org/community/teams/metat/introduction http://www.jcommops.org/dbcp/data/metadata.html</u> 

National Centers for Environmental Information (NCEI) Metadata Training <u>https://www.ncddc.noaa.gov/metadata-standards/metadata-training/course-one/</u> 

Introduction to Oceanographic Data Management <u>http://classroom.oceanteacher.org/course/view.php?id=131</u> 

Ocean Best Practices System <u>https://obpsystem.org/</u> 

Argo Quality Control Manual for CTD and Trajectory Data Version 3.3 <u>https://archimer.ifremer.fr/doc/00228/33951/</u> 

8 

_Data QC Flags Manual_ 

## **Appendix A. QARTOD Data QC Flag Manual Team** 

|**QARTOD Data QC**|**Flag Manual Reviewers, Version 1.2**|
|---|---|
|**Name**|**Organization**|
|Jessica Austin<br>Mark Bushnell<br>Jorge Capella<br>Mike Crowley<br>Felimon Gayanilo<br>Corey Olfe<br>Teresa Updyke<br>Micah Wengren|Axiom Data Science<br>U.S. IOOS<br>CARICOOS<br>Rutgers University<br>Texas A&M University<br>University of California San Diego<br>Old Dominion University<br>U.S. IOOS|
|Darren Wright|Universityof California San Diego|
|**U.S. IOOS Reg**|**ional Associations, Version 1.2**|
|**Name**|**Organization**|
|Josie Quintrell<br>Clarissa Anderson|IOOS Association<br>SCCOOS|
|Jake Kritzer|NERACOOS|
|Debra Hernandez|SECOORA|
|Melissa Iwamoto|PacIOOS|
|Barbara Kirkpatrick|GCOOS|
|Gerhard Kuska|MARACOOS|
|Molly McCammon|AOOS|
|Julio Morell|CARICOOS|
|Jan Newton|NANOOS|
|Kelli Paige|GLOS|
|HenryRuhl|CeNCOOS|
|**QARTOD B**|**oard of Advisors, Version 1.2**|
|**Name**|**Organization**|
|Kathleen Bailey – Project Manager|U.S. IOOS|
|Julie Bosch|NOAA/National Centers for Environmental Information|
|Eugene Burger<br>Jennifer Dorton|NOAA/Pacific Marine Environmental Laboratory<br>SECOORA|
|Regina Easley<br>Robert Heitsenrether<br>Jeff King<br>Karen Grissom<br>Mario Tamburri|National Institute of Standards and Technology<br>NOS/Center for Operational Oceanographic Products and Services<br>U.S. Army Corps of Engineers<br>NOAA/National Data Buoy Center<br>University of Maryland Center for Environmental Science /<br>Chesapeake Biological Laboratory|
|Julianna Thomas – BOA Chair<br>Christoph Waldmann|SCCOOS/Scripps Institution of Oceanography/Coastal Data<br>Information Program (retired)<br>Universityof Bremen/MARUM|



A-1 

_Data QC Flags Manual_ 

|**DMAC Communit**<br>**Regional Ass**<br>|**y, Version 1.2**<br>**ociations**<br>|
|---|---|
|**AOOS**|**GCOOS**|
|Carol Janzen|Bob Currier|
|**CARICOOS**|**SECOORA**|
|Miguel Canals|Jennifer Dorton|
|Roy Watlington|Filipe Pires Alvarenga Fernandes<br>AbbeyWakely|
|**Research Organizations**||
|**Gulf of Maine Research Institute**|**Scripps Institution of Oceanography**|
|Eric Bridger|VickyRowley|
|**Monterey Bay Aquarium Research Institute**<br>Fred Bahr|**Smithsonian Environmental Research Center**<br>Matthew Ogburn|
|**Federal and State Agencies**||
|**Bureau of Ocean Energy Management**|**Environmental Protection Agency**|
|Brian Zelenke|Dwane Young|
|Jonathan Blythe||
|**Great Lakes Commission**|**U.S. Geological Survey**|
|Guan Wang|Abigail Benson<br>Sky Bristol<br>James Kreft<br>Rich Signell|
|**National Oceanic and Atmospheric Administration**||
|Tim Boyer|Jessica Morgan|
|Mark Bushnell|Kevin O'Brien|
|Gabrielle Canonico|Thomas Ryan|
|Kenneth Casey|Bob Simons|
|Lynn Dewitt|Derrick Snowden|
|Dave Easter|Tiffany Vance|
|Benjamin LaCour|Micah Wengren|
|Tony Lavoi|Bill Woodward|
|Frank Lodato||



A-2 

_Data QC Flags Manual_ 

|**Academic Institutions, Version 1.2**||
|---|---|
|**University of Maine**|Bob Fleming|
|**University of Maryland**|Mario Tamburri|
|**Dalhousie University**|Lenore Bajona<br>Brad Covey<br>Richard Davis|
|**University of Puerto Rico**|Jorge Capella<br>Juan Orlando Gonzalez Lopez|
|**University of Hawaii**|James T. Potemra|
|**University of Washington**|Emilio Mayorga|
|**Texas A & M University**|Felimon Gayanilo|
|**Rutgers University**|John Kerfoot<br>Michael Vardaro|
|**University of Tasmania**|Peter Walsh|
|**Private Industry**||
|**LimnoTech**|Kathy Koch<br>Tad Slawecki|
|**RPS Group**|Ben Adams<br>Robert Fratantonio<br>Kelly Knee<br>Brian McKenna|
|**Axiom**|Jessica Austin<br>Rob Bochenek<br>Stacey Buckelew<br>Shane StClair<br>Kyle Wilcox|
|**Ocean Tracking Network**|Jonathan Pye|
|**GMRI**|Alex Kerney|



A-3 

_Data QC Flags Manual_ 

|**QARTOD Data QC**|**Flag Manual Reviewers, Version 1.1**|
|---|---|
|**Name**|**Organization**|
|Mark Bushnell<br>Luke Campbell<br>Emilio Mayorga|U.S. IOOS<br>RPS Group<br>NANOOS/University of Washington|
|**U.S. IOOS Reg**|**ional Associations, Version 1.1**|
|**Name**|**Organization**|
|Josie Quintrell<br>Clarissa Anderson<br>Francisco Chavez<br>Debra Hernandez<br>Barbara Kirkpatrick<br>Gerhard Kuska<br>Molly McCammon<br>Julio Morell<br>Ru Morrison<br>Jan Newton<br>Melissa Iwamoto|IOOS Association<br>SCCOOS<br>CeNCOOS<br>SECOORA<br>GCOOS<br>MARACOOS<br>AOOS<br>CariCOOS<br>NERACOOS<br>NANOOS<br>PacIOOS|
|Kelli Paige|GLOS|
|**QARTOD B**|**oard of Advisors, Version 1.1**|
|**Name**|**Organization**|
|Kathleen Bailey – Project Manager<br>Julie Bosch<br>Eugene Burger<br>Janet Fredericks<br>Matt Howard<br>Bob Jensen<br>Chris Paternostro<br>Mario Tamburri<br>Julie Thomas – BOA Chair|U.S. IOOS<br>NOAA/National Centers for Environmental Information<br>NOAA/Pacific Marine Environmental Laboratory<br>Woods Hole Oceanographic Institution<br>GCOOS/Texas A&M University<br>U.S. Army Corps of Engineers<br>NOS/CO-OPS<br>University of Maryland Center for Environmental Science /<br>Chesapeake Biological Laboratory<br>SCCOOS/Scripps Institution of Oceanography/Coastal Data<br>Information Program|



A-4 

_Data QC Flags Manual_ 

### **<mark>DMAC Community, Version 1.1</mark>** 

##### **Regional Associations** 

|**AOOS**|**GCOOS**|
|---|---|
|Carol Janzen|Bob Currier|
|**CARICOOS**|**SECOORA**|
|Miguel Canals|Abbey Wakely|
|Roy Watlington|Debra Hernandez|
||Filipe Pires Alvarenga Fernandes|
|**Research Organizations**||
|**Gulf of Maine Research Institute**|**Scripps Institution of Oceanography**|
|Eric Bridger|Darren Wright|
|**Monterey Bay Aquarium Research Institute**|**Smithsonian Environmental Research Center**|
|Aric Bickel|Matthew Ogburn|
|Anderson David||
|Fred Bahr||
|**Federal and State Agencies**||
|**Bureau of Ocean Energy Management**|**Environmental Protection Agency**|
|Brian Zelenke|Dwane Young|
|Jonathan Blythe||
|**Great Lakes Commission**||
|Guan Wang||
|**National Oceanic and Atmospheric Administration**||
|Becky Baltes|Jennifer Bosch|
|Bill Woodward|Jennifer Patterson|
|Kenneth Casey|Jessica Morgan|
|Mark VanWaes|Kevin O'Brien|
|Alexander Birger|Lynn Dewitt|
|Bob Simons|Mark Bushnell|
|Byron Kilbourne|Mathew Biddle|
|Dave Easter|Micah Wengren|
|Derrick Snowden|Rita Adak|
|Eric Johnson|Robert Bassett|
|Frank Lodato|Samantha Simmons|
|Gabrielle Canonico|Thomas Ryan|
|Jack Harlan|Tiffany Vance|
|Jason Gedamke|Tim Boyer|
|Jeff de La Beaujardiere|Tony Lavoi|
|Jenifer Rhoades|Xiaoyan Li|
|**U.S. Army Corps of Engineers**|**U.S. Geological Survey**|
|Jeff Lillycrop|Abigail Benson<br>James Kreft|
||Rich Signell|
||SkyBristol|



A-5 

_Data QC Flags Manual_ 

|**Academic Instituti**|**ons, Version 1.1**||
|---|---|---|
||**University of Maine**|Bob Fleming|
||**University of Maryland**|Mario Tamburri|
||**Dalhousie University**|Brad Covey<br>Lenore Bajona<br>Richard Davis|
||**University of Puerto Rico**|Jorge Capella<br>Juan Orlando Gonzalez Lopez<br>Julio Morell|
||**University of Hawaii**|Chris Ostrander<br>James T. Potemra<br>Melissa Iwamoto|
||**University of Washington**|Emilio Mayorga|
||**Texas A & M University**|Felimon Gayanilo|
||**Rutgers University**<br>**University of Tasmania**|John Kerfoot<br>Michael Vardaro<br>Peter Walsh|
|**Private Industry**|||
||**LimnoTech**|Kathy Koch<br>Tad Slawecki|
||**RPS Group**|Kelly Knee<br>Luke Campbell<br>Melanie Gearon|
||**Axiom**|Kyle Wilcox<br>Rob Bochenek<br>Shane StClair|
||**Animal Tracking Network**|Jonathan Pye|



A-6 

_Data QC Flags Manual_ 

# **<mark>Data QC Flag Manual Editors, Version 1.0</mark>** 

|**Name**|**Organization**|
|---|---|
|Mark Bushnell, Lead|CoastalObsTechServices LLC/CO-OPS|
|Ray Toll|Old Dominion University/NDBC|
|Helen Worthington|REMSA/CO-OPS|



# **Data QC Flag Manual Reviewers/DMAC Committee,** 

# **Version 1.0** 

|**Name**|**Organization**|
|---|---|
|Rob Bochenek|AOOS/Axiom Consulting & Design|
|Julie Bosch|NOAA/NCDDC|
|Eric Bridger|NERACOOS/GMRI|
|Jorge Capella|CariCOOS/University of Puerto Rico|
|Jeremy Cothran|SECOORA|
|Janet Fredericks|WHOI|
|Lisa Hazard|SCCOOS/Scripps Institute of Oceanography|
|Bob Heitsenrether|NOAA/CO-OPS|
|Matt Howard|GCOOS/Texas A&M University|
|Steven Le|CeNCOOS/SAIC|
|Emilio Mayorga|NANOOS/University of Washington|
|Jennifer Patterson|CeNCOOS/MBARI|
|Jim Potemra|PacIOOS/University of Hawaii|
|Rob Ragsdale|U.S. IOOS|
|Tad Slawecki|GLOS/LimnoTech|
|Derrick Snowden|U.S. IOOS|
|Shane StClair|AOOS/Axiom Consulting & Design|
|Vembu Subramanian|SECOORA|
|Julie Thomas|SIO/CDIP|
|Kyle Wilcox|MARACOOS/Applied Science Associates,Inc.|



# **<u><mark>QARTOD Board of Advisors, Version 1.0</mark></u>** 

|**Name**|**Organization**|
|---|---|
|Joe Swaykos - Chair|NDBC|
|Derrick Snowden|U.S. IOOS|
|Julie Bosch|NOAA/NCDDC|
|Julie Thomas|SIO/CDIP|
|Derrick Snowden|US IOOS|
|Matt Howard|GCOOS|
|Chris Paternostro|NOAA/CO-OPS|
|Bob Jensen|USACE|
|Janet Fredericks|WHOI|



A-7 

_Data QC Flags Manual_ 

|**U.S. I**<br>|**OOS Regional Associations,**<br>**Version 1.0**<br>|
|---|---|
|**Name**|**Organization**|
|Josie Quintrell – Director<br>Leslie Rosenfeld|U.S. IOOS Association<br>CeNCOOS|
|Jan Newton|NANOOS|
|Debra Hernandez|SECOORA|
|Julie Thomas|SCCOOS|
|Ann Jochens|GCOOS|
|Gerhard Kuska|MARACOOS|
|Molly McCammon|AOOS|
|Ru Morrison|NERACOOS|
|Jorge Corridor|CariCOOS|
|Heather Kerkering|PacIOOS|
|Jen Read|GLOS|



A-8 

