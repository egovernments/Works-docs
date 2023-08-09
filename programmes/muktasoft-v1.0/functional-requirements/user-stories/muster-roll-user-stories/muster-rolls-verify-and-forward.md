# Muster Rolls - Verify & Forward

## **Context**

Provide users with options to verify and forward muster rolls to subsequent workflows.

## Actors

Employees.

## Actions

1. To verify and forward the muster roll to the next workflow user, a pop-up window is provided to capture the below-given details.
   * **Assignee name**- Drop-down - Non Mandatory -  _The next user in the workflow i.e._ _**Approver**, hence the employees having the role_ _**Muster\_Roll\_Approver**_ _are displayed in drop-down with the name and the designation. E.g. Mahesh K working as ME and have the role of Muster\_Roll\_Approver will be displayed ‘Mahesh K - Municipal Engineer’._
   * **Comments** - Text area - Non-Mandatory -  _In case any comments to be added._
   * **Attach Supporting Document** - Non-Mandatory - _Any document to be uploaded as a supporting document._
   * **Verify and Forward** - _Action Button_
   * **Cancel** - _Action Button_
2. On **Verify and Forward -**&#x20;
   * The pop-up window is closed, a toast success message is displayed and the view muster roll page is refreshed.
   * The action menu is loaded according to the role-action mapping of the currently logged-in user.
   * The muster roll is forwarded to the next user in the workflow and shown in its inbox.
   * The workflow state changes accordingly and timelines show the current state of the muster roll.
   * The muster roll is removed from the currently logged-in user’s inbox.

| Role                 | From State               | To State             | Status   |
| -------------------- | ------------------------ | -------------------- | -------- |
| Muster Roll Verifier | Pending for verification | Pending for approval | Verified |

On cancel, a pop-up window is closed, toast cancel message is displayed on the view muster roll page.

**Toast Success Message:** The muster roll has been forwarded successfully.

**Failure Message:** Verification of muster roll failed.

**Toast Cancel Message:** Action has been cancelled.

## **Notification**

Not applicable.

## **User Interface**

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=3359%3A41038\&t=cbmvGs4oGd2vjDTA-4)

## **Acceptance Criteria**

<table><thead><tr><th width="185">Acceptance Criteria</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>On verify and forward, the muster roll is forwarded to the next user in the flow.</td></tr><tr><td>2</td><td>The pop-up window gets closed and the view muster roll page is refreshed. A toast success message is displayed.</td></tr><tr><td>3</td><td>Workflow states changes and based on the existing role the user can view the muster roll page on refresh.</td></tr><tr><td>4</td><td>On cancel pop-up window gets closed. A toast cancel message is displayed.</td></tr></tbody></table>

