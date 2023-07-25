# Search Muster Roll

## Context

Search a muster roll by various ULB employees/users.

## Actors

Employee

Role: MUSTER ROLL VERIFIER, MUSTER ROLL APPROVER

### Scope

* Search - To search the result upon supplying the parameter values.
* Clear Search - To clear the search parameters supplied.

### Details

1. **Search Muster Roll**- It has to be configurable and is mapped with a role on demand.
2. Search Muster Roll is provided to allow the users to search a muster roll and view its details.

#### Search Criteria

<table><thead><tr><th width="100">#</th><th width="176">Field</th><th width="154">Data Type</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Ward</td><td>Drop-down</td><td>Auto-complete, matching search. The values populated from ward boundary master data.</td></tr><tr><td>2</td><td>Project type</td><td>Drop-down</td><td>Project type masters value</td></tr><tr><td>3</td><td>Project name</td><td>Textbox</td><td>Project name</td></tr><tr><td>4</td><td>Muster Roll ID</td><td>Textbox</td><td>Muster roll ID, unique identification no.</td></tr><tr><td>5</td><td>Status</td><td>Drop-down</td><td>Workflow state of a muster roll.</td></tr><tr><td>6</td><td>Created From</td><td>Date Picker</td><td>Muster roll creation date.</td></tr><tr><td>7</td><td>Created To</td><td>Date Picker</td><td>Muster roll creation date.</td></tr></tbody></table>

1. At least one parameter is required to perform the search.
2. The date range From Date/ To Date is considered one parameter.
3. An exact search is performed for the values entered/selected except the project name.
4. For project name fuzzy search to be enabled.
5. In case multiple parameter values are supplied AND are applied for searching record.

#### Search Result

The search result is shown as given below.

<table><thead><tr><th width="73">#</th><th width="159">Field</th><th width="140">Data Type</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Muster Roll ID</td><td>Display Only</td><td>A hyperlink to open the muster roll  in view mode.</td></tr><tr><td>2</td><td>Project name</td><td>Display Only</td><td>Project name with project description displayed as tool-tip on mouseover</td></tr><tr><td>3</td><td>Name of CBO</td><td>Display Only</td><td>Name of the organization to whom Work Order is awarded.</td></tr><tr><td>5</td><td>Location</td><td>Display Only</td><td>Locality name along with ward name. (Locality + Ward)</td></tr><tr><td>6</td><td>Status</td><td>Display Only</td><td>Workflow status of the muster roll.</td></tr><tr><td>7</td><td>Wage Amount</td><td>Display Only</td><td>Total muster roll amount.</td></tr></tbody></table>

## Validations

At least one parameter is required to perform the search.

## Notifications

Not applicable.

## User Interface

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=3290%3A34994\&t=jQLnT6PHHxDEn1cW-4)

## Acceptance Criteria

<table><thead><tr><th width="224">Acceptance Criteria</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>At least one parameter is required to perform the search.</td></tr><tr><td>2</td><td>Search result displayed on matching records found else no record found message is displayed.</td></tr><tr><td>3</td><td>Pagination is applied if more than 10 records are found.</td></tr></tbody></table>

