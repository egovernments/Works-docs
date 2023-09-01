---
description: >-
  User should be able to create → Forward (or) check → Forward/Reject a
  contract.
---

# Contract Workflow

1. Contracts will be created by **contract\_creator**, Checked by **contract\_checker** and approver by **contract\_approver**. This will be linear workflow and rejected contracts at any point in lifecycle will come into inbox of creator.
2. Contracts counters on Home Screen will increase/decrease as the inbox items for checkers and approvers increase/decrease respectively.
3. Actions menu on view page of Work orders should have actions to be taken by respective Actors
4. For Work Orders (Non-Departmental)
   1. WO is created by JE, Approved by ME. Checkers in between depends on Implementation and can vary from ULB to ULB
   2. Approved WO goes into Work Order inbox of respective organisation.
   3. Organisation can either accept or reject.
   4. Rejected Work Orders will come back into inbox of creator and cycle repeats
5. For Work Orders (Departmental)
   1. WO is created by JE, Approved by ME. Checkers in between depends on Implementation and can vary from ULB to ULB
   2. Approved WO goes into Work Order inbox of respective organisation.
   3. Organisation can either accept or reject.
   4. Rejected Work Orders will come back into inbox of creator and cycle repeats
6. For Purchase Orders
   1. PO is created by JE, Approved by ME. Checkers in between depends on Implementation and can vary from ULB to ULB. An Infra expert can be assigned to check PO.
   2. Approved PO goes as SMS to registered Vendor
   3. Vendor can click on the PO link & download approved PO’s PDF.

**Once the Estimate are created they will move to the respective checker and approver's inbox as pending items.**

<figure><img src="../../../../../../.gitbook/assets/Screenshot from 2022-12-06 13-27-24.png" alt=""><figcaption><p>Contract Proposal InboxView</p></figcaption></figure>

#### View Contract

* From Contract Proposal Inbox, User can come into Contract View Screen where Details of Contract present while creating the contract and Workflow history will be displayed.
* User can take necessary actions by clicking on Actions Menu.

<figure><img src="../../../../../../.gitbook/assets/image (12) (1).png" alt=""><figcaption><p>View Contract Screen</p></figcaption></figure>

### Taking Actions on Contract

An Action bar on the View Contract Screen shows the list of actions&#x20;

1. Forward Contract
2. Reject Contract
3. Modify Contract
4. Approve Contract

When any action is clicked respective popup is rendered according to the selected action. We have created three popups for approve, forward and reject. They are shown below

<div align="left">

<figure><img src="../../../../../../.gitbook/assets/image (32) (1).png" alt=""><figcaption><p>Forward Processing Modal</p></figcaption></figure>

</div>

<figure><img src="../../../../../../.gitbook/assets/Screenshot from 2022-12-06 13-34-04.png" alt=""><figcaption><p>Reject Processing Modal</p></figcaption></figure>

<figure><img src="../../../../../../.gitbook/assets/Screenshot from 2022-12-06 13-34-33.png" alt=""><figcaption><p>Approve Estimate Modal</p></figcaption></figure>

When these popups are submitted, Update Contract API is called containing the relevant updates in the workflow object contained in the request body. The contract service internally calls the workflow service and updates the status of the application.

#### Response Screen

Upon successful update, a response screen is displayed as follows

<figure><img src="../../../../../../.gitbook/assets/image (16) (1).png" alt=""><figcaption><p>Contract Updation Acknowledgement Screen</p></figcaption></figure>
