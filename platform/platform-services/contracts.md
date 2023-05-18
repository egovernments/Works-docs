# Contracts

## Overview

The contract service captures work orders or purchase orders. It validates the work order against the estimate(s).  Line items from one estimate can be put in a contract. Line items from multiple estimates can be aggregated into one work order as well. The contract service validates the line items from each estimate as part of create and update.

### Dependencies

* Estimate service
* IDGen
* MDMS
* Workflow
* User
* HRMS
* Organisation

### Key Functionalities

* Models a real world work order/contract&#x20;
* All line items of a single estimate can be put in a contract.
* Line items from multiple estimates can also be grouped into a contract.
* The service validates the estimate line items and ensures no duplication happens in including estimate line items in a contract.&#x20;
* Terms and conditions, milestones and payment calendar are WIP

### Code:

[Contracts](https://github.com/egovernments/DIGIT-Works/tree/master/backend/contracts)

### Deployment:

[Contract Helm charts](https://github.com/egovernments/DIGIT-DevOps/tree/digit-works/deploy-as-code/helm/charts/digit-works/backend/contracts)

### Master Data Types

Contract Type - defines different contract types

OIC Roles - defines Officer-in-charge roles

CBO Roles - defines the capacities in which an organisation can accept the contract.

### Integration

**Base path:**

`/contracts`

API [specification](../architecture/common-services/contracts-service/contracts-technical-docs.md#api-contract-link)

[Contracts postman collection](https://github.com/egovernments/DIGIT-Works/blob/master/backend/contracts/Contract\_Service\_Postman\_Scripts.postman\_collection.json)
