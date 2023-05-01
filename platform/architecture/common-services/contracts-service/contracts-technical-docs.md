---
description: Work related contracts
---

# Contracts Technical Docs

## Overview

The contract service captures work orders or purchase orders. It validates the work order against the estimate(s). &#x20;

### Dependencies

* Estimate service
* IDGen
* MDMS
* Workflow
* User
* HRMS
* Organisation

## API Specifications

### API Contract Link

{% embed url="https://editor.swagger.io/?url=https://raw.githubusercontent.com/egovernments/DIGIT-Works/master/backend/contract-service/Contract_v1.0.0_oas3.yaml" %}

### Data Model&#x20;

### DB Schema Diagram

<figure><img src="https://github.com/egovernments/DIGIT-Works/blob/master/backend/contract-service/Contract%20Service%20ER%20diagram.png?raw=true" alt=""><figcaption></figcaption></figure>

### Web Sequence Diagrams

{% tabs %}
{% tab title="Create" %}
<figure><img src="https://github.com/egovernments/DIGIT-Works/blob/develop/backend/contract-service/docs/SequenceDiagrams/pngs/ContractCreation.png?raw=true" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Update" %}
<figure><img src="https://github.com/egovernments/DIGIT-Works/blob/develop/backend/contract-service/docs/SequenceDiagrams/pngs/ContractUpdation.png?raw=true" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Search" %}
<figure><img src="../../../../.gitbook/assets/Contract Search.png" alt=""><figcaption></figcaption></figure>


{% endtab %}
{% endtabs %}

### Master Data Types

Contract Type - defines different contract types



### Postman Collection

TBD



