# Estimate Technical Sanction

## **Scope**

Technical sanction of estimates.

## **Actors**

Employees

## **Details**

### **Technical Sanction**

* To technically sanction the estimate the action Technical Sanction is enabled in the action menu and a pop-up window is opened with the following details.
  1. **Assignee name**- This is a drop-down field and non-mandatory. The drop-down displays employees having the role of **Estimate Approver** with their names and the designation. For instance, Rakesh K works as an Executive Officer and has the role of Estimate Approver displayed as Rakesh K - Estimate Approver. &#x20;
  2. **Comments** - This is a text and non-mandatory field. Users can add any remarks or comments.  &#x20;
  3. **Attach Supporting Document** - This is a non-mandatory field. Users can attach and upload supporting documents.&#x20;
  4. **Technical Sanction**- This is an action button.
  5. **Cancel** - This is an action button.
* On technical sanction,
  1. The pop-up window is closed, a toast success message is displayed and the view estimate page is refreshed.
  2. The action menu is loaded according to the role-action mapping of the current user.
  3. The application is forwarded to the next user in the workflow and the workflow state changes.
  4. Timelines show the current state of the estimate in the workflow.

| Role               | From State                     | To State             | Status                 |
| ------------------ | ------------------------------ | -------------------- | ---------------------- |
| Technical Sanction | Pending for technical sanction | Pending for approval | Technically Sanctioned |

* Clicking on cancel closes the pop-up window and a toast cancel message is displayed on the view estimate page.

{% hint style="success" %}
**Toast Success Message:**

The estimate is technically sanctioned successfully.

**Failure Message:**

Technical sanctioning of estimated failed.

**Toast Cancel Message:**

Action is cancelled.
{% endhint %}

## **Notification**

Not applicable.

## **UI**

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=2014%3A31068\&t=vPbLKm950fDLjage-4)

## **Acceptance Criteria**

| Acceptance Criteria |                                                                                                              |
| ------------------- | ------------------------------------------------------------------------------------------------------------ |
| 1                   | On technical sanction, the estimate is forwarded to the next user in the workflow                            |
| 2                   | The pop-up window is closed, a toast success message is displayed, and the estimate page is refreshed        |
| 3                   | The View Estimate page is refreshed based on the changes in the workflow status and the logged-in user role. |
| 4                   | Clicking on cancel closes the pop-up window. A toast cancel message is displayed.                            |
