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

<table data-header-hidden><thead><tr><th width="88"></th><th></th><th width="143"></th><th width="108"></th><th></th></tr></thead><tbody><tr><td><strong>#</strong></td><td><strong>Field</strong></td><td><strong>Data Type</strong></td><td><strong>Required</strong> </td><td><strong>Description</strong></td></tr><tr><td>1</td><td>Project ID</td><td>Display</td><td>Y</td><td> </td></tr><tr><td>2</td><td>Proposal Date</td><td>Date</td><td>Y</td><td>A date to be entered by the user, can not be a future date.</td></tr><tr><td>3</td><td>Project Name</td><td>Alphanumeric (32)</td><td>Y</td><td><p>Name of the project</p><p>Special Chars allowed <strong>{ / .- _$@#' }</strong></p></td></tr><tr><td>4</td><td>Project Description</td><td>Alphanumeric (256)</td><td>Y</td><td><p>A brief details of works listed under wish-list.</p><p>Special Chars allowed <strong>{ / .- _$@#' ()}</strong></p></td></tr><tr><td> </td><td><strong>Project Details</strong></td><td> </td><td> </td><td> </td></tr><tr><td>5</td><td>Letter Reference/ Requirement number</td><td>Alphanumeric (32)</td><td>N</td><td><p>Usually the Offline File/ Letter Number related to the project</p><p>Special Chars allowed <strong>{ / .- _$@#' }</strong></p></td></tr><tr><td>6</td><td>Project Type</td><td>Drop-down</td><td>Y</td><td>The list of values mentioned under the masters data section. Please refer the <a href="https://digit-discuss.atlassian.net/browse/PFM-2165"><strong>story</strong> </a>to view the sample data of work type.</td></tr><tr><td>7</td><td>Target Demography</td><td>Drop-down</td><td>Y</td><td>What is the demography the work is being done. E.g. Slum, Areas inhabited by SC, ST, Minorities.</td></tr><tr><td>8</td><td>Estimated Cost</td><td>Numeric</td><td>Y</td><td>The pre-estimated cost of the project.</td></tr><tr><td> </td><td><strong>Location Details</strong></td><td> </td><td> </td><td> </td></tr><tr><td>9</td><td>Geolocation</td><td>Co-ordinates</td><td>N</td><td>Input latitude/ longitude, or the GIS-Map to pin the location. </td></tr><tr><td>10</td><td>City</td><td>Auto-populated</td><td>Y</td><td>Name of ULB of the logged in user.</td></tr><tr><td>11</td><td>Ward</td><td>Drop-down</td><td>Y</td><td>Values are the wards no. and names of logged-in ULB/City.</td></tr><tr><td>12</td><td>Locality</td><td>Drop-down</td><td>Y</td><td>Values are the locality names of logged-in ULB/City.</td></tr><tr><td> </td><td><em><strong>Attachments</strong></em></td><td> </td><td> </td><td> </td></tr><tr><td>13</td><td>Proposal Document</td><td>File Attachment</td><td>N</td><td>Name of file which is uploaded as an attachment.</td></tr><tr><td>14</td><td>Finalized Worklist</td><td>File Attachment</td><td>N</td><td>Files can be of type doc, xls, pdf. The documents to be attached are configurable.</td></tr><tr><td>15</td><td>Feasibility Analysis</td><td>File Attachment</td><td>N</td><td>To add more attachments</td></tr><tr><td>16</td><td>Others</td><td>Textbox</td><td>N</td><td>To enter the file name</td></tr><tr><td> </td><td> </td><td>File Attachment</td><td>N</td><td>To attach the file.</td></tr></tbody></table>

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

<table><thead><tr><th width="206">Acceptance Criteria</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Modify project is given to the role specified.</td></tr><tr><td>2</td><td>On Submit, the record gets saved.</td></tr><tr><td>3</td><td>Validations are taken care of.</td></tr></tbody></table>

