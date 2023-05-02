# Estimate Approve Workflow

## **Scope**

Approve estimates

## **Actors**

Estimate Approver

## **Details**

### **Approve**

* For the approval of an estimate, action **Approve** is provided and the below-given detail is captured in a pop-window on approval.
  1. **Comments** - This is a text and non-mandatory field. Users can add any remarks or comments. &#x20;
  2. **Attach Supporting Document** - This is a non-mandatory field. Users can attach and upload supporting documents.&#x20;
  3. **Approve** - This is an action button.
  4. **Cancel** - This is an action button.
* On Approve,
  1. The estimate is approved.
  2. Approve pop-up window is closed, a toast success message is displayed and the view estimate page is refreshed.
  3. Workflow state changes as given below.

| Role              | From State           | To State | Status   |
| ----------------- | -------------------- | -------- | -------- |
| Estimate Approver | Pending for approval | Approved | Approved |

* On cancel, the toast cancel message is displayed.

{% hint style="success" %}
**Toast Success Message:**

The estimate is administratively approved successfully.

**Failure Message:**

Approval of estimate failed.

**Toast Cancel Message:**

Action is cancelled.
{% endhint %}

## **Notification**

_SMS to the estimate creator_

Estimate \<estimate no.> for the project \<projectname> of the location \<location> is approved. For more details log in to MUKTASoft to view the estimate details.

## **UI**

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=2014%3A31246\&t=vPbLKm950fDLjage-4)

## **Acceptance Criteria**

| Acceptance Criteria | Description                                                  |
| ------------------- | ------------------------------------------------------------ |
| 1                   | On approval, estimate workflow state changes accordingly.    |
| 2                   | On approval, a notification is sent to the estimate creator. |
