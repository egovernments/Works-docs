# Estimates

## Overview

Estimates are created for each project/sub-project entity.

**Need and Background:**

1. An estimate is prepared for each Works project so as to get technically sanctioned and proceed with tendering/contract.
2. Estimates are created for each project/sub-project entity.
3. There are multiple estimate types for each project prepared with different levels of abstraction.

<table><thead><tr><th width="174">Estimate Type</th><th>Definition</th></tr></thead><tbody><tr><td>Proposal</td><td>A single line item has the overall project cost against the project title. This requires in-principal Admin sanction. Once approved detailed estimate for the same is created.</td></tr><tr><td>Detailed</td><td>A detailed estimate contains engineering drawings done on AutoCAD &#x26; other drawing tools. Modern tools also abstract out many measurements and materials from drawings created by these tools.</td></tr><tr><td>Abstract</td><td>An abstract estimate is prepared using standard SOR &#x26; Non-SOR Items defined by PWD (mostly ULBs customise SOR and have their own copies). SOR items are created internally using item rates.</td></tr><tr><td>Revised</td><td>When a project's finances are increasing then to what is initially estimated, revision estimates are created and approved. revision estimates may or may not have the same SORs as initial estimates. Revised estimate line items added to initial line items will give overall project cost</td></tr><tr><td>Deviation</td><td>A deviation statement is a type of estimation when the scope of the project changes but the project cost is meant to remain the same. The deviation statement and revised estimate are the same as far as the estimation process is concerned. The approving authority changes only.</td></tr><tr><td>Spill Over</td><td>For a multi-year project, an estimate is financially broken down into pieces and budget allocation is done for each year instead of allocating the entire budget in the first year.</td></tr></tbody></table>

## Functional Requirements

1. After creating the project (and getting approved if there is a workflow) JE will start estimating the project.&#x20;
2. To create an estimate following details are required.
   * Line Items from SOR
   * Non-SOR line items
   * Overheads
3. There are 3 ways how estimates can be added.
   * Manually adding from SOR Master List
   * Using Estimate Template
   * Copying the format of existing similar projects and changing the values
4. To select line items for SOR, select the SOR category, search for the SOR line item by SOR code or SOR description and select the SOR.&#x20;
   * To the SOR line item, add the quantity that is required for this project.&#x20;
   * SOR standard amount multiplied by this quantity gives the line item-wise cost.&#x20;
5. Measurements can be captured at the SOR line item level directly by the specified UOM or length, breadth, height, quantity can be captured and stored in an empty measurement book so as to utilise it later for m book recordings.&#x20;
   * Multiplication of L,B,H,Q will give the required quantity of the line item for the estimate.&#x20;
6. A non-SOR line item will not be defined in MDMS and hence will not be searchable using the SOR category or Code.&#x20;
   * Rate, Quantity and Description have to be entered manually.&#x20;
   * Just like SOR, instead of quantity directly, L,B,H,Q can also be captured.&#x20;
7. All SOR and Non-SOR items in the way captured in the estimates will be created as empty records in the Measurement Book to capture readings later.&#x20;
8. Overheads are predefined masters.&#x20;
   * The cost of the project becomes the cost of SOR and Non-SOR items plus overheads.
   * Overheads are either added on top of SOR and Non-SoR separately or can be derived from SOR Sub Line items.
   * Overheads amount will not be going to the contractor but will be going to specific heads defined in the Master for respective overheads. (GST 12% to GST department, Cess 1% to labour dept etc). This means Contracts will selectively capture only a few overheads for contractors.
9. Each estimate will have a unique ID that is generated
   * ID: EST/\<ULB/Department Code>/\<Year>/\<month>/\<Date>/\<running sequence number>
10. Status of an estimate
    * Created
    * In progress
    * Approved
    * Rejected
    * Cancelled

## Masters

**Schedule of Rates (SOR)**

1. SOR is a line item that represents the rate for a single unit of work. SOR is defined by the Central PWD or state PWD and is revised based on the market needs from time to time. In general, there are about 3000+ SOR line items
2. Each executing authority ULB/Department may modify the rates of these SORs by applying lead charges.
   * Lead Masters will be varying for each project as the project site will be different for each.
   * For simplicity, SORs are usually kept constant under a ULB.
3. Each SOR Item may have multiple variants with slight changes in description and amounts.
   * Ex. Estimate of tiling for the ground floor and estimate of tiling for the first floor will change by 15 Rs to capture the carriage charges. These should be captured with .serial\_number. (Parent.Child)

<table><thead><tr><th width="154">Field</th><th width="143">Data Type</th><th width="97">Required (Y/N)</th><th>Comments</th></tr></thead><tbody><tr><td>SOR Category ID</td><td>Drop down</td><td>Y</td><td><p>Options will be the list of Category Code from the SOR category type master</p><p>The combination of category Code and Item code is unique</p></td></tr><tr><td>Item ID</td><td>Alphanumeric</td><td>Y</td><td>System generated</td></tr><tr><td>Item Description</td><td></td><td>Y</td><td>Item description of the selected Item</td></tr><tr><td>Unit of Measurement</td><td></td><td>Y</td><td>Options will be the list from Unit of measurement master</td></tr><tr><td><em>[Array] for specific date ranges</em></td><td></td><td></td><td></td></tr><tr><td>Item Rate</td><td>Numeric</td><td>Y</td><td>Multiple entries can be specified for each Item, but there cannot be an overlap in the rates for a range of dates</td></tr><tr><td>Item rate Applicable From</td><td>Date</td><td>Y</td><td>To be entered in the format dd/mm/yyyy</td></tr><tr><td>Item rate Applicable To</td><td>Date</td><td>N</td><td>To be entered in the format dd/mm/yyyy</td></tr></tbody></table>

**Analysis of Rates**

1. Each line item of a SOR master/SOR variant will further be divided into Sub line items that come from a set of category Masters like Labour Master, Material Master, Royalty Master, Carriage Master etc.
   * A group of Sub line items together will form an estimate line item.
   * Each sub-line item will have Item detail 1, item detail 2, quantity, UOM, rate, estimated amount.
   * The sum of all sub-line items will become the total of the SOR line item
   * Item detail 1 will capture whether it is material/labour/carriage/overhead/royalty etc
   * Item detail 2 will capture the exact details of the item from the respective item master. rates need to be auto-populated.
2. With this when extracted, we should be able to produce labour analysis, material analysis and other standard reports, coming from the estimates.

**Basic Rates of Materials Master**

<table data-header-hidden><thead><tr><th width="160"></th><th width="138"></th><th width="109"></th><th></th></tr></thead><tbody><tr><td><strong>Field</strong></td><td><strong>Data Type</strong></td><td><strong>Required (Y/N)</strong></td><td><strong>Comments</strong></td></tr><tr><td>ID</td><td>NA</td><td>Na</td><td>System generated ID</td></tr><tr><td>Department</td><td>Dropdown</td><td>Y</td><td>Labour rates may vary by each department</td></tr><tr><td>Material Category</td><td>Dropdown</td><td>Y</td><td>brick and tile, stone and road, metal and iron etc</td></tr><tr><td>Description of Material</td><td>Alphanumeric</td><td>Y</td><td>Second Class Table Moulded Chamber Burnt Bricks 9" x 41<br>/2" x 3"</td></tr><tr><td>Quantity</td><td>Numeric</td><td>Y</td><td>Quantity for which base rate is defined. Default to 1</td></tr><tr><td>Unit</td><td>Dropdown</td><td>Y</td><td>Nos, Ton, etc</td></tr><tr><td><em>[Array] for specific date ranges</em></td><td></td><td></td><td></td></tr><tr><td>Item Rate</td><td>Numeric</td><td>Y</td><td>Multiple entries can be specified for each Item, but there cannot be an overlap in the rates for a range of dates</td></tr><tr><td>Item rate Applicable From</td><td>Date</td><td>Y</td><td>To be entered in the format dd/mm/yyyy</td></tr><tr><td>Item rate Applicable To</td><td>Date</td><td>N</td><td>To be entered in the format dd/mm/yyyy</td></tr></tbody></table>

**Note**: There are roughly about 200 materials and some of whose rates change quarterly.

**Labour Rate Master**

<table data-header-hidden><thead><tr><th width="142"></th><th width="138"></th><th width="147"></th><th></th></tr></thead><tbody><tr><td><strong>Field</strong></td><td><strong>Data Type</strong></td><td><strong>Required (Y/N)</strong></td><td><strong>Comments</strong></td></tr><tr><td>ID</td><td>NA</td><td>Na</td><td>System generated ID</td></tr><tr><td>Department</td><td>Dropdown</td><td>Y</td><td>Labour rates may vary by each department</td></tr><tr><td>Skill Category</td><td>Dropdown</td><td>Y</td><td>Highly Skilled, Semi Skilled Unskilled etc</td></tr><tr><td>Description of Labour</td><td>Alphanumeric</td><td>Y</td><td>Technical Assistant, Stone Polisher, Smith etc</td></tr><tr><td>Quantity</td><td>Numeric</td><td>Y</td><td>Quantity for which base rate is defined. Default to 1</td></tr><tr><td>Unit</td><td>Dropdown</td><td>Y</td><td>Day/Week/Month</td></tr><tr><td><em>[Array] for specific date ranges</em></td><td></td><td></td><td></td></tr><tr><td>Rate</td><td>Numeric</td><td>Y</td><td>Rate of Labour for specified (Quantity' units)</td></tr><tr><td>From Date</td><td>Date</td><td>Y</td><td>Date from which these rates are applicable</td></tr><tr><td>To Date</td><td>Date</td><td>Y</td><td>Date to which these rates are applicable</td></tr></tbody></table>

There are about 80 types of labour.

**Lead Master**

Lead Master will have the carriage and royalty details of each item that goes into the individual SOR items.

<table data-header-hidden><thead><tr><th width="136"></th><th width="171"></th><th width="120"></th><th></th></tr></thead><tbody><tr><td>Field</td><td>Data Type</td><td>Required (Y/N)</td><td>Comments</td></tr><tr><td>ID</td><td>NA</td><td>NA</td><td>System Generated</td></tr><tr><td>Item ID</td><td>Dropdown</td><td></td><td>Item for which Lead SOR is present</td></tr><tr><td>Item Name</td><td>Autofill/Dropdown</td><td>Y</td><td>Item for which Lead SOR is present</td></tr><tr><td>Name of Quarry</td><td>Dropdown</td><td>N</td><td>For Materials. Doesnt appy for labour</td></tr><tr><td>Unit</td><td>Dropdown</td><td>Y</td><td>Unit of Measurement</td></tr><tr><td>Lead (Km.)</td><td>Numeric</td><td>N</td><td>Distance from quarry</td></tr><tr><td>Basic Cost</td><td>Autofill</td><td>Y</td><td>Basic cost pulled from material rate master or labour rate master</td></tr><tr><td>Conveyance Cost</td><td>Numeric</td><td>N</td><td></td></tr><tr><td>Royalty</td><td>Numeric</td><td>N</td><td>Royalty on applicable material, abstracted, will go into specific head defined during estimation</td></tr><tr><td>Total</td><td>Calculation</td><td>Y</td><td>Total new cost of line item</td></tr></tbody></table>

When a lead master is set on a particular material in a particular ULB, all SOR line items that contain this item will take the amount from the lead master and not from the basic rate master

**Non Schedule of Rates (SOR)**

1. Non-SOR items are not defined by CPWD and based on project requirements will get added to the estimate.&#x20;
2. They will have the same attributes as the SOR item, but will not have a defined SOR ID or SOR category.

Ex. Purchasing Fancy benches & themed dustbins at Park. The rate, in this case, is fixed by JE upon discussing with potential vendors

**Overheads**

Overheads can be of two types.

1. In-Line Overheads - Defined within the SOR line items
2. Estimate Level Overheads -
   * These are defined on top of estimates. Each overhead will be defined within a time range with either percentage or lump sum value of the entire estimated cost

We should be able to abstract out similar overheads from multiple SOR line items and groups to form a single overall overhead for the estimate.

<table data-header-hidden><thead><tr><th width="138"></th><th width="142"></th><th width="120"></th><th></th></tr></thead><tbody><tr><td><strong>Field</strong></td><td><strong>Data Type</strong></td><td><strong>Required (Y/N)</strong></td><td><strong>Comments</strong></td></tr><tr><td>ID</td><td>NA</td><td>NA</td><td>ID generated for each overhead type</td></tr><tr><td>Name</td><td>Alphanumeric</td><td>Y</td><td><p>Name of the overhead</p><p>Ex. Labour Cess, GST, Royalty etc</p></td></tr><tr><td>Description</td><td>Alphanumeric</td><td>N</td><td>Description</td></tr><tr><td>Account head</td><td>Dropdown</td><td>Y</td><td>Account head to which overheads should be credited</td></tr><tr><td><em>[Array] for specific date ranges</em></td><td></td><td></td><td></td></tr><tr><td>From Date</td><td>Date</td><td>Y</td><td>Date from which these rates are applicable</td></tr><tr><td>To Date</td><td>Date</td><td>Y</td><td></td></tr><tr><td>Percentage/ Lumpsum</td><td>Numeric</td><td>Y</td><td>Percentage or Lumpsum amount of estimate including value</td></tr></tbody></table>

**Revised Estimates**

1. Estimate revision can happen before the final bill is submitted and the project is closed. For a revised estimate, the user can come onto the existing estimate and click actions → Revise estimate. This goes for a similar approval cycle as the main estimate.
2. For a revised estimate -
   * New line items can be added.
   * Existing line items can be removed
   * Quantities in existing estimates can be modified.
3. A contract that is created from this estimate also needs to be revised and sent to the contractor for approval.
4. Measurement books accordingly will get changed as per the new estimate.
5. If some part of the estimate is already measured and the bill has been created/approved, a revised estimate for that line item cannot go under that approved bill quantity for that line item.

**Schedule Category**

A schedule category is a grouping of SORs for easy identification and filtering. There are a total of about 3000 SOR items divided into 15-20 SOR groups

Examples - Earth Work, Masonry, Brick Work, Painting, etc

<table data-header-hidden><thead><tr><th width="158"></th><th width="145"></th><th width="133"></th><th></th></tr></thead><tbody><tr><td>Field</td><td>Data Type</td><td>Required (Y/N)</td><td>Comments</td></tr><tr><td>Category Code</td><td>Alphanumeric</td><td>Y</td><td>Unique Code Assigned to the Schedule Category</td></tr><tr><td>Category Name</td><td>Alphanumeric</td><td>Y</td><td>Name Assigned to the Schedule Category</td></tr></tbody></table>

**Estimate Template**

1. Templates are created for specific types and sub-types of work so they can be reused for future use.
2. Templates are groupings of SOR items that combine to complete a similar kind of work.
3. On the UI, the Estimates inbox will have an Estimate Template section and users can see a list of templates and create a new template from there, and modify the existing template.

Ex. Template to build 100 mt of 20 ft road, Template to build 8\*10 sq ft standard room. &#x20;

<table data-header-hidden><thead><tr><th width="148"></th><th width="150"></th><th width="114"></th><th></th></tr></thead><tbody><tr><td>Field</td><td>Data Type</td><td>Required (Y/N)</td><td>Comments</td></tr><tr><td>Template Code</td><td>Alphanumeric</td><td>Y</td><td>Define the template code</td></tr><tr><td>Name</td><td>Alphanumeric</td><td>Y</td><td>Name for template</td></tr><tr><td>Description</td><td>Alphanumeric</td><td>Y</td><td>Description of the template</td></tr><tr><td>Status</td><td>Dropdown</td><td>Y</td><td><p>Status of the template</p><ul><li>Active</li><li>Inactive</li></ul></td></tr><tr><td>Work Type</td><td>Dropdown</td><td>Y</td><td>Select the Type of work. All the work types defined in the system should be shown</td></tr><tr><td>Work Sub Type</td><td>Dropdown</td><td>Y</td><td>Select the Sub type of work. All the work sub types defined in the system should be shown here</td></tr><tr><td><em>[Array] for each line item</em></td><td></td><td></td><td></td></tr><tr><td>Schedule Category</td><td>Dropdown</td><td>Y</td><td>Options are the list of SOR categories from the SOR category master.</td></tr><tr><td>SOR</td><td>Alphanumeric</td><td>Y</td><td>Enter the template code and search for it</td></tr><tr><td>Non_SOR Code</td><td>Alphanumeric</td><td>N</td><td></td></tr><tr><td>Non_SOR Description</td><td>Alphanumeric</td><td>N</td><td></td></tr><tr><td>Non_SOR UOM</td><td>Dropdown</td><td>N</td><td>lenght--KM; Area--SQM</td></tr><tr><td>Non_SOR Unit Rate</td><td>Numeric</td><td>N</td><td></td></tr></tbody></table>

## **Mockups**

<table data-header-hidden><thead><tr><th width="280">Description</th><th>Mockups</th></tr></thead><tbody><tr><td>Create Estimate</td><td><img src="../../../.gitbook/assets/image (19).png" alt=""></td></tr><tr><td>Estimate Successfully Created</td><td><img src="../../../.gitbook/assets/image (42).png" alt=""></td></tr><tr><td>Estimates Inbox</td><td><img src="../../../.gitbook/assets/image (14).png" alt=""></td></tr><tr><td>Inbox Table</td><td><img src="../../../.gitbook/assets/image (29).png" alt=""></td></tr><tr><td>SOR Data entry screen</td><td><img src="../../../.gitbook/assets/image (39).png" alt=""></td></tr></tbody></table>

## **User Acceptance Criteria**

A user should be able to

1. Create an estimate using templates
2. Add SOR items from SOR Master
3. Change values as required for current work
4. Add/auto-populate overheads
5. Able to generate Material Analysis and Labour Analysis
6. Download PDFs of Labour analysis, material analysis, and Overall Estimate
