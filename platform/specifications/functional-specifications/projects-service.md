---
description: DIGIT - Projects functional details
---

# Project

## Overview

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
5. The project details capture the financial details such as the funding source for the project. These details, however, are not part of the Project Service but are captured as part of the Program Service.

## Features & Scope

The table below provides the list of project attributes.

<table><thead><tr><th width="148">Field</th><th width="138">Data Type</th><th width="145">Required (Y/N)</th><th>Validations / Comments</th></tr></thead><tbody><tr><td>Id</td><td>NA</td><td>Y</td><td>System generated UUID</td></tr><tr><td>Name</td><td>Alphanumeric</td><td>Y</td><td>MinChar 2 - Max Char - NA<br>Ex - Construction of School Building</td></tr><tr><td>Project Type</td><td>MDMS Data</td><td>Y</td><td>Should be pre-defined master data<br>Ex - Building</td></tr><tr><td>Project Sub Type</td><td>MDMS Data</td><td>N</td><td>Should be pre-defined master data. Estimate templates are linked to a project subtype<br>Ex - School Building</td></tr><tr><td>Project Group</td><td>MDMS Data</td><td>Y</td><td>Should be pre-defined master data. Contract &#x26; Assetisation terms are defined based on this value.<br>Ex - Capital Works</td></tr><tr><td>Address</td><td></td><td>Y</td><td>Address of the main project.</td></tr><tr><td>Proposed Start date</td><td>Date</td><td>N</td><td></td></tr><tr><td>Proposed End date</td><td>Date</td><td>N</td><td></td></tr><tr><td>Parent</td><td>ID</td><td>N</td><td>Parent Project ID</td></tr><tr><td>Status</td><td>MDMS Data</td><td>Y</td><td>Created, Rejected, Cancelled, In-progress, Completed</td></tr><tr><td>Owning Department</td><td>MDMS Data</td><td>Y</td><td></td></tr><tr><td>Reference No</td><td>Alphanumeric</td><td>N</td><td>MinChar 2 - Max Char - NA<br><br>Reference No to Offline File if any</td></tr><tr><td>Description</td><td>Alphanumeric</td><td>N</td><td>MinChar 2 - Max Char - NA<br><br>Description of the Project</td></tr><tr><td>Documents</td><td>Attachments</td><td>N</td><td>Upto 5 Documents each of 5 MB<br><br>Document Attachments</td></tr></tbody></table>

## Use Cases

A project can be divided into multiple sub-projects, each with its own workflows/business requirements defined.&#x20;

## Mockups

<table data-header-hidden><thead><tr><th width="283">Description</th><th>Mockups</th></tr></thead><tbody><tr><td>Create Project with no sub projects</td><td><img src="../../../.gitbook/assets/image (22).png" alt=""></td></tr><tr><td>Create Project with Sub projects</td><td><img src="../../../.gitbook/assets/image (1) (3).png" alt=""></td></tr><tr><td>Capturing Financial details of project (Part of Program service)</td><td><img src="../../../.gitbook/assets/image (3) (1).png" alt=""></td></tr><tr><td>Capturing Sub Project Details</td><td><img src="../../../.gitbook/assets/image (8).png" alt=""></td></tr><tr><td>Project Created Successfully</td><td><img src="../../../.gitbook/assets/image (34).png" alt=""></td></tr><tr><td>View Project</td><td><img src="../../../.gitbook/assets/image (1) (1).png" alt=""></td></tr><tr><td>Projects Inbox</td><td><img src="../../../.gitbook/assets/image (21).png" alt=""></td></tr><tr><td>Inbox Table</td><td><img src="../../../.gitbook/assets/image (32).png" alt=""></td></tr></tbody></table>

