# Modify Project Details

## Scope

Modify Project

Search Project → View Project Details → Modify Project Details

## Actors

Employee Role: Project Admin

## Details

1. Option is provided to modify the project details.
2. **Modify Project** form is developed as per the UI design provided and the attributes listed below.

## Attributes

| **#** | **Field**                            | **Data Type**      | **Required**  | **Description**                                                                                                                                                                      |
| ----- | ------------------------------------ | ------------------ | ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1     | Project ID                           | Display            | Y             |                                                                                                                                                                                      |
| 2     | Proposal Date                        | Date               | Y             | A date to be entered by the user, can not be a future date.                                                                                                                          |
| 3     | Project Name                         | Alphanumeric (32)  | Y             | <p>Name of the project</p><p>Special Chars allowed <strong>{ / .- _$@#' }</strong></p>                                                                                               |
| 4     | Project Description                  | Alphanumeric (256) | Y             | <p>A brief details of works listed under wish-list.</p><p>Special Chars allowed <strong>{ / .- _$@#' ()}</strong></p>                                                                |
|       | **Project Details**                  |                    |               |                                                                                                                                                                                      |
| 5     | Letter Reference/ Requirement number | Alphanumeric (32)  | N             | <p>Usually the Offline File/ Letter Number related to the project</p><p>Special Chars allowed <strong>{ / .- _$@#' }</strong></p>                                                    |
| 6     | Project Type                         | Drop-down          | Y             | The list of values mentioned under the masters data section. Please refer the [**story** ](https://digit-discuss.atlassian.net/browse/PFM-2165)to view the sample data of work type. |
| 7     | Target Demography                    | Drop-down          | Y             | What is the demography the work is being done. E.g. Slum, Areas inhabited by SC, ST, Minorities.                                                                                     |
| 8     | Estimated Cost                       | Numeric            | Y             | The pre-estimated cost of the project.                                                                                                                                               |
|       | **Location Details**                 |                    |               |                                                                                                                                                                                      |
| 9     | Geolocation                          | Co-ordinates       | N             | Input latitude/ longitude, or the GIS-Map to pin the location.                                                                                                                       |
| 10    | City                                 | Auto-populated     | Y             | Name of ULB of the logged in user.                                                                                                                                                   |
| 11    | Ward                                 | Drop-down          | Y             | Values are the wards no. and names of logged-in ULB/City.                                                                                                                            |
| 12    | Locality                             | Drop-down          | Y             | Values are the locality names of logged-in ULB/City.                                                                                                                                 |
|       | _**Attachments**_                    |                    |               |                                                                                                                                                                                      |
| 13    | Proposal Document                    | File Attachment    | N             | Name of file which is uploaded as an attachment.                                                                                                                                     |
| 14    | Finalized Worklist                   | File Attachment    | N             | Files can be of type doc, xls, pdf. The documents to be attached are configurable.                                                                                                   |
| 15    | Feasibility Analysis                 | File Attachment    | N             | To add more attachments                                                                                                                                                              |
| 16    | Others                               | Textbox            | N             | To enter the file name                                                                                                                                                               |
|       |                                      | File Attachment    | N             | To attach the file.                                                                                                                                                                  |

## Validations

1. Field-level validations as mentioned in the attribute tables. Same as mentioned in Create Project Story.
2. A project for which no estimate is created or the latest created estimate is rejected can only be modified. Else the validation message on click of Modify button is displayed.

The estimate is prepared for the project, hence the details can not be modified.

## Configurations

### Attachments

DIGIT standard attachment component to be provided.

### Workflow

No workflow is to be configured for the modification of project details.

## Actions

**Submit:** On submit -

1. The project record gets saved into the system and Success Page is displayed.
2. Due to some technical reason if modification fails, Failure Page is displayed.

## Notifications

Not applicable.

## User Interface

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=1769%3A29696\&t=lliv14frYnlv4Nww-4)

## Acceptance Criteria

| Acceptance Criteria | Description                                    |
| ------------------- | ---------------------------------------------- |
| 1                   | Modify project is given to the role specified. |
| 2                   | On Submit, the record gets saved.              |
| 3                   | Validations are taken care of.                 |

