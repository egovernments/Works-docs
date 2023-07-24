# View Estimate

## Scope

View Estimate

Search Estimate → View Estimate.

## Actors

Employee

Role: All roles applicable to an employee user.

## Details

1. To view the details of the saved Estimate, **View Estimate Page** is provided.
2. Estimate is searched using the **Search Estimate** feature and then on click of Estimate No. view estimate page is opened with the below details displayed.

## Attributes

* Estimate No.
* Estimate Type
* Project ID
* Date of Proposal
* Project Name
* Project Description
* **Project Details \[** The project details are shown as view project detail in a separate TAB**]**
* **Estimation Details**
  1. _**Line Items - Below information is displayed in the grid.**_
     * Description
     * UOM
     * Rate
     * Quantity
     * Amount
  2. Total - Grid total.
  3. _**Overheads - Below information is displayed in the grid.**_
     * Overhead
     * Percentage/ Lump-sum
     * Amount
  4. Total - Grid Total
  5. Total Estimated Amount
* _**Material and Labour Analysis**_
  1. Labour Cost
  2. Material Cost
* _**Attachments**_
  1. Detailed Estimate
  2. Labour Analysis
  3. Material Analysis
  4. Design Document
* _**Timelines**_** \[**DIGIT standard way of displaying the timelines, refer to wire-frame and as described in workflow story**]**
* **Actions** - Based on the workflow state and role the logged-in user has.

## Validations

Not applicable.

## Configurations

Not applicable.

## Actions

* For **In Workflow** Estimates, actions in the **Action Menu,** workflow actions based on the role of the logged-in user.
  1. Verify and Forward,
  2. Technical Sanction
  3. Approve
  4. Send Back
  5. Send Back To Originator
  6. Edit Estimate
  7. Reject
* For **Approved** Estimates, actions in the Action Menu, actions based on the role of the logged-in user.
  1. Create Work Order - If the estimate is not created.
  2. View Work Order - If the work order is created and not in **Rejected** status.
  3. Create Revised Estimate - In V2.
  4. Create Deviation Statement- In V2.
* **Rejected** - No actions/ even action button is not displayed.

## Notifications

Not applicable.

## User Interface

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=2273%3A32708\&t=ezrYIQWHGlDd2IDy-4)

## Acceptance Criteria

<table><thead><tr><th width="195">Acceptance Criteria</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Estimate details are displayed as described in the story.</td></tr><tr><td>2</td><td>Actions are enabled as per the estimated workflow state and role of the logged-in user.</td></tr></tbody></table>
