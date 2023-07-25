# Muster Roll - Edit/Submit

## **Context**

Provide users with the option to edit or submit muster rolls.

## Actors

Employees.

## Actions

1. ‘**Edit**’ Muster roll action is to be mapped with CBO ADMIN and Muster Roll Verifier.
2. It is configurable and can be mapped with other roles too on demand.
3. The muster roll which is in a workflow can only be edited.
4. The approved muster roll cannot be edited.
5. Edit muster roll allows the user to edit the muster roll.
6. Only the **Days Measured** under the attendance details are allowed to edit by Muster Roll Verifier.
7. **Quantity of work (days)** values changes according to the change in **Days Measured**. Quantity of work = Sum of days measured for all the wage seekers.

Once the muster roll is edited, it is re-submitted again for verification/ approval using the action **‘Submit’**.

**On submit**, based on the logged-in user role, a workflow pop-up window is displayed.

<table><thead><tr><th width="282">Role</th><th>Workflow Window</th></tr></thead><tbody><tr><td>CBO ADMIN</td><td> </td></tr><tr><td>Muster Roll Verifier</td><td>Verify and Forward pop-up window</td></tr></tbody></table>

1. On respective workflow action, changes get saved and the muster roll is forwarded to the next user in the workflow.
2. On Cancel, the pop-up window gets closed and the action gets cancelled.
3. Accordingly, the messages are shown.

## **Notification**

On edit of muster roll, SMS notification is sent to CBO.

Dear \<contactpersonname>, Muster roll \<musterrollid> for the project \<project name> has been modified by the \<employeeuser+designation>. Please login to MUKTASoft to see the detail.

## **User Interface**

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=3359%3A39409\&t=cbmvGs4oGd2vjDTA-4)

## **Acceptance Criteria**

<table><thead><tr><th width="202">Acceptance Criteria</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Role-based access based on configuration.</td></tr><tr><td>2</td><td>The muster roll which is in a workflow only can be edited.</td></tr><tr><td>3</td><td>Muster roll is opened in editable mode.</td></tr><tr><td>4</td><td>The details given in table can be edited by user.</td></tr><tr><td>5</td><td>On Submit, the muster roll is again forwarded to the next user for the approval process.</td></tr></tbody></table>

