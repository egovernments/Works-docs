# Create/ Submit Work Order

### **Submit**

1. Hence for **Work Order Creator**, **On** **Submit** pop-up window is opened to capture below given details.
   1. **Assignee name**- Drop-down - Non Mandatory -  _The next user in the workflow i.e. work order verifier hence the employees having the role **Work\_Order\_Verifier** are displayed in drop-down with the Name and Designation. E.g. Suresh K working as Junior Assistant Executive Engineer and have the role of work order verifier will be displayed ‘**Suresh K - Assistant Executive Engineer**’._
   2. **Comments** - Text area - Non Mandatory -  _In case any comments to be added._
   3. **Forward**- _Action Button_
   4. **Cancel** - _Action Button_
2. On **Forward**,
   1. Pop-up window is closed, toast success message is displayed and view work order page is refreshed.
   2. Action menu is loaded according to the role-action mapping of the current logged-in user.
   3. Work order is forwarded to next user in the workflow and shown in its inbox.
   4. The workflow state changes accordingly and timelines shows the current state of estimate.
   5. Work order is removed from the current logged-in user’s inbox.

| **Action**         | **Role**           | **From State**         | **To State**             | Status       |
| ------------------ | ------------------ | ---------------------- | ------------------------ | ------------ |
| Submit/ Forward    | Work Order Creator |                        | Pending for verification | Submitted    |
| Re-submit/ Forward | Work Order Creator | Pending for correction | Pending for verification | Re-submitted |

1. On cancel, pop-up window is closed, toast cancel message is displayed on the view work order page.

**Toast Success Message:**

Work order has been forwarded successfully.

**Failure Message:**

Forward of work order is failed.

**Toast Cancel Message:**

Action has been cancelled.

**Validation**

_Not applicable._

**Notification**

_Not applicable._

## **User Interface**

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=1835%3A32629\&t=wWexCFFY2p7fxq5l-4)

## **Acceptance Criteria**

1. On submission, the application is forwarded to the next user in the flow.
2. The pop-up window gets closed and the application page is refreshed. A toast success message is displayed.
3. On cancel pop-up window is closed. A toast cancel message is displayed.
4. Workflow states changes, and based on role existing user has view work order page refreshes.
