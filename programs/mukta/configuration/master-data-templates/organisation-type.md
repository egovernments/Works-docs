# Organisation Type

## Introduction

The Community Based Organization and Vendors are created as 2 different type of organization.

## Data Table

| Sr. No. | Code | Description                  | Description (Odiya)  | Effective From | Effective To | Is Active |
| ------- | ---- | ---------------------------- | -------------------- | -------------- | ------------ | --------- |
| 1       | VEN  | Vendor/ Supplier             | ବିକ୍ରେତା / ଯୋଗାଣକାରୀ |                |              |           |
| 2       | CBO  | Community Based Organization | ଗୋଷ୍ଠୀ ଭିତ୍ତିକ ସଂଗଠନ |                |              |           |

{% hint style="info" %}
The data given in the table is sample data for reference.
{% endhint %}

## Data Definition

| Sr. No. | Column Name         | Data Type    | Data Size | Is Mandatory? | Definition/ Description                         |
| ------- | ------------------- | ------------ | --------- | ------------- | ----------------------------------------------- |
| 1       | Code                | Alphanumeric | 64        | Yes           | A unique code that identifies the project type. |
| 2       | Project Type        | Text         | 256       | Yes           | Provides the name of the project type           |
| 3       | Project Type (Odia) | Text         | 256       | No            | Project type name in local language             |
| 4       | Effective From      | Date         |           |               | Date from which the project is effective        |
| 5       | Effective To        | Date         |           |               | Date till which the project is effective        |
| 6       | Is Active           | Boolean      |           |               | Whether the project is active or not            |

## Attachments

{% file src="../../../../.gitbook/assets/MUKTA - Master Data-2.xlsx" %}
