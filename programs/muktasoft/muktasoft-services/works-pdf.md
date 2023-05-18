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

### Integration

