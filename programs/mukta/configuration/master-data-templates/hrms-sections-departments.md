# HRMS Sections/Departments

## Introduction

These are name of sections/ departments within the ULBs which set the functional scope of employees belong to these sections.

## Data Table

| Sr. No. | Code | Description                       | Description (Odiya)        | Effective From | Effective To | Is Active |
| ------- | ---- | --------------------------------- | -------------------------- | -------------- | ------------ | --------- |
| 1       | ADM  | Administration                    | ପ୍ରଶାସନ                    |                |              |           |
| 2       | REV  | Tax                               | କର                         |                |              |           |
| 3       | ACC  | Accounts                          | ଆୟ ବ୍ୟୟ ହିସାବ              |                |              |           |
| 4       | PHS  | Public Health and Sanitation      | ଜନସ୍ୱାସ୍ଥ୍ୟ ଏବଂ ପରିମଳ      |                |              |           |
| 5       | WRK  | Works                             | କାର୍ଯ୍ୟସମୂହ                |                |              |           |
| 6       | TWP  | Town Planning                     | ଟାଉନ୍ ଯୋଜନା                |                |              |           |
| 7       | NULM | National Urban Livelihood Mission | ଜାତୀୟ ସହରାଞ୍ଚଳ ଜୀବିକା ମିଶନ |                |              |           |
| 8       | PR   | Public Relations                  | ଜନ ସମ୍ପର୍କ                 |                |              |           |

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
