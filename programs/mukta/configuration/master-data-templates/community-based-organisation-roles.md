---
description: Role definition master data templates
---

# Community-Based Organisation Roles

## Introduction

In MUKA community based organizations have different roles to play based on the work value. The role defined are Implementation Agengency and Implementation Partner.&#x20;

## Data Table

| Sr. No. | Code\* | Description                                                | Description (Odiya) | Effective From | Effective To | Is Active |
| ------- | ------ | ---------------------------------------------------------- | ------------------- | -------------- | ------------ | --------- |
| 1       | DR     | Drainage and sewerage work \[Except de-siltation]          |                     |                |              |           |
| 2       | SN     | Sanitation work \[Except road sweeping and drain cleaning] |                     |                |              |           |
| 3       | WT     | Water conservation and rain water harvesting structures    |                     |                |              |           |

{% hint style="info" %}
The data given in the table is sample data for reference.
{% endhint %}

## Data Definition

| Sr. No. | Column Name         | Data Type    | Data Size | Is Mandatory? | Definition/ Description                         |
| ------- | ------------------- | ------------ | --------- | ------------- | ----------------------------------------------- |
| 1       | Code                | Alphanumeric | 64        | Yes           | A unique code that identifies the project type. |
| 2       | Description         | Text         | 256       | Yes           | Provides the name of the project type           |
| 3       | Description (Odiya) | Text         | 256       | No            | Project type name in local language             |
| 4       | Effective From      | Date         |           |               | Date from which the project is effective        |
| 5       | Effective To        | Date         |           |               | Date till which the project is effective        |
| 6       | Is Active           | Boolean      |           |               | Whether the project is active or not            |

## Attachments
