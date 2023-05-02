# Estimate Create/Submit Workflow

## **Scope**

Fill in and submit estimate details.

## Actors

Estimate Creators

## **Details**

### **Submit**

* **Estimate Creators** will find the **On** **Submit** pop-up window to capture the details given below:
  1. **Assignee name** - This field offers a drop-down and is non-mandatory. The drop-down displays the names of employees having the role of _**Estimate\_Verifier**  and their Designation. For instance, Suresh K working as Junior Assistant Executive Engineer and having the role of estimate verifier is displayed as ‘**Suresh K - Assistant Executive Engineer**’._
  2. **Comments** - This field is a text area and is non-mandatory. The field is used to add any remarks or comments in context.
  3. **Forward** - This is an Action button_._
  4. **Cancel** - This is an Action button.
* The On **Forward** pop-up window captures the following details:
  1. The submit pop-up window is closed and a toast success message is displayed and the view estimate page is refreshed.
  2. The action menu is loaded according to the role-action mapping of the currently logged-in user.
  3. The estimate is forwarded to the next user in the workflow and shown in its inbox.
  4. The workflow state changes accordingly and timelines show the current state of the estimate.
  5. The estimate is removed from the currently logged-in user’s inbox.

| Action             | Role             | From State             | To State                 |
| ------------------ | ---------------- | ---------------------- | ------------------------ |
| Submit/ Forward    | Estimate Creator |                        | Pending for verification |
| Re-submit/ Forward | Estimate Creator | Pending for correction | Pending for verification |

* The On Cancel closes the submit pop-up window and displays the toast cancel message on the View Estimate page.

{% hint style="success" %}
**Toast Success Message**

The estimate is forwarded successfully.

**Failure Message**

Forward of estimate failed.

**Toast Cancel Message**

Action is cancelled.
{% endhint %}

## **Validation**

As mentioned in the story.

## **Notification**

Not applicable.

## **UI**

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=1828%3A31023\&t=ukJt9iBu9XkCZoOe-4)

## **Acceptance Criteria**

| Acceptance Criteria | Description                                                                                              |
| ------------------- | -------------------------------------------------------------------------------------------------------- |
| 1                   | On Submit, the application is forwarded to the next user in the workflow.                                |
| 2                   | The pop-up window is closed and the application page is refreshed. A toast success message is displayed. |
| 3                   | On Cancel closes the pop-up window. A toast cancel message is displayed.                                 |
| 4                   | Workflow state changes and the view estimate page refreshes based on the logged-in user role.            |
