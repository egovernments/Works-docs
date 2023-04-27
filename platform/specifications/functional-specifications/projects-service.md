---
description: DIGIT - Projects
---

# Projects Service

## Overview

**Need:**

Projects are the first entity of work defined by the state/ Department/ ULB or any executing authority that wishes to do a “Project”. This consists of basic details like IDs, description, address, Sub project Details, project types, start and end dates etc.&#x20;

Projects need not be focussed on just construction or civil works. A Health campaign, an office decoration, a pre-contractual phase with an IT vendor for new software, new service delivery initiatives etc all of it can be projects.

**Users:** Junior Engineer or Assistant Engineer who creates Works Projects for the ULB/Department

**Description:**

1. JE creates Projects with below mentioned attributes.
2. A project can have sub projects as well depending on way of executing the project.
   1. A project when is divided into sub projects, each will have same attributes to be captured as the main project.
3. A project can be sent for approval depending on need.
   1. Usually administrative sanction is done on projects by EO. After Approval, detailed and abstract estimates are done
      1. When Admin sanction is done, fund is also blocked in the respective heads of accounts.
      2. Statuses of a Project
         1. Created
         2. In progress
         3. Approved
         4. Rejected
         5. Cancelled
4. After a project is created on the UI, system should generate a unique ID for each project/ sub project.
   1. ID: PROJ/\<ULB/Department Code>/\<Year>/\<month>/\<Date>/\<running sequence number>
5. While creating a project, certain financial details are also captured as to where to fund this project from. These however are not part of Project service and will be part of program service

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





## Use Cases

1. A project can be divided into Multiple Sub Projects and each can have its own workflows/business requirements defined.&#x20;

Mockups\



| Create Project with no sub projects                              | ![](<../../../.gitbook/assets/image (22).png>)    |
| ---------------------------------------------------------------- | ------------------------------------------------- |
| Create Project with Sub projects                                 | ![](<../../../.gitbook/assets/image (1) (3).png>) |
| Capturing Financial details of project (Part of Program service) | ![](<../../../.gitbook/assets/image (3).png>)     |
| Capturing Sub Project Details                                    | ![](<../../../.gitbook/assets/image (8).png>)     |
| Project Created Successfully                                     | ![](<../../../.gitbook/assets/image (34).png>)    |
| View Project                                                     | ![](<../../../.gitbook/assets/image (1).png>)     |
| Projects Inbox                                                   | ![](<../../../.gitbook/assets/image (21).png>)    |
| Inbox Table                                                      | ![](<../../../.gitbook/assets/image (32).png>)    |
