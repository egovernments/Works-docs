---
description: New release features, enhancements, and fixes
---

# Release Notes

## Release Summary <a href="#release-summary" id="release-summary"></a>

DIGIT-Works release v0.2 is a new release that offers new platform features and functions, the details of which are provided below.

**Functional changes**&#x20;

* Added time extension capability in contracts.
* Added signed audit capability for bank accounts and expense.
* Added ability to update organisation contact details.
* Integration from organisation to individual service.
* Added ability to update payment and bill status at line item level.

**Non-functional changes**&#x20;

* NA

## New ‌Feature Additions <a href="#new-feature-additions" id="new-feature-additions"></a>

<table><thead><tr><th width="210">Feature</th><th>Description</th></tr></thead><tbody><tr><td>Contract</td><td>Ability to extend time period for a contract.</td></tr><tr><td>Bank account</td><td>Signed audit logs enabled for bank account.</td></tr><tr><td>Expense</td><td>Added status update at line item level</td></tr></tbody></table>

## Known Issues

The following things are known issues that need to be addressed as part of the platform roadmap:

* Integration with error queue implementation for all services and requisite measures to fix them need to be in place. In case of unrecoverable failures, this will provide a way to alert and institute measures to resolve.&#x20;
* Alert mechanisms when critical errors occur need to be in place, especially with billing.&#x20;
* Offline & low connectivity use cases need to be handled as a best practice.
* Improved logging across services to help troubleshoot
* Attendance service and muster roll are to be made configurable by adding a unit of measurement.&#x20;
* Expense service to push workflow as part of the payload into the Kafka topic for persistence.&#x20;
* Expense service & calculator to read effectiveFrom and effectiveTo dates from master data and pick rates accordingly.
* Remove SMS related localisation from all services and move to a separate service.
* Master data to be reviewed for all modules and state level master data to be added in master-config.json. Eliminate extra code in modules to strip out state level tenant.
* Performance testing and benchmarking of services.
* Security audit.

## Document Resources and Links <a href="#document-resources-and-links" id="document-resources-and-links"></a>

### Technical Documents

| Doc links                                                 |
| --------------------------------------------------------- |
| [High Level Design](../architecture/high-level-design.md) |
| [Low Level Design](../architecture/low-level-design/)     |

### Service Documents

| Doc Links                                                                |
| ------------------------------------------------------------------------ |
| [Contract](../configuration/service-configuration/contract.md)           |
| [Bank Accounts](../configuration/service-configuration/bank-accounts.md) |
