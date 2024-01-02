# Measurement Book Service

## Overview

The Measurement Registry captures measurement data according to the estimate and contract. Line items from estimate are validated and measurement data are added as part of the create and update API.

### Dependencies

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

### Key Functionality

* This service is an addendum to the measurement book registry.
* The service validates if data is according to the estimate and contract line items.
* It also captures workflow of a given measurement.
* The service sends sms notification to the concerned person with project id.

### Code

[Measurement book service](https://github.com/egovernments/DIGIT-Works/tree/6d58b3f8674334f2ad4b838bb383253faa9fe092/backend/measurement-service)

### Deployment

[Measurement book service helm charts](https://github.com/egovernments/DIGIT-DevOps/tree/2f99b0978d5581b30cf10ffbae27e8d48d309948/deploy-as-code/helm/charts/digit-works/backend/measurement-service)

### Integration

API [contract](../architecture/low-level-design/services/detailed-measurement-book.md#api-contract-link)

[Postman collection](https://github.com/egovernments/DIGIT-Works/blob/6afb2f0df23c43c67c252ddf8817c6d79481a73b/backend/measurement-service/docs/Measurement.postman\_collection.json)
