# Bank Account

## Overview

The bank accounts registry houses financial account details of individual and organisational entities. The registry stores the account name, type, bank branch identifier (IFSC code) and other optional information. The bank branch identifier can be configured as master data. This makes it easy to extend this registry for use in countries outside India. The registry encrypts all PII and stores it in a secure fashion.

## Code

[Module code](https://github.com/egovernments/DIGIT-Works/tree/master/backend/bankaccounts)

[Helm charts](https://github.com/egovernments/DIGIT-DevOps/tree/digit-works/deploy-as-code/helm/charts/digit-works/backend/bankaccounts) for deployment

## API Specifications

**Base path**: `/bankaccount-service/bankaccounts/`

### API Contract Link

API specification is available [here](https://github.com/egovernments/DIGIT-Works/tree/master/backend/bankaccounts/docs). To view in Swagger editor, click below.

{% embed url="https://editor.swagger.io/?url=https://raw.githubusercontent.com/egovernments/DIGIT-Works/master/backend/bankaccounts/docs/bank-account-v1.0.0.yaml" %}

## Data Model&#x20;

### DB Schema Diagram

<figure><img src="https://github.com/egovernments/DIGIT-Works/blob/master/backend/bankaccounts/docs/Bank_Account_DB_Schema.png?raw=true" alt=""><figcaption></figcaption></figure>

### Web Sequence Diagrams



### Persister

[Bank account service persister](https://github.com/egovernments/works-configs/blob/UAT/egov-persister/bankaccounts-persister.yml)

### Indexer

No indexer has been configured for this service.&#x20;

### Master Data Types

BankBranchIdentifier
