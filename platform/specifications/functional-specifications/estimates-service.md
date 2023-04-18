# Estimates Service

## Overview

Estimates are created for each project/sub-project entity.

**Need and Background:**

1. An estimate is prepared for each Works project so to get technically sanctioned and proceed with tendering/contract.
2. Estimates are created for each project/sub-project entity.
3. There are multiple estimate types for each project prepared with different levels of abstraction.

| **Estimate Type** | **Definition**                                                                                                                                                                                                                                                                        |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Proposal          | A single line item having the overall project cost against the project title. This will go for in-principal Admin sanction. Once Approved Detailed Estimate for the same will be created                                                                                              |
| Detailed          | A Detailed Estimate contains of engineering drawings done on AutoCAD & other drwawing tools. Modern tools also abstract out many measurements and materials from drawings created in these tools.                                                                                     |
| Abstract          | Abstract Estimate is prepared using standard SOR & Non SOR Items defined by PWD (manytimes ULBs customise SOR and have their own copies). SOR items is created internally using Item rates                                                                                            |
| Revised           | When a project finances is increasing than to what is initially estimated, revision estimates are created and approved. revision estimates may or may not have same SORs as initial estimates. Revised estimate line items added to initial line items will give overall project cost |
| Deviation         | Deviation statement is a type of estimation when scope of the project changes but project cost is meant to remain same. Deviation statement and revised estimate are same as far as estimation process is concered. Only approving authority will change                              |
| Spill Over        | For a Multi year project, an estimate is financially broken down into pieces and budget allocation is done for each year instead of allocating entire budget in first year.                                                                                                           |

#### Functional Requirements

1. After creating the project (and getting approved if there is a workflow) JE will start estimating the project.&#x20;
2. To create an estimate following details are required.
   1. Line Items from SOR
   2. Non SOR Line items
   3. Overheads
3. There are 3 ways how estimates can be added.
   1. Manually adding from SOR Master List
   2. Using Estimate Template
   3. Copying the format of existing similar project and changing the values
4. **Type1:** To select line items for SOR, select the SOR category, search for the SOR line item by SOR code or SOR description and select the SOR.&#x20;
   1. To the SOR line item, add the quantity that is required for this project.&#x20;
   2. SOR standard amount multiplied with this quantity gives the line item wise cost.&#x20;
5. Measurements can be captured at SOR line item level directly by the specified UOM or  length, breadth, height, quantity can be captured and stored in empty measurement book so as to utilise it later for m book recordings.&#x20;
   1. Multiplication of L,B,H,Q will give the required quantity of the line item for the estimate.&#x20;
6. A non SOR line item will not be defined in MDMS and hence will not be searchable using SOR category or Code.&#x20;
   1. Rate, Quantity, Description has to be entered manually.&#x20;
   2. Just like SOR, instead of quantity directly, L,B,H,Q can also be captured.&#x20;
7. All SOR and Non SOR items in the way captured in the estimates will be created as empty records in the Measurement Book to capture readings later.&#x20;
8. Overheads are predefined masters.&#x20;
   1. The cost of the project becomes the cost of SOR, Non SOR items plus overheads.
   2. Overheads are either added on top of SOR and Non SoR separately or can be derived from SOR Sub Line items.
   3. Overheads amount will not be going to contractor but will be going to specific heads defined in the Master for respective overheads. (GST 12% to GST department, Cess 1% to labour dept etc). Which means Contracts will selectively capture only few overheads for contractors.
9. Each estimate will have a unique ID that is generated
   1. ID: EST/\<ULB/Department Code>/\<Year>/\<month>/\<Date>/\<running sequence number>
10. Status of an estimate
    1. Created
    2. In progress
    3. Approved
    4. Rejected
    5. Cancelled

#### Masters

**Schedule of Rates (SOR)**

1. SOR is a line item that represents the rate for a single unit of work. SOR is defined by the Central PWD or state PWD and is revised based on the market needs from time to time. In general there are about 3000+ SOR line items
2. Each executing authority ULB/Department may modify rates of these SORs by applying lead charges.
   1. Lead Masters will be varying for each project as the project site will be different for each.
   2. For simplicity SORs are usually kept constant under a ULB.
3. Each SOR Item may have multiple variants with slight change in description and amounts.
   1. Ex. Estimate of tiling for ground floor and estimate of tiling for first floor will change by 15 Rs to capture the carriage charges. These should be captured with .serial\_number. (Parent.Child)

| **Field**                           | **Data Type** | **Required (Y/N)** | **Comments**                                                                                                                                      |
| ----------------------------------- | ------------- | ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| SOR Category ID                     | Drop down     | Y                  | <p>Options will be the list of Category Code from the SOR category type master</p><p>The combination of category Code and Item code is unique</p> |
| Item ID                             | Alphanumeric  | Y                  | System generated                                                                                                                                  |
| Item Description                    |               | Y                  | Item description of the selected Item                                                                                                             |
| Unit of Measurement                 |               | Y                  | Options will be the list from Unit of measurement master                                                                                          |
| _\[Array] for specific date ranges_ |               |                    |                                                                                                                                                   |
| Item Rate                           | Numeric       | Y                  | Multiple entries can be specified for each Item, but there cannot be an overlap in the rates for a range of dates                                 |
| Item rate Applicable From           | Date          | Y                  | To be entered in the format dd/mm/yyyy                                                                                                            |
| Item rate Applicable To             | Date          | N                  | To be entered in the format dd/mm/yyyy                                                                                                            |

**Analysis of Rates**

1. Each line item of an SOR master/SOr Variant will further be divided into Sub line items that come from a set of category Masters like Labour Master, Material master, Royalty Master, Carriage master etc.
   1. A group of Sub line items together will form an esitmate line item.
   2. Each sub line item will have Item detail1, item detail 2, quantity, uom, rate, estimated amount.
   3. Sum of all sub line items will become total of the SOR line item
   4. Item detail 1 will capture whether it is material/labour/carriage/overhead/royalty etc
   5. Item detail 2 will capture exact details of the item from the respective item master. rates need to be auto populated.
2. With this when extracted out, we should be able to produce labour analysis, material analysis and other standard reports, coming from the estimates.

**Basic Rates of Materials Master**

| **Field**                           | **Data Type** | **Required (Y/N)** | **Comments**                                                                                                      |
| ----------------------------------- | ------------- | ------------------ | ----------------------------------------------------------------------------------------------------------------- |
| ID                                  | NA            | Na                 | System generated ID                                                                                               |
| Department                          | Dropdown      | Y                  | Labour rates may vary by each department                                                                          |
| Material Category                   | Dropdown      | Y                  | brick and tile, stone and road, metal and iron etc                                                                |
| Description of Material             | Alphanumeric  | Y                  | <p>Second Class Table Moulded Chamber Burnt Bricks 9" x 41<br>/2" x 3"</p>                                        |
| Quantity                            | Numeric       | Y                  | Quantity for which base rate is defined. Default to 1                                                             |
| Unit                                | Dropdown      | Y                  | Nos, Ton, etc                                                                                                     |
| _\[Array] for specific date ranges_ |               |                    |                                                                                                                   |
| Item Rate                           | Numeric       | Y                  | Multiple entries can be specified for each Item, but there cannot be an overlap in the rates for a range of dates |
| Item rate Applicable From           | Date          | Y                  | To be entered in the format dd/mm/yyyy                                                                            |
| Item rate Applicable To             | Date          | N                  | To be entered in the format dd/mm/yyyy                                                                            |

**Note**: There are roughly about 200 materials and some of whose rates change quarterly.

**Labour Rate Master**

| **Field**                           | **Data Type** | **Required (Y/N)** | **Comments**                                          |
| ----------------------------------- | ------------- | ------------------ | ----------------------------------------------------- |
| ID                                  | NA            | Na                 | System generated ID                                   |
| Department                          | Dropdown      | Y                  | Labour rates may vary by each department              |
| Skill Category                      | Dropdown      | Y                  | Highly Skilled, Semi Skilled Unskilled etc            |
| Description of Labour               | Alphanumeric  | Y                  | Technical Assistant, Stone Polisher, Smith etc        |
| Quantity                            | Numeric       | Y                  | Quantity for which base rate is defined. Default to 1 |
| Unit                                | Dropdown      | Y                  | Day/Week/Month                                        |
| _\[Array] for specific date ranges_ |               |                    |                                                       |
| Rate                                | Numeric       | Y                  | Rate of Labour for specified (Quantity' units)        |
| From Date                           | Date          | Y                  | Date from which these rates are applicable            |
| To Date                             | Date          | Y                  | Date to which these rates are applicable              |

There are about 80 types of labour

**Lead Master**

1. Lead Master will have the carriage and royalty details of each item that goes into the individual SOR items.

| Field           | Data Type         | Required (Y/N) | Comments                                                                                         |
| --------------- | ----------------- | -------------- | ------------------------------------------------------------------------------------------------ |
| ID              | NA                | NA             | System Generated                                                                                 |
| Item ID         | Dropdown          |                | Item for which Lead SOR is present                                                               |
| Item Name       | Autofill/Dropdown | Y              | Item for which Lead SOR is present                                                               |
| Name of Quarry  | Dropdown          | N              | For Materials. Doesnt appy for labour                                                            |
| Unit            | Dropdown          | Y              | Unit of Measurement                                                                              |
| Lead (Km.)      | Numeric           | N              | Distance from quarry                                                                             |
| Basic Cost      | Autofill          | Y              | Basic cost pulled from material rate master or labour rate master                                |
| Conveyance Cost | Numeric           | N              |                                                                                                  |
| Royalty         | Numeric           | N              | Royalty on applicable material, abstracted, will go into specific head defined during estimation |
| Total           | Calculation       | Y              | Total new cost of line item                                                                      |

When a lead master is set on a particlar material in a particylar ULB, all SOR line items that contain this item will take amount from lead master and not from basic rate master

**Non Schedule of Rates (SOR)**

1. Non SOR items are not defined by CPWD and based on projects requirements will get added to estimate.&#x20;
2. They will have same attributes as of SOR item, but will not have defined SOR ID or SOR category.

Ex. Purchasing Fancy benches & themed dustbins at Park. rate in this case if fixed by JE upon discussing with potential vendors

**Overheads**

1. Overheads can be of two types.
   1. In Line Overheads - Defined within the SOR line items
   2. Estimate Level Overheads -
      1. These are defined on top of estimates. Each overhead will be defined within a time range with either percentage or lumpsum value of the entire estimate cost
   3. we should be able to abstract out similar overheads from multiple SOR line items and group to form a single overall overhead for the estimate.

| **Field**                           | **Data Type** | **Required (Y/N)** | **Comments**                                                        |
| ----------------------------------- | ------------- | ------------------ | ------------------------------------------------------------------- |
| ID                                  | NA            | NA                 | ID generated for each overhead type                                 |
| Name                                | Alphanumeric  | Y                  | <p>Name of the overhead</p><p>Ex. Labour Cess, GST, Royalty etc</p> |
| Description                         | Alphanumeric  | N                  | Description                                                         |
| Account head                        | Dropdown      | Y                  | Account head to which overheads should be credited                  |
| _\[Array] for specific date ranges_ |               |                    |                                                                     |
| From Date                           | Date          | Y                  | Date from which these rates are applicable                          |
| To Date                             | Date          | Y                  |                                                                     |
| Percentage/ Lumpsum                 | Numeric       | Y                  | Percentage or Lumpsum amount of estimate including value            |

**Revised Estimates**

1. Estimate revision can happen until before final bill is submitted and project is closed. For a revised estimate, user can come onto the existing estimate, click actions → Revise estimate. This goes for a similar approval cycle as the main estimate.
2. For a revised estimate -
   1. New line items can be added.
   2. Existing line items can be removed
   3. Quantities in existing estimates can be modified.
3. A contract that is created from this estimate also needs to be revised and sent to contractor for approval.
4. Measurement books accordingly will get changed as per new estimate.
5. If some part of estimate is already measured and bill has been created/approved, reised estimate for that line item cannot go under that approved bill quantity for that line item.

**Schedule Category**

1. Schedule category is a grouping of SORs for easy identification and filtering. There are total about 3000 SOR items divided into 15-20 SOR groups

Example - Earth Work, Masonry, Brick Work, Painting, etc

| Field         | Data Type    | Required (Y/N) | Comments                                      |
| ------------- | ------------ | -------------- | --------------------------------------------- |
| Category Code | Alphanumeric | Y              | Unique Code Assigned to the Schedule Category |
| Category Name | Alphanumeric | Y              | Name Assigned to the Schedule Category        |

**Estimate template**

1. Templates are created for specific type and sub types of work so they can be reused for future use.
2. Templates are a groupings of SOR items that combine to complete a similar kind of work.
3. On the UI, Estimates inbox will have Estimate Template section and users can see list of templates and create new template from there, modify existing template.

Ex. Template to build 100 mt of 20 ft road, Template to build 8\*10 sft standard room. &#x20;

| Field                         | Data Type    | Required (Y/N) | Comments                                                                                       |
| ----------------------------- | ------------ | -------------- | ---------------------------------------------------------------------------------------------- |
| Template Code                 | Alphanumeric | Y              | Define the template code                                                                       |
| Name                          | Alphanumeric | Y              | Name for template                                                                              |
| Description                   | Alphanumeric | Y              | Description of the template                                                                    |
| Status                        | Dropdown     | Y              | <p>Status of the template</p><ul><li>Active</li><li>Inactive</li></ul>                         |
| Work Type                     | Dropdown     | Y              | Select the Type of work. All the work types defined in the system should be shown              |
| Work Sub Type                 | Dropdown     | Y              | Select the Sub type of work. All the work sub types defined in the system should be shown here |
| _\[Array] for each line item_ |              |                |                                                                                                |
| Schedule Category             | Dropdown     | Y              | Options are the list of SOR categories from the SOR category master.                           |
| SOR                           | Alphanumeric | Y              | Enter the template code and search for it                                                      |
| Non\_SOR Code                 | Alphanumeric | N              |                                                                                                |
| Non\_SOR Description          | Alphanumeric | N              |                                                                                                |
| Non\_SOR UOM                  | Dropdown     | N              | lenght--KM; Area--SQM                                                                          |
| Non\_SOR Unit Rate            | Numeric      | N              |                                                                                                |

####

**Mockups**

| Create Estimate               | ![](<../../../.gitbook/assets/image (19).png>) |
| ----------------------------- | ---------------------------------------------- |
| Estimate Successfully Created | ![](<../../../.gitbook/assets/image (42).png>) |
| Estimates Inbox               | ![](<../../../.gitbook/assets/image (14).png>) |
| Inbox Table                   | ![](<../../../.gitbook/assets/image (29).png>) |
| SOR Data entry screen         | ![](<../../../.gitbook/assets/image (39).png>) |



**User Acceptance Criteria**

user should be able to

1. Create Estimate using Template
2. Add SOR items from SOR Master
3. Change values as required for current work
4. Add/auto-populate overheads
5. Able to generate Material Analysis and Labour Analysis
6. Download PDFs of Labour analysis, material analysis, Overall Estimate

