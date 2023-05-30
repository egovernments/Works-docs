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

<table data-header-hidden><thead><tr><th width="89"></th><th width="169"></th><th width="140"></th><th width="109"></th><th></th></tr></thead><tbody><tr><td><strong>#</strong></td><td><strong>Field</strong></td><td><strong>Data Type</strong></td><td><strong>Required</strong></td><td><strong>Description</strong></td></tr><tr><td>1</td><td>Date of proposal</td><td>Date</td><td>Y</td><td>A date to be entered by the user, can not be a future date.</td></tr><tr><td>2</td><td>Project Name</td><td>Alphanumeric (32)</td><td>Y</td><td><p>Name of the project.</p><p>Special Chars allowed <strong>{ / .- _$@#' }</strong></p></td></tr><tr><td>3</td><td>Project Description</td><td>Alphanumeric (256)</td><td>Y</td><td><p>A brief details of works listed under wish-list.</p><p>Special Chars allowed <strong>{ / .- _$@#' () :}</strong></p></td></tr><tr><td> </td><td><strong>Project Details</strong></td><td> </td><td> </td><td> </td></tr><tr><td>4</td><td>Letter Reference</td><td>Alphanumeric (32)</td><td>N</td><td><p>Usually the Offline File/ Letter Number related to the project</p><p>Special Chars allowed <strong>{ / .- _$@#' }</strong></p></td></tr><tr><td>5</td><td>Project Type</td><td>Drop-down</td><td>Y</td><td>The list of values mentioned under the masters data section. Please refer the <a href="https://digit-discuss.atlassian.net/browse/PFM-2165"><strong>story</strong> </a>to view the sample data of work type.</td></tr><tr><td>6</td><td>Target Demography</td><td>Drop-down</td><td>Y</td><td>What is the demography the work is being done. E.g. Slum, Areas inhabited by SC, ST, Minorities.</td></tr><tr><td>7</td><td>Estimated Cost</td><td>Numeric</td><td>Y</td><td>The pre-estimated cost of the project.</td></tr><tr><td> </td><td><strong>Location Details</strong></td><td> </td><td> </td><td> </td></tr><tr><td>8</td><td>Geolocation</td><td>Co-ordinates</td><td>N</td><td>Input latitude/ longitude, or the GIS-Map to pin the location. Co-ordinate validation.</td></tr><tr><td>9</td><td>City</td><td>Auto-populated</td><td>Y</td><td>Name of ULB of the logged in user.</td></tr><tr><td>10</td><td>Ward</td><td>Drop-down</td><td>Y</td><td>Values are the wards no. and names of logged-in ULB/City.</td></tr><tr><td>11</td><td>Locality</td><td>Drop-down</td><td>Y</td><td>Values are the locality names of logged-in ULB/City.</td></tr><tr><td> </td><td><em><strong>Relevant Documents</strong></em></td><td> </td><td> </td><td> </td></tr><tr><td>12</td><td>Proposal Document</td><td>File Attachment</td><td>N</td><td>Name of file which is uploaded as an attachment.</td></tr><tr><td>13</td><td>Finalized Worklist</td><td>File Attachment</td><td>N</td><td>Files can be of type jpg, doc, xls, docx, xlsx, pdf. The documents to be attached are configurable.</td></tr><tr><td>14</td><td>Feasibility Analysis</td><td>File Attachment</td><td>N</td><td>To add more attachments</td></tr><tr><td>15</td><td>Others</td><td>Textbox</td><td>N</td><td>To enter the file name</td></tr><tr><td> </td><td> </td><td>File Attachment</td><td>N</td><td>To attach the file.</td></tr></tbody></table>

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

<table><thead><tr><th width="206">Acceptance Criteria</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Create project is given to the role specified.</td></tr><tr><td>2</td><td>On save, the record gets saved, the success page is displayed and the respective ID is generated as per the given format.</td></tr><tr><td>3</td><td>All the validations are taken care.</td></tr></tbody></table>
