# Organisation

### Overview

This is being designed as a cross-functional registry that will house vendors, suppliers, contractors, non-profits, SHGs etc.. Can be used across domains.&#x20;

### Code

[Organisation](https://github.com/egovernments/DIGIT-Works/tree/master/backend/organisation)

### API Specification

**Base Path:** /org-services/organisation

Raw API spec resides [here](https://raw.githubusercontent.com/egovernments/DIGIT-Works/master/backend/organisation/Organisation\_V1.0\_OAS3\_final.yaml). To view in Swagger editor, click below:

{% embed url="https://editor.swagger.io/?url=https://raw.githubusercontent.com/egovernments/DIGIT-Works/master/backend/organisation/Organisation_V1.0_OAS3_final.yaml" %}

### DB Schema

<figure><img src="https://github.com/egovernments/DIGIT-Works/blob/master/backend/organisation/docs/diagrams/Oraganisation%20Service%20-%20DB%20Schema.png?raw=true" alt=""><figcaption></figcaption></figure>

### Sequence Diagrams



### Master Data

OrgType - Defines types of organisations

OrgFunctionCategory - The functional area where an organisation works

OrgFunctionClass - The class (rating) of an organisation in a specific functional area.

OrgTaxIdentifier - The list of tax identifiers that can be entered.

OrgTransferCode - The bank account transfer code (IFSC etc..). This is usually only one defined in the master data. Can be customised for other countries.

### Postman Collection

[Organisation postman collection](https://github.com/egovernments/DIGIT-Works/blob/master/backend/organisation/docs/Organisation%20Registry%20-%20Test%20Scripts.postman\_collection.json)

