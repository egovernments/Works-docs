# Estimates

## Overview

Estimate Service will allow users to create estimates and forward them for approval to higher authorities across departments for technical, financial, and admin sanctions.

## API Specifications

### API Contract Link

{% embed url="https://raw.githubusercontent.com/egovernments/DIGIT-Works/develop/backend/estimate-service/docs/Estimate-service-1.0.0.yaml" %}

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

Estimate inbox uses the Inbox V2 service which queries ES to retrieve details for the inbox. For more information on Inbox V2, please refer [here](https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/2289271031/Event+based+inbox).&#x20;

#### Estimate PDF

TBD. The proposed sequence diagram is below.

![](../../../../../.gitbook/assets/Estimate-PDF.png)



