---
description: Provides an overview of the configuration of the estimate service
---

# Estimate

## Overview

The estimate service provides the functionality to create, update and search for estimates related to a Works project. An estimate is always linked to a project. For low-level technical design, please refer to this section.

## Pre-requisites

The following services need to be running for the estimate service to function:

* DIGIT backbone services (PostgreSQL, Elastic Search, Zuul)
* Project&#x20;
* MDMS
* Persister
* Indexer
* Workflow
* User
* [IDGen](https://core.digit.org/platform/core-services/id-generation-service)
* MDMS V2
* Contract Service
* Measurement Service

## Functionality

Refer to the [functional specifications](../../functional-specifications/estimates.md) for details on the capabilities supported by this service.

## Configuration

### MDMS Configuration

Configure roles, actions and role-action mappings as per the table below by referring to this document:

<table><thead><tr><th width="276.3333333333333">Role</th><th width="514">APIs</th></tr></thead><tbody><tr><td>ESTIMATE_CREATOR</td><td>/estimate-service/estimate/v1/_create</td></tr><tr><td></td><td>/estimate-service/estimate/v1/_search</td></tr><tr><td></td><td>/wms/estimate/_search</td></tr><tr><td>ESTIMATE_VERIFIER</td><td>/estimate-service/estimate/v1/_update</td></tr><tr><td></td><td>/estimate-service/estimate/v1/_search</td></tr><tr><td></td><td>/wms/estimate/_search</td></tr><tr><td>TECHNICAL_SANCTIONER</td><td>/estimate-service/estimate/v1/_update</td></tr><tr><td></td><td>/estimate-service/estimate/v1/_search</td></tr><tr><td></td><td>/wms/estimate/_search</td></tr><tr><td>ESTIMATE_APPROVER</td><td>/estimate-service/estimate/v1/_update</td></tr><tr><td></td><td>/estimate-service/estimate/v1/_search</td></tr><tr><td></td><td>/wms/estimate/_search</td></tr><tr><td>ESTIMATE_VIEWER</td><td>/estimate-service/estimate/v1/_search</td></tr><tr><td></td><td>/wms/estimate/_search</td></tr><tr><td>EMPLOYEE_COMMON</td><td>/inbox/v2/_search</td></tr></tbody></table>

Refer to the sample [here](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/ACCESSCONTROL-ROLEACTIONS/roleactions.json).&#x20;

### Persister Configuration&#x20;

The persister file for the service is called `estimate-service.yml`.

[https://github.com/egovernments/configs/blob/UNIFIED-DEV/works/egov-persister/estimate-service.yml](https://github.com/egovernments/configs/blob/UNIFIED-DEV/works/egov-persister/estimate-service.yml)

Follow the steps [here](./#persister-configuration) for configuring this.

### Indexer Configuration

Ensure the below files are present in [https://github.com/egovernments/configs/blob/UNIFIED-DEV/works/egov-indexer/estimateservices-indexer.yml](https://github.com/egovernments/configs/blob/UNIFIED-DEV/works/egov-indexer/estimateservices-indexer.yml)

In case the above files are not present, add them in the given location and restart the ‘egov-indexer’  service in the respective environment. Before restarting the service ensure the below configurations are done.

{% hint style="info" %}
**Note:** Add [this config](https://github.com/egovernments/DIGIT-DevOps/pull/1101/commits/5a31196d78e8aa537a3176f67f4b1951e1306a0f) in the respective environment YAML file in the DevOps repository and then deploy the service.
{% endhint %}

### Idgen Configuration

In the common-masters folder of MDMS, locate the IDFormat.json file. ID formats should be configured for the Estimate number as well as Estimate Detail objects. Make sure the following lines are added and the format modified per implementation:

```json
{
  "tenantId": "pg",
  "moduleName": "common-masters",
  "IdFormat": [
    {
      "format": "ES/[fy:yyyy-yy]/[SEQ_ESTIMATE_NUM]",
      "idname": "estimate.number"
    },
    {
      "format": "RE/[fy:yyyy-yy]/[SEQ_ESTIMATE_REVISION_NUM]",
      "idname": "estimate.revision.number"
    }]
}
```

#### Other masters for Estimate:

The following masters need to be configured for the Estimate service. Please make sure to use the same master name and module names:

[UOM - Unit of measurement](https://github.com/egovernments/works-mdms-data/blob/UAT/data/statea/common-masters/uom.json)

[Overheads](https://github.com/egovernments/works-mdms-data/blob/UAT/data/statea/works/Overheads.json)

### Workflow Configuration

The workflow configuration for Estimate is as follows. This payload needs to be called against businessService \_create API for workflow configuration:

{% code lineNumbers="true" %}
```sh
"BusinessServices": [
    {
      "tenantId": "statea",
      "businessService": "ESTIMATE",
      "business": "estimate-service",
      "businessServiceSla": 432000000,
      "states": [
	  {
          "sla": null,
          "state": null,
          "applicationStatus": "SUBMITTED",
          "docUploadRequired": false,
          "isStartState": true,
          "isTerminateState": false,
          "isStateUpdatable": true,
          "actions": [
            {
              "action": "SUBMIT",
              "nextState": "PENDINGFORVERIFICATION",
              "roles": [
                "ESTIMATE_CREATOR"
              ]
            }
          ]
        },
        {
          "sla": 172800000,
          "state": "PENDINGFORVERIFICATION",
          "applicationStatus": "VERIFIED",
          "docUploadRequired": false,
          "isStartState": true,
          "isTerminateState": false,
          "isStateUpdatable": true,
          "actions": [
            {
              "action": "VERIFYANDFORWARD",
              "nextState": "PENDINGFORTECHNICALSANCTION",
              "roles": [
                "ESTIMATE_VERIFIER"
              ]
            },
            {
              "action": "SENDBACK",
              "nextState": "PENDINGFORCORRECTION",
              "roles": [
                "ESTIMATE_VERIFIER"
              ]
            },
            {
              "action": "REJECT",
              "nextState": "REJECTED",
              "roles": [
				"ESTIMATE_VERIFIER"
              ]
            }
          ]
        },
        {
          "sla": 86400000,
          "state": "PENDINGFORTECHNICALSANCTION",
          "applicationStatus": "TECHNICALLY SANCTIONED",
          "docUploadRequired": false,
          "isStartState": false,
          "isTerminateState": false,
          "isStateUpdatable": true,
          "actions": [
            {
              "action": "TECHNICALSANCTION",
              "nextState": "PENDINGFORAPPROVAL",
              "roles": [
                "TECHNICAL_SANCTIONER"
              ]
            },
            {
              "action": "SENDBACK",
              "nextState": "PENDINGFORVERIFICATION",
              "roles": [
                "TECHNICAL_SANCTIONER"
              ]
            },
            {
              "action": "SENDBACKTOORIGINATOR",
              "nextState": "PENDINGFORCORRECTION",
              "roles": [
				"TECHNICAL_SANCTIONER"
              ]
            },
            {
              "action": "REJECT",
              "nextState": "REJECTED",
              "roles": [
				"TECHNICAL_SANCTIONER"
              ]
            }
          ]
        },
        {
          "sla": 86400000,
          "state": "PENDINGFORAPPROVAL",
          "applicationStatus": "SENT BACK",
          "docUploadRequired": false,
          "isStartState": false,
          "isTerminateState": false,
          "isStateUpdatable": true,
          "actions": [
            {
              "action": "SENDBACK",
              "nextState": "PENDINGFORTECHNICALSANCTION",
              "roles": [
                "ESTIMATE_APPROVER"
              ]
            },
            {
              "action": "SENDBACKTOORIGINATOR",
              "nextState": "PENDINGFORCORRECTION",
              "roles": [
				"ESTIMATE_APPROVER"	
              ]
            },
            {
              "action": "APPROVE",
              "nextState": "APPROVED",
              "roles": [
                "ESTIMATE_APPROVER"
              ]
            },
            {
              "action": "REJECT",
              "nextState": "REJECTED",
              "roles": [
				"ESTIMATE_APPROVER"	
              ]
            }
          ]
        },
        {
          "sla": 86400000,
          "state": "PENDINGFORCORRECTION",
          "applicationStatus": "RE-SUBMITTED",
          "docUploadRequired": false,
          "isStartState": false,
          "isTerminateState": false,
          "isStateUpdatable": true,
          "actions": [
            {
              "action": "RE-SUBMITTED",
              "nextState": "PENDINGFORVERIFICATION",
              "roles": [
                "ESTIMATE_CREATOR"
              ]
            },
            {
              "action": "SENDBACKTOORIGINATOR",
              "nextState": "PENDINGFORCORRECTION",
              "roles": [
                "ESTIMATE_CREATOR"
              ]
            },
            {
              "action": "REJECT",
              "nextState": "REJECTED",
              "roles": [
                "ESTIMATE_CREATOR"
              ]
            }
          ]
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
        }
      ]
    }
  ]
```
{% endcode %}

### Inbox Configuration

Inbox should be configured if Workflow is configured for the estimate service. If there is no workflow involved, this can be skipped.

Add the inbox-v2 configuration in a respective environment in MDMS as it has been done [here](https://github.com/egovernments/egov-mdms-data/blob/UNIFIED-DEV/data/pg/inbox-v2/InboxConfiguration.json). Below is the inbox configuration for the Estimate service:

{% code lineNumbers="true" %}
```
{
      "module": "estimate-service",
      "index": "estimate-inbox-v2",
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
          "name": "estimateId",
          "path": "Data.estimateNumber.keyword",
          "isMandatory": false
        },
        {
          "name": "department",
          "path": "Data.executingDepartment.keyword",
          "isMandatory": false
        },
        {
          "name": "typeOfWork",
          "path": "Data.project.projectType.keyword",
          "isMandatory": false
        },
        {
          "name": "projectId",
          "path": "Data.project.projectNumber.keyword",
          "isMandatory": false
        },
        {
          "name": "fromProposalDate",
          "path": "Data.proposalDate",
          "isMandatory": false,
          "operator": "GTE"
        },
        {
          "name": "toProposalDate",
          "path": "Data.proposalDate",
          "isMandatory": false,
          "operator": "LTE"
        },
        {
          "name": "createdBy",
          "path": "Data.auditDetails.createdBy.keyword",
          "isMandatory": false
        }
      ],
      "sortBy": {
          "path": "Data.auditDetails.createdTime",
          "defaultOrder": "ASC"
      },
      "sourceFilterPathList": ["Data.currentProcessInstance", "Data.auditDetails", "Data.additionalDetails"]
    }
```
{% endcode %}

[https://github.com/egovernments/egov-mdms-data/blob/UNIFIED-DEV/data/pg/inbox-v2/InboxConfiguration.json](https://github.com/egovernments/egov-mdms-data/blob/UNIFIED-DEV/data/pg/inbox-v2/InboxConfiguration.json)

## Deployment

The below variables should be configured well before the deployment of the estimate service build image. These are configured in the DevOps repository:

* Add these ‘db-host’,’db-name’,’db-url’, ’domain’ and all the digit core platform services configurations (Idgen, workflow, user etc.) in respective environments YAML file.
* Add estimate-service related environment variables’ value like the way it's done in [‘dev](https://github.com/egovernments/DIGIT-DevOps/blob/unified-env/deploy-as-code/helm/environments/unified-works-dev.yaml)’ environment YAML file.
* Add the ‘[egov-mdms-service](https://github.com/egovernments/DIGIT-DevOps/blob/5a9eb4c6141e19bd747238889ceed9bc9fffdc6f/deploy-as-code/helm/environments/works-dev.yaml#L190)’ related configuration to the respective environment YAML file. Make sure you change the gitsync.branch name.
* Check the estimate-service persister file is added in the egov-persister.perister-yml-path variable. If not, follow the steps outlined [here](https://github.com/egovernments/DIGIT-DevOps/blob/5a9eb4c6141e19bd747238889ceed9bc9fffdc6f/deploy-as-code/helm/environments/works-dev.yaml#L233).
* Make sure to add the DB(Postgres and flyway) username & password in the respective environment secret YAML file. Follow the steps given [here](https://github.com/egovernments/DIGIT-DevOps/blob/e742a292f2966bb1affb3b03edd643a777917ba1/deploy-as-code/helm/environments/works-dev-secrets.yaml#L3).
* Ensure that the DIGIT core services-related secrets are added to the respective environment secret file. Follow the steps given [here](https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/environments/works-dev-secrets.yaml).

## Integration

Postman scripts for Estimate are available here.
