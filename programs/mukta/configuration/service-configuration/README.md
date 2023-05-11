---
description: Configuring platform services
---

# Service Configuration

This page lists common configuration steps that need to be repeatedly performed for all services. Follow the steps in the context of each service replacing only certain values as required. The respective service will provide the information on what needs to be replaced.

## Deploying a Service

Deploying a service involves three parts:

* Deploying a published docker image of the service in a DIGIT environment
* Having the Helm charts necessary for the service deployment. Helm charts configure the environment variables for the service specific to a Kube cluster. A service can be deployed using  CI/CD[^1] OR  directly using Helm commands from a system. All helm charts for MUKTA[^2] services are [available in this repository here](https://github.com/egovernments/DIGIT-DevOps/tree/digit-works/deploy-as-code/helm/charts/digit-works/backend).&#x20;
* Configuring the service&#x20;
  * MDMS[^3], IDGen, Workflow, other masters for the service to work properly to be set up in GitHub.

## MDMS Role-Action Configuration

For more information on MDMS, please visit here.

All modules expose certain actions (APIs), roles (actors) and role-action mappings (who can access which resource). Role-action mappings are used for access control.&#x20;

Each service documentation will have a role-action table that identifies which actor can access which resource. Please follow the outline below replacing specific actions/roles for each module.&#x20;

Actions, Roles and Role-Action mapping are defined under a master tenant under folders. The folders have the same name as the module name for easy identification.&#x20;

Example:

![](<../../../../.gitbook/assets/Screenshot 2023-05-01 at 5.13.19 PM.png>)

In the above image, "pg" is the state level tenant. The three folders highlighted in orange contain the masters for actions, roleactions and roles respectively.&#x20;

{% hint style="info" %}
Folder structures are only for categorisation and easy navigation of master files. The MDMS service retrieves  data only through module and master names. Make sure that these are correct.
{% endhint %}

### Configure Actions

Add all the APIs exposed by the service (refer to service for actual APIs) to the <mark style="background-color:orange;">`actions.json`</mark> file in MDMS. Keep appending new entries to the bottom of the file. Make sure the `id` field is unique. Best practice is to increment the id by one when adding a new entry. This id field will be used in the role-action mapping.

**Module name:** ACCESSCONTROL-ACTIONS-TEST

**Master name:** actions-test

{% hint style="info" %}
In case 403s are encountered despite configuration, double check the actions.json file to make sure the API in question has a unique ID. In case of duplicate IDs, a 403 will be thrown by Zuul.
{% endhint %}

#### Example:

A sample entry is shown below:

```json
{
      "id": {unique ID},
      "name": "Create Estimate",
      "url": "/estimate-service/estimate/v1/_create",
      "parentModule": "estimate-service",
      "displayName": "Create Estimate",
      "orderNumber": 0,
      "enabled": false,
      "serviceCode": "estimate-service",
      "code": "null",
      "path": ""
    },
    {
      "id": {unique ID},
      "name": "Search Estimate",
      "url": "/estimate-service/estimate/v1/_search",
      "parentModule": "estimate-service",
      "displayName": "Search Estimate",
      "orderNumber": 0,
      "enabled": false,
      "serviceCode": "estimate-service",
      "code": "null",
      "path": ""
    },
    {
      "id": {unique ID},
      "name": "Update Estimate",
      "url": "/estimate-service/estimate/v1/_update",
      "parentModule": "estimate-service",
      "displayName": "Update Estimate",
      "orderNumber": 0,
      "enabled": false,
      "serviceCode": "estimate-service",
      "code": "null",
      "path": ""
    },
```

### Configure Roles

Configure roles based on the roles column (refer to service documentation) in the roles.json file. Make sure the role doesn't already exist. Append new roles to the bottom of the file.&#x20;

**Module name:** ACCESSCONTROL-ROLES

**Master name:** roles

{% hint style="warning" %}
#### Assign EMPLOYEE\_COMMON to all actors in the Works platform.
{% endhint %}

#### Example:

A sample entry is shown below:

```json
{
      "code": "ESTIMATE_CREATOR",
      "name": "ESTIMATE CREATOR",
      "description": "Estimate Creator"
    },
    {
      "code": "ESTIMATE_VIEWER",
      "name": "ESTIMATE VIEWER",
      "description": "Estimate VIEWER having search api access"
    },
```

### Configure Role-Action:

Role-action mapping should be configured as per the role-action table defined. Add new entries to the bottom of the roleactions.json file.&#x20;

Identify the action id (from the actions.json file) and map roles to that id. If multiple roles are mapped to an API, then each of them becomes a unique entry in the roleactions.json file.

**Module name:** ACCESSCONTROL-ROLEACTIONS

**Master name:** roleactions.json

#### Example:

A sample set of role-action entries is shown below. Each of the `actionid` fields needs to match a corresponding API from the actions.json file.&#x20;

For example, below, `ESTIMATE_CREATOR` is being given access to API actionid 9. This maps to the estimate create API in our repository. Note that the `actionid` and `tenantId` might differ from implementation to implementation.&#x20;

```json
 {
      "rolecode": "ESTIMATE_CREATOR",
      "actionid": 9,
      "actioncode": "",
      "tenantId": "pg"
    },
    {
      "rolecode": "ESTIMATE_VERIFIER",
      "actionid": 11,
      "actioncode": "",
      "tenantId": "pg"
    },
    {
      "rolecode": "TECHNICAL_SANCTIONER",
      "actionid": 11,
      "actioncode": "",
      "tenantId": "pg"
    }
```



## Persister Configuration

Each service has a persister.yaml file which needs to be stored in the configs repository. The actual file will be mentioned in the service documentation.&#x20;

Please add that yaml file under the configs repository if not present already.

{% hint style="warning" %}
Make sure to restart MDMS and the persister service after adding the file at the above location.
{% endhint %}

## Indexer Configuration

[^1]: Continuous Integration/Continuous Deployment

[^2]: Mukhyamantri Karma Tatpara Abhiyan Yojana ( MUKTA Yojana) - a government  scheme to provide employment

[^3]: Master Data Management Service
