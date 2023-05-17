---
description: DIGIT - Projects functional details
---

# Projects Service

<table data-card-size="large" data-view="cards"><thead><tr><th data-type="content-ref"></th><th></th><th></th></tr></thead><tbody><tr><td><a href="../../architecture/common-services/projects-service/project-technical-docs.md">project-technical-docs.md</a></td><td>Click on the link above to explore the technical specifications for the project service.</td><td></td></tr></tbody></table>

## Overview

**Need**

Projects are the first work entity defined by the State/Department/ULB or any executing authority. This consists of basic details like IDs, descriptions, addresses, sub-project details, project types, start and end dates etc.&#x20;

Projects may not focus on just construction or civil works. A health campaign, an office decoration, a pre-contractual phase with an IT vendor for new software, new service delivery initiatives etc are examples of projects.

**Users:** Junior Engineer or Assistant Engineer who creates Works Projects for the ULB/Department

**Description**

1. JE creates projects with the below-mentioned attributes.
2. A project can have sub-projects as well depending on the way of executing the project.
   * When a project is divided into sub-projects, each will have the same attributes to be captured as the main project.
3. A project can be sent for approval depending on the need.
   * Usually, the administrative sanction is done on projects by EO. Post approval, detailed and abstract estimates are done.
     * Once the admin sanctions the project, the fund is also blocked for the respective heads of accounts.
     * Project status -
       * Created
       * In progress
       * Approved
       * Rejected
       * Cancelled
4. Once a project is created on the UI, the system generates a unique ID for each project/sub-project.
   * ID: PROJ/\<ULB/Department Code>/\<Year>/\<month>/\<Date>/\<running sequence number>
5. The project details capture the financial details such as the funding source for the project. These details, however, are not part of the Project service but are captured as part of the Program service.

## Features & Scope

The table below provides the list of project attributes.

| Field               | Data Type    | Required (Y/N) | Validations / Comments                                                                                                              |
| ------------------- | ------------ | -------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| Id                  | NA           | Y              | System generated UUID                                                                                                               |
| Name                | Alphanumeric | Y              | <p>MinChar 2 - Max Char - NA<br>Ex - Construction of School Building</p>                                                            |
| Project Type        | MDMS Data    | Y              | <p>Should be pre-defined master data<br>Ex - Building</p>                                                                           |
| Project Sub Type    | MDMS Data    | N              | <p>Should be pre-defined master data. Estimate templates are linked to a project subtype<br>Ex - School Building</p>                |
| Project Group       | MDMS Data    | Y              | <p>Should be pre-defined master data. Contract &#x26; Assetisation terms are defined based on this value.<br>Ex - Capital Works</p> |
| Address             |              | Y              | Address of the main project.                                                                                                        |
| Proposed Start date | Date         | N              |                                                                                                                                     |
| Proposed End date   | Date         | N              |                                                                                                                                     |
| Parent              | ID           | N              | Parent Project ID                                                                                                                   |
| Status              | MDMS Data    | Y              | Created, Rejected, Cancelled, In-progress, Completed                                                                                |
| Owning Department   | MDMS Data    | Y              |                                                                                                                                     |
| Reference No        | Alphanumeric | N              | <p>MinChar 2 - Max Char - NA<br><br>Reference No to Offline File if any</p>                                                         |
| Description         | Alphanumeric | N              | <p>MinChar 2 - Max Char - NA<br><br>Description of the Project</p>                                                                  |
| Documents           | Attachments  | N              | <p>Upto 5 Documents each of 5 MB<br><br>Document Attachments</p>                                                                    |

## Use Cases

A project can be divided into multiple sub-projects, each with its own workflows/business requirements defined.&#x20;

## Mockups

| Create Project with no sub projects                              | ![](<../../../.gitbook/assets/image (22).png>)    |
| ---------------------------------------------------------------- | ------------------------------------------------- |
| Create Project with Sub projects                                 | ![](<../../../.gitbook/assets/image (1) (1).png>) |
| Capturing Financial details of project (Part of Program service) | ![](<../../../.gitbook/assets/image (3).png>)     |
| Capturing Sub Project Details                                    | ![](<../../../.gitbook/assets/image (8).png>)     |
| Project Created Successfully                                     | ![](<../../../.gitbook/assets/image (34).png>)    |
| View Project                                                     | ![](<../../../.gitbook/assets/image (2).png>)     |
| Projects Inbox                                                   | ![](<../../../.gitbook/assets/image (21).png>)    |
| Inbox Table                                                      | ![](<../../../.gitbook/assets/image (32).png>)    |

