---
description: Wageseeker Tech Document
---

# WageSeeker

### Overview

This module helps in creating an individual(Wage Seeker) , it is needed in Mukta to assign work, track attendance and process DBTs.

This module has 3  associated screens :&#x20;

1. Search
2. View
3. Modify

### MDMS Configurations

####

| S.No. | Data             | MDMS Link                                                                                                                                                                                                                                                                                    |
| ----- | ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1     | Relationship     | [https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/Relationship.json](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/Relationship.json)                                                                                       |
| 2     | GenderType       | [https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/GenderType.json](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/GenderType.json)                                                                                           |
| 3     | SocialCategory   | [https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/SocialCategory.json](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/SocialCategory.json)                                                                                   |
| 4     | WageSeekerSkills | [https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/WageSeekerSkills.json](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/WageSeekerSkills.json)                                                                               |
| 5     | TenantBoundary   | [https://github.com/egovernments/works-mdms-data/blob/8285bc63aac7f056326165897ac18918520c9723/data/pg/citya/egov-location/boundary-data.json](https://github.com/egovernments/works-mdms-data/blob/8285bc63aac7f056326165897ac18918520c9723/data/pg/citya/egov-location/boundary-data.json) |

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



| S.No | API                                      | <p>Action ID</p><p><br></p> | Roles                            |
| ---- | ---------------------------------------- | --------------------------- | -------------------------------- |
| 1    | <p>/individual/v1/_search</p><p><br></p> | 71                          | <p>MUKTA_ADMIN,<br>ORG_ADMIN</p> |
| 2    | /individual/v1/\_update                  | 72                          | <p>MUKTA_ADMIN,<br>ORG_ADMIN</p> |
| 3    | /individual/v1/\_delete                  | 74                          | <p>MUKTA_ADMIN,<br>ORG_ADMIN</p> |

#### Sidebar configuration&#x20;



| S.No | Screen            | Navigation URL                               | <p>LeftIcon Updates</p><p><br></p> | Roles        |
| ---- | ----------------- | -------------------------------------------- | ---------------------------------- | ------------ |
| 1    | Search Individual | /works-ui/employee/masters/search-wageseeker | dynamic:WageseekerIcon             | MUKTA\_ADMIN |

Sample object for a sidebar action define in MDMS (containing navigationUrl)

\


```
{
      "id": 78,
      "name": "WAGESEEKER",
      "url": "url",
      "displayName": "Masters Search Wageseeker",
      "orderNumber": 10,
      "parentModule": "",
      "enabled": true,
      "serviceCode": "WageSeeker",
      "code": "null",
      "navigationURL": "/works-ui/employee/masters/search-wageseeker",
      "path": "8WageSeeker.Search",
      "leftIcon": "dynamic:WageseekerIcon"
    }

```

#### Screen configuration&#x20;



| S.No | Screen        | Configuration                                                                                                                                |
| ---- | ------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| 1    | Create/Modify | [Modify Individual Config](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/commonMuktaUiConfig/CreateWageSeekerConfig.json) |
| 2    | Search        | [Search Individual Config](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/commonMuktaUiConfig/SearchIndividualConfig.json) |

### Localization Configuration and Modules

| TenantID | Module                   |
| -------- | ------------------------ |
| pg       | rainmaker-masters        |
| pg       | rainmaker-common-masters |
| pg       | rainmaker-common         |
| pg.citya | rainmaker-pg.citya       |

### &#x20;Workflow Configuration

&#x20;  NA



### Customization

1. Modify Individual Screen

* Please use the common Utility “PreProcessMDMSConfig”.&#x20;
* Pass the associated dependencies for the config.
* The utility will return a config which will run through FormComposer.
* Refer docs for Pre-Process config in Component comments.\


2. Search Individual Screen

* Please use the common utility “preProcessMDMSConfigInboxSearch”.
* Pass the associated dependencies for the config.
* The utility will return a config which will run through RenderFormFields.
* Refer docs for Pre-Process config in Component comments.
* All the Inbox and Search Screens throughout the app are rendered using this component [Inbox/Search Composer](https://github.com/egovernments/DIGIT-Works/blob/c2a234bb4b21f0e54ca9664ee3e99d72ce871168/frontend/micro-ui/web/micro-ui-internals/packages/react-components/src/hoc/InboxSearchComposer.js)

3. Validations added&#x20;

* All Form validations are being added in the Screen Configurations. Add the populators for respective validations and mention the JSON path for the Pre-Process to work.\


4. Delete API Usage

* To update individual skills update Individual and delete individual APIs are being used
* If skills already exist then those can be updated with update API, if any skills are to be removed then delete API is used, in this case whole skill object need to be send with ‘isDeleted’ flag equals to true.
