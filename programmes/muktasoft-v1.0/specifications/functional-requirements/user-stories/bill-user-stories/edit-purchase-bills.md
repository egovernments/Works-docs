# Edit Purchase Bills

## **Context**

Provides users with the option to edit purchase bills.

## Action

**On submit -** A workflow pop-up window is displayed based on the logged-in user role. Users can select the respective workflow action. Any changes are saved and an estimate is forwarded to the subsequent user in the workflow.

**On Cancel -** the pop-up window gets closed and the action the submit action gets cancelled.

Messages are shown according to workflow stories.

1. Edit bill action is to be mapped with the Bill Creator.
2. It is configurable and can to mapped with other roles too on demand.
3. Only bills in a workflow can be edited. Rejected and Approved bills cannot be edited.
4. Edit bill allows the user to edit the below-given bill details.

<table><thead><tr><th width="72">#</th><th>Field</th><th width="118">Data Type</th><th width="107">Required</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Bill number</td><td>Read Only</td><td>NA</td><td> </td></tr><tr><td>2</td><td>Bill date</td><td>Read Only</td><td>NA</td><td> </td></tr><tr><td>3</td><td>Work order number</td><td>Read Only</td><td>NA</td><td>Work Order number</td></tr><tr><td>4</td><td>Project ID</td><td>Read Only</td><td>NA</td><td>Project ID</td></tr><tr><td>5</td><td>Project Description</td><td>Read Only</td><td>NA</td><td>Project description of the work.</td></tr><tr><td>6</td><td>Location</td><td>Read Only</td><td>NA</td><td>Locality + Ward</td></tr><tr><td> </td><td><strong>Invoice Details</strong></td><td> </td><td> </td><td> </td></tr><tr><td>5</td><td>Vendor's Name</td><td>Searchable Drop-down</td><td>Y</td><td>The organization of type Vendor Only can be searched here by entering at least first 3 chars.</td></tr><tr><td>6</td><td>Vendor ID</td><td>Read Only</td><td>Y</td><td>Vendor ID of searched and selected vendor is displayed here.</td></tr><tr><td>7</td><td>Invoice No.</td><td>Alphanumeric (64)</td><td>Y</td><td>Vendor’s invoice number</td></tr><tr><td>8</td><td>Invoice Date</td><td>Date</td><td>Y</td><td>Invoice date, it can not be a future date.</td></tr><tr><td>9</td><td>Material Cost</td><td>Numeric</td><td>Y</td><td> </td></tr><tr><td>10</td><td>GST</td><td>Numeric</td><td>Y</td><td> </td></tr><tr><td> </td><td><strong>Bill Details</strong></td><td> </td><td> </td><td> </td></tr><tr><td>12</td><td>Bill Amount</td><td>Numeric</td><td>Y</td><td>Total of Material Cost + GST.</td></tr><tr><td> </td><td><strong>Deductions</strong></td><td><strong>Grid</strong></td><td> </td><td><strong>As per the configuration, deductions will be listed, deductions are applicable to vendor’s invoices only.</strong></td></tr><tr><td>13</td><td>Deduction</td><td>Drop-down</td><td>NA</td><td>Deduction as per the configuration, amount is auto calculated.</td></tr><tr><td>14</td><td>Percentage/ Fixed</td><td>Auto-populated</td><td>NA</td><td>Deduction as per the configuration, amount is auto calculated.</td></tr><tr><td>15</td><td>Amount</td><td>Auto- calculated</td><td>NA</td><td>Deduction as per the configuration, amount is auto calculated.</td></tr><tr><td>16</td><td>Action</td><td>Button</td><td>NA</td><td>Deduction as per the configuration, amount is auto calculated.</td></tr><tr><td>17</td><td>Total</td><td>Auto-calculated</td><td>NA</td><td>Total of all the deductions added.</td></tr><tr><td>18</td><td>Net Payable</td><td>Read Only</td><td>NA</td><td>Total bill amount</td></tr><tr><td> </td><td><strong>Relevant Documents</strong></td><td> </td><td> </td><td> </td></tr><tr><td>19</td><td>Vendor Invoice</td><td>File Picker</td><td>Y</td><td>All the invoices from vendors into one PDF.</td></tr><tr><td>20</td><td>Measurement Book</td><td>File Picker</td><td>Y</td><td>PDF copy of manual measurement book.</td></tr><tr><td>21</td><td>Material Utilisation Log</td><td>File Picker</td><td>Y</td><td>PDF copy of material utilization log.</td></tr><tr><td>22</td><td>Others</td><td> </td><td> </td><td> </td></tr></tbody></table>

Once the estimate is edited, it is re-submitted again for approval process using the action ‘**Submit’**.

## **Notifications**

Not applicable.

## **User Interface**

The user interface for this page is similar to the create bill screen.

## **Acceptance Criteria**

<table><thead><tr><th width="194">Acceptance Criteria</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Role-based access based on configuration.</td></tr><tr><td>2</td><td>The bill which is in the workflow can only be edited.</td></tr><tr><td>3</td><td>Bill is opened in editable mode.</td></tr><tr><td>4</td><td>The details given in the table can be edited by the user.</td></tr><tr><td>5</td><td>On Submit, the bill is again forwarded to the next user for the approval process.</td></tr></tbody></table>
