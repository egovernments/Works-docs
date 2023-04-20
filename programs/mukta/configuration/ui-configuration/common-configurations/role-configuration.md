---
description: >-
  This Document says about the Roles Required to Perform action in Works
  Frontend App
---

# Role Configuration

| S.No | Module              | Actions                                                                                                                                     | Role Description             | Roles                                                             |
| ---- | ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------- | ----------------------------------------------------------------- |
| 1    | Project             | Create Search Modify                                                                                                                        | Project Creator              | PROJECT\_CREATOR                                                  |
| 2    | Project             | Search                                                                                                                                      | Project Viewer               | PROJECT\_VIEWER                                                   |
| 4    | Estimate            | Create Search Edit                                                                                                                          | Estimate Creator             | ESTIMATE\_CREATOR, PROJECT\_VIEWER                                |
| 5    | Estimate            | Search Update(Workflow)                                                                                                                     | Estimate Verifier            | ESTIMATE\_VERIFIER, PROJECT\_VIEWER                               |
| 6    | Estimate            | Search Update(Workflow)                                                                                                                     | Technical Sanctioner         | TECHNICAL\_SANCTIONER, PROJECT\_VIEWER                            |
| 7    | Estimate            | Search Update(Workflow)                                                                                                                     | Estimate Approver            | ESTIMATE\_APPROVER, PROJECT\_VIEWER                               |
| 8    | Estimate            | Search                                                                                                                                      | Estimate Viewer              | ESTIMATE\_VIEWER, PROJECT\_VIEWER                                 |
| 9    | Contract            | Create Search Edit                                                                                                                          | Work Order Creator           | WORK\_ORDER\_CREATOR,ESTIMATE\_VIEWER,PROJECT\_VIEWER,ORG\_VIEWER |
| 10   | Contract            | Search Update(Workflow)                                                                                                                     | Work Order Verifier          | WORK\_ORDER\_VIEWER,ESTIMATE\_VIEWER,PROJECT\_VIEWER              |
| 11   | Contract            | Search Update(Workflow)                                                                                                                     | WOrk Order Approver          | WORK\_ORDER\_APPROVER,ESTIMATE\_VIEWER,PROJECT\_VIEWER            |
| 13   | Muster Roll         | Search Update(Workflow) and Edit                                                                                                            | Muster Roll Verifier         | MUSTER\_ROLL\_VERIFIER,ORG\_VIEWER                                |
| 14   | Muster Roll         | Search Update(Workflow)                                                                                                                     | Muster Roll Approver         | MUSTER\_ROLL\_APPROVER,ORG\_VIEWER                                |
| 15   | Organization        | Create Update Search                                                                                                                        | MUKTA Admin                  | MUKTA\_ADMIN                                                      |
| 16   | Wage Seeker         | Update Search                                                                                                                               | MUKTA Admin                  | MUKTA\_ADMIN                                                      |
| 17   | Employee Management | Create Update Search                                                                                                                        | HRMS Admin                   | HRMS\_ADMIN                                                       |
| 18   | Mukta Dashboard     | Mukta Dashboard                                                                                                                             | Dashboard Viewer             | STADMIN                                                           |
| 19   | CBO Portal          | all actions of CBO portal                                                                                                                   | CBO Admin                    | ORG\_ADMIN                                                        |
| 20   | Billing             | Inbox Search View Create                                                                                                                    | Bill Creator                 | BILL\_CREATOR                                                     |
| 21   | Billing             | Inbox Search View                                                                                                                           | Bill Viewer                  | BILL\_VIEWER                                                      |
| 22   | Common              | This role will have all common access that employee should have like edit profile, get Workflow status ,Inbox Search, HRMS Employee Search, | Common Role For all employee | EMPLOYEE\_COMMON                                                  |
| 23   | Organization        | Search                                                                                                                                      | Org Viewer                   | ORG\_VIEWER                                                       |

