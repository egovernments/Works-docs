# Deployment Guide

## Overview

Browse through the headers below to find the steps to deploy the Mukta services.

## Service Builds

Please refer to this [link for the service builds](../release-notes/service-build-updates.md) used.

## Deploy Helm Charts

Helm charts for all Mukta services are [available here](https://github.com/egovernments/DIGIT-DevOps/tree/digit-works/deploy-as-code/helm/charts/digit-works). To override the environment variables, please create a Helm environment chart [like this](https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/environments/mukta-uat.yaml) for your DIGIT environment and customise the values.&#x20;

## Configure Master Data Management Service (MDMS)&#x20;

1. Create Common Masters
   * Create IdFormat.json that will be used by [egov-id-gen](https://core.digit.org/platform/core-services/id-generation-service) service.
   * Create StateInfo.json which will configure eligible languages for the tenant
2. Create tenants by [following this doc](https://urban.digit.org/platform/configure-digit/setting-up-master-data/configuring-tenants).
3. Create sample [boundary data](https://github.com/egovernments/works-mdms-data/tree/UAT/data/statea/cityone/egov-location). Refer to this [document](https://core.digit.org/guides/data-setup-guide/location-module) for more details&#x20;
4. Create configs for -
   * [Access Control services](https://core.digit.org/platform/core-services/access-control-services)
   * [Role mapping](https://github.com/egovernments/works-mdms-data/blob/UAT/data/statea/ACCESSCONTROL-ROLES/roles.json)
   * [Role-Action mappings](https://github.com/egovernments/works-mdms-data/blob/UAT/data/statea/ACCESSCONTROL-ROLEACTIONS/roleactions.json)
5. Configure map-config for the [tenant](https://github.com/egovernments/health-campaign-mdms/tree/v1.0.0/data/default/map-config)
6. Restart the MDMS server and restart the Zuul API gateway.&#x20;

{% hint style="info" %}
**Note:** Any modifications made to the configuration mentioned above will necessitate a restart of the MDMS server. Similarly, changes to the "action-test.json" and "roleactions.json" files will require a restart of the Zuul API gateway.
{% endhint %}

## Deploy DIGIT Core Services

Refer to the [section](../release-notes/service-build-updates.md)[ ](./#service-builds)for a list of core services to be deployed.

## Deploy DIGIT Works Services

Refer to the [section](../../../../platform/release-notes/service-build-updates.md) for a list of Works platform services to be deployed.

## Deploy MuktaSoft Services

Refer to the [section](../release-notes/service-build-updates.md) for a list of MuktaSoft services to be deployed.

## Configure Mukta

Find below the breakdown of the steps:&#x20;

* Step 1: Create a [persister config ](https://github.com/egovernments/works-configs/tree/QA/egov-persister)for each backend service. The [persister service](https://core.digit.org/platform/core-services/persister-service) will use these configurations.&#x20;
* Step 2: Create an [indexer config](https://github.com/egovernments/works-configs/tree/QA/egov-indexer) for each backend service. The [indexer service](https://core.digit.org/platform/core-services/indexer-service) will use these configurations.
* Step 3: Create [workflow configuration](https://github.com/egovernments/works-configs/tree/QA/workflow-configs) for the defined business services.&#x20;

{% hint style="info" %}
**Note:** If you make any changes to the indexer and persister configurations, you will need to restart the indexer and persister services for the changes to take effect.
{% endhint %}

## Create Users&#x20;

Create users following [this document](https://core.digit.org/guides/data-setup-guide/user-module).

## Upsert Localisation

Upsert localisation [following this document](https://core.digit.org/guides/data-setup-guide/localisation-module).



{% hint style="info" %}
### Mukta MDMS Configuration

MDMS configuration is listed for each service.

* [Project](../../../../platform/architecture/low-level-design/services/project.md)
* [Estimates](../../../../platform/platform-services/estimate.md)
* [Contracts](../../../../platform/configuration/service-configuration/contract.md#mdms-configuration)
* [Attendance](../../../../platform/configuration/service-configuration/attendance.md#configuration)
* [Muster Roll](../../../../platform/configuration/service-configuration/muster-roll.md#configuration)
* [Expense](../../../../platform/configuration/service-configuration/expense.md#configuration)
* [Expense Calculator](../muktasoft-services/expense-calculator.md)
{% endhint %}

###
