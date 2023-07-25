# Create Wage Bill

## Context

Provide users with the option to create wage bills.

## Actors

Employee

Role: Bill Creator

## Actions

#### On Create

1. Bill record gets saved into the system, and attains a workflow state ‘Approved’.
2. Bill No. is generated in a **specified format**.
3. Format for Work Bill No. is **WB-FY-<6digitrunningno.>**. Example: **WB/2022-23/000051**
4. Bill is available to download in **PDF** as per the given format. There will be a separate ticket for PDF download.

### Details

1. A wage bill is created for the wages paid to wage seekers.
2. **The wage bill** is created automatically on approval of the muster roll.
3. To calculate the wage amount and the payee detail muster roll is considered as input.
4. A success toast message is displayed on the creation of the bill.
5. To view the bill details bill is searched and then view.

## Validations

Not applicable.

## Configurations

Not applicable.

#### Workflow

#### Standard Deductions

Not applicable.

### Notifications

Not applicable.

## User Interface

No UI is needed.

## Acceptance Criteria

<table><thead><tr><th width="237">Acceptance Criteria</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Bill is created with the approval of the muster roll.</td></tr><tr><td>2</td><td>Bill gets approved on creation.</td></tr><tr><td>3</td><td>The bill number is generated as per the specified format given.</td></tr><tr><td>4</td><td>The bill amount is calculated as per the logic defined in the story.</td></tr></tbody></table>

