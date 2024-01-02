# Search and View Detailed Estimate

## Scope

View Detailed Estimate

Search Estimate → View Estimate.

## Actors <a href="#actors" id="actors"></a>

No change.

## Details <a href="#details" id="details"></a>

1. There is no change in existing search estimate.
2. Changes are for the attributes added newly.

### Attributes <a href="#attributes" id="attributes"></a>

1. Estimate Number
2. Estimate Type
3. Project ID
4. Project Sanction Date
5. Project Name
6. Project Description
7. Project Details \[\*The project details is shown as view project detail in a separate TAB\*]
8. Estimation Details
9. _**SORs - Below information is displayed in the grid.**_
   1. Type
   2. Code
   3. Description
   4. Unit
   5. Rate
   6. Quantity
   7. Amount
      1. Measurements
         1. Type
         2. Description
         3. Numbers
         4. Length
         5. Breath
         6. Height/ Depth
         7. Quantity
         8. Total
   8. Grand Total - Grid total.
10. _**Non SORs - Below information is displayed in the grid.**_
    1. Description
    2. Unit
    3. Rate
    4. Quantity
    5. Amount
    6. Measurements
       1. Type
       2. Description
       3. Numbers
       4. Length
       5. Breath/ Area
       6. Height/ Depth
       7. Quantity
       8. Total
    7. Grand Total - Grid total.
11. _**Other Charges - Below information is displayed in the grid.**_
    1. Head
    2. Percentage/ Lump-sum
    3. Amount
    4. Total - Grid Total
12. Total Estimated Amount
13. _**View Analysis Statements**_
14. _**Relevant Documents**_
15. _**Timelines**_** \[**DIGIT standard way if displaying the timelines,refer wire-frame and as description in workflow story**]**
16. _**Actions**_ - Based on the workflow state and role logged-in user has.

### Validations <a href="#validations" id="validations"></a>

Not applicable.

### Configurations <a href="#configurations" id="configurations"></a>

Not applicable.

### Actions <a href="#actions" id="actions"></a>

1. For 'In Workflow' Estimate, actions are the workflow actions based on the role of logged-in user.
   1. Save as Draft
   2. Verify and Forward
   3. Technical Sanction
   4. Approve
   5. Send Back
   6. Send Back To Originator
   7. Edit Estimate
   8. Reject
2. For Approved Estimate, actions based on the role of logged-in user.
   1. Create Work Order - If the work order is not created.
   2. View Work Order - If the work order is created and not in **Rejected** status.
   3. Create Revised Estimate - In v2.1
3. For Rejected Estimate, No action/ even action button is not enabled.

### Notifications <a href="#notifications" id="notifications"></a>

Not applicable.

## User Interface <a href="#userinterface" id="userinterface"></a>

<figure><img src="../../../../../../.gitbook/assets/View Detailed Estimate (1).png" alt=""><figcaption></figcaption></figure>

## Acceptance Criteria <a href="#acceptancecriteria" id="acceptancecriteria"></a>

1. Estimate details is displayed as described in the story.
2. Actions are enabled as per the estimate workflow state and role logged-in user has.
