# Measurement Book Service

## Overview

The measurement book service integrates estimate line item validation and workflow along with the measurement book registry.

## Pre-requisites

A running DIGIT platform is needed to deploy the measurement service. Specifically, the following dependencies are needed:

* DIGIT backbone services
* Persister
* Indexer
* MDMS
* Measurement Book Registry
* Estimate
* Contract
* Project
* HRMS
* Localization
* Workflow

## Functionality

This service provides APIs to create, update and search for measurement service.  Refer to the [functional specifications here](../../functional-specifications/measurements.md).

## Deployment

The below variables should be configured for the measurement registry in the Helm environment file prior to deployment. The Helm environment file will be located under:

`https://github.com/`<mark style="color:red;">`{{ORG}}`</mark>`/DIGIT-DevOps/deploy-as-code/helm/environments/`<mark style="color:red;">`{{EnvironmentFile}}`</mark>`.yaml`

Refer to the [sample here](https://github.com/egovernments/DIGIT-DevOps/blob/unified-env/deploy-as-code/helm/environments/unified-works-dev.yaml).

* Add db-host,db-name,db-url,domain and all the digit core platform services configurations (Idgen, workflow,user etc.) in the YAML file.
* Add the ‘[egov-mdms-service](https://github.com/egovernments/DIGIT-DevOps/blob/unified-env/deploy-as-code/helm/environments/unified-works-dev.yaml#L416)’ related configuration to the respective environment YAML file. Make sure you change the gitsync.branch name.
* Check the measurement-registry persister file is added to the **`egov-persister.perister-yml-path`** variable. If not, please add the way it's done [here](https://github.com/egovernments/DIGIT-DevOps/blob/1f68ca9dcb4b27689c32f2026a4ea0de3761a88d/deploy-as-code/helm/environments/unified-works-dev.yaml#L445).
* Make sure to add the DB(Postgres and flyway) username & password in the respective environment secret yaml file. Follow the steps [here](https://github.com/egovernments/DIGIT-DevOps/blob/1f68ca9dcb4b27689c32f2026a4ea0de3761a88d/deploy-as-code/helm/environments/unified-works-dev-secrets.yaml#L3).
* Make sure to add the DIGIT core services-related secrets configured in the respective environment secret file. Follow the steps [here](https://github.com/egovernments/DIGIT-DevOps/blob/1f68ca9dcb4b27689c32f2026a4ea0de3761a88d/deploy-as-code/helm/environments/unified-works-dev-secrets.yaml#L3).

{% hint style="info" %}
Restart egov-mdms-service, egov-persister, egov-indexer, inbox, egov-workflow-v2, egov-accesscontrol and zuul after the above changes are performed.
{% endhint %}

## Configuration

### MDMS configuration

Configure actions, roles and role-action mappings from the table below. Follow the steps here.

<table><thead><tr><th width="295">Role</th><th>APIs</th></tr></thead><tbody><tr><td>MB_CREATOR</td><td>/measurement-service/v1/_create</td></tr><tr><td></td><td>/measurement-service/v1/_update</td></tr><tr><td></td><td>/measurement-service/v1/_search</td></tr><tr><td></td><td>/wms/measurement-service/_search</td></tr><tr><td>MB_VERIFIER</td><td>/measurement-service/v1/_update</td></tr><tr><td></td><td>/measurement-service/v1/_search</td></tr><tr><td></td><td>/wms/measurement-service/_search</td></tr><tr><td>MB_APPROVER</td><td>/measurement-service/v1/_update</td></tr><tr><td></td><td>/measurement-service/v1/_search</td></tr><tr><td>MB_VIEWER</td><td>/measurement-service/v1/_search</td></tr><tr><td></td><td>/wms/measurement-service/_search</td></tr><tr><td>EMPLOYEE_COMMON</td><td>/inbox/v2/_search</td></tr></tbody></table>

These have to be translated into JSON in the role-action mapping module in MDMS.

Example - available [here](https://github.com/egovernments/egov-mdms-data/blob/0dd049ffddbc7c6078b940b5eb9eb4951eb8996a/data/pg/ACCESSCONTROL-ROLEACTIONS/roleactions.json).&#x20;

### Workflow Configuration

#### Measurement Service Workflow

The following workflow JSON needs to be put in the request body of the `/egov-workflow-v2/egov-wf/businessservice/_create` API.&#x20;

```
"BusinessServices": [
{
  "tenantId": "pg",
  "businessService": "MB",
  "business": "measurement-book-service",
  "businessServiceSla": 432000000,
  "states": [
    {
      "sla": null,
      "state": null,
      "applicationStatus": null,
      "docUploadRequired": true,
      "isStartState": true,
      "isTerminateState": false,
      "isStateUpdatable": true,
      "actions": [
        {
          "action": "SAVE_AS_DRAFT",
          "nextState": "DRAFTED",
          "roles": [
           "MB_CREATOR"
          ]
        }
      ]
    },
    {
      "sla": null,
      "state": "DRAFTED",
      "applicationStatus": "DRAFTED",
      "docUploadRequired": false,
      "isStartState": false,
      "isTerminateState": false,
      "isStateUpdatable": false,
      "actions": [
        {
          "action": "SUBMIT",
          "nextState": "PENDING_FOR_VERIFICATION",
          "roles": [
            "MB_CREATOR"
          ]
        },
        {
          "action": "REJECT",
          "nextState": "REJECTED",
          "roles": [
            "MB_CREATOR"
          ]
        }
      ]
    },
    {
      "sla": 172800000,
      "state": "PENDING_FOR_VERIFICATION",
      "applicationStatus": "SUBMITTED",
      "docUploadRequired": false,
      "isStartState": false,
      "isTerminateState": false,
      "isStateUpdatable": false,
      "actions": [
        {
          "action": "VERIFY_AND_FORWARD",
          "nextState": "PENDING_FOR_APPROVAL",
          "roles": [
           "MB_VERIFIER"
          ]
        },
        {
          "action": "SENT_BACK",
          "nextState": "PENDING_FOR_CORRECTION",
          "roles": [
            "MB_VERIFIER"
          ]
        },
        {
          "action": "REJECT",
          "nextState": "REJECTED",
          "roles": [
            "MB_VERIFIER"
          ]
        }
      ]
    },
    {
      "sla": 86400000,
      "state": "PENDING_FOR_APPROVAL",
      "applicationStatus": "VERIFIED",
      "docUploadRequired": false,
      "isStartState": false,
      "isTerminateState": false,
      "isStateUpdatable": false,
      "actions": [
        {
          "action": "SENT_BACK",
          "nextState": "PENDING_FOR_VERIFICATION",
          "roles": [
            "MB_APPROVER"
          ]
        },
        {
          "action": "APPROVE",
          "nextState": "APPROVED",
          "roles": [
            "MB_APPROVER"
          ]
        },
        {
          "action": "REJECT",
          "nextState": "REJECTED",
          "roles": [
            "MB_APPROVER"
          ]
        },
        {
          "action": "SEND_BACK_TO_ORIGINATOR",
          "nextState": "PENDING_FOR_VERIFICATION",
          "roles": [
            "MB_APPROVER"
          ]
        }
      ]
    },
    {
      "sla": 86400000,
      "state": "PENDING_FOR_CORRECTION",
      "applicationStatus": "SENT_BACK",
      "docUploadRequired": false,
      "isStartState": false,
      "isTerminateState": false,
      "isStateUpdatable": false,
      "actions": [
        {
          "action": "EDIT/RE-SUBMIT",
          "nextState": "PENDING_FOR_VERIFICATION",
          "roles": [
            "MB_CREATOR"
          ]
        },
        {
          "action": "REJECT",
          "nextState": "REJECTED",
          "roles": [
            "MB_CREATOR"
          ]
        },
        {
          "action": "SEND_BACK_TO_ORIGINATOR",
          "nextState": "PENDING_FOR_VERIFICATION",
          "roles": [
            "MB_CREATOR"
          ]
        }
      ]
    },
    {
      "sla": null,
      "state": "REJECTED",
      "applicationStatus": "REJECTED",
      "docUploadRequired": false,
      "isStartState": false,
      "isTerminateState": true,
      "isStateUpdatable": false,
      "actions": null
    },
    {
      "sla": null,
      "state": "APPROVED",
      "applicationStatus": "APPROVED",
      "docUploadRequired": false,
      "isStartState": false,
      "isTerminateState": true,
      "isStateUpdatable": false,
      "actions": null
    }

  ]
}
]
```

[Workflow configuration](https://github.com/egovernments/configs/blob/UNIFIED-DEV/works/workflow-configs/MB.json)

### Persister Configuration

Please make sure that the file[ <mark style="color:purple;">measurement-service-persister.yml</mark>](https://github.com/egovernments/configs/blob/e3cca4152e63d9b671ed34c2e0fa321f1b4da87c/works/egov-persister/measurement-service-persister.yml) is present in the **`configs`** repository in the below location.&#x20;

[https://github.com/\<YOUR ORGANISATION>/configs/tree/UNIFIED-DEV/works/egov-persister](https://github.com/egovernments/configs/blob/e3cca4152e63d9b671ed34c2e0fa321f1b4da87c/works/egov-persister/measurement-persister.yml)

### Indexer Configuration

Please make sure that the file [measurement-service-indexer.yml](https://github.com/egovernments/configs/blob/e3cca4152e63d9b671ed34c2e0fa321f1b4da87c/works/egov-indexer/measurement-indexer.yml) is present in the **`configs`** repository in the below location.&#x20;

[https://github.com/\<YOUR ORGANISATION>/configs/tree/UNIFIED-DEV/works/egov-indexer](https://github.com/egovernments/configs/blob/e3cca4152e63d9b671ed34c2e0fa321f1b4da87c/works/egov-persister/measurement-persister.yml)



{% hint style="info" %}
Make sure to restart MDMS, persister service and indexer service after adding the file at the above location.
{% endhint %}

### Inbox Configuration

In the MDMS repository, locate the[ inbox configuration file](https://github.com/egovernments/egov-mdms-data/blob/0dd049ffddbc7c6078b940b5eb9eb4951eb8996a/data/pg/inbox-v2/InboxConfiguration.json). Make sure the following JSON is added to the inbox configuration:

```
{
  "module": "measurement-service",
  "index": "measurement-service-index",
  "allowedSearchCriteria": [
    {
      "name": "tenantId",
      "path": "Data.tenantId.keyword",
      "isMandatory": true,
      "operator": "EQUAL"
    },
    {
      "name": "status",
      "path": "Data.currentProcessInstance.state.uuid.keyword",
      "isMandatory": false
    },
    {
      "name": "measurementNumber",
      "path": "Data.measurementNumber.keyword",
      "isMandatory": false,
      "operator": "EQUAL"
    },
    {
      "name": "projectId",
      "path": "Data.contract.additionalDetails.projectId.keyword",
      "isMandatory": false,
      "operator": "EQUAL"
    },
    {
      "name": "ward",
      "path": "Data.contract.additionalDetails.ward.keyword",
      "isMandatory": false,
      "operator": "EQUAL"
    },
    {
      "name": "assignee",
      "path": "Data.currentProcessInstance.assignes.uuid.keyword",
      "isMandatory": false
    },
    {
      "name": "projectType",
      "path": "Data.contract.additionalDetails.projectType.keyword",
      "isMandatory": false,
      "operator": "EQUAL"
    }

  ],
  "sortBy": {
    "path": "Data.auditDetails.createdTime",
    "defaultOrder": "DESC"
  },
  "sourceFilterPathList": [
    "Data.referenceId",
    "Data.id",
    "Data.measurementNumber",
    "Data.measures",
    "Data.auditDetails",
    "Data.history",
    "Data.currentProcessInstance",
    "Data.additionalDetails",
    "Data.workflow",
    "Data.wfStatus",
    "Data.contract.additionalDetails",
    "Data.contract.id",
    "Data.contract.contractNumber",
    "Data.contract.additionalDetails"
  ]
}
```
