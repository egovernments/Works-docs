# Estimate Workflow (Role Action Mapping)

## **Context**

For any project, an estimate is prepared and then sent for the approval process. The approval process contains various workflow levels and states associated with those levels.

## **Scope**

Estimate preparation for a work, by the Estimate Creator and then its verification and approval by other users (actors) in the workflow.

## **Details**

### Role (Actors) - Action Mapping

| S.No. | Role (Actors)         | Actions                                                                                                                           | User Persona                              |
| ----- | --------------------- | --------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------- |
| 1     | ESTIMATE\_CREATOR     | <ul><li>Create</li><li>Submit</li><li>Search</li><li>View</li><li>Edit/ Re-submit</li></ul>                                       | Junior Engineer/ Assistant Engineer       |
| 2     | ESTIMATE\_VERIFIER    | <ul><li>Search</li><li>View</li><li>Verify and Forward</li><li>Send Back</li></ul>                                                | Executive Engineer                        |
| 3     | TECHNICAL\_SANCTIONER | <ul><li>Search</li><li>View</li><li>Technical Sanction</li><li>Send Back</li><li>Send Back To Originator</li><li>Reject</li></ul> | Municipal Engineer                        |
| 4     | ESTIMATE\_ APPROVER   | <ul><li>Search</li><li>View</li><li>Approve</li><li>Send Back</li><li>Send Back To Originator</li><li>Reject</li></ul>            | Executive Officer/ Municipal Commissioner |
| 5     | ESTIMATE\_VIEWER      | <ul><li>Search</li><li>View</li></ul>                                                                                             | MUKTA Cordinator                          |

### Workflow States

| #  | Action                  | Role                           | From State                     | To State                       | Status                 |
| -- | ----------------------- | ------------------------------ | ------------------------------ | ------------------------------ | ---------------------- |
| 1  | Submit                  | Estimate Creator               |                                | Pending for verification       | Submitted              |
| 2  | Verify and Forward      | Estimate Verifier              | Pending for verification       | Pending for technical sanction | Verified               |
| 3  | Technical Sanction      | Technical Sanctioner           | Pending for technical sanction | Pending for approval           | Technically Sanctioned |
| 4  | Send Back               | Estimate Verifier              | Pending for verification       | Pending for correction         | Sent Back              |
| 5  | Send Back               | Technical Sanctioner           | Pending for technical sanction | Pending for verification       | Sent Back              |
| 6  | Send Back               | Estimate Approver              | Pending for approval           | Pending for technical sanction | Sent Back              |
| 7  | Send Back To Originator | **\<roles having access>**     | **\<Current Status>**          | Pending for correction         | Sent Back              |
| 8  | Edit/ Re-submit         | Estimate Creator               | Pending for correction         | Pending for verification       | Re-submitted           |
| 9  | Approve                 | Estimate Approver              | Pending for approval           | Approved                       | Approved               |
| 10 | Reject                  | **\<any roles having access>** | **\<Current Status>**          | Rejected                       | Rejected               |

## **SLAs**

| Service Name | Workflow State/Event | Current State                  | SLA (In Days) |
| ------------ | -------------------- | ------------------------------ | ------------- |
| Estimate     | Edit/ Re-submit      | Pending for correction         | 1             |
|              | Verify and Forward   | Pending for verification       | 2             |
|              | Technical Sanction   | Pending for technical sanction | 1             |
|              | Approve              | Pending for approval           | 1             |

## **UI**

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=2168%3A32051\&t=v7XALjtyM4MwBoaO-4)

## **Acceptance Criteria**

| Acceptance Criteria | Description                                                                                                                |
| ------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| 1                   | Roles are created as given provided.                                                                                       |
| 2                   | Actions are configured based on role-action mapping.                                                                       |
| 3                   | Workflow states are defined as provided and the state transition is done accordingly by updating the status appropriately. |

