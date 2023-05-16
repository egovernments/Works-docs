# Overheads

## Introduction

Overheads are the items other than SOR and Non-SOR which are included in the estimate to complete the estimation and arrive the final value of work.

## Data Table

| Sr. No. | Code | Description           | Description (Odiya) | Is work order value? | Calculation Method | Percentage/ Value | Effective From | Effective To | Is Active |
| ------- | ---- | --------------------- | ------------------- | -------------------- | ------------------ | ----------------- | -------------- | ------------ | --------- |
| 1       | SC   | Supervision Charge    | ତଦାରଖ ଦେୟ           | Yes                  | Percentage         | 7.5               |                |              |           |
| 2       | GST  | Goods and Service Tax | ଦ୍ରବ୍ୟ ଏବଂ ସେବା କର  | Yes                  | Percentage         | 18                |                |              |           |

{% hint style="info" %}
The data given in the table is sample data for reference.
{% endhint %}

## Data Definition

| Sr. No. | Column Name          | Data Type    | Data Size | Is Mandatory? | Definition/ Description                         |
| ------- | -------------------- | ------------ | --------- | ------------- | ----------------------------------------------- |
| 1       | Code                 | Alphanumeric | 64        | Yes           | A unique code that identifies the project type. |
| 2       | Description          | Text         | 256       | Yes           | Provides the name of the project type           |
| 3       | Description (Odiya)  | Text         | 256       | No            | Project type name in local language             |
| 4       | Is work order value? | Boolean      |           |               |                                                 |
| 5       | Calculation Method   | Identifier   |           |               |                                                 |
| 6       | Percentage/Value     | Numeric      |           |               |                                                 |
| 4       | Effective From       | Date         |           |               | Date from which the project is effective        |
| 5       | Effective To         | Date         |           |               | Date till which the project is effective        |
| 6       | Is Active            | Boolean      |           |               | Whether the project is active or not            |

## Attachments

{% file src="../../../../.gitbook/assets/MUKTA - Master Data-2.xlsx" %}
