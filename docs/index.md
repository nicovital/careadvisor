<!-- {!README.md!} -->

# CareAdvisor 
Technical Specification


## **Table of Contents**

Last Updated On July 11, 2022


[TOC]





# **Integration Plan**
[INTPLAN]

The ERAdvisor technical implementation process includes a number of stages for implementation, beginning with the kickoff call. Depending on the scope of data feeds for onboarding, the below plan will include additional testing and validation as required.



<p id="gdcalert1" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline drawings not supported directly from Docs. You may want to copy the inline drawing to a standalone drawing and export by reference. See <a href="https://github.com/evbacher/gd2md-html/wiki/Google-Drawings-by-reference">Google Drawings by reference</a> for details. The img URL below is a placeholder. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert2">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![drawing](https://docs.google.com/drawings/d/12345/export/png)


<table>
  <tr>
   <td>
    ●  Implementation overview
<p>
●  Identify resources
<p>

    ●  Determine method of \
connectivity
   </td>
   <td>
    ●  Establish & test connectivity
<p>

    ●  Sign-off on data feed  \
specifications
<p>

    ●  Develop & prep for  \
Testing plan
   </td>
   <td>
    ●  Complete workflows for full functionality testing
<p>

    ●  Signoff on change control
<p>

    ●  Schedule production data Go-live 
   </td>
   <td>
    ●  Validation of production data handling by app
<p>

    ●  Registration workflow validation in production
<p>
●  Turn the app live
<p>
●  Go-live completed!
   </td>
  </tr>
</table>


The technical integration typically spans 12 weeks from kickoff to official go-live depending on technical requirements for the hospital or health system. The overall implementation includes additional workstreams from an operational standpoint. That work is completed in parallel to the technical work, as overviewed below:



<p id="gdcalert2" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image1.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert3">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image1.png "image_tooltip")



# Integration Details

There are several different levels of integration with ERAdvisor available to clients, each providing additional features and functionality depending on the amount of data provided.

When choosing to go beyond the non-integrated solution, it is recommended that at least the ADT & location data be provided as this provides significantly increased patient utilization and an enhanced ED experience for patients.


## Product Features By Data Feed


<table>
  <tr>
   <td><strong>  Features</strong>
   </td>
   <td colspan="2" ><strong>Light Integration</strong>
   </td>
   <td colspan="2" ><strong>Full Integration</strong>
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td><strong>ADT</strong>
   </td>
   <td><strong>+ Locations</strong>
   </td>
   <td><strong>+ Notes</strong>
   </td>
   <td><strong>+ Orders/Results</strong>
   </td>
  </tr>
  <tr>
   <td>
      Step-by-step ED Guide
   </td>
   <td>✓
   </td>
   <td>✓
   </td>
   <td>✓
   </td>
   <td>✓
   </td>
  </tr>
  <tr>
   <td>
      Follow Up Scheduling
   </td>
   <td>✓
   </td>
   <td>✓
   </td>
   <td>✓
   </td>
   <td>✓
   </td>
  </tr>
  <tr>
   <td>
      Auto-invite via SMS
   </td>
   <td>✓
   </td>
   <td>✓
   </td>
   <td>✓
   </td>
   <td>✓
   </td>
  </tr>
  <tr>
   <td>
      Direct Messaging
   </td>
   <td>✓
   </td>
   <td>✓
   </td>
   <td>✓
   </td>
   <td>✓
   </td>
  </tr>
  <tr>
   <td>
      Follow-up Scheduling, Patient Portal
   </td>
   <td>✓
   </td>
   <td>✓
   </td>
   <td>✓
   </td>
   <td>✓
   </td>
  </tr>
  <tr>
   <td>
      Family/Friend Sharing
   </td>
   <td>✓
   </td>
   <td>✓
   </td>
   <td>✓
   </td>
   <td>✓
   </td>
  </tr>
  <tr>
   <td>
      AI Wait Times for Total LOS
   </td>
   <td>✓
   </td>
   <td>✓
   </td>
   <td>✓
   </td>
   <td>✓
   </td>
  </tr>
  <tr>
   <td>
      AI Wait Times for Bed, Discharge
   </td>
   <td>
   </td>
   <td>✓
   </td>
   <td>✓
   </td>
   <td>✓
   </td>
  </tr>
  <tr>
   <td>
      Automatic Progress through each ED Step
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>✓
   </td>
   <td>✓
   </td>
  </tr>
  <tr>
   <td>
      AI Wait Times for Triage, Secondary, Dispo
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>✓
   </td>
   <td>✓
   </td>
  </tr>
  <tr>
   <td>
      Specific Follow-up Instructions
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>✓
   </td>
   <td>✓
   </td>
  </tr>
  <tr>
   <td>
      AI Wait Times for Labs & Imaging
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>✓
   </td>
  </tr>
</table>



# Detailed Integration Feed Requirements


## MSH.6 Values

Vital is able to ingest the HL7 from your interfaces in its default form. With a full technical integration with multiple types of HL7 interfaces passing from your system to Vital, there is a recommended interface identification in MSH.6. Please see below for those recommended values and work with your Implementation Manager for concerns here.

ADT 									**MSH.6 = ADT**

Lab Feed (Orders & Results)					**MSH.6 = LAB**

Rad Feed (Orders & Results)					**MSH.6 = RAD**

Cardiology Feed (Orders & Results)				**MSH.6 = CARD**

Notes									**MSH.6 = NOTES**

Flowsheets (Nursing notes with discrete data)			**MSH.6 = FLOW**


## ADT Feed


### Key Data Elements



* Key patient identifiers (MRN, Visit Number/FIN/Encounter ID)
* Patient demographics & contacts, mobile phone is critical
* Patient visit information
* Patient location information
* Patient insurance & guarantor information
* Patient care team
* Patient & visit status


### Key Features & Benefits



* Automated patient Invite, language settings, opt-out, and authentication
* Individualized step automation
* Artificial Intelligence (AI) features for wait time estimates
* ED Outcome status
* AI features for aggregate projections, such as ED volume and busyness histogram
* Patient follow up for after-visit outreach


### Details

The ADT feed is the most critical and necessarily comprehensive of the data feeds as it is responsible for providing much of the base functionality for product features. The ADT feed is responsible for the creation of both the visit and the patient within the software, as well as providing the status of the visit and patient. The data within the ADT feed allows Vital to trigger the initial invite to the software (or opt-out if the flag is set), set the preferred language settings for the patient, and authenticate the patient to confirm identity. Throughout the visit, ADT feeds provide visit and patient updates, and allow our system to track progress throughout the visit. Key data elements also provide our AI and Machine Learning (ML) algorithms with critical features needed to produce wait time estimates.

_For more information, please refer to **Appendix A: ADT Feed Specification**_


## Room/Bed Data Extract (Optional)


### Key Data Elements



* Key patient identifiers (MRN, Visit Number/FIN/Encounter ID)
* Facility, Department, Room, and Bed, with accompanying timestamps


### Key Features & Benefits



* Individualized step automation
* AI features for wait time estimates


### Details

This feed is an optional enhancement to the ADT feed, and is only necessary if the existing ADT feed does not contain the patient’s room and bed information throughout their ED visit.

_For more information, please refer to **Appendix B: Room/Bed Data Extract Specification**_


## Diagnostic Orders Feed


### Key Data Elements



* Key patient identifiers (MRN, Visit Number/FIN/Encounter ID)
* Patient demographics
* Order control data
* Order detail data elements, including timestamps
* Diagnostic orders for laboratory, radiology, and cardiology


### Key Features & Benefits



* Diagnostic test progress tracking
* AI features for wait time estimates
* AI features for aggregate projections, such as ED volume and busyness histogram
* AI features for predictive outcomes
* Patient education


### Details

The diagnostic orders feed provides key data elements necessary to enhance the patient experience while increasing the number of AI features available for wait time estimates, aggregate projections, and predictions for patient outcomes. Knowing the orders being placed also allows enhanced patient education functionality by tailoring the information being displayed to patients, providing a more unique and customized experience.

_For more information, please refer to **Appendix C: Diagnostic Orders Feed Specification**_


## Diagnostic Results Feed


### Key Data Elements



* Key patient identifiers (MRN, Visit Number/FIN/Encounter ID)
* Patient demographics
* Order control data
* Result details
* Result status


### Key Features & Benefits



* Diagnostic test progress tracking
* AI features for wait time estimates
* AI features for predictive outcomes
* Patient education


### Details

The diagnostic results feed provides the response to the diagnostic orders. The diagnostic results allows the software to close the loop on outstanding diagnostic tests, and informs patients when the results have been made available for their care team to review. Under the hood, the individual diagnostic results provide the necessary AI features for getting more personalized wait time estimates using models specific to the diagnostic workflow. Finally, diagnostic results provide the data necessary for additional patient education.

_For more information, please refer to **Appendix D: Diagnostic Results Feed Specification**_


## Clinical Disposition Orders Feed


### Key Data Elements



* Key patient identifiers (MRN, Visit Number/FIN/Encounter ID)
* Patient demographics
* Order control data
* Order details


### Key Features & Benefits



* Individualized step automation
* AI features for wait time estimates
* Enhanced patient experience for outcome transitions


### Details

Disposition orders provide the software with the ED visit disposition the moment the order is placed by the provider care team. This allows the application to prepare the patient, in advance of the actual outcome transition, for considerations that may be necessary for the pending Admit, Observation, or Discharge outcome. There are specific AI models that look at the time of disposition in order to enhance wait time estimates as well as to provide predictions related to patient flow, both within the ED and the facility at large.

_For more information, please refer to **Appendix E: Disposition Orders Feed Specification**_


## Nursing Flowsheets


### Key Data Elements



* Key patient identifiers (MRN, Visit Number/FIN/Encounter ID)
* Patient demographics
* Chief complaint, vitals, and acuity (ESI value)
* Clinically relevant nursing notes
* Specific note types include:
    * Triage
    * Nursing assessment
    * Discharge Summary


### Key Features & Benefits



* Individualized step automation
* AI features for wait time estimates
* AI features for ESI calculation
* AI features for workflow prediction


### Details

The nursing flowsheets provide key data elements related to patient flow through the ED. A combination of the chief complaint, vitals, and assigned acuity score provides the initial bases for predicting when the patient will be taken back, as well as the expected diagnostic tests that may be ordered. Initial and updated vitals are used to internally calculate expected ESI score, which has proven to be highly effective in predicting wait times during exceptionally busy periods within the ED. Any vital updates received work to re-inform the AI models accordingly, allowing for highly specialized and individualized estimates throughout the ED visit.

_For more information, please refer to **Appendix F: Nursing Flowsheet Specification**_


## Provider Notes


### Key Data Elements



* Key patient identifiers (MRN, Visit Number/FIN/Encounter ID)
* Patient demographics
* Discrete and narrative provider notes
* Specific note types include:
    * ER History & Physical
    * Consultation Notes
    * Addendums


### Key Features & Benefits



* Individualized step automation
* AI features for wait time estimates
* Enhanced patient experience for outcome transitions
* Patient follow up for after-visit outreach
* Patient education


### Details

The provider notes contain significant data related to the patient flow, both within the ED visit as well as post-ED follow up. In addition to providing AI features related to outcome transitions, similar to disposition orders, the provider notes provide the recommendations for post-discharge care, including follow up and patient education. The software leverages Natural Language Processing (NLP) to distill the important information and bubble that up to the patient, allowing for a more informed discharge experience.

_For more information, please refer to **Appendix G: Provider Notes Specification**_




# Appendix A: ADT Feed Specification


## Supported Event Types


<table>
  <tr>
   <td><strong>Event Code</strong>
   </td>
   <td><strong>Event Type</strong>
   </td>
  </tr>
  <tr>
   <td>A01
   </td>
   <td>Admit Notification
   </td>
  </tr>
  <tr>
   <td>A02
   </td>
   <td>Patient Transfer
   </td>
  </tr>
  <tr>
   <td>A03
   </td>
   <td>Discharge/End Visit
   </td>
  </tr>
  <tr>
   <td>A04
   </td>
   <td>Register a Patient
   </td>
  </tr>
  <tr>
   <td>A05
   </td>
   <td>Pre-Admit a Patient
   </td>
  </tr>
  <tr>
   <td>A06
   </td>
   <td>Change an outpatient to an inpatient
   </td>
  </tr>
  <tr>
   <td>A07
   </td>
   <td>Change an inpatient to an outpatient
   </td>
  </tr>
  <tr>
   <td>A08
   </td>
   <td>Update patient information
   </td>
  </tr>
  <tr>
   <td>A09
   </td>
   <td>Patient departing - tracking
   </td>
  </tr>
  <tr>
   <td>A10
   </td>
   <td>Patient arriving - tracking
   </td>
  </tr>
  <tr>
   <td>A11
   </td>
   <td>Cancel admit/visit notification
   </td>
  </tr>
  <tr>
   <td>A12
   </td>
   <td>Cancel transfer
   </td>
  </tr>
  <tr>
   <td>A13
   </td>
   <td>Cancel discharge/end visit
   </td>
  </tr>
  <tr>
   <td>A14
   </td>
   <td>Pending admit
   </td>
  </tr>
  <tr>
   <td>A15
   </td>
   <td>Pending transfer
   </td>
  </tr>
  <tr>
   <td>A16
   </td>
   <td>Pending discharge
   </td>
  </tr>
  <tr>
   <td>A17
   </td>
   <td>Swap patients
   </td>
  </tr>
  <tr>
   <td>A20
   </td>
   <td>Bed status update
   </td>
  </tr>
  <tr>
   <td>A21
   </td>
   <td>Patient goes on a “leave of absence”
   </td>
  </tr>
  <tr>
   <td>A22
   </td>
   <td>Patient returns from a “leave of absence”
   </td>
  </tr>
  <tr>
   <td>A23
   </td>
   <td>Delete a patient record
   </td>
  </tr>
  <tr>
   <td>A25
   </td>
   <td>Cancel pending discharge
   </td>
  </tr>
  <tr>
   <td>A26
   </td>
   <td>Cancel pending transfer
   </td>
  </tr>
  <tr>
   <td>A27
   </td>
   <td>Cancel pending admit
   </td>
  </tr>
  <tr>
   <td>A28
   </td>
   <td>Add person information
   </td>
  </tr>
  <tr>
   <td>A29
   </td>
   <td>Delete person information
   </td>
  </tr>
  <tr>
   <td>A31
   </td>
   <td>Update person information
   </td>
  </tr>
  <tr>
   <td>A32
   </td>
   <td>Cancel patient arriving - tracking
   </td>
  </tr>
  <tr>
   <td>A33
   </td>
   <td>Cancel patient departing - tracking
   </td>
  </tr>
  <tr>
   <td>A38
   </td>
   <td>Cancel pre-admit
   </td>
  </tr>
  <tr>
   <td>A40
   </td>
   <td>Merge patient - patient identifier list
   </td>
  </tr>
  <tr>
   <td>A41
   </td>
   <td>Merge patient - patient account number
   </td>
  </tr>
  <tr>
   <td>A42
   </td>
   <td>Merge visit - visit number
   </td>
  </tr>
  <tr>
   <td>A43
   </td>
   <td>Move patient information - patient identifier list
   </td>
  </tr>
  <tr>
   <td>A44
   </td>
   <td>Move account information - patient account number
   </td>
  </tr>
  <tr>
   <td>A45
   </td>
   <td>Move visit information - visit number
   </td>
  </tr>
</table>



## Supported Segments

The following section defines the HL7 ADT segments to be included in the integration. As mentioned above, the goal is to integrate the full, unfiltered ADT feed including all message types, segments, and data fields available out of your registration system.

**Optionality Values**



* **Required** for app functionality
* **Recommended** for an enhanced app experience
* **Optional** and low impact if absent from the message

<table>
  <tr>
   <td>
<strong>Segment Code</strong>
   </td>
   <td><strong>Segment Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>MSH
   </td>
   <td>

<p id="gdcalert3" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Message Header Segment"). Did you generate a TOC with blue links? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert4">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

<a href="#heading=h.jcgw1d1czai4">Message Header Segment</a>
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>EVN
   </td>
   <td>

<p id="gdcalert4" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Event Type"). Did you generate a TOC with blue links? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert5">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

<a href="#heading=h.nbmax1iowzqr">Event Type</a>
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>PID
   </td>
   <td>

<p id="gdcalert5" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Patient Identification"). Did you generate a TOC with blue links? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert6">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

<a href="#heading=h.8zp5tvpyw2n">Patient Identification</a>
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PD1
   </td>
   <td>

<p id="gdcalert6" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Patient Additional Demographic"). Did you generate a TOC with blue links? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert7">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

<a href="#heading=h.adlg4rthbcgt">Patient Additional Demographic</a>
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>NK1
   </td>
   <td>

<p id="gdcalert7" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Next of Kin"). Did you generate a TOC with blue links? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert8">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

<a href="#heading=h.zeco4swum7o7">Next of Kin</a>
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1
   </td>
   <td>

<p id="gdcalert8" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Patient Visit"). Did you generate a TOC with blue links? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert9">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

<a href="#heading=h.u1dt2jkhg57i">Patient Visit</a>
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PV2
   </td>
   <td>

<p id="gdcalert9" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Patient Visit - Additional Info"). Did you generate a TOC with blue links? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert10">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

<a href="#heading=h.g2mrznghurzg">Patient Visit - Additional Info</a>
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBX
   </td>
   <td>

<p id="gdcalert10" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Observation/Result"). Did you generate a TOC with blue links? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert11">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

<a href="#heading=h.xowdxa3dx5ds">Observation/Result</a>
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>AL1
   </td>
   <td>

<p id="gdcalert11" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Allergy Information"). Did you generate a TOC with blue links? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert12">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

<a href="#heading=h.e90mhgypjmf7">Allergy Information</a>
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>DG1
   </td>
   <td>

<p id="gdcalert12" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Diagnosis Information"). Did you generate a TOC with blue links? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert13">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

<a href="#heading=h.t650n26pmdar">Diagnosis Information</a>
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PR1
   </td>
   <td>

<p id="gdcalert13" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Procedures"). Did you generate a TOC with blue links? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert14">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

<a href="#heading=h.7k8qfnt11ed3">Procedures</a>
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ROL
   </td>
   <td>

<p id="gdcalert14" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Role"). Did you generate a TOC with blue links? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert15">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

<a href="#heading=h.rqrd1ss0ao9x">Role</a>
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>GT1
   </td>
   <td>

<p id="gdcalert15" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Guarantor"). Did you generate a TOC with blue links? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert16">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

<a href="#heading=h.guxv04ecetqt">Guarantor</a>
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN1
   </td>
   <td>

<p id="gdcalert16" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Insurance"). Did you generate a TOC with blue links? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert17">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

<a href="#heading=h.epaczk3kq6yb">Insurance</a>
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN2
   </td>
   <td>

<p id="gdcalert17" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Insurance Additional Information"). Did you generate a TOC with blue links? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert18">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

<a href="#heading=h.e4ztyh61lzz">Insurance Additional Information</a>
   </td>
   <td>Recommended
   </td>
  </tr>
</table>





# Appendix B: Room/Bed Data Extract Specification

This section details the proposed custom export that may be recommended based on the data fidelity of patient location information in the standard ADT feed.

The output can use the column names provided, or custom names can be provided as well. Additional details are as follows:



* Runs every 5 - 15 minutes
* Should include ED patient location information for the past 1 hour
* Output should be a comma-separated values list, or .csv
* Individual values should be surrounded by quotation marks (“)
* Individual values should be separated by commas (,)
* All leading and trailing spaces should be eliminated
* All records should be separated by a new line character
* The first row in the file should be the header row

<table>
  <tr>
   <td>
<strong>Column Name</strong>
   </td>
   <td><strong>Data Element</strong>
   </td>
   <td><strong>Data Format</strong>
   </td>
  </tr>
  <tr>
   <td>MRN
   </td>
   <td>Patient’s Medical Record Number
   </td>
   <td>string
   </td>
  </tr>
  <tr>
   <td>Visit_ID
   </td>
   <td>The Visit ID, or Encounter ID, associated with the patient’s visit
   </td>
   <td>string
   </td>
  </tr>
  <tr>
   <td>Facility
   </td>
   <td>The facility for the patient’s location record
   </td>
   <td>string
   </td>
  </tr>
  <tr>
   <td>Department
   </td>
   <td>The department or unit for the patient’s location record
   </td>
   <td>string
   </td>
  </tr>
  <tr>
   <td>Room
   </td>
   <td>The room for the patient’s location record. This can also include non-treatment locations such as the ED waiting room and Checkout “locations”
   </td>
   <td>string
   </td>
  </tr>
  <tr>
   <td>Bed
   </td>
   <td>The bed (if available) for the patient’s location record
   </td>
   <td>string
   </td>
  </tr>
  <tr>
   <td>DateTimeUpdated
   </td>
   <td>The timestamp for the patient’s location record
   </td>
   <td>Timestamp
<p>
<em>multiple formats are acceptable</em>
<p>
mm/dd/yyyy HH:MM:ss
<p>
yyyy-mm-dd HH:MM:ss
   </td>
  </tr>
</table>





# Appendix C: Diagnostic Orders Specification


## Supported Event Types


<table>
  <tr>
   <td><strong>Event Code</strong>
   </td>
   <td><strong>Event Type</strong>
   </td>
  </tr>
  <tr>
   <td>O01
   </td>
   <td>Order Message
   </td>
  </tr>
</table>



## Supported Segments

The following section defines the HL7 ORM segments to be included in the integration. 

**Optionality Values**



* **Required** for app functionality
* **Recommended** for an enhanced app experience
* **Optional** and low impact if absent from the message

<table>
  <tr>
   <td>
<strong>Segment Code</strong>
   </td>
   <td><strong>Segment Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>MSH
   </td>
   <td>

<p id="gdcalert18" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Message Header Segment"). Did you generate a TOC with blue links? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert19">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

<a href="#heading=h.jcgw1d1czai4">Message Header Segment</a>
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PID
   </td>
   <td>Patient Identification
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PD1
   </td>
   <td>Patient Additional Demographic
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1
   </td>
   <td>Patient Visit
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PV2
   </td>
   <td>Patient Visit - Additional Information
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN1
   </td>
   <td>Insurance
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN2
   </td>
   <td>Insurance Additional Information
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>GT1
   </td>
   <td>Guarantor
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>AL1
   </td>
   <td>Patient Allergy Information
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ORC
   </td>
   <td>Common Order
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>OBR
   </td>
   <td>Observation Request
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>RQD
   </td>
   <td>Requisition Detail
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>RQ1
   </td>
   <td>Requisition Detail-1
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>RXO
   </td>
   <td>Pharmacy/Treatment Order
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ODS
   </td>
   <td>Dietary Orders, Supplements, and Preferences
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ODT
   </td>
   <td>Diet Tray Instructions
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>DG1
   </td>
   <td>Diagnosis
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBX
   </td>
   <td>Observation/Result
   </td>
   <td>Recommended
   </td>
  </tr>
</table>



# Appendix D: Diagnostic Results Specification


## Supported Event Types


<table>
  <tr>
   <td><strong>Event Code</strong>
   </td>
   <td><strong>Event Type</strong>
   </td>
  </tr>
  <tr>
   <td>R01
   </td>
   <td>Unsolicited transmission of an observation message
   </td>
  </tr>
  <tr>
   <td>R30
   </td>
   <td>Unsolicited Point-Of-Care Observation Message without Existing Order - Place An Order
   </td>
  </tr>
</table>



## Supported Segments

The following section defines the HL7 ORU segments to be included in the integration. 

**Optionality Values**



* **Required** for app functionality
* **Recommended** for an enhanced app experience
* **Optional** and low impact if absent from the message

<table>
  <tr>
   <td>
<strong>Segment Code</strong>
   </td>
   <td><strong>Segment Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>MSH
   </td>
   <td>

<p id="gdcalert19" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Message Header Segment"). Did you generate a TOC with blue links? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert20">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

<a href="#heading=h.jcgw1d1czai4">Message Header Segment</a>
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PID
   </td>
   <td>Patient Identification
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PD1
   </td>
   <td>Patient Additional Demographic
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1
   </td>
   <td>Patient Visit
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PV2
   </td>
   <td>Patient Visit - Additional Information
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ORC
   </td>
   <td>Common Order
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>OBR
   </td>
   <td>Observation Request
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>CTD
   </td>
   <td>Contact Data
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>FT1
   </td>
   <td>Financial Transaction
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>CTI
   </td>
   <td>Clinical Trial Identification
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TQ1
   </td>
   <td>Timing/Quantity
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TQ2
   </td>
   <td>Timing/Quantity Relationship
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBX
   </td>
   <td>Observation/Result
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>SPM
   </td>
   <td>Specimen
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>NTE
   </td>
   <td>Notes and Comments
   </td>
   <td>Recommended
   </td>
  </tr>
</table>



# Appendix E: Disposition Orders Specification


## Supported Event Types


<table>
  <tr>
   <td><strong>Event Code</strong>
   </td>
   <td><strong>Event Type</strong>
   </td>
  </tr>
  <tr>
   <td>O01
   </td>
   <td>Order Message
   </td>
  </tr>
</table>



## Supported Segments

The following section defines the HL7 ORM segments to be included in the integration. 

**Optionality Values**



* **Required** for app functionality
* **Recommended** for an enhanced app experience
* **Optional** and low impact if absent from the message

<table>
  <tr>
   <td>
<strong>Segment Code</strong>
   </td>
   <td><strong>Segment Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>MSH
   </td>
   <td>

<p id="gdcalert20" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Message Header Segment"). Did you generate a TOC with blue links? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert21">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

<a href="#heading=h.jcgw1d1czai4">Message Header Segment</a>
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PID
   </td>
   <td>Patient Identification
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PD1
   </td>
   <td>Patient Additional Demographic
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1
   </td>
   <td>Patient Visit
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PV2
   </td>
   <td>Patient Visit - Additional Information
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN1
   </td>
   <td>Insurance
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN2
   </td>
   <td>Insurance Additional Information
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>GT1
   </td>
   <td>Guarantor
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>AL1
   </td>
   <td>Patient Allergy Information
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ORC
   </td>
   <td>Common Order
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>OBR
   </td>
   <td>Observation Request
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>RQD
   </td>
   <td>Requisition Detail
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>RQ1
   </td>
   <td>Requisition Detail-1
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>RXO
   </td>
   <td>Pharmacy/Treatment Order
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ODS
   </td>
   <td>Dietary Orders, Supplements, and Preferences
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ODT
   </td>
   <td>Diet Tray Instructions
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>DG1
   </td>
   <td>Diagnosis
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBX
   </td>
   <td>Observation/Result
   </td>
   <td>Recommended
   </td>
  </tr>
</table>



# Appendix F: Nursing Flowsheets Specification


## Supported Event Types


<table>
  <tr>
   <td><strong>Event Code</strong>
   </td>
   <td><strong>Event Type</strong>
   </td>
  </tr>
  <tr>
   <td>R01
   </td>
   <td>Unsolicited transmission of an observation message
   </td>
  </tr>
  <tr>
   <td>T01
   </td>
   <td>Original document notification
   </td>
  </tr>
  <tr>
   <td>T02
   </td>
   <td>Original document notification and content
   </td>
  </tr>
  <tr>
   <td>T03
   </td>
   <td>Document status change notification
   </td>
  </tr>
  <tr>
   <td>T04
   </td>
   <td>Document status change notification and content
   </td>
  </tr>
  <tr>
   <td>T05
   </td>
   <td>Document addendum notification
   </td>
  </tr>
  <tr>
   <td>T06
   </td>
   <td>Document addendum notification and content
   </td>
  </tr>
  <tr>
   <td>T07
   </td>
   <td>Document edit notification
   </td>
  </tr>
  <tr>
   <td>T08
   </td>
   <td>Document edit notification and content
   </td>
  </tr>
  <tr>
   <td>T09
   </td>
   <td>Document replacement notification
   </td>
  </tr>
  <tr>
   <td>T10
   </td>
   <td>Document replacement notification and content
   </td>
  </tr>
  <tr>
   <td>T11
   </td>
   <td>Original document notification
   </td>
  </tr>
</table>



## Supported Segments - ORU

The following section defines the HL7 ORU segments to be included in the integration. 

**Optionality Values**



* **Required** for app functionality
* **Recommended** for an enhanced app experience
* **Optional** and low impact if absent from the message

<table>
  <tr>
   <td>
<strong>Segment Code</strong>
   </td>
   <td><strong>Segment Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>MSH
   </td>
   <td>

<p id="gdcalert21" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Message Header Segment"). Did you generate a TOC with blue links? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert22">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

<a href="#heading=h.jcgw1d1czai4">Message Header Segment</a>
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PID
   </td>
   <td>Patient Identification
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PD1
   </td>
   <td>Patient Additional Demographic
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1
   </td>
   <td>Patient Visit
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>ORC
   </td>
   <td>Common Order
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>OBR
   </td>
   <td>Observation Request
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>DG1
   </td>
   <td>Diagnosis
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>OBX
   </td>
   <td>Observation/Result
   </td>
   <td>Recommended
   </td>
  </tr>
</table>



## Supported Segments - MDM

The following section defines the HL7 MDM segments to be included in the integration. 

**Optionality Values**



* **Required** for app functionality
* **Recommended** for an enhanced app experience
* **Optional** and low impact if absent from the message

<table>
  <tr>
   <td>
<strong>Segment Code</strong>
   </td>
   <td><strong>Segment Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>MSH
   </td>
   <td>

<p id="gdcalert22" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Message Header Segment"). Did you generate a TOC with blue links? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert23">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

<a href="#heading=h.jcgw1d1czai4">Message Header Segment</a>
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PID
   </td>
   <td>Patient Identification
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PD1
   </td>
   <td>Patient Additional Demographic
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1
   </td>
   <td>Patient Visit
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>ORC
   </td>
   <td>Common Order
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>OBR
   </td>
   <td>Observation Request
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>TQ1
   </td>
   <td>Timing/Quantity
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TQ2
   </td>
   <td>Timing/Quantity Relationship
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TXA
   </td>
   <td>Transcription Document Header
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBX
   </td>
   <td>Observation/Result
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>NTE
   </td>
   <td>Notes and Comments
   </td>
   <td>Recommended
   </td>
  </tr>
</table>





# Appendix G: Provider Notes Specification


## Supported Event Types


<table>
  <tr>
   <td><strong>Event Code</strong>
   </td>
   <td><strong>Event Type</strong>
   </td>
  </tr>
  <tr>
   <td>R01
   </td>
   <td>Unsolicited transmission of an observation message
   </td>
  </tr>
  <tr>
   <td>T01
   </td>
   <td>Original document notification
   </td>
  </tr>
  <tr>
   <td>T02
   </td>
   <td>Original document notification and content
   </td>
  </tr>
  <tr>
   <td>T03
   </td>
   <td>Document status change notification
   </td>
  </tr>
  <tr>
   <td>T04
   </td>
   <td>Document status change notification and content
   </td>
  </tr>
  <tr>
   <td>T05
   </td>
   <td>Document addendum notification
   </td>
  </tr>
  <tr>
   <td>T06
   </td>
   <td>Document addendum notification and content
   </td>
  </tr>
  <tr>
   <td>T07
   </td>
   <td>Document edit notification
   </td>
  </tr>
  <tr>
   <td>T08
   </td>
   <td>Document edit notification and content
   </td>
  </tr>
  <tr>
   <td>T09
   </td>
   <td>Document replacement notification
   </td>
  </tr>
  <tr>
   <td>T10
   </td>
   <td>Document replacement notification and content
   </td>
  </tr>
  <tr>
   <td>T11
   </td>
   <td>Original document notification
   </td>
  </tr>
</table>



## Supported Segments - ORU

The following section defines the HL7 ORU segments to be included in the integration. 

**Optionality Values**



* **Required** for app functionality
* **Recommended** for an enhanced app experience
* **Optional** and low impact if absent from the message

<table>
  <tr>
   <td>
<strong>Segment Code</strong>
   </td>
   <td><strong>Segment Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>MSH
   </td>
   <td>

<p id="gdcalert23" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Message Header Segment"). Did you generate a TOC with blue links? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert24">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

<a href="#heading=h.jcgw1d1czai4">Message Header Segment</a>
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PID
   </td>
   <td>Patient Identification
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PD1
   </td>
   <td>Patient Additional Demographic
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1
   </td>
   <td>Patient Visit
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>ORC
   </td>
   <td>Common Order
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>OBR
   </td>
   <td>Observation Request
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>DG1
   </td>
   <td>Diagnosis
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>OBX
   </td>
   <td>Observation/Result
   </td>
   <td>Recommended
   </td>
  </tr>
</table>



## Supported Segments - MDM

The following section defines the HL7 MDM segments to be included in the integration. 

**Optionality Values**



* **Required** for app functionality
* **Recommended** for an enhanced app experience
* **Optional** and low impact if absent from the message

<table>
  <tr>
   <td>
<strong>Segment Code</strong>
   </td>
   <td><strong>Segment Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>MSH
   </td>
   <td>

<p id="gdcalert24" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Message Header Segment"). Did you generate a TOC with blue links? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert25">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

<a href="#heading=h.jcgw1d1czai4">Message Header Segment</a>
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PID
   </td>
   <td>Patient Identification
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PD1
   </td>
   <td>Patient Additional Demographic
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1
   </td>
   <td>Patient Visit
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>ORC
   </td>
   <td>Common Order
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>OBR
   </td>
   <td>Observation Request
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>TQ1
   </td>
   <td>Timing/Quantity
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TQ2
   </td>
   <td>Timing/Quantity Relationship
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TXA
   </td>
   <td>Transcription Document Header
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBX
   </td>
   <td>Observation/Result
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>NTE
   </td>
   <td>Notes and Comments
   </td>
   <td>Recommended
   </td>
  </tr>
</table>





# Appendix H: Segment & Field Specification

The below specifications are not meant to be an exhaustive list of fields. The primary purpose of these resources is to identify what data elements are:



* **Required** for app functionality
* **Recommended** for an enhanced app experience
* **Optional** and low impact if absent from the message

Please note: If a segment or field is not identified, then it is to be considered **Optional**.


## MSH - Message Header Segment


<table>
  <tr>
   <td><strong>Field Code</strong>
   </td>
   <td><strong>Field Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>MSH.1
   </td>
   <td>Field Separator
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>MSH.2
   </td>
   <td>Encoding Characters
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>MSH.3
   </td>
   <td>Sending Application
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>MSH.4
   </td>
   <td>Sending Facility
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>MSH.5
   </td>
   <td>Receiving Application
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>MSH.6
   </td>
   <td>Receiving Facility
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>MSH.7
   </td>
   <td>Date/Time of Message
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>MSH.8
   </td>
   <td>Security
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>MSH.9
   </td>
   <td>Message Type^Event Type
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>MSH.10
   </td>
   <td>Message Control ID
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>MSH.11
   </td>
   <td>Processing ID [ ‘D’ | ‘T’ | ‘P’ ]
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>MSH.12
   </td>
   <td>Version ID
   </td>
   <td>Required
   </td>
  </tr>
</table>



## 


## PID - Patient Identification Segment


<table>
  <tr>
   <td><strong>Field Code</strong>
   </td>
   <td><strong>Field Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>PID.1
   </td>
   <td>Set ID
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PID.2
   </td>
   <td>Patient ID
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PID.3
   </td>
   <td>Patient Identifier List
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PID.4
   </td>
   <td>Alternate Patient ID
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PID.5
   </td>
   <td>Patient Name
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PID.6
   </td>
   <td>Mother’s Maiden Name
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>PID.7
   </td>
   <td>Date/Time of Birth
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PID.8
   </td>
   <td>Administrative Sex
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>PID.9
   </td>
   <td>Patient Alias
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PID.10
   </td>
   <td>Race
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>PID.11
   </td>
   <td>Patient Address
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PID.12
   </td>
   <td>Country Code
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>PID.13
   </td>
   <td>Phone - Home
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PID.14
   </td>
   <td>Phone - Business
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>PID.15
   </td>
   <td>Primary Language
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PID.16
   </td>
   <td>Marital Status
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>PID.17
   </td>
   <td>Religion
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PID.18
   </td>
   <td>Patient Account Number
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>PID.29
   </td>
   <td>Patient Death Date/Time
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PID.30
   </td>
   <td>Patient Death Indicator
   </td>
   <td>Required
   </td>
  </tr>
</table>



## 


## PD1 - Patient Additional Demographics Segment


<table>
  <tr>
   <td><strong>Field Code</strong>
   </td>
   <td><strong>Field Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>PD1.1
   </td>
   <td>Living Dependency
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>PD1.3
   </td>
   <td>Patient Primary Facility
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>PD1.4
   </td>
   <td>Patient Primary Care Provider
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PD1.5
   </td>
   <td>Student Indicator
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>PD1.10
   </td>
   <td>Duplicate Patient
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PD1.12
   </td>
   <td>Protection Indicator
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PD1.13
   </td>
   <td>Protection Indicator Effective Date
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PD1.14
   </td>
   <td>Place of Worship
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PD1.15
   </td>
   <td>Advance Directive Code
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PD1.16
   </td>
   <td>Immunization Registry Status
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>PD1.17
   </td>
   <td>Immunization Registry Effective Date
   </td>
   <td>Optional
   </td>
  </tr>
</table>



## NK1 - Next of Kin Segment


<table>
  <tr>
   <td><strong>Field Code</strong>
   </td>
   <td><strong>Field Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>NK1.1
   </td>
   <td>Set ID
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>NK1.2
   </td>
   <td>Name
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>NK1.3
   </td>
   <td>Relationship
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>NK1.4
   </td>
   <td>Address
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>NK1.5
   </td>
   <td>Phone Number
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>NK1.6
   </td>
   <td>Business Phone Number
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>NK1.7
   </td>
   <td>Contact Role
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>NK1.8
   </td>
   <td>Start Date
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>NK1.9
   </td>
   <td>End Date
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>NK1.20
   </td>
   <td>Primary Language
   </td>
   <td>Recommended
   </td>
  </tr>
</table>



## 


## PV1 - Patient Visit Segment


<table>
  <tr>
   <td><strong>Field Code</strong>
   </td>
   <td><strong>Field Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>PV1.1
   </td>
   <td>Set ID
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PV1.2
   </td>
   <td>Patient Class
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PV1.3
   </td>
   <td>Assigned Patient Location
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>    PV1.3.1
   </td>
   <td>Point of Care
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>    PV1.3.2
   </td>
   <td>Room
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>    PV1.3.3
   </td>
   <td>Bed
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>    PV1.3.4
   </td>
   <td>Facility
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>    PV1.3.5
   </td>
   <td>Location Status
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>    PV1.3.6
   </td>
   <td>Person Location Type
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>    PV1.3.7
   </td>
   <td>Building
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.4
   </td>
   <td>Admission Type
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.5
   </td>
   <td>Preadmit Number
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>PV1.6
   </td>
   <td>Prior Patient Location
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.7
   </td>
   <td>Attending Doctor
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.8
   </td>
   <td>Referring Doctor
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.9
   </td>
   <td>Consulting Doctor
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.10
   </td>
   <td>Hospital Service
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.11
   </td>
   <td>Temporary Location
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.12
   </td>
   <td>Preadmit Test Indicator
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.13
   </td>
   <td>Re-admission Indicator
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.14
   </td>
   <td>Admit Source
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.15
   </td>
   <td>Ambulatory Status
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.16
   </td>
   <td>VIP Indicator
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.17
   </td>
   <td>Admitting Doctor
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.18
   </td>
   <td>Patient Type
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.19
   </td>
   <td>Visit Number
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.34
   </td>
   <td>Delete Account Indicator
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.35
   </td>
   <td>Delete Account Date
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.36
   </td>
   <td>Discharge Disposition
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.37
   </td>
   <td>Discharged To Location
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.39
   </td>
   <td>Servicing Facility
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.40
   </td>
   <td>Bed Status
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.41
   </td>
   <td>Account Status
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.42
   </td>
   <td>Pending Location
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.43
   </td>
   <td>Prior Temporary Location
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.44
   </td>
   <td>Admit Date/Time
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.45
   </td>
   <td>Discharge Date/Time
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV1.50
   </td>
   <td>Alternate Visit ID
   </td>
   <td>Optional
   </td>
  </tr>
</table>



## PV2 - Patient Visit Additional Information Segment


<table>
  <tr>
   <td><strong>Field Code</strong>
   </td>
   <td><strong>Field Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>PV2.1
   </td>
   <td>Prior Pending Location
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV2.2
   </td>
   <td>Accomodation Code
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV2.3
   </td>
   <td>Admit Reason
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>PV2.4
   </td>
   <td>Transfer Reason
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV2.7
   </td>
   <td>Visit user Code
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV2.8
   </td>
   <td>Expected Admit Date/Time
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>PV2.9
   </td>
   <td>Expected Discharge Date/Time
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>PV2.12
   </td>
   <td>Visit Description
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV2.13
   </td>
   <td>Referral Source Code
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV2.14
   </td>
   <td>Previous Service Date
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV2.16
   </td>
   <td>Purge Status Code
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>PV2.17
   </td>
   <td>Purge Status Date
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>PV2.18
   </td>
   <td>Special Program Code
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>PV2.19
   </td>
   <td>Retention Indicator
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>PV2.20
   </td>
   <td>Expected Number of Insurance Plans
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV2.22
   </td>
   <td>Visit Protection indicator
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV2.23
   </td>
   <td>Clinical Organization Name
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>PV2.24
   </td>
   <td>Patient Status Code
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV2.25
   </td>
   <td>Visit Priority Code
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV2.26
   </td>
   <td>Previous Treatment Date
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV2.27
   </td>
   <td>Expected Discharge Disposition
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV2.29
   </td>
   <td>First Similar Illness Date
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>PV2.33
   </td>
   <td>Expected Surgery Date/Time
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV2.38
   </td>
   <td>Mode of Arrival Code
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV2.39
   </td>
   <td>Recreational Drug Use Code
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>PV2.40
   </td>
   <td>Admission Level of Care Code
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV2.41
   </td>
   <td>Precaution Code
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>PV2.42
   </td>
   <td>Patient Condition Code
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>PV2.45
   </td>
   <td>Advance Directive Code
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>PV2.46
   </td>
   <td>Patient Status Effective Date
   </td>
   <td>Recommended
   </td>
  </tr>
</table>



## AL1 - Patient Allergy Information Segment


<table>
  <tr>
   <td><strong>Field Code</strong>
   </td>
   <td><strong>Field Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>AL1.1
   </td>
   <td>Set ID
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>AL1.2
   </td>
   <td>Allergen Type Code
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>AL1.3
   </td>
   <td>Allergen Code/Mnemonic/Description
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>AL1.4
   </td>
   <td>Allergy Severity Code
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>AL1.5
   </td>
   <td>Allergy Reaction Code
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>AL1.6
   </td>
   <td>Identification Date
   </td>
   <td>Recommended
   </td>
  </tr>
</table>



## DG1 - Diagnosis Segment


<table>
  <tr>
   <td><strong>Field Code</strong>
   </td>
   <td><strong>Field Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>DG1.1
   </td>
   <td>Set ID
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>DG1.2
   </td>
   <td>Diagnosis Coding Method
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>DG1.3
   </td>
   <td>Diagnosis Code
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>DG1.4
   </td>
   <td>Diagnosis Description
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>DG1.5
   </td>
   <td>Diagnosis Date/Time
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>DG1.6
   </td>
   <td>Diagnosis Type
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>DG1.7
   </td>
   <td>Major Diagnostic Category
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>DG1.8
   </td>
   <td>Diagnostic Related Group
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>DG1.9
   </td>
   <td>Drg Approval Indicator
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>DG1.10
   </td>
   <td>Drg Grouper Review Code
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>DG1.15
   </td>
   <td>Diagnosis Priority
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>DG1.16
   </td>
   <td>Diagnosing Clinician
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>DG1.17
   </td>
   <td>Diagnosis Classification
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>DG1.18
   </td>
   <td>Confidential Indicator
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>DG1.19
   </td>
   <td>Attestation Date/Time
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>DG1.20
   </td>
   <td>Diagnosis Identifier
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>DG1.21
   </td>
   <td>Diagnosis Action Code
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>DG1.22
   </td>
   <td>Parent Diagnosis
   </td>
   <td>Optional
   </td>
  </tr>
</table>



## GT1 - Guarantor Segment


<table>
  <tr>
   <td><strong>Field Code</strong>
   </td>
   <td><strong>Field Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>GT1.1
   </td>
   <td>Set ID
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>GT1.2
   </td>
   <td>Guarantor Number
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>GT1.3
   </td>
   <td>Guarantor Name
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>GT1.4
   </td>
   <td>Guarantor Spouse Name
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>GT1.5
   </td>
   <td>Guarantor Address
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>GT1.6
   </td>
   <td>Guarantor Phone Number - Home
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>GT1.7
   </td>
   <td>Guarantor Phone Number - Business
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>GT1.8
   </td>
   <td>Guarantor Date/Time of Birth
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>GT1.9
   </td>
   <td>Guarantor Administrative Sex
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>GT1.10
   </td>
   <td>Guarantor Type
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>GT1.11
   </td>
   <td>Guarantor Relationship
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>GT1.13
   </td>
   <td>Guarantor Date Begin
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>GT1.14
   </td>
   <td>Guarantor Date End
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>GT1.15
   </td>
   <td>Guarantor Priority
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>GT1.24
   </td>
   <td>Guarantor Death Date/Time
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>GT1.25
   </td>
   <td>Guarantor Death Flag
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>GT1.36
   </td>
   <td>Guarantor Primary Language
   </td>
   <td>Recommended
   </td>
  </tr>
</table>



## 


## IN1 - Insurance Segment


<table>
  <tr>
   <td><strong>Field Code</strong>
   </td>
   <td><strong>Field Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>IN1.1
   </td>
   <td>Set ID
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>IN1.2
   </td>
   <td>Health Plan ID
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>IN1.3
   </td>
   <td>Insurance Company ID
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>IN1.4
   </td>
   <td>Insurance Company Name
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN1.5
   </td>
   <td>Insurance Company Address
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN1.6
   </td>
   <td>Insurance Company Contact Person
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>IN1.7
   </td>
   <td>Insurance Company Phone Number
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>IN1.8
   </td>
   <td>Group Number
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>IN1.9
   </td>
   <td>Group Name
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN1.10
   </td>
   <td>Insured’s group Employee ID
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>IN1.11
   </td>
   <td>Insured’s Group Employee Name
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>IN1.12
   </td>
   <td>Plan Effective Date
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN1.13
   </td>
   <td>Plan Expiration Date
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN1.14
   </td>
   <td>Authorization Information
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>IN1.15
   </td>
   <td>Plan Type
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN1.16
   </td>
   <td>Name of Insured
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN1.17
   </td>
   <td>Insured’s Relationship To Patient
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN1.18
   </td>
   <td>Insured’s Date Of Birth
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>IN1.19
   </td>
   <td>Insured’s Address
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>IN1.20
   </td>
   <td>Assignment Of Benefits
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>IN1.21
   </td>
   <td>Coordination of Benefits Priority
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>IN1.22
   </td>
   <td>Notice of Admission Flag
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN1.23
   </td>
   <td>Notice of Admission Date
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN1.28
   </td>
   <td>Verification Date/Time
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN1.29
   </td>
   <td>Verification By
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN1.35
   </td>
   <td>Company Plan Code
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN1.36
   </td>
   <td>Policy Number
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN1.45
   </td>
   <td>Verification Status
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN1.46
   </td>
   <td>Prior Insurance Plan ID
   </td>
   <td>Recommended
   </td>
  </tr>
</table>



## 


## IN2 - Insurance Additional Information Segment


<table>
  <tr>
   <td><strong>Field Code</strong>
   </td>
   <td><strong>Field Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>IN2.1
   </td>
   <td>Insured’s Employee ID
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN2.2
   </td>
   <td>Insured’s Social Security Number
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>IN2.3
   </td>
   <td>Insured’s Employer’s Name & ID
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN2.4
   </td>
   <td>Employer Information Data
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN2.5
   </td>
   <td>Mail Claim Party
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>IN2.6
   </td>
   <td>Medicare Health Insurance Card Number
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN2.7
   </td>
   <td>Medicaid Case Name
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN2.8
   </td>
   <td>Medicaid Case Number
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN2.9
   </td>
   <td>Military Sponsor Name
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN2.10
   </td>
   <td>Military ID Number
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN2.11
   </td>
   <td>Dependent of Military Recipient
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN2.25
   </td>
   <td>Payor ID
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN2.26
   </td>
   <td>Payor Subscriber ID
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN2.32
   </td>
   <td>Ambulatory Status
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN2.34
   </td>
   <td>Primary Language
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN2.37
   </td>
   <td>Protection Indicator
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN2.38
   </td>
   <td>Student Indicator
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN2.39
   </td>
   <td>Religion
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN2.44
   </td>
   <td>Insured’s Employment Start Date
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN2.45
   </td>
   <td>Employment Stop Date
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN2.59
   </td>
   <td>Policy Scope
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>IN2.60
   </td>
   <td>Policy Source
   </td>
   <td>Recommended
   </td>
  </tr>
</table>



## ORC - Common Order Segment


<table>
  <tr>
   <td><strong>Field Code</strong>
   </td>
   <td><strong>Field Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>ORC.1
   </td>
   <td>Order Control
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ORC.2
   </td>
   <td>Placer Order Number
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>ORC.3
   </td>
   <td>Filler Order Number
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ORC.4
   </td>
   <td>Placer Group Number
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ORC.5
   </td>
   <td>Order status
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>ORC.6
   </td>
   <td>Response Flag
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ORC.7
   </td>
   <td>Quantity/Timing
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ORC.8
   </td>
   <td>Parent Order
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ORC.9
   </td>
   <td>Date/Time of Transaction
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>ORC.10
   </td>
   <td>Entered By
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ORC.11
   </td>
   <td>Verified By
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ORC.12
   </td>
   <td>Ordering Provider
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ORC.13
   </td>
   <td>Enterer’s Location
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>ORC.14
   </td>
   <td>Call Back Phone Number
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>ORC.15
   </td>
   <td>Order Effective Date/Time
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ORC.16
   </td>
   <td>Order Control Code Reason
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ORC.17
   </td>
   <td>Entering Organization
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ORC.18
   </td>
   <td>Entering Device
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ORC.19
   </td>
   <td>Action By
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>ORC.20
   </td>
   <td>Advanced Beneficiary Notice Code
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>ORC.21
   </td>
   <td>Ordering Facility Name
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ORC.22
   </td>
   <td>Ordering Facility Address
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ORC.23
   </td>
   <td>Ordering Facility Phone Number
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ORC.24
   </td>
   <td>Ordering Provider Address
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ORC.25
   </td>
   <td>Order Status Modifier
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ORC.26
   </td>
   <td>Advanced Beneficiary Notice Override Reason
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>ORC.27
   </td>
   <td>Filler’s Expected Availability Date/Time
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>ORC.28
   </td>
   <td>Confidentiality Code
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ORC.29
   </td>
   <td>Order Type
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>ORC.30
   </td>
   <td>Enterer Authorization Mode
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>ORC.31
   </td>
   <td>Parent Universal Service Identifier
   </td>
   <td>Optional
   </td>
  </tr>
</table>



## OBR - Observation Request Segment


<table>
  <tr>
   <td><strong>Field Code</strong>
   </td>
   <td><strong>Field Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>OBR.1
   </td>
   <td>Set ID
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>OBR.2
   </td>
   <td>Placer Order Number
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBR.3
   </td>
   <td>Filler Order Number
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBR.4
   </td>
   <td>Universal Service Identifier
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBR.5
   </td>
   <td>Priority - OBR
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBR.6
   </td>
   <td>Requested Date/Time
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>OBR.7
   </td>
   <td>Observation Date/Time
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBR.8
   </td>
   <td>Observation End Date/Time
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBR.9
   </td>
   <td>Collection Volume
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBR.10
   </td>
   <td>Collection Identifier
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBR.11
   </td>
   <td>Specimen Action Code
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBR.12
   </td>
   <td>Danger Code
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBR.13
   </td>
   <td>Relevant Clinical Information
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBR.14
   </td>
   <td>Specimen Received Date/Time
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBR.15
   </td>
   <td>Specimen Source
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBR.16
   </td>
   <td>Ordering Provider
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBR.22
   </td>
   <td>Results Report/Status Change Date/Time
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBR.23
   </td>
   <td>Charge to Practice
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>OBR.24
   </td>
   <td>Diagnostic Service Section ID
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBR.25
   </td>
   <td>Result Status
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBR.26
   </td>
   <td>Parent Result
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBR.27
   </td>
   <td>Quantity/Timing
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBR.31
   </td>
   <td>Reason for Study
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBR.32
   </td>
   <td>Principal Result Interpreter
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBR.33
   </td>
   <td>Technician
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBR.34
   </td>
   <td>Transcriptionist
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBR.35
   </td>
   <td>Scheduled Date/Time
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBR.44
   </td>
   <td>Procedure Code
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBR.45
   </td>
   <td>Procedure Code Modifier
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBR.50
   </td>
   <td>Parent Universal Service Identifier
   </td>
   <td>Recommended
   </td>
  </tr>
</table>



## OBX - Observation/Result Segment


<table>
  <tr>
   <td><strong>Field Code</strong>
   </td>
   <td><strong>Field Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>OBX.1
   </td>
   <td>Set ID
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>OBX.2
   </td>
   <td>Value Type
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>OBX.3
   </td>
   <td>Observation Identifier
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>OBX.4
   </td>
   <td>Observation Sub-ID
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBX.5
   </td>
   <td>Observation Value
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>OBX.6
   </td>
   <td>Units
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBX.7
   </td>
   <td>References Range
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBX.8
   </td>
   <td>Abnormal Flags
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBX.9
   </td>
   <td>Probability
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBX.10
   </td>
   <td>Nature of Abnormal Test
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBX.11
   </td>
   <td>Observation Result Status
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>OBX.12
   </td>
   <td>Effective Date of Reference Range
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBX.13
   </td>
   <td>User Defined Access Checks
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>OBX.14
   </td>
   <td>Date/Time of the Observation
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBX.15
   </td>
   <td>Producer’s ID
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBX.16
   </td>
   <td>Responsible Observer
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBX.17
   </td>
   <td>Observation Method
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBX.18
   </td>
   <td>Equipment Instance Identifier
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBX.19
   </td>
   <td>Date/Time of the Analysis
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBX.23
   </td>
   <td>Performing Organization Name
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBX.24
   </td>
   <td>Performing Organization Address
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>OBX.25
   </td>
   <td>Performing Organization Medical Director
   </td>
   <td>Recommended
   </td>
  </tr>
</table>



## ROL - Role Segment


<table>
  <tr>
   <td><strong>Field Code</strong>
   </td>
   <td><strong>Field Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>ROL.1
   </td>
   <td>Role instance ID
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>ROL.2
   </td>
   <td>Action Code
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ROL.3
   </td>
   <td>Role
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>ROL.4
   </td>
   <td>Role Person
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>ROL.5
   </td>
   <td>Role Begin Date/Time
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ROL.6
   </td>
   <td>Role End Date/Time
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ROL.7
   </td>
   <td>Role Duration
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ROL.8
   </td>
   <td>Role Action reason
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ROL.9
   </td>
   <td>Provider Type
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ROL.10
   </td>
   <td>Organization Unit Type
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ROL.11
   </td>
   <td>Office/Home Address/Birthplace
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>ROL.12
   </td>
   <td>Phone
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ROL.13
   </td>
   <td>Person’s Location
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>ROL.14
   </td>
   <td>Organization
   </td>
   <td>Recommended
   </td>
  </tr>
</table>



## RQD - Requisition Detail Segment


<table>
  <tr>
   <td><strong>Field Code</strong>
   </td>
   <td><strong>Field Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>RQD.1
   </td>
   <td>Requisition Line Number
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>RQD.2
   </td>
   <td>Item Code - Internal
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RQD.3
   </td>
   <td>Item Code - External
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RQD.4
   </td>
   <td>Hospital Item Code
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>RQD.5
   </td>
   <td>Requisition Quantity
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>RQD.6
   </td>
   <td>Requisition Unit of Measure
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RQD.7
   </td>
   <td>Department Cost Center
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RQD.8
   </td>
   <td>Item Natural Account Code
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RQD.9
   </td>
   <td>Deliver to ID
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RQD.10
   </td>
   <td>Date Needed
   </td>
   <td>Recommended
   </td>
  </tr>
</table>



## TXA - Transcription Document Header Segment


<table>
  <tr>
   <td><strong>Field Code</strong>
   </td>
   <td><strong>Field Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>TXA.1
   </td>
   <td>Set ID
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>TXA.2
   </td>
   <td>Document Type
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>TXA.3
   </td>
   <td>Document Content Presentation
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>TXA.4
   </td>
   <td>Activity Date/Time
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>TXA.5
   </td>
   <td>Primary Activity Provider Code/Name
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>TXA.6
   </td>
   <td>Origination Date/Time
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>TXA.7
   </td>
   <td>Transcription Date/Time
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TXA.8
   </td>
   <td>Edit Date/Time
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TXA.9
   </td>
   <td>Originator Code/Name
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TXA.10
   </td>
   <td>Assigned Document Authenticator
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TXA.11
   </td>
   <td>Transcriptionist Code/Name
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TXA.12
   </td>
   <td>Unique Document Number
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>TXA.13
   </td>
   <td>Parent Document Number
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TXA.14
   </td>
   <td>Placer Order Number
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TXA.15
   </td>
   <td>Filler order Number
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TXA.16
   </td>
   <td>Unique Document File Name
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>TXA.17
   </td>
   <td>Document Completion Status
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>TXA.18
   </td>
   <td>Document Confidentiality Status
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TXA.19
   </td>
   <td>Document Availability Status
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TXA.20
   </td>
   <td>Document Storage Status
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>TXA.21
   </td>
   <td>Document Change Reason
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TXA.22
   </td>
   <td>Authentication Person, Timestamp
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TXA.23
   </td>
   <td>Distributed Copies (Code and Name)
   </td>
   <td>Optional
   </td>
  </tr>
</table>



## RXO - Pharmacy/Treatment Order Segment


<table>
  <tr>
   <td><strong>Field Code</strong>
   </td>
   <td><strong>Field Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>RXO.1
   </td>
   <td>Requested Give Code
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>RXO.2
   </td>
   <td>Requested Give Amount - Minimum
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RXO.3
   </td>
   <td>Requested Give Amount - Maximum
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RXO.4
   </td>
   <td>Requested Give Units
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RXO.5
   </td>
   <td>Requested Dosage Form
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RXO.6
   </td>
   <td>Provider’s Pharmacy/Treatment Instructions
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RXO.7
   </td>
   <td>Provider’s Administration Instructions
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RXO.8
   </td>
   <td>Deliver-To Location
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>RXO.9
   </td>
   <td>Allow Substitutions
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RXO.10
   </td>
   <td>Requested Dispense Code
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RXO.11
   </td>
   <td>Requested Dispense Amount
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RXO.12
   </td>
   <td>Requested Dispense Units
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RXO.13
   </td>
   <td>Number of Refills
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RXO.14
   </td>
   <td>Ordering Provider’s DEA Number
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RXO.15
   </td>
   <td>Pharmacist/Treatment Supplier’s Verifier ID
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RXO.16
   </td>
   <td>Needs Human Review
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>RXO.17
   </td>
   <td>Requested Give Per (Time Unit)
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RXO.18
   </td>
   <td>Requested Give Strength
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RXO.19
   </td>
   <td>Requested Give Strength Units
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RXO.20
   </td>
   <td>Indication
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RXO.21
   </td>
   <td>Requested Give Rate Amount
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RXO.22
   </td>
   <td>Requested Give Rate Units
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RXO.23
   </td>
   <td>Total Daily Dose
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RXO.24
   </td>
   <td>Supplementary Code
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RXO.25
   </td>
   <td>Requested Drug Strength Volume
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RXO.26
   </td>
   <td>Requested Drug Strength Volume Units
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RXO.27
   </td>
   <td>Pharmacy Order Type
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>RXO.28
   </td>
   <td>Dispensing Interval
   </td>
   <td>Recommended
   </td>
  </tr>
</table>



## TQ1 - Timing/Quantity Segment


<table>
  <tr>
   <td><strong>Field Code</strong>
   </td>
   <td><strong>Field Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>TQ1.1
   </td>
   <td>Set ID
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>TQ1.2
   </td>
   <td>Quantity
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>TQ1.3
   </td>
   <td>Repeat Pattern
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TQ1.4
   </td>
   <td>Explicit Time
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TQ1.5
   </td>
   <td>Relative Time and Units
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TQ1.6
   </td>
   <td>Service Duration
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TQ1.7
   </td>
   <td>Start Date/Time
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>TQ1.8
   </td>
   <td>End Date/Time
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TQ1.9
   </td>
   <td>Priority
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TQ1.10
   </td>
   <td>Condition Text
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>TQ1.11
   </td>
   <td>Text Instruction
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>TQ1.12
   </td>
   <td>Conjunction
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TQ1.13
   </td>
   <td>Occurrence Duration
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TQ1.14
   </td>
   <td>Total Occurrences
   </td>
   <td>Recommended
   </td>
  </tr>
</table>



## TQ2 - Timing/Quantity Relationship Segment


<table>
  <tr>
   <td><strong>Field Code</strong>
   </td>
   <td><strong>Field Name</strong>
   </td>
   <td><strong>Optionality</strong>
   </td>
  </tr>
  <tr>
   <td>TQ2.1
   </td>
   <td>Set ID
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td>TQ2.2
   </td>
   <td>Sequence/Results Flag
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TQ2.3
   </td>
   <td>Related Placer Number
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TQ2.4
   </td>
   <td>Related Filler Number
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TQ2.5
   </td>
   <td>Related Placer Group
   </td>
   <td>Recommended
   </td>
  </tr>
  <tr>
   <td>TQ2.6
   </td>
   <td>Sequence Condition Code
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>TQ2.7
   </td>
   <td>Cyclic Entry/Exit Indicator
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>TQ2.8
   </td>
   <td>Sequence Condition Time Interval
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>TQ2.9
   </td>
   <td>Cyclic Group Maximum Number of Repeats
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td>TQ2.10
   </td>
   <td>Special Service Request Relationship
   </td>
   <td>Optional
   </td>
  </tr>
</table>

