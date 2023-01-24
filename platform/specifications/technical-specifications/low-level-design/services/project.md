---
description: High level design document
---

# Project

## Overview



## API Specifications

### API Contract Link

{% embed url="https://editor.swagger.io/?url=https://raw.githubusercontent.com/egovernments/DIGIT-Works/develop/backend/project-management-system/Project-Management-System-1.0.0.yaml" %}

### APIs



## Data Model&#x20;

### DB Schema Diagram

<figure><img src="https://github.com/egovernments/DIGIT-Works/blob/develop/backend/project-management-system/src/main/resources/Project_Management_System_DB_Diagram.png?raw=true" alt=""><figcaption><p>Project Service DB Schema</p></figcaption></figure>

### Web Sequence Diagrams

{% tabs %}
{% tab title="Create" %}
<figure><img src="https://github.com/egovernments/DIGIT-Works/blob/develop/backend/project-management-system/src/main/resources/docs/sequence_diagrams/create/ProjectCreation.webp?raw=true" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Update" %}

{% endtab %}
{% endtabs %}

### Postman Collection

The postman collection used to test APIs is [here](https://raw.githubusercontent.com/egovernments/DIGIT-Works/develop/backend/project-management-system/src/main/resources/Project%20Management%20System.postman\_collection.json). Please import the link into Postman and follow the instructions to run the collection.&#x20;

### Master Data Types

The following primary masters are defined by this module and used for validations. Other common masters such as department, tenant etc..are also used by this module.&#x20;

| Module Name | Master Name    | Sample Data                                                                                                                                                                                                  |
| ----------- | -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| works       | NatureOfWork   | [https://raw.githubusercontent.com/egovernments/works-mdms-data/DEV/data/pb/works/NatureOfWork.json](https://raw.githubusercontent.com/egovernments/works-mdms-data/DEV/data/pb/works/NatureOfWork.json)     |
| works       | ProjectType    | [https://raw.githubusercontent.com/egovernments/works-mdms-data/DEV/data/pb/works/ProjectType.json](https://raw.githubusercontent.com/egovernments/works-mdms-data/DEV/data/pb/works/ProjectType.json)       |
| works       | ProjectSubType | [https://raw.githubusercontent.com/egovernments/works-mdms-data/DEV/data/pb/works/ProjectSubType.json](https://raw.githubusercontent.com/egovernments/works-mdms-data/DEV/data/pb/works/ProjectSubType.json) |

