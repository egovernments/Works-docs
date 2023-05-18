---
description: <WORK IN PROGRESS>
---

# MusterRoll

### Overview

This module helps in viewing and updating the muster rolls.

ROLE: ORG\_ADMIN

This module has 2 associated screens :&#x20;

1. View Muster Rolls Inbox&#x20;
2. Muster Roll Table Screen

### MDMS Configurations

| S.No.               | Data             | MDMS Link                                                                                                                              |
| ------------------- | ---------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| 1                   | AttendanceHours  | [Attendance Hours](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/AttendanceHours.json)               |
| <p>2</p><p><br></p> | WageSeekerSkills | [Wage Seeker Skills](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/WageSeekerSkills.json)            |
| 3                   | Sent Back to CBO | [Sent Back to CBO Code](https://github.com/egovernments/works-mdms-data/blob/UAT/data/statea/commonUiConfig/CBOMusterInboxConfig.json) |

Based on the business workflow state set for Muster Roll ( Sent BAck for Correction) in respective environments, Add the corresponding code in [Sent Back to CBO Code](https://github.com/egovernments/works-mdms-data/blob/UAT/data/statea/commonUiConfig/CBOMusterInboxConfig.json) MDMS



#### User actions&#x20;

On this page, the following actions need to be performed: If the muster roll is in workflow, User can only view the muster roll, If the muster roll is sent back to CBO,then user can edit the attendance and resubmit the muster roll,\


### Validations

* If Muster Roll is in Workflow, The screen will only be a view page and Save as Draft and Re-Submit button will not be shown in the screen
* Based on the [Attendance Hours](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/AttendanceHours.json) list, users will be allowed to mark the attendance as Full Day, Half Day, or absent. If the list is of length 2, users will be allowed to mark only Full and Absent, Else, users can mark halfday as well.\


#### API Details

| 1 | <p>muster-roll/v1/_estimate</p><p><br></p>                         | <p>{</p><p> "musterRoll": {</p><p>   "tenantId":,</p><p>   "registerId":,</p><p>   "startDate":,</p><p>   "endDate": </p><p> }</p><p>}</p><p><br></p> | To get the attendance log for the selected Date range                             |
| - | ------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| 3 | <p>attendance/log/v1/_create</p><p><br></p>                        | <p>{"attendance": []}</p><p><br></p>                                                                                                                  | To log the attendance of the individuals for the week                             |
| 4 | <p>attendance/log/v1/_update</p><p><br></p>                        | <p><br></p>                                                                                                                                           | To update the attendance log of the individuals for Sent Back To CBO Muster Rolls |
| 5 | <p>muster-roll/v1/_search</p><p><br></p>                           | <p><br></p>                                                                                                                                           | To check if any existing muster rolls present for the selected week               |
| 6 | <p>egov-workflow-v2/egov-wf/businessservice/_search</p><p><br></p> | <p>{</p><p> "tenantId":,</p><p> "businessServices": “musterRollId”,</p><p>}</p><p><br></p>                                                            | To check the workflow status of the Muster Roll                                   |

#### DIGIT Components and Custom Components Used&#x20;

| S.No | Component                             | Path                                                                                                                                                                           | Description                                                               |
| ---- | ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------- |
| 1    | <p>DigitTable</p><p><br><br></p>      | [DigitTable.dart](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/widgets/molecules/digit\_table.dart)                                    | Custom Table with fixed first column and other columns scrollable         |
| 2    | <p>DropDownDialog</p><p><br></p>      | [DropDownDialog](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/widgets/atoms/table\_dropdown.dart)                                      | A dialog with dropdown options                                            |
| 3    | <p>DateRangePicker</p><p><br></p>     | [DateRangePicker](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/widgets/atoms/date\_range\_picker.dart)                                 | A custom Date Range picker to select a range of the month / year          |
| 4    | <p>DigitElevatedButton</p><p><br></p> | [DigitElevatedButton](https://github.com/egovernments/health-campaign-field-worker-app/blob/main-parallel/packages/digit\_components/lib/widgets/digit\_elevated\_button.dart) | An Elevated Submit Button                                                 |
| 6    | <p>WorkDetailsCard</p><p><br></p>     | [DetailsCard](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/widgets/WorkDetailsCard.dart)                                               | Details Card based on DIGIT Figma design                                  |
| 7    | DigitTimeLine                         | [DigitTimeline](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/widgets/atoms/digit\_timeline.dart)                                       | WorkFlow TimeLine component viewing Workflow state, And Assignees Details |

### Localization Configuration and Modules

| TenantID | Module                   |
| -------- | ------------------------ |
| pg       | rainmaker-common         |
| pg       | rainmaker-muster         |
| pg       | rainmaker-common-masters |
| pg       | rainmaker-workflow       |
| pg.citya | rainmaker-pg.citya       |

### Reference Files

1. Blocs :&#x20;

* [Attendance Create Log Bloc](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/blocs/attendance/attendance\_create\_log.dart)
* [Search Muster Rolls in a Tenanat](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/blocs/muster\_rolls/search\_muster\_roll.dart)
* [Muster Search From Muster ID Bloc](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/blocs/muster\_rolls/search\_individual\_muster\_roll.dart)
* [Get Muster Roll Workflow Bloc](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/blocs/muster\_rolls/get\_muster\_workflow.dart)
* [Muster Get Attendance Log Bloc](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/blocs/muster\_rolls/muster\_roll\_estimate.dart)
* [Create and Update Muster Roll Bloc](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/blocs/muster\_rolls/create\_muster.dart)

2. Models :

* [Estimate Muster Roll Model](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/models/muster\_rolls/estimate\_muster\_roll\_model.dart)
* [Search Muster Roll Model](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/models/muster\_rolls/muster\_roll\_model.dart)
* [Muster Workflow model](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/models/muster\_rolls/muster\_workflow\_model.dart)

3. Repositories:&#x20;

* [Attendance Register Repo](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/data/repositories/attendence\_repository/attendence\_register.dart)
* [Muster Roll Repo](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/data/repositories/muster\_roll\_repository/muster\_roll.dart)
* [Workflow Repo](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/data/repositories/workflow\_repository/workflow.dart)

4. Screens

* [Muster Inbox Screen](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/pages/view\_muster\_rolls.dart)
* [Muster Roll View and Edit Table](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/pages/shg\_inbox.dart)
