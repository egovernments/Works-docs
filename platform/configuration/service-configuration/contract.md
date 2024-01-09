---
description: Detailed description of configuring the contract service
---

# Contract

## Overview

The contract service provides the functionality of a works contract.&#x20;

## Pre-requisites

A running DIGIT platform is needed to deploy the contract service. Specifically, the following dependencies are needed:

* Estimate
* Organisation
* User
* Workflow
* IDGen
* HRMS
* Notification
* Persister
* Indexer
* MDMS

## Functionality

This service provides APIs to create, update and search for contracts. Refer to the [functional specifications here](../../functional-specifications/contracts.md) for detailed scope and functionality. Low-level technical design is [available here. ](../../architecture/low-level-design/services/contracts.md)

## Deployment

The below variables should be configured for the contract service in the Helm environment file prior to deployment. The Helm environment file will be located under:

`https://github.com/`<mark style="color:red;">`{{ORG}}`</mark>`/DIGIT-DevOps/deploy-as-code/helm/environments/`<mark style="color:red;">`{{EnvironmentFile}}`</mark>`.yaml`

Refer to the [sample here](https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/environments/works-dev.yaml).

* Add db-host,db-name,db-url,domain and all the digit core platform services configurations (Idgen, workflow,user etc.) in the YAML file.
* Add contract-service related environment variables’ value like the way it's done in [‘dev](https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/environments/works-dev.yaml#L206)’ environment YAML file. Search for "contract-service" in the file.&#x20;
* Add the ‘[egov-mdms-service](https://github.com/egovernments/DIGIT-DevOps/blob/5a9eb4c6141e19bd747238889ceed9bc9fffdc6f/deploy-as-code/helm/environments/works-dev.yaml#L190)’ related configuration to the respective environment YAML file. Make sure you change the gitsync.branch name.
* Check the contract-service persister file is added to the **`egov-persister.perister-yml-path`** variable. If not, please add the way it's done [here](https://github.com/egovernments/DIGIT-DevOps/blob/1f68ca9dcb4b27689c32f2026a4ea0de3761a88d/deploy-as-code/helm/environments/unified-works-dev.yaml#L445).
* Make sure to add the DB(Postgres and flyway) username & password in the respective environment secret yaml file. Follow the steps [here](https://github.com/egovernments/DIGIT-DevOps/blob/1f68ca9dcb4b27689c32f2026a4ea0de3761a88d/deploy-as-code/helm/environments/unified-works-dev-secrets.yaml#L3).
* Make sure to add the DIGIT core services-related secrets configured in the respective environment secret file. Follow the steps [here](https://github.com/egovernments/DIGIT-DevOps/blob/1f68ca9dcb4b27689c32f2026a4ea0de3761a88d/deploy-as-code/helm/environments/unified-works-dev-secrets.yaml#L3).

{% hint style="info" %}
Restart egov-mdms-service, egov-persister, egov-indexer, inbox, egov-workflow-v2, egov-accesscontrol and zuul after the above changes are performed.
{% endhint %}

## Configuration

### MDMS Configuration

Configure actions, roles and role-action mappings from the table below. Follow the steps [here](./).

<table><thead><tr><th width="295">Role</th><th>APIs</th></tr></thead><tbody><tr><td>WORK_ORDER_CREATOR</td><td>/contract/v1/_create</td></tr><tr><td></td><td>/contract/v1/_update</td></tr><tr><td></td><td>/contract/v1/_search</td></tr><tr><td></td><td>/wms/contract/_search</td></tr><tr><td>WORK_ORDER_VERIFIER</td><td>/contract/v1/_update</td></tr><tr><td></td><td>/contract/v1/_search</td></tr><tr><td></td><td>/wms/contract/_search</td></tr><tr><td>WORK_ORDER_APPROVER</td><td>/contract/v1/_update</td></tr><tr><td></td><td>/contract/v1/_search</td></tr><tr><td>WORK_ORDER_VIEWER</td><td>/contract/v1/_search</td></tr><tr><td></td><td>/wms/contract/_search</td></tr><tr><td>EMPLOYEE_COMMON</td><td>/inbox/v2/_search</td></tr></tbody></table>

These have to be translated into JSON in the role-action mapping module in MDMS.

Example - available [here](https://github.com/egovernments/egov-mdms-data/blob/0dd049ffddbc7c6078b940b5eb9eb4951eb8996a/data/pg/ACCESSCONTROL-ROLEACTIONS/roleactions.json).&#x20;

#### Other masters to be added:

The following masters are to be added as per the table below:

<table data-header-hidden><thead><tr><th width="213"></th><th></th></tr></thead><tbody><tr><td>CBO Roles</td><td><a href="https://github.com/egovernments/egov-mdms-data/blob/0dd049ffddbc7c6078b940b5eb9eb4951eb8996a/data/pg/works/ContractCBORoles.json">https://github.com/egovernments/egov-mdms-data/blob/0dd049ffddbc7c6078b940b5eb9eb4951eb8996a/data/pg/works/ContractCBORoles.json</a></td></tr><tr><td>OCI Roles</td><td><a href="https://github.com/egovernments/egov-mdms-data/blob/0dd049ffddbc7c6078b940b5eb9eb4951eb8996a/data/pg/works/ContractOfficerIncharge.json">https://github.com/egovernments/egov-mdms-data/blob/0dd049ffddbc7c6078b940b5eb9eb4951eb8996a/data/pg/works/ContractOfficerIncharge.json</a></td></tr><tr><td>ContractType</td><td><a href="https://github.com/egovernments/egov-mdms-data/blob/0dd049ffddbc7c6078b940b5eb9eb4951eb8996a/data/pg/works/ContractType.json">https://github.com/egovernments/egov-mdms-data/blob/0dd049ffddbc7c6078b940b5eb9eb4951eb8996a/data/pg/works/ContractType.json</a></td></tr><tr><td>Overheads</td><td><a href="https://github.com/egovernments/egov-mdms-data/blob/0dd049ffddbc7c6078b940b5eb9eb4951eb8996a/data/pg/works/Overheads.json">https://github.com/egovernments/egov-mdms-data/blob/0dd049ffddbc7c6078b940b5eb9eb4951eb8996a/data/pg/works/Overheads.json</a></td></tr></tbody></table>

## Idgen Configuration

Make sure the id format is configured in the ‘IdFormat.json’ file of the ‘common-masters’ module. The sample [is available here](https://github.com/egovernments/egov-mdms-data/blob/0dd049ffddbc7c6078b940b5eb9eb4951eb8996a/data/pg/common-masters/IdFormat.json#L34).&#x20;

| IDGen Format                                                                                                                                                                                                                                                  |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>{</p><p>      "format": "WO/[fy:yyyy-yy]/[SEQ_CONTRACT_NUM]",</p><p>      "idname": "contract.number"</p><p> }<br>{</p><p>        "format": "RW/[fy:yyyy-yy]/[SEQ_CONT_SUPPLEMENT_NUM]",</p><p>        "idname": "contract.supplement.number" </p><p>}</p> |

### Workflow Configuration

#### Contract Workflow

The following workflow JSON needs to be put in the request body of the `/egov-workflow-v2/egov-wf/businessservice/_create` API.&#x20;

{% hint style="info" %}
For more information on configuring workflow, please refer to the Workflow Service documentation here.
{% endhint %}

{% code lineNumbers="true" %}
```json
"BusinessServices": [
    {
      "tenantId": "pg",
      "businessService": "CONTRACT",
      "business": "contract-service",
      "businessServiceSla": 604800000,
      "states": [
        {
          "sla": null,
          "state": null,
          "applicationStatus": null,
          "docUploadRequired": false,
          "isStartState": true,
          "isTerminateState": false,
          "isStateUpdatable": true,
          "actions": [
            {
              "action": "CREATE",
              "nextState": "PENDING_FOR_VERIFICATION",
              "roles": [
                "WORK_ORDER_CREATOR"
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
          "isStateUpdatable": true,
          "actions": [
            {
              "action": "VERIFY_AND_FORWARD",
              "nextState": "PENDING_FOR_APPROVAL",
              "roles": [
                "WORK_ORDER_VERIFIER"
              ]
            },
            {
              "action": "SEND_BACK",
              "nextState": "PENDING_FOR_CORRECTION",
              "roles": [
                "WORK_ORDER_VERIFIER"
              ]
            },
            {
              "action": "REJECT",
              "nextState": "REJECTED",
              "roles": [
                "WORK_ORDER_VERIFIER"
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
          "isStateUpdatable": true,
          "actions": [
            {
              "action": "APPROVE",
              "nextState": "APPROVED",
              "roles": [
                "WORK_ORDER_APPROVER"
              ]
            },
            {
              "action": "SEND_BACK",
              "nextState": "PENDING_FOR_VERIFICATION",
              "roles": [
                "WORK_ORDER_APPROVER"
              ]
            },
            {
              "action": "REJECT",
              "nextState": "REJECTED",
              "roles": [
                "WORK_ORDER_APPROVER"
              ]
            },
            {
              "action": "SEND_BACK_TO_ORIGINATOR",
              "nextState": "PENDING_FOR_CORRECTION",
              "roles": [
                "WORK_ORDER_APPROVER"
              ]
            }
          ]
        },
        {
          "sla": 604800000,
          "state": "APPROVED",
          "applicationStatus": "APPROVED",
          "docUploadRequired": false,
          "isStartState": false,
          "isTerminateState": false,
          "isStateUpdatable": true,
          "actions": [
            {
              "action": "ACCEPT",
              "nextState": "ACCEPTED",
              "roles": [
                "ORG_ADMIN"
              ]
            },
            {
              "action": "DECLINE",
              "nextState": "PENDING_FOR_REASSIGNMENT",
              "roles": [
                "ORG_ADMIN"
              ]
            },
            {
              "action": "REJECT",
              "nextState": "REJECTED",
              "roles": [
                "ORG_ADMIN"
              ]
            }
          ]
        },
        {
          "sla": 86400000,
          "state": "PENDING_FOR_CORRECTION",
          "applicationStatus": "SENT_BACK",
          "docUploadRequired": false,
          "isStartState": true,
          "isTerminateState": false,
          "isStateUpdatable": true,
          "actions": [
            {
              "action": "EDIT",
              "nextState": "PENDING_FOR_VERIFICATION",
              "roles": [
                "WORK_ORDER_CREATOR"
              ]
            },
            {
              "action": "REJECT",
              "nextState": "REJECTED",
              "roles": [
                "WORK_ORDER_CREATOR"
              ]
            }
          ]
        },
        {
          "sla": 86400000,
          "state": "PENDING_FOR_REASSIGNMENT",
          "applicationStatus": "DECLINED",
          "docUploadRequired": false,
          "isStartState": true,
          "isTerminateState": false,
          "isStateUpdatable": true,
          "actions": [
            {
              "action": "EDIT",
              "nextState": "PENDING_FOR_VERIFICATION",
              "roles": [
                "WORK_ORDER_CREATOR"
              ]
            },
            {
              "action": "REJECT",
              "nextState": "REJECTED",
              "roles": [
                "WORK_ORDER_CREATOR"
              ]
            }
          ]
        },
        {
          "sla": null,
          "state": "ACCEPTED",
          "applicationStatus": "ACCEPTED",
          "docUploadRequired": false,
          "isStartState": false,
          "isTerminateState": true,
          "isStateUpdatable": false,
          "actions": [
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
          "actions": [
          ]
        }
      ]
    }
  ]
```
{% endcode %}

### Persister Configuration

Please make sure that the file[ <mark style="color:purple;">contract-service-persister.yml</mark>](https://github.com/egovernments/configs/blob/e3cca4152e63d9b671ed34c2e0fa321f1b4da87c/works/egov-persister/contract-service-persister.yml) is present in the **`configs`** repository in the below location.&#x20;

[https://github.com/\<YOUR ORGANISATION>/works-configs/tree/DEV/egov-persister](https://github.com/egovernments/works-configs/tree/DEV/egov-persister)

If not present, please make sure to add the persister YML file.&#x20;

{% hint style="warning" %}
Make sure to restart MDMS and the persister service after adding the file at the above location.
{% endhint %}

### Indexer Configuration

Please make sure that the file [<mark style="color:blue;">contractservices-indexer.yml</mark>](https://github.com/egovernments/configs/blob/e3cca4152e63d9b671ed34c2e0fa321f1b4da87c/works/egov-indexer/contractservices-indexer.yml) is present in the **`configs`** repository in the below location.&#x20;

[https://github.com/\{{your organisation\}}/works-configs/tree/DEV/egov-indexer](https://github.com/egovernments/works-configs/tree/DEV/egov-indexer)

### Inbox Configuration

In the MDMS repository, locate the[ inbox configuration file](https://github.com/egovernments/egov-mdms-data/blob/0dd049ffddbc7c6078b940b5eb9eb4951eb8996a/data/pg/inbox-v2/InboxConfiguration.json). Make sure the following JSON is added to the inbox configuration:

{% code lineNumbers="true" %}
```json
{
  "module": "contract-service",
  "index": "contract-inbox",
  "allowedSearchCriteria": [
    {
      "name": "tenantId",
      "path": "Data.tenantId.keyword",
      "isMandatory": true,
      "operator": "EQUAL"
    },
    {
      "name": "workOrderNumber",
      "path": "Data.contractNumber.keyword",
      "isMandatory": false,
      "operator": "EQUAL"
    },
    {
      "name": "revisedWorkOrderNumber",
      "path": "Data.supplementNumber.keyword",
      "isMandatory": false,
      "operator": "EQUAL"
    },
    {
      "name": "status",
      "path": "Data.currentProcessInstance.state.uuid.keyword",
      "isMandatory": false
    },
    {
      "name": "projectId",
      "path": "Data.additionalDetails.projectId.keyword",
      "isMandatory": false,
      "operator": "EQUAL"
    },
    {
      "name": "projectType",
      "path": "Data.additionalDetails.projectType.keyword",
      "isMandatory": false,
      "operator": "EQUAL"
    },
    {
      "name": "ward",
      "path": "Data.additionalDetails.ward.keyword",
      "isMandatory": false,
      "operator": "EQUAL"
    },
    {
      "name": "locality",
      "path": "Data.additionalDetails.locality.keyword",
      "isMandatory": false,
      "operator": "EQUAL"
    },
    {
      "name": "wfStatus",
      "path": "Data.contractStatus.keyword",
      "isMandatory": false
    },
    {
      "name": "assignee",
      "path": "Data.currentProcessInstance.assignes.uuid.keyword",
      "isMandatory": false
    }
  ],
  "sortBy": {
    "path": "Data.auditDetails.createdTime",
    "defaultOrder": "DESC"
  },
  "sourceFilterPathList": [
    "Data.contractNumber",
    "Data.businessService",
    "Data.additionalDetails.projectName",
    "Data.additionalDetails.projectId",
    "Data.additionalDetails.orgName",
    "Data.currentProcessInstance",
    "Data.totalContractedAmount",
    "Data.auditDetails"
  ]
}
```
{% endcode %}

{% hint style="warning" %}
Restart the Inbox service after updating the above configuration
{% endhint %}

## Integration

The API specifications for this service are located [here](https://works.digit.org/v/works-v1.0-in-progress/platform/architecture/low-level-design/services/contracts#api-contract-link). Postman scripts are available [here](https://github.com/egovernments/DIGIT-Works/blob/develop/backend/contracts/Contract\_Service\_Postman\_Scripts.postman\_collection.json) for reference to understand the request payloads.&#x20;
