# Detailed Measurement Book

## Overview

The measurement book is a measure of progress in a Works contract.

## API Specifications

### API Contract Link

{% embed url="https://editor.swagger.io/?url=https://raw.githubusercontent.com/egovernments/DIGIT-Specs/works-v2/Domain%20Services/Works/Measurement-Book-v1.0.0.yaml" %}

### APIs

{% swagger src="../../../../.gitbook/assets/Measurement-Book-v1.0.0.yaml" path="/measurement/v1/_create" method="post" %}
[Measurement-Book-v1.0.0.yaml](../../../../.gitbook/assets/Measurement-Book-v1.0.0.yaml)
{% endswagger %}

{% swagger src="../../../../.gitbook/assets/Measurement-Book-v1.0.0.yaml" path="/measurement/v1/_update" method="post" %}
[Measurement-Book-v1.0.0.yaml](../../../../.gitbook/assets/Measurement-Book-v1.0.0.yaml)
{% endswagger %}

{% swagger src="../../../../.gitbook/assets/Measurement-Book-v1.0.0 (1).yaml" path="/measurement/v1/_search" method="post" %}
[Measurement-Book-v1.0.0 (1).yaml](<../../../../.gitbook/assets/Measurement-Book-v1.0.0 (1).yaml>)
{% endswagger %}

{% swagger src="../../../../.gitbook/assets/Measurement-Book-v1.0.0.yaml" path="/measurementservice/v1/_create" method="post" %}
[Measurement-Book-v1.0.0.yaml](../../../../.gitbook/assets/Measurement-Book-v1.0.0.yaml)
{% endswagger %}

{% swagger src="../../../../.gitbook/assets/Measurement-Book-v1.0.0.yaml" path="/measurementservice/v1/_update" method="post" %}
[Measurement-Book-v1.0.0.yaml](../../../../.gitbook/assets/Measurement-Book-v1.0.0.yaml)
{% endswagger %}

{% swagger src="../../../../.gitbook/assets/Measurement-Book-v1.0.0 (1).yaml" path="/measurementservice/v1/_search" method="post" %}
[Measurement-Book-v1.0.0 (1).yaml](<../../../../.gitbook/assets/Measurement-Book-v1.0.0 (1).yaml>)
{% endswagger %}

## Data Model&#x20;

### DB Schema Diagram

<figure><img src="../../../../.gitbook/assets/measurement registry.png" alt=""><figcaption></figcaption></figure>

<div align="left">

<figure><img src="../../../../.gitbook/assets/measurement service.png" alt="" width="187"><figcaption></figcaption></figure>

</div>

### Web Sequence Diagrams

#### Measurement Registry

{% tabs %}
{% tab title="Create" %}
<figure><img src="../../../../.gitbook/assets/MBRegistryCreateAPI.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/MBRegistryCreateAPIValidation.png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Update" %}
<figure><img src="../../../../.gitbook/assets/MBRegistryUpdateAPI.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/MBRegistryUpdateAPIValidation.png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Search" %}
<figure><img src="../../../../.gitbook/assets/MBRegistrySearchAPI.png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

#### Measurement Service

{% tabs %}
{% tab title="Create" %}
<figure><img src="../../../../.gitbook/assets/MBServiceCreateAPI.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/MBServiceCreateAPIValidation.png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Update" %}
<figure><img src="../../../../.gitbook/assets/MBServiceUpdateAPI.png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Search" %}
<figure><img src="../../../../.gitbook/assets/MBServiceSearchAPI (1).png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

## Related Topics

1. [Functional Specifications - Measurement Book](../../../functional-specifications/measurements.md)
2. [Detailed Measurement Book User Stories](../../../../programmes/muktasoft-v2.0/specifications/functional-requirements/user-stories/detailed-mb/)
3. [Measurement Book UI Configuration](../../../../programmes/muktasoft-v2.0/deployment/configuration/ui-configuration/modules/measurement.md)
