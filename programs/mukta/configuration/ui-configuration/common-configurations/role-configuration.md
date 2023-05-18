---
description: >-
  This Document says about the Roles Required to Perform action in Works
  Frontend App
---

# Role Configuration

| S.No | Module              | Actions                                                                                                                                     | Role Description             | Roles                                                                           |
| ---- | ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------- | ------------------------------------------------------------------------------- |
| 1    | Project             | Create Search Modify                                                                                                                        | Project Creator              | <p>PROJECT_CREATOR,<br>ESTIMATE_VIEWER</p>                                      |
| 2    | Project             | Search                                                                                                                                      | Project Viewer               | PROJECT\_VIEWER                                                                 |
| 4    | Estimate            | Create Search Edit                                                                                                                          | Estimate Creator             | <p>ESTIMATE_CREATOR,<br>PROJECT_VIEWER]</p>                                     |
| 5    | Estimate            | Search Update(Workflow)                                                                                                                     | Estimate Verifier            | ESTIMATE\_VERIFIER, PROJECT\_VIEWER                                             |
| 6    | Estimate            | Search Update(Workflow)                                                                                                                     | Technical Sanctioner         | TECHNICAL\_SANCTIONER, PROJECT\_VIEWER                                          |
| 7    | Estimate            | Search Update(Workflow)                                                                                                                     | Estimate Approver            | ESTIMATE\_APPROVER, PROJECT\_VIEWER                                             |
| 8    | Estimate            | Search                                                                                                                                      | Estimate Viewer              | ESTIMATE\_VIEWER, PROJECT\_VIEWER                                               |
| 9    | Contract            | Create Search Edit                                                                                                                          | Work Order Creator           | <p>WORK_ORDER_CREATOR,<br>ESTIMATE_VIEWER,<br>PROJECT_VIEWER,<br>ORG_VIEWER</p> |
| 10   | Contract            | Search Update(Workflow)                                                                                                                     | Work Order Verifier          | <p>WORK_ORDER_VERIFIER,<br>ESTIMATE_VIEWER,<br>PROJECT_VIEWER</p>               |
| 11   | Contract            | Search Update(Workflow)                                                                                                                     | WOrk Order Approver          | <p>WORK_ORDER_APPROVER,<br>ESTIMATE_VIEWER,<br>PROJECT_VIEWER</p>               |
| 13   | Muster Roll         | Search Update(Workflow) and Edit                                                                                                            | Muster Roll Verifier         | <p>MUSTER_ROLL_VERIFIER,<br>ORG_VIEWER</p>                                      |
| 14   | Muster Roll         | Search Update(Workflow)                                                                                                                     | Muster Roll Approver         | MUSTER\_ROLL\_APPROVER,ORG\_VIEWER                                              |
| 15   | Organization        | Create Update Search                                                                                                                        | MUKTA Admin                  | MUKTA\_ADMIN                                                                    |
| 16   | Wage Seeker         | Update Search                                                                                                                               | MUKTA Admin                  | MUKTA\_ADMIN                                                                    |
| 17   | Employee Management | Create Update Search                                                                                                                        | HRMS Admin                   | HRMS\_ADMIN                                                                     |
| 18   | Mukta Dashboard     | Mukta Dashboard                                                                                                                             | Dashboard Viewer             | STADMIN                                                                         |
| 19   | CBO Portal          | all actions of CBO portal                                                                                                                   | CBO Admin                    | ORG\_ADMIN                                                                      |
| 20   | Billing             | Inbox Search update **Create**                                                                                                              | Bill Creator                 | BILL\_CREATOR,WORK\_ORDER\_VIEWER,ORG\_VIEWER                                   |
| 21   | Billing             | <p>Inbox Search View,<br>Update</p>                                                                                                         | Bill Viewer                  | BILL\_VIEWER                                                                    |
| 22   | Common              | This role will have all common access that employee should have like edit profile, get Workflow status ,Inbox Search, HRMS Employee Search, | Common Role For all employee | EMPLOYEE\_COMMON                                                                |
| 23   | Organization        | Search                                                                                                                                      | Org Viewer                   | ORG\_VIEWER                                                                     |
| 24   | Expense             | Supervision Bill Generator                                                                                                                  | CronJob                      | SYSTEM                                                                          |
| 25   | Payment             | <p>Payment Advise Creation ,<br>Download </p>                                                                                               | Bill Accountant              | BILL\_ACCOUNTANT,CONTRACT\_VIEWER,ORG\_VIEWER,BILL\_VIEWER                      |
| 26   | Contract            | Search                                                                                                                                      | Contract Viewer              | WORK\_ORDER\_VIEWER                                                             |
| 27   | Billing             | Search, View , Update                                                                                                                       | BILL Verifier                | BILL\_VERIFIER,WORK\_ORDER\_VIEWER,ORG\_VIEWER                                  |
| 28   | BILL\_VIEWER        | BILL\_VIEWER                                                                                                                                | BILL\_VIEWER                 | BILL\_APPROVER,WORK\_ORDER\_VIEWER,ORG\_VIEWER                                  |

**Note:**

1. Employee Common (**EMPLOYEE\_COMMON**) role is to be added for all the users since it provides them with all employees' common actions mentioned as in table SNo 22.
2. Bill Accountant and Mukta admin should not be added for any Employee who performs an action in Muster, Bill, Project,Estimate, or  Contract Modules.
3. There are few restricted roles which should not be given to any Employees

<pre><code><strong> ["CBO_ADMIN","STADMIN","ORG_ADMIN","ORG_STAFF","SYSTEM"] 
</strong><strong>
</strong></code></pre>

