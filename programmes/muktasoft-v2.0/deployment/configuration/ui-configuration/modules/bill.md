# Bill

## Overview

This module is used to handle all billing-related actions such as Create, Update and View Bills.

This module has 5  associated screens :&#x20;

1. Create (Purchase Bill)
2. Search
3. View (Wage, Purchase, Supervision)
4. Modify (Purchase Bill)
5. Download Bills&#x20;

## Configurations

### MDMS Configurations

<table><thead><tr><th width="84.99999999999997">#</th><th width="223">Data</th><th>MDMS Link</th></tr></thead><tbody><tr><td>1</td><td>BillType</td><td><a href="https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/expense/BusinessService.json">https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/expense/BusinessService.json</a></td></tr><tr><td>2</td><td>TenantBoundary</td><td><a href="https://github.com/egovernments/works-mdms-data/blob/8285bc63aac7f056326165897ac18918520c9723/data/pg/citya/egov-location/boundary-data.json">https://github.com/egovernments/works-mdms-data/blob/8285bc63aac7f056326165897ac18918520c9723/data/pg/citya/egov-location/boundary-data.json</a></td></tr></tbody></table>

### Module Enablement Configuration&#x20;

Set module code as “Expenditure” in Module.js for Billing Module. Refer [CityModule.json](https://github.com/egovernments/works-mdms-data/blob/481752ba70aa29d235967d8ba6080685d897324a/data/pg/tenant/citymodule.json)

{% code lineNumbers="true" %}
```
{
            "module": "Expenditure",
            "code": "Expenditure",
            "active": true,
            "order": 7,
            "tenants": [
                {
                    "code": "pg.cityb"
                },
                {
                    "code": "pg.cityc"
                },
                {
                    "code": "pg.citya"
                }
            ]
        }

```
{% endcode %}

Enable Module in App.js. Update the object ‘enabledModules’. Use the code “Expenditure”. This code should match the code of the cityModule.json, mentioned above.

### Role-action Mapping

<table><thead><tr><th width="105">#</th><th>API</th><th width="146">Action ID</th><th>Roles</th></tr></thead><tbody><tr><td>1</td><td>/expense-calculator/purchase/v1/_createbill</td><td>112</td><td>BILL_CREATOR</td></tr><tr><td>2</td><td>/expense-calculator/v1/_search</td><td>113</td><td>BILL_CREATOR<br>BILL_VERIFIER<br>BILL_VIEWER<br>BILL_ACCOUNTANT</td></tr><tr><td>3</td><td>/expense/bill/v1/_search</td><td>106</td><td>BILL_CREATOR<br>BILL_VERIFIER<br>BILL_APPROVER<br>BILL_ACCOUNTANT</td></tr><tr><td>4</td><td>/wms/expense/_search</td><td>110</td><td>BILL_CREATOR<br>BILL_VERIFIER<br>BILL_APPROVER<br>BILL_ACCOUNTANT</td></tr><tr><td>5</td><td>/expense/payment/v1/_create</td><td>116</td><td>BILL_ACCOUNTANT</td></tr><tr><td>6</td><td>/egov-pdf/bill/_search</td><td>114</td><td>BILL_CREATOR</td></tr><tr><td>7</td><td>/expense/payment/v1/_search</td><td>122</td><td>BILL_ACCOUNTANT</td></tr><tr><td>8</td><td>/expense/payment/v1/_update</td><td>125</td><td>BILL_ACCOUNTANT</td></tr><tr><td></td><td></td><td></td><td></td></tr></tbody></table>

### Sidebar Configuration&#x20;

<table><thead><tr><th width="58">#</th><th width="121">Screens</th><th width="182">Navigation URL</th><th width="228">Left Icon Updates</th><th>Roles</th></tr></thead><tbody><tr><td>1</td><td>Search Bills</td><td>/works-ui/employee/expenditure/search-bill</td><td>dynamic:ExpenditureIcon</td><td><p></p><p>BILL_VIEWER</p></td></tr></tbody></table>

Sample object for a sidebar action define in MDMS (containing navigationUrl)

{% code lineNumbers="true" %}
```
{
      "id": 56,
      "name": "BILLS",
      "url": "url",
      "displayName": "Bill Search",
      "orderNumber": 2,
      "parentModule": "",
      "enabled": true,
      "serviceCode": "BILLS",
      "code": "null",
      "navigationURL": "/works-ui/employee/expenditure/search-bill",
      "path": "BILLS.BillSearch",
      "leftIcon": "dynamic:ExpenditureIcon"
    }

```
{% endcode %}

### Screen Configuration&#x20;

<table><thead><tr><th width="105.66666666666666">#</th><th>Screen</th><th>Configuration</th></tr></thead><tbody><tr><td>1</td><td>Create/Modify Purchase bill</td><td><a href="https://github.com/egovernments/works-mdms-data/blob/DEV/data/pg/commonMuktaUiConfig/CreatePurchaseBillConfig.json">Create Bill Config</a></td></tr></tbody></table>

### Localization Configuration & Modules

<table><thead><tr><th width="241">TenantID</th><th>Module</th></tr></thead><tbody><tr><td>pg</td><td>rainmaker-expenditure</td></tr><tr><td>pg</td><td>rainmaker-common</td></tr><tr><td>pg</td><td>rainmaker-common-masters</td></tr><tr><td>pg</td><td>rainmaker-workflow</td></tr><tr><td>pg.citya</td><td>rainmaker-pg.citya</td></tr></tbody></table>

### Workflow Configuration

\<details>

## Customization

1. Create Purchase Bill screen -
   * Please use the common Utility “PreProcessMDMSConfig”.&#x20;
   * Pass the associated dependencies for the config.
   * The utility will return a config which will run through FormComposer.
   * Refer to docs for Pre-Process config in Component comments.
2. Search Bill screen -
   * Please use the common utility “preProcessMDMSConfigInboxSearch”.
   * Pass the associated dependencies for the config.
   * The utility will return a config which will run through RenderFormFields.
   * Refer to docs for Pre-Process config in Component comments.
   * All the Inbox and Search Screens throughout the app are rendered using this component [Inbox/Search Composer](https://github.com/egovernments/DIGIT-Works/blob/c2a234bb4b21f0e54ca9664ee3e99d72ce871168/frontend/micro-ui/web/micro-ui-internals/packages/react-components/src/hoc/InboxSearchComposer.js)
   * Checkbox selection is added to the results table displayed in the search screen based on the search config passed via MDMS
3. Download Bill screen -&#x20;
   * DownloadBillConfig is used to render a table to show bills where the download link is provided to download respective bills.
