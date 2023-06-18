---
description: >-
  This page describes the integration with the Integrated Financial Management
  System of Odisha state
---

# IFMS Adapter

## Overview

Integration with Odisha IFMS is via the Just-in-Time (JIT) APIs provided by the Odisha treasury.

## Components

<figure><img src="../../../.gitbook/assets/JITComponents (1).png" alt=""><figcaption></figcaption></figure>

## Sequence Diagram

#### Happy path

{% tabs %}
{% tab title="Posting a payment instruction" %}
<figure><img src="../../../.gitbook/assets/posting-pi (1).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Checking Payment Status" %}
<figure><img src="../../../.gitbook/assets/checking-status.svg" alt=""><figcaption><p>Checking PI status</p></figcaption></figure>
{% endtab %}
{% endtabs %}

#### Errors

<figure><img src="../../../.gitbook/assets/errorconditions.png" alt=""><figcaption><p>Handling errors</p></figcaption></figure>

## API specifications

{% file src="../../../.gitbook/assets/ifms-adapter-v1.0.0.yaml" %}

