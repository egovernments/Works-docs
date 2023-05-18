---
description: New release features, enhancements, and fixes
---

# Release Notes

## Release Summary <a href="#release-summary" id="release-summary"></a>

DIGIT-Works release v0.1 is a new release that offers new platform features and functions, the details of which are provided below.

**Functional changes**&#x20;

* **Projects** - Create a Project, Modify a Project, View a Project & Search a Project
* **Estimates** - Create an Estimate, Modify an Estimate, View an Estimate & Search an Estimate
* **Contract** - Create a Contract, Modify a Contract, View a Contract & Search for a Contract
* **Organisation** - Create an Organisation, Modify an Organisation, View an Organisation & Search for an Organisation
* **Attendance** - Create an Attendance Register, Modify an Attendance Register, View an Attendance Register & Search an Attendance Register
* **Muster** **roll -** Create a Muster roll, Update a Muster roll
* **Expense (Bill) -** Create a Wage Bill, Purchase Bill, Supervision Bill, Modify a Wage Bill, Purchase Bill, supervision Bill
* **Individual** - Create an Individual, Modify an Individual, View an Individual & Search an Individual.
* **Bank account** - Create a Bank account, Modify a Bank account, View a Bank account & Search a Bank account.

**Non-functional changes**&#x20;

* NA

## New ‌Feature Additions <a href="#new-feature-additions" id="new-feature-additions"></a>

| Feature        | Description                                                                                                               |
| -------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Projects       | Create a Project, Modify a Project, View a Project & Search a Project                                                     |
| Estimates      | Create an Estimate, Modify an Estimate, View an Estimate & Search an Estimate                                             |
| Contract       | Create a Contract, Modify a Contract, View a Contract & Search for a Contract                                             |
| Organisation   | Create an Organisation, Modify an Organisation, View an Organisation & Search for an Organisation                         |
| Attendance     | Create an Attendance Register, Modify an Attendance Register, View an Attendance Register & Search an Attendance Register |
| Muster roll    | Create a Muster roll, Update a Muster roll                                                                                |
| Expense (Bill) | Create a Wage Bill, Purchase Bill, Supervision Bill, Modify a Wage Bill, Purchase Bill, supervision Bill                  |
| Individual     | Create an Individual, Modify an Individual, View an Individual & Search an Individual.                                    |
| Bank account   | Create a Bank account, Modify a Bank account, View a Bank account & Search a Bank account.                                |

## Enhancements

It is a fresh development and getting released for the first time.

## Known Issues

The following things are known issues that need to be addressed as part of the platform roadmap:

* The payment status of bills needs to be updatable after offline processing.&#x20;
* Integration with error queue implementation for all services and requisite measures to fix them need to be in place. In case of unrecoverable failures, this will provide a way to alert and institute measures to resolve.&#x20;
* Alert mechanisms when critical errors occur need to be in place, especially with billing.&#x20;
* Offline & low connectivity use cases need to be handled as a best practice.
* Improved logging across services to help troubleshoot
* Attendance service and muster roll are to be made configurable by adding a unit of measurement.&#x20;
* Performance testing and benchmarking of services.
* Security audit.

## Document Resources and Links <a href="#document-resources-and-links" id="document-resources-and-links"></a>

### Technical Documents

| Doc links                                                                                          |
| -------------------------------------------------------------------------------------------------- |
| [High Level Design](../architecture/high-level-design.md)                                          |
| [Individual](../specifications/technical-specifications/low-level-design/registries/individual.md) |

### Backend Service Documents

| Doc Links                                                                                  |
| ------------------------------------------------------------------------------------------ |
| [Project](../configuration/service-configuration/project.md)                               |
| [Estimate](../../programs/mukta/configuration/service-configuration/estimate.md)           |
| [Contract](../../programs/mukta/configuration/service-configuration/contract.md)           |
| [Attendance](../../programs/mukta/configuration/service-configuration/attendance.md)       |
| [Muster Roll](../../programs/mukta/configuration/service-configuration/muster-roll.md)     |
| [Expense](../../programs/mukta/configuration/service-configuration/expense.md)             |
| [Bank Accounts](../../programs/mukta/configuration/service-configuration/bank-accounts.md) |
| [Organization](../../programs/mukta/configuration/service-configuration/organisation.md)   |
| [Individual](../../programs/mukta/configuration/service-configuration/individual.md)       |
