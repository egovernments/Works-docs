---
description: Workorder/Contract UI Tech Documentation
---

# Workorder

### Overview

This module helps in creating a work order for the Project based on the estimates designed.  This enables in deciding the Tendering, Quotation and Nomination. Based on the nomination, CBO is being mapped to the respective Work Order.\


This module has 5 associated screens :&#x20;

1. Create
2. Search
3. Modify
4. View
5. Inbox

### MDMS Configurations

| S.No. | Data            | MDMS Link                                                                                                                                                                                    |
| ----- | --------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1     | Role Of CBO     | [https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/ContractCBORoles.json](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/ContractCBORoles.json) |
| 2     | Document Config | https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/DocumentConfig.json                                                                                                   |

#### Module enablement configuration&#x20;

1. Set module code as “Contracts” in Module.js of Contracts Module. Refer https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/tenant/citymodule.json

```
 {
            "module": "Contracts",
            "code": "Contracts",
            "active": true,
            "order": 5,
            "tenants": [
                {
                    "code": "pg.cityb"
                },
                {
                    "code": "pg.cityc"
                },
                {
                    "code": "pg.citya"
                }
            ]
     }


```

2. Enable Module in App.js. Update the object ‘enabledModules’. Use the code “Contracts”. This code should match with the code of the cityModule.json, mentioned above.

#### Role-action mapping

| S.No | API                                                     | <p>Action ID</p><p><br></p> | Roles                                                              |
| ---- | ------------------------------------------------------- | --------------------------- | ------------------------------------------------------------------ |
| 1    | <p>/contract-service/contract/v1/_create</p><p><br></p> | 66                          | <p>WORK_ORDER_CREATOR</p><p><br></p>                               |
| 2    | /contract-service/contract/v1/\_search                  | 68                          | WORK\_ORDER\_CREATOR, WORK\_ORDER\_APPROVER, WORK\_ORDER\_VERIFIER |
| 3    | /contract-service/contract/v1/\_update                  | 67                          | WORK\_ORDER\_CREATOR, WORK\_ORDER\_APPROVER, WORK\_ORDER\_VERIFIER |
| 4    | /estimate-service/estimate/v1/\_search                  | 10                          | ESTIMATE\_VERIFIER                                                 |
| 5    | /pms/project/v1/\_search                                | 52                          | PROJECT\_VIEWER                                                    |
| 6    | /egov-hrms/employees/\_search                           | 4                           | EMPLOYEE\_COMMON                                                   |
| 7    | /org-services/organisation/v1/\_search                  | 91                          | ORG\_ADMIN, WORK\_ORDER\_CREATOR, MUKTA\_ADMIN                     |
| 8    | /wms/contract/\_search                                  | 89                          | WORK\_ORDER\_CREATOR, WORK\_ORDER\_VERIFIER                        |

#### Sidebar configuration&#x20;

| S.No | Screen          | Navigation URL                                       | <p>LeftIcon Updates</p><p><br></p>     | Roles                                                                          |
| ---- | --------------- | ---------------------------------------------------- | -------------------------------------- | ------------------------------------------------------------------------------ |
| 1    | Contract Inbox  | <p>/works-ui/employee/contracts/inbox</p><p><br></p> | <p>dynamic:ContractIcon</p><p><br></p> | <p>WORK_ORDER_CREATOR, WORK_ORDER_VERIFIER, WORK_ORDER_APPROVER</p><p><br></p> |
| 2    | Create Contract | /works-ui/employee/estimate/search-estimate          | dynamic:ContractIcon                   | WORK\_ORDER\_CREATOR                                                           |

```
{
      "id": 58,
      "name": "CONTRACTS",
      "url": "url",
      "displayName": "Contracts Inbox",
      "orderNumber": 2,
      "parentModule": "",
      "enabled": true,
      "serviceCode": "CONTRACTS",
      "code": "null",
      "navigationURL": "/works-ui/employee/contracts/inbox",
      "path": "3CONTRACTS.Inbox",
      "leftIcon": "dynamic:ContractIcon"
   }

```

#### Screen configuration&#x20;

| S.No | Screen  | Configuration                                                                                                   |
| ---- | ------- | --------------------------------------------------------------------------------------------------------------- |
| 1    | Create  | https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/commonMuktaUiConfig/CreateWorkOrderConfig.json |
| 2    | Search  | https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/commonMuktaUiConfig/SearchContractConfig.json  |
| 3    | Inbox   | https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/commonMuktaUiConfig/InboxConfigContracts.json  |

### Localization Configuration and Modules

| TenantID | Module              |
| -------- | ------------------- |
| pg       | rainmaker-contracts |

### &#x20;Workflow Configuration

| UI Component Name | Business Service        |
| ----------------- | ----------------------- |
| WorkflowActions   | contract-approval-mukta |

### Customization

1\. API-based Data -&#x20;

* Name of CBO - This field is being captured on the Create screen and Modify screen. Data for this field comes from the backend.
* CBO ID - This field is being set based on the value selected in the Name Of CBO.
* Name of Officer In Charge - This field is being populated based on the HRMS Search. Here the role is hardcoded to ‘OFFICER\_IN\_CHARGE’.
* Designation of Officer In Charge - This field is being set based on the value selected in the Name of Officer in charge.
* Work Order Amount - This field shows the calculated amount of Total Estimated Cost minus the Overheads which has ‘isWorkOrderValue’ as true. Please refer [this](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/Overheads.json) OverHeads config for Amount calculation.
* Role of CBO will be shown based on the calculated Work Order Amount. If the calculated Work Order Amount is less than ‘amount’ in RoleOfCBO Config, show Implementation Agency else show Implementation Partner. This logic will vary based on the updates in the [RoleOfCBO config](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/ContractCBORoles.json).

#### &#x20;  2.   Custom Components used in Projects :&#x20;

* Document Config -&#x20;
* Based on the [document config](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/DocumentConfig.json), respective documents will be rendered on the Create Screen. Please mention the validations, file type limits and file size limits in this config.
* Work Order Terms and Conditions -&#x20;
* This Component will help input description in the table. Users can add and delete the rows. First row won't be deleted, clicking on the delete button will empty the first row. Refer Component - WOTermsAndConditions.\


#### &#x20;  3.   Create Screen :&#x20;

1. Please use the common Utility “PreProcessMDMSConfig”.&#x20;
2. Pass the associated dependencies for the config.
3. The utility will return a config which will run through FormComposer.
4. Refer docs for Pre-Process config in Component comments.



&#x20; **4.  Inbox / Search Screen :**&#x20;

1. Please use the common utility “preProcessMDMSConfigInboxSearch”.
2. Pass the associated dependencies for the config.
3. The utility will return a config which will run through RenderFormFields.
4. Refer docs for Pre-Process config in Component comments.
