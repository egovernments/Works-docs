# Verify & Forward

## **Context**

Provide users with the option to verify and forward the bills in the workflow.

## **Actions**

1. Verify and forward action is provided with a pop-up window to capture the below given details.
   * **Assignee name**- Drop-down - Non Mandatory -  _The next user in the workflow i.e._ _**Verification**, hence the employees having the role_ _**Bill\_Verifier**_ _are displayed in drop-down with the name and the designation. E.g. Mahesh K working as ME and having the role of Bill\_Verifier will be displayed as ‘Mahesh K - Accountant’._
   * **Comments** - Text area - Non-Mandatory -  In case any comments to be added.
   * **Attach Supporting Document** - Non-Mandatory - Any document to be uploaded as a supporting document.
   * **Verify and Forward** - Action Button
   * **Cancel** - Action Button
2. On **Verify and Forward -**
   * A pop-up window is closed, a toast success message is displayed and the view bill page is refreshed.
   * The action menu is loaded according to the role-action mapping of the currently logged-in user.
   * Bill is forwarded to the next user in the workflow and shown in its inbox.
   * The workflow state changes accordingly and timelines show the current state of the Bill.
   * Bill is removed from the currently logged-in user’s inbox.

<table><thead><tr><th width="154">Role</th><th>From State</th><th>To State</th><th>Status</th></tr></thead><tbody><tr><td>Bill Verifier</td><td>Pending for verification</td><td>Pending for approval</td><td>Verified</td></tr></tbody></table>

On cancel, the pop-up window is closed and a toast cancel message is displayed on the View Bill page.

**Toast Success Message:** Bill has been forwarded successfully.

**Failure Message:** Verification of bill failed.

**Toast Cancel Message:** Action has been cancelled.

## **Notification**

Not applicable.

## **User Interface**

This is a common UI which we have for the verify and forward workflow action.

## **Acceptance Criteria**

<table><thead><tr><th width="192">Acceptance Criteria</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>On verify and forward action, the bill is forwarded to the next user in the flow.</td></tr><tr><td>2</td><td>The pop-up window is closed and the bill page is refreshed. The toast success message is displayed.</td></tr><tr><td>3</td><td>Workflow states changes and based on the role the existing user has view bill page refreshes.</td></tr><tr><td>4</td><td>On cancel, the pop-up window gets closed. A toast cancel message is displayed.</td></tr></tbody></table>
