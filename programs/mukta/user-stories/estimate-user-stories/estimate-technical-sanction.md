# Estimate Technical Sanction

### **Technical Sanction**

1. To technically sanction the estimate the action ‘Technical Sanction’ is enabled in action menu and a pop-up window is opened with following details.
   1. **Assignee name**- Drop-down - Non Mandatory -  _The next user in the workflow i.e. **Estimate\_Approver**, hence the employees having the role Estimate\_Approver are displayed in drop-down with the name and the designation. E.g. Rakesh K working as Executive Officer and have the role of Estimate Approver will be displayed ‘RakeshK - Executive Officer’._
   2. **Comments** - Text area - Non Mandatory -  _In case any comments to be added._
   3. **Attach Supporting Document** - Non Mandatory - _Any document to be uploaded as supporting document._
   4. **Technical Sanction**- _Action Button_
   5. **Cancel** - _Action Button_
2. On technical sanction,
   1. Pop-up window is closed, toast success message is displayed and view estimate page is refreshed.
   2. Action menu is loaded according to the role-action mapping of the current user.
   3. Application is forwarded to next user in the workflow and the workflow state changes.
   4. Timelines shows the current state of estimate in the workflow.

| **Role**           | **From State**                 | **To State**         | **Status**             |
| ------------------ | ------------------------------ | -------------------- | ---------------------- |
| Technical Sanction | Pending for technical sanction | Pending for approval | Technically Sanctioned |

* Clicking on cancel closes the pop-up window and a toast cancel message is displayed on the view estimate page.

{% hint style="info" %}
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
