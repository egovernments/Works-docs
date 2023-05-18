---
description: Muster Roll Web UI Tech Documentation
---

# Muster Roll Web

### Overview

This module helps in processing muster rolls through the workflow. Muster rolls created from SHG app end up in the web interface for workflow approval.\


This module has 5 associated screens :&#x20;



1. Inbox
2. Edit
3. View
4. Search



#### Module enablement configuration&#x20;

1. Set module code as "AttendenceMgmt" in Module.js of AttendenceMgmt  Module. Refer https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/tenant/citymodule.json

```json
{
            "module": "AttendenceMgmt",
            "code": "AttendenceMgmt",
            "active": true,
            "order": 4,
            "tenants": [
                {
                    "code": "statea.citytwo"
                },
                {
                    "code": "statea.citythree"
                },
                {
                    "code": "statea.cityone"
                }
            ]
}
```

2. Enable Module in App.js. Update the object ‘enabledModules’. Use the code “AttendenceMgmt”. This code should match with the code of the cityModule.json, mentioned above.

#### Role-action mapping

| S.No | API                                       | <p>Action ID</p><p><br></p> | Roles                                         |
| ---- | ----------------------------------------- | --------------------------- | --------------------------------------------- |
| 2    | /muster-roll/v1/\_search                  | 37                          | MUSTER\_ROLL\_VERIFIER,MUSTER\_ROLL\_APPROVER |
| 3    | /muster-roll/v1/\_update                  | 38                          | MUSTER\_ROLL\_VERIFIER,MUSTER\_ROLL\_APPROVER |
| 5    | /egov-pdf/download/musterRoll/muster-roll | 104                         | MUSTER\_ROLL\_APPROVER,MUSTER\_ROLL\_VERIFIER |
| 6    | /egov-hrms/employees/\_search             | 4                           | EMPLOYEE\_COMMON                              |
| 7    | /expense-calculator/v1/\_estimate         | 108                         | MUSTER\_ROLL\_APPROVER,MUSTER\_ROLL\_VERIFIER |
| 8    | /inbox/v2/\_search                        | 65                          | EMPLOYEE\_COMMON                              |

#### Sidebar configuration&#x20;

| S.No | Screen             | Navigation URL                                      | <p>LeftIcon Updates</p><p><br></p> | Roles                                         |
| ---- | ------------------ | --------------------------------------------------- | ---------------------------------- | --------------------------------------------- |
| 1    | Muster Roll Search | /works-ui/employee/attendencemgmt/search-attendance | dynamic:AttendanceIcon             | MUSTER\_ROLL\_APPROVER,MUSTER\_ROLL\_VERIFIER |
| 2    | Muster Roll Inbox  | /works-ui/employee/attendencemgmt/inbox             | dynamic:AttendanceIcon             | EMPLOYEE\_COMMON                              |
|      |                    |                                                     |                                    |                                               |

```json
{
      "id": 59,
      "name": "ATTENDENCEMGMT",
      "url": "url",
      "displayName": "ATTENDENCEMGMT Inbox",
      "orderNumber": 2,
      "parentModule": "",
      "enabled": true,
      "serviceCode": "ATTENDENCEMGMT",
      "code": "null",
      "navigationURL": "/works-ui/employee/attendencemgmt/inbox",
      "path": "4ATTENDENCEMGMT.Inbox",
      "leftIcon": "dynamic:AttendanceIcon"
}
```

#### Screen configuration&#x20;

| S.No | Screen | Configuration                                                                                                                                                                                                                                                                  |
| ---- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1    | Search | [https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/commonMuktaUiConfig/SearchContractConfig.json](https://github.com/egovernments/works-mdms-data/blob/c4be764c33afd9fbffacb631fb5343cb0f8c28eb/data/statea/commonMuktaUiConfig/SearchAttendanceWMSConfig.json) |
| 2    | Inbox  | [https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/commonMuktaUiConfig/InboxConfigContracts.json](https://github.com/egovernments/works-mdms-data/blob/9871717c016cf8a6311d752c9390e7ea00692077/data/statea/commonMuktaUiConfig/InboxMusterConfig.json)         |

### Localization Configuration and Modules

| TenantID | Module                   |
| -------- | ------------------------ |
| statea   | rainmaker-attendencemgmt |

### &#x20;Workflow Configuration

| UI Component Name | Business Service |
| ----------------- | ---------------- |
| WorkflowActions   | MR               |

### Customization

1\. API-based Data -&#x20;

* Total Wage Amount - Amount shown in view muster roll screen is fetched from expense-calculator

2**.  Inbox / Search Screen :**&#x20;

1. Please use the common utility “preProcessMDMSConfigInboxSearch”.
2. Pass the associated dependencies for the config.
3. The utility will return a config which will run through RenderFormFields.
4. Refer docs for Pre-Process config in Component comments.