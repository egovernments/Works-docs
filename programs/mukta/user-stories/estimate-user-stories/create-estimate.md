# Create Estimate

## Context

The estimate is a document which is prepared to estimate the amount of work required to complete. The estimate helps the Government in tendering, contracting and measuring the work to release the payment.

## Scope

Create Estimate

Search Project → Search Result → View Project Details → Create Estimate

## Actors

Employee Role: Estimate Creator

## Details

1. For each project, an estimate is created to award the work to CBO/ JE.
2. **Create Estimate** form is developed as per the UI design provided and the attributes listed below.

## Attributes

| **S. No.** | **Field**                          | **Data Type**     | **Required** | **Description**                                                                                                    |
| ---------- | ---------------------------------- | ----------------- | ------------ | ------------------------------------------------------------------------------------------------------------------ |
| 1          | Estimate Type                      | Auto-selected     | Y            | Options are **Original**, Revised, Deviated.                                                                       |
| 2          | Project ID                         | Display Only      | Y            | Project ID                                                                                                         |
| 3          | Date of Proposal                   | Display Only      | Y            | Date of proposal                                                                                                   |
| 4          | Project Name                       | Display Only      | Y            | Name of the project                                                                                                |
| 5          | Project Description                | Display Only      | Y            | Project description                                                                                                |
| 6          | **Project Details**                | **Tab**           |              | Same as View Project Details Page.                                                                                 |
| 7          | **Estimation Details**             | **Tab**           |              |                                                                                                                    |
| 8          | _**Line Items**_                   | Grid              | Y            | To capture SOR/ Non-SOR items.                                                                                     |
| 9          | Description                        | Textbox           | Y            | The description of SOR/ Non-SOR item.                                                                              |
| 10         | UOM                                | Drop-down         | Y            | Unit of measurement from the drop-down.                                                                            |
| 11         | Rate                               | Numeric           | Y            | Rate per unit                                                                                                      |
| 12         | Quantity                           | Numeric           | Y            | Quantity estimated                                                                                                 |
| 13         | Amount                             | Auto-calculated   | Y            | Amount calculated, Rate\*Quantity.                                                                                 |
| 14         | _Total_                            | _Auto-calculated_ | _Y_          | _Grid total_                                                                                                       |
| 15         | _**Overheads**_                    | **Section/ Grid** | Y            | A grid to add the overheads configured in the system.                                                              |
| 16         | Overhead                           | Drop-down         | Y            | Overhead from the drop-down                                                                                        |
| 17         | Percentage/ Lump-sum               | Display           | Y            | Valued from the configuration.                                                                                     |
| 18         | Amount                             | Numeric           | Y            | Auto-calculated/ user entered based on the configuration                                                           |
| 19         | _Total_                            | _Auto-calculated_ | _Y_          | _Grid Total_                                                                                                       |
| 20         | Total Estimated Amount             | Auto-calculated   | Y            | Total Estimated Amount = Line Item Amount + Total of all the overheads/ additions.                                 |
| 21         | _**Labour and Material Analysis**_ | _**Section**_     |              |                                                                                                                    |
| 22         | Material Cost                      | Numeric           | Y            | Cost of material component of the work.                                                                            |
| 23         | Labour Cost                        | Numeric           | Y            | Cost of labour component of the work.                                                                              |
| 24         | _**Relevant Documents**_           |                   |              |                                                                                                                    |
| 25         | Detailed Estimate                  | File Attachment   | Y            | <p>DIGIT standard file attachment component, file size 5MB. </p><p>Format support doc,docx, xls,xlsx pdf, jpg.</p> |
| 26         | Labor Analysis                     | File Attachment   | Y            | <p>DIGIT standard file attachment component, file size 5MB.</p><p>Format support doc,docx, xls,xlsx pdf, jpg.</p>  |
| 27         | Material Analysis                  | File Attachment   | Y            | <p>DIGIT standard file attachment component, file size 5MB.</p><p>Format support doc,docx, xls,xlsx pdf, jpg.</p>  |
| 28         | Project Design                     | File Attachment   | N            | <p>DIGIT standard file attachment component, file size 5MB.</p><p>Format support doc,docx, xls,xlsx pdf, jpg.</p>  |
| 29         | Others                             | Texbox            | N            | To capture the file which is to be uploaded.                                                                       |
|            |                                    | File Attachment   | N            | <p>DIGIT standard file attachment component, file size 5MB.</p><p>Format support doc,docx, xls,xlsx pdf, jpg.</p>  |

## Validations

1. Field level validations as mentioned in the attribute tables and the in-line validations are displayed.
   * Amount: “Amount can include numbers only.”
   * Material Cost: “Material cost includes numbers only.”
   * Labour Cost: “Labour cost includes numbers only.”
2. The total Material Cost and Labour Costs should not be more than the Total Estimated Amount.
   * Validation Message: “Material and labour costs should not be more than the estimated amount.”

## Configurations

### Attachments

DIGIT standard attachment component.

### Workflow

It is configurable at the ULB level, the stories for configuring the workflow are given separately.

### Overheads/ Additions

1. The overheads in general being used in estimates are given below.
   * **Royalty on Earth Work** - It is user entered value
   * **Supervision Charge** - It is calculated and calculated on the line item amount at the rate of 7.5%.
   * **Goods and Service Tax** - It is calculated and calculated on the line item amount at the rate of 18%.
2. Overheads are configurable in the system and configured with its complete definition.
3. There is a separate ticket for overhead configuration.

## Actions

#### On Submit

1. The workflow window is displayed to capture the assignee name and the comments for forwarding the estimate.
2. On Forward -
   * **The success Page** is displayed.
   * The estimate record gets saved into the system, and the workflow state reflects ‘**Pending for verification**’.
   * Estimate No. is generated in a **specified format**, if it is a direct submit.
   * Format for Estimate No. is **ES/FY/<6digitrunningno.>**. Example: **ES/2022-23/000051**
   * The 6-digit running sequence no. is reset to 1 at the start of every FY.
   * The estimate is available to download in **PDF** as per the given format. There will be a separate ticket for PDF download.
3. In case the system fails to create the record, the **Failure Page** is displayed.

## Notifications

Not applicable.

## User Interface

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=2435%3A35724\&t=ejsnb7xhkFG3BDc9-4)

## Acceptance Criteria

| Acceptance Criteria | Description                                                                                            |
| ------------------- | ------------------------------------------------------------------------------------------------------ |
| 1                   | Overhead are rendered and their values are calculated according to the configuration.                  |
| 2                   | On Submit, the estimate gets saved, workflow state changes accordingly, and estimate no. is generated. |
| 3                   |                                                                                                        |

