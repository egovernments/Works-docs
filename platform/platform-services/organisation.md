# Organisation

## Overview

This is being designed as a cross-functional registry that will house vendors, suppliers, contractors, non-profits, SHGs etc.. Can be used across domains.&#x20;

### Dependencies

* DIGIT backbone services
* Persister
* Indexer
* IDGen
* Individual&#x20;

## Key Functionalities

* Provides create/update/search operations for organisation entities.
* Captures organisation details, contact details and classifications.
* Links organisations to functional areas they are operational in.

### Code

[Organisation](https://github.com/egovernments/DIGIT-Works/tree/master/backend/organisation)

## Deployment

[Helm chart](https://github.com/egovernments/DIGIT-DevOps/tree/digit-works/deploy-as-code/helm/charts/digit-works/backend/organisation)

### Master Data

OrgType - Defines types of organisations

OrgFunctionCategory - The functional area where an organisation works

OrgFunctionClass - The class (rating) of an organisation in a specific functional area.

OrgTaxIdentifier - The list of tax identifiers that can be entered.

OrgTransferCode - The bank account transfer code (IFSC etc..). This is usually the only one defined in the master data. Can be customised for other countries.

## Integration

[API spec](../architecture/low-level-design/registries/organization.md#api-specification)

[Organisation postman collection](https://github.com/egovernments/DIGIT-Works/blob/master/backend/organisation/docs/Organisation%20Registry%20-%20Test%20Scripts.postman\_collection.json)
