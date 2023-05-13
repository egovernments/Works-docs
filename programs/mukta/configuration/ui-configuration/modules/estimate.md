---
description: Estimate Module Frontend Tech Documentation
---

# Estimate

### Overview

This module helps in creating estimates based on projects created.  This enables in deciding the Tendering, and Quotation.&#x20;

This module has 5 associated screens :&#x20;

1. Create Estimate
2. Search Estimate
3. Edit Estimate
4. View Estimate&#x20;
5. Estimate Inbox

### MDMS Configurations

| **S.No.**           | **Data**                 | **MDMS Link**                                                                                                                                                |
| ------------------- | ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1                   | UOM(Unit of Measurement) | [Unit of Measurement Masters](https://github.com/egovernments/works-mdms-data/blob/7e35616d8b0a21261854de7a38a4e814a2934888/data/pg/common-masters/uom.json) |
| <p>2</p><p><br></p> | Overheads                | [Overheads Masters](https://github.com/egovernments/works-mdms-data/blob/fa1435e1757c544f9a71a4455e3f9df5a595b802/data/pg/works/Overheads.json)              |
| 3                   | Document Config          | [Document Upload Config](https://github.com/egovernments/works-mdms-data/blob/677f82c458acefc1c7484387e056f1e8f7ad99b4/data/pg/works/DocumentConfig.json)    |

#### Module enablement configuration&#x20;

1. Set module code as “Estimate” in Module.js of Estimate Module. Refer this file [CityModule.json](https://github.com/egovernments/works-mdms-data/blob/481752ba70aa29d235967d8ba6080685d897324a/data/pg/tenant/citymodule.json) &#x20;

```
{
            "module": "Estimate",
            "code": "Estimate",
            "active": true,
            "order": 3,
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

2. Enable Module in App.js. Update the object ‘enabledModules’. Use the code “Estimate”. This code should match the code of the cityModule.json, mentioned above.

#### Role-action mapping

| S.No | API                                    | <p>Action ID</p><p><br></p> | Roles                                                                                                                                |
| ---- | -------------------------------------- | --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| 1    | /estimate-service/estimate/v1/\_create | 9                           | <p>ESTIMATE_CREATOR</p><p><br></p>                                                                                                   |
| 2    | /estimate-service/estimate/v1/\_search | 10                          | <p>ESTIMATE_CREATOR, ESTIMATE_VERIFIER, TECHNICAL_SANCTIONER</p><p>ESTIMATE_APPROVER</p><p>ESTIMATE_VIEWER</p><p>EMPLOYEE_COMMON</p> |
| 3    | /estimate-service/estimate/v1/\_update | 11                          | ESTIMATE\_VERIFIER, TECHNICAL\_SANCTIONER, ESTIMATE\_APPROVER                                                                        |
| 4    | /wms/estimate/\_search                 | 77                          | EMPLOYEE\_COMMON                                                                                                                     |
| 5    | /pms/project/v1/\_search               | 52                          | PROJECT\_VIEWER                                                                                                                      |



#### Sidebar configuration&#x20;

| S.No | Screen          | Navigation URL                                                | <p>LeftIcon Updates</p><p><br></p>     | Roles                                                                                                                   |
| ---- | --------------- | ------------------------------------------------------------- | -------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| 1    | Search Estimate | <p>/works-ui/employee/estimate/search-estimate</p><p><br></p> | <p>dynamic:EstimateIcon</p><p><br></p> | <p>ESTIMATE_VIEWER</p><p><br></p>                                                                                       |
| 2    | Estimate Inbox  | /works-ui/employee/estimate/inbox                             | dynamic:EstimateIcon                   | <p>ESTIMATE_VERIFIER</p><p>TECHNICAL_SANCTIONER</p><p>ESTIMATE_APPROVER</p><p></p><p></p><p></p><p>ESTIMATE_CREATOR</p> |

* Sample object for a sidebar action define in MDMS( containing navigationUrl )

```
{
      "id": 17,
      "name": "ESTIMATE",
      "url": "url",
      "displayName": "Estimate Inbox",
      "orderNumber": 2,
      "parentModule": "",
      "enabled": true,
      "serviceCode": "ESTIMATE",
      "code": "null",
      "navigationURL": "/works-ui/employee/estimate/inbox",
      "path": "2ESTIMATE.EstimateInbox",
      "leftIcon": "dynamic:EstimateIcon"
    }

```

#### Screen configuration&#x20;

| S.No | Screen              | Configuration                                                                                                                                                                        |
| ---- | ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1    | Create Estimate     | [Create Estimate Config](https://github.com/egovernments/works-mdms-data/blob/85f0eccb705dbb0b5e8756c96531782e1ba6da10/data/pg/commonMuktaUiConfig/CreateEstimateConfig.json)        |
| 2    | Search Estimate     | [Search Estimate Config](https://github.com/egovernments/works-mdms-data/blob/766b3aa37999fb9c671aa6dbe4c8b9d922d28264/data/pg/commonMuktaUiConfig/SearchEstimateConfig.json)        |
| 3    | Estimate Inbox      | [Estimate Inbox Config](https://github.com/egovernments/works-mdms-data/blob/766b3aa37999fb9c671aa6dbe4c8b9d922d28264/data/pg/commonMuktaUiConfig/EstimateInboxConfig.json)          |
| 4    | WMS Estimate Search | [Estimate WMS Search Config](https://github.com/egovernments/works-mdms-data/blob/766b3aa37999fb9c671aa6dbe4c8b9d922d28264/data/pg/commonMuktaUiConfig/SearchEstimateWMSConfig.json) |

### Localization Configuration and Modules

| TenantID | Module                   |
| -------- | ------------------------ |
| pg       | rainmaker-common         |
| pg       | rainmaker-estimate       |
| pg       | rainmaker-common-masters |
| pg       | rainmaker-workflow       |
| pg.citya | rainmaker-pg.citya       |

### &#x20;Workflow Configuration

1. Business Service name - “mukta-estimate”. Refer this MDMS file for workflow businessServices names  [Workflow](https://github.com/egovernments/works-mdms-data/blob/31b29c19a5839d7cea6e13dc800fc93c53364e4b/data/pg/expense/BusinessService.json)&#x20;
2. For Workflow related Actions, In all View Screens, we are using two components:

* [Workflow Actions](https://github.com/egovernments/DIGIT-Works/blob/c2a234bb4b21f0e54ca9664ee3e99d72ce871168/frontend/micro-ui/web/micro-ui-internals/packages/react-components/src/atoms/WorkflowActions.js) -> For calling the update API with appropriate workflow action(through action bar rendered on the bottom of view screen). This component has all the logic to show actions according to the logged in user, showing relevant popups and calling the update API to execute an action.

&#x20;     Popups are rendered based on configMap defined in this config file [Popup](https://github.com/egovernments/DIGIT-Works/blob/b001e1e4ed39a09830389fe258e164b0b4570531/frontend/micro-ui/web/micro-ui-internals/packages/react-components/src/atoms/Modals/config/configEstimateModal.js).

[Workflow Timeline](https://github.com/egovernments/DIGIT-Works/blob/6de6633cb1da5c5bd17b8a4f258a090d5b68a28d/frontend/micro-ui/web/micro-ui-internals/packages/react-components/src/atoms/WorkflowTimeline.js) -> For showing workflow history on View Screens.

### Customization

&#x20;**Custom Components used in Estimate:**&#x20;

1. Document Config -&#x20;

* Based on the [document config](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/DocumentConfig.json), respective documents will be rendered on the Create Screen. Please mention the validations, file type limits and file size limits in this config

2. NonSOR Table -  [Non SOR Table](https://github.com/egovernments/DIGIT-Works/blob/7b7f5a74bf992f5b393a43e21520409b398bc9e0/frontend/micro-ui/web/micro-ui-internals/packages/modules/Estimate/src/pageComponents/NonSORTable.js)

* Used in Create Estimate Screen to capture Non Sor line items. &#x20;

3. Overheads Table -  [Overheads Table](https://github.com/egovernments/DIGIT-Works/blob/7b7f5a74bf992f5b393a43e21520409b398bc9e0/frontend/micro-ui/web/micro-ui-internals/packages/modules/Estimate/src/pageComponents/OverheadsTable.js)

* Used in Create Estimate Screen to capture Overhead items. &#x20;

4. Total Estimate Amount -   [Total Estimate Amount](https://github.com/egovernments/DIGIT-Works/blob/7b7f5a74bf992f5b393a43e21520409b398bc9e0/frontend/micro-ui/web/micro-ui-internals/packages/modules/Estimate/src/pageComponents/TotalEstAmount.js)

* Used in Create Estimate Screen to calculate and render Total Estimate Amount. &#x20;

5. UploadFileComposer -   [Upload File Composer](https://github.com/egovernments/DIGIT-Works/blob/b001e1e4ed39a09830389fe258e164b0b4570531/frontend/micro-ui/web/micro-ui-internals/packages/react-components/src/hoc/UploadFileComposer.js)

* Used in Create Estimate Screen to render document upload section using  [Document Config](https://github.com/egovernments/works-mdms-data/blob/677f82c458acefc1c7484387e056f1e8f7ad99b4/data/pg/works/DocumentConfig.json)

6. Labour and Material Analysis-   [Labour and Material Analysis](https://github.com/egovernments/DIGIT-Works/blob/7b7f5a74bf992f5b393a43e21520409b398bc9e0/frontend/micro-ui/web/micro-ui-internals/packages/modules/Estimate/src/pageComponents/LabourAnalysis.js)

Used in Create Estimate Screen to capture labour and material costs, total labour and material costs cannot be greater than the total Estimate Amount

**Create Estimate Screen :**&#x20;

1. Please use the common Utility “PreProcessMDMSConfig”.&#x20;
2. Pass the associated dependencies for the config.
3. The utility will return a config which will run through FormComposer.
4. Refer to docs for Pre-Process config in Component comments.
5. UOM and Overheads captured in the create screen are MDMS data.

&#x20; **Inbox / Search Screen :**&#x20;

1. Please use the common utility “preProcessMDMSConfigInboxSearch”.
2. Pass the associated dependencies for the config.
3. The utility will return a config which will run through RenderFormFields.
4. Refer to docs for Pre-Process config in Component comments.

All the Inbox and Search Screens throughout the app are rendered using this component [Inbox/Search Composer](https://github.com/egovernments/DIGIT-Works/blob/c2a234bb4b21f0e54ca9664ee3e99d72ce871168/frontend/micro-ui/web/micro-ui-internals/packages/react-components/src/hoc/InboxSearchComposer.js)
