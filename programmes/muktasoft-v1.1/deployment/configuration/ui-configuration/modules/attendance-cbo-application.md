# Attendance (CBO Application)

## Overview

This module helps in logging the attendance of each individual in a register and creating the muster roll for a particular week.

ROLE: ORG\_ADMIN

This module has 2 associated screens: View Register Inbox Track Attendance Table Screen

## MDMS Configurations

<table><thead><tr><th width="103.99999999999997">S.No.</th><th>Data</th><th>MDMS Link</th></tr></thead><tbody><tr><td>1</td><td>AttendanceHours</td><td><a href="https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/AttendanceHours.json">Attendance Hours</a></td></tr><tr><td><p></p><p>2<br></p></td><td>WageSeekerSkills</td><td><a href="https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/WageSeekerSkills.json">Wage Seeker Skills</a></td></tr><tr><td>3</td><td>CBOMusterSubmission</td><td><a href="https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/commonUiConfig/CBOMusterSubmission.json">Muster Roll Submission</a></td></tr></tbody></table>

## User Actions

This page involves several actions:&#x20;

1. The CBO Admin selects a date range using the Date Picker.
2. Upon selecting a date, the entire week is automatically chosen.
3. After selecting the week, by clicking "Apply," the pre-saved attendance log for that week becomes visible.
4. The user can then modify the attendance log for each individual and save it as a draft using the "Save as Draft" button.
5. The user can also submit the muster roll. Upon submission, the user will be prompted to enter skills for each individual.
6. After entering skills, the user can submit the muster roll for that specific week.

Validations:

* If no date range is selected or cleared, attempting to use the "Save as Draft" button will display an error, prompting the user to select a date range.
* The ability to submit the muster roll depends on the CBOMusterSubmission MDMS Config.

```
isEndOfWeek && selectedDateRange!.endDate > DateTime.now().millisecondsSinceEpoch


code": "END_OF_WEEK",            "value": "end of week",            "active": false


```

Depending on the value of END\_OF\_WEEK:

1. If END\_OF\_WEEK is false, users can create the muster roll on any day of the week.
2. If END\_OF\_WEEK is true, users can submit the muster roll only on or after the last day of the week (Sunday).

If an existing muster roll for the selected range is in a workflow state, the Track Attendance page will be a view-only page. Otherwise, users will be able to log attendance and submit the muster roll.

The options for marking attendance are determined by the Attendance Hours list:

* If the list contains two options, users can mark attendance as Full Day or Absent.
* If the list has more than two options, users can mark attendance as Full Day, Half Day, or Absent.

### API Details

<table><thead><tr><th width="90">S.No.</th><th>API</th><th width="197">Body/Query Params</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td><p>attendance/v1/_search</p><p><br></p></td><td><p>{</p><p>"tenantId":””,</p><p> "ids":””</p><p>}</p><p><br></p></td><td><p>Gives the list of registers linked to the org </p><p><br></p></td></tr><tr><td>2</td><td><p>muster-roll/v1/_estimate</p><p><br></p></td><td><p>{</p><p> "musterRoll": {</p><p>   "tenantId":,</p><p>   "registerId":,</p><p>   "startDate":,</p><p>   "endDate": </p><p> }</p><p>}</p><p><br></p></td><td>To get the attendance log for the selected Date range</td></tr><tr><td>3</td><td><p>attendance/log/v1/_create</p><p><br></p></td><td><p>{"attendance": []}</p><p><br></p></td><td>To log the attendance of the individuals for the week</td></tr><tr><td>4</td><td><p>attendance/log/v1/_update</p><p><br></p></td><td><br></td><td>To update the attendance log of the individuals for Sent Back To CBO Muster Rolls</td></tr><tr><td>5</td><td><p>muster-roll/v1/_search</p><p><br></p></td><td><br></td><td>To check if any existing muster rolls present for the selected week</td></tr><tr><td>6</td><td><p>egov-workflow-v2/egov-wf/businessservice/_search</p><p><br></p></td><td><p>{</p><p> "tenantId":,</p><p> "businessServices": “musterRollId”,</p><p>}</p><p><br></p></td><td>To check the workflow status of the Muster Roll</td></tr></tbody></table>

### Sidebar Configuration&#x20;

\<details>

### **DIGIT Components & Custom Components Used**&#x20;

<table><thead><tr><th width="92">S.No.</th><th>Component</th><th>Path</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td><p></p><p>DigitTable<br><br></p></td><td><a href="https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works_shg_app/lib/widgets/molecules/digit_table.dart">DigitTable.dart</a></td><td>Custom Table with fixed first column and other columns scrollable</td></tr><tr><td>2</td><td><p>DropDownDialog</p><p><br></p></td><td><a href="https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works_shg_app/lib/widgets/atoms/table_dropdown.dart">DropDownDialog</a></td><td>A dialog with dropdown options</td></tr><tr><td>3</td><td><p>DateRangePicker</p><p><br></p></td><td><a href="https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works_shg_app/lib/widgets/atoms/date_range_picker.dart">DateRangePicker</a></td><td>A custom Date Range picker to select a range of the month / year</td></tr><tr><td>4</td><td><p>DigitElevatedButton</p><p><br></p></td><td><a href="https://github.com/egovernments/health-campaign-field-worker-app/blob/main-parallel/packages/digit_components/lib/widgets/digit_elevated_button.dart">DigitElevatedButton</a></td><td>An Elevated Submit Button </td></tr><tr><td>6</td><td><p>WorkDetailsCard</p><p><br></p></td><td><a href="https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works_shg_app/lib/widgets/WorkDetailsCard.dart">DetailsCard</a></td><td>Details Card based on DIGIT Figma design</td></tr></tbody></table>

### Localization Configuration & Modules

<table><thead><tr><th width="227">TenantID</th><th>Module</th></tr></thead><tbody><tr><td>pg</td><td>rainmaker-common</td></tr><tr><td>pg</td><td>rainmaker-attendance</td></tr><tr><td>pg</td><td>rainmaker-common-masters</td></tr><tr><td>pg</td><td>rainmaker-workflow</td></tr><tr><td>pg.citya</td><td>rainmaker-pg.citya</td></tr></tbody></table>

## Reference Files/Links&#x20;

1. Blocs:&#x20;
   * [Search Registers](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/blocs/attendance/search\_projects/search\_projects.dart)
   * [Search Individual Register](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/blocs/attendance/search\_projects/search\_individual\_project.dart)
   * [Attendance Create Log Bloc](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/blocs/attendance/attendance\_create\_log.dart)
   * [Muster Search With From and To Date Bloc](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/blocs/muster\_rolls/from\_to\_date\_search\_muster\_roll.dart)
   * [Get Muster Roll Workflow Bloc](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/blocs/muster\_rolls/get\_muster\_workflow.dart)
   * [Muster Get Attendance Log Bloc](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/blocs/muster\_rolls/muster\_roll\_estimate.dart)
   * [Create and Update Muster Roll Bloc](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/blocs/muster\_rolls/create\_muster.dart)
2. Models:&#x20;
   * [Attendance register Model](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/models/attendance/attendance\_registry\_model.dart)
   * [Estimate Muster Roll Model](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/models/muster\_rolls/estimate\_muster\_roll\_model.dart)
   * [Search Muster Roll Model](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/models/muster\_rolls/muster\_roll\_model.dart)
   * [Muster Workflow model](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/models/muster\_rolls/muster\_workflow\_model.dart)
3. Repositories:&#x20;
   * [Attendance Register Repo](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/data/repositories/attendence\_repository/attendence\_register.dart)
   * [Muster Roll Repo](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/data/repositories/muster\_roll\_repository/muster\_roll.dart)
   * [Workflow Repo](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/data/repositories/workflow\_repository/workflow.dart)
4. Screens:
   * [Register Inbox Screen](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/pages/trackAttendance/track-attendance\_inbox.dart)
   * [Track Attendance Screen](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/works\_shg\_app/lib/pages/track\_attendance.dart)
