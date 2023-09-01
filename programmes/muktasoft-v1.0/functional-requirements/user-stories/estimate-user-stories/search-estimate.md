# Search Estimate

## Context

Search estimates enable the users to search a in workflow/ approved estimate to take further action, like creating a work order.

## Scope

Search an estimate by various ULB employees/users.

## Actors

Employee

Role: Estimate Creator, Estimate Verifier, Technical Sanctioner, Approver.

## Details

1. **Search Estimate** - It has to be configurable and allow mapping with a role on demand.
2. Search Estimate is provided to allow the users to search for an estimate and view its details.

### Search Criteria

<table><thead><tr><th width="110">S.No.</th><th width="157">Field Name</th><th width="153">Data Type</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Ward</td><td>Drop-down</td><td>Auto-complete, matching search.</td></tr><tr><td>2</td><td>Project Type</td><td>Drop-down</td><td>Project type</td></tr><tr><td>3</td><td>Project Name</td><td>Textbox</td><td>Project name.</td></tr><tr><td>4</td><td>Estimate No.</td><td>Textbox</td><td>Estimate no.</td></tr><tr><td>5</td><td>Status</td><td>Drop-down</td><td>Workflow status of an estimate.</td></tr><tr><td>6</td><td>From Date</td><td>Date Range</td><td>Estimate creation date.</td></tr><tr><td>7</td><td>To Date</td><td>Date Range</td><td>Estimate creation date.</td></tr><tr><td>8</td><td><strong>Search</strong></td><td>Button</td><td> </td></tr><tr><td>9</td><td><strong>Clear Search</strong></td><td>Button</td><td> </td></tr></tbody></table>

&#x20;

1. At least one parameter’s value is required to perform the search.
2. The date range From Date/ To Date is considered one parameter.
3. An exact search is performed for the values entered/selected other than Project Name.
4. For Project Name, fuzzy search to be provided.
5. In case multiple parameter values are supplied AND are applied for searching record.

### Search Result

1. The search result is shown as given below.
2. Pagination is displayed to handle the big result set. 10 records per page are displayed.
3. The option to download the result set in Excel/ PDF is provided.

<table><thead><tr><th width="94">S.No.</th><th width="143">Field Name</th><th width="148">Data Type</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Estimate No.</td><td>Display Only</td><td>A hyperlink to open the estimate  in view mode.</td></tr><tr><td>2</td><td>Project Name</td><td>Display Only</td><td>Mouseover action on the project name shows the project description as a tooltip.</td></tr><tr><td>3</td><td>Location</td><td>Display Only</td><td>Locality name along with ward name. Locality + Ward</td></tr><tr><td>4</td><td>Prepared By</td><td>Display Only</td><td>Name of user who has prepared it.</td></tr><tr><td>5</td><td>Status</td><td>Display Only</td><td>Status of the estimate.</td></tr><tr><td>6</td><td>Estimated Amount</td><td>Display Only</td><td>Total estimated amount.</td></tr></tbody></table>

## Validations

1. At least one parameter’s value is required to perform the search.

## Actions

1. **Search** - It will perform the search and display the result. In case, no result is found appropriate message is displayed.
2. **Clear Search** - It will clear the search parameters.
3. **Estimate No.** - Hyperlink will take the user to the estimate detail page.

## Notifications

Not applicable.

## User Interface

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=1826%3A29380\&t=MLqqNStLndtZykqP-4)

## Acceptance Criteria

<table><thead><tr><th width="199">Acceptance Criteria</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>At least one parameter is required to perform the search.</td></tr><tr><td>2</td><td>Search results are displayed on matching records found else no record found message is displayed.</td></tr><tr><td>3</td><td>Pagination is applied if more than 10 records are found.</td></tr></tbody></table>

