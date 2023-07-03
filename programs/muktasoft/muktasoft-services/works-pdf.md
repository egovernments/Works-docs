# Works PDF

### Overview

Works-PDF is a service that can work between pdf-service and client requests. In works-pdf, there have multiple APIs to generate multiple PDFs. The service fetches data from multiple services, combines them, and sends the request to the PDF service to generate PDF.

It also has the functionality to generate an Excel file when payment is initiated. It listens to `expense-payment-create` topic and payment data.

### Dependency&#x20;

* MDMS
* PDF
* Project
* Estimates
* Muster Roll&#x20;
* Contract
* Organization
* Localization
* Expense
* Expense calculator
* Bankaccount
* Filestore

### Key Functionality

* It fetches data from multiple Create multiple PDFs like estimate, muster, project, etc.
* When a payment is created it generates excel files based on the payment bills, because listening to payment create topic.
* User can regenerate the payment excel using the same payment id.



### Code

[Works-PDF](https://github.com/egovernments/DIGIT-Works/tree/master/utilities/works-pdf)

### Deployment

* [Helm Chart](https://github.com/egovernments/DIGIT-DevOps/tree/digit-works/deploy-as-code/helm/charts/digit-works/utilities/works-pdf)
* [Environment](https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/environments/works-dev.yaml)&#x20;
  * Add all pdf configurations under pdf-service data config and format config
  * Add file type 'application/zip' under `xlsx` format in `egov-filestore` `allowed-file-formats-map`.

### PDF Configs

* Estimates PDF - [Data Config](https://github.com/egovernments/works-configs/blob/UAT/pdf-service/data-config/estimate.json), [Format Config](https://github.com/egovernments/works-configs/blob/UAT/pdf-service/format-config/estimate.json)
* Muster Roll PDF - [Data Config](https://github.com/egovernments/works-configs/blob/UAT/pdf-service/data-config/nominal-muster-roll.json), [Format Config](https://github.com/egovernments/works-configs/blob/UAT/pdf-service/format-config/nominal-muster-roll.json)
* Project PDF - [Data Config](https://github.com/egovernments/works-configs/blob/UAT/pdf-service/data-config/project-detail.json), [Format Config](https://github.com/egovernments/works-configs/blob/UAT/pdf-service/format-config/project-detail.json)
* Work order PDF - [Data Config](https://github.com/egovernments/works-configs/blob/UAT/pdf-service/data-config/work-order.json), [Format Config](https://github.com/egovernments/works-configs/blob/UAT/pdf-service/format-config/work-order.json)

### Roll Action&#x20;

<table><thead><tr><th width="507.3333333333333">API EndPoints</th><th>Roles</th></tr></thead><tbody><tr><td>/egov-pdf/download/estimate/estimates</td><td><p>ESTIMATE_CREATOR</p><p>ESTIMATE_VERIFIER</p><p>TECHNICAL_SANCTIONER</p><p>ESTIMATE_APPROVER</p><p>ESTIMATE_VIEWER</p></td></tr><tr><td>/egov-pdf/download/musterRoll/muster-roll</td><td><p>MUSTER_ROLL_APPROVER</p><p>ORG_ADMIN</p><p>MUSTER_ROLL_VERIFIER</p></td></tr><tr><td>/egov-pdf/download/project/project-details</td><td>PROJECT_VIEWER</td></tr><tr><td>/egov-pdf/download/workOrder/work-order</td><td><p>ORG_ADMIN</p><p>WORK_ORDER_VIEWER</p><p>WORK_ORDER_APPROVER</p></td></tr><tr><td>/egov-pdf/bill/_generate</td><td>BILL_ACCOUNTANT</td></tr><tr><td>/egov-pdf/bill/_search</td><td>BILL_ACCOUNTANT</td></tr></tbody></table>

### Account creation for deductions

Create accounts for purchase and wage bills, for head codes where category is deduction.&#x20;

E.g. this is the head code object

```
{
      "id": "5",
      "code": "LC",
      "category": "deduction",
      "service": "works.purchase",
      "description": "Labour Cess",
      "active": true,
      "effectiveFrom": 1682164954037,
      "effectiveTo": null
}
```

And tenantId is pg.citya

The format of referenceId is `Deduction_{tanentId}_{headcode}`

Then create a bank account with the field `referenceId` value `Deduction_pg.citya_LC`
