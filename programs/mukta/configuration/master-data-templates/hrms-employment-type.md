# HRMS Employment Type

## Introduction

These are the employment types for the employees working in ULBs like Temporary, Parmanent.

## Data Table

| Sr. No. | Code | Description | Description (Odiya) | Effective From | Effective To | Is Active |
| ------- | ---- | ----------- | ------------------- | -------------- | ------------ | --------- |
| 1       | PNT  | Permanent   | ସ୍ଥାୟୀ              |                |              |           |
| 2       | TMP  | Temporary   | ଅସ୍ଥାୟୀ             |                |              |           |
| 3       | DEP  | Deputation  | ପ୍ରତିନିଯୁକ୍ତି       |                |              |           |
| 4       | CNT  | Contractual | ଚୁକ୍ତିଭିତ୍ତିକ       |                |              |           |

{% hint style="info" %}
The data given in the table is sample data for reference.
{% endhint %}

## Data Definition

| Sr. No. | Column Name          | Data Type    | Data Size | Is Mandatory? | Definition/ Description                         |
| ------- | -------------------- | ------------ | --------- | ------------- | ----------------------------------------------- |
| 1       | Code                 | Alphanumeric | 64        | Yes           | A unique code that identifies the project type. |
| 2       | Project Type         | Text         | 256       | Yes           | Provides the name of the project type           |
| 3       | Project Type (Odiya) | Text         | 256       | No            | Project type name in local language             |
| 4       | Effective From       |              |           |               | Date from which the project is effective        |
| 5       | Effective To         |              |           |               | Date till which the project is effective        |
| 6       | Is Active            |              |           |               | Whether the project is active or not            |

## Attachments

{% file src="../../../../.gitbook/assets/MUKTA - Master Data-2.xlsx" %}
