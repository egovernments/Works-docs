---
description: High level design document
---

# Project

## Overview

The project service provides APIs to create, update and manage a generic project. A project can have one or more of the following constructs: staff, tasks, beneficiaries and facilities. Currently, this service is shared across the Health and Works platforms. All Works projects start with a project construct. The Works platform uses only 3 primary APIs: project create, update and search. For low-level design and other information on this service, click [here](http://127.0.0.1:5000/s/j7fNh51k98E3IpNor4eY/platform/architecture/low-level-design/services/project).&#x20;

## Key Functionalities

* Creating, updating, and searching for a project
* Adding staff, tasks, resources and facilities to a project

## Code

[Module code](https://github.com/egovernments/health-campaign-services/tree/master/health-services/project)

[Deployment in Works](https://github.com/egovernments/DIGIT-DevOps/tree/digit-works/deploy-as-code/helm/charts/digit-works/backend/project)

## Integration

### API Spec

**Base path**: /project/

Documentation for this service is available [here](https://health.digit.org/platform/low-level-design/services/project).&#x20;

### Postman Collection

Click [here](https://raw.githubusercontent.com/egovernments/DIGIT-Works/develop/backend/project-management-system/src/main/resources/Project%20Management%20System.postman\_collection.json) to access the Postman collection used to test APIs. Import the link into Postman and follow the instructions to run the collection.&#x20;

## Master Data Types

The following primary masters are defined by this module and used for validations. Other common masters such as department, tenant etc..are also used by this module.&#x20;

<table><thead><tr><th width="172.66666666666669">Module Name</th><th width="155">Master Name</th><th>Sample Data</th></tr></thead><tbody><tr><td>works</td><td>ProjectType</td><td><a href="https://github.com/egovernments/works-mdms-data/blob/UAT/data/statea/works/ProjectType.json">https://github.com/egovernments/works-mdms-data/blob/UAT/data/statea/works/ProjectType.json</a></td></tr></tbody></table>

