---
description: Detailed description of configuring the contract service
---

# Contract

### Overview

The contract service provides the functionality of a works contract.&#x20;

### Pre-requisites

A running DIGIT platform is needed to deploy the contract service. Specifically, the following dependencies are needed:

* Estimate
* Organisation
* User
* Persister
* Indexer

### Functionality

This service provides APIs to create, update and search for contracts. Please refer to the functional specifications for detailed scope and functionality. Low-level technical design is available here.&#x20;

### Deployment

Below are the variables that should be configured for the contract service in the Helm environment file prior to deployment. The Helm environment file will be located under:

`https://github.com/`<mark style="color:red;">`{{ORG}}`</mark>`/DIGIT-DevOps/deploy-as-code/helm/environments/`<mark style="color:red;">`{{EnvironmentFile}}`</mark>`.yaml`

Please refer to a [sample here](https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/environments/works-dev.yaml).

* Add db-host,db-name,db-url,domain and all the digit core platform services configurations (Idgen, workflow,user etc.) in the YAML file.
* Add contract-service related environment variables’ value like the way it's done in [‘dev](https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/environments/works-dev.yaml#L206)’ environment yaml file. Search for "contract-service" in the file.&#x20;
* Add the ‘[egov-mdms-service](https://github.com/egovernments/DIGIT-DevOps/blob/5a9eb4c6141e19bd747238889ceed9bc9fffdc6f/deploy-as-code/helm/environments/works-dev.yaml#L190)’ related configuration to the respective environment yaml file. Make sure you change the gitsync.branch name.
* Check the contract-service persister file is added in the **`egov-persister.perister-yml-path`** variable. If not, please add the way it's done [here](https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/environments/works-dev.yaml#L310).
* Make sure to add the DB(Postgres and flyway) username & password in the respective environment secret yaml file the way it's done [here](https://github.com/egovernments/DIGIT-DevOps/blob/e742a292f2966bb1affb3b03edd643a777917ba1/deploy-as-code/helm/environments/works-dev-secrets.yaml#L3).
* Make sure to add the digit core services related secrets are configured in the respective environment secret file the way it's done [here](https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/environments/works-dev-secrets.yaml).

{% hint style="info" %}
Restart egov-mdms-service, egov-persister, egov-indexer, inbox, egov-workflow-v2, egov-accesscontrol and zuul after the above changes are performed.
{% endhint %}

### Configuration

#### Configure Actions

Add all the APIs exposed by the contract service (refer to table below for actual APIs) to the actions.json file in MDMS

**Module name:** ACCESSCONTROL-ACTIONS-TEST

**Master name:** actions-test

#### Configure Roles

Configure roles based on the roles column below in roles.json file.&#x20;

**Module name:** ACCESSCONTROL-ROLES

**Master name:** roles

#### Configure Role-Action:

Role-action mapping is configured in MDMS per the table belowAdd .&#x20;

**Module name:** ACCESSCONTROL-ROLEACTIONS

**Master name:** roleactions.json

| Role                  | APIs                   |
| --------------------- | ---------------------- |
| WORK\_ORDER\_CREATOR  | /contract/v1/\_create  |
|                       | /contract/v1/\_update  |
|                       | /contract/v1/\_search  |
|                       | /inbox/v2/\_search     |
|                       | /wms/contract/\_search |
| WORK\_ORDER\_VERIFIER | /contract/v1/\_update  |
|                       | /contract/v1/\_search  |
|                       | /inbox/v2/\_search     |
|                       | /wms/contract/\_search |
| WORK\_ORDER\_APPROVER | /contract/v1/\_update  |
|                       | /contract/v1/\_search  |
|                       | /inbox/v2/\_search     |
| WORK\_ORDER\_VIEWER   | /contract/v1/\_search  |
|                       | /wms/contract/\_search |

These have to be translated into JSON in the role-action mapping module in MDMS.

The physical location of the file in MDMS can be anywhere as long as the module name and master name are defined correctly. Typically, a folder called [ACCESSCONTROL-ROLEACTIONS](https://github.com/egovernments/works-mdms-data/tree/DEV/data/pg/ACCESSCONTROL-ROLEACTIONS) is defined under a tenant folder for clarity purposes. Example is [here](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/ACCESSCONTROL-ROLEACTIONS/roleactions.json). But this is not mandatory.&#x20;

#### Other masters to be added:

The following masters are to be added as per the table below:

| CBO Roles    | [https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/ContractCBORoles.json](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/ContractCBORoles.json)               |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| OCI Roles    | [https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/ContractOfficerIncharge.json](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/ContractOfficerIncharge.json) |
| ContractType | [https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/ContractType.json](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/ContractType.json)                       |
| Overheads    | [https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/Overheads.json](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/works/Overheads.json)                             |

#### Idgen Configuration

Make sure the id format is configured in the ‘IdFormat.json’ file of the ‘common-masters’ module. Sample [is here](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/common-masters/IdFormat.json#L29-L32).&#x20;

| IDGen Format                                                                                                          |
| --------------------------------------------------------------------------------------------------------------------- |
| <p>{</p><p>      "format": "WO/[fy:yyyy-yy]/[SEQ_CONTRACT_NUM]",</p><p>      "idname": "contract.number"</p><p> }</p> |

### Workflow Configuration

The following Workflow JSON needs to be put in the request body of the `/egov-workflow-v2/egov-wf/businessservice/_create` API.&#x20;

{% hint style="info" %}
For more information on configuring workflow, please refer to the Workflow Service documentation here.
{% endhint %}

```json
"BusinessServices": [
    {
      "tenantId": "pg",
      "businessService": "contract-approval-mukta",
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

Sample CURL is also included below.&#x20;

{% hint style="warning" %}
Note that authToken and other requestInfo parameters should be updated as per your environment.
{% endhint %}

```
curl --location 'http://localhost:8020/egov-workflow-v2/egov-wf/businessservice/_update' \
--header 'Content-Type: application/json' \
--data '{
    "RequestInfo": {
    "apiId": "estimate",
    "action": "",
    "did": 1,
    "key": "",
    "msgId": "20170310130900|en_IN",
    "requesterId": "",
    "ts": 1513579888683,
    "ver": "1.0.0",
    "authToken": "{{REPLACE THIS}}",
    "userInfo": {
      "uuid": "{{REPLACE WITH VALID USER ID}}"
    }
  },
  "BusinessServices": [
        {
            "tenantId": "pg",
            "uuid": "c798a157-b494-4b61-acb9-6c5923f2fc10",
            "businessService": "mukta-estimate",
            "business": "estimate-service",
            "businessServiceSla": 432000000,
            "states": [
                {
                    "auditDetails": {
                        "createdBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                        "lastModifiedBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                        "createdTime": 1678950370209,
                        "lastModifiedTime": 1678950370209
                    },
                    "uuid": "35fd0feb-319f-4af2-bfa1-faa770ec05cb",
                    "tenantId": "pg",
                    "businessServiceId": "c798a157-b494-4b61-acb9-6c5923f2fc10",
                    "sla": null,
                    "state": null,
                    "applicationStatus": null,
                    "docUploadRequired": false,
                    "isStartState": true,
                    "isTerminateState": false,
                    "isStateUpdatable": true,
                    "actions": [
                        {
                            "auditDetails": {
                                "createdBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "lastModifiedBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "createdTime": 1678950370209,
                                "lastModifiedTime": 1678950370209
                            },
                            "uuid": "a5689bee-5d02-4311-9ad4-62959bb50e8c",
                            "tenantId": "pg",
                            "currentState": "35fd0feb-319f-4af2-bfa1-faa770ec05cb",
                            "action": "SUBMIT",
                            "nextState": "6cc0eebd-e9f5-485b-94cd-cd28e7733974",
                            "roles": [
                                "ESTIMATE_CREATOR"
                            ],
                            "active": true
                        }
                    ]
                },
                {
                    "auditDetails": {
                        "createdBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                        "lastModifiedBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                        "createdTime": 1678950370209,
                        "lastModifiedTime": 1678950370209
                    },
                    "uuid": "6cc0eebd-e9f5-485b-94cd-cd28e7733974",
                    "tenantId": "pg",
                    "businessServiceId": "c798a157-b494-4b61-acb9-6c5923f2fc10",
                    "sla": 172800000,
                    "state": "PENDINGFORVERIFICATION",
                    "applicationStatus": "SUBMITTED",
                    "docUploadRequired": false,
                    "isStartState": true,
                    "isTerminateState": false,
                    "isStateUpdatable": true,
                    "actions": [
                        {
                            "auditDetails": {
                                "createdBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "lastModifiedBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "createdTime": 1678950370209,
                                "lastModifiedTime": 1678950370209
                            },
                            "uuid": "381cfe14-296f-4e03-8475-31495341a788",
                            "tenantId": "pg",
                            "currentState": "6cc0eebd-e9f5-485b-94cd-cd28e7733974",
                            "action": "VERIFYANDFORWARD",
                            "nextState": "98a0383d-5367-4f1e-a4f2-82a0b7ad6b9f",
                            "roles": [
                                "ESTIMATE_VERIFIER"
                            ],
                            "active": true
                        },
                        {
                            "auditDetails": {
                                "createdBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "lastModifiedBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "createdTime": 1678950370209,
                                "lastModifiedTime": 1678950370209
                            },
                            "uuid": "ca298290-42db-47c0-ae1d-f2e1249cc582",
                            "tenantId": "pg",
                            "currentState": "6cc0eebd-e9f5-485b-94cd-cd28e7733974",
                            "action": "SENDBACK",
                            "nextState": "06da8fe1-1d68-4ea8-9409-217182b58846",
                            "roles": [
                                "ESTIMATE_VERIFIER"
                            ],
                            "active": true
                        },
                        {
                            "auditDetails": {
                                "createdBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "lastModifiedBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "createdTime": 1678950370209,
                                "lastModifiedTime": 1678950370209
                            },
                            "uuid": "8dcacc97-36a4-42f1-8fab-8393cb3171c8",
                            "tenantId": "pg",
                            "currentState": "6cc0eebd-e9f5-485b-94cd-cd28e7733974",
                            "action": "REJECT",
                            "nextState": "37615e97-0eba-4022-be8b-3feaf0bf4441",
                            "roles": [
                                "ESTIMATE_VERIFIER"
                            ],
                            "active": true
                        }
                    ]
                },
                {
                    "auditDetails": {
                        "createdBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                        "lastModifiedBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                        "createdTime": 1678950370209,
                        "lastModifiedTime": 1678950370209
                    },
                    "uuid": "98a0383d-5367-4f1e-a4f2-82a0b7ad6b9f",
                    "tenantId": "pg",
                    "businessServiceId": "c798a157-b494-4b61-acb9-6c5923f2fc10",
                    "sla": 86400000,
                    "state": "PENDINGFORTECHNICALSANCTION",
                    "applicationStatus": "VERIFIED",
                    "docUploadRequired": false,
                    "isStartState": false,
                    "isTerminateState": false,
                    "isStateUpdatable": true,
                    "actions": [
                        {
                            "auditDetails": {
                                "createdBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "lastModifiedBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "createdTime": 1678950370209,
                                "lastModifiedTime": 1678950370209
                            },
                            "uuid": "bf5e5d56-9662-4077-b08b-fd3a678942d2",
                            "tenantId": "pg",
                            "currentState": "98a0383d-5367-4f1e-a4f2-82a0b7ad6b9f",
                            "action": "TECHNICALSANCTION",
                            "nextState": "c3249e25-9d3b-4b6f-9029-8a69b0b60415",
                            "roles": [
                                "TECHNICAL_SANCTIONER"
                            ],
                            "active": true
                        },
                        {
                            "auditDetails": {
                                "createdBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "lastModifiedBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "createdTime": 1678950370209,
                                "lastModifiedTime": 1678950370209
                            },
                            "uuid": "bb623a34-015b-4ce2-8167-d5333b5ffbce",
                            "tenantId": "pg",
                            "currentState": "98a0383d-5367-4f1e-a4f2-82a0b7ad6b9f",
                            "action": "SENDBACK",
                            "nextState": "6cc0eebd-e9f5-485b-94cd-cd28e7733974",
                            "roles": [
                                "TECHNICAL_SANCTIONER"
                            ],
                            "active": true
                        },
                        {
                            "auditDetails": {
                                "createdBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "lastModifiedBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "createdTime": 1678950370209,
                                "lastModifiedTime": 1678950370209
                            },
                            "uuid": "b08b8f1d-6fc6-49ab-98c2-887b90ff5d90",
                            "tenantId": "pg",
                            "currentState": "98a0383d-5367-4f1e-a4f2-82a0b7ad6b9f",
                            "action": "SENDBACKTOORIGINATOR",
                            "nextState": "06da8fe1-1d68-4ea8-9409-217182b58846",
                            "roles": [
                                "TECHNICAL_SANCTIONER"
                            ],
                            "active": true
                        },
                        {
                            "auditDetails": {
                                "createdBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "lastModifiedBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "createdTime": 1678950370209,
                                "lastModifiedTime": 1678950370209
                            },
                            "uuid": "0dacba16-22bf-44e3-bdc9-8dc54c215cbf",
                            "tenantId": "pg",
                            "currentState": "98a0383d-5367-4f1e-a4f2-82a0b7ad6b9f",
                            "action": "REJECT",
                            "nextState": "37615e97-0eba-4022-be8b-3feaf0bf4441",
                            "roles": [
                                "TECHNICAL_SANCTIONER"
                            ],
                            "active": true
                        }
                    ]
                },
                {
                    "auditDetails": {
                        "createdBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                        "lastModifiedBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                        "createdTime": 1678950370209,
                        "lastModifiedTime": 1678950370209
                    },
                    "uuid": "c3249e25-9d3b-4b6f-9029-8a69b0b60415",
                    "tenantId": "pg",
                    "businessServiceId": "c798a157-b494-4b61-acb9-6c5923f2fc10",
                    "sla": 86400000,
                    "state": "PENDINGFORAPPROVAL",
                    "applicationStatus": "TECHNICALLY SANCTIONED",
                    "docUploadRequired": false,
                    "isStartState": false,
                    "isTerminateState": false,
                    "isStateUpdatable": true,
                    "actions": [
                        {
                            "auditDetails": {
                                "createdBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "lastModifiedBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "createdTime": 1678950370209,
                                "lastModifiedTime": 1678950370209
                            },
                            "uuid": "bbb05598-8a74-42c4-8e04-b9499c571fda",
                            "tenantId": "pg",
                            "currentState": "c3249e25-9d3b-4b6f-9029-8a69b0b60415",
                            "action": "SENDBACK",
                            "nextState": "98a0383d-5367-4f1e-a4f2-82a0b7ad6b9f",
                            "roles": [
                                "ESTIMATE_APPROVER"
                            ],
                            "active": true
                        },
                        {
                            "auditDetails": {
                                "createdBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "lastModifiedBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "createdTime": 1678950370209,
                                "lastModifiedTime": 1678950370209
                            },
                            "uuid": "94d39cba-3271-4dae-b014-8eae07657bcc",
                            "tenantId": "pg",
                            "currentState": "c3249e25-9d3b-4b6f-9029-8a69b0b60415",
                            "action": "SENDBACKTOORIGINATOR",
                            "nextState": "06da8fe1-1d68-4ea8-9409-217182b58846",
                            "roles": [
                                "ESTIMATE_APPROVER"
                            ],
                            "active": true
                        },
                        {
                            "auditDetails": {
                                "createdBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "lastModifiedBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "createdTime": 1678950370209,
                                "lastModifiedTime": 1678950370209
                            },
                            "uuid": "97e550ff-20eb-4fd5-85ae-e395ba9dd358",
                            "tenantId": "pg",
                            "currentState": "c3249e25-9d3b-4b6f-9029-8a69b0b60415",
                            "action": "APPROVE",
                            "nextState": "fcd34bba-9f52-4de6-9a16-2a50315cfb91",
                            "roles": [
                                "ESTIMATE_APPROVER"
                            ],
                            "active": true
                        },
                        {
                            "auditDetails": {
                                "createdBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "lastModifiedBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "createdTime": 1678950370209,
                                "lastModifiedTime": 1678950370209
                            },
                            "uuid": "eaca07c5-d361-41a2-8d77-0063a075d2f3",
                            "tenantId": "pg",
                            "currentState": "c3249e25-9d3b-4b6f-9029-8a69b0b60415",
                            "action": "REJECT",
                            "nextState": "37615e97-0eba-4022-be8b-3feaf0bf4441",
                            "roles": [
                                "ESTIMATE_APPROVER"
                            ],
                            "active": true
                        }
                    ]
                },
                {
                    "auditDetails": {
                        "createdBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                        "lastModifiedBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                        "createdTime": 1678950370209,
                        "lastModifiedTime": 1678950370209
                    },
                    "uuid": "06da8fe1-1d68-4ea8-9409-217182b58846",
                    "tenantId": "pg",
                    "businessServiceId": "c798a157-b494-4b61-acb9-6c5923f2fc10",
                    "sla": 86400000,
                    "state": "PENDINGFORCORRECTION",
                    "applicationStatus": "SENT BACK",
                    "docUploadRequired": false,
                    "isStartState": false,
                    "isTerminateState": false,
                    "isStateUpdatable": true,
                    "actions": [
                        {
                            "auditDetails": {
                                "createdBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "lastModifiedBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "createdTime": 1678950370209,
                                "lastModifiedTime": 1678950370209
                            },
                            "uuid": "6228efd7-30c5-4bef-ae67-0c6517707b37",
                            "tenantId": "pg",
                            "currentState": "06da8fe1-1d68-4ea8-9409-217182b58846",
                            "action": "RE-SUBMITTED",
                            "nextState": "6cc0eebd-e9f5-485b-94cd-cd28e7733974",
                            "roles": [
                                "ESTIMATE_CREATOR"
                            ],
                            "active": true
                        },
                        {
                            "auditDetails": {
                                "createdBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "lastModifiedBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                                "createdTime": 1678950370209,
                                "lastModifiedTime": 1678950370209
                            },
                            "uuid": "fc711556-4849-4ca1-a47b-54f3facaac79",
                            "tenantId": "pg",
                            "currentState": "06da8fe1-1d68-4ea8-9409-217182b58846",
                            "action": "REJECT",
                            "nextState": "37615e97-0eba-4022-be8b-3feaf0bf4441",
                            "roles": [
                                "ESTIMATE_CREATOR"
                            ],
                            "active": true
                        }
                    ]
                },
                {
                    "auditDetails": {
                        "createdBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                        "lastModifiedBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                        "createdTime": 1678950370209,
                        "lastModifiedTime": 1678950370209
                    },
                    "uuid": "fcd34bba-9f52-4de6-9a16-2a50315cfb91",
                    "tenantId": "pg",
                    "businessServiceId": "c798a157-b494-4b61-acb9-6c5923f2fc10",
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
                    "auditDetails": {
                        "createdBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                        "lastModifiedBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                        "createdTime": 1678950370209,
                        "lastModifiedTime": 1678950370209
                    },
                    "uuid": "37615e97-0eba-4022-be8b-3feaf0bf4441",
                    "tenantId": "pg",
                    "businessServiceId": "c798a157-b494-4b61-acb9-6c5923f2fc10",
                    "sla": null,
                    "state": "REJECTED",
                    "applicationStatus": "REJECTED",
                    "docUploadRequired": false,
                    "isStartState": false,
                    "isTerminateState": true,
                    "isStateUpdatable": false,
                    "actions": null
                }
            ],
            "auditDetails": {
                "createdBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                "lastModifiedBy": "7e46e32c-187c-4fb4-9d6b-1ac70fa8f011",
                "createdTime": 1678950370209,
                "lastModifiedTime": 1678950370209
            }
        }
    ]
}'l
```

### Persister Configuration

Please make sure that the file[ <mark style="color:purple;"><mark style="color:orange;">contract-service-persister.yml<mark style="color:orange;"></mark>](https://github.com/egovernments/works-configs/blob/DEV/egov-persister/contract-service-persister.yml) is present in the **`configs`** repository in the below location.&#x20;

[https://github.com/\<YOUR ORGANISATION>/works-configs/tree/DEV/egov-persister\
](https://github.com/egovernments/works-configs/tree/DEV/egov-persister)

If not present, please make sure to add the persister YML file.&#x20;

{% hint style="warning" %}
Make sure to restart MDMS and the persister service after adding the file at the above location.
{% endhint %}

### Indexer Configuration

Please make sure that the file [<mark style="color:blue;">contractservices-indexer.yml</mark>](https://github.com/egovernments/works-configs/blob/DEV/egov-indexer/contractservices-indexer.yml) is present in the **`configs`** repository in the below location.&#x20;

[https://github.com/\{{your organisation\}}/works-configs/tree/DEV/egov-indexer](https://github.com/egovernments/works-configs/tree/DEV/egov-indexer)

### Inbox Configuration

In the MDMS repository, locate the[ inbox configuration file](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/inbox-v2/InboxConfiguration.json). Make sure the following JSON is added to the inbox configuration:

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
          "isMandatory": true,
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
      "sourceFilterPathList": ["Data.contractNumber" ,"Data.additionalDetails.projectName","Data.additionalDetails.orgName", "Data.currentProcessInstance", "Data.totalContractedAmount", "Data.auditDetails"]
    }
```

{% hint style="warning" %}
Restart the Inbox service after updating above configuration
{% endhint %}

### Integration

The API specifications for this service are located [here](https://works.digit.org/platform/specifications/technical-specifications/low-level-design/services/contracts#api-contract-link). Postman scripts are also provided here for reference to understand the request payloads.&#x20;
