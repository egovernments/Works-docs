# Create Contract

Create Contract will have link to create contract from view approved estimate sub Estimate table screen.

<figure><img src="../../../../../../.gitbook/assets/image (20) (1).png" alt=""><figcaption><p>View Approved Estimate Screen</p></figcaption></figure>

Clicking on this will open create contract screen.

<figure><img src="../../../../../../.gitbook/assets/image (36) (1).png" alt=""><figcaption><p>Create Contract Screen</p></figcaption></figure>

#### Add create contract fields mdms config

Add the following MDMS config to fetch the values of different dropdown filed of create estimate

```json
MDMS config for Depatment, Designation
{
    tenant,   //pb
    "common-masters",
        [
            {
                "name": "Department"
            },
            {
                "name": "Designation"
            }
        ]
}
```

Once the above details are filled, user needs to forward contract to concerned department and official for checking. Forwarding is considered as part of contract creation.Fill in the details and click “Forward and Approve”.

<figure><img src="../../../../../../.gitbook/assets/Screenshot from 2022-12-06 11-46-54.png" alt=""><figcaption><p>Workflow Modal</p></figcaption></figure>

Once Create Contract API call is successful, an acknowledgement screen is shown.

<figure><img src="../../../../../../.gitbook/assets/image (18) (1).png" alt=""><figcaption><p>Create Contract Acknowledgement Screen</p></figcaption></figure>

#### DropDown Data and Localization

Some of the dropdown data is fetched from mdms and hrms search API

<table><thead><tr><th width="292.3333333333333">PageComponent</th><th>Data Source</th><th>API / MDMS Object</th></tr></thead><tbody><tr><td>Executing Department</td><td>MDMS</td><td><p>{</p><p>tenant, </p><p>"common-masters", </p><p>     [ { "name": "Department" } ]</p><p>}</p></td></tr><tr><td>Designation</td><td>MDMS</td><td><p>{</p><p>tenant, </p><p>"common-masters", </p><p>     [ { "name": "Designation" } ]</p><p>}</p></td></tr><tr><td>Designation of officer in charge</td><td>hrms</td><td>/egov-hrms/employees/_search</td></tr><tr><td>Name of officer in charge</td><td>hrms</td><td>/egov-hrms/employees/_search</td></tr></tbody></table>

Localization keys are added under the ‘_rainmaker-works_’ locale module. In future if any new labels are implemented in works module that should also be pushed in the locale DB under _rainmaker-works_ locale module. Below is the example of few locale labels for hindi and English.

```json
{
    "code":"WORKS_CREATE_CONTRACT",
    "message":"एक अनुबंध बनाएं",
    "module":"rainmaker-works",
    "locale":"hi_IN"
}

{
    "code":"WORKS_CREATE_CONTRACT",
    "message":"Create a Contract",
    "module":"rainmaker-works",
    "locale":"en_IN"
}
```
