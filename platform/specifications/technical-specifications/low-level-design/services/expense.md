# Expense

## Overview

The expense module implements the functionality of bills and payments. A bill or a group of bills can be aggregated together as payments. Payments advice can be submitted through integration with IFMS (Integrated Financial Management Systems) or any other third party payments provider. The expense module always works in combination with a calculator service. The calculator service is implementation specific and provides business logic to compute bills. The calculator calls into the expense service to create bills. In general, the expense create/update APIs are not called by any other module other than the calculator. For more information on the sample calculator provided with the Works platform, please navigate here.&#x20;

## Code

[Expense Module](https://github.com/egovernments/DIGIT-Works/tree/master/backend/expense)

[Helm Chart](https://github.com/egovernments/DIGIT-DevOps/tree/digit-works/deploy-as-code/helm/charts/digit-works/backend/expense)

## API Specifications

**Base path**: `/expense/bill/`

### API Contract Link

API specification is available [here](https://github.com/egovernments/DIGIT-Specs/blob/master/works/expense-contract.yml). To view in Swagger editor, click below.

{% embed url="https://editor.swagger.io/?url=https://raw.githubusercontent.com/egovernments/DIGIT-Specs/master/works/expense-contract.yml" %}

## Data Model&#x20;

### DB Schema Diagram

<figure><img src="https://github.com/egovernments/DIGIT-Works/blob/master/backend/expense/src/main/resources/db-diagram-expense.png?raw=true" alt=""><figcaption></figcaption></figure>

### Web Sequence Diagrams



### Persister

[Expense persister](https://github.com/egovernments/works-configs/blob/UAT/egov-persister/expense-bill-payment-persister.yaml)

### Indexer

Indexer Config: [Expense indexer](https://github.com/egovernments/works-configs/blob/UAT/egov-indexer/expensebill-indexer.yml)

Index Name: expense-bill-index

### Master Data&#x20;

HeadCodes

ApplicableCharges

LabourCharges

BusinessService

PayerList
