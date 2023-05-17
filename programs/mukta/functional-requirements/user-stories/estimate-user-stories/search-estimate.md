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

| S.No. | Field Name       | Data Type  | Description                     |
| ----- | ---------------- | ---------- | ------------------------------- |
| 1     | Ward             | Drop-down  | Auto-complete, matching search. |
| 2     | Project Type     | Drop-down  | Project type                    |
| 3     | Project Name     | Textbox    | Project name.                   |
| 4     | Estimate No.     | Textbox    | Estimate no.                    |
| 5     | Status           | Drop-down  | Workflow status of an estimate. |
| 6     | From Date        | Date Range | Estimate creation date.         |
| 7     | To Date          | Date Range | Estimate creation date.         |
| 8     | **Search**       | Button     |                                 |
| 9     | **Clear Search** | Button     |                                 |

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

| S.No. | Field Name       | Data Type    | Description                                                                      |
| ----- | ---------------- | ------------ | -------------------------------------------------------------------------------- |
| 1     | Estimate No.     | Display Only | A hyperlink to open the estimate  in view mode.                                  |
| 2     | Project Name     | Display Only | Mouseover action on the project name shows the project description as a tooltip. |
| 3     | Location         | Display Only | Locality name along with ward name. Locality + Ward                              |
| 4     | Prepared By      | Display Only | Name of user who has prepared it.                                                |
| 5     | Status           | Display Only | Status of the estimate.                                                          |
| 6     | Estimated Amount | Display Only | Total estimated amount.                                                          |

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

| Acceptance Criteria | Description                                                                                       |
| ------------------- | ------------------------------------------------------------------------------------------------- |
| 1                   | At least one parameter is required to perform the search.                                         |
| 2                   | Search results are displayed on matching records found else no record found message is displayed. |
| 3                   | Pagination is applied if more than 10 records are found.                                          |

