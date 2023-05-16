# Unit Of Measurement (Units)

## Introduction

Unit of measurements is the units used to capture the measurement and create the estimate for work in MUKTA.

## Data Table

| Sr. No. | Code | Description   | Description (Odiya) | Effective From | Effective To | Is Active |
| ------- | ---- | ------------- | ------------------- | -------------- | ------------ | --------- |
| 1       | CUM  | Cubic Meter   | ଘନ ମିଟର             |                |              |           |
| 2       | SQM  | Square Meter  | ବର୍ଗ ମିଟର           |                |              |           |
| 3       | RMT  | Running Meter | ରନିଙ୍ଗ ମିଟର         |                |              |           |
| 4       | KG   | Kilogram      | କିଲୋଗ୍ରାମ           |                |              |           |
| 5       | NOS  | Numbers       | ସଂଖ୍ୟାଗୁଡିକ         |                |              |           |
| 6       | CFT  | Cubic Feet    | ଘନ ଫୁଟ              |                |              |           |
| 7       | SFT  | Square Feet   | ବର୍ଗ ଫୁଟ            |                |              |           |
| 8       | FT   | Feet          | ଫୁଟ                 |                |              |           |

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

{% file src="../../../../.gitbook/assets/MUKTA - Master Data-2.xlsx" %}

