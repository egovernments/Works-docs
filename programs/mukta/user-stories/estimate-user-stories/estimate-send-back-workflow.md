# Estimate Send Back Workflow

## **Scope**

Send back the estimate to the previous user for necessary action.

## **Actors**

Estimate Verifier, Technical Sanction, Estimate Approver

## **Details**

### **Send Back**

* To send the estimate back to the previous user in the workflow, **Send Back** action is provided with the below details to be captured.
  1. **Comments** - This is a text area and non-mandatory. Users can add _any_ remarks/instructions to be passed on to the previous users in the workflow.
  2. **Attach Supporting Document** - This is the field for document upload and non-mandatory. Users can attach and upload supporting documents as required.  _I_
  3. **Send Back** - This is an Action button.
  4. **Cancel** - This is an Action button.
* On Send Back
  1. The pop-up window is closed and a toast success message is displayed.
  2. The view estimate page is refreshed and the action menu is loaded according to the role the logged-in user has.
  3. The estimate is sent back to the previous user’s inbox.
  4. Workflow states change as per the flow.

| Role               | From State                     | To State                       | Status    |
| ------------------ | ------------------------------ | ------------------------------ | --------- |
| Estimate Verifier  | Pending for verification       | Pending for correction         | Sent Back |
| Technical Sanction | Pending for technical sanction | Pending for verification       | Sent Back |
| Estimate Approver  | Pending for approval           | Pending for technical sanction | Sent Back |

* On cancel, the toast cancel message is displayed on the view estimate page.

{% hint style="info" %}
**Toast Success Message:**

The estimate is sent back successfully.

**Failure Message:**

Sending back of estimate is failed.

**Toast Cancel Message:**

Action is cancelled.
{% endhint %}

## **Notification**

Not applicable.

## **UI**

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=2014%3A30534\&t=vPbLKm950fDLjage-4)

## **Acceptance Criteria**

<table><thead><tr><th width="236">Acceptance Criteria</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>On send back, the Pop-up window is closed, a toast success message is displayed and the view estimate page is refreshed</td></tr><tr><td>2</td><td>The estimate is sent back to the previous user in the workflow</td></tr><tr><td>3</td><td>Workflow state changes based on the role as mentioned in the story above</td></tr><tr><td>4</td><td>On cancel, the pop-up window is closed and the toast cancel message is displayed</td></tr></tbody></table>

