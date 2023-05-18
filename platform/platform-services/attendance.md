# Attendance

## Overview

The attendance module allows creation of an attendance register, enrolment of staff and attendees and capture of attendance records with entry/exit times. To compute attendance based on the logs, a calculator service should be built with specific business logic.&#x20;

### Dependencies

* DIGIT backbone services
* IDGen
* Persister

### Key Functionalities

* Allows creation/updation/search of an attendance register
* Allows mapping of staff and attendees to a register and enforces permissions.
* Logs entry and exit timestamps in epoch time for a referenced entity

### Code

[Module code](https://github.com/egovernments/DIGIT-Works/tree/master/backend/attendance)

### Deployment

[Helm Charts](https://github.com/egovernments/DIGIT-DevOps/tree/digit-works/deploy-as-code/helm/charts/digit-works/backend/attendance)

### Integration

#### Base Path:&#x20;

/attendance/

[API spec](../architecture/common-services/attendance-management/attendance-technical-docs.md#api-specifications)

[Attendance Postman collection](https://raw.githubusercontent.com/egovernments/DIGIT-Works/master/backend/attendance/Attendace%20Service%20Postman%20Scripts.postman\_collection.json)
