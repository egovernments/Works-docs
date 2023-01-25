---
description: Description of the attendance service
---

# Attendance

## Overview

This is a generic attendance module that allows creation of an attendance register, enrolment of staff and attendees and capture of attendance records with entry/exit times. To compute attendance based on the logs, a calculator service should be built with specific business logic.&#x20;

## API Specifications

### API Contract Link

{% embed url="https://editor.swagger.io/?url=https://raw.githubusercontent.com/egovernments/DIGIT-Works/develop/backend/attendance-service/Attendance-Service-1.0.0.yaml" %}

### APIs

{% swagger src="../../../../../.gitbook/assets/Attendance-Service-1.0.0.yaml" path="/attendance/v1/_create" method="post" %}
[Attendance-Service-1.0.0.yaml](../../../../../.gitbook/assets/Attendance-Service-1.0.0.yaml)
{% endswagger %}

{% swagger src="../../../../../.gitbook/assets/Attendance-Service-1.0.0.yaml" path="/attendance/v1/_update" method="post" %}
[Attendance-Service-1.0.0.yaml](../../../../../.gitbook/assets/Attendance-Service-1.0.0.yaml)
{% endswagger %}

{% swagger src="../../../../../.gitbook/assets/Attendance-Service-1.0.0.yaml" path="/attendance/v1/_search" method="post" %}
[Attendance-Service-1.0.0.yaml](../../../../../.gitbook/assets/Attendance-Service-1.0.0.yaml)
{% endswagger %}

{% swagger src="../../../../../.gitbook/assets/Attendance-Service-1.0.0.yaml" path="/attendance/staff/v1/_create" method="post" %}
[Attendance-Service-1.0.0.yaml](../../../../../.gitbook/assets/Attendance-Service-1.0.0.yaml)
{% endswagger %}

{% swagger src="../../../../../.gitbook/assets/Attendance-Service-1.0.0.yaml" path="/attendance/staff/v1/_delete" method="post" %}
[Attendance-Service-1.0.0.yaml](../../../../../.gitbook/assets/Attendance-Service-1.0.0.yaml)
{% endswagger %}

{% swagger src="../../../../../.gitbook/assets/Attendance-Service-1.0.0.yaml" path="/attendance/attendee/v1/_create" method="post" %}
[Attendance-Service-1.0.0.yaml](../../../../../.gitbook/assets/Attendance-Service-1.0.0.yaml)
{% endswagger %}

{% swagger src="../../../../../.gitbook/assets/Attendance-Service-1.0.0.yaml" path="/attendance/attendee/v1/_delete" method="post" %}
[Attendance-Service-1.0.0.yaml](../../../../../.gitbook/assets/Attendance-Service-1.0.0.yaml)
{% endswagger %}

{% swagger src="../../../../../.gitbook/assets/Attendance-Service-1.0.0.yaml" path="/attendance/log/v1/_create" method="post" %}
[Attendance-Service-1.0.0.yaml](../../../../../.gitbook/assets/Attendance-Service-1.0.0.yaml)
{% endswagger %}

{% swagger src="../../../../../.gitbook/assets/Attendance-Service-1.0.0.yaml" path="/attendance/log/v1/_update" method="post" %}
[Attendance-Service-1.0.0.yaml](../../../../../.gitbook/assets/Attendance-Service-1.0.0.yaml)
{% endswagger %}

{% swagger src="../../../../../.gitbook/assets/Attendance-Service-1.0.0.yaml" path="/attendance/log/v1/_search" method="post" %}
[Attendance-Service-1.0.0.yaml](../../../../../.gitbook/assets/Attendance-Service-1.0.0.yaml)
{% endswagger %}

## Data Model

### DB Schema Diagram

<figure><img src="../../../../../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

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



