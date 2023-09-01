# Muster Rolls - Send Back To CBO

## **Context**

Provide users with the option to send back muster rolls to CBO for any corrections or specific action.

## **Actors**

Employees.

## Actions

1. This feature is provided to send the muster roll back to CBO for any correction required. Below given details are captured.
   * **Comments** - Text area - Non-mandatory - _It allows users to add any remarks/ instructions to be passed to the originator (CBO) of the muster roll._
   * **Attach Supporting Document** - Document upload - Non-mandatory - _In case any documents are to be attached while sending the muster roll back to CBO._
   * **Send Back** - Action Button
   * **Cancel** - Action Button
2. On **Send Back -**
   * The pop-up window is closed and a toast success message is displayed.
   * The view muster roll page is refreshed and the actions menu is loaded according to the role the logged-in user has.
   * The muster roll is placed into the muster roll creator/CBO.
   * The ‘Edit Muster Roll’ option is provided to **CBO** to edit the muster roll and attached the new documents files and Re-submit it.
   * Workflow state changes as given below.

| Role                                                  | From State            | To State               | Status    |
| ----------------------------------------------------- | --------------------- | ---------------------- | --------- |
| **\<roles having access to send back to originator>** | **\<Current Status>** | Pending for correction | Sent Back |

3\. On cancel, the pop-up window is closed, toast cancel message is displayed on the view muster roll page.

**Toast Success Message:** Muster roll has been sent back to the CBO successfully.

**Failure Message:** Sending back of muster roll is failed.

**Toast Cancel Message:** Action has been cancelled.

## **Notification**

_Notification is sent to CBO_

Dear \<contactpersonname>, Muster roll \<musterrollID for the project \<project name>has been sent back for correction. Please login to MUKTASoft to see the details.

## **User Interface**

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=3359%3A42709\&t=cbmvGs4oGd2vjDTA-4)

## **Acceptance Criteria**

<table><thead><tr><th width="215">Acceptance Criteria</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>The muster roll is moved to CBO.</td></tr><tr><td>2</td><td>CBO- <strong>Edit</strong> action is enabled to edit the muster roll.</td></tr><tr><td>3</td><td>Workflow state changes as mentioned in the ticket.</td></tr></tbody></table>

