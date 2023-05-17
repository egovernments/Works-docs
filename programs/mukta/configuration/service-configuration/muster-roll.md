---
description: >-
  Muster roll is a record of attendance and quantity of work done by wage
  seekers.
---

# Muster Roll

### Overview

A muster roll is a record of attendance, wages due and the quantity of work done by labour for a specific period of time.

The attendance service provides raw attendance logs. The muster roll service aggregates attendance logs and computes attendance based on business logic. For eg., whether attendance is to be measured in hours or days, what is considered a half day or a full day of attendance etc.. is business logic that will vary between implementations. These are configurable in this service and calculations on attendance will be performed based on these configurations.

### Pre-requisites

* Attendance
* Individual
* Persister
* MDMS
* Workflow
* Idgen
* Notification

### Functionality

Provides APIs to:

* Estimate wages of a wage seeker based on his/her attendance logs
* Create a muster roll with a list of wage seekers
* Update a muster roll with modified aggregate attendance
* Search for a muster roll based on some defined parameters. For more info, please see Swagger contract.

### Deployment

Below are the variables that should be configured for the muster roll service in the Helm environment file prior to deployment. The Helm environment file will be located under:

`https://github.com/`<mark style="color:red;">`{{ORG}}`</mark>`/DIGIT-DevOps/deploy-as-code/helm/environments/`<mark style="color:red;">`{{EnvironmentFile}}`</mark>`.yaml`

Please refer to a [sample here](https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/environments/works-dev.yaml).

* Add these ‘db-host’,’db-name’,’db-url’,’domain’ and all the digit core platform services configurations (Idgen, workflow,user etc.) in respective environments yaml file.
* Add muster-roll-service related environment variables’ value like the way it's done in the[ ‘dev](https://github.com/egovernments/DIGIT-DevOps/blob/5a9eb4c6141e19bd747238889ceed9bc9fffdc6f/deploy-as-code/helm/environments/works-dev.yaml#L175)’ environment yaml file.
  * [https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/environments/works-dev.yaml#L79](https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/environments/works-dev.yaml#L79)&#x20;
  * [https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/environments/works-dev.yaml#L203](https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/environments/works-dev.yaml#L203)&#x20;
  * [https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/environments/works-dev.yaml#L264](https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/environments/works-dev.yaml#L264)&#x20;
  * [https://github.com/egovernments/DIGIT-DevOps/commit/684a75232e422357245eab5fefacde28f64ffc0e](https://github.com/egovernments/DIGIT-DevOps/commit/684a75232e422357245eab5fefacde28f64ffc0e)&#x20;
  * [https://github.com/egovernments/DIGIT-DevOps/commit/478e493bc245e6e3cdea9d4e9599e2b51b880bb0](https://github.com/egovernments/DIGIT-DevOps/commit/478e493bc245e6e3cdea9d4e9599e2b51b880bb0)&#x20;
  * [https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/charts/digit-works/backend/muster-roll-service/values.yaml](https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/charts/digit-works/backend/muster-roll-service/values.yaml)&#x20;
* Add the [egov-mdms-service](https://github.com/egovernments/DIGIT-DevOps/blob/5a9eb4c6141e19bd747238889ceed9bc9fffdc6f/deploy-as-code/helm/environments/works-dev.yaml#L190) related configuration to the respective environment yaml file. Make sure you change the **`gitsync.branch`** name.
* Check the muster-roll-service persister file is added in the **`egov-persister.perister-yml-path`** variable. If not, please add the way it's done[ here](https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/environments/works-dev.yaml#L263).
* Make sure to add the DB(Postgres and flyway) username & password in the respective environment secret yaml file the way it's done[ here](https://github.com/egovernments/DIGIT-DevOps/blob/e742a292f2966bb1affb3b03edd643a777917ba1/deploy-as-code/helm/environments/works-dev-secrets.yaml#L3).
* Make sure to add the digit core services related secrets are configured in the respective environment secret file the way it's done[ here](https://github.com/egovernments/DIGIT-DevOps/blob/digit-works/deploy-as-code/helm/environments/works-dev-secrets.yaml).

### Configuration

#### Configure Actions

Add all the APIs exposed (refer to table below for actual APIs) to the actions.json file in MDMS

**Module name:** ACCESSCONTROL-ACTIONS-TEST

**Master name:** actions-test

#### Configure Roles

Configure roles based on the roles column below in roles.json file.&#x20;

**Module name:** ACCESSCONTROL-ROLES

**Master name:** roles

#### Configure Role-Action:

Role-action mapping is configured in MDMS per the table below .&#x20;

**Module name:** ACCESSCONTROL-ROLEACTIONS

**Master name:** roleactions.json

| Roles                                                                                                                       | API Endpoints              |
| --------------------------------------------------------------------------------------------------------------------------- | -------------------------- |
| <p>ORG_ADMIN</p><p>ORG_STAFF</p>                                                                                            | /muster-roll/v1/\_estimate |
| <p>ORG_ADMIN</p><p>ORG_STAFF</p>                                                                                            | /muster-roll/v1/\_create   |
| <p></p><p>ORG_ADMIN</p><p>ORG_STAFF</p><p>MUSTER_ROLL_VERIFIER</p><p>MUSTER_ROLL_APPROVER</p><p><br></p>                    | /muster-roll/v1/\_update   |
| <p>ORG_ADMIN</p><p>ORG_STAFF</p><p>MUSTER_ROLL_VERIFIER</p><p>MUSTER_ROLL_APPROVER</p><p>BILL_CREATOR</p><p>BILL_VIEWER</p> | /muster-roll/v1/\_search   |

#### Other masters to be added

Other muster roll masters are configured in the **`common-masters`** folder:

[MusterRoll.json](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pb/common-masters/MusterRoll.json)

[WageSeekers.json](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pb/common-masters/WageSeekerSkills.json)

### Integration

[Environment file](https://github.com/egovernments/DIGIT-Works/blob/develop/backend/muster-roll-service/src/main/resources/Muster%20Environment.postman\_environment.json)

[Postman collection](https://github.com/egovernments/DIGIT-Works/blob/develop/backend/muster-roll-service/src/main/resources/Muster%20Roll%20Service.postman\_collection.json)

#### Steps to run the postman collection:

1\. Import the postman collection for muster roll service into the Postman application.

2\. Import the environment variables required for running the postman collection. This will create an environment ‘Muster Environment’.

3\. MusterRoll requires the below services from Attendance Service API to be run. So run the below services before running the muster roll postman collection.

&#x20;   a) Create Attendance register - [https://{hostname}/attendance/v1/\_create](https://works-dev.digit.org/attendance/v1/\_create)

&#x20;   b) Enroll attendees to the register - [https://\{{hostname\}}/attendance/attendee/v1/\_create](https://works-dev.digit.org/attendance/attendee/v1/\_create)

&#x20;   c) Attendance log create - [https://\{{hostname\}}/attendance/log/v1/\_create](https://works-dev.digit.org/attendance/log/v1/\_create)

4\. Update the current value of the variable ‘registerId’ in ‘Muster Environment’ with the id returned by the response in the create attendance register ( in step 3 a)

5\. Run ‘Muster Roll Service’ postman collection as ‘Run Collection’ . It will run the /\_estimate, /\_create, /\_update and /\_search api’s success and validation error scenarios.

6\. Muster will be created for the attendees enrolled in the attendance register (in step 3 b) using the attendance logs created (in step 3 c).

&#x20;The current value of environment variables ‘musterRollId’ and ‘musterRollNumber’ will be set from the response of the /\_create muster roll which will be used by /\_update and /\_search apis.

\




\
