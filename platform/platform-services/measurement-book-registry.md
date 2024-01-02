# Measurement Book Registry

## Overview

The Measurement Registry captures measurement data according. It was designed as a reusable registry by validating just documents.

### Dependencies

* DIGIT backbone services
* Persister
* Indexer
* IDGen
* MDMS
* FileStore

### Key Functionalities

* Models real world measurement book to keep record of measurements
* Measurements like length, breadth, height and number of units are taken as input and stored.
* Quantity can be directly or can be calculated by giving measurement data of length, breadth, height and number of units.
* Documents given are validated against fileStore service and stored in registry

### Code

[Measurement book registry](https://github.com/egovernments/DIGIT-Works/tree/6d58b3f8674334f2ad4b838bb383253faa9fe092/backend/measurement-registry)

### Deployment

[Measurement book registry helm charts](https://github.com/egovernments/DIGIT-DevOps/tree/2f99b0978d5581b30cf10ffbae27e8d48d309948/deploy-as-code/helm/charts/digit-works/backend/measurement-registry)

### Integration

API [contract](../architecture/low-level-design/services/detailed-measurement-book.md#api-contract-link)

[Postman collection](https://github.com/egovernments/DIGIT-Works/blob/6afb2f0df23c43c67c252ddf8817c6d79481a73b/backend/measurement-registry/docs/Measurement.postman\_collection.json)

###
