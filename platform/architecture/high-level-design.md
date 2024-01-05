# High Level Design

The platform architecture illustration below provides a visual representation of the key components and layers that facilitate a seamless flow of information across multiple departments.

<figure><img src="../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

The high-level design of the Works System is divided into three main parts, the details of which are available below.

1. [Master (Reference) Data](high-level-design.md#id-1.-master-reference-data)
2. [Works Registries](high-level-design.md#id-2.-works-registries)
3. [Reused/Enhanced DIGIT Core Services](high-level-design.md#id-3.-reused-enhanced-digit-services)

## **1. Master (Reference) Data**

This part includes various classifications of master data used in the Works platform. Some examples of this master data include:

* Organisation Class
* Organisation Functional Area
* Organisation Type
* Department
* Nature of Work
* Wage Seeker Skills
* Labour Charges
* Overheads
* Headcodes
* Applicable Charges
* Mode of Entrustment
* Beneficiary Type
* Designations
* Hierarchical Masters like Type of Work, Sub-type of Work
* Location (which is the same as DIGIT)

{% hint style="info" %}
DIGIT core service masters are not covered here. Refer to the service documentation to find the comprehensive list of services.
{% endhint %}

## 2. Works Registries

This part comprises various registries that store information related to the Works platform. Some of the key registries are:

* [**Individual Registry**](low-level-design/registries/individual.md)**:** Stores details of individual citizens, whether or not they are DIGIT system users. In cases where login access is required, user accounts are created and stored separately in the User registry. This allows for a clear distinction between citizen data and user management within the system.
* [**Organisation Registry:**](low-level-design/registries/organization.md) Holds details of different types of organisations, their functional areas, and classes.
* [**Bank Accounts Registry:**](low-level-design/registries/bank-account.md) Stores bank account details securely for online payments.

### Works Services

This part includes domain-specific services (listed below) developed or planned for the Works platform.

* [Project](../platform-services/project.md)
* [Estimate](../platform-services/estimate.md)
* [Contracts](../platform-services/contracts.md)
* [Attendance](../platform-services/attendance.md)
* [Muster roll](../platform-services/muster-roll.md)
* [Expense/Billing](../platform-services/expense.md)
* JIT Adapter (on the roadmap)
* Milestones (on the roadmap)
* Payment Calendar (on the roadmap)
* [Measurement Book](../platform-services/measurement-book-registry.md) (on the roadmap)

## 3. Reused/Enhanced DIGIT Services

This part lists the core services from DIGIT that are reused or enhanced in the Works Project. Some of these as-is reused DIGIT core services include:

* [Master Data Management Service (MDMS)](https://core.digit.org/platform/core-services/mdms-master-data-management-service)
* [Location Service](https://core.digit.org/platform/core-services/location-services)
* [User Service](https://core.digit.org/platform/core-services/user-services)
* [Access Control Service](https://core.digit.org/platform/core-services/access-control-services)
* [Zuul API Gateway](https://core.digit.org/platform/core-services/zuul-service)
* [PDF Service](https://core.digit.org/platform/core-services/pdf-generation-service)
* [File Store Service](https://core.digit.org/platform/core-services/filestore-service)
* [IdGen Service](https://core.digit.org/platform/core-services/id-generation-service)
* [Persister](https://core.digit.org/platform/core-services/persister-service)
* [Indexer](https://core.digit.org/platform/core-services/indexer-service)
* Inbox Service
* [Report Service](https://core.digit.org/platform/core-services/report-service)

This architectural design ensures seamless data flow across multiple departments and provides a foundation for efficient and integrated operations within the Works Management System.
