# Estimate Inbox

## Scope

Inbox for Employees

## Actors

Employees

Role: Estimate\_Creator, Estimate\_Verifier, Technical\_Sanctioner, Estimate\_Approver.

## Details

Inbox page for employees to be developed duly taking care of the MUKTA branding aspect.

### Attributes

The inbox of employees is divided into 4 sections.

### **Menu Title**

1. Product Name - **MUKTA** in this case.
2. Menu Links
   * Create Estimate - This link will take the user to the **Search Project** screen to search the project and create the estimate.
   * Search Estimate - This link will take the user to the **Search Estimate** screen to search the estimates and view the details.

### **Search Parameters**

1. Estimate No.
2. Project ID
3. Project type

### **Filters**

1. Assigned to me - This filter allows the users to filter the estimates assigned to logged-in users only and display the results accordingly.
2. Assigned to all - Selected by default this filter allows the users to search and view all the estimates that are pending for action and assigned to the user-specific role.
3. Ward - Multi-select filter to fetch estimates created for selected projects belonging to the selected ward(s).
4. Locality - Multi-select filter to fetch estimates created for selected projects belonging to selected locality(ies).
5. Workflow state - Filter to display the estimates in the selected workflow state.

### **Result Display Area**

1. Estimate No.
2. Project name
3. Prepared by
4. Assignee
5. Workflow state
6. Estimated Amount
7. SLA days remaining

{% hint style="info" %}
**It should be a DIGIT standard Inbox that allows configuration based on requests from the implementation.**
{% endhint %}

## Validations

Not applicable

## Configurations

Not applicable

## Actions

Menu Links and Search, Filter Apply and Numbers Hyperlinks.

## Notifications

Not applicable.

## User Interface

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=1595%3A22111\&t=MLqqNStLndtZykqP-4)

## Acceptance Criteria

| Acceptance Criteria | Description                                                   |
| ------------------- | ------------------------------------------------------------- |
| 1                   | It should be a service-wise inbox for all the employee users. |
| 2                   | Must follow the DIGIT standard inbox design.                  |
