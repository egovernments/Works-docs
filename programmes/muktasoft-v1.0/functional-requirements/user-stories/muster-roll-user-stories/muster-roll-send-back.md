# Muster Roll - Send Back

### **Context**

Provide users with the option to send back muster rolls to the previous user in the workflow for specific actions.

## Actors

Employees.

## Actions

1. To send the muster roll back to the previous user in the workflow, **Send Back** action is provided with the below details to be captured.
   * **Comments** - Text area - Non-mandatory - _It allows users to add any remarks/instructions to be passed on to the previous user in the workflow._
   * **Attach Supporting Document** - Document upload - Non-mandatory - _In case any documents are to be attached._
   * **Send Back** - Action Button
   * **Cancel** - Action Button
2. On Send Back -&#x20;
   * The pop-up window is closed and a toast success message is displayed.
   * The view muster roll page is refreshed and the action menu is loaded according to the role the logged-in user has.
   * The muster roll is sent back to the previous user inbox.
   * Workflow states change as per the flow.

| Role                 | From State           | To State                 | Status    |
| -------------------- | -------------------- | ------------------------ | --------- |
| Muster Roll Approver | Pending for approval | Pending for verification | Sent Back |

On cancel, the toast cancel message is displayed on top of the view muster roll page.

**Toast Success Message:** Muster roll has been sent back successfully.

**Failure Message:** Sending back of muster roll is failed.

**Toast Cancel Message:** Action has been cancelled.

## **Notification**

Not applicable.

## **User Interface**

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=3359%3A41037\&t=cbmvGs4oGd2vjDTA-4)

## **Acceptance Criteria**

<table><thead><tr><th width="201">Acceptance Criteria</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>On send back, the pop-up window is closed, a toast success message is displayed and the view muster roll page is refreshed.</td></tr><tr><td>2</td><td>The muster roll is sent back to just the previous user in the workflow and the workflow timeline gets updated.</td></tr><tr><td>3</td><td>Workflow state changes based on the role as mentioned in the story above.</td></tr><tr><td>4</td><td>On cancel, the pop-up window is closed, toast cancel message is displayed.</td></tr></tbody></table>

