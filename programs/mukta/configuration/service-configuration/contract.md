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

### Configuration

#### Configure Actions

#### Configure Roles and role-action mapping

Role-action mapping is configured per the table below in MDMS.&#x20;

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

### Integration

The API specifications for this service are located [here](https://works.digit.org/platform/specifications/technical-specifications/low-level-design/services/contracts#api-contract-link). Postman scripts are also provided here for reference to understand the request payloads.&#x20;
