---
description: New release features, enhancements, and fixes
---

# Release Notes

## Release Summary <a href="#release-summary" id="release-summary"></a>

DIGIT-Works release v1.0 is a new release that offers new platform features and functions, the details of which are provided below.

**Functional changes**&#x20;

* Added detailed estimate capability in estimate service.
* Added revision of estimate in estimate service.
* Added SOR and Non-SOR in estimate service.
* Added revision contract in contract service.
* Added measurement service validation while revision estimate and contract.
* Added SOR and Rate master using MDMS-v2.

**Non-functional changes**&#x20;

* Added contact details encryption in organisation service.
* Removed Tenant ID splitting from all the services and added modules in master-config.json.
* Expense service & calculator to read effectiveFrom and effectiveTo dates from master data and pick rates accordingly.
* Updated attendance service query while the changing CBO.

## New ‌Feature Additions <a href="#new-feature-additions" id="new-feature-additions"></a>

<table><thead><tr><th width="210">Feature</th><th>Description</th></tr></thead><tbody><tr><td>Estimate</td><td>Ability to add details like length, width, height, etc in an estimate details.</td></tr><tr><td>Estimate</td><td>Ability to create revision of an estimate.</td></tr><tr><td>Contract</td><td>Ability to revision for a contract.</td></tr><tr><td>Measurement Service</td><td>Create a Measurement, Modify a Measurement, View a Measurement &#x26; Search for a Measurement with Workflow</td></tr><tr><td>Measurement Registry</td><td>Create a Measurement, Modify a Measurement, View a Measurement &#x26; Search for a Measurement without Workflow</td></tr></tbody></table>

## Known Issues

The following things are known issues that need to be addressed as part of the platform roadmap:

* Integration with error queue implementation for all services and requisite measures to fix them need to be in place. In case of unrecoverable failures, this will provide a way to alert and institute measures to resolve.&#x20;
* Alert mechanisms when critical errors occur need to be in place, especially with billing.&#x20;
* Offline & low connectivity use cases need to be handled as a best practice.
* Improved logging across services to help troubleshoot
* Expense service to push workflow as part of the payload into the Kafka topic for persistence.&#x20;
* Remove SMS-related localisation from all services and move to a separate service.
* Performance testing and benchmarking of services.
* Security audit.

## Document Resources and Links <a href="#document-resources-and-links" id="document-resources-and-links"></a>

### Technical Documents

| Doc links                                                 |
| --------------------------------------------------------- |
| [High Level Design](../architecture/high-level-design.md) |
| [Low Level Design](../architecture/low-level-design/)     |

### Service Documents

| Doc Links                                                                             |
| ------------------------------------------------------------------------------------- |
| [Estimate](../platform-services/estimate.md)                                          |
| [Contract](../configuration/service-configuration/contract.md)                        |
| [Measurement](../architecture/low-level-design/services/detailed-measurement-book.md) |
