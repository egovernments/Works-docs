---
description: Describes a calculator service for computing attendance
---

# Muster Roll

## Overview

The muster roll service aggregates attendance logs from the attendance service based on some rules and presents an attendance aggregate for a time period (week or month) per individual. This can then be used to compute payments or other semantics.&#x20;

## API Specifications

### API Contract Link

{% embed url="https://editor.swagger.io/?url=https://raw.githubusercontent.com/egovernments/DIGIT-Works/develop/backend/muster-roll-service/Muster-Roll-Service-1.0.0.yaml" %}

## Data Model

### DB Schema Diagram

<figure><img src="../../../../../.gitbook/assets/Muster_roll_DbSchema.png" alt=""><figcaption></figcaption></figure>

### Web Sequence Diagrams

{% tabs %}
{% tab title="Create" %}
<figure><img src="../../../../../.gitbook/assets/Muster-Roll Create.png" alt=""><figcaption></figcaption></figure>


{% endtab %}

{% tab title="Second Tab" %}
<figure><img src="../../../../../.gitbook/assets/Muster-Roll Update.png" alt=""><figcaption></figcaption></figure>


{% endtab %}

{% tab title="Search" %}
<figure><img src="../../../../../.gitbook/assets/Muster-Roll Search.png" alt=""><figcaption></figcaption></figure>


{% endtab %}
{% endtabs %}



**MASTER DATA**&#x20;

{% embed url="https://github.com/egovernments/works-mdms-data/blob/DEV/data/pb/common-masters/MusterRoll.json" %}

{% embed url="https://github.com/egovernments/works-mdms-data/blob/DEV/data/pb/common-masters/WageSeekerSkills.json" %}

**POSTMAN SCRIPT**&#x20;

Steps to run the postman collection for the Muster Roll services APIs:

———————————————————————————————————

1\. Import the postman collection for musterRoll -&#x20;

[https://github.com/egovernments/DIGIT-Works/blob/develop/backend/muster-roll-service/src/main/resources/Muster%20Roll%20Service.postman\_collection.json](https://github.com/egovernments/DIGIT-Works/blob/develop/backend/muster-roll-service/src/main/resources/Muster%20Roll%20Service.postman\_collection.json)

2\. Import the environment variables required for running the postman collection -  [https://github.com/egovernments/DIGIT-Works/blob/develop/backend/muster-roll-service/src/main/resources/Muster%20Environment.postman\_environment.json](https://github.com/egovernments/DIGIT-Works/blob/develop/backend/muster-roll-service/src/main/resources/Muster%20Environment.postman\_environment.json)which will create an environment ‘Muster Environment’.

3\. MusterRoll requires the below services from Attendance Service API to be run prior to creating muster. So run the below services before running the musterRoll postman collection.

&#x20;   a) create Attendance register - [https://works-dev.digit.org/attendance/v1/\_create](https://works-dev.digit.org/attendance/v1/\_create)

&#x20;   b) Attendee enroll - [https://works-dev.digit.org/attendance/attendee/v1/\_create](https://works-dev.digit.org/attendance/attendee/v1/\_create)

&#x20;   c) Attendance log create - [https://works-dev.digit.org/attendance/log/v1/\_create](https://works-dev.digit.org/attendance/log/v1/\_create)

4\. Update the current value of the variable ‘registerId’ in the ‘Muster Environment’ with the id returned by the response of the create attendance register ( in step 3 a)

5\. Run the ‘Muster Roll Service’ postman collection as ‘Run Collection’ . It will run the /\_estimate, /\_create, /\_update and /\_search APIs success and validation error scenarios.

6\. Muster will be created for the attendees enrolled in the attendance register (in step 3 b) using the attendance logs created (in step 3 c).

The current value of environment variables ‘musterRollId’ and ‘musterRollNumber’ will be set from the response of the /\_create muster roll which will be used by /\_update and /\_search APIs.

&#x20;****&#x20;
