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

<table data-header-hidden><thead><tr><th width="96"></th><th width="202"></th><th width="142"></th><th width="105"></th><th></th></tr></thead><tbody><tr><td><strong>S. No.</strong></td><td><strong>Field</strong></td><td><strong>Data Type</strong></td><td><strong>Required</strong></td><td><strong>Description</strong></td></tr><tr><td>1</td><td>Estimate Type</td><td>Auto-selected</td><td>Y</td><td>Options are <strong>Original</strong>, Revised, Deviated.</td></tr><tr><td>2</td><td>Project ID</td><td>Display Only</td><td>Y</td><td>Project ID</td></tr><tr><td>3</td><td>Date of Proposal</td><td>Display Only</td><td>Y</td><td>Date of proposal</td></tr><tr><td>4</td><td>Project Name</td><td>Display Only</td><td>Y</td><td>Name of the project</td></tr><tr><td>5</td><td>Project Description</td><td>Display Only</td><td>Y</td><td>Project description</td></tr><tr><td>6</td><td><strong>Project Details</strong></td><td><strong>Tab</strong></td><td> </td><td>Same as View Project Details Page.</td></tr><tr><td>7</td><td><strong>Estimation Details</strong></td><td><strong>Tab</strong></td><td> </td><td> </td></tr><tr><td>8</td><td><em><strong>Line Items</strong></em></td><td>Grid</td><td>Y</td><td>To capture SOR/ Non-SOR items.</td></tr><tr><td>9</td><td>Description</td><td>Textbox</td><td>Y</td><td>The description of SOR/ Non-SOR item.</td></tr><tr><td>10</td><td>UOM</td><td>Drop-down</td><td>Y</td><td>Unit of measurement from the drop-down.</td></tr><tr><td>11</td><td>Rate</td><td>Numeric</td><td>Y</td><td>Rate per unit</td></tr><tr><td>12</td><td>Quantity</td><td>Numeric</td><td>Y</td><td>Quantity estimated</td></tr><tr><td>13</td><td>Amount</td><td>Auto-calculated</td><td>Y</td><td>Amount calculated, Rate*Quantity.</td></tr><tr><td>14</td><td><em>Total</em></td><td><em>Auto-calculated</em></td><td><em>Y</em></td><td><em>Grid total</em></td></tr><tr><td>15</td><td><em><strong>Overheads</strong></em></td><td><strong>Section/ Grid</strong></td><td>Y</td><td>A grid to add the overheads configured in the system.</td></tr><tr><td>16</td><td>Overhead</td><td>Drop-down</td><td>Y</td><td>Overhead from the drop-down</td></tr><tr><td>17</td><td>Percentage/ Lump-sum</td><td>Display</td><td>Y</td><td>Valued from the configuration.</td></tr><tr><td>18</td><td>Amount</td><td>Numeric</td><td>Y</td><td>Auto-calculated/ user entered based on the configuration</td></tr><tr><td>19</td><td><em>Total</em></td><td><em>Auto-calculated</em></td><td><em>Y</em></td><td><em>Grid Total</em></td></tr><tr><td>20</td><td>Total Estimated Amount</td><td>Auto-calculated</td><td>Y</td><td>Total Estimated Amount = Line Item Amount + Total of all the overheads/ additions.</td></tr><tr><td>21</td><td><em><strong>Labour and Material Analysis</strong></em></td><td><em><strong>Section</strong></em></td><td> </td><td> </td></tr><tr><td>22</td><td>Material Cost</td><td>Numeric</td><td>Y</td><td>Cost of material component of the work.</td></tr><tr><td>23</td><td>Labour Cost</td><td>Numeric</td><td>Y</td><td>Cost of labour component of the work.</td></tr><tr><td>24</td><td><em><strong>Relevant Documents</strong></em></td><td> </td><td> </td><td> </td></tr><tr><td>25</td><td>Detailed Estimate</td><td>File Attachment</td><td>Y</td><td><p>DIGIT standard file attachment component, file size 5MB. </p><p>Format support doc,docx, xls,xlsx pdf, jpg.</p></td></tr><tr><td>26</td><td>Labor Analysis </td><td>File Attachment</td><td>Y</td><td><p>DIGIT standard file attachment component, file size 5MB.</p><p>Format support doc,docx, xls,xlsx pdf, jpg.</p></td></tr><tr><td>27</td><td>Material Analysis</td><td>File Attachment</td><td>Y</td><td><p>DIGIT standard file attachment component, file size 5MB.</p><p>Format support doc,docx, xls,xlsx pdf, jpg.</p></td></tr><tr><td>28</td><td>Project Design</td><td>File Attachment</td><td>N</td><td><p>DIGIT standard file attachment component, file size 5MB.</p><p>Format support doc,docx, xls,xlsx pdf, jpg.</p></td></tr><tr><td>29</td><td>Others</td><td>Texbox</td><td>N</td><td>To capture the file which is to be uploaded.</td></tr><tr><td> </td><td> </td><td>File Attachment</td><td>N</td><td><p>DIGIT standard file attachment component, file size 5MB.</p><p>Format support doc,docx, xls,xlsx pdf, jpg.</p></td></tr></tbody></table>

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

<table><thead><tr><th width="206">Acceptance Criteria</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Overheads are rendered and their values are calculated according to the configuration.</td></tr><tr><td>2</td><td>On Submit, the estimate gets saved, workflow state changes accordingly, and estimate no. is generated.</td></tr></tbody></table>

