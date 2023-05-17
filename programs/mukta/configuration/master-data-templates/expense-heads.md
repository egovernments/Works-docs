# Expense Heads

## Introduction

These are the heads under which MUKTA expenditure is booked.&#x20;

## Data Table

| Sr. No. | Code | Description           | Description (Odiya) | Effective From | Effective To | Is Active |
| ------- | ---- | --------------------- | ------------------- | -------------- | ------------ | --------- |
| 1       | WEG  | Wages                 | ମଜୁରୀ               |                |              |           |
| 2       | SC   | Supervision Charge    | ତଦାରଖ ଦେୟ           |                |              |           |
| 3       | GST  | Goods and Service Tax | ଦ୍ରବ୍ୟ ଏବଂ ସେବା କର  |                |              |           |
| 4       | MC   | Material Cost         | ସାମଗ୍ରୀ ମୂଲ୍ୟ       |                |              |           |
| 5       | PA   | Purchase              | କ୍ରୟ ପରିମାଣ         |                |              |           |

{% hint style="info" %}
The data given in the table is sample data for reference.
{% endhint %}

## Data Definition

| Sr. No. | Column Name         | Data Type    | Data Size | Is Mandatory? | Definition/ Description                         |
| ------- | ------------------- | ------------ | --------- | ------------- | ----------------------------------------------- |
| 1       | Code                | Alphanumeric | 64        | Yes           | A unique code that identifies the project type. |
| 2       | Description         | Text         | 256       | Yes           | Provides the name of the project type           |
| 3       | Description (Odiya) | Text         | 256       | No            | Project type name in local language             |
| 4       | Effective From      |              |           |               | Date from which the project is effective        |
| 5       | Effective To        |              |           |               | Date till which the project is effective        |
| 6       | Is Active           |              |           |               | Whether the project is active or not            |

## Attachments

{% file src="../../../../.gitbook/assets/MUKTA - Master Data-2.xlsx" %}
