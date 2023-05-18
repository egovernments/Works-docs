---
description: This service models estimates for Works projects.
---

# Estimates

## Overview

Estimate Service will allow users to create estimates and forward them for approval to higher authorities across departments for technical, financial, and admin sanctions. For more technical information on this service, please refer to the [GitHub module README](https://github.com/egovernments/DIGIT-Works/tree/develop/backend/estimate-service) as well as the [docs](https://github.com/egovernments/DIGIT-Works/tree/develop/backend/estimate-service/docs) folder.

### Dependencies

* Project
* MDMS
* Workflow
* Notification
* Access Control
* User
* IDGen

## API Specifications

**Base Path:** /estimates/

### API Contract Link

{% embed url="https://editor.swagger.io/?url=https://raw.githubusercontent.com/egovernments/DIGIT-Works/master/backend/estimates/docs/Estimate-service-1.0.0.yaml" %}
Estimates API specification
{% endembed %}

### DB Schema Diagram

<figure><img src="https://github.com/egovernments/DIGIT-Works/blob/master/backend/estimates/docs/diagrams/DB_Schema_Estimat-%20Service.png?raw=true" alt=""><figcaption><p>Estimate Schema Diagram</p></figcaption></figure>

#### Estimate Flow Diagram

The below diagram shows the interaction between the estimate service and the persister, indexer. This does not follow the default pattern. Instead, enrichment of the payload for the indexer happens via a separate consumer and then the enriched payload is pushed to a topic. The indexer listens to this topic and sends it to ElasticSearch.&#x20;

<figure><img src="https://github.com/egovernments/DIGIT-Works/blob/master/backend/estimates/docs/diagrams/EstimateFlowDiagram.png?raw=true" alt=""><figcaption></figcaption></figure>

### Web Sequence Diagrams

{% tabs %}
{% tab title="Create Estimate" %}
![](<../../../../.gitbook/assets/Estimate Create.png>)


{% endtab %}

{% tab title="Update Estimate" %}
![](<../../../../.gitbook/assets/Estimate Update.png>)


{% endtab %}

{% tab title="Search Estimate" %}
![](<../../../../.gitbook/assets/Estimate Search.png>)


{% endtab %}
{% endtabs %}

#### Estimate Inbox

Estimate inbox uses the Inbox V2 service (from DIGIT core) which queries ES to retrieve details for the inbox. For more information on Inbox V2, please refer [here](https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/2289271031/Event+based+inbox).&#x20;

{% hint style="info" %}
Inbox is needed when there is a workflow enabled for the service.&#x20;
{% endhint %}

#### Estimate PDF

The proposed sequence diagram is below.

![](../../../../.gitbook/assets/Estimate-PDF.png)

#### Postman Collections

TBD

