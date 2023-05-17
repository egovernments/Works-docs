# Search Project

## Scope

Search project by ULB/ employee users.

## Actors

Employee Role: Project Admin, Project\_Viewer

## Details

1. **Search Project** action has to be configurable and allow mapping with a role on demand.
2. **Search Project** is provided to allow the users to search Work and view its details/ create estimates.

#### Search Criteria

| **#** | **Field Name** | **Data Type** | **Description**                                                              |
| ----- | -------------- | ------------- | ---------------------------------------------------------------------------- |
| 1     | Ward           | Drop-down     | List of ward boundaries for logged-in user ULB with search by entering name. |
| 2     | Project Type   | Drop-down     | Values of work type from MDMS configuration.                                 |
| 3     | Project Name   | Textbox       | Project Name                                                                 |
| 4     | Project ID     | Textbox       | Work identification no. generated for a work in works proposal               |
| 6     | From Date      | Date Picker   | Proposal creation date, entered by user while creating works proposal.       |
| 7     | To Date        | Date Picker   | Proposal creation date, entered by user while creating works proposal.       |

{% hint style="info" %}
* At least one parameter is required to perform the search.
* Consider From Date and To Date as a Date Range single parameter.
* An exact search is performed for the values entered/selected other than **Project Name**.
* For Project Name, fuzzy search is applicable.
* In case multiple parameter values are supplied AND are applied for searching record.
{% endhint %}

### Search Result

1. The search result is shown as given below.
2. Pagination is displayed to handle the big result set. 10 records are displayed per page.
3. The option to download the result set in Excel/ PDF is provided.

| **#** | **Field**      | **Data Type** | **Comments**                                                                       |
| ----- | -------------- | ------------- | ---------------------------------------------------------------------------------- |
| 1     | Project ID     | Display Only  | A hyperlink to open the project details in view mode.                              |
| 2     | Project Name   | Display Only  | Name of project having **project description** displayed as tool-tip on mouseover. |
| 4     | Location       | Display Only  | Locality name along with ward name.                                                |
| 5     | Estimated Cost | Display Only  | The project cost from the project details                                          |

## Validations

All the actions are displayed based on role action mapping and the user role assignment.

## Actions

1. **Search** - It will perform the search based on the values supplied for search parameters and the logic defined.
2. **Clear Search** - It will clear the values filled for searched parameters.
3. **Project ID** - It will take the user to the **View Project Details Page**.

## Notifications

Not applicable.

## User Interface

{% embed url="https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=1756%3A31164&t=lliv14frYnlv4Nww-4" %}

## Acceptance Criteria

| Acceptance Criteria | Description                                                                         |
| ------------------- | ----------------------------------------------------------------------------------- |
| 1                   | Search Parameters/ Search Logic should be as stated in the story above.             |
| 2                   | Search result is shown as described in the story.                                   |
| 3                   | Pagination is provided to handle more results and 10 records per page is displayed. |
