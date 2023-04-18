---
description: UI configuration for screens
---

# UI Configuration

**Mock Screens Figma Link:**&#x20;

{% embed url="https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=1:2&t=rN5iRNy8jvmI57VD-0" %}



**DevOps Configuration::**\
\
The following block of code has to be added to the environment file.

```yaml

works-ui:
  custom-js-injection: |
    sub_filter.conf: "
      sub_filter  '<head>' '<head>
      <script src=https://s3.ap-south-1.amazonaws.com/works-dev-asset/globalConfigsWorks.js type=text/javascript></script>';"
```

{% embed url="https://github.com/egovernments/DIGIT-DevOps/blob/8f80d072be92a8a3cbcac438ca3abdd5e999d17b/deploy-as-code/helm/environments/works-dev.yaml#L587" %}
Works dev Environment Configuration
{% endembed %}



**GlobalConfig (Env Configuration)**



```javascript
var globalConfigs = (function () {
  var stateTenantId = 'pg'
   var gmaps_api_key = 'AIzaSyAQOd09-vjmk1sXFb_ZQYDz2nlfhXq7Wf8';
   var contextPath = 'works-ui'; 
   var configModuleName = 'commonMuktaUiConfig'; 
   var centralInstanceEnabled = false;
   var footerBWLogoURL = 'https://s3.ap-south-1.amazonaws.com/egov-dev-assets/digit-footer-bw.png';
   var footerLogoURL = 'https://s3.ap-south-1.amazonaws.com/egov-dev-assets/digit-footer.png';
   var digitHomeURL = 'https://www.digit.org/';
   var xstateWebchatServices = 'wss://dev.digit.org/xstate-webchat/';
   var assetS3Bucket = 'egov-dev-assets';
   var invalidEmployeeRoles = ["CBO_ADMIN","STADMIN","ORG_ADMIN","ORG_STAFF"] 

 
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

{% embed url="https://s3.ap-south-1.amazonaws.com/works-dev-asset/globalConfigsWorks.js" %}
Global Config
{% endembed %}

**MDMS configs**\
All the UI Screen Config Of MUkta is present in this folder [commonMuktaUiConfig](https://github.com/egovernments/works-mdms-data/tree/DEV/data/pg/commonMuktaUiConfig)

[https://github.com/egovernments/works-mdms-data/tree/DEV/data/pg/commonMuktaUiConfig](https://github.com/egovernments/works-mdms-data/tree/DEV/data/pg/commonMuktaUiConfig)\
\
Other MDMS configs\


{% content-ref url="../../programs/mukta/configuration/ui-configuration/mdms-configuration.md" %}
[mdms-configuration.md](../../programs/mukta/configuration/ui-configuration/mdms-configuration.md)
{% endcontent-ref %}

{% embed url="https://docs.google.com/spreadsheets/d/1m72DeHvIrvt4P6NRlg2lAc-3Xrs_a56co7SqkrrZDKU/edit#gid=0" %}
MDMS Configs
{% endembed %}

**Roles Configuration**\


{% content-ref url="../../programs/mukta/configuration/ui-configuration/role-configuration.md" %}
[role-configuration.md](../../programs/mukta/configuration/ui-configuration/role-configuration.md)
{% endcontent-ref %}

\
\
**Localization Configs**\
[**https://docs.google.com/spreadsheets/d/1Pk5TD\_GbnWB6z6cJ1IhsaVCxY9PKcBTg2IpIZ1dXgX4/edit#gid=934078231**](https://docs.google.com/spreadsheets/d/1Pk5TD\_GbnWB6z6cJ1IhsaVCxY9PKcBTg2IpIZ1dXgX4/edit#gid=934078231)\
