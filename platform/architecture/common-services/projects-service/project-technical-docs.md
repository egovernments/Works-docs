---
description: High level design document
---

# Project Technical Docs

## Overview

Find the API specs and master data details required to deploy the Project service.

### API Spec

Documentation for this service is available [here](https://health.digit.org/platform/low-level-design/services/project). Refer to the doc to access technical details.

### Postman Collection

Click [here](https://raw.githubusercontent.com/egovernments/DIGIT-Works/develop/backend/project-management-system/src/main/resources/Project%20Management%20System.postman\_collection.json) to access the Postman collection used to test APIs. Import the link into Postman and follow the instructions to run the collection.&#x20;

### Master Data Types

The following primary masters are defined by this module and used for validations. Other common masters such as department, tenant etc..are also used by this module.&#x20;

| Module Name | Master Name    | Sample Data                                                                                                                                                                                                  |
| ----------- | -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| works       | NatureOfWork   | [https://raw.githubusercontent.com/egovernments/works-mdms-data/DEV/data/pb/works/NatureOfWork.json](https://raw.githubusercontent.com/egovernments/works-mdms-data/DEV/data/pb/works/NatureOfWork.json)     |
| works       | ProjectType    | [https://raw.githubusercontent.com/egovernments/works-mdms-data/DEV/data/pb/works/ProjectType.json](https://raw.githubusercontent.com/egovernments/works-mdms-data/DEV/data/pb/works/ProjectType.json)       |
| works       | ProjectSubType | [https://raw.githubusercontent.com/egovernments/works-mdms-data/DEV/data/pb/works/ProjectSubType.json](https://raw.githubusercontent.com/egovernments/works-mdms-data/DEV/data/pb/works/ProjectSubType.json) |

