# Payment Advice Format

## Introduction

This the template to generate the payment advice from the system. After downloading the data accountant will be able to proceed with payments in IFMS system.

## Data Table

| Sr. No. | Project ID | Work Order ID | Bill Number       | Bill Type   | Gross Amount | Beneficiary Type | Beneficiary Name | Beneficiary ID | Account Type | Bank Account Number | IFSC | Payable Amount |
| ------- | ---------- | ------------- | ----------------- | ----------- | ------------ | ---------------- | ---------------- | -------------- | ------------ | ------------------- | ---- | -------------- |
| 1       |            |               | PB/2023-24/000001 | Purchase    | 1010         | ORG              |                  |                |              |                     |      | 1000           |
| 2       |            |               | PB/2023-24/000001 | Purchase    | 1010         | ULB              |                  |                |              |                     |      | 10             |
| 3       |            |               | SB/2023-24/000002 | Supervision | 900          | ORG              |                  |                |              |                     |      | 900            |
|         |            |               | WB/2023-24/00001  | WAGE        | 100          | IND              | A                |                |              |                     |      |                |
|         |            |               | WB/2023-24/00001  | WAGE        | 200          | IND              | B                |                |              |                     |      |                |
|         |            |               | WB/2023-24/00001  | WAGE        | 300          | IND              | C                |                |              |                     |      |                |
|         |            |               |                   |             |              |                  |                  |                |              |                     |      |                |
|         |            |               |                   |             |              |                  |                  |                |              |                     |      |                |
|         |            |               |                   |             |              |                  |                  |                |              |                     |      |                |

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
