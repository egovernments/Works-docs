# Work Order Workflow

## **Context**

Work order is created for an approved estimate in order to award the work to CBO and then send it for the approval process. The approval process contains various workflow levels and states associated with those levels.

## **Scope**

Work order preparation for a work by the Work Order Creator and then its verification and approval by other users (actors) in the workflow.

## **Details**

### Role (Actors) - Action Mapping

| # | Role                | Action                                                                                                                   | User Persona                                                       |
| - | ------------------- | ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------ |
| 1 | WORK ORDER CREATOR  | <ul><li>Create </li><li>Search </li><li>View </li><li>Edit/ Re-submit</li><li>Submit </li><li>Reject</li></ul>           | Junior Engineer/ Assistant Engineer                                |
| 2 | WORK ORDER VERIFIER | <ul><li>Search</li><li>View </li><li>Verify and Forward</li><li>Send Back </li></ul>                                     | Executive Officer                                                  |
| 3 | WORK ORDER APPROVER | <ul><li>Search</li><li>View </li><li>Approve</li><li>Send Back </li><li>Send Back To Originator</li><li>Reject</li></ul> | Municipal Engineer                                                 |
| 4 | CBO ADMIN           | <ul><li>Accept</li><li>Decline</li></ul>                                                                                 | Community based organization contact person (President/ Secretary) |

### Workflow States

| #  | Action                  | Role                           | From State                | To State                  | Status       |
| -- | ----------------------- | ------------------------------ | ------------------------- | ------------------------- | ------------ |
| 1  | Submit                  | Work Order Creator             |                           | Pending for verification  | Submitted    |
| 2  | Verify and Forward      | Work Order Verifier            | Pending for verification  | Pending for approval      | Verified     |
| 3  | Send Back               | Work Order Verifier            | Pending for verification  | Pending for correction    | Sent Back    |
| 4  | Send Back               | Work Order Approver            | Pending for approval      | Pending for verification  | Sent Back    |
| 5  | Send Back To Originator | **\<any roles having access>** | **\<Current Status>**     | Pending for correction    | Sent Back    |
| 6  | Edit/ Re-submit         | Work Order Creator             | Pending for correction    | Pending for verification  | Re-submitted |
| 7  | Approve                 | Work Order Approver            | Pending for approval      | Approved                  | Approved     |
| 8  | Reject                  | **\<any roles having access>** | **\<Current Status>**     | Rejected                  | Rejected     |
| 9  | Accept                  | CBO Admin                      | Approved                  | Accepted                  | Accepted     |
| 10 | Decline                 | CBO Admin                      | Approved                  | Pending for re-assignment | Declined     |
| 11 | Edit/ Re-submit         | Work Order Creator             | Pending for re-assignment | Pending for verification  | Re-submitted |

### SLAs

| Service Name | Action             | Current State             | SLAs (In Days) |
| ------------ | ------------------ | ------------------------- | -------------- |
| Work Order   | Edit/ Re-submit    | Pending for correction    | 1              |
|              | Edit/ Re-submit    | Pending for re-assignment | 1              |
|              | Verify and Forward | Pending for verification  | 2              |
|              | Approve            | Pending for approval      | 1              |
|              | Accept             | Approved                  | 7              |

## **User Interface (UI)**

UI design is going to be the same as the estimate workflow. Only the workflow states will be displayed as per the table given above.

## **Acceptance Criteria**

| Acceptance Criteria | Description                                                                           |
| ------------------- | ------------------------------------------------------------------------------------- |
| 1                   | Actions are configured based on role-action mapping.                                  |
| 2                   | Workflow states are defined as provided and the state transition is done accordingly. |
