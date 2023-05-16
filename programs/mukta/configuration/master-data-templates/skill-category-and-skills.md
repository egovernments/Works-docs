# Skill Category & Skills

## Introduction

Skills are defined for the wage seekers and have different wages defined for each skill category.  These wages are revised by the government over then period of time.

## Data Table

| Sr. No. | Category \* | Skill (English)\*                                          | Skill (Odiya) | Rates | Effective From | Effective To | Is Active |
| ------- | ----------- | ---------------------------------------------------------- | ------------- | ----- | -------------- | ------------ | --------- |
| 1       | DR          | Drainage and sewerage work \[Except de-siltation]          |               |       |                |              |           |
| 2       | SN          | Sanitation work \[Except road sweeping and drain cleaning] |               |       |                |              |           |
| 3       | WT          | Water conservation and rain water harvesting structures    |               |       |                |              |           |

{% hint style="info" %}
The data given in the table is sample data for reference.
{% endhint %}

## Data Definition

| Sr. No. | Column Name     | Data Type    | Data Size | Is Mandatory? | Definition/ Description                         |
| ------- | --------------- | ------------ | --------- | ------------- | ----------------------------------------------- |
| 1       | Category        | Alphanumeric | 64        | Yes           | A unique code that identifies the project type. |
| 2       | Skill (English) | Text         | 256       | Yes           | Provides the name of the project type           |
| 3       | Skill (Odiya)   | Text         | 256       | No            | Project type name in local language             |
| 4       | Rates           | Numeric      |           |               |                                                 |
| 5       | Effective From  | Date         |           |               | Date from which the project is effective        |
| 6       | Effective To    | Date         |           |               | Date till which the project is effective        |
| 7       | Is Active       | Boolean      |           |               | Whether the project is active or not            |

## Attachments

