# View Project Details

## Scope

View Project Details

## Actors

Employee

Role: Project Admin, Project\_Viewer

## Details

1. To view the detailed saved of a Finalized Work, **View Project Details Page** is provided.
2. First, the Project is searched using the **Search Project** feature and then on click of Project ID **View Project Details Page** is opened with the below details displayed.

## Attributes

1. Project ID
2. Proposal Date
3. Project Name
4. Project Description
5. **Project Details**
   * Reference No./ Requirement number
   * Project Type
   * Target Demography
   * Estimated Cost
6. **Location Details**
   * Geolocation
   * City
   * Ward
   * Locality
7. **Action \[Modify Project, Create Estimate, View Estimate** - Actions displayed within action menu]
8. **Attachments** \[Proposal File, etc.]

## Validations

1. A project for which no estimate was created or the latest created estimate is rejected can only be edited. Else the validation message is displayed.
2. Out of Create Estimate/ View Estimate, only one action is displayed based on the condition and the role of the logged-in user.
   * If the estimate is created and in workflow OR approved, View Estimate is displayed.
   * If no estimate is created OR the latest created estimate is rejected, Create Estimate is displayed.

## Configurations

Not applicable.

## Actions

1. **Modify Project** - It will allow the user to edit the project details.
2. **Create Estimate** - It will take the user to create the estimate page.
3. **View Estimate** - It will take the user to the view estimate page.

## Notifications

Not applicable.

## User Interface

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=1756%3A32194\&t=lliv14frYnlv4Nww-4)

## Acceptance Criteria

<table><thead><tr><th width="206">Acceptance Criteria</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Project details are displayed as described in the story.</td></tr><tr><td>2</td><td>Actions are enabled as per the role the logged-in user has.</td></tr><tr><td>3</td><td></td></tr></tbody></table>
