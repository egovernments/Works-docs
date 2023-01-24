---
description: Create an Estimate Proposal
---

# Create Estimate

### Add Module MDMS (Master Data Management Service) Configuration

When creating a works module, the module needs to be enabled in `citymodule.json.`Add the Following details in [citymodule.json](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pb/tenant/citymodule.json)

```json
{
    "tenantId": "pb",
    "moduleName": "tenant",
    "citymodule": [
        {
            "module": "Works",
            "code": "Works",
            "active": true,
            "order": 1,
            "tenants": [
                {
                    "code": "pb.jalandhar"
                },
                {
                    "code": "pb.nawanshahr"
                },
                {
                    "code": "pb.amritsar"
                }
            ]
        }
}
```

Estimate Creator will have link to create estimate from estimate inbox screen.

<figure><img src="../../../../.gitbook/assets/Screenshot from 2022-11-07 17-20-16.png" alt=""><figcaption><p>Estimate Proposal Inbox</p></figcaption></figure>

Clicking on this will open create estimate screen.

#### Add create Estimate mdms config&#x20;

Add the following MDMS config to fetch the values of different dropdown filed of create estimate

```json
MDMS config for Depatment
{
    tenant,   //pb
    "common-masters",
        [
            {
                "name": "Department"
            }
        ]
}

MDMS config for Beneficiary Type, Entrustment Mode, Nature Of Work, Type Of Work
{
     tenant,    //pb
        "works",
        [
            {
                "name": "BeneficiaryType"
            },
            {
                "name": "EntrustmentMode"
            },
            {
                "name": "NatureOfWork"
            },
            {
                "name": "TypeOfWork"
            },
        ]
}

MDMS config for Scheme, Budget Head, Functions, Fund
{
    tenant,
        "finance",
        [
            {
                "name": "Scheme"
            },
            {
                "name": "BudgetHead"
            },
            {
                "name": "Functions"
            },
            {
                "name": "Fund"
            }
        ]
}

MDMS config for location
{
    tenantId,  //pb.amritsar || pb.jalandhar etc.
        "egov-location",
        [
            {
                "name": "TenantBoundary"
            },
        ]
}
```

<figure><img src="../../../../.gitbook/assets/image (32).png" alt=""><figcaption><p>Create Estimate Form</p></figcaption></figure>

Once the above details are filled, user needs to forward estimate to concerned department and official for checking. Forwarding is considered as part of estimate creation.Fill in the details and click “Forward Estimate”.

<figure><img src="../../../../.gitbook/assets/Screenshot from 2022-11-07 17-50-38.png" alt="Processing Modal"><figcaption><p>Workflow Modal</p></figcaption></figure>

Each Work detail will be referred to as Sub-Estimate & sub Estimate will back track to all details of Estimate as-is. At least 1 Sub-Estimate has to be created to create an Estimate. Sum of All Amounts of Sub-Estimates is the Estimate Amount.

Once Create Estimate API call is successful, an acknowledgement screen is shown.

<figure><img src="../../../../.gitbook/assets/Screenshot from 2022-11-07 18-10-18.png" alt=""><figcaption><p>Create Estimate Acknowledgement Screen</p></figcaption></figure>

**API Call Roll action-mapping**

| API                                    | Action Id | Roles        |
| -------------------------------------- | --------- | ------------ |
| /estimate-service/estimate/v1/\_create | 9         | EST\_CREATOR |

#### Sample Curl for Create API

```json
jcurl 'https://works-dev.digit.org/estimate-service/estimate/v1/_create' \
  -H 'authority: works-dev.digit.org' \
  -H 'accept: application/json, text/plain, */*' \
  -H 'accept-language: en-US,en;q=0.9' \
  -H 'content-type: application/json;charset=UTF-8' \
  -H 'origin: https://works-dev.digit.org' \
  -H 'referer: https://works-dev.digit.org/works-ui/employee/works/create-estimate' \
  -H 'sec-ch-ua: "Google Chrome";v="107", "Chromium";v="107", "Not=A?Brand";v="24"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "Linux"' \
  -H 'sec-fetch-dest: empty' \
  -H 'sec-fetch-mode: cors' \
  -H 'sec-fetch-site: same-origin' \
  -H 'user-agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/107.0.0.0 Safari/537.36' \
  --data-raw '{
        "estimate": {
            "tenantId":"pb.amritsar",
            "status":"ACTIVE",
            "estimateStatus":"ACTIVE",
            "subject":"Construct new schools",
            "requirementNumber":"78960",
            "description":"Construct new schools",
            "department":"DEPT_3",
            "location":"pb.amritsar:ADMIN:pb.amritsar:Z1:B3:SUN08",
            "workCategory":"Engineering",
            "beneficiaryType":"Minority",
            "natureOfWork":"Operation & Maintenance",
            "typeOfWork":"Road",
            "subTypeOfWork":"RD02",
            "entrustmentMode":"Nomination",
            "fund":"01",
            "function":"0006",
            "budgetHead":"02",
            "scheme":"AMRUT",
            "subScheme":"AMRUT-01",
            "estimateDetails":[{
                "name":"Amrut Yojana",
                "amount":"90876"
            }],
            "additionalDetails":{
            "formData":{},
            "createdBy":"Est Super User",
            "owner":"Est Super User",
            },
        "workflow":{
            "action":"CREATE",
            "comment":"",
            "assignees":["88bd1b70-dd6d-45f7-bcf7-5aa7a6fae7d9"]
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
                "roles":[{
                    "name":"Employee",
                    "code":"EMPLOYEE",
                    "tenantId":"pb.amritsar"
                    },{
                    "name":"EST CREATOR",
                    "code":"EST_CREATOR",
                    "tenantId":"pb.amritsar"
                }],
                "active":true,
                "tenantId":"pb.amritsar",
                "permanentCity":null
            },
        "msgId":"1667826119526|en_IN",
        "plainAccessRequest":{}
        }
    }'
```

#### DropDown Data and Localization

Some of the dropdown data is fetched from mdms and hrms search API

| PageComponent                                | Data Source | API                                                                                                                                                                                                                      |
| -------------------------------------------- | ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Executing Department                         | mdms        | <p>{</p><p>tenant, </p><p>"common-masters", </p><p>     [ { "name": "Department" } ]</p><p>}</p>                                                                                                                         |
| Ward, Location                               | mdms        | <p>{</p><p>"pb.amritsar", </p><p>"egov-location", </p><p>     [ { "name": "TenantBoundary" }]</p><p>}</p>                                                                                                                |
| Beneficiary, Nature of Work, Type of Work    | mdms        | <p>{</p><p>"pb, </p><p>"works", </p><p>     [ { "name": "BeneficiaryType" },</p><p>       { "name": "EntrustmentMode" }, </p><p>       { "name": "NatureOfWork" }, </p><p>       { "name": "TypeOfWork" }, ]</p><p>}</p> |
| Fund, Function, Budget Head,Scheme, subSchem | mdms        | <p>{</p><p>"pb", </p><p>"finance", </p><p>       [ { "name": "BudgetHead" },</p><p>          { "name": "Functions" }, </p><p>          { "name": "Fund" },</p><p>          { "name": "Scheme"} ] </p><p>}</p>            |
| Designation of officer in charge             | hrms        | /egov-hrms/employees/\_search                                                                                                                                                                                            |
| Name of officer in charge                    | hrms        | /egov-hrms/employees/\_search                                                                                                                                                                                            |

Localization keys are added under the ‘_rainmaker-works_’ locale module. In future if any new labels are implemented in works module that should also be pushed in the locale DB under _rainmaker-works_ locale module. Below is the example of few locale labels for hindi and English.

```json
{
    "code":"ACTION_TEST_CREATE_ESTIMATE",
    "message":"अनुमान बनाएँ",
    "module":"rainmaker-works",
    "locale":"hi_IN"
}

{
    "code":"ACTION_TEST_CREATE_ESTIMATE",
    "message":"Create Estimate",
    "module":"rainmaker-works",
    "locale":"en_IN"
}
```

#### Roles - Action

| Role                              | Actions                                      |
| --------------------------------- | -------------------------------------------- |
| Creator (EST\_CREATOR)            | Create/Edit(Rejected) Estimate and Forawrded |
| Checket1 (EST\_CHECKER)           | Checked Estimate and Forwarded               |
| Checker2 (EST\_TECH\_SANC)        | Checked Estimate and Forwarded               |
| Admin Approver (EST\_ADMIN\_SANC) | Approved Estimate                            |
