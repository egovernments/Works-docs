# Create Revised Estimate

## Scope

Create Revised Estimate

Home > Estimates > Search Estimate> Revise Estimate

## Actors <a href="#actors" id="actors"></a>

ULB: Estimate Creator

## Details <a href="#details" id="details"></a>

1. Option to revise estimate to be provided.
2. The same estimate inbox is used to process revised WO.
3. A original estimate is revised on less or excess deviation and it can be revised only once.
4. The attributes defining revised estimate are as given below.

<table data-header-hidden><thead><tr><th width="79"></th><th></th><th width="101"></th><th width="129"></th><th></th></tr></thead><tbody><tr><td>#</td><td><strong>Field Name</strong></td><td><strong>Data Type</strong></td><td><strong>Is Mandatory?</strong></td><td><strong>Description</strong></td></tr><tr><td>1</td><td>Estimate Type</td><td>Display</td><td>Yes</td><td>Estimate type, Revised.</td></tr><tr><td>2</td><td>Project ID</td><td>Display</td><td>Yes</td><td>Project ID</td></tr><tr><td>3</td><td>Project Sanction Date</td><td>Display</td><td>Yes</td><td>Project sanction date</td></tr><tr><td>4</td><td>Project Name</td><td>Display</td><td>Yes</td><td>Project name</td></tr><tr><td>5</td><td>Project Description</td><td>Display</td><td>Yes</td><td>Project description</td></tr><tr><td></td><td><strong>Search SOR</strong> - It provides the option to search a SOR and add to estimate.</td><td></td><td></td><td></td></tr><tr><td></td><td><strong>SORs</strong></td><td></td><td></td><td></td></tr><tr><td>1</td><td>Code</td><td>Display</td><td>Yes</td><td>SOR code, unique identifier for each SOR.</td></tr><tr><td>2</td><td>SOR Description</td><td>Display</td><td>Yes</td><td>SOR description from the SOR master for the selected SOR.</td></tr><tr><td>3</td><td>Unit</td><td>Display</td><td>Yes</td><td>Unit of measurement</td></tr><tr><td>4</td><td>Rate</td><td>Display</td><td>Yes</td><td>The rate defined and effective currently.</td></tr><tr><td>5</td><td>Original Quantity</td><td>Display</td><td>Yes</td><td>Originally estimated quantity.</td></tr><tr><td>6</td><td>Original Amount</td><td>Display</td><td>Yes</td><td>Originally estimated amount.</td></tr><tr><td>7</td><td>Revised Quantity</td><td>Display</td><td>Yes</td><td>Calculated value out of measurements.</td></tr><tr><td>8</td><td>Revised Amount</td><td>Display</td><td>Yes</td><td>Calculated value and equal to Qty*Amount.</td></tr><tr><td></td><td><strong>Measurements</strong> - A able to capture the measurement details and calculate the quantity using it.</td><td></td><td></td><td></td></tr><tr><td>1.1</td><td>Sr. No.</td><td>Display</td><td>Auto</td><td>Measurement serial number.</td></tr><tr><td>1.2</td><td>Type</td><td>Drop-down</td><td>Yes</td><td>Plus/ Minus measurements.</td></tr><tr><td>1.3</td><td>Name</td><td><p>Alphanumeric</p><p>(32 Chars)</p></td><td>Yes</td><td>The name of the measurement.</td></tr><tr><td>1.4</td><td>Number (Nos)</td><td><p>Numeric</p><p>(6,4)</p></td><td>Yes</td><td>No. of items.</td></tr><tr><td>1.5</td><td>Length (L)</td><td><p>Numeric</p><p>(6,4)</p></td><td>Yes</td><td>Length measured. Allowed up-to 4 places of decimal.</td></tr><tr><td>1.6</td><td>Breadth (B)</td><td><p>Numeric</p><p>(6,4)</p></td><td>Yes</td><td>Width measured. Allowed up-to 4 places of decimal.</td></tr><tr><td>1.7</td><td>Height/ Depth </td><td><p>Numeric</p><p>(6,4)</p></td><td>Yes</td><td>Depth measured. Allowed up-to 4 places of decimal.</td></tr><tr><td>1.8</td><td>Quantity</td><td>Display</td><td>Yes</td><td>Qty = N* L*B*D; rounded up-to 4 places of decimal.</td></tr><tr><td>1.9</td><td>Total</td><td>Display</td><td>Yes</td><td>Grid total for the quantities of measurements. rounded up-to 4 places of decimal.</td></tr><tr><td></td><td><strong>Non SORs</strong></td><td></td><td></td><td></td></tr><tr><td>1</td><td>SOR Description</td><td><p>Alphanumeric</p><p>(2048 Chars)</p></td><td>Yes</td><td>SOR description from the SOR master for the selected SOR.</td></tr><tr><td>2</td><td>Unit</td><td>Drop-down</td><td>Yes</td><td>Unit of measurement</td></tr><tr><td>3</td><td>Rate</td><td><p>Numeric</p><p>(6,2)</p></td><td>Yes</td><td>The rate defined and effective currently.</td></tr><tr><td>4</td><td>Original Quantity</td><td>Display</td><td>Yes</td><td>Originally estimated quantity.</td></tr><tr><td>5</td><td>Original Amount</td><td>Display</td><td>Yes</td><td>Originally estimated amount</td></tr><tr><td>6</td><td>Revised Quantity</td><td>Display</td><td>Yes</td><td>Calculated value out of measurements.</td></tr><tr><td>7</td><td>Revised Amount</td><td>Display</td><td>Yes</td><td>Calculated value and equal to Qty*Amount.</td></tr><tr><td></td><td><strong>Measurements</strong> - The table is same as described under SOR.</td><td></td><td></td><td></td></tr><tr><td></td><td><strong>Other Charges</strong> - It is going to be same as provided in the existing estimate screen as overhead.</td><td></td><td></td><td></td></tr><tr><td>7</td><td>View Analysis Statements</td><td>Link</td><td>Yes</td><td>It will take the user to analysis page. It gets enabled once the analysis is generated.</td></tr><tr><td></td><td><strong>Actions</strong></td><td></td><td></td><td></td></tr><tr><td>1</td><td>Save as Draft</td><td>Button</td><td>Yes</td><td>Save the estimate as a draft.</td></tr><tr><td>2</td><td>Generate Analysis</td><td>Button</td><td>Yes</td><td>Generates the analysis and populates the figures.</td></tr><tr><td>3</td><td>Submit</td><td>Button</td><td>Yes</td><td>Submit the estimate for verification.</td></tr></tbody></table>

### Actions <a href="#actions" id="actions"></a>

1. Save as Draft - It is to save the details captured for detailed estimate and keeping it with creator.
2. Generate Analysis - Generate the analysis statement out of saved detailed estimate details.
3. Submit - It is the same as per existing estimate, allow the user to forward the estimate for verification.
4. View Analysis Statements - It will take the user to view analysis statement HTML page.

#### On Save as Draft

1. Estimate is created with the details provided.
2. If it is first time, estimate no. is generated as per the format provided. \[RE/2022-23/000031]
3. Success toast message is displayed and page is loaded again in editable mode with the details saved.
4. Estimate gets assigned to the creator and made available in his/her inbox with the WF state Drafted.
5. On open from inbox, its get opened in editable mode same as edit estimate.

`Estimate details are saved.`

#### On Submit

1. This action is enabled for saved estimate only.
2. The estimate details are saved.
3. Analysis statements are revised.
4. Estimate is forwarded to verifier.
5. Success page is displayed with success message.

#### On Generate Analysis

1. First time, this action is enabled for saved estimate only.
2. The analysis is generated and Success toast message is displayed.
3. View Analysis Statements link is enabled.

`Analysis statements are generated successfully.`

`Analysis statements generation failed.`

### Validations <a href="#validations" id="validations"></a>

1. Field level validation as provided in the table above.
2. The revised quantity to be validated against the total consumed quantity at each and every workflow state. Means while the revise estimate is saved, submitted, verified, and approved.

`The revised quantity can not be less than the consumed quantity.`

### Configuration <a href="#configuration" id="configuration"></a>

Not applicable.

### Notifications <a href="#notifications" id="notifications"></a>

Not applicable

### User Interface <a href="#userinterface" id="userinterface"></a>

<figure><img src="../../../../../../.gitbook/assets/Create Revise Estimate (1).png" alt=""><figcaption></figcaption></figure>

## Acceptance Criteria <a href="#acceptancecriteria" id="acceptancecriteria"></a>

1. The estimate inbox is used to process revised estimate.
2. The workflow is going to be same as original estimate.
3. The drafted estimate is assigned to the creator of estimate and can be searched using search estimate.
4. Estimate is made available to the inbox of estimate creator as well.
5. Validation against the consumed quantity from MB.
