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

<table><thead><tr><th width="110">S.No.</th><th>Field</th><th width="158">Data Type</th><th width="89">Required</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Estimate No.</td><td>Display Only</td><td>Y</td><td> </td></tr><tr><td>2</td><td>Estimate Type</td><td>Display Only</td><td>Y</td><td> </td></tr><tr><td>3</td><td>Project ID</td><td>Display Only</td><td>Y</td><td> </td></tr><tr><td>4</td><td>Date of proposal</td><td>Display Only</td><td>Y</td><td> </td></tr><tr><td>5</td><td>Project Name</td><td>Display Only</td><td>Y</td><td>This value is populated from project</td></tr><tr><td>6</td><td>Project Description</td><td>Display Only</td><td>Y</td><td>This value is populated from project</td></tr><tr><td>7</td><td><strong>Project Details</strong></td><td><strong>Tab/ Display</strong></td><td> </td><td>Same to project view</td></tr><tr><td>8</td><td><strong>Estimation Details</strong></td><td><strong>Tab</strong></td><td> </td><td> </td></tr><tr><td>9</td><td><em><strong>Line Items</strong></em></td><td>Grid</td><td> </td><td>SOR/ Non-SOR items.</td></tr><tr><td>10</td><td>Description</td><td>Textbox</td><td>Y</td><td>The description of SOR/ Non-SOR item.</td></tr><tr><td>11</td><td>UOM</td><td>Drop-down</td><td>Y</td><td>Unit of measurement from the drop-down.</td></tr><tr><td>12</td><td>Rate</td><td>Numeric</td><td>Y</td><td>Rate per unit</td></tr><tr><td>13</td><td>Quantity</td><td>Numeric</td><td>Y</td><td>Quantity estimated</td></tr><tr><td>14</td><td>Amount</td><td>Auto-calculated</td><td>Y</td><td>Amount calculated, Rate*Quantity.</td></tr><tr><td>15</td><td>Total</td><td>Auto-calculated</td><td>Y</td><td>Grid total</td></tr><tr><td>16</td><td><em><strong>Overhead</strong></em></td><td><strong>Section/ Grid</strong></td><td> </td><td> </td></tr><tr><td>17</td><td>Overhead</td><td>Drop-down</td><td>Y</td><td>The values are populated from the configuration</td></tr><tr><td>18</td><td>Percentage/ Lump-sum</td><td>Display</td><td>Y</td><td>The value is displayed per the configuration.</td></tr><tr><td>19</td><td>Amount</td><td>Auto-calculated</td><td>Y</td><td>Auto-calculated/ User Entered, based on the configuration.</td></tr><tr><td>20</td><td>Total</td><td>Auto-calculated</td><td>Y</td><td>Grid Total</td></tr><tr><td>21</td><td>Total Estimated Amount</td><td>Auto-calculated</td><td>Y</td><td>Total estimated value of the project.</td></tr><tr><td>22</td><td><em><strong>Labour and Material Analysis</strong></em></td><td><em><strong>Section</strong></em></td><td> </td><td> </td></tr><tr><td>23</td><td>Material Cost</td><td>Numeric</td><td>Y</td><td>Cost of the material component</td></tr><tr><td>24</td><td>Labour Cost</td><td>Numeric</td><td>Y</td><td>Cost of the labour component</td></tr><tr><td>25</td><td><em><strong>Relevant Documents</strong></em></td><td> </td><td> </td><td> </td></tr><tr><td>26</td><td>Detailed Estimate</td><td>File Attachment</td><td>Y</td><td>DIGIT standard file attachment component, file size 5MB. </td></tr><tr><td>27</td><td>Labor Analysis </td><td>File Attachment</td><td>Y</td><td>DIGIT standard file attachment component, file size 5MB.</td></tr><tr><td>28</td><td>Material Analysis</td><td>File Attachment</td><td>Y</td><td>DIGIT standard file attachment component, file size 5MB.</td></tr><tr><td>29</td><td>Project Design</td><td>File Attachment</td><td>N</td><td>DIGIT standard file attachment component, file size 5MB.</td></tr><tr><td>30</td><td>Others</td><td>Texbox</td><td>N</td><td>To capture the file which is to be uploaded.</td></tr><tr><td> </td><td> </td><td>File Attachment</td><td>N</td><td>DIGIT standard file attachment component, file size 5MB.</td></tr></tbody></table>

Once the estimate is edited, it is re-submitted again for approval process using the **Submit** action.

## **Notification**

Not applicable.

## **Actions**

**On submit** a workflow pop-up window is displayed based on the logged-in user role.

<table><thead><tr><th width="250">Role</th><th>Workflow window</th></tr></thead><tbody><tr><td>Estimate Creator</td><td>Submit pop-up window</td></tr><tr><td>Estimate Verifier</td><td>Verify and Forward pop-up window</td></tr><tr><td>Technical Sanctioner</td><td>Technical Sanction pop-up window</td></tr><tr><td>Approver</td><td>Approval pop-up window</td></tr></tbody></table>

On taking respective workflow action, changes get saved and the estimate is forwarded to the next user in the workflow.

On Cancel, the pop-up window is closed and the submit action is cancelled.

Messages are displayed as per workflow stories.

## **UI**

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=1828%3A33133\&t=djH0uqfGMEwJm930-4)

## **Acceptance Criteria**

<table><thead><tr><th width="207">Acceptance Criteria</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Configurable role-based access</td></tr><tr><td>2</td><td>Only the estimates in workflow can be edited</td></tr><tr><td>3</td><td>Estimate is opened in editable mode</td></tr><tr><td>4</td><td>The details given in the table can be edited by user</td></tr><tr><td>5</td><td>On Submit the estimate is again forwarded to the next user for the approval process</td></tr></tbody></table>

