---
description: Description of the attendance service
---

# Attendance Technical Docs

## Overview

This is a generic attendance module that allows creation of an attendance register, enrolment of staff and attendees and capture of attendance records with entry/exit times. To compute attendance based on the logs, a calculator service should be built with specific business logic.&#x20;

### Code

[Module code](https://github.com/egovernments/DIGIT-Works/tree/master/backend/attendance)

[Deployment Helm Charts](https://github.com/egovernments/DIGIT-DevOps/tree/digit-works/deploy-as-code/helm/charts/digit-works/backend/attendance)

## API Specifications

### Base Path:&#x20;

/attendance/

### API Contract Link

{% embed url="https://editor.swagger.io/?url=https://raw.githubusercontent.com/egovernments/DIGIT-Works/master/backend/attendance/Attendance-Service-1.0.0.yaml" %}

## Data Model

### DB Schema Diagram

<figure><img src="../../../../../.gitbook/assets/image (26) (1).png" alt=""><figcaption></figcaption></figure>

### Web Sequence Diagram

#### Attendance Register

{% tabs %}
{% tab title="Create" %}
<figure><img src="../../../../../.gitbook/assets/Attendance-Register Create (1).png" alt=""><figcaption></figcaption></figure>


{% endtab %}

{% tab title="Update" %}
<figure><img src="../../../../../.gitbook/assets/Attendance-Register Update (1).png" alt=""><figcaption></figcaption></figure>


{% endtab %}

{% tab title="Search" %}
<figure><img src="../../../../../.gitbook/assets/Attendance-Register Search (1).png" alt=""><figcaption></figcaption></figure>


{% endtab %}
{% endtabs %}

#### Staff

{% tabs %}
{% tab title="Create" %}
<figure><img src="../../../../../.gitbook/assets/Staff Create.png" alt=""><figcaption></figcaption></figure>


{% endtab %}

{% tab title="Update/Delete" %}
<figure><img src="../../../../../.gitbook/assets/Staff Delete.png" alt=""><figcaption></figcaption></figure>


{% endtab %}
{% endtabs %}

#### Attendee

{% tabs %}
{% tab title="Create" %}
<figure><img src="../../../../../.gitbook/assets/Attendee Create.png" alt=""><figcaption></figcaption></figure>


{% endtab %}

{% tab title="Delete" %}
<figure><img src="../../../../../.gitbook/assets/Attendee Delete.png" alt=""><figcaption></figcaption></figure>


{% endtab %}
{% endtabs %}

#### Attendance Log

{% tabs %}
{% tab title="Create" %}
<figure><img src="../../../../../.gitbook/assets/Attendance Log Create.png" alt=""><figcaption></figcaption></figure>


{% endtab %}

{% tab title="Update" %}
<figure><img src="../../../../../.gitbook/assets/Attendance Log Update.png" alt=""><figcaption></figcaption></figure>


{% endtab %}

{% tab title="Search" %}
<figure><img src="../../../../../.gitbook/assets/Attendance Log Search.png" alt=""><figcaption></figcaption></figure>


{% endtab %}
{% endtabs %}



### Master Data Types

### Postman Collection

Postman collection can be imported from [here](https://github.com/egovernments/DIGIT-Works/blob/master/backend/attendance/Attendace%20Service%20Postman%20Scripts.postman\_collection.json).

