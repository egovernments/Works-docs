---
description: >-
  User should be able to create → Forward (or) check → Forward/Reject an
  estimate.
---

# Estimate Worflow

<figure><img src="../../../../../../../.gitbook/assets/image (29) (1).png" alt=""><figcaption><p>Estimate Workflow</p></figcaption></figure>

Once the Estimate are created they will move to the respective checker and approver's inbox as pending items.

<figure><img src="../../../../../../../.gitbook/assets/Screenshot from 2022-11-07 17-20-16.png" alt=""><figcaption><p>Estimate Proposal InboxView Estimate</p></figcaption></figure>

#### View Estimate

* From Estimate Proposal Inbox, User can come into Estimate View Screen where Details of Estimate present while creating the estimate and Workflow history will be displayed.
* User can take necessary actions by clicking on Actions Menu.

<figure><img src="../../../../../../../.gitbook/assets/image (2) (1).png" alt=""><figcaption><p>View Estimate Screen</p></figcaption></figure>

Sample ProcessInstance Worflow Object as given below:

```json
{
    "RequestInfo": {
        "apiId": "estimate-service",
        "action": "",
        "did": 1,
        "key": "",
        "msgId": "20170310130900|en_IN",
        "requesterId": "",
        "ts": 1513579888683,
        "ver": "1.0.0",
        "authToken": "94ecb06f-8e5b-4798-af8f-56a987560209",
        "userInfo":{
            "uuid":"7e46e32c-187c-4fb4-9d6b-1ac70fa8f011"
        }
    },
    "BusinessServices": [
        {
            "tenantId": "pb",
            "businessService": "estimate-approval-2",
            "business": "estimate-service",
            "businessServiceSla": 432000000,
            "states": [
                {
                    "sla": null,
                    "state": null,
                    "applicationStatus": null,
                    "docUploadRequired": false,
                    "isStartState": true,
                    "isTerminateState": false,
                    "isStateUpdatable": true,
                    "actions": [
                        {
                            "action": "CREATE",
                            "nextState": "CREATED",
                            "roles": [
                                "EST_CREATOR"
                            ]
                        }
                    ]
                },
                {
                    "sla": null,
                    "state": "CREATED",
                    "applicationStatus": "CREATED",
                    "docUploadRequired": false,
                    "isStartState": true,
                    "isTerminateState": false,
                    "isStateUpdatable": true,
                    "actions": [
                        {
                            "action": "CHECK",
                            "nextState": "CHECKED",
                            "roles": [
                                "EST_CHECKER"
                            ]
                        },
                        {
                            "action": "REJECT",
                            "nextState": "REJECTED",
                            "roles": [
                                "EST_CHECKER"
                            ]
                        }
                    ]
                },
                {
                    "sla": null,
                    "state": "CHECKED",
                    "applicationStatus": "CHECKED",
                    "docUploadRequired": false,
                    "isStartState": false,
                    "isTerminateState": false,
                    "isStateUpdatable": true,
                    "actions": [
                        {
                            "action": "TECHNICALSANCATION",
                            "nextState": "TECHNICALSANCATIONDONE",
                            "roles": [
                                "EST_TECH_SANC"
                            ]
                        },
                        {
                            "action": "REJECT",
                            "nextState": "REJECTED",
                            "roles": [
                                "EST_TECH_SANC"
                            ]
                        }
                    ]
                },
                {
                    "sla": null,
                    "state": "TECHNICALSANCATIONDONE",
                    "applicationStatus": "TECHNICALSANCATIONDONE",
                    "docUploadRequired": false,
                    "isStartState": false,
                    "isTerminateState": false,
                    "isStateUpdatable": true,
                    "actions": [
                        {
                            "action": "ADMINSANCTION",
                            "nextState": "APPROVED",
                            "roles": [
                                "EST_ADMIN_SANC"
                            ]
                        },
                        {
                            "action": "REJECT",
                            "nextState": "REJECTED",
                            "roles": [
                                "EST_ADMIN_SANC"
                            ]
                        }
                    ]
                },
                {
                    "sla": null,
                    "state": "REJECTED",
                    "applicationStatus": "REJECTED",
                    "docUploadRequired": false,
                    "isStartState": false,
                    "isTerminateState": false,
                    "isStateUpdatable": true,
                    "actions": [
                        {
                            "action": "EDIT",
                            "nextState": "CREATED",
                            "roles": [
                                "EST_CREATOR"
                            ]
                        }
                    ]
                },
                {
                    "sla": null,
                    "state": "APPROVED",
                    "applicationStatus": "APPROVED",
                    "docUploadRequired": false,
                    "isStartState": false,
                    "isTerminateState": true,
                    "isStateUpdatable": false,
                    "actions": null
                }
            ]
        }
    ]
}
```

#### Sample Curl to fetch ProcessInstance

{% code overflow="wrap" %}
```json
curl 'https://works-dev.digit.org/estimate-service/estimate/v1/_search?tenantId=pb.amritsar&department=DEPT_1&typeofwork=Road&fromProposalDate=1667241000000&toProposalDate=1667845799000&limit=10&sortBy=department&sortOrder=DESC&_=1667829358481' \
  -H 'authority: works-dev.digit.org' \
  -H 'accept: application/json, text/plain, */*' \
  -H 'accept-language: en-US,en;q=0.9' \
  -H 'content-type: application/json;charset=UTF-8' \
  -H 'origin: https://works-dev.digit.org' \
  -H 'referer: https://works-dev.digit.org/works-ui/employee/works/search-Estimate' \
  -H 'sec-ch-ua: "Google Chrome";v="107", "Chromium";v="107", "Not=A?Brand";v="24"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "Linux"' \
  -H 'sec-fetch-dest: empty' \
  -H 'sec-fetch-mode: cors' \
  -H 'sec-fetch-site: same-origin' \
  -H 'user-agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/107.0.0.0 Safari/537.36' \
  --data-raw '{
    "RequestInfo":{
      "apiId":"Rainmaker",
      "authToken":"153c3161-55ce-4485-96fa-f67ea9757eea",
      "msgId":"1667829358480|en_IN",
      "plainAccessRequest":{}
    }
  }'
```
{% endcode %}

### Taking Actions on Estimate

An Action bar on the View Estimate Screen shows the list of actions&#x20;

1. Forward Estimate
2. Reject Estimate
3. Modify Estimate
4. Approve Estimate

When any action is clicked respective popup is rendered according to the selected action. We have created three popups for approve, forward and reject. They are shown below

<figure><img src="../../../../../../../.gitbook/assets/image (13) (1).png" alt=""><figcaption><p>Forward Processing Modal</p></figcaption></figure>

<figure><img src="../../../../../../../.gitbook/assets/Screenshot from 2022-11-07 19-36-48.png" alt=""><figcaption><p>Reject Processing Modal</p></figcaption></figure>

<figure><img src="../../../../../../../.gitbook/assets/image (2) (2).png" alt=""><figcaption><p>Approve Estimate Modal</p></figcaption></figure>

When these popups are submitted, Update Estimate API is called containing the relevant updates in the workflow object contained in request body. Estimate service internally calls the workflow service and updates the status of application.

#### Sample curl for Update Estimate

```json
curl 'http://localhost:3000/estimate-service/estimate/v1/_update' \
  -H 'Accept: application/json, text/plain, */*' \
  -H 'Accept-Language: en-US,en;q=0.9' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json;charset=UTF-8' \
  -H 'Origin: http://localhost:3000' \
  -H 'Referer: http://localhost:3000/works-ui/employee/works/view-estimate?tenantId=pb.amritsar&estimateNumber=EP/2022-23/11/000143&department=DEPT_1' \
  -H 'Sec-Fetch-Dest: empty' \
  -H 'Sec-Fetch-Mode: cors' \
  -H 'Sec-Fetch-Site: same-origin' \
  -H 'User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/107.0.0.0 Safari/537.36' \
  -H 'sec-ch-ua: "Google Chrome";v="107", "Chromium";v="107", "Not=A?Brand";v="24"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "Linux"' \
  --data-raw '{
      "estimate":{
          "id":"e9d1e26c-7231-4fad-97f0-297dab173c23",
          "tenantId":"pb.amritsar",
          "estimateNumber":"EP/2022-23/11/000143",
          "adminSanctionNumber":null,
          "proposalDate":1667824800917,
          "status":"ACTIVE",
          "estimateStatus":"CREATED",
          "subject":"Construct new schools",
          "requirementNumber":"88888999",
          "description":"Construct new schools",
          "department":"DEPT_1",
          "location":"pb.amritsar:ADMIN:pb.amritsar:Z1:B2:SUN40",
          "workCategory":"Engineering",
          "beneficiaryType":"SC",
          "natureOfWork":"Operation & Maintenance",
          "typeOfWork":"Road",
          "subTypeOfWork":"RD01",
          "entrustmentMode":"e-Procurement",
          "fund":"02",
          "function":"0003",
          "budgetHead":"03",
          "scheme":"AMRUT",
          "subScheme":"AMRUT-01",
          "totalAmount":null,
          "estimateDetails":[{
              "id":"4cbef8e4-aa3c-4c93-a954-a94f04ea8c96",
              "estimateDetailNumber":"EP/2022-23/11/000143/000124",
              "name":"Amrut Yojana",
              "amount":98760,
              "additionalDetails":null
          }],
          "auditDetails":{
              "createdBy":"c8d0093a-4d2b-495f-8bdf-fd9d3594e43f",
              "lastModifiedBy":"c8d0093a-4d2b-495f-8bdf-fd9d3594e43f",
              "createdTime":1667824800916,
              "lastModifiedTime":1667824800916
          },
          "additionalDetails":{
              "owner":"Est Super User",
              "formData":{},
              "createdBy":"Est Super User",
              "filesAttached":[]
          }
      },
      "workflow":{
              "action":"CHECK",
              "comment":"Okay",
              "assignees":["c8d0093a-4d2b-495f-8bdf-fd9d3594e43f"]
      },
      "RequestInfo":{
              "apiId":"Rainmaker",
              "authToken":"153c3161-55ce-4485-96fa-f67ea9757eea",
              "userInfo":{
                  "id":110,
                  "uuid":"c8d0093a-4d2b-495f-8bdf-fd9d3594e43f",
                  "userName":"EST_SUPER",
                  "name":"Est Super User",
                  "mobileNumber":"9876543210",
                  "emailId":"",
                  "locale":null,
                  "type":"EMPLOYEE",
                  "roles":[
                      {
                      "name":"Employee",
                      "code":"EMPLOYEE",
                      "tenantId":"pb.amritsar"
                      },{
                      "name":"EST_CHECKER",
                      "code":"EST_CHECKER",
                      "tenantId":"pb.amritsar"
                      },{
                      "name":"EST TECH SANC",
                      "code":"EST_TECH_SANC",
                      "tenantId":"pb.amritsar"
                      },{
                      "name":"EST FIN SANC",
                      "code":"EST_FIN_SANC",
                      "tenantId":"pb.amritsar"
                      }
                  ],
                  "active":true,
                  "tenantId":"pb.amritsar",
                  "permanentCity":null
              },
          "msgId":"1667833964561|en_IN","plainAccessRequest":{}
      }
      }'

```

_Users must have the respective roles for taking actions on the Estimate, Otherwise the Action Bar will not be visible. And users can only take actions on the applications assigned to them._

#### Response Screen

Upon successful update a response screen is displayed as follows

<figure><img src="../../../../../../../.gitbook/assets/Screenshot from 2022-11-07 20-55-19.png" alt=""><figcaption><p>Estimate Updation Acknowledgement Screen</p></figcaption></figure>

### Role-Action Mapping

<table><thead><tr><th width="216">Role</th><th width="415.3333333333333">Action</th></tr></thead><tbody><tr><td>EST_CHECKER</td><td>CHECK (Check and Forward) / REJECT</td></tr><tr><td>EST_TECH_SANC</td><td>TECHNICALSANCTION (Check and Forward) / REJECT</td></tr><tr><td>EST_ADMIN<em>_</em>SANC</td><td>ADMINSANCTION (Approve) / REJECT</td></tr></tbody></table>
