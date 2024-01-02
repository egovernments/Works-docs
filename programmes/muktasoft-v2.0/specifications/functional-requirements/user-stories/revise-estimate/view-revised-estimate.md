# View Revised Estimate

## Details

1. The same search feature for original estimate is used to search and view the revised estimate too.
2. Revised estimate display the original and revised both the quantities as per the attributes given below.

<table data-header-hidden><thead><tr><th width="70"></th><th width="152"></th><th width="112"></th><th width="130"></th><th></th></tr></thead><tbody><tr><td>#</td><td><strong>Field Name</strong></td><td><strong>Data Type</strong></td><td><strong>Is Mandatory?</strong></td><td><strong>Description</strong></td></tr><tr><td>1</td><td>Estimate Type</td><td>Display</td><td>Yes</td><td>Estimate type, Revised.</td></tr><tr><td>2</td><td>Original Estimate Number</td><td>Hyperlink</td><td>Yes</td><td>The original estimate number as hyperlink on click open the estimate in view mode.</td></tr><tr><td>3</td><td>Project ID</td><td>Display</td><td>Yes</td><td>Project ID</td></tr><tr><td>4</td><td>Project Sanction Date</td><td>Display</td><td>Yes</td><td>Project sanction date</td></tr><tr><td>5</td><td>Project Name</td><td>Display</td><td>Yes</td><td>Project name</td></tr><tr><td>6</td><td>Project Description</td><td>Display</td><td>Yes</td><td>Project description</td></tr><tr><td></td><td><strong>SORs</strong></td><td></td><td></td><td></td></tr><tr><td>2</td><td>Code</td><td>Display</td><td>Yes</td><td>SOR code, unique identifier for each SOR.</td></tr><tr><td>3</td><td>SOR Description</td><td>Display</td><td>Yes</td><td>SOR description from the SOR master for the selected SOR.</td></tr><tr><td>3</td><td>Unit</td><td>Display</td><td>Yes</td><td>Unit of measurement</td></tr><tr><td>4</td><td>Rate</td><td>Display</td><td>Yes</td><td>The rate defined and effective currently.</td></tr><tr><td>5</td><td>Original Quantity</td><td>Display</td><td>Yes</td><td>The quantity available in original estimate.</td></tr><tr><td>6</td><td>Revised Quantity</td><td>Display</td><td>Yes</td><td>Calculated value out of measurements.</td></tr><tr><td>7</td><td>Revised Amount</td><td>Display</td><td>Yes</td><td>Calculated value and equal to Qty*Amount.</td></tr><tr><td></td><td><strong>Measurements</strong></td><td></td><td></td><td></td></tr><tr><td>1.1</td><td>Sr. No.</td><td>Display</td><td>Auto</td><td>Measurement serial number.</td></tr><tr><td>1.2</td><td>Type</td><td>Display</td><td>Yes</td><td>Plus/ Minus measurements.</td></tr><tr><td>1.3</td><td>Name</td><td>Display</td><td>Yes</td><td>The name of the measurement.</td></tr><tr><td>1.4</td><td>Number (Nos)</td><td><p>Numeric</p><p>(6,4)</p></td><td>Yes</td><td>No. of items.</td></tr><tr><td>1.5</td><td>Length (L)</td><td><p>Numeric</p><p>(6,4)</p></td><td>Yes</td><td>Length measured</td></tr><tr><td>1.6</td><td>Breadth (B)</td><td><p>Numeric</p><p>(6,4)</p></td><td>Yes</td><td>Width measured</td></tr><tr><td>1.7</td><td>Height/ Depth </td><td><p>Numeric</p><p>(6,4)</p></td><td>Yes</td><td>Depth measured</td></tr><tr><td>1.8</td><td>Quantity</td><td>Display</td><td>Yes</td><td>Qty =  N* L*B*D;</td></tr><tr><td>1.9</td><td>Total</td><td>Display</td><td>Yes</td><td>Grid total for the quantities of measurements</td></tr></tbody></table>

**Non SORs** - Non-SOR details

**Other Charges** - Same as view detailed estimate.

**View analysis statements** - To view the analysis statements.

**Timelines**- Workflow timelines.

## UI <a href="#ui" id="ui"></a>

<figure><img src="../../../../../../.gitbook/assets/View Revise Estimate.png" alt=""><figcaption></figcaption></figure>

## Acceptance Criteria <a href="#acceptancecriteria" id="acceptancecriteria"></a>

1. Revised quantity and amount is displayed along with original quantity.
