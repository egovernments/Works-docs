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

<table data-header-hidden><thead><tr><th width="98.99999999999997"></th><th width="188"></th><th></th></tr></thead><tbody><tr><td>S.No.</td><td>Data</td><td>MDMS Link</td></tr><tr><td>1</td><td>Relationship</td><td><a href="https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/Relationship.json">https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/Relationship.json</a></td></tr><tr><td>2</td><td>GenderType</td><td><a href="https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/GenderType.json">https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/GenderType.json</a></td></tr><tr><td>3</td><td>SocialCategory</td><td><a href="https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/SocialCategory.json">https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/SocialCategory.json</a></td></tr><tr><td>4</td><td>WageSeekerSkills</td><td><a href="https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/WageSeekerSkills.json">https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/WageSeekerSkills.json</a></td></tr><tr><td>5</td><td>TenantBoundary</td><td><a href="https://github.com/egovernments/works-mdms-data/blob/8285bc63aac7f056326165897ac18918520c9723/data/pg/citya/egov-location/boundary-data.json">https://github.com/egovernments/works-mdms-data/blob/8285bc63aac7f056326165897ac18918520c9723/data/pg/citya/egov-location/boundary-data.json</a></td></tr></tbody></table>

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



<table data-header-hidden><thead><tr><th width="82"></th><th></th><th width="147"></th><th></th></tr></thead><tbody><tr><td>S.No</td><td>API</td><td><p>Action ID</p><p><br></p></td><td>Roles</td></tr><tr><td>1</td><td><p>/individual/v1/_search</p><p><br></p></td><td>71</td><td>MUKTA_ADMIN,<br>ORG_ADMIN</td></tr><tr><td>2</td><td>/individual/v1/_update</td><td>72</td><td>MUKTA_ADMIN,<br>ORG_ADMIN</td></tr><tr><td>3</td><td>/individual/v1/_delete</td><td>74</td><td>MUKTA_ADMIN,<br>ORG_ADMIN</td></tr></tbody></table>

#### Sidebar configuration&#x20;



<table data-header-hidden><thead><tr><th width="83"></th><th></th><th></th><th></th><th></th></tr></thead><tbody><tr><td>S.No</td><td>Screen</td><td>Navigation URL</td><td><p>LeftIcon Updates</p><p><br></p></td><td>Roles</td></tr><tr><td>1</td><td>Search Individual</td><td>/works-ui/employee/masters/search-wageseeker</td><td>dynamic:WageseekerIcon</td><td>MUKTA_ADMIN</td></tr></tbody></table>

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



<table data-header-hidden><thead><tr><th width="97.99999999999997"></th><th></th><th></th></tr></thead><tbody><tr><td>S.No</td><td>Screen</td><td>Configuration</td></tr><tr><td>1</td><td>Create/Modify</td><td><a href="https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/commonMuktaUiConfig/CreateWageSeekerConfig.json">Modify Individual Config</a></td></tr><tr><td>2</td><td>Search</td><td><a href="https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/commonMuktaUiConfig/SearchIndividualConfig.json">Search Individual Config</a></td></tr></tbody></table>

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
