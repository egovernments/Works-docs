---
description: Test planning for MuktaSoft V1.0, HUDD
---

# UAT Test Planning

## 1.0 Objective

The purpose of this document is to outline the User Acceptance Testing (UAT) process for the MUKTA application developed on the DIGIT-Works platform for the implementation of the MUKTA scheme notified by the Government of Odisha. This will enable the ULB and CBO users to validate that the MUKTASoft application meets the agreed-upon acceptance criteria for various functionalities.

It will ensure that the system satisfies the needs of the business as specified in the [functional requirements ](../../../mukta/functional-requirements.md)([PRD](../../../mukta/product-requirements-document.md)/ [User Stories](../../../mukta/user-stories/)) and provides confidence in its use. It will also help to identify defects with associated risks and suggest enhancements(change requests), communicate all known defects/enhancements to the project team, and ensure that all issues are addressed in an appropriate manner prior to go-live.

## 2.0 UAT Methodology

During the testing process, a pre-approved list of test cases/scripts will be executed to verify the behaviour and performance of various functionalities. The observations from the testing will be noted and classified as defects, enhancements, or clarifications. Some of the enhancements may be doable using configuration changes while others( Change Requests) may have to go through a change management process.

UAT observation classification:

| # | Observation Type     | Description                                                                                                                                         | Addressing Mechanism                                                                                                                                                                                                                                                                                            |
| - | -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | Defects              | Any observation pertaining to a feature or functionality not working as expected or agreed at the time of scope review, will be classified as issue | The observations classified as defects will be taken up by the eGov program team for further validation, prioritisation and fixing. Minor issues originating due to incorrect configurations or erroneous labels, or translations will be fixed and be made available for re-testing during the next UAT cycle. |
| 2 | Change Requests (CR) | Any recommendations to enable or disable a functionality from the initial requirements or a new functionality to be added                           | These will be handled via Change control Process as per the SoP defined and will be evaluated based on their impact and effort.                                                                                                                                                                                 |
| 3 | Clarifications       | A query which is related to usage of a system where the manual process would be slightly different from system process.                             | These will be clarified then and there with the help of department and document in the UAT sign off document.                                                                                                                                                                                                   |

The UAT team will execute all the test scripts referenced in section 6.0.  Users may also perform additional tests not detailed in the plan but remain relevant and within the scope of the project. &#x20;

Users will report feedback to the eGov team for documentation and escalation using a Google sheet. These defects will be described, prioritized, and tracked by using screen captures, verbiage, and steps necessary for the development team to reproduce the defect. For change requests the requirements will be described, analysed, prioritised and tracked.  Information on defect and CR processing can be found in section 7.0.

### 2.1 Test Phases

The various phases of UAT are illustrated in the diagram below:

<div align="left">

<figure><img src="../../../../.gitbook/assets/image (14) (2).png" alt=""><figcaption></figcaption></figure>

</div>

### 2.2 Scope for UAT

UAT is conducted by distributing all test case scenarios to various roles. The UAT session will start with a product demo CUM brief training for all the users.&#x20;

1. MuktaSoft web application for employees.
2. MuktaSoft web (Mobile First) and mobile (Android) application for CBOs.
3. Well-defined functional scope.
4. Well-defined role-wise functional test case scenarios covering end-to-end flow.
5. Well-defined system configuration and master data.
6. Identified application users from ULBs and CBOs.
7. Performing the test with the real-world data from ULB’s files.
8. Capturing test case results and observations.
9. Resolution of issues reported as agreed upon.

#### Out of the scope of UAT

For the below-mentioned functionalities, separate demos and/or training sessions will be conducted for the targeted user groups.

1. Helpdesk for complaints and user management
   * User Management module to add/update/ activate/deactivate users and role mapping
   * Handling complaints via inbox functionality
2. HUDD and ULB dashboards and reports.&#x20;
3. Project Closure, Work Order Revision, and Bill PDFs.
4. JIT-FS and Aadhar Integrations.

During UAT, the team will validate the end-to-end flow and features of the application to validate:&#x20;

* End-to-end business flow for each of the identified users flows&#x20;
* All the required fields are present
* The system accepts only valid values
* Users can save after filling in the mandatory fields in the form filling&#x20;
* Correctness of label and its translation

### 2.3 Prerequisites for UAT

Following is the list of prerequisites for conducting the UAT

1. The MuktaSoft mobile app for UAT deployed in the UAT environment
2. Installation of the MuktaSoft app on CBO user mobiles (Android 10 and Above)
3. Configuration of MuktaSoft mobile app in UAT environment with master data
4. Readiness of handouts
   * Test case document
   * Defect/change request reporting template&#x20;
5. Availability of teams from HUDD, SUDA, UMC and CBOs for user acceptance testing
6. Nomination of participants for the UAT session so that test accounts can be created by eGov.
7. Configuration of ticket tracking tool for UAT (JIRA)

## 3.0 UAT Environment

The UAT environment is similar to the production environment in terms of specifications and is provided by eGov, so that accurate assumptions can be drawn regarding the application’s performance.

Applicable IP addresses and URLs will be provided by eGov team to the UAT Team and all the mobiles will be configured for access to the test environment.

### 3.1 UAT Process

Each test participant will be provided with a checklist to verify access to the applications within the defined scope of testing.  The tester will then log in, perform the prescribed steps and generate the expected results for each activity.  Any feature identified as missing or a bug during testing from the UAT environment should be reported back to eGov.

### 3.2 UAT Data

Access to test data is a vital component in conducting a comprehensive test of the system.  All UAT participants will require the usage of test accounts and other actual files from the ULBs with the project's data to use as the test data.  All user roles should fully emulate production in the UAT path. The test accounts and role mapping shall be done for the users identified by eGov. Following are sample test data for UA testing:

1. Sample Master Data
   * Tenant configuration data
   * Location/boundary master (Ward/ Locality )
   * Application configuration master data
     * Project Type
     * Target Demography
     * Unit of Measurement
     * Overheads
     * Skill Category
     * Skills
     * CBO Role
     * Deductions
     * Organization Type
     * Organization Sub Type
     * Organization Functional Category
     * Organization Class/ Rank
     * ULBs Sections/ Departments
     * Designations
   * User data for test login creation
     * Employees
     * Community-Based Organizations
   * Wage seeker’s master data
2. Testing Data&#x20;
   * MUKTA works manual files - to use the data in the files as test data

## 4.0 Roles and Responsibilities

HUDD

* Nomination of stakeholders for executing  the UAT
* Verification of product based on UAT scenarios
* Decision regarding date and venue
* Arrangement of logistics-Venue
* Providing feedback after the UAT session and sign off
* Provision devices (15 laptops for master trainers and ULB Employees + Android phones for the 8 SHG members)&#x20;

eGov

* Demo  before the UAT event
* Training before UAT initiation&#x20;
* Framing test scenarios
* Creation of UAT Plan
* Collection and triaging of the UAT feedback

UMC

* Review of translated UAT feedback (as provided by HUDD Odia cell)&#x20;
* Nominate master trainers to participate in the UAT&#x20;

### 4.1 UAT Team

The test team is composed of members who possess a knowledge of the operations and processes on the ground. &#x20;

1. These team members will be able to initiate test input, review the results&#x20;
2. Have prior experience/learnings from on-ground implementation MUKTA

All team members will be presented by the eGov team with an overview of the test process and their specific roles in UAT.  The eGov team will oversee testing by assigning scripts to testers, providing general support, and serving as the primary UAT contact point throughout the test cycle.

| Name of participant                     | Project Role/Designation                 | Phone Extension | Email                           | Entity (ULB/HUDD/UMC/CBO) |
| --------------------------------------- | ---------------------------------------- | --------------- | ------------------------------- | ------------------------- |
| Shri.TARUN KUMAR MOHAPATRA              | Executive Officer Dhenkanal Municipality | 9337013841      | tarunmohapatra65@gmail.com      | ULB- Dhenkanal            |
| DINESH KUMAR NAIK                       | Junior Engineer                          | 8328998068      |    dldkl1983@gmail.com          | ULB- Dhenkanal            |
| PARBATI SAHU                            | Junior Engineer                          | 7809480648      | parbati.withu@gmail.com         | ULB- Dhenkanal            |
| <p>JNYANENDRA KUMAR ROUT</p><p><br></p> | Assistant engineer                       | 9437321763      | J.krout1234@gmail.com           | ULB- Dhenkanal            |
| RASMITA MISHRA                          | Municipal Engineer                       | 9438300884      | rasmitamishra2012@gmail.com     | ULB- Dhenkanal            |
| SUBRAT MOHANTY                          | Project Coordinator                      | 9439285069      | subratm1991@gmail.com           | ULB- Dhenkanal            |
| BISWAPRATAP SWAIN                       | Implementation Expert                    | 9337903256      | biswapratap21@gmail.com         | ULB- Dhenkanal            |
| SAROJ KUMAR SAHOO                       | Accountant Mukta                         | 7532061778      | sarojsahoo20@gmail.com          | ULB- Dhenkanal            |
| SUBHASMITA ROUT                         | MIS                                      | 8018817757      | smileysubha011@gmail.com        | ULB- Dhenkanal            |
| Ipsita priyadarshini pattnayak          | (President) Omm Sairam SHG               | 7608890395      | <p><br></p>                     | SHG-Dhenkanal             |
| Sobhasini Mohapatra                     | (SHG member) Sai Shree SHG               | 8018867549      | <p><br></p>                     | SHG-Dhenkanal             |
| Kalyani Acharya                         | (President) Matru Shakti SHG             | 8457984081      | <p><br></p>                     | SHG-Dhenkanal             |
| Bandana Barik                           | (President) Radhakrushna SDA             | 9853009717      | <p><br></p>                     | SDA- Dhenkanal            |
| Shri.Dilip Mohanty                      | Executive Officer, Jatni Municipality    | 9437829447      | <p><br></p>                     | ULB- Jatni                |
| Anuradha pradhan                        | Municipal Engineer                       | 9439053858      | <p><br></p>                     | ULB-Jatni                 |
| Deepak kumar ratha                      | Assistant Engineer                       | 9437192524      | <p><br></p>                     | ULB- Jatni                |
| Alok kumar swain                        | Junior Engineer                          | 9437696344      | <p><br></p>                     | ULB-Jatni                 |
| Madhusmita biswal                       | Project Coordinator                      | 7750019741      | <p><br></p>                     | ULB-Jatni                 |
| Ascharyananda behera                    | Implementation Expert                    | 7008965961      | <p><br></p>                     | ULB-Jatni                 |
| Preetiabhinav pattnayak                 | Account                                  | 8249766981      | <p><br></p>                     | ULB-Jatni                 |
| Snehanjali Khatua                       | MIS                                      | 9090747277      | <p><br></p>                     | ULB-Jatni                 |

## 5.0 UAT Deliverables

The following sections detail milestones crucial to the completion of the UAT phase of the project.  Once all dependent milestones have been completed, HUDD will formally sign off on the system’s functionality and distribute an email to all project stakeholders.

### 5.1 UAT Definition

### Detailed Functional Scope

Employee and CBO Portals are deployed into the UAT instance with the features listed below

| S.No. | Details                                                                                                                                                                                                                                                                                               |
| ----- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1     | **Employee Portal:** The list of features to which an employee user has access to                                                                                                                                                                                                                     |
| 1.1   | **Project:** Create, Search, View and Modify a project, download project details PDF                                                                                                                                                                                                                  |
| 1.2   | **Estimate:** Create, Search, View, and Process the estimate for approval, download the estimate PDF                                                                                                                                                                                                  |
| 1.3   | <p><strong>Estimate:</strong> The below actions are available for processing the estimate based on specific user roles -</p><p>1. Create and Forward</p><p>2. Verify and Forward</p><p>3. Technical Sanction</p><p>4. Approve</p><p>5. Send Back</p><p>6. Send Back To Originator</p><p>7. Reject</p> |
| 1.4   | **Work Order:** Create, Search, View, and Process the work order for approval, download the work order PDF                                                                                                                                                                                            |
| 1.5   | <p><strong>Work Order:</strong> While processing the work order below are the actions enabled based on the role a user has</p><p>1. Create and Forward</p><p>2. Verify and Forward</p><p>3. Approve</p><p>4. Send Back</p><p>5. Send Back To Originator</p><p>6. Reject</p>                           |
| 1.6   | **Muster Roll:** Search, View, and Process the muster roll for approval, download the muster roll PDF                                                                                                                                                                                                 |
| 1.7   | <p><strong>Muster Roll:</strong> While processing the muster roll below are the actions enabled based on the role a user has</p><p>1. Verify and Forward</p><p>2. Approve</p><p>3. Send Back</p><p>4. Send Back To CBO</p>                                                                            |
| 1.8   | **Billing:** Create, Search, View, and Process the purchase bill for approval                                                                                                                                                                                                                         |
| 1.9   | <p><strong>Billing:</strong> While processing the purchase bill below are the actions enabled based on the role a user has</p><p>1. Create and Forward</p><p>2. Verify and Forward</p><p>3. Approve</p><p>4. Send Back</p><p>5. Send Back To Originator</p><p>6. Reject</p>                           |
| 1.10  | Auto creation of wage bill on approval of a muster roll                                                                                                                                                                                                                                               |
| 1.11  | Auto creation of supervision bill on approval of a muster roll                                                                                                                                                                                                                                        |
| 1.12  | **Payment Advice:** Search for the bill and download the payment advice to enable the user for processing payments                                                                                                                                                                                    |
| 1.13  | **Organization:** Create, Search, View, and Modify organization details (CBOs/ Vendors)                                                                                                                                                                                                               |
| 1.14  | **Wage Seeker:** Search, View, and Modify of a wage seekers                                                                                                                                                                                                                                           |
| 1.15  | **Employee/ Users:** Create, Search, View, and Modify employee users with the role mapping                                                                                                                                                                                                            |
| 2     | **CBO Portal/ Mobile App:** The list of features which a CBO user will be able to perform                                                                                                                                                                                                             |
| 2.1   | **My Works:** View, Accept, Decline work order which was awarded to CBO                                                                                                                                                                                                                               |
| 2.2   | Engage/ Disengage wage seekers to the work order accepted                                                                                                                                                                                                                                             |
| 2.3   | **Attendance Tracking:** Track attendance daily, and create muster roll weekly                                                                                                                                                                                                                        |
| 2.4   | **Muster Rolls:** View, and Edit muster roll                                                                                                                                                                                                                                                          |
| 2.5   | **My Bills:** View bills                                                                                                                                                                                                                                                                              |
| 2.6   | **Wage Seeker:** Register a wage seeker                                                                                                                                                                                                                                                               |
| 3     | Application supports English and Odia language.                                                                                                                                                                                                                                                       |
|       | <mark style="background-color:orange;">**Pre-requisites**</mark>                                                                                                                                                                                                                                      |
| 1     | UAT users are created into UAT and the username and password is shared.                                                                                                                                                                                                                               |
| 2     | CBO mobile UAT app is released and APK is shared with the UAT CBO users.                                                                                                                                                                                                                              |
| 3     | UAT application URLs are shared with the users.                                                                                                                                                                                                                                                       |
| 4     | Participating CBO organizations are created during UAT.                                                                                                                                                                                                                                               |
| 5     | Help manuals are created and shared.                                                                                                                                                                                                                                                                  |
| 6     | Change management mechanism defined.                                                                                                                                                                                                                                                                  |

### 5.2 UAT - Session structure

The UAT session will be conducted physically in Bhubaneswar, Odisha at the HUDD office. The detailed plan for the UAT session is as follows:&#x20;

| #                     | Activity                                                                              | Approximate Duration | Time                                 |
| --------------------- | ------------------------------------------------------------------------------------- | -------------------- | ------------------------------------ |
| Day 1- 22nd May 2023  | <p><br></p>                                                                           |                      |                                      |
| 1                     | Registration                                                                          | 30  minutes          | 9.00 am - 9.30 am                    |
| 2                     | Demonstration of MUKTASoft                                                            | 60 minutes           | 9.30 am - 10.30 am                   |
| <p><br></p>           | Tea Break-1                                                                           | 30 minutes           | 10.30 am - 11.00 am                  |
| 3                     | Hands-on Training Session 1 (Project, Estimate)                                       | 120 minutes          | 11.00  am - 1.00 pm                  |
| <p><br></p>           | Lunch Break                                                                           | 60 minutes           | 1.00 pm - 2.00 pm                    |
| 4                     | Hands-on Training Session 2 (Work Order,Muster Roll, Purchase Bill, Payment Advice)   | 120 minutes          | 2.00 pm - 4.00 pm                    |
| <p><br></p>           | Tea Break-2                                                                           | 30 minutes           | 4.00 pm - 4.30 pm                    |
| 5                     | Hands-on Training Session 3 (CBO Portal)                                              | 60 minutes           | 4.30 pm -  5.30 pm                   |
| Day 2 - 23rd May 2023 | <p><br></p>                                                                           |                      |                                      |
| 1                     | Hands-on Training continues                                                           | 90 Minutes           | 9.30 am - 11.00 am                   |
| <p><br></p>           | Tea Break-1                                                                           | 30 minutes           | 11.00 am - 11.30 am                  |
| 2                     | Q & A, Feedback, Preparation for UAT (Test case handouts distributed based on Roles)  | 90 minutes           | <p>11.30 am - 1.00 pm</p><p><br></p> |
| <p><br></p>           | Lunch Break                                                                           | 60 minutes           | 1.00 pm - 2.00 pm                    |
| 3                     | UAT Session 1                                                                         | 120 minutes          | 2.00 pm - 4:00 pm                    |
| <p><br></p>           | Tea Break-2                                                                           | 30 minutes           | 4.00 pm - 4.30 pm                    |
| 4                     | UAT Session 2                                                                         | 60 minutes           | 4.30 pm - 5.30 pm                    |
| Day 3 - 24th May 2023 |                                                                                       |                      |                                      |
| 1                     | UAT Session 3                                                                         | 90 minutes           | 9.30 am - 11.00 am                   |
| <p><br></p>           | Tea Break-1                                                                           | 30 minutes           | 11.00 am - 11.30 am                  |
| 2                     | UAT Session 4                                                                         | 90 minutes           | 11.30 am - 1.00 pm                   |
| <p><br></p>           | Lunch Break                                                                           | 60 minutes           | 1.00 pm - 2.00 pm                    |
| 3                     | UAT Session 5                                                                         | 120 minutes          | 2.00 pm - 4.00 pm                    |
| <p><br></p>           | Tea Break-2                                                                           | 30 minutes           | 4.00 pm - 4.30 pm                    |
| 4                     | UAT Session 6                                                                         | 60 minutes           | 4.30 pm - 5.30 pm                    |
| Day 4 - 25th May 2023 |                                                                                       |                      |                                      |
| 1                     | UAT Session 7                                                                         | 90 minutes           | 9.30 am - 11.00 am                   |
| <p><br></p>           | Tea Break-1                                                                           | 30 minutes           | 11.00 am - 11.30 am                  |
| 2                     | UAT Session 8                                                                         | 90 minutes           | 11.30 am - 1.00 pm                   |
| <p><br></p>           | Lunch Break                                                                           | 60 minutes           | 1.00 pm - 2.00 pm                    |
| 3                     | Bugs, Enhancements, Feedback Collection and Prioritization                            | 120 minutes          | 2.00 pm - 4.00 pm                    |
| <p><br></p>           | Tea Break-2                                                                           | 30 minutes           | 4.00 pm - 4.30 pm                    |
| 4                     | Feedback , Quiz on Training and UAT, Closure                                          | 90 minutes           | 4.30 pm - 6.00 pm                    |

The CR analysis may take more than the anticipated timelines. The CR analysis if exceeding more than Day 2, the analysis results, acceptance and prioritisation will be discussed in a subsequent meeting.

### 5.3 UAT Sign-off Checklist

* The signoff shall be provided at the end of UAT by HUDD via email communication or official orders/memo to the eGov.
* All UAT Test cases completed: Verified that all UAT test cases, as defined in the UAT plan, have been executed and completed
* Business requirements validated: Validated that all business requirements, as defined in the requirements documentation - all features, functions, workflows, calculations, and translations have been thoroughly tested and verified
* Compatibility tested: Verified that the application has been tested on the specified devices, Operating System (Windows 10  Pro, Android 10 and Above), and browser Chrome (Latest version)  and any compatibility issues have been addressed.
* All feedback has been identified and documented. Agreed on the priority.
* Documentation updated: Ensured that all relevant documentation, including user manuals, have been updated post-UAT and they reflect changes identified and acted on during UAT
* UAT summary report prepared: Prepared a UAT summary report that includes the UAT results, findings, and any outstanding issues or risks identified during UAT
* The mutually agreed defects/CR from UAT will be resolved and demonstrated to users within the agreed time frame.
* Post resolution and demonstration of all the issues the application will be ready for deployment in the production environment&#x20;

### 5.4 UAT Success Criteria&#x20;

* Training on the UAT environment was completed with 100% participation as per the plan. In case some of the participants are not available, prior intimation with reason is to be captured.
* No P1 bugs were found during the execution of the test scenarios.
* 90% of the total test cases should be executed successfully and the observed behaviour was found to match the expected results.
* Post Training and UAT sessions, a quiz will be administered to check the familiarity of the participants with MUKTASoft. The quiz must be completed with at least 75% correct responses.

## 6.0 UA Test  Scenarios

Test cases provide a high-level description of the functionality to be tested.  All regression and new functionality test cases are contained in the Excel spreadsheet “UA Test Cases” available at: \[[UAT Test Scenarios](uat-test-case-scenarios.md)]. &#x20;

The team will leverage relevant QA test cases for project-specific functionality.  Each test case based on new functionality will reference a specific functional requirement.

Each script contains: the test case number, test description, requirement number, action to be performed, test data to be utilized, expected results, error descriptions (if applicable), pass/fail results, date tested, and any additional comments from the UA tester.

The UA test scripts are contained within the UAT test case spreadsheet and can be accessed via hyperlinks from each individual test case.

## 7.0 UAT Feedback&#x20;

Defects and Change Requests will be entered and tracked in JIRA by the eGov team during the UAT process.  Each entry will include detailed information about each defect/CR.

#### UAT Defect/CR Tracking

The test team will be provided with instructions on how to effectively execute test scripts, as well as identify, capture, and report defects/observations by the eGov team at the beginning of the UAT session. The test team will present their findings during the UAT session.&#x20;

#### UAT Defect Life Cycle&#x20;

Defects must be clearly captured and escalated to ensure prompt resolution by development.  Each defect submitted by UAT will be assigned a priority, worked by development, resolved, and re-tested by UAT prior to closure.  The following is a snapshot of the standard defect lifecycle:

![](<../../../../.gitbook/assets/image (12) (2).png>)

eGov and HUDD together will prioritize and classify defects.  Defects found in UAT can be assigned one of three (3) levels of severity:

* **P1, Work Halted** – Testing defects that due to the complexity of the function or the scheduled dates are putting the implementation date at risk.  No workaround exists.
* **P2, Work Slowed** – Testing defects occurring in a less complex function of the application with sufficient time to resolve before the implementation date – but must be implemented as scheduled.  A workaround has been identified and is listed in the defect.
* **P3 and lower, Work Unaffected** – Testing defects occurring in a function that is simple to fix or could be excluded if not resolved by the scheduled implementation date.

Response (acknowledgement of the issue) Commitments for Defects

| Severity                      | Description                                                                                                      | Response SLA |
| ----------------------------- | ---------------------------------------------------------------------------------------------------------------- | ------------ |
| P1, Work Halted               | Critical application outage impacting service for which the cause is unknown. No bypass or workaround available. | 4 hours      |
| P2, Work Slowed               | A key component of the application is degraded, unusable or unavailable, some users affected.                    | 1 day        |
| P3 and lower, Work Unaffected | A component of the application is degraded, which causes a minor inconvenience, but a workaround is available.   | 2 days       |

As a non-profit, we are unable to make any commitment on how long issues will take to fix and deploy in production. We will endeavour to resolve P1 issues as quickly as possible.  &#x20;

#### UAT Change Request Life Cycle&#x20;

CR must be clearly captured and reported for analysis to identify effort and impact in the eGov team. Each CR submitted will be validated and categorised for acceptance and then assigned with a priority. The development team will work on it and will be made available for testing. Following is a snapshot of the standard CR lifecycle:

\
![](<../../../../.gitbook/assets/image (3) (1).png>)

#### Categorisation&#x20;

eGov in consultation with HUDD will decide acceptance and categorisation of change requests. Change requests found in UAT can be assigned one of three (3) levels of category:

* Must Have – Change requests that are needed for the success of a campaign. No workaround exists.
* Should Have – Change requests that are required for better tracking and monitoring and will increase the ease of use of the system for users. A workaround has been identified and is listed in the CR.
* Good to Have – Change requests that are simply for better visualisation and reporting. It could be excluded if not resolved by the scheduled implementation date.

eGov to endeavour to cover Must Have changes before distribution. Lower priority changes will be taken through the eGov Gating process for planning subsequent releases.

## 8.0 References

The following are reference documents which have been leveraged for project-specific information in the design of the UAT plan:

| Document                                  | Document Link                                                                                                                                                                                                                                                                |
| ----------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Test Case Document                        | [Test case scenarios](test-case-scenarios.md)                                                                                                                                                                                                                                |
| Defect/ Change Request Reporting Template | [Issue Reporting Template](issue-reporting-template.md)                                                                                                                                                                                                                      |
| Training Feedback                         | [Click here ](https://docs.google.com/forms/d/1It266KQECgzUtU8uVjSJGCryTuUlpMGlOYHtG4RCw3I/viewform?ts=64620419\&edit\_requested=true)                                                                                                                                       |
| UAT Feedback form                         | <p>English - <a href="https://docs.google.com/forms/d/1hJh9Idye7CX-2zghcF2IgT2_VMIbq03PJjWt3JSC5hM/edit?ts=645dc757">Click Here</a></p><p>Odiya - <a href="https://docs.google.com/forms/d/1YAAO4tfHADly26ThKKB-JYsxUKKY9IlB_vWYh6f1aLU/edit?ts=64634b8c">Click Here</a></p> |

