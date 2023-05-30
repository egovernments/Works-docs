---
description: Project Module Frontend Tech Documentation
---

# Project

### Overview

This module enables the Junior Engineer to capture the details of the Project, Search and view the existing Projects and Modify the Project. This module is the initial step in starting the work.



This module has 4 associated screens :

1. Create
2. Search
3. Modify
4. View

### MDMS Configurations

<table data-header-hidden><thead><tr><th width="124.99999999999997"></th><th width="209"></th><th></th></tr></thead><tbody><tr><td>S.No.</td><td>Data</td><td>MDMS Link</td></tr><tr><td>1</td><td>Project Type</td><td>https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/ProjectType.json</td></tr><tr><td>2</td><td>Target Demography</td><td>https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/TargetDemography.json</td></tr><tr><td>3</td><td>ULB, City, Locality</td><td>https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/citya/egov-location/boundary-data.json</td></tr><tr><td><br></td><td><br></td><td>https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/cityb/egov-location/boundary-data.json</td></tr><tr><td><br></td><td><br></td><td>https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/cityc/egov-location/boundary-data.json</td></tr><tr><td>4</td><td>Document Config</td><td>https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/DocumentConfig.json</td></tr></tbody></table>

#### Module enablement configuration&#x20;

1. Set module code as “Project” in Module.js of Project Module. Refer https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/tenant/citymodule.json.

```
 {
            "module": "Project",
            "code": "Project",
            "active": true,
            "order": 8,
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
},

```

2. Enable Module in App.js. Update the object ‘enabledModules’. Use the code “Project”. This code should match with the code of the cityModule.json, mentioned above.

#### PDF Configuration

The Project created can be downloaded in PDF format from the View Project Screen of the Project Module. This PDF has the Description, Work details, and Location details of the respective Project.

**PDF URL** : https://works-dev.digit.org/egov-pdf/download/project/project-details?projectId=\<project-Id>\&tenantId=\<tenant-Id>

#### Role-action mapping

<table data-header-hidden><thead><tr><th width="84"></th><th width="283"></th><th width="101"></th><th></th></tr></thead><tbody><tr><td>S.No</td><td>API</td><td><p>Action ID</p><p><br></p></td><td>Roles</td></tr><tr><td>1</td><td><p>/pms/project/v1/_create</p><p><br></p></td><td><p>51</p><p><br></p></td><td><p>PROJECT_CREATOR</p><p><br></p></td></tr><tr><td>2</td><td>/pms/project/v1/_search</td><td>52</td><td>PROJECT_VIEWER</td></tr><tr><td>3</td><td>/pms/project/v1/_update</td><td>52</td><td>PROJECT_CREATOR</td></tr></tbody></table>

**Sidebar configuration**&#x20;

<table data-header-hidden><thead><tr><th width="79"></th><th width="128"></th><th></th><th width="125"></th><th></th></tr></thead><tbody><tr><td>S.No</td><td>Screen</td><td>Navigation URL</td><td><p>LeftIcon Updates</p><p><br></p></td><td>Roles</td></tr><tr><td>1</td><td>Create Project</td><td><p>/works-ui/employee/project/create-project</p><p><br></p></td><td><p>dynamic:ProjectIcon</p><p><br></p></td><td><p>PROJECT_CREATOR</p><p><br></p></td></tr><tr><td>2</td><td>Search Project</td><td>/works-ui/employee/project/search-project</td><td><p>dynamic:ProjectIcon</p><p><br></p></td><td>PROJECT_VIEWER</td></tr></tbody></table>

#### Sample Configuration

```
 {
     "id": 15,
     "name": "PROJECT",
     "url": "url",
     "displayName": "Create Project",
     "orderNumber": 1,
     "parentModule": "",
     "enabled": true,
     "serviceCode": "PROJECT",
     "code": "null",
     "navigationURL": "/works-ui/employee/project/create-project",
     "path": "1PROJECT.Create",
     "leftIcon": "dynamic:ProjectIcon"
  }

```

#### Screen configuration&#x20;

<table data-header-hidden><thead><tr><th width="64.66666666666666"></th><th width="185"></th><th></th></tr></thead><tbody><tr><td>S.No</td><td>Screen</td><td>Configuration</td></tr><tr><td>1</td><td>Create / Update</td><td>https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/commonMuktaUiConfig/CreateProjectConfig.json</td></tr><tr><td>2</td><td>Search</td><td>https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/commonMuktaUiConfig/SearchProjectConfig.json</td></tr></tbody></table>

### Localization Configuration and Modules

| TenantID | Module                   |
| -------- | ------------------------ |
| pg       | rainmaker-project        |
| pg       | rainmaker-common-masters |
| pg       | rainmaker-common         |
| pg.citya | rainmaker-pg.citya       |

### &#x20;Workflow Configuration

&#x20; NA



### Customization

**Create Screen :**&#x20;

1. Please use the common Utility “PreProcessMDMSConfig”.&#x20;
2. Pass the associated dependencies for the config.
3. The utility will return a config that will run through FormComposer.
4. Refer to docs for Pre-Process config in Component comments.

&#x20; **Search Screen :**&#x20;

1. Please use the common utility “preProcessMDMSConfigInboxSearch”.
2. Pass the associated dependencies for the config.
3. The utility will return a config that will run through RenderFormFields.
4. Refer to docs for Pre-Process config in Component comments.

&#x20;  **Custom Components Used in Projects :**&#x20;

1. Document Config -&#x20;
2. Based on the [document config](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/DocumentConfig.json), respective documents will be rendered on the Create Screen. Please mention the validations, file type, and file size limits in this config.
3. &#x20;Form Validations :

&#x20;       Is all Form Validation being added in the Screen Configurations? Add the populators for respective validations and mention the JSON path for the Pre-Process to work.

\
