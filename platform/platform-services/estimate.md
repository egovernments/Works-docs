# Estimate

## Overview

Estimate Service allows users to create estimates and forward them for Workflow approval to higher authorities across departments for technical, financial, and admin sanctions. A prepared estimate can then be tendered out for contracting.

### Dependencies

* Project
* MDMS
* Workflow
* Notification
* Access Control
* User
* IDGen

### Key Functionality

* Create/update/search for Work estimates for a project.&#x20;
* Allows upload of offline documents related to estimate creation as part of create.
* Workflow and inbox integration

### Code

[Estimate](https://github.com/egovernments/DIGIT-Works/tree/master/backend/estimates)

### Deployment

[Helm chart](https://github.com/egovernments/DIGIT-DevOps/tree/digit-works/deploy-as-code/helm/charts/digit-works/backend/estimates)

### Master Data

| Master Name | Sample Data | Description                                                                                                           |
| ----------- | ----------- | --------------------------------------------------------------------------------------------------------------------- |
| Overheads   | Sample      | Contains the overhead charges applicable on an estimate.                                                              |
| SOR (TBD)   | TBD         | Contains a comprehensive list of items and rates defined by the department. To be used in preparation of an estimate. |

### Integration

**Base Path:** /estimates/

[API spec](../architecture/low-level-design/services/estimates.md#api-contract-link)

Postman collection for this service is [available here](https://raw.githubusercontent.com/egovernments/DIGIT-Works/master/backend/estimates/Estimate\_Service\_Collection.postman\_collection.json).&#x20;
