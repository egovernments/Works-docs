---
description: New release features, enhancements, and fixes
---

# Release Notes

## Release Summary <a href="#release-summary" id="release-summary"></a>

DIGIT-Works release v1.0 is a new release that offers new platform features and functions, the details of which are provided below.

**Functional changes**&#x20;

* Added detailed estimate capability in estimate service
* Added revision of estimate in estimate service
* Added SOR and Non-SOR in estimate service
* Added revision contract in contract service
* Added measurement service validation while revision estimate and contract
* Added SOR and Rate master using MDMS-v2

**Non-functional changes**&#x20;

* Added contact details encryption in organisation service
* Removed Tenant ID splitting from all the services and added modules in master-config.json
* Expense service & calculator to read effectiveFrom and effectiveTo dates from master data and pick rates accordingly
* Updated attendance service query while the changing CBO

## New ‌Feature Additions <a href="#new-feature-additions" id="new-feature-additions"></a>

<table><thead><tr><th width="210">Feature</th><th>Description</th></tr></thead><tbody><tr><td>Estimate</td><td>Ability to add details like length, width, height, etc in an estimate details.</td></tr><tr><td>Estimate</td><td>Ability to create revision of an estimate.</td></tr><tr><td>Contract</td><td>Ability to revise contracts</td></tr><tr><td>Measurement Service</td><td>Create, modify, view &#x26; search Measurements in workflow</td></tr><tr><td>Measurement Registry</td><td>Create, modify, view &#x26; search Measurements without workflow</td></tr></tbody></table>

## Known Issues

The list below are known issues that need to be addressed as part of the platform roadmap:

* Multiple measurements can not be created at the same time for one contract.
* Integrated error queue implementation for all services along with the necessary measures for addressing issues, is required. In situations of unrecoverable failures, this setup will provide a means to trigger prompt alerts and implement corrective actions.
* Establishing alert mechanisms for critical errors, particularly in the context of billing, is required.&#x20;
* Managing offline & low connectivity use cases as a best practice.
* Improved logging across services to help troubleshoot.
* The expense service should include the workflow as part of the payload and push it into the Kafka topic for persistence.&#x20;
* Separate SMS-related localization from all services and migrate it to a dedicated service.
* Performance testing and benchmarking of services.
* Security audit.
* Multiple mdms-v2 calls in services, because mdms-v2 was returning only one master's response.
* Code refactoring of works-services like
  * Remove unused models
  * Change package names
  * Remove duplicate validation logic

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
