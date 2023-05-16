# Standard Deductions

## Introduction

These are deductions which are made from the purchase bills and then remitted to respective departments.

## Data Table

| Sr. No. | Code   | Description         | Description (Odiya)     | Applicable  | Calculation Method | Percentage/ Value | Effective From | Effective To | Is Active |
| ------- | ------ | ------------------- | ----------------------- | ----------- | ------------------ | ----------------- | -------------- | ------------ | --------- |
| 1       | LC     | Labour Cess         | ଶ୍ରମ ଉପକର (ସେସ୍)        | Vendor      | Percentage         | 1                 |                |              |           |
| 2       | ITTDS  | IT TDS              | ଆଇ.ଟି ଟି.ଡ଼ି.ଏସ୍         | Vendor      | Percentage         | 10                |                |              |           |
| 3       | ROM    | Royalty on minerals | ଖଣିଜ ପଦାର୍ଥ ଉପରେ ଲାଭାଂଶ | Vendor      | Not Calculated     |                   |                |              |           |
| 4       | ECB    | Empty Cement Bag    | ଖାଲି ସିମେଣ୍ଟ ବ୍ୟାଗ୍     | Vendor      | Not Calculated     |                   |                |              |           |
| 5       | GSTTDS | GST TDS             | ଜି.ଏସ୍.ଟି ଟି.ଡ଼ି.ଏସ୍     | Vendor      | Percentage         | 2                 |                |              |           |

{% hint style="info" %}
The data given in the table is sample data for reference.
{% endhint %}

## Data Definition

| Sr. No. | Column Name        | Data Type    | Data Size | Is Mandatory? | Definition/ Description                         |
| ------- | ------------------ | ------------ | --------- | ------------- | ----------------------------------------------- |
| 1       | Code               | Alphanumeric | 64        | Yes           | A unique code that identifies the project type. |
| 2       | Description        | Text         | 256       | Yes           | Provides the name of the project type           |
| 3       | Description (Odia) | Text         | 256       | No            | Project type name in local language             |
| 4       | Applicable         | Options      |           |               |                                                 |
| 5       | Calculation Method | Identifier   |           |               |                                                 |
| 6       | Percentage/Value   | Numeric      |           |               |                                                 |
| 4       | Effective From     | Date         |           |               | Date from which the project is effective        |
| 5       | Effective To       | Date         |           |               | Date till which the project is effective        |
| 6       | Is Active          | Boolean      |           |               | Whether the project is active or not            |

## Attachments

{% file src="../../../../.gitbook/assets/MUKTA - Master Data-2.xlsx" %}
