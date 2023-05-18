---
description: Organization Tech Document
---

# Organization

This module helps in creating an organization which are business functions that work with ULB to execute projects. These can be typical contractors, SHGs or material vendors. All of them are registered under the same Organization Master.&#x20;



This module has 4 associated screens :&#x20;

1. Create
2. Search
3. View
4. Modify

### MDMS Configurations

#### MDMS Configurations

| S.No. | Data                | MDMS Link                                                                                                                                                                                                                                                                                    |
| ----- | ------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1     | OrgType             | [https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/OrgType.json](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/OrgType.json)                                                                                                 |
| 2     | OrgFunctionCategory | [https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/OrgFunctionCategory.json](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/OrgFunctionCategory.json)                                                                         |
| 3     | OrgFunctionClass    | [https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/OrgFunctionClass.json](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/OrgFunctionClass.json)                                                                               |
| 4     | OrgTaxIdentifier    | [https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/OrgTaxIdentifier.json](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/OrgTaxIdentifier.json)                                                                               |
| 5     | BankAccType         | [https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/BankAccType.json](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/BankAccType.json)                                                                                                           |
| 6     | OrgTransferCode     | [https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/OrgTransferCode.json](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/OrgTransferCode.json)                                                                                 |
| 7     | TenantBoundary      | [https://github.com/egovernments/works-mdms-data/blob/8285bc63aac7f056326165897ac18918520c9723/data/pg/citya/egov-location/boundary-data.json](https://github.com/egovernments/works-mdms-data/blob/8285bc63aac7f056326165897ac18918520c9723/data/pg/citya/egov-location/boundary-data.json) |

#### Module enablement configuration&#x20;

1. Set module code as “Masters” in Module.js for Masters (Organization) Module. Refer [CityModule.json](https://github.com/egovernments/works-mdms-data/blob/481752ba70aa29d235967d8ba6080685d897324a/data/pg/tenant/citymodule.json)

```
 {
            "module": "Masters",
            "code": "Masters",
            "active": true,
            "order": 6,
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

2. Enable Module in App.js. Update the object ‘enabledModules’. Use the code “Masters”. This code should match with the code of the cityModule.json, mentioned above.

#### Role-action mapping



| S.No | API                                                     | <p>Action ID</p><p><br></p> | Roles                                                |
| ---- | ------------------------------------------------------- | --------------------------- | ---------------------------------------------------- |
| 1    | <p>/org-services/organisation/v1/_create</p><p><br></p> | 100                         | MUKTA\_ADMIN                                         |
| 2    | /org-services/organisation/v1/\_search                  | 91                          | <p>MUKTA_ADMIN,<br>ORG_ADMIN, WORK_ORDER_CREATOR</p> |
| 3    | /org-services/organisation/v1/\_update                  | 101                         | MUKTA\_ADMIN                                         |

#### Sidebar configuration&#x20;



| S.No | Screen              | Navigation URL                                 | <p>LeftIcon Updates</p><p><br></p> | Roles        |
| ---- | ------------------- | ---------------------------------------------- | ---------------------------------- | ------------ |
| 1    | Create Organisation | /works-ui/employee/masters/create-organization | dynamic:OrganisationIcon           | MUKTA\_ADMIN |
| 2    | Search Organisation | /works-ui/employee/masters/search-organization | dynamic:OrganisationIcon           | MUKTA\_ADMIN |

#### Screen configuration&#x20;

| S.No | Screen        | Configuration                                                                                                                           |
| ---- | ------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| 1    | Create/Modify | [Create Org Config](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/commonMuktaUiConfig/CreateOrganizationConfig.json) |
| 2    | Search        | [Search Org Config](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/commonMuktaUiConfig/SearchOrganisationConfig.json) |

### Localization Configuration and Modules

| TenantID | Module            |
| -------- | ----------------- |
| pg       | rainmaker-masters |

### &#x20;Workflow Configuration

NA

### Customization

1. Custom Components used

&#x20;     TransferCodeTable -

* This component is a common component used to show Tax identifiers and     Transfer Codes input options in the ‘Financial Details’ section in Create screen
* Dropdown options for tax identifiers and transfer codes are populated by MDMS data
* Used can select type via dropdown and value needs to be entered for the corresponding type
* Users can add and delete rows for tax identifiers since there can be multiple identifiers. First row won't be deleted.
* Refer Component: [TransferCodeComponent](https://github.com/egovernments/DIGIT-Works/blob/master/frontend/micro-ui/web/micro-ui-internals/packages/modules/Masters/src/components/TransferCodeTable.js)\


#### 2. Create Organization Screen

* Please use the common Utility “PreProcessMDMSConfig”.&#x20;
* Pass the associated dependencies for the config.
* The utility will return a config that will run through FormComposer.
* Refer to docs for Pre-Process config in Component comments.
* Tax Identifiers and Transfer Codes are MDMS data.&#x20;

3\. Search Organization Screen

* Please use the common utility “preProcessMDMSConfigInboxSearch”.
* Pass the associated dependencies for the config.
* The utility will return a config that will run through RenderFormFields.
* Refer to docs for Pre-Process config in Component comments.
* All the Inbox and Search Screens throughout the app are rendered using this component [Inbox/Search Composer](https://github.com/egovernments/DIGIT-Works/blob/c2a234bb4b21f0e54ca9664ee3e99d72ce871168/frontend/micro-ui/web/micro-ui-internals/packages/react-components/src/hoc/InboxSearchComposer.js)
* Validations added
* All Form validations are being added in the Screen Configurations. Add the populators for respective validations and mention the JSON path for the Pre-Process to work.
* IFSC code has 2 validations as below

1. Pattern validation (given in config)
2. Third-party API is being used to get band and branch name based on entered valid IFSC code, This API throws 404 if the code is not valid, in that case the valid error message is displayed below the input field
3. Tax identifiers are not mandatory while creating Organisation. But as per API implementation, it's required in payload hence we send a dummy identifier value if the user has not entered anything in Tax identifier input. In the View Organisation screen if the PAN value is above the dummy value then ‘NA’ is displayed on the screen.

* Default value: Type => PAN, Value => XXXXX0123X
