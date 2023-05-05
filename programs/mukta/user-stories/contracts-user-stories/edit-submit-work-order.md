# Edit/Submit Work Order

## **Scope**

1. Edit Work Order action is to be mapped with Work Order Creator.
2. It is configurable and can to mapped with other roles too on demand.
3. The work order which is in the workflow can only be edited.
4. Rejected, Approved, and Accepted work orders can not be edited.
5. Edit work orders allows the user to edit the below-given work order detail.

| #  | Field                            | Data Type                               | Required | Description                                                                                                                                                                                                                                                                                                     |
| -- | -------------------------------- | --------------------------------------- | -------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1  | Work order number                | Display Only                            | NA       | Work order no.                                                                                                                                                                                                                                                                                                  |
| 2  | Project ID                       | Display Only                            | NA       | Project ID of the project.                                                                                                                                                                                                                                                                                      |
| 3  | Date of proposal                 | Display Only                            | NA       | Date of the proposal from the project.                                                                                                                                                                                                                                                                          |
| 4  | Project name                     | Display Only                            | NA       | Project name                                                                                                                                                                                                                                                                                                    |
| 5  | Project description              | Display Only                            | NA       | Project description                                                                                                                                                                                                                                                                                             |
| 6  | **Project Details**              | **Tab**                                 |          | Displayed as per view project details.                                                                                                                                                                                                                                                                          |
| 7  | **Estimate Details**             | **Tab**                                 |          | Displayed as per view estimate details.                                                                                                                                                                                                                                                                         |
| 8  | **Work Order Details**           | **Tab**                                 |          |                                                                                                                                                                                                                                                                                                                 |
| 9  | Name of CBO                      | Drop-down                               | Y        | The name of the CBO from the organization master maintained at the ULB level. The name is searchable in the drop-down.                                                                                                                                                                                          |
| 10 | CBO ID                           | Display                                 | Y        | The CBO ID from the organization registry.                                                                                                                                                                                                                                                                      |
| 11 | Role of CBO                      | <p>Drop-down</p><p>(Auto- selected)</p> | Y        | <p>The role of the CBO is decided based on the estimated amount. It is configurable in the system.</p><ol><li>IP (Implementation Partner) - If the estimated cost of the works is more than Rs.15 Lakhs</li><li>IA (Implementation Agency) -  If the estimated cost of the works is up to Rs.15 Lakhs</li></ol> |
| 12 | Name of the officer in-charge    | Drop-down                               | Y        | The drop-down values are population based on the role assigned. The name is searchable in the drop-down. Name + Designation                                                                                                                                                                                     |
| 13 | Designation of officer in-charge | Display                                 | Y        | Displayed from the EIS/User’s record saved in the system.                                                                                                                                                                                                                                                       |
| 14 | Project completion period        | Numeric                                 | Y        | Number of days work to be completed.                                                                                                                                                                                                                                                                            |
| 15 | Work order amount                | Read Only                               | Y        | Total estimated cost of the selected work.                                                                                                                                                                                                                                                                      |
|    | **Relevant Documents**           | **Sections**                            |          |                                                                                                                                                                                                                                                                                                                 |
| 16 | BOQ                              | File Attachment                         | Y        | Allows single file, not greater than 5 MB. Files can be of type doc, xls, pdf, jpg.                                                                                                                                                                                                                             |
| 17 | Labour Analysis                  | File Attachment                         | Y        | Allows single file, not greater than 5 MB. Files can be of type doc, xls, pdf, jpg.                                                                                                                                                                                                                             |
| 18 | Material Analysis                | File Attachment                         | Y        | Allows single file, not greater than 5 MB. Files can be of type doc, xls, pdf, jpg.                                                                                                                                                                                                                             |
| 19 | Terms and conditions             | File Attachment                         | Y        | Allows single file, not greater than 5 MB. Files can be of type doc, xls, pdf, jpg.                                                                                                                                                                                                                             |
| 20 | Others                           | Textbox                                 | N        | To capture the file name                                                                                                                                                                                                                                                                                        |
| 21 |                                  | File Attachment                         | N        | To attach the file file the name entered above in the textbox.                                                                                                                                                                                                                                                  |

Once the work order is edited, it is re-submitted for approval using the **Submit** action button.

## **Notification**

Not applicable.

## **Actions**

Based on the logged-in user role, a workflow pop-up window is displayed on submit.

| Role                | Workflow window                  |
| ------------------- | -------------------------------- |
| Work Order Creator  | Submit pop-up window             |
| Work Order Verifier | Verify and Forward pop-up window |
| Approver            | Approval pop-up window           |

1. On respective workflow action, changes get saved and the work order is forwarded to the next user in the workflow.
2. On Cancel, the pop-up window gets closed and the action gets cancelled.
3. Accordingly, the messages are shown.

## **User Interface**

\<To be updated>

## **Acceptance Criteria**

| Acceptance Criteria | Description                                                                 |
| ------------------- | --------------------------------------------------------------------------- |
| 1                   | Role-based access based on configuration.                                   |
| 2                   | The work order which is in the workflow can only be edited.                 |
| 3                   | The work order is opened in editable mode.                                  |
| 4                   | The details given in the table can be edited by the user.                   |
| 5                   | On Submit, the work order is again forwarded to the next user for approval. |

