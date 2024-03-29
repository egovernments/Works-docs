# Deployment Guide

## Mukta Release Notes

| Version     | Date       | Description                |
| ----------- | ---------- | -------------------------- |
| Version 1.0 | 18/05/2023 | First release of MuktaSoft |

## Service Builds

Please refer to this [link for the service builds](deployment/release-notes/service-build-updates.md) used.

## Deployment Helm Charts

Helm charts for all Mukta services are [available here](https://github.com/egovernments/DIGIT-DevOps/tree/digit-works/deploy-as-code/helm/charts/digit-works). To override the environment variables, please create a Helm environment chart [like this](https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/environments/mukta-uat.yaml) for your DIGIT environment and customize the values.&#x20;

## Configure MDMS Configs Steps

1. Create Common Masters

&#x20;      a. Create IdFormat.json which will be used by [egov-id-gen](https://core.digit.org/platform/core-services/id-generation-service) service.

&#x20;      b. Create StateInfo.json which will configure eligible languages for tenant

2. Create tenants by [following this doc](https://urban.digit.org/platform/configure-digit/setting-up-master-data/configuring-tenants).
3. Create sample [boundary data](https://github.com/egovernments/works-mdms-data/tree/UAT/data/statea/cityone/egov-location). Refer for to this [document](https://core.digit.org/guides/data-setup-guide/location-module) for more details&#x20;
4. Create configs for [Access Control Sevices](https://core.digit.org/platform/core-services/access-control-services)

* [Role mapping](https://github.com/egovernments/works-mdms-data/blob/UAT/data/statea/ACCESSCONTROL-ROLES/roles.json)
* [Role-Action mappings](https://github.com/egovernments/works-mdms-data/blob/UAT/data/statea/ACCESSCONTROL-ROLEACTIONS/roleactions.json)

8. Configure map-config for the [tenant](https://github.com/egovernments/health-campaign-mdms/tree/v1.0.0/data/default/map-config)

&#x20;Restart the MDMS server and restart the Zuul API gateway.&#x20;

Note: Any modifications in the above configuration, need to restart the MDMS server. Any modifications to action-test.json and roleactions.json require a restart of the Zuul API gateway.

### Deploy Digit Core Services

Refer to the [section](deployment/release-notes/service-build-updates.md)[ ](deployment-guide.md#service-builds)for a list of core services to be deployed

### Deploy DIGIT Works Services

Refer to the [section](../../platform/release-notes/service-build-updates.md) for a list of Works platform services to be deployed

### Deploy MuktaSoft services

Refer to the [section](deployment/release-notes/service-build-updates.md) for a list of MuktaSoft services to be deployed

### Steps to configure Mukta configs

Step 1: Create a [persister config ](https://github.com/egovernments/works-configs/tree/UAT/egov-persister)for each backend service which will be picked by the [persister service](https://core.digit.org/platform/core-services/persister-service)

Step 2: Create an [indexer config](https://github.com/egovernments/works-configs/tree/UAT/egov-indexer) for each backend service which will be picked by the [indexer service](https://core.digit.org/platform/core-services/indexer-service)

Step 3: Create [workflow configuration](https://github.com/egovernments/works-configs/tree/UAT/workflow-configs) for all the business services defined here.&#x20;

Note: Any changes to indexer and persister configs, requires restart of indexer and persister.

### User Creation

Create users following [this document](https://core.digit.org/guides/data-setup-guide/user-module).

### Localisation upsert

Upsert localisation [following this document](https://core.digit.org/guides/data-setup-guide/localisation-module).

### Mukta MDMS Configuration:

MDMS configuration is listed for each service.

[Project](../../platform/architecture/low-level-design/services/project.md)

[Estimates](../../platform/platform-services/estimates.md)

[Contracts](../../programs/mukta/configuration/service-configuration/contract.md#mdms-configuration)

[Attendance](../../programs/mukta/configuration/service-configuration/attendance.md#configuration)

[Muster Roll](../../programs/mukta/configuration/service-configuration/muster-roll.md#configuration)

[Expense](../../programs/mukta/configuration/service-configuration/expense.md#configuration)

[Expense Calculator](muktasoft-services/expense-calculator.md)

