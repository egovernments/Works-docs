# Estimate

## Overview

Estimate Service allows users to create estimates and forward them for Workflow approval to higher authorities across departments for technical, financial, and admin sanctions. A prepared estimate can then be tendered out for contracting.

### Dependencies

* Project
* MDMS
* Workflow
* Notification
* Access Control
* User
* IDGen
* mdmsV2
* Contract Service
* Measurement Service

## Key Functionalities

* Create/update/search for Work estimates for a project.&#x20;
* Allows upload of offline documents related to estimate creation as part of Create.
* Workflow and inbox integration
* Create/update/search for Work Revised Estimate for an existing approved estimate.

## Code

[Estimate](https://github.com/egovernments/DIGIT-Works/tree/master/backend/estimates)

## Integration

### **API Spec**

**Base Path:** /estimates/

[API spec](../architecture/low-level-design/services/detailed-estimates.md#api-contract-link)

### Postman Collection

Postman collection for this service is [available here](https://github.com/egovernments/DIGIT-Works/blob/141824e20b335a42397ec09f599ba832d75d5d96/backend/estimates/Estimate\_Service\_Collection.postman\_collection.json)

## Deployment

[Helm chart](https://github.com/egovernments/DIGIT-DevOps/blob/unified-env/deploy-as-code/helm/charts/digit-works/backend/estimates/values.yaml)

## Master Data

<table><thead><tr><th width="144.66666666666666">Master Name</th><th width="314">Sample Data</th><th>Description</th></tr></thead><tbody><tr><td>Overheads</td><td><p></p><pre class="language-json"><code class="lang-json">{
            "id": "1",
            "code": "SC",
            "description": "Supervision Charge",
            "active": true,
            "isAutoCalculated":true,
            "isWorkOrderValue":true,
            "type": "percentage",
            "value": "7.5",
            "effectiveFrom": 1682164954037,
            "effectiveTo": null
 }
</code></pre></td><td>Contains the overhead charges applicable on an estimate.</td></tr><tr><td>SOR </td><td><p>- Sample data for SOR<br></p><pre class="language-json"><code class="lang-json">{
"id": "SOR_000188",
"uom": "Nos",
"sorType": "W",
"quantity": 1000,
"sorSubType": "NA",
"sorVariant": "NA",
"description": "1000 Bricks for constructing any wall of length 10*10*10"
}
</code></pre></td><td>Contains a comprehensive list of items and rates defined by the department. To be used in preparation of an estimate.</td></tr><tr><td>SOR Rates</td><td><p>- Sample data for Rates </p><p></p><pre class="language-json"><code class="lang-json">{
    "rate": 989,
    "sorId": "SOR_000152",
    "validTo": "1697846400000",
    "validFrom": "1697587200000",
    "amountDetails": [
                        {
                            "type": "fixed",
                            "heads": "MH.2",
                            "amount": 979
                        }
                    ]
                }
</code></pre><p></p></td><td>Contains a comprehensive list of items and rates defined by the department. To be used in preparation of an estimate.</td></tr><tr><td>Category</td><td><p></p><pre class="language-json"><code class="lang-json">"Category": [
    {
      "name": "Overhead",
      "code": "OVERHEAD",      
	   "active": true
    },
    {
      "name": "SOR",
      "code": "SOR",      
	   "active": true
    },
    {
      "name": "non-SOR",
      "code": "NON-SOR",      
	   "active": true
    }
  ]
</code></pre></td><td>Contains the category of all items.<br> - SOR<br> - NON-SOR<br> - OVERHEAD</td></tr><tr><td>UOM</td><td><p></p><pre class="language-json"><code class="lang-json">{
            "code":"KG",
            "description":"Kilogram",
            "active":true,
            "effectiveFrom":1677044852,
            "effectiveTo":null
        },
</code></pre></td><td>Contains the unit of measurement for all categories.</td></tr></tbody></table>

&#x20;
