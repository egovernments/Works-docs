# Bill Scheduler

### Overview

This bill scheduler is a cronjob scheduler for calculating the supervision bill. It runs based on environment configuration. It triggers multiple APIs to generate the supervision bill.

### **Dependency**

* MDMS
* User
* Contract
* Expense Calculator

### Key Functionalities

* It creates supervision bills based on ACTIVE contracts using expense-calculate service /v1/\_calculate API.

### Code

[Bill Scheduler ](https://github.com/egovernments/DIGIT-Works/tree/master/utilities/expense-cronjob)

### Deployment

[Helm Charts](https://github.com/egovernments/DIGIT-DevOps/tree/digit-works/deploy-as-code/helm/charts/utilities/expense-cronjob)





&#x20;

