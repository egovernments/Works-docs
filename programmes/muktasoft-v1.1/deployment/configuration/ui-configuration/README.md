---
description: UI configuration for app
---

# UI Configuration

## **Overview**

This page provides details about the MuktaSoft UI configuration required to enable it in any environment.

## **DevOps Configuration**

In the DevOps repository of your organization, locate the following `"deploy-as-code/helm/environments/works-dev.yaml"`. Inside the environment YAML file used to deploy the Works platform, please add the following block of code:

```yaml

works-ui:
  custom-js-injection: |
    sub_filter.conf: "
      sub_filter  '<head>' '<head>
      <script src={{INSERT_YOUR_AWS_BUCKET_NAME}}/globalConfigsWorks.js type=text/javascript></script>';"
```

A dev environment sample file is linked [here](https://github.com/egovernments/DIGIT-DevOps/blob/8f80d072be92a8a3cbcac438ca3abdd5e999d17b/deploy-as-code/helm/environments/works-dev.yaml#L587). Note that you will have to modify this for your deployment.

## **Global Configuration**&#x20;

This section contains a config that is applicable globally to all UI modules. These need to be configured prior to service-specific UI configurations.

#### Steps to create a globalconfig.js file:

1. Create a config file (globalconfigs.js) with below-mentioned configurations (see code below).
2. Configure all the images/logos required in the S3 and add links as footerBWLogoURL, footerLogoURL.
3. Mention the state tenant ID as stateTenantId.
4. If any user roles have to be made invalid add as invalidEmployeeRoles.
5. Then push this global config file into your S3 bucket as globalconfigs.js.
6. Mention the globalConfigs file URL in your [`Environment config`](./#devops-configuration) .

```javascript
var globalConfigs = (function () {
  var stateTenantId = 'pg' // statetenantId
   var gmaps_api_key = '<<INSERT_GMAP_GENERATED_TOKEN>>';
   var contextPath = 'works-ui'; 
   var configModuleName = 'commonMuktaUiConfig'; 
   var centralInstanceEnabled = false;
   var footerBWLogoURL = '{{INSERT_YOUR_AWS_BUCKET_NAME}}/digit-footer-bw.png';
   var footerLogoURL = '{{INSERT_YOUR_AWS_BUCKET_NAME}}/digit-footer.png';
   var digitHomeURL = 'https://www.digit.org/';
   var xstateWebchatServices = 'wss://dev.digit.org/xstate-webchat/';
   var assetS3Bucket = '{{INSERT_YOUR_AWS_BUCKET_NAME}}';
   var invalidEmployeeRoles = ["CBO_ADMIN","STADMIN","ORG_ADMIN","ORG_STAFF","SYSTEM"] 

 
   var getConfig = function (key) {
     if (key === 'STATE_LEVEL_TENANT_ID') {
       return stateTenantId;
     }
     else if (key === 'GMAPS_API_KEY') {
       return gmaps_api_key;
     }
     else if (key === 'ENABLE_SINGLEINSTANCE') {
       return centralInstanceEnabled;
     } else if (key === 'DIGIT_FOOTER_BW') {
       return footerBWLogoURL;
     } else if (key === 'DIGIT_FOOTER') {
       return footerLogoURL;
     } else if (key === 'DIGIT_HOME_URL') {
       return digitHomeURL;
     } else if (key === 'xstate-webchat-services') {
       return xstateWebchatServices;
     } else if (key === 'S3BUCKET') {
       return assetS3Bucket;
     } else if (key === 'CONTEXT_PATH'){
	return contextPath;
     } else if (key === 'UICONFIG_MODULENAME'){
	return configModuleName;
     } else if (key === 'INVALIDROLES'){
	return invalidEmployeeRoles;
     }
   };
 
 
   return {
     getConfig
   };
 }());
```

## **MDMS Configuration**

All the UI Screen configurations required for MUKTA are present in this folder [commonMuktaUiConfig](https://github.com/egovernments/works-mdms-data/tree/DEV/data/pg/commonMuktaUiConfig).\
\
For other MDMS configurations, please check [here](common-configurations/mdms-configuration.md).

## **Roles Configuration**

Please refer to the table in [this document ](common-configurations/role-configuration.md)for screen-specific role configuration. Note that some of this will overlap with configurations done for the backend service modules. If already present in MDMS, please ignore it.&#x20;

## **Localization Configuration**

All strings localized per module are provided in this [sheet linked here](https://docs.google.com/spreadsheets/d/1Pk5TD\_GbnWB6z6cJ1IhsaVCxY9PKcBTg2IpIZ1dXgX4/edit#gid=934078231). To translate the UI into other languages, please follow this sheet and provide appropriate translations in your language.&#x20;

## **Reference Links**

Figma screens for the UI are [here](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=1-2). Refer to them to understand the MUKTA UI.&#x20;

