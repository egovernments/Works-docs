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

| S.No.       | Data                | MDMS Link                                                                                               |
| ----------- | ------------------- | ------------------------------------------------------------------------------------------------------- |
| 1           | Project Type        | https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/ProjectType.json                 |
| 2           | Target Demography   | https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/TargetDemography.json            |
| 3           | ULB, City, Locality | https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/citya/egov-location/boundary-data.json |
| <p><br></p> | <p><br></p>         | https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/cityb/egov-location/boundary-data.json |
| <p><br></p> | <p><br></p>         | https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/cityc/egov-location/boundary-data.json |
| 4           | Document Config     | https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/DocumentConfig.json              |

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

| S.No | API                                       | <p>Action ID</p><p><br></p> | Roles                             |
| ---- | ----------------------------------------- | --------------------------- | --------------------------------- |
| 1    | <p>/pms/project/v1/_create</p><p><br></p> | <p>51</p><p><br></p>        | <p>PROJECT_CREATOR</p><p><br></p> |
| 2    | /pms/project/v1/\_search                  | 52                          | PROJECT\_VIEWER                   |
| 3    | /pms/project/v1/\_update                  | 52                          | PROJECT\_CREATOR                  |

**Sidebar configuration**&#x20;

| S.No | Screen         | Navigation URL                                              | <p>LeftIcon Updates</p><p><br></p>    | Roles                             |
| ---- | -------------- | ----------------------------------------------------------- | ------------------------------------- | --------------------------------- |
| 1    | Create Project | <p>/works-ui/employee/project/create-project</p><p><br></p> | <p>dynamic:ProjectIcon</p><p><br></p> | <p>PROJECT_CREATOR</p><p><br></p> |
| 2    | Search Project | /works-ui/employee/project/search-project                   | <p>dynamic:ProjectIcon</p><p><br></p> | PROJECT\_VIEWER                   |

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

| S.No | Screen          | Configuration                                                                                                 |
| ---- | --------------- | ------------------------------------------------------------------------------------------------------------- |
| 1    | Create / Update | https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/commonMuktaUiConfig/CreateProjectConfig.json |
| 2    | Search          | https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/commonMuktaUiConfig/SearchProjectConfig.json |

### Localization Configuration and Modules

| TenantID | Module                   |
| -------- | ------------------------ |
| pg       | rainmaker-project        |
| pg       | rainmaker-common-masters |
| pg       | rainmaker-common         |
| pg.citya | rainmaker-pg.citya       |

### &#x20;Workflow Configuration

NA



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
