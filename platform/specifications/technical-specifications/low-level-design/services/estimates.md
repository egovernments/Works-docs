---
description: This service hosts estimates for projects.
---

# Estimates

## Overview

Estimate Service will allow users to create estimates and forward them for approval to higher authorities across departments for technical, financial, and admin sanctions.

### Dependencies

* Project
* MDMS
* User
* IDGen

## API Specifications

### API Contract Link

{% embed url="https://raw.githubusercontent.com/egovernments/DIGIT-Works/develop/backend/estimate-service/docs/Estimate-service-1.0.0.yaml" %}

### DB Schema Diagram

<figure><img src="https://github.com/egovernments/DIGIT-Works/blob/develop/backend/estimate-service/docs/diagrams/DB_Schema_Estimat-%20Service.png?raw=true" alt=""><figcaption></figcaption></figure>

### Estimate Flow Diagram

Below diagram shows the interaction between the estimate service and the persister, indexer. This does not follow the default recommended pattern. The indexer listens on a separate topic.&#x20;

<figure><img src="https://github.com/egovernments/DIGIT-Works/blob/develop/backend/estimate-service/docs/diagrams/EstimateFlowDiagram.png?raw=true" alt=""><figcaption></figcaption></figure>

### Web Sequence Diagrams

{% tabs %}
{% tab title="Create Estimate" %}
![](<../../../../../.gitbook/assets/Estimate Create.png>)


{% endtab %}

{% tab title="Update Estimate" %}
![](<../../../../../.gitbook/assets/Estimate Update.png>)


{% endtab %}

{% tab title="Search Estimate" %}
![](<../../../../../.gitbook/assets/Estimate Search.png>)


{% endtab %}
{% endtabs %}

#### Estimate Inbox

Estimate inbox uses the Inbox V2 service (from DIGIT core) which queries ES to retrieve details for the inbox. For more information on Inbox V2, please refer [here](https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/2289271031/Event+based+inbox).&#x20;

#### Estimate PDF

TBD. The proposed sequence diagram is below.

![](../../../../../.gitbook/assets/Estimate-PDF.png)



