# Muster Roll - Approve

## **Context**

Provides users with the option to approve muster rolls.

## **Actors**

Employees.

## **Actions**

1. For the approval of the muster roll, the **Approve** action button is provided that captures the below-given details through a popup window on approval.
   * **Comments** - Text area - Non-mandatory
   * **Attach Supporting Document** - Document upload - Non-mandatory
   * **Approve** - Action Button
   * **Cancel** - Action Button
2. On Approve,
   * The muster roll is approved.
   * Approve pop-up window is closed, a toast success message is displayed and the view muster roll page is refreshed.
   * Workflow timelines are displayed accordingly.
   * Workflow state changes as given below.

| Role                 | From State           | To State | Status   |
| -------------------- | -------------------- | -------- | -------- |
| Muster Roll Approver | Pending for approval | Approved | Approved |

On cancel, a toast cancel message is displayed.

**Toast Success Message:** Muster roll has been approved successfully.

**Failure Message:** Approval of muster roll is failed.

**Toast Cancel Message:** Action has been cancelled.

## **Notification**

SMS to the CBO

Dear \<contactpersonname>, Muster roll \<musterrollID, amount \<amount> for the project \<project name>has been approved. Please login to MUKTASoft to see the details.

## **User Interface**

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=3359%3A43654\&t=cbmvGs4oGd2vjDTA-4)

## **Acceptance Criteria**

<table><thead><tr><th width="200">Acceptance Criteria</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>On approve - the muster roll workflow state changes accordingly.</td></tr><tr><td>2</td><td>a SMS notification is sent to the CBO</td></tr></tbody></table>
