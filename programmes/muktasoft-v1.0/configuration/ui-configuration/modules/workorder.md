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

<table data-header-hidden><thead><tr><th width="70.99999999999997"></th><th width="183"></th><th></th></tr></thead><tbody><tr><td>S.No.</td><td>Data</td><td>MDMS Link</td></tr><tr><td>1</td><td>Role Of CBO</td><td><a href="https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/ContractCBORoles.json">https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/ContractCBORoles.json</a></td></tr><tr><td>2</td><td>Document Config</td><td>https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/DocumentConfig.json</td></tr></tbody></table>

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

<table data-header-hidden><thead><tr><th width="91"></th><th width="260"></th><th width="110"></th><th></th></tr></thead><tbody><tr><td>S.No</td><td>API</td><td><p>Action ID</p><p><br></p></td><td>Roles</td></tr><tr><td>1</td><td><p>/contract-service/contract/v1/_create</p><p><br></p></td><td>66</td><td><p>WORK_ORDER_CREATOR</p><p><br></p></td></tr><tr><td>2</td><td>/contract-service/contract/v1/_search</td><td>68</td><td>WORK_ORDER_CREATOR, WORK_ORDER_APPROVER, WORK_ORDER_VERIFIER</td></tr><tr><td>3</td><td>/contract-service/contract/v1/_update</td><td>67</td><td>WORK_ORDER_CREATOR, WORK_ORDER_APPROVER, WORK_ORDER_VERIFIER</td></tr><tr><td>4</td><td>/estimate-service/estimate/v1/_search</td><td>10</td><td>ESTIMATE_VERIFIER</td></tr><tr><td>5</td><td>/pms/project/v1/_search</td><td>52</td><td>PROJECT_VIEWER</td></tr><tr><td>6</td><td>/egov-hrms/employees/_search</td><td>4</td><td>EMPLOYEE_COMMON</td></tr><tr><td>7</td><td>/org-services/organisation/v1/_search</td><td>91</td><td>ORG_ADMIN, WORK_ORDER_CREATOR, MUKTA_ADMIN</td></tr><tr><td>8</td><td>/wms/contract/_search</td><td>89</td><td>WORK_ORDER_CREATOR, WORK_ORDER_VERIFIER</td></tr></tbody></table>

#### Sidebar configuration&#x20;

<table data-header-hidden><thead><tr><th width="87"></th><th width="124"></th><th></th><th></th><th></th></tr></thead><tbody><tr><td>S.No</td><td>Screen</td><td>Navigation URL</td><td><p>LeftIcon Updates</p><p><br></p></td><td>Roles</td></tr><tr><td>1</td><td>Contract Inbox</td><td><p>/works-ui/employee/contracts/inbox</p><p><br></p></td><td><p>dynamic:ContractIcon</p><p><br></p></td><td><p>WORK_ORDER_CREATOR, WORK_ORDER_VERIFIER, WORK_ORDER_APPROVER</p><p><br></p></td></tr><tr><td>2</td><td>Create Contract</td><td>/works-ui/employee/estimate/search-estimate</td><td>dynamic:ContractIcon</td><td>WORK_ORDER_CREATOR</td></tr></tbody></table>

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

<table data-header-hidden><thead><tr><th width="71.99999999999997"></th><th width="139"></th><th></th></tr></thead><tbody><tr><td>S.No</td><td>Screen</td><td>Configuration</td></tr><tr><td>1</td><td>Create </td><td>https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/commonMuktaUiConfig/CreateWorkOrderConfig.json</td></tr><tr><td>2</td><td>Search</td><td>https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/commonMuktaUiConfig/SearchContractConfig.json</td></tr><tr><td>3</td><td>Inbox</td><td>https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/commonMuktaUiConfig/InboxConfigContracts.json</td></tr></tbody></table>

### Localization Configuration and Modules

<table data-header-hidden><thead><tr><th width="251"></th><th></th></tr></thead><tbody><tr><td>TenantID</td><td>Module</td></tr><tr><td>pg</td><td>rainmaker-contracts</td></tr><tr><td>pg</td><td>rainmaker-common-masters</td></tr><tr><td>pg</td><td>rainmaker-common</td></tr><tr><td>pg</td><td>rainmaker-workflow</td></tr><tr><td>pg.citya</td><td>rainmaker-pg.citya</td></tr></tbody></table>

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
