# View Muster Roll

## Context

Provide users with the option to view muster rolls.

## Actors

Employee

Role: Muster Roll Verifier, Muster Roll Approver.

## Actions

### Scope

View Muster Roll

Search Muster Roll→ View Muster Roll

1. For Muster Rolls in workflow - workflow actions are based on the role of the logged-in user.
   * Edit
   * Verify and Forward
   * Send Back
   * Send Back To CBO
   * Approve
2. For Approved Muster Roll
   * None (as of now)

### Details

1. To view the details of the muster roll, the **View Muster Roll** page is provided.
2. The muster roll is searched using the search Muster Roll feature and then on click of Muster Roll ID, the View Muster Roll page is opened displaying the below details.

#### Attributes

1. Muster Roll ID
2. Work Order Number
3. Project ID
4. Project description
5. Name of CBO
6. Role of CBO
7. Muster roll period
8. No. of wage seekers
9. Total attendance (in days)
10. Quantity of work (in days)
11. Total wage amount(₹)
12. **Attendance Details -** In tabular form
    * Sr. No.
    * ID
    * Name
    * Father/ Husband Name
    * Skill
    * Date/ Day (7 days)
    * Days Worked
    * Days Measured
    * Wage Per Day
    * Total Wage
    * Account/ IFSC
    * Aadhaar (Masked)
13. **Workflow timelines** - As per the designed UI.

## Validations

Not applicable.

## Configurations

Not applicable.

## Notifications

Not applicable.

## User Interface

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=3290%3A35413\&t=cbmvGs4oGd2vjDTA-4)

## Acceptance Criteria

<table><thead><tr><th width="249">Acceptance Criteria</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Muster roll details are displayed as described in the story.</td></tr><tr><td>2</td><td>Actions are enabled as per the muster roll workflow state and role of the logged-in user.</td></tr></tbody></table>

