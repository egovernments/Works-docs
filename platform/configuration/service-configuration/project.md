---
description: Steps to configure the project service
---

# Project

## Overview

The project service provides APIs to create, update and manage a generic project. A project can have one or more of the following constructs: staff, tasks, beneficiaries and facilities. This service is shared across multiple eGov missions. The source code for this service resides [here](https://github.com/egovernments/health-campaign-services/tree/demo/health-services/project). For a deeper understanding, please refer to the following:

[Low-level design](https://works.digit.org/platform/specifications/technical-specifications/low-level-design/services/project)

[Functional specifications](https://works.digit.org/platform/specifications/functional-specifications/projects-service)

## Pre-requisites

* DIGIT backbone services&#x20;
* Persister
* Indexer
* MDMS

## Functionalities

The project service provides the below functionalities. Currently, only APIs to create, update, search and delete projects are used by the Works platform. The remaining APIs are consumed by other platforms.&#x20;

* Provides APIs to create, update, delete, and search projects.&#x20;
* Provides APIs to create, update, delete, and search project beneficiaries.&#x20;
* Provides APIs to bulk create, update, and delete project beneficiaries.&#x20;
* Provides APIs to create, update, delete, and search project facilities.&#x20;
* Provides APIs to bulk create, bulk update, bulk delete project facility&#x20;
* Provides APIs to create, update, delete, and search project staff.&#x20;
* Provides APIs to bulk create, update, and delete project staff.&#x20;
* Provides APIs to create, update, delete and search project tasks.&#x20;
* Provides APIs to bulk create, update, and delete project tasks.&#x20;
* Provides APIs to create, update, delete, and search project resources.&#x20;
* Provides APIs to bulk create, update, and delete project tasks.

## API Details

**Base URL:** pms/project/v1

## Configuration Details

### MDMS Configuration

#### roles.json

```json
 {
      "code": "PROJECT_CREATOR",
      "name": "PROJECT CREATOR",
      "description": "Project Creator"
    },
    {
      "code": "PROJECT_VIEWER",
      "name": "PROJECT VIEWER",
      "description": "Project Viewer"
    },
```

{% hint style="info" %}
Define (if not present already) and assign the EMPLOYEE\_COMMON role to all project actors.&#x20;
{% endhint %}

#### actions.json

Below are the actions or APIs exposed by the Project service used by the Works platform. Note that the "id" in the attributes needs to be unique and may be different in the implementation environment. It need not be exactly the same as what is shown below.

```json
{
      "id": 51,
      "name": "Create Project",
      "url": "/pms/project/v1/_create",
      "parentModule": "project-management-system",
      "displayName": "Create Project",
      "orderNumber": 0,
      "enabled": false,
      "serviceCode": "project-management-system",
      "code": "null",
      "path": ""
    },
    {
      "id": 52,
      "name": "Search Project",
      "url": "/pms/project/v1/_search",
      "parentModule": "project-management-system",
      "displayName": "Search Project",
      "orderNumber": 0,
      "enabled": false,
      "serviceCode": "project-management-system",
      "code": "null",
      "path": ""
    },
    {
      "id": 53,
      "name": "Update Project",
      "url": "/pms/project/v1/_update",
      "parentModule": "project-management-system",
      "displayName": "Update Project",
      "orderNumber": 0,
      "enabled": false,
      "serviceCode": "project-management-system",
      "code": "null",
      "path": ""
    },
```

### roleactions.json

The following table shows the mapping between the APIs and the roles:

| Role Code        | Description     | API                  |
| ---------------- | --------------- | -------------------- |
| PROJECT\_CREATOR | Project Creator | /project/v1/\_create |
|                  |                 | /project/v1/\_update |
|                  |                 | /project/v1/\_search |
| PROJECT\_VIEWER  | Project Viewer  | /project/v1/\_search |
| EMPLOYEE\_COMMON | Employee Common | /inbox/v2/\_search   |

The following role-action mappings derived from the above table are configured for the Project service in the roleactions.json in MDMS. A sample is provided below. Make sure the action ID is correct and corresponds to actions.json.&#x20;

```json
{
      "id": 51,
      "name": "Create Project",
      "url": "/project/v1/_create",
      "parentModule": "project-management-system",
      "displayName": "Create Project",
      "orderNumber": 0,
      "enabled": false,
      "serviceCode": "project-management-system",
      "code": "null",
      "path": ""
    },
    {
      "id": 52,
      "name": "Search Project",
      "url": "/project/v1/_search",
      "parentModule": "project-management-system",
      "displayName": "Search Project",
      "orderNumber": 0,
      "enabled": false,
      "serviceCode": "project-management-system",
      "code": "null",
      "path": ""
    },
    {
      "id": 53,
      "name": "Update Project",
      "url": "/project/v1/_update",
      "parentModule": "project-management-system",
      "displayName": "Update Project",
      "orderNumber": 0,
      "enabled": false,
      "serviceCode": "project-management-system",
      "code": "null",
      "path": ""
    },
```

### Other Master Data Configuration

1\. [ProjectType ](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/ProjectType.json)&#x20;

2\. [ProjectSubType](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/ProjectSubType.json)

3\. [Department](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/Department.json#L55-L59)

4\. [Boundary Data](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/citya/egov-location/boundary-data.json)

## Deployment Details

The image name of the service is available in the release charts in the DevOps repository. The service can be deployed using Helm commands.&#x20;

Environment variables to be configured in the Helm chart for the service are:

1. Add the ‘db-host’,’db-name’,’db-url’,’domain’ and all the digit core platform services configurations (Idgen, workflow, user etc.) in respective environments yaml file.
2. Add project-management-system related environment variables values. A sample from a[ ‘dev](https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/environments/works-dev.yaml)’ environment yaml file is provided below:
   * [https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/environments/works-dev.yaml#L78](https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/environments/works-dev.yaml#L78)&#x20;
   * [https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/environments/works-dev.yaml#L200-L205](https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/environments/works-dev.yaml#L200-L205)&#x20;
   * [https://github.com/egovernments/DIGIT-DevOps/tree/digit-works/deploy-as-code/helm/charts/digit-works/backend/project-management-system](https://github.com/egovernments/DIGIT-DevOps/tree/digit-works/deploy-as-code/helm/charts/digit-works/backend/project-management-system)&#x20;
3. Add the ‘[egov-mdms-service](https://github.com/egovernments/DIGIT-DevOps/blob/5a9eb4c6141e19bd747238889ceed9bc9fffdc6f/deploy-as-code/helm/environments/works-dev.yaml#L190)’ related configuration to the respective environment yaml file. Make sure you change the git-sync branch name to one that is appropriate for the environment.
4. Check the project management system persister file is added in the egov-persister.persister-yml-path variable. If not, please add the way it's done[ here](https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/environments/works-dev.yaml#L266).
5. Make sure to add the DB(Postgres and flyway) username & password in the respective environment secrets yaml file the way it's done[ here](https://github.com/egovernments/DIGIT-DevOps/blob/e742a292f2966bb1affb3b03edd643a777917ba1/deploy-as-code/helm/environments/works-dev-secrets.yaml#L3).
6. Make sure to add the DIGIT core service-related secrets that are configured in the respective environment secret file the way it's done[ here](https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/environments/works-dev-secrets.yaml).

{% hint style="warning" %}
**NOTE:** Restart egov-mdms-service, egov-persister and zuul after the above changes are performed.
{% endhint %}

## Integration Details

Refer to the [API spec](https://works.digit.org/platform/specifications/technical-specifications/low-level-design/services/project) for a description of the APIs. The associated [Postman scripts](https://github.com/egovernments/DIGIT-Works/blob/develop/backend/project-management-system/src/main/resources/Project%20Management%20System%20-%20Postman%20Test%20Suite.postman\_collection.json) are provided here for reference. Use these to understand the request payloads.&#x20;

