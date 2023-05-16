# Organisation Sub Type

## Introduction

The Community Based Organization are further categories and refered as sub type.

## Data Table

| Sr. No. | Parent Code (Org Type) | Code | Description                    | Description (Odiya)       | Effective From | Effective To | Is Active |
| ------- | ---------------------- | ---- | ------------------------------ | ------------------------- | -------------- | ------------ | --------- |
| 1       | VEN                    | CMS  | Construction Material Supplier | ନିର୍ମାଣ ସାମଗ୍ରୀ ଯୋଗାଣକାରୀ |                |              |           |
| 2       | VEN                    | NA   | Not Applicable                 | ପ୍ରଯୁଜ୍ୟ ନୁହେଁ            |                |              |           |
| 3       | CBO                    | MSG  | Mission Shakti Group           | ମିଶନ୍ ଶକ୍ତି ଗୋଷ୍ଠୀ        |                |              |           |
| 4       | CBO                    | SDA  | Slum Dwellers Association      | ବସ୍ତି ବାସିନ୍ଦା ସଂଘ        |                |              |           |
| 5       | CBO                    | ALF  | Area Level Federation          | କ୍ଷେତ୍ର ସ୍ତରୀୟ ମହାସଂଘ     |                |              |           |
| 6       | CBO                    | CLF  | Clustor Level Federation       | କ୍ଲଷ୍ଟର ସ୍ତରୀୟ ମହାସଂଘ     |                |              |           |

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
