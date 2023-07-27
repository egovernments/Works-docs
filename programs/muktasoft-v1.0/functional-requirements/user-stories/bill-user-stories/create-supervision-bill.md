# Create Supervision Bill

## Context

Create Supervision Bill

## Actors

Employee

Role: Bill Creator

## Actions

#### On Create

1. Bill record gets saved into the system, and the workflow state changes to ‘Approved’.
2. Bill No. is generated in a **specified format**.
3. Format for Work Bill No. is **SB-FY-<6digitrunningno.>**. Example: **SB/2022-23/000051**
4. Bill is available to download in **PDF** as per the given format. There will be a separate ticket for PDF download.

### Details

1. Supervision bill is created for the supervision of the CBO for in-progress projects.
2. **Supervision Bills** are created automatically on approval of the muster roll.
3. The system should pick only those Wage and Purchase bills which are approved and pending for supervision bill creation.
4. To calculate the supervision charge amount approved wage bills and purchase bills amount is considered based on the use cases mentioned below.

In case CBO’s role is Implementation Agency

Supervision Charge = (Total of Wage Bills Gross Amount + Total of Purchase Bills Gross Amount) \* Supervision Rate/100;

In case CBO’s role is Implementation Partner

Supervision Charge = (Total of Wage Bills Gross Amount) \* Supervision Rate/100;

5\. To view the bill details, bill search and then view.

## Validations

Field-level validations as mentioned in the attribute tables.

## Configurations

Not applicable.

#### Workflow

Bills get the status approved on creation.

#### Standard Deductions

Not applicable.

## Notifications

To CBO - Supervision bill {billnumber} of amount {amount} is approved and forwarded for payment processing.

## User Interface

Create UI is not required.

## Acceptance Criteria

<table><thead><tr><th width="182">Acceptance Criteria</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Bill is created with the approval of the muster roll.</td></tr><tr><td>2</td><td>Bill gets approved on creation.</td></tr><tr><td>3</td><td>The bill number is generated as per the specified format given.</td></tr><tr><td>4</td><td>The bill amount is calculated as per the logic defined in the story.</td></tr></tbody></table>
