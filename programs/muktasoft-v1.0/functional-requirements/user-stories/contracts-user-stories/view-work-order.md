# View Work Order

## Context

View specific work order details.

## Actors

Employee

Role: Work Order Creator, Work Order Verifier, Work Order Approver.

## Actions

#### Scope

View Work Order

Search Work Order→ View Work Order

#### Details

1. To view the details of the saved Work Order, a **View Work Order** page is provided.
2. First the work order is searched using the search Work Order feature and then on click of Work Order No. the view work order page is opened displaying the below details.

#### Attributes

1. Work order number
2. Project ID
3. Date of proposal
4. Project name
5. Project description
6. **Work Order Details**
   * Name of CBO
   * Organization ID
   * Role of CBO
   * Designation of officer in-charge
   * Name of the officer in-charge
   * Project completion period (In days)
   * Work order amount
7. **Relevant Document**
   * File Attachments - allow to view the documents, on click document is opened to view.
8. **Workflow timelines** - As per the designed UI.
9. **Terms and conditions** - Terms and conditions are displayed as entered.

#### Workflow Actions

1. For In Workflow Work Order - Workflow actions are based on the role of the logged-in user.
   * Edit
   * Verify and Forward
   * Send Back
   * Send Back To Originator
   * Approve
   * Reject
2. For accepted WO
   * Revise Work Order (Time extension only)

## Validations

Field level validations as mentioned in the attribute tables.

## Configurations

Not applicable.

## Notifications

Not applicable.

## User Interface

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=1835%3A32821\&t=ewVSJBLAMoyry76D-4)

## Acceptance Criteria

<table><thead><tr><th width="200">Acceptance Criteria</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Work Order details are displayed as described in the story.</td></tr><tr><td>2</td><td>Actions are enabled as per the work order workflow state and role the logged-in user has.</td></tr></tbody></table>

