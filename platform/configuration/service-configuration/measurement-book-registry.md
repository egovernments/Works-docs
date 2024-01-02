# Measurement Book Registry

## Overview

The registry provides functionality to add measures data.

## Pre-requisites

A running DIGIT platform is needed to deploy the measurement registry. Specifically, the following dependencies are needed:

* DIGIT backbone services
* Persister
* Indexer
* IDGen
* MDMS
* FileStore

## Functionality

This service provides APIs to create, update and search for measurement registry.  Refer to the [functional specifications here](../../functional-specifications/measurements.md).

## Deployment

The below variables should be configured for the measurement registry in the Helm environment file prior to deployment. The Helm environment file will be located under:

`https://github.com/`<mark style="color:red;">`{{ORG}}`</mark>`/DIGIT-DevOps/deploy-as-code/helm/environments/`<mark style="color:red;">`{{EnvironmentFile}}`</mark>`.yaml`

Refer to the [sample here](https://github.com/egovernments/DIGIT-DevOps/blob/unified-env/deploy-as-code/helm/environments/unified-works-dev.yaml).

* Add db-host,db-name,db-url,domain and all the digit core platform services configurations (Idgen, workflow,user etc.) in the YAML file.
* Add the ‘[egov-mdms-service](https://github.com/egovernments/DIGIT-DevOps/blob/unified-env/deploy-as-code/helm/environments/unified-works-dev.yaml#L416)’ related configuration to the respective environment YAML file. Make sure you change the gitsync.branch name.
* Check the measurement-registry persister file is added to the **`egov-persister.perister-yml-path`** variable. If not, please add the way it's done [here](https://github.com/egovernments/DIGIT-DevOps/blob/1f68ca9dcb4b27689c32f2026a4ea0de3761a88d/deploy-as-code/helm/environments/unified-works-dev.yaml#L445).
* Make sure to add the DB(Postgres and flyway) username & password in the respective environment secret yaml file. Follow the steps [here](https://github.com/egovernments/DIGIT-DevOps/blob/1f68ca9dcb4b27689c32f2026a4ea0de3761a88d/deploy-as-code/helm/environments/unified-works-dev-secrets.yaml#L3).
* Make sure to add the DIGIT core services-related secrets configured in the respective environment secret file. Follow the steps [here](https://github.com/egovernments/DIGIT-DevOps/blob/1f68ca9dcb4b27689c32f2026a4ea0de3761a88d/deploy-as-code/helm/environments/unified-works-dev-secrets.yaml#L3).

{% hint style="info" %}
Restart egov-mdms-service and egov-persister after the above changes are performed.
{% endhint %}

### Idgen Configuration

Make sure the id format is configured in the ‘IdFormat.json’ file of the ‘common-masters’ module. The sample [is available here](https://github.com/egovernments/egov-mdms-data/blob/0dd049ffddbc7c6078b940b5eb9eb4951eb8996a/data/pg/common-masters/IdFormat.json#L94C1-L94C1).&#x20;

| IDGen Format                                                                                                               |
| -------------------------------------------------------------------------------------------------------------------------- |
| <p></p><pre><code>{
  "format": "MB/[fy:yyyy-yy]/[SEQ_MEASUREMENT_NUM]",
  "idname": "mb.reference.number"
}
</code></pre> |

### Persister Configuration

Please make sure that the file[ <mark style="color:purple;">measurement-registry-persister.yml</mark>](https://github.com/egovernments/configs/blob/e3cca4152e63d9b671ed34c2e0fa321f1b4da87c/works/egov-persister/measurement-persister.yml) is present in the **`configs`** repository in the below location.&#x20;

[https://github.com/\<YOUR ORGANISATION>/configs/tree/UNIFIED-DEV/works/egov-persister](https://github.com/egovernments/configs/blob/e3cca4152e63d9b671ed34c2e0fa321f1b4da87c/works/egov-persister/measurement-persister.yml)

If not present, please make sure to add the persister YML file.&#x20;

{% hint style="warning" %}
Make sure to restart MDMS and the persister service after adding the file at the above location.
{% endhint %}
