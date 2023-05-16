# Organisation Functional Category

## Introduction

The organization's functional category define the functional area of an organization.

## Data Table

| Sr. No. | Parent Code (Org Type) | Code | Description     | Description (Odiya)   | Effective From | Effective To | Is Active |
| ------- | ---------------------- | ---- | --------------- | --------------------- | -------------- | ------------ | --------- |
| 1       | VEN                    | CW   | Civil Works     | ବେସାମରିକ କାର୍ଯ୍ୟସମୂହ  |                |              |           |
| 2       | VEN                    | EW   | Electical Works | ବୈଦ୍ୟୁତିକ କାର୍ଯ୍ୟସମୂହ |                |              |           |
| 3       | CBO                    | NA   | Not Applicable  | ପ୍ରଯୁଜ୍ୟ ନୁହେଁ        |                |              |           |

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
