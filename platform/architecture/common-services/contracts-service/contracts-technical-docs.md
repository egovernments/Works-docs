---
description: Work related contracts
---

# Contracts Technical Docs

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

### Code:

Code for this module resides [here](https://github.com/egovernments/DIGIT-Works/tree/master/backend/contracts).

## API Specifications

#### Base path:

/contracts

### API Contract Link

API spec YAML is [here](https://raw.githubusercontent.com/egovernments/DIGIT-Works/master/backend/estimates/docs/Estimate-service-1.0.0.yaml). Click below to view it in Swagger Editor.

{% embed url="https://editor.swagger.io/?url=https://raw.githubusercontent.com/egovernments/DIGIT-Works/master/backend/contracts/Contract_v1.0.0_oas3.yaml" %}

### Data Model&#x20;

### DB Schema Diagram

<figure><img src="https://github.com/egovernments/DIGIT-Works/blob/master/backend/contracts/Contract%20Service%20ER%20diagram.png?raw=true" alt=""><figcaption></figcaption></figure>

### Web Sequence Diagrams

{% tabs %}
{% tab title="Create" %}
<figure><img src="https://github.com/egovernments/DIGIT-Works/blob/master/backend/contracts/docs/SequenceDiagrams/pngs/ContractCreation.png?raw=true" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Update" %}
<figure><img src="https://github.com/egovernments/DIGIT-Works/blob/master/backend/contracts/docs/SequenceDiagrams/pngs/ContractUpdation.png?raw=true" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Search" %}
<figure><img src="../../../../.gitbook/assets/Contract Search.png" alt=""><figcaption></figcaption></figure>


{% endtab %}
{% endtabs %}

### Master Data Types

Contract Type - defines different contract types

OIC Roles - defines Officer-in-charge roles

CBO Roles - defines the capacities in which an organisation can accept the contract.

### Postman Collection

TBD



