# Measurements

## Overview

Measurement books or M-Books help track the work progress once the execution of the contract is initiated.&#x20;

Click on the MBook feature below to view functional details:

* [MBook Create](measurements.md#mbook-create)
* [MBook Track](measurements.md#mbook-track)
* [MBook Cancel](measurements.md#mbook-cancel)

## **MBook Create**

### **Need**

Digitising offline measurement books offers several advantages, including:

1. **Faster Measurement Capture**: Digital tools allow for quicker and more efficient recording of measurements, reducing the time required for data entry.
2. **Timely Data Capture**: Real-time or near-real-time data capture ensures that measurements are recorded promptly, eliminating delays in processing.
3. **Error-Free Calculation**: Automated calculations reduce the risk of human errors in measurement calculations, leading to more accurate results.
4. **Automation of Billing**: Digital systems can automate the billing process, generating invoices and reports based on the captured measurements, further streamlining operations.

Overall, digitisation enhances efficiency, accuracy, and the overall effectiveness of measurement and billing processes.

### **Background**

1. Measurement Books are legal copies signed and issued by contract\_creator to the contractor noting down the Book ID, Number of Pages, and Title (as per project title).&#x20;
2. In offline methods, measurements can be filled daily, weekly, monthly or as per demand (usually before the time of bill creation) to raise a bill and attach a copy of the book as a reference document validating the bill information.
3. Measurement Books are initially empty. The M-Books will be filled with the estimated line items only. Once all the estimated line items are filled/counted in the MBook, they can be submitted along with the final Bill.&#x20;
4. The Book is also sent as an attachment to the accountant for bill approval.

### **User**

* The system creates the M-Book automatically while the contract is accepted.&#x20;
* Contractor/MBook-tracker will track M-Book readings
* MBook-Checker will check the measurements
* MBook-Approver will approve the measurements

### **Details**

1. While creating an estimate, the estimate creator can add measurement rows for each SOR /Non-SOR line item. It is not mandatory to fill in these measurements unless the user clicks the "+" icon in the Quantity section of the SOR line item row.
2. Upon selecting the measurement box, an expansion slide-down will appear. Here he/she can enter the measurement details
3. The user can delete or add multiple measurement items.&#x20;
4. The measurement box will contain fields for quantity, length, width, and height/depth and the product of these three values will be automatically calculated and populated in the Quantity box.
5. In cases where an object's area is not measured using length, width, and height, the user can directly enter the area in the Quantity field. The fields for length, width, and size should be greyed out and not editable in such cases.
6. The summation of all the measurement quantities will be automatically populated in the SOR/Non-SOR Quantity row. This quantity will then be multiplied by the rate to calculate the final amount.
7. Measurement Book will be created only when the contract is accepted.
8. Mbook line items will be SOR line items if while creating an estimate, a sub-line item under SOR is not created.&#x20;
   * If SOR sub-line items are created, the M-Book will have to be tracked at the SOR sub-line items level.&#x20;
9. There should be an option to capture images of physical MBook and site photos along with MBook readings for each date.&#x20;
10. Each MBook entry will go for approval workflow

### **Specifications**

<table><thead><tr><th width="152">Field</th><th width="140">Data Type</th><th width="109">Required (Y/N)</th><th>Comments</th></tr></thead><tbody><tr><td>ID</td><td>NA</td><td>NA</td><td>UUID</td></tr><tr><td>MBook ID</td><td>Alphanumeric</td><td>Y</td><td><p>Mbook ID</p><p>MB&#x3C;Year>/&#x3C;Mo>/&#x3C;Running Sequence></p></td></tr><tr><td>Contract ID</td><td>Autofill</td><td>Y</td><td>Every Mbook is linked to a contract</td></tr><tr><td>MBook Created Date</td><td></td><td></td><td><p>Date it is created in the system.</p><p>Typically date of acceptance of Contract</p></td></tr><tr><td>MBook start Date</td><td>Date</td><td>Y</td><td>Start date of Measurement Book - From this date onwards readings can be taken</td></tr><tr><td>MBook end date</td><td>Date</td><td>Y</td><td>End date of Measurement Book - On this date onwards readings capture should stop</td></tr><tr><td><em>[Array for each dated entry]</em></td><td></td><td></td><td></td></tr><tr><td>Mbook reference number</td><td>Text</td><td>Y</td><td>Offline reference number of Mbook, Since this may change after few weeks due to limit in number of pages in each mbook, readings this could be captured with each date</td></tr><tr><td>MB Entry Date</td><td>Alphanumeric</td><td>Y</td><td>Default to today's date. Can take dates between mbook start date and today's date. Cannot be future date</td></tr><tr><td>MB from page</td><td>Alphanumeric</td><td>Y</td><td>Offline reference of Page numbers in mbook hard copy.</td></tr><tr><td>Mb To Page</td><td>Date</td><td>Y</td><td>Offline reference of Page numbers in mbook hard copy.</td></tr><tr><td>Attachments</td><td>Attachments</td><td>N</td><td>Photos of site, photos of physical mbook</td></tr><tr><td><em>[Array for each SOR/NON SOR Line Item]</em></td><td></td><td></td><td></td></tr><tr><td>SOR ID</td><td>View Only</td><td>N</td><td>Only for Line items that have SOR ID</td></tr><tr><td>Description</td><td>View Only</td><td>Y</td><td>From Estimate</td></tr><tr><td>UOM</td><td>View Only</td><td>Y</td><td>From Estimate</td></tr><tr><td>Approved Quantity</td><td>View Only</td><td>Y</td><td>From Estimate</td></tr><tr><td>Approved Rate</td><td>View Only</td><td>Y</td><td>From Estimate</td></tr><tr><td>Current MB Entry</td><td>Numeric</td><td>Y</td><td>Entry from last reading till current reading</td></tr><tr><td>Remarks</td><td>Alphanumeric</td><td>N</td><td>Comments if any against that particular reading.</td></tr><tr><td><em>[Array for each Sub Line Item if defined during estimation]</em></td><td></td><td></td><td></td></tr><tr><td>Is Deduction?</td><td>Binary</td><td>Y</td><td><p>Yes/No.</p><p>This is used to measure if any Sub line item has to be measured fully and removed a certain piece. Since payment is done on overall quantity and not based on individual sub line item level measurements this will not affect billing</p></td></tr><tr><td>Description</td><td>Alphanumeric</td><td>Y</td><td></td></tr><tr><td>Number</td><td>Numeric</td><td>Y</td><td>Quantity of construction mentioned in the description</td></tr><tr><td>Length</td><td>Numeric</td><td>Y</td><td>Length of construction mentioned in the description</td></tr><tr><td>Width</td><td>Numeric</td><td>Y</td><td>Width of construction mentioned in the description</td></tr><tr><td>Depth/height</td><td>Numeric</td><td>Y</td><td>Depth of construction mentioned in the description</td></tr></tbody></table>

### **Acceptance Criteria**&#x20;

1. Create an M-Book when the contract is accepted with the start and end dates as per the contract
2. Measurements can be taken both on the web and mobile (Mobile First).
3. Measurement books initially will have line items from estimates with zero quantities. These will get filled as the project progresses and cannot go beyond what is estimated.&#x20;
4. Measurement Book readings can be sent for approval for any duration/marked period, from the last marked period.&#x20;
5. Once approved, that corresponding amount will be allowed for payment to the contractor.

## **MBook Track**

### **Need**

Tracking of MBook will be required to know the project progress and subsequently pay to contractor based on work done

### **User**

Mbook-Tracker

### **Details**

1. Mbook tracking can be done only against the line items that are captured in the estimate.&#x20;
   * This can be done at the estimate SOR line item level or sub line item level. &#x20;
2. At least one measurement needs to be filled in to submit an MBook for approval.
3. Each submission of the measurement book can use the same ID of the MBook with a running sequence number appended at the end.
4. To add another measurement reading for the same project, users can click on Actions > Add New Measurements, which opens another tab.
5. The overall measurements cannot exceed the estimated quantities.
6. A project can have any number of measurement entries.
7. M Book tracking can only be done until the last date of Mbook.&#x20;
8. Each mBook recording will have approval workflow.&#x20;
   * MBook is created by contractor/mbooktracker,
   * Checked by m-book checker,
   * Approved by m-book approver.
9. An Mbook should be able to tell using analysis of rates, how much labor, material and other heads as bifurcated in the estimate under SOR item detail 1.&#x20;
   * Upon each mBook entry creation a labour consumption log and material consumption log should also be generated as to how much material from the last entry till this entry is consumed.&#x20;
   * Only based on material consumed, the material supplier is eligible to get paid.

## **MBook Cancel**

### **Need**

Cancelling of Mbook is only possible with the cancellation of the contract &#x20;

### User

Contract\_Canceller

### **Details**

1. If a contract gets cancelled Mbook will also get cancel status.&#x20;
2. MBook reading entry if is in the approval workflow, will be moved to cancel status as well.&#x20;
3. Whatever approvals done so far on Mbook workflows are eligible for payments.&#x20;
   * Since we do automatic payments, a bill would have already been created for such mbook entries.

### Screens

<table><thead><tr><th width="243"></th><th></th></tr></thead><tbody><tr><td>Track Measurement </td><td><img src="../../.gitbook/assets/image (153).png" alt=""></td></tr><tr><td>Detailed measurement input screen</td><td><img src="../../.gitbook/assets/image (154).png" alt=""></td></tr><tr><td>Measurements successfullly submitted</td><td><img src="../../.gitbook/assets/image (157).png" alt=""></td></tr><tr><td>Measurement Inbox</td><td><img src="../../.gitbook/assets/image (159).png" alt=""></td></tr><tr><td>Measurement Book Search</td><td><img src="../../.gitbook/assets/image (160).png" alt=""></td></tr></tbody></table>
