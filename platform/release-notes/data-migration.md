# Data Migration

## CBO Migration

Migration is required in individuals and attendance data if worksv0.1 is already deployed.

{% hint style="info" %}
This migration is Mukta-specific, it will not be part of our master code.
{% endhint %}

## &#x20;Migration Steps

1. Use [this](https://github.com/egovernments/DIGIT-Works/tree/PFM-4439-UserMigrationToIndividual) specific branch of the organization service, which includes the mentioned changes.  Follow the [links here](https://github.com/egovernments/DIGIT-Works/pull/1324/files) to access the branch and change details.
2. Build and deploy this service in your environment.
3.  User this curl to migrate the data

    ```json
    curl --location --request POST 'http://localhost:8035/org-services/organisation/v1/_migrate' \
    --header 'authority: works-qa.digit.org' \
    --header 'accept: application/json, text/plain, */*' \
    --header 'accept-language: en-US,en;q=0.9' \
    --header 'content-type: application/json' \
    --header 'cookie: intercom-id-xp1951jv=72181a5e-32d1-4d97-8e85-5e9574ee7ede; intercom-device-id-xp1951jv=9586a950-3d1e-4818-bae2-c9673e615146; _ga=GA1.1.1354941045.1656251739; _ga_H9YC8FEN6F=GS1.1.1684744433.6.1.1684744462.31.0.0; amp_fef1e8=7b52e48b-c09e-406a-aedb-0c7c474c5f69R...1h119fs43.1h11aomp6.95.18.ad; _ga_XBQP06FR8V=GS1.1.1684745770.1.0.1684745773.0.0.0; __cuid=626a55cb986f4721b4761ce8d267d319' \
    --header 'dnt: 1' \
    --header 'origin: https://works-qa.digit.org' \
    --header 'referer: https://works-qa.digit.org/works-ui/employee/masters/create-organization' \
    --header 'sec-ch-ua: "Google Chrome";v="113", "Chromium";v="113", "Not-A.Brand";v="24"' \
    --header 'sec-ch-ua-mobile: ?0' \
    --header 'sec-ch-ua-platform: "macOS"' \
    --header 'sec-fetch-dest: empty' \
    --header 'sec-fetch-mode: cors' \
    --header 'sec-fetch-site: same-origin' \
    --header 'user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/113.0.0.0 Safari/537.36' \
    --data-raw '{
        "RequestInfo": {
            "apiId": "Rainmaker",
            "authToken": "aba4853b-3aba-4eca-bd46-5e5e25322fd2",
            "userInfo": {
                "id": 420,
                "uuid": "7054704f-e713-42ed-a237-cdc5cfc345e3",
                "userName": "Master user",
                "name": "Vasanth",
                "mobileNumber": "9962597391",
                "emailId": null,
                "locale": null,
                "type": "EMPLOYEE",
                "roles": [
                    {
                        "name": "MUKTA Admin",
                        "code": "MUKTA_ADMIN",
                        "tenantId": "pg.citya"
                    }
                ],
                "active": true,
                "tenantId": "pg.citya",
                "permanentCity": null
            },
            "msgId": "1685054419235|en_IN",
            "plainAccessRequest": {}
        }
    }'
    ```
4.  Run the below queries manually if the phone number is changed for the existing organisation.

    ```sql
    // GET organisations for which mobile number is changed
    select id, mobilenumber from individual where id in ( select id from eg_org_contact_detail where individual_id is null and tenant_id='od.testing');
    // Find those user details for each by encrypted mobile number
    select id, uuid, username from eg_user where mobilenumber='encMobileNumber';
    // Update that individual with correct values
    update individual set userid='userid', useruuid='userUuid', issystemuseractive=true, username='decMobileNumber', type='CITIZEN', roles='[{"code": "ORG_ADMIN", "name":"Organization admin", "tenantId": null, "description": null}]' WHERE id='individualId';
    // restore the contact details with older mobile number
    update eg_org_contact_detail set contact_mobile_number='decMobileNumber' , individual_id='individualId' where id='individualId';
    // Get attendence staff detils with older details
    select * from eg_wms_attendance_staff where individual_id='userUuid';
    // if attendence staff details are there then update according to new attendance service
    UPDATE eg_wms_attendance_staff set individual_id='individualId' where individual_id='userUuid';
    ```
