# Estimate Details

## Overview



## API Specifications

### API Contract Link

{% embed url="https://editor.swagger.io/?url=https://raw.githubusercontent.com/egovernments/DIGIT-Works/develop/backend/estimate-service/Estimate-service-1.0.0.yaml" %}

### APIs



## Data Model

### DB Schema Diagram



### Web Sequence Diagrams



### Master Data Types

#### [Schedule of Rates (SOR)](estimate-details.md#schedule-of-rates-sor)

1. SOR is a line item representing the rate for a single unit of work. SOR is defined by the Central PWD or state PWD and is revised based on the market needs from time to time.&#x20;
2. Each executing authority ULB/Department may modify the rates of these SORs by applying lead charges. Hence, SOR line items with material supply will have different rates across various ULBs

Example: Cost of 1 sqm of the wall, 1 quintal of sand, and 100 man-days of unskilled labour.

The following are attributes for SOR Master:

| Field                             | Data Type    | Required (Y/N) | Comments                                                                                                                                       |
| --------------------------------- | ------------ | -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| SOR Category ID                   | Drop down    | Y              | <p>Options will be the list of Category Code from the SOR category type master<br>The combination of category Code and Item code is unique</p> |
| Item ID                           | Alphanumeric | Y              |                                                                                                                                                |
| Item Description                  |              | Y              | Item description of the selected Item                                                                                                          |
| Unit of Measurement               |              | Y              | Options will be the list from Unit of measurement master                                                                                       |
| \[Array] for specific date ranges |              |                |                                                                                                                                                |
| Item Rate                         | Numeric      | Y              | Multiple entries can be specified for each Item, but there cannot be an overlap in the rates for a range of dates                              |
| Item rate Applicable From         | Date         | Y              | To be entered in the format dd/mm/yyyy                                                                                                         |
| Item rate Applicable To           | Date         | N              | To be entered in the format dd/mm/yyyy                                                                                                         |

#### [Non Schedule of Rates (SOR)](estimate-details.md#non-schedule-of-rates-sor)

1. Non-SOR items are not defined by CPWD and based on project requirements will get added to the estimate.&#x20;

Example: Purchasing fancy benches & themed dustbins at the park. The rates in this case is fixed by the JE after discussing with potential vendors.

#### [Overheads](estimate-details.md#overheads)

1. Overheads are additions on top of the project costs. Overheads go into specific heads of accounts at the time of billing.&#x20;
2. Each overhead will be defined within a time range with either percentage or lump sum value of the entire estimated cost.

| Field                             | Data Type    | Required (Y/N) | Comments                                                             |
| --------------------------------- | ------------ | -------------- | -------------------------------------------------------------------- |
| ID                                | NA           | NA             | ID generated for each overhead type                                  |
| Name                              | Alphanumeric | Y              | <p>Name of the overhead<br><br>Ex. Labour Cess, GST, Royalty etc</p> |
| Description                       | Alphanumeric | N              | Description                                                          |
| Account head                      | Dropdown     | Y              | Accounthead to which overheads should be credited                    |
| Expenditure type                  | Dropdown     | Y              | <p>• Capital<br>• Revenue</p>                                        |
| \[Array] for specific date ranges |              |                |                                                                      |
| From Date                         | Date         | Y              | Date from which these rates are applicable                           |
| To Date                           | Date         | Y              |                                                                      |
| Percentage/ Lumpsum               | Numeric      | Y              | Percentage or Lumpsum amount of estimate including value             |

#### [Schedule Category](estimate-details.md#schedule-category)

1. A Schedule Category is a grouping of SORs for easy identification and filtering. There are total of about 3000 SOR items divided into 15-20 SOR groups

Example: Earth Work, Masonry, Brick Work, Painting, etc

| Field         | Data Type    | Required (Y/N) | Comments                                      |
| ------------- | ------------ | -------------- | --------------------------------------------- |
| Category Code | Alphanumeric | Y              | Unique Code Assigned to the Schedule Category |
| Category Name | Alphanumeric | Y              | Name Assigned to the Schedule Category        |

#### [Estimate template](estimate-details.md#estimate-template)

1. Templates are created for a specific type and sub-type of work so they can be reused for future use.
2. Templates are groupings of SOR items that combine to complete a similar kind of work.

Example: Template to build 100 mt of 20 ft road, Template to build 8\*10 sq ft standard room. &#x20;

| Field                         | Data Type    | Required (Y/N) | Comments                                                                                       |
| ----------------------------- | ------------ | -------------- | ---------------------------------------------------------------------------------------------- |
| Template Code                 | Alphanumeric | Y              | Define the template code                                                                       |
| Name                          | Alphanumeric | Y              | Name for template                                                                              |
| Description                   | Alphanumeric | Y              | Description of the template                                                                    |
| Status                        | Dropdown     | Y              | <p>Status of the template<br>• Active<br>• Inactive</p>                                        |
| Work Type                     | Dropdown     | Y              | Select the Type of work. All the work types defined in the system should be shown              |
| Work Sub Type                 | Dropdown     | Y              | Select the Sub type of work. All the work sub types defined in the system should be shown here |
| _\[Array] for each line item_ |              |                |                                                                                                |
| Schedule Category             | Dropdown     | Y              | Options are the list of SOR categories from the SOR category master.                           |
| SOR                           | Alphanumeric | Y              | Enter the template code and search for it                                                      |
| Non\_SOR Code                 | Alphanumeric | N              |                                                                                                |
| Non\_SOR Description          | Alphanumeric | N              |                                                                                                |
| Non\_SOR UOM                  | Dropdown     | N              | lenght--KM; Area--SQM                                                                          |
| Non\_SOR Unit Rate            | Numeric      | N              |                                                                                                |

#### [Labour Rate Master](estimate-details.md#labour-rate-master)

Labour rates are defined by various skill categories and departments at times. Labour rates master helps in generating labour statements for the project.

Below are the attributes for the labour rate master

| Field                             | Data Type    | Required (Y/N) | Comments                                              |
| --------------------------------- | ------------ | -------------- | ----------------------------------------------------- |
| ID                                | NA           | Na             | System generated ID                                   |
| Department                        | Dropdown     | Y              | Labour rates may vary by each department              |
| Skill Category                    | Dropdown     | Y              | Highly Skilled, Semi Skilled Unskilled etc            |
| Description of Labour             | Alphanumeric | Y              | Technical Assistant, Stone Polisher, Smith etc        |
| Quantity                          | Numeric      | Y              | Quantity for which base rate is defined. Default to 1 |
| Unit                              | Dropdown     | Y              | Day/Week/Month                                        |
| \[Array] for specific date ranges |              |                |                                                       |
| Rate                              | Numeric      | Y              | Rate of Labour for specified (Quantity' units)        |
| From Date                         | Date         | Y              | Date from which these rates are applicable            |
| To Date                           | Date         | Y              | Date to which these rates are applicable              |

#### [Material Rate Master](estimate-details.md#material-rate-master)

Material rate master helps in identifying and abstracting materials from a list of estimates and creating a material statement for the project.

| Field                   | Data Type    | Required (Y/N) | Comments                                                                   |
| ----------------------- | ------------ | -------------- | -------------------------------------------------------------------------- |
| ID                      | NA           | Na             | System generated ID                                                        |
| Department              | Dropdown     | Y              | Labour rates may vary by each department                                   |
| Material Category       | Dropdown     | Y              | brick and tile, stone and road, metal and iron etc                         |
| Description of Material | Alphanumeric | Y              | <p>Second Class Table Moulded Chamber Burnt Bricks 9" x 41<br>/2" x 3"</p> |
| Quantity                | Numeric      | Y              | Quantity for which base rate is defined. Default to 1                      |
| Unit                    | Dropdown     | Y              | Nos, Ton, etc                                                              |
| Rate                    | Numeric      | Y              | Rate of material for specified (Quantity' units)                           |

#### [Lead Statement Master](estimate-details.md#lead-statement-master)

Labour and material rate masters as defined by PWD may need to be revised as per the lead (distance) rates for each executing body. This is applicable only for a few materials where quarries are situated far from the operating site.&#x20;

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

