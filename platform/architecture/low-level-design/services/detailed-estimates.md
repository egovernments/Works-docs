---
description: This service models estimates for Works projects
---

# Detailed Estimates

## Overview

Estimate Service allows users to create estimates and forward them for approval to higher authorities across departments for technical, financial, and admin sanctions. For more technical information on this service, please refer to the [GitHub module README](https://github.com/egovernments/DIGIT-Works/blob/52188e228e33e03862ef149a40b1e14b08dea5e5/backend/estimates/README.md) and the [docs](https://github.com/egovernments/DIGIT-Works/tree/b0028753345abcfc812a637e1df998ad1ea45060/backend/estimates/docs) folder. The detailed estimate allows users to select a SOR (schedule of rates) item to add to the estimate and enter detailed measurements for the SOR item (if applicable).&#x20;

### Dependencies

* [Project](https://health.digit.org/platform/architecture/low-level-design/services/project)
* [MDMS](https://core.digit.org/platform/core-services/mdms-master-data-management-service)
* [Workflow](https://core.digit.org/platform/core-services/workflow-service)
* [Notification](https://core.digit.org/platform/core-services/sms-notification-service)
* [Localisation](https://core.digit.org/platform/core-services/localization-service)
* [Access Control](https://core.digit.org/platform/core-services/access-control-services)
* [User](https://core.digit.org/platform/core-services/user-services)
* [IDGen](https://core.digit.org/platform/core-services/id-generation-service)
* [MDMS V2](https://core.digit.org/platform/core-services/mdms-master-data-management-service/setting-up-master-data/mdms-rewritten)
* [Contract Service](../../../platform-services/contracts.md)
* [Measurement Service](../../../platform-services/measurement-book-service.md)

## API Specifications

**Base Path:** /estimates/

### API Contract Link

{% embed url="https://editor.swagger.io/?url=https://raw.githubusercontent.com/egovernments/DIGIT-Works/master/backend/estimates/docs/Estimate-service-1.0.0.yaml" %}
Estimates API specification
{% endembed %}

## Data Model

### DB Schema Diagram

<figure><img src="../../../../.gitbook/assets/estimate.png" alt=""><figcaption></figcaption></figure>

## Estimate Flow Diagram

The diagram below shows the interaction between the estimate service and the persister, indexer. This does not follow the default pattern. Instead, enrichment of the payload for the indexer happens via a separate consumer and then the enriched payload is pushed to a topic. The indexer listens to this topic and sends it to ElasticSearch.&#x20;

<div align="left">

<figure><img src="https://github.com/egovernments/DIGIT-Works/blob/master/backend/estimates/docs/diagrams/EstimateFlowDiagram.png?raw=true" alt=""><figcaption></figcaption></figure>

</div>

## Web Sequence Diagrams

{% tabs %}
{% tab title="Create Estimate" %}
<div data-full-width="true">

<figure><img src="../../../../.gitbook/assets/detailed-estimate-create.png" alt=""><figcaption><p>Create</p></figcaption></figure>

</div>

<figure><img src="../../../../.gitbook/assets/EstimateCreateValidations.png" alt=""><figcaption><p>Validations</p></figcaption></figure>
{% endtab %}

{% tab title="Update Estimate" %}
<figure><img src="../../../../.gitbook/assets/estimate-update-happypath.png" alt=""><figcaption><p>Detailed Estimate Update</p></figcaption></figure>
{% endtab %}

{% tab title="Search Estimate" %}

{% endtab %}
{% endtabs %}

### Revision Estimates

{% tabs %}
{% tab title="Create Revision Estimate" %}
<figure><img src="../../../../.gitbook/assets/Create Revision Estimate.png" alt=""><figcaption><p>Revision Estimate create flow</p></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/Revision Estimate Create Validation.png" alt=""><figcaption><p>Revision Estimate Validations</p></figcaption></figure>
{% endtab %}

{% tab title="Update Revision Estimate" %}
<figure><img src="../../../../.gitbook/assets/Update Revision Estimate.png" alt=""><figcaption><p>Update Revision Estimate Flow</p></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/Update Revision Estimate Validation.png" alt=""><figcaption><p>Validaiton of Revision Estimate Validation</p></figcaption></figure>
{% endtab %}
{% endtabs %}

### Estimate Inbox

Estimate inbox uses the Inbox V2 service (from DIGIT core) which queries ES to retrieve details for the inbox. For more information on Inbox V2, please refer [here](https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/2289271031/Event+based+inbox).&#x20;

{% hint style="info" %}
An inbox is needed when there is a workflow enabled for the service.&#x20;
{% endhint %}

### Estimate PDF

The proposed sequence diagram is below.

![](../../../../.gitbook/assets/Estimate-PDF.png)

## Postman Collections

TBD

## Related Topics

* [Functional specifications - Estimates](../../../functional-specifications/estimates.md)
* [Estimates module service configuration](../../../configuration/service-configuration/estimate.md)
* [Estimates module UI configuration](../../../../programmes/muktasoft-v2.0/deployment/configuration/ui-configuration/drafts/estimate/) - for MuktaSoft
* [Estimates user stories](../../../../programmes/muktasoft-v2.0/specifications/functional-requirements/user-stories/jit-fs-integration/) - for MuktaSoft
* [Employee user manual on using the Estimates module ](../../../../programmes/muktasoft-v2.0/implementation/training-resources/user-manual/employee-user-manual/detailed-estimate.md)- for MuktaSoft