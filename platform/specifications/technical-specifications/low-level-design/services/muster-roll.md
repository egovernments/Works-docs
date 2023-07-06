---
description: Describes a calculator service for computing attendance
---

# Muster Roll

## Overview

The muster roll service aggregates attendance logs from the attendance service based on some rules and presents an attendance aggregate for a time period (week or month) per individual. This can then be used to compute payments or other semantics.&#x20;

## Dependencies

DIGIT backbone services

Idgen

Persister

Indexer

Workflow

User

Attendance

## Code

[Module code](https://github.com/egovernments/DIGIT-Works/tree/master/backend/muster-roll)

[Helm charts](https://github.com/egovernments/DIGIT-DevOps/tree/digit-works/deploy-as-code/helm/charts/digit-works/backend/muster-roll)

## API Specifications

#### Path:

/muster-roll

### API Contract Link

{% embed url="https://editor.swagger.io/?url=https://raw.githubusercontent.com/egovernments/DIGIT-Works/develop/backend/muster-roll-service/Muster-Roll-Service-1.0.0.yaml" %}

## Data Model

### DB Schema Diagram

<figure><img src="../../../../../.gitbook/assets/Muster_roll_DbSchema.png" alt=""><figcaption></figcaption></figure>

### Web Sequence Diagrams

{% tabs %}
{% tab title="Create" %}
<figure><img src="../../../../../.gitbook/assets/Muster-Roll Create.png" alt=""><figcaption></figcaption></figure>


{% endtab %}

{% tab title="Second Tab" %}
<figure><img src="../../../../../.gitbook/assets/Muster-Roll Update.png" alt=""><figcaption></figcaption></figure>


{% endtab %}

{% tab title="Search" %}
<figure><img src="../../../../../.gitbook/assets/Muster-Roll Search.png" alt=""><figcaption></figcaption></figure>


{% endtab %}
{% endtabs %}



#### **Master Data**&#x20;

{% embed url="https://github.com/egovernments/works-mdms-data/blob/DEV/data/pb/common-masters/MusterRoll.json" %}

{% embed url="https://github.com/egovernments/works-mdms-data/blob/DEV/data/pb/common-masters/WageSeekerSkills.json" %}

