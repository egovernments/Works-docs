---
description: >-
  This page describes the integration with the Integrated Financial Management
  System of Odisha state
---

# IFMS Adapter

## Overview

Integration with Odisha IFMS is via the Just-in-Time (JIT) APIs provided by the Odisha treasury.

## Components

<figure><img src="../../../../.gitbook/assets/JITComponents (1).png" alt=""><figcaption></figcaption></figure>

## Sequence Diagram

#### Success Flow

{% tabs %}
{% tab title="Posting a payment instruction" %}
<figure><img src="../../../../.gitbook/assets/Posting-PI2.png" alt=""><figcaption><p>Posting a PI</p></figcaption></figure>
{% endtab %}

{% tab title="Checking Payment Status" %}
<figure><img src="../../../../.gitbook/assets/checking-status (1).png" alt=""><figcaption><p>Checking PI status</p></figcaption></figure>
{% endtab %}

{% tab title="Errors" %}
<figure><img src="../../../../.gitbook/assets/ErrorFlows (1).png" alt=""><figcaption><p>Handling errors</p></figcaption></figure>


{% endtab %}
{% endtabs %}



## API specifications

{% file src="../../../../.gitbook/assets/ifms-adapter-v1.0.0.yaml" %}

