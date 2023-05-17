# Estimate Edit/Submit Workflow

## **Scope**

Edit estimate details.

## **Actors**

Estimate Creator

## Details

### **Edit Estimate**

1. The Edit Estimate action is mapped to the Estimate Creator user role.
2. It is configurable and can be mapped to other roles too as per requirement.
3. The estimate which is in a workflow can only be edited. Rejected and approved estimates can not be edited.
4. Edit Estimate allows the user to edit the below-given estimate details.

| S.No. | Field                              | Data Type         | Required | Description                                                |
| ----- | ---------------------------------- | ----------------- | -------- | ---------------------------------------------------------- |
| 1     | Estimate No.                       | Display Only      | Y        |                                                            |
| 2     | Estimate Type                      | Display Only      | Y        |                                                            |
| 3     | Project ID                         | Display Only      | Y        |                                                            |
| 4     | Date of proposal                   | Display Only      | Y        |                                                            |
| 5     | Project Name                       | Display Only      | Y        | This value is populated from project                       |
| 6     | Project Description                | Display Only      | Y        | This value is populated from project                       |
| 7     | **Project Details**                | **Tab/ Display**  |          | Same to project view                                       |
| 8     | **Estimation Details**             | **Tab**           |          |                                                            |
| 9     | _**Line Items**_                   | Grid              |          | SOR/ Non-SOR items.                                        |
| 10    | Description                        | Textbox           | Y        | The description of SOR/ Non-SOR item.                      |
| 11    | UOM                                | Drop-down         | Y        | Unit of measurement from the drop-down.                    |
| 12    | Rate                               | Numeric           | Y        | Rate per unit                                              |
| 13    | Quantity                           | Numeric           | Y        | Quantity estimated                                         |
| 14    | Amount                             | Auto-calculated   | Y        | Amount calculated, Rate\*Quantity.                         |
| 15    | Total                              | Auto-calculated   | Y        | Grid total                                                 |
| 16    | _**Overhead**_                     | **Section/ Grid** |          |                                                            |
| 17    | Overhead                           | Drop-down         | Y        | The values are populated from the configuration            |
| 18    | Percentage/ Lump-sum               | Display           | Y        | The value is displayed per the configuration.              |
| 19    | Amount                             | Auto-calculated   | Y        | Auto-calculated/ User Entered, based on the configuration. |
| 20    | Total                              | Auto-calculated   | Y        | Grid Total                                                 |
| 21    | Total Estimated Amount             | Auto-calculated   | Y        | Total estimated value of the project.                      |
| 22    | _**Labour and Material Analysis**_ | _**Section**_     |          |                                                            |
| 23    | Material Cost                      | Numeric           | Y        | Cost of the material component                             |
| 24    | Labour Cost                        | Numeric           | Y        | Cost of the labour component                               |
| 25    | _**Relevant Documents**_           |                   |          |                                                            |
| 26    | Detailed Estimate                  | File Attachment   | Y        | DIGIT standard file attachment component, file size 5MB.   |
| 27    | Labor Analysis                     | File Attachment   | Y        | DIGIT standard file attachment component, file size 5MB.   |
| 28    | Material Analysis                  | File Attachment   | Y        | DIGIT standard file attachment component, file size 5MB.   |
| 29    | Project Design                     | File Attachment   | N        | DIGIT standard file attachment component, file size 5MB.   |
| 30    | Others                             | Texbox            | N        | To capture the file which is to be uploaded.               |
|       |                                    | File Attachment   | N        | DIGIT standard file attachment component, file size 5MB.   |

Once the estimate is edited, it is re-submitted again for approval process using the **Submit** action.

## **Notification**

Not applicable.

## **Actions**

**On submit** a workflow pop-up window is displayed based on the logged-in user role.

| Role                 | Workflow window                  |
| -------------------- | -------------------------------- |
| Estimate Creator     | Submit pop-up window             |
| Estimate Verifier    | Verify and Forward pop-up window |
| Technical Sanctioner | Technical Sanction pop-up window |
| Approver             | Approval pop-up window           |

On taking respective workflow action, changes get saved and the estimate is forwarded to the next user in the workflow.

On Cancel, the pop-up window is closed and the submit action is cancelled.

Messages are displayed as per workflow stories.

## **UI**

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=1828%3A33133\&t=djH0uqfGMEwJm930-4)

## **Acceptance Criteria**

| Acceptance Criteria | Description                                                                         |
| ------------------- | ----------------------------------------------------------------------------------- |
| 1                   | Configurable role-based access                                                      |
| 2                   | Only the estimates in workflow can be edited                                        |
| 3                   | Estimate is opened in editable mode                                                 |
| 4                   | The details given in the table can be edited by user                                |
| 5                   | On Submit the estimate is again forwarded to the next user for the approval process |

