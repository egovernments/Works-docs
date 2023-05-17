# Estimate Send Back To Originator Workflow

## Scope

Send back estimates to the originator for necessary action.

## Actors

Employees

## Details

### **Send Back To Originator**

* This allows the user to send the estimate back to the originator’s inbox for any correction required. Below given detail is captured.
  1. **Comments** - This is a text area and non-mandatory field. Users can _a_dd any remarks/ instructions to be passed to the originator of the estimate_._
  2. **Attach Supporting Document** - This is a document upload field and non-mandatory. Users can attach and upload supporting documents while sending the estimate back to the originator.
  3. **Send Back** - This is an action button.
  4. **Cancel** - This is an action button.
* On **Send Back**
  1. The pop-up window is closed and a toast success message is displayed.
  2. The view estimate page is refreshed and the actions menu is loaded according to the role the logged-in user has.
  3. The estimate is moved to the creator’s inbox.
  4. The Edit Estimate option is available to the **Estimate Creator** to edit the estimate and attached the new documents files and submit it.
  5. Workflow state changes as given below.

| Role                                                  | From State            | To State               | Status    |
| ----------------------------------------------------- | --------------------- | ---------------------- | --------- |
| **\<roles having access to send back to originator>** | **\<Current Status>** | Pending for correction | Sent Back |

* Clicking on cancel closes the pop-up window and the toast cancel message is displayed on the view estimate page.

{% hint style="info" %}
**Toast Success Message:**

The estimate is sent back to the creator successfully.

**Failure Message:**

Sending back of estimate failed.

**Toast Cancel Message:**

Action is cancelled.
{% endhint %}

## **Notification**

_Not applicable._

## **UI**

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=2014%3A30712\&t=vPbLKm950fDLjage-4)

## **Acceptance Criteria**

| Acceptance Criteria | Description                                                             |
| ------------------- | ----------------------------------------------------------------------- |
| 1                   | The estimate is moved to Estimate Creator’s inbox.                      |
| 2                   | Estimate Creator- Edit Estimate action is enabled to edit the estimate. |
| 3                   | Workflow state changes as mentioned in the ticket.                      |
