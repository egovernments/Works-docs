# Data Migration

## Organisation Service

Organisation Service: Implemented encryption on Organisation user details

{% hint style="info" %}
Note: Before migration make sure your elastic index is not read-only.
{% endhint %}

Build for migration: organisation-db:PFM-4468\_Organisation\_Encryption\_Migration-7903f8ed-104

Run the following query:\
CREATE TABLE IF NOT EXISTS encryption\_migration(uuid VARCHAR(100), is\_migrated boolean);

## &#x20;Migration Steps

To migrate data follow the steps given below:

1. **Use the Specific Branch**:
   * Access the [branch of the organization service](https://github.com/egovernments/DIGIT-Works/tree/7903f8edd7c3e4572b676efee0f09b7fc9474324/backend/organisation) with the mentioned changes.&#x20;
   * [Click here](https://github.com/egovernments/DIGIT-Works/tree/PFM-4468\_Organisation\_Encryption\_Migration/backend/organisation) to access the branch and change details.
2. **Build and Deploy the Service**:
   * Clone or download the code from the specific branch.
   * Run the following query:\
     CREATE TABLE IF NOT EXISTS encryption\_migration(uuid VARCHAR(100), is\_migrated boolean);
   * Use the curl below to migrate the data.
3. ```json
   curl --location 'http://localhost:8035/org-services/organisation/v1/_migrate' \
   --header 'authority: works-uat.digit.org' \
   --header 'accept: application/json, text/plain, */*' \
   --header 'accept-language: en-US,en;q=0.9' \
   --header 'content-type: application/json' \
   --header 'cookie: intercom-id-xp1951jv=72181a5e-32d1-4d97-8e85-5e9574ee7ede; intercom-device-id-xp1951jv=9586a950-3d1e-4818-bae2-c9673e615146; _ga=GA1.1.1354941045.1656251739; _ga_H9YC8FEN6F=GS1.1.1684744433.6.1.1684744462.31.0.0; amp_fef1e8=7b52e48b-c09e-406a-aedb-0c7c474c5f69R...1h119fs43.1h11aomp6.95.18.ad; _ga_XBQP06FR8V=GS1.1.1684745770.1.0.1684745773.0.0.0; __cuid=626a55cb986f4721b4761ce8d267d319' \
   --header 'dnt: 1' \
   --header 'origin: https://works-uat.digit.org' \
   --header 'referer: https://works-uat.digit.org/works-ui/employee/masters/view-organization?tenantId=statea.cityone&orgId=ORG-000071' \
   --header 'sec-ch-ua: "Google Chrome";v="113", "Chromium";v="113", "Not-A.Brand";v="24"' \
   --header 'sec-ch-ua-mobile: ?0' \
   --header 'sec-ch-ua-platform: "macOS"' \
   --header 'sec-fetch-dest: empty' \
   --header 'sec-fetch-mode: cors' \
   --header 'sec-fetch-site: same-origin' \
   --header 'user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/113.0.0.0 Safari/537.36' \
   --data '{
       "RequestInfo": {
           "apiId": "Rainmaker",
           "authToken": "c60cda91-a143-4311-9c76-6ff91926c23d",
           "userInfo": {
               "id": 922,
               "uuid": "45614d29-9a50-4970-aba5-81b380745f48",
               "userName": "ANSH-001",
               "name": "Ansh",
               "mobileNumber": "9876543210",
               "emailId": null,
               "type": "EMPLOYEE",
               "roles": [
                   {
                       "name": "HRMS Admin",
                       "code": "HRMS_ADMIN",
                       "tenantId": "pg.citya"
                   },
                   {
                       "name": "WORK ORDER CREATOR",
                       "code": "WORK_ORDER_CREATOR",
                       "tenantId": "pg.citya"
                   },
                   {
                       "name": "ESTIMATE VERIFIER",
                       "code": "ESTIMATE_VERIFIER",
                       "tenantId": "pg.citya"
                   },
                   {
                       "name": "ESTIMATE APPROVER",
                       "code": "ESTIMATE_APPROVER",
                       "tenantId": "pg.citya"
                   },
                   {
                       "name": "MB_VERIFIER",
                       "code": "MB_VERIFIER",
                       "tenantId": "pg.citya"
                   },
                   {
                       "name": "WORK ORDER VERIFIER",
                       "code": "WORK_ORDER_VERIFIER",
                       "tenantId": "pg.citya"
                   },
                   {
                       "name": "PROJECT VIEWER",
                       "code": "PROJECT_VIEWER",
                       "tenantId": "pg.citya"
                   },
                   {
                       "name": "MB_CREATOR",
                       "code": "MB_CREATOR",
                       "tenantId": "pg.citya"
                   },
                   {
                       "name": "MUSTER ROLL VERIFIER",
                       "code": "MUSTER_ROLL_VERIFIER",
                       "tenantId": "pg.citya"
                   },
                   {
                       "name": "OFFICER IN CHARGE",
                       "code": "OFFICER_IN_CHARGE",
                       "tenantId": "pg.citya"
                   },
                   {
                       "name": "PROJECT CREATOR",
                       "code": "PROJECT_CREATOR",
                       "tenantId": "pg.citya"
                   },
                   {
                       "name": "Employee Common",
                       "code": "EMPLOYEE_COMMON",
                       "tenantId": "pg.citya"
                   },
                   {
                       "name": "BILL_VIEWER",
                       "code": "BILL_VIEWER",
                       "tenantId": "pg.citya"
                   },
                   {
                       "name": "TECHNICAL SANCTIONER",
                       "code": "TECHNICAL_SANCTIONER",
                       "tenantId": "pg.citya"
                   },
                   {
                       "name": "BILL_CREATOR",
                       "code": "BILL_CREATOR",
                       "tenantId": "pg.citya"
                   },
                   {
                       "name": "MUSTER ROLL APPROVER",
                       "code": "MUSTER_ROLL_APPROVER",
                       "tenantId": "pg.citya"
                   },
                   {
                       "name": "ESTIMATE VIEWER",
                       "code": "ESTIMATE_VIEWER",
                       "tenantId": "pg.citya"
                   },
                   {
                       "name": "WORK ORDER APPROVER",
                       "code": "WORK_ORDER_APPROVER",
                       "tenantId": "pg.citya"
                   },
                   {
                       "name": "MB_APPROVER",
                       "code": "MB_APPROVER",
                       "tenantId": "pg.citya"
                   },
                   {
                       "name": "ESTIMATE CREATOR",
                       "code": "ESTIMATE_CREATOR",
                       "tenantId": "pg.citya"
                   },
                   {
                       "name": "MB_VIEWER",
                       "code": "MB_VIEWER",
                       "tenantId": "pg.citya"
                   },
                   {
                       "name": "MUKTA Admin",
                       "code": "MUKTA_ADMIN",
                       "tenantId": "pg.citya"
                   }
               ],
               "tenantId": "pg.citya"
           },
           "msgId": "1687176345894|en_IN",
           "plainAccessRequest": {}
       }
   }'
   ```

## Contracts migration

```
// For first contract
UPDATE eg_wms_contract_line_items
SET contract_line_item_ref = eg_wms_contract_line_items.id
FROM eg_wms_contract
WHERE eg_wms_contract_line_items.contract_id = eg_wms_contract.id
      AND (eg_wms_contract.business_service IS NULL OR eg_wms_contract.business_service = 'CONTRACT');

// For revised contracts
UPDATE eg_wms_contract_line_items AS t1
SET contract_line_item_ref = (
    SELECT contract_line_item_ref
    FROM eg_wms_contract_line_items AS t2
    WHERE t2.estimate_id = t1.estimate_id
      AND t2.estimate_line_item_id = t1.estimate_line_item_id
      AND t2.contract_line_item_ref IS NOT NULL
    LIMIT 1
)
WHERE t1.contract_line_item_ref IS NULL;

UPDATE eg_wms_contract SET version_number=version_number+1 WHERE business_service='CONTRACT-REVISION';

UPDATE eg_wms_contract SET business_service='CONTRACT' WHERE business_service is null;

UPDATE eg_wms_contract SET version_number=1 WHERE business_service ='CONTRACT';
```
