---
description: DIGIT - Projects
---

# Projects Service

## Overview

Projects are the first entity of work defined by the state/ Department/ ULB or any executing authority that wishes to do a Project. This consists of basic details like IDs, descriptions, addresses, Sub-project Details, Project Types, Start and End Dates etc.&#x20;

Projects need not be focussed on just construction or civil works. A Health campaign, an office decoration, a pre-contractual phase with an IT vendor for new software, new service delivery initiatives etc are all examples of projects.

## Features & Scope

The table below provides the list of Project attributes.

| Field               | Data Type    | Required (Y/N) | Validations / Comments                                                                                                                  |
| ------------------- | ------------ | -------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| Id                  | NA           | Y              | System generated UUID                                                                                                                   |
| Name                | Alphanumeric | Y              | <p>MinChar 2 - Max Char - NA<br><br>Ex - Construction of School Building</p>                                                            |
| Project Type        | MDMS Data    | Y              | <p>Should be pre defined master data<br><br>Ex - Building</p>                                                                           |
| Project Sub Type    | MDMS Data    | N              | <p>Should be pre defined master data. Estimate templates are linked to project sub type<br><br>Ex - School Building</p>                 |
| Project Group       | MDMS Data    | Y              | <p>Should be pre defined master data. Contract &#x26; Assetisation terms are defined based on this value.<br><br>Ex - Capital Works</p> |
| Address             |              | Y              | Address of the main project.                                                                                                            |
| Proposed Start date | Date         | N              |                                                                                                                                         |
| Proposed End date   | Date         | N              |                                                                                                                                         |
| Parent              | ID           | N              | Parent Project ID                                                                                                                       |
| Status              | MDMS Data    | Y              | Created, Rejected, Cancelled, In-progress, Completed                                                                                    |
| Owning Department   | MDMS Data    | Y              |                                                                                                                                         |
| Reference No        | Alphanumeric | N              | <p>MinChar 2 - Max Char - NA<br><br>Reference No to Offline File if any</p>                                                             |
| Description         | Alphanumeric | N              | <p>MinChar 2 - Max Char - NA<br><br>Description of the Project</p>                                                                      |
| Documents           | Attachments  | N              | <p>Upto 5 Documents each of 5 MB<br><br>Document Attachments</p>                                                                        |

## Functional Requirements



## Use Cases

1. A project can be divided into Multiple Sub Projects and each can have its own workflows/business requirements defined.&#x20;
2.

## Mockups

\
