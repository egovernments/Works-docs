# Estimate Verify & Forward Workflow

## **Scope**

Verify and forward estimates

## **Actors**

Estimate Verifier

## **Details**

### **Verify & Forward**

* To verify and forward the estimate to the next workflow user - the verify and forward action is provided with a pop-up window to capture the below-given details.
  1. **Assignee name** - This field is drop-down and non-mandatory.  The drop-down displays employees having the role of **Technical Sanctioner** with their names and the designation. For instance, Mahesh K works as a Municipal Engineer and has the role of technical sanctioner displayed as Mahesh K - Municipal Engineer.
  2. **Comments** - This field is drop-down and non-mandatory. This field allows the addition of any remarks or comments. &#x20;
  3. **Attach Supporting Document** - This is a non-mandatory field. Users can attach and upload supporting documents.&#x20;
  4. **Verify and Forward** - This is an action button.
  5. **Cancel** - This is an action button_._
* On **Verify and Forward**,
  1. The pop-up window is closed, a toast success message is displayed and the view estimate page is refreshed.
  2. The action menu is loaded according to the role-action mapping of the currently logged-in user.
  3. The estimate is forwarded to the next user in the workflow and displayed in their inbox.
  4. The workflow state changes accordingly and timelines show the current state of the estimate.
  5. The estimate is removed from the currently logged-in user’s inbox.

| Role              | From State               | To State                       | Status   |
| ----------------- | ------------------------ | ------------------------------ | -------- |
| Estimate Verifier | Pending for verification | Pending for technical sanction | Verified |

* On cancel, the pop-up window is closed and the toast cancel message is displayed on the view estimate page.

{% hint style="success" %}
**Toast Success Message:**

The estimate is verified and forwarded successfully.

**Failure Message:**

Verification of estimate failed.

**Toast Cancel Message:**

Action is cancelled.
{% endhint %}

## **Notification**

Not applicable.

## **UI**

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=2014%3A30157\&t=vPbLKm950fDLjage-4)

## **Acceptance Criteria**

| Acceptance Criteria | Description                                                                                                  |
| ------------------- | ------------------------------------------------------------------------------------------------------------ |
| 1                   | Clicking on Verify and Forward moves the estimate to the next user in the flow                               |
| 2                   | The pop-up window is closed and the view estimate page is refreshed. Toast success message is displayed.     |
| 3                   | The View Estimate page is refreshed based on the changes in the workflow status and the existing user role.  |
| 4                   | On cancel the pop-up window is closed. A toast cancel message is displayed.                                  |
