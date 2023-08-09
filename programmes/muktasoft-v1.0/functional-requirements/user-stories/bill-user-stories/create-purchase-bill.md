# Create Purchase Bill

## Context

Provides users with the scope to create purchase bills.

## Actors

Employee

Role: Bill Creator

## Actions

### Scope

Create Purchase Bill

Search Work Order → View Work Order → Create Purchase Bill

On submit - the Forward pop-up window is opened to forward the bill for verification.

On Forward -

1. Bill record gets saved into the system as bill type **Purchase Bill**, and attain a workflow state ‘**Pending for verification**’.
2. Bill No. is generated in a **specified format**, if it is direct submit.
3. Format for bill No. is **PB/FY/<6digitrunningno.>**. Example: **PB/2022-23/000051**
4. The work bill is available to download in **PDF** as per the given format. There will be a separate ticket for PDF download.

### Details

1. Purchase bill is created for the material supplied for the in-progress projects.
2. **Create Purchase Bill** form is developed as per the UI design provided and the attributes listed below.

#### Attributes

<table><thead><tr><th width="78">#</th><th width="172">Field</th><th width="129">Data Type</th><th width="106">Required</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Work order number</td><td>Read Only</td><td>NA</td><td>Work Order number</td></tr><tr><td>2</td><td>Project ID</td><td>Read Only</td><td>NA</td><td>Project ID</td></tr><tr><td>3</td><td>Project Description</td><td>Read Only</td><td>NA</td><td>Project description of the work.</td></tr><tr><td>4</td><td>Location</td><td>Read Only</td><td>NA</td><td>Locality + Ward</td></tr><tr><td> </td><td><strong>Invoice Details</strong></td><td> </td><td> </td><td> </td></tr><tr><td>5</td><td>Vendor's Name</td><td>Searchable Drop-down</td><td>Y</td><td>The organization of type Vendor Only can be searched here by entering at least first 3 chars.</td></tr><tr><td>6</td><td>Vendor ID</td><td>Read Only</td><td>Y</td><td>Vendor ID of searched and selected vendor is displayed here.</td></tr><tr><td>7</td><td>Invoice No.</td><td>Alphanumeric (64)</td><td>Y</td><td>Vendor’s invoice number</td></tr><tr><td>8</td><td>Invoice Date</td><td>Date</td><td>Y</td><td>Invoice date, it can not be a future date.</td></tr><tr><td>9</td><td>Material Cost</td><td>Numeric</td><td>Y</td><td> </td></tr><tr><td>10</td><td>GST</td><td>Numeric</td><td>N</td><td> </td></tr><tr><td> </td><td><strong>Bill Details</strong></td><td> </td><td> </td><td> </td></tr><tr><td>11</td><td>Bill Date</td><td>Date</td><td>Y</td><td>Today’s date, display only.</td></tr><tr><td>12</td><td>Bill Amount</td><td>Auto-calculated</td><td>Y</td><td>Total of Material Cost + GST.</td></tr><tr><td> </td><td><strong>Deductions</strong></td><td><strong>Grid</strong></td><td> </td><td><strong>As per the configuration, deductions will be listed, deductions are applicable to vendor’s invoices only.</strong></td></tr><tr><td>13</td><td>Deduction</td><td>Drop-down</td><td>NA</td><td>Deduction as per the configuration, amount is auto calculated.</td></tr><tr><td>14</td><td>Percentage/ Fixed</td><td>Auto-populated</td><td>NA</td><td>Deduction as per the configuration, amount is auto calculated.</td></tr><tr><td>15</td><td>Amount</td><td>Auto- calculated</td><td>NA</td><td>Deduction as per the configuration, amount is auto calculated.</td></tr><tr><td>16</td><td>Action</td><td>Button</td><td>NA</td><td>Deduction as per the configuration, amount is auto calculated.</td></tr><tr><td>17</td><td>Total</td><td>Auto-calculated</td><td>NA</td><td>Total of all the deductions added.</td></tr><tr><td>18</td><td>Net Payable</td><td>Read Only</td><td>NA</td><td>Total bill amount</td></tr><tr><td> </td><td><strong>Relevant Documents</strong></td><td> </td><td> </td><td> </td></tr><tr><td>19</td><td>Vendor Invoice</td><td>File Picker</td><td>Y</td><td>All the invoices from vendors into one PDF.</td></tr><tr><td>20</td><td>Measurement Book</td><td>File Picker</td><td>Y</td><td>PDF copy of manual measurement book.</td></tr><tr><td>21</td><td>Material Utilisation Log</td><td>File Picker</td><td>Y</td><td>PDF copy of material utilization log.</td></tr><tr><td>22</td><td>Others</td><td> </td><td> </td><td> </td></tr></tbody></table>

## Validations

Field-level validations as mentioned in the attribute tables.

#### Workflow

It is configurable at the ULB level, the stories for configuring the workflow are given separately.

#### Standard Deductions

## Notifications

Not applicable.

## User Interface

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=3937-39994\&t=CyCIchVyLU0gwL23-4)

## Acceptance Criteria

<table><thead><tr><th width="210">Acceptance Criteria</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Bill created and attain the status of pending verification.</td></tr><tr><td>2</td><td>Bill number is generated as per the format given.</td></tr></tbody></table>

