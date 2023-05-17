# Estimate Reject Workflow

## **Scope**

Reject estimates

## **Actors**

Employees

## **Details**

### **Reject**

* To reject an estimate, action is provided to capture the below-given details and reject the estimate.
  1. **Comments** - This is a text and non-mandatory field. Users can add any remarks or comments. &#x20;
  2. **Attach Supporting Document** - Users can attach and upload the required documents.
  3. **Reject** - This is an action button.
  4. **Cancel** - This is an action button.
* On Reject,
  1. The pop-up window is closed and a toast reject message is displayed.
  2. The estimate page is refreshed. No actions are enabled for the rejected estimate.
  3. The estimate creator is informed about the rejection of the estimate.
  4. Workflow state changes as given below.

| Role                                           | From State           | To State | Status   |
| ---------------------------------------------- | -------------------- | -------- | -------- |
| **\<the role having access of reject action>** | **\<Current State>** | Rejected | Rejected |

* On cancel, the toast cancel message is displayed on the view estimate page.

{% hint style="success" %}
**Toast Success Message:**

The estimate is rejected successfully.

**Failure Message:**

Rejection of estimate failed.

**Toast Cancel Message:**

Action is cancelled.
{% endhint %}

## **Notification**

_SMS to the creator’s mobile_

Estimate \<estimate no.> for the project \<project name> of the location \<location> is rejected by \<username+designation>. For more details, log in to MUKTASoft to view the estimate details.

## **UI**

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=2014%3A30890\&t=vPbLKm950fDLjage-4)

## **Acceptance Criteria**

1. On reject, the estimate is rejected and the estimate status changes accordingly.
2. No further actions can be performed on a rejected estimate.
3. Notification is sent to the estimate creator.
4. Workflow state changes as mentioned above in the story.
