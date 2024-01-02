# Expense

## Overview

The expense module implements the functionality of bills and payments. A bill or a group of bills can be aggregated together as payments. Payments advice can be submitted through integration with IFMS (Integrated Financial Management Systems) or any other third party payments provider. The expense module always works in combination with a calculator service. The calculator service is implementation specific and provides business logic to compute bills. The calculator calls into the expense service to create bills. In general, the expense create/update APIs are not called by any other module other than the calculator. For more information on the sample calculator provided with the Works platform, please navigate here.&#x20;

### Dependencies

* DIGIT backbone services
* Persister
* Indexer
* IDGen
* MDMS
* Workflow
* Notification

### Key Functionality

* Create/update/search functionality for bills
* Ability to create different bill types according to configuration.
* Workflow is integrated and needs to be configured for usage.
* Works with an expense calculator that contains the business logic to compute bills.&#x20;

### Code

[Expense Module](https://github.com/egovernments/DIGIT-Works/tree/master/backend/expense)

### Deployment

[Helm Chart](https://github.com/egovernments/DIGIT-DevOps/tree/digit-works/deploy-as-code/helm/charts/digit-works/backend/expense)

### Master Data&#x20;

HeadCodes

### Integration

[API spec](../architecture/low-level-design/services/expense.md#api-specifications)

Postman TBD
