# Create Project

## Context

ULBs prepare the list of works by inviting the ward members and then go through an approval process duly checking on the allocation of funds available. Once the list is finalized and approved in all aspects, the option to enter the same into the system is provided to enable the ULB users to prepare an estimate for each work and then take the work to the closure completing the other activities in the system.

Each finalized Work in the work list is considered a project and the same is created first to start the work.

## Scope

Create Project

## Actors

Employee

Role: Project Admin (JE, AE, ME)

## Details

1. Option is provided to enter the approved/ finalized work from the work list for which an estimate will be prepared and the work will be carried out.
2. **Create Project** is developed as per the UI design provided and the attributes listed below.

## Attributes

| **#** | **Field**                | **Data Type**      | **Required** | **Description**                                                                                                                                                                      |
| ----- | ------------------------ | ------------------ | ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1     | Date of proposal         | Date               | Y            | A date to be entered by the user, can not be a future date.                                                                                                                          |
| 2     | Project Name             | Alphanumeric (32)  | Y            | <p>Name of the project.</p><p>Special Chars allowed <strong>{ / .- _$@#' }</strong></p>                                                                                              |
| 3     | Project Description      | Alphanumeric (256) | Y            | <p>A brief details of works listed under wish-list.</p><p>Special Chars allowed <strong>{ / .- _$@#' () :}</strong></p>                                                              |
|       | **Project Details**      |                    |              |                                                                                                                                                                                      |
| 4     | Letter Reference         | Alphanumeric (32)  | N            | <p>Usually the Offline File/ Letter Number related to the project</p><p>Special Chars allowed <strong>{ / .- _$@#' }</strong></p>                                                    |
| 5     | Project Type             | Drop-down          | Y            | The list of values mentioned under the masters data section. Please refer the [**story** ](https://digit-discuss.atlassian.net/browse/PFM-2165)to view the sample data of work type. |
| 6     | Target Demography        | Drop-down          | Y            | What is the demography the work is being done. E.g. Slum, Areas inhabited by SC, ST, Minorities.                                                                                     |
| 7     | Estimated Cost           | Numeric            | Y            | The pre-estimated cost of the project.                                                                                                                                               |
|       | **Location Details**     |                    |              |                                                                                                                                                                                      |
| 8     | Geolocation              | Co-ordinates       | N            | Input latitude/ longitude, or the GIS-Map to pin the location. Co-ordinate validation.                                                                                               |
| 9     | City                     | Auto-populated     | Y            | Name of ULB of the logged in user.                                                                                                                                                   |
| 10    | Ward                     | Drop-down          | Y            | Values are the wards no. and names of logged-in ULB/City.                                                                                                                            |
| 11    | Locality                 | Drop-down          | Y            | Values are the locality names of logged-in ULB/City.                                                                                                                                 |
|       | _**Relevant Documents**_ |                    |              |                                                                                                                                                                                      |
| 12    | Proposal Document        | File Attachment    | N            | Name of file which is uploaded as an attachment.                                                                                                                                     |
| 13    | Finalized Worklist       | File Attachment    | N            | Files can be of type jpg, doc, xls, docx, xlsx, pdf. The documents to be attached are configurable.                                                                                  |
| 14    | Feasibility Analysis     | File Attachment    | N            | To add more attachments                                                                                                                                                              |
| 15    | Others                   | Textbox            | N            | To enter the file name                                                                                                                                                               |
|       |                          | File Attachment    | N            | To attach the file.                                                                                                                                                                  |

## Validations

Field-level validations as mentioned in the attribute tables.

* Mandatory Fields: \<Field Name> can not be empty.
* Date of proposal: The date of the proposal can not be a future date.
* Project Name:&#x20;
  1. Project name can only include letters, numbers, and the following special characters: **/ .- \_$@#'**&#x20;
  2. The project name should not be more than 32 characters.
* Project Description:
  1. Project name can only include letters, numbers, and the following special characters: **/ .- \_$@#' ():**
  2. The project description should not be more than 256 characters.
* Letter reference/ Requirement number:
  1. Letter reference can only include letters, numbers, and the following special characters: **/ .- \_$@#'**
  2. Letter reference should not be more than 32 characters
* Estimated Cost: Estimated Cost can only include numbers.
* Geolocation: Entered co-ordinates are not the valid latitude or longitude.

## Configurations

### Attachments

It should be as per the DIGIT standard attachment component/mechanism.

### **Workflow**

Not applicable.

## Actions

**Submit -** On submit following activities are performed.

On successful creation of a project.

1. **The success Page** is displayed.
2. The project record gets saved into the system with the status **Finalized.**
3. The project ID is generated in a **specified format**.&#x20;
4. Format for Project ID is **PJ/FY/<6digitrunningno.>**. Example:  **PJ/2022-23/000051**
5. 6 DIGIT running sequence number is reset to 1 at the start of every financial year.
6. Project details is available to download in **PDF** as per the given format. There will be a separate ticket for PDF download.

On Failure

1. **The failure Page** is displayed.

## Notifications

Not applicable.

## User Interface



## Acceptance Criteria

| Acceptance Criteria | Description                                                                                                               |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| 1                   | Create project is given to the role specified.                                                                            |
| 2                   | On save, the record gets saved, the success page is displayed and the respective ID is generated as per the given format. |
| 3                   | All the validations are taken care.                                                                                       |
