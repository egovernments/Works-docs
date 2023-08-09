---
description: Test planning for MuktaSoft V1.0, HUDD
---

# UAT Test Planning

## 1.0 Objective

The purpose of this document is to outline the User Acceptance Testing (UAT) process for the MUKTA application developed on the DIGIT-Works platform for the implementation of the MUKTA scheme notified by the Government of Odisha. This will enable the ULB and CBO users to validate that the MUKTASoft application meets the agreed-upon acceptance criteria for various functionalities.

It will ensure that the system satisfies the needs of the business as specified in the [functional requirements ](../../functional-requirements/)([PRD](../../functional-requirements/product-requirements-document.md)/ [User Stories](../../functional-requirements/user-stories/)) and provides confidence in its use. It will also help to identify defects with associated risks and suggest enhancements(change requests), communicate all known defects/enhancements to the project team, and ensure that all issues are addressed in an appropriate manner prior to go-live.

## 2.0 UAT Methodology

During the testing process, a pre-approved list of test cases/scripts will be executed to verify the behaviour and performance of various functionalities. The observations from the testing will be noted and classified as defects, enhancements, or clarifications. Some of the enhancements may be doable using configuration changes while others( Change Requests) may have to go through a change management process.

UAT observation classification:

<table><thead><tr><th width="74">#</th><th width="145">Observation Type</th><th width="198">Description</th><th>Addressing Mechanism</th></tr></thead><tbody><tr><td>1</td><td>Defects</td><td>Any observation pertaining to a feature or functionality not working as expected or agreed at the time of scope review, will be classified as issue</td><td>The observations classified as defects will be taken up by the eGov program team for further validation, prioritisation and fixing. Minor issues originating due to incorrect configurations or erroneous labels, or translations will be fixed and be made available for re-testing during the next UAT cycle.</td></tr><tr><td>2</td><td>Change Requests (CR)</td><td>Any recommendations to enable or disable a functionality from the initial requirements or a new functionality to be added</td><td>These will be handled via Change control Process as per the SoP defined and will be evaluated based on their impact and effort.</td></tr><tr><td>3</td><td>Clarifications</td><td>A query which is related to usage of a system where the manual process would be slightly different from system process. </td><td>These will be clarified then and there with the help of department and document in the UAT sign off document.</td></tr></tbody></table>

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
   * User management module to add/update/ activate/deactivate users and role mapping
   * Handling complaints via inbox functionality
2. HUDD and ULB dashboards and reports.&#x20;
3. Project closure, work order revision, and bill PDFs.
4. JIT-FS and Aadhar integrations.

During UAT, the team will validate the end-to-end flow and features of the application to validate:&#x20;

* End-to-end business flow for each of the identified users flows&#x20;
* All the required fields are present
* The system accepts only valid values
* Users can save after filling in the mandatory fields in the form filling&#x20;
* Correctness of label and its translation

### 2.3 Prerequisites for UAT

Following is the list of pre-requisites for conducting the UAT

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

Each test participant will be provided with a checklist to verify access to the applications within the defined scope of testing.  The tester then logs in, performs the prescribed steps and generates the expected results for each activity.  Any feature identified as missing or a bug during testing from the UAT environment should be reported back to eGov.

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

<table><thead><tr><th>Name of participant</th><th>Project Role/Designation</th><th width="159">Phone Extension</th><th width="163">Email</th><th>Entity (ULB/HUDD/UMC/CBO)</th></tr></thead><tbody><tr><td>Shri.TARUN KUMAR MOHAPATRA</td><td>Executive Officer Dhenkanal Municipality</td><td>9337013841</td><td>tarunmohapatra65@gmail.com     </td><td>ULB- Dhenkanal</td></tr><tr><td>DINESH KUMAR NAIK</td><td>Junior Engineer</td><td>8328998068  </td><td>   dldkl1983@gmail.com  </td><td>ULB- Dhenkanal</td></tr><tr><td>PARBATI SAHU</td><td>Junior Engineer</td><td>7809480648</td><td>parbati.withu@gmail.com</td><td>ULB- Dhenkanal</td></tr><tr><td><p>JNYANENDRA KUMAR ROUT</p><p><br></p></td><td>Assistant engineer</td><td>9437321763</td><td>J.krout1234@gmail.com</td><td>ULB- Dhenkanal</td></tr><tr><td>RASMITA MISHRA</td><td>Municipal Engineer</td><td>9438300884</td><td>rasmitamishra2012@gmail.com</td><td>ULB- Dhenkanal</td></tr><tr><td>SUBRAT MOHANTY</td><td>Project Coordinator</td><td>9439285069</td><td>subratm1991@gmail.com</td><td>ULB- Dhenkanal</td></tr><tr><td>BISWAPRATAP SWAIN</td><td>Implementation Expert</td><td>9337903256</td><td>biswapratap21@gmail.com</td><td>ULB- Dhenkanal</td></tr><tr><td>SAROJ KUMAR SAHOO</td><td>Accountant Mukta</td><td>7532061778</td><td>sarojsahoo20@gmail.com</td><td>ULB- Dhenkanal</td></tr><tr><td>SUBHASMITA ROUT</td><td>MIS</td><td>8018817757</td><td>smileysubha011@gmail.com</td><td>ULB- Dhenkanal</td></tr><tr><td>Ipsita priyadarshini pattnayak</td><td>(President) Omm Sairam SHG</td><td>7608890395</td><td><br></td><td>SHG-Dhenkanal</td></tr><tr><td>Sobhasini Mohapatra</td><td>(SHG member) Sai Shree SHG</td><td>8018867549</td><td><br></td><td>SHG-Dhenkanal</td></tr><tr><td>Kalyani Acharya</td><td>(President) Matru Shakti SHG</td><td>8457984081</td><td><br></td><td>SHG-Dhenkanal</td></tr><tr><td>Bandana Barik</td><td>(President) Radhakrushna SDA</td><td>9853009717</td><td><br></td><td>SDA- Dhenkanal</td></tr><tr><td>Shri.Dilip Mohanty</td><td>Executive Officer, Jatni Municipality</td><td>9437829447</td><td><br></td><td>ULB- Jatni</td></tr><tr><td>Anuradha pradhan</td><td>Municipal Engineer</td><td>9439053858</td><td><br></td><td>ULB-Jatni</td></tr><tr><td>Deepak kumar ratha</td><td>Assistant Engineer</td><td>9437192524</td><td><br></td><td>ULB- Jatni</td></tr><tr><td>Alok kumar swain</td><td>Junior Engineer</td><td>9437696344</td><td><br></td><td>ULB-Jatni</td></tr><tr><td>Madhusmita biswal</td><td>Project Coordinator</td><td>7750019741</td><td><br></td><td>ULB-Jatni</td></tr><tr><td>Ascharyananda behera</td><td>Implementation Expert</td><td>7008965961</td><td><br></td><td>ULB-Jatni</td></tr><tr><td>Preetiabhinav pattnayak</td><td>Account </td><td>8249766981</td><td><br></td><td>ULB-Jatni</td></tr><tr><td>Snehanjali Khatua</td><td>MIS</td><td>9090747277</td><td><br></td><td>ULB-Jatni</td></tr></tbody></table>

## 5.0 UAT Deliverables

The following sections detail milestones crucial to the completion of the UAT phase of the project.  Once all dependent milestones have been completed, HUDD will formally sign off on the system’s functionality and distribute an email to all project stakeholders.

### 5.1 UAT Definition

### Detailed Functional Scope

Employee portal and CBO app are deployed in the UAT instance with the below-listed features:

<table><thead><tr><th width="114">S.No.</th><th>Details</th></tr></thead><tbody><tr><td>1</td><td><strong>Employee Portal:</strong> The list of features to which an employee user has access to</td></tr><tr><td>1.1</td><td><strong>Project:</strong> Create, Search, View and Modify a project, download project details PDF</td></tr><tr><td>1.2</td><td><strong>Estimate:</strong> Create, Search, View, and Process the estimate for approval, download the estimate PDF</td></tr><tr><td>1.3</td><td><p><strong>Estimate:</strong> The below actions are available for processing the estimate based on specific user roles -</p><p>1. Create and Forward</p><p>2. Verify and Forward</p><p>3. Technical Sanction</p><p>4. Approve</p><p>5. Send Back</p><p>6. Send Back To Originator</p><p>7. Reject</p></td></tr><tr><td>1.4</td><td><strong>Work Order:</strong> Create, Search, View, and Process the work order for approval, download the work order PDF</td></tr><tr><td>1.5</td><td><p><strong>Work Order:</strong> While processing the work order below are the actions enabled based on the role a user has</p><p>1. Create and Forward</p><p>2. Verify and Forward</p><p>3. Approve</p><p>4. Send Back</p><p>5. Send Back To Originator</p><p>6. Reject</p></td></tr><tr><td>1.6</td><td><strong>Muster Roll:</strong> Search, View, and Process the muster roll for approval, download the muster roll PDF</td></tr><tr><td>1.7</td><td><p><strong>Muster Roll:</strong> While processing the muster roll below are the actions enabled based on the role a user has</p><p>1. Verify and Forward</p><p>2. Approve</p><p>3. Send Back</p><p>4. Send Back To CBO</p></td></tr><tr><td>1.8</td><td><strong>Billing:</strong> Create, Search, View, and Process the purchase bill for approval</td></tr><tr><td>1.9</td><td><p><strong>Billing:</strong> While processing the purchase bill below are the actions enabled based on the role a user has</p><p>1. Create and Forward</p><p>2. Verify and Forward</p><p>3. Approve</p><p>4. Send Back</p><p>5. Send Back To Originator</p><p>6. Reject</p></td></tr><tr><td>1.10</td><td>Auto creation of wage bill on approval of a muster roll</td></tr><tr><td>1.11</td><td>Auto creation of supervision bill on approval of a muster roll</td></tr><tr><td>1.12</td><td><strong>Payment Advice:</strong> Search for the bill and download the payment advice to enable the user for processing payments</td></tr><tr><td>1.13</td><td><strong>Organization:</strong> Create, Search, View, and Modify organization details (CBOs/ Vendors)</td></tr><tr><td>1.14</td><td><strong>Wage Seeker:</strong> Search, View, and Modify of a wage seekers</td></tr><tr><td>1.15</td><td><strong>Employee/ Users:</strong> Create, Search, View, and Modify employee users with the role mapping</td></tr><tr><td>2</td><td><strong>CBO Mobile App:</strong> The list of features which a CBO user will be able to perform</td></tr><tr><td>2.1</td><td><strong>My Works:</strong> View, accept, decline work order which was awarded to CBO</td></tr><tr><td>2.2</td><td>Engage/ disengage wage seekers to the work order accepted</td></tr><tr><td>2.3</td><td><strong>Attendance Tracking:</strong> Track attendance daily, and create muster roll weekly </td></tr><tr><td>2.4</td><td><strong>Muster Rolls:</strong> View and edit muster roll</td></tr><tr><td>2.5</td><td><strong>My Bills:</strong> View bills</td></tr><tr><td>2.6</td><td><strong>Wage Seeker:</strong> Register a wage seeker</td></tr><tr><td>3</td><td>Application supports English and Odiya language</td></tr><tr><td></td><td><mark style="background-color:orange;"><strong>Pre-requisites</strong></mark> </td></tr><tr><td>1</td><td>UAT users are created into UAT and the username and password is shared</td></tr><tr><td>2</td><td>CBO mobile UAT app is released and APK is shared with the UAT CBO users</td></tr><tr><td>3</td><td>UAT application URLs are shared with the users</td></tr><tr><td>4</td><td>Participating CBO organizations are created during UAT</td></tr><tr><td>5</td><td>Help manuals are created and shared</td></tr><tr><td>6</td><td>Change management mechanism defined</td></tr></tbody></table>

### 5.2 UAT - Session structure

The UAT session will be conducted physically in Bhubaneswar, Odisha at the HUDD office. The detailed plan for the UAT session is as follows:&#x20;

<table><thead><tr><th width="142">#</th><th width="241">Activity</th><th width="191">Approximate Duration</th><th>Time</th></tr></thead><tbody><tr><td>Day 1- 22nd May 2023</td><td><br></td><td></td><td></td></tr><tr><td>1</td><td>Registration</td><td>30  minutes</td><td>9.00 am - 9.30 am</td></tr><tr><td>2</td><td>Demonstration of MUKTASoft </td><td>60 minutes</td><td>9.30 am - 10.30 am</td></tr><tr><td><br></td><td>Tea Break-1</td><td>30 minutes</td><td>10.30 am - 11.00 am</td></tr><tr><td>3</td><td>Hands-on Training Session 1 (Project, Estimate) </td><td>120 minutes</td><td>11.00  am - 1.00 pm</td></tr><tr><td><br></td><td>Lunch Break</td><td>60 minutes</td><td>1.00 pm - 2.00 pm</td></tr><tr><td>4</td><td>Hands-on Training Session 2 (Work Order,Muster Roll, Purchase Bill, Payment Advice) </td><td>120 minutes</td><td>2.00 pm - 4.00 pm</td></tr><tr><td><br></td><td>Tea Break-2</td><td>30 minutes</td><td>4.00 pm - 4.30 pm</td></tr><tr><td>5</td><td>Hands-on Training Session 3 (CBO App)</td><td>60 minutes</td><td>4.30 pm -  5.30 pm</td></tr><tr><td>Day 2 - 23rd May 2023</td><td><br></td><td></td><td></td></tr><tr><td>1</td><td>Hands-on Training continues</td><td>90 Minutes</td><td>9.30 am - 11.00 am</td></tr><tr><td><br></td><td>Tea Break-1</td><td>30 minutes</td><td>11.00 am - 11.30 am</td></tr><tr><td>2</td><td>Q &#x26; A, Feedback, Preparation for UAT (Test case handouts distributed based on Roles) </td><td>90 minutes</td><td><p>11.30 am - 1.00 pm</p><p><br></p></td></tr><tr><td><br></td><td>Lunch Break</td><td>60 minutes</td><td>1.00 pm - 2.00 pm</td></tr><tr><td>3</td><td>UAT Session 1</td><td>120 minutes</td><td>2.00 pm - 4:00 pm</td></tr><tr><td><br></td><td>Tea Break-2</td><td>30 minutes</td><td>4.00 pm - 4.30 pm</td></tr><tr><td>4</td><td>UAT Session 2</td><td>60 minutes</td><td>4.30 pm - 5.30 pm</td></tr><tr><td>Day 3 - 24th May 2023</td><td></td><td></td><td></td></tr><tr><td>1</td><td>UAT Session 3</td><td>90 minutes</td><td>9.30 am - 11.00 am</td></tr><tr><td><br></td><td>Tea Break-1</td><td>30 minutes</td><td>11.00 am - 11.30 am</td></tr><tr><td>2</td><td>UAT Session 4</td><td>90 minutes</td><td>11.30 am - 1.00 pm</td></tr><tr><td><br></td><td>Lunch Break</td><td>60 minutes</td><td>1.00 pm - 2.00 pm</td></tr><tr><td>3</td><td>UAT Session 5</td><td>120 minutes</td><td>2.00 pm - 4.00 pm</td></tr><tr><td><br></td><td>Tea Break-2</td><td>30 minutes</td><td>4.00 pm - 4.30 pm</td></tr><tr><td>4</td><td>UAT Session 6</td><td>60 minutes</td><td>4.30 pm - 5.30 pm</td></tr><tr><td>Day 4 - 25th May 2023</td><td></td><td></td><td></td></tr><tr><td>1</td><td>UAT Session 7</td><td>90 minutes</td><td>9.30 am - 11.00 am</td></tr><tr><td><br></td><td>Tea Break-1</td><td>30 minutes</td><td>11.00 am - 11.30 am</td></tr><tr><td>2</td><td>UAT Session 8</td><td>90 minutes</td><td>11.30 am - 1.00 pm</td></tr><tr><td><br></td><td>Lunch Break</td><td>60 minutes</td><td>1.00 pm - 2.00 pm</td></tr><tr><td>3</td><td>Bugs, Enhancements, Feedback Collection and Prioritization</td><td>120 minutes</td><td>2.00 pm - 4.00 pm</td></tr><tr><td><br></td><td>Tea Break-2</td><td>30 minutes</td><td>4.00 pm - 4.30 pm</td></tr><tr><td>4</td><td>Feedback , Quiz on Training and UAT, Closure </td><td>90 minutes</td><td>4.30 pm - 6.00 pm</td></tr></tbody></table>

The CR analysis may take more than the anticipated timelines. The CR analysis if exceeding more than Day 2, the analysis results, acceptance and prioritisation will be discussed in a subsequent meeting.

### 5.3 UAT Sign-off Checklist

* The signoff shall be provided at the end of UAT by HUDD via email communication or official orders/memo to the eGov.
* All UAT test cases completed: Verified that all UAT test cases, as defined in the UAT plan, have been executed and completed
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
* Post training and UAT sessions, a quiz will be administered to check the familiarity of the participants with MuktaSoft. The quiz must be completed with at least 75% correct responses.

## 6.0 UA Test  Scenarios

Test cases provide a high-level description of the functionality to be tested.  All regression and new functionality test cases are contained in the Excel spreadsheet “UA Test Cases” available at: \[[UAT Test Scenarios](uat-test-case-scenarios.md)]. &#x20;

The team will leverage relevant QA test cases for project-specific functionality.  Each test case based on new functionality will reference a specific functional requirement.

Each script contains: the test case number, test description, requirement number, action to be performed, test data to be utilized, expected results, error descriptions (if applicable), pass/fail results, date tested, and any additional comments from the UA tester.

The UA test scripts are contained within the UAT test case spreadsheet and can be accessed via hyperlinks from each individual test case.

## 7.0 UAT Feedback&#x20;

Defects and change requests are entered and tracked in JIRA by the eGov team during the UAT process.  Each entry includes detailed information about each defect/CR.

#### UAT Defect/CR Tracking

The test team is provided with instructions on how to effectively execute test scripts, as well as identify, capture, and report defects/observations by the eGov team at the beginning of the UAT session. The test team present their findings during the UAT session.&#x20;

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
![](<../../../../.gitbook/assets/image (3) (1) (2).png>)

#### Categorisation&#x20;

eGov in consultation with HUDD will decide acceptance and categorisation of change requests. Change requests found in UAT can be assigned one of three (3) levels of category:

* Must Have – Change requests that are needed for the success of a campaign. No workaround exists.
* Should Have – Change requests that are required for better tracking and monitoring and will increase the ease of use of the system for users. A workaround has been identified and is listed in the CR.
* Good to Have – Change requests that are simply for better visualisation and reporting. It could be excluded if not resolved by the scheduled implementation date.

eGov to endeavour to cover Must Have changes before distribution. Lower priority changes will be taken through the eGov Gating process for planning subsequent releases.

## 8.0 References

The following are reference documents which have been leveraged for project-specific information in the design of the UAT plan:

<table><thead><tr><th width="314">Document</th><th>Document Link</th></tr></thead><tbody><tr><td>Test Case Document </td><td><a href="test-case-scenarios.md">Test case scenarios</a></td></tr><tr><td>Defect/ Change Request Reporting Template</td><td><a href="issue-reporting-template.md">Issue Reporting Template</a></td></tr><tr><td>Training Feedback</td><td><a href="https://docs.google.com/forms/d/1It266KQECgzUtU8uVjSJGCryTuUlpMGlOYHtG4RCw3I/viewform?ts=64620419&#x26;edit_requested=true">Click here </a></td></tr><tr><td>UAT Feedback form</td><td><p>English - <a href="https://docs.google.com/forms/d/1hJh9Idye7CX-2zghcF2IgT2_VMIbq03PJjWt3JSC5hM/edit?ts=645dc757">Click Here</a></p><p>Odiya - <a href="https://docs.google.com/forms/d/1YAAO4tfHADly26ThKKB-JYsxUKKY9IlB_vWYh6f1aLU/edit?ts=64634b8c">Click Here</a></p></td></tr></tbody></table>

