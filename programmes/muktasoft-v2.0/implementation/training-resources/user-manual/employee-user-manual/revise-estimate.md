# Revise Estimate

## Revise Estimate <a href="#docs-internal-guid-abe02c1e-7fff-0122-8c3b-ebeb61fc50de" id="docs-internal-guid-abe02c1e-7fff-0122-8c3b-ebeb61fc50de"></a>

Revisions to estimates are common in construction projects, and they can be prompted by various reasons, including changes in rates or deviations in originally estimated quantities.

In both cases, transparency is essential. The revised estimate should clearly outline the reasons for the revision, detailing the changes made to rates or quantities. Additionally, it's important to communicate these revisions to relevant stakeholders and obtain approvals as needed to ensure alignment with project goals and budget constraints.

## Inbox

The same inbox used for managing detailed estimates is also utilized to track and process revised estimates.

**Home Page > Estimates**

To access the estimate inbox, follow these steps:

<mark style="color:red;">**Step 1:**</mark> Navigate to the home page.

<mark style="color:red;">**Step 2:**</mark> Look for and click on the "Estimates" option. This action navigates you to the estimate inbox, where you can manage and view the estimates.

<figure><img src="../../../../../../.gitbook/assets/image (236).png" alt=""><figcaption></figcaption></figure>

![](<../../../../../../.gitbook/assets/1 (9).png>)

<mark style="color:red;">**Step 3:**</mark> Select and apply the filters and search parameters as applicable.&#x20;

* The feature menus are displayed on the top left side.
* The bottom panel displays the filters on the left.
  1. Assigned to Me - The only estimates assigned to the logged-in user are displayed on the right side window.
  2. Assigned to All - It is default selected and hence the estimates assigned to anyone are displayed on the right side window.
  3. Ward- It filters the application based on the ward selected and then displays the result on the right side window.
  4. Workflow States - It appears only when the application type filter is selected. It filters the application based on the application status selected and then displays the result on the right side window.
* The Search parameters are displayed on the top right. Search the estimate by Estimate Number, Project ID, and Project Type.

<mark style="color:red;">**Step 4:**</mark> The window on the bottom right lists the estimates based on the default settings and applied filters and search parameters.

## Create

**Hope Page >> Estimates >> Create Revise Estimate**

To initiate revision of estimate, users can search for the original estimate, view its details, and then, from the actions menu, select 'Create Revise Estimate.' This action opens the revise estimate page for users to fill in and submit.

<figure><img src="../../../../../../.gitbook/assets/image (209).png" alt=""><figcaption><p>Estimate Header Details</p></figcaption></figure>

<figure><img src="../../../../../../.gitbook/assets/image (210).png" alt=""><figcaption><p>Search and Add SOR</p></figcaption></figure>

<figure><img src="../../../../../../.gitbook/assets/image (211).png" alt=""><figcaption><p>Originally Added SOR</p></figcaption></figure>

<figure><img src="../../../../../../.gitbook/assets/image (212).png" alt=""><figcaption><p>Originally Added Non-SOR</p></figcaption></figure>

<figure><img src="../../../../../../.gitbook/assets/image (213).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../../../.gitbook/assets/image (214).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../../../.gitbook/assets/image (215).png" alt=""><figcaption></figcaption></figure>

### Validations

1. An estimate can not be revised is a Work Order is in workflow.
2. An estimate can not be revised if a Time Extension Request is in workflow.
3. An estimate can not be revised if a MB is in workflow.

## Workflow

The workflow of revise estimate is exactly same as detailed estimate. It follows the same roles and actions applicable for detailed estimate. [Please estimate workflow section for more details.](../../../../../../platform/architecture/low-level-design/services/detailed-estimates.md)

## Search

The search screen for estimate is also utilized to search for revised estimates.

**Home Page > Estimates> Search Estimate**

The 'Search Estimate' functionality empowers ULB employees to locate specific estimates with precision by utilizing multiple filters, streamlining the process of retrieving relevant and targeted information.

**Search Criteria**

1. Ward
2. Project Type
3. Project Name
4. Estimate Number/ Revised Estimate Number
5. Status
6. From Date
7. To Date

<figure><img src="../../../../../../.gitbook/assets/image (237).png" alt=""><figcaption></figcaption></figure>

<mark style="color:red;">**Step 1:**</mark> It is mandatory to enter at least one search parameter or more to search for an estimate.

The system fetches the estimates created between the specified period by entering the date range in created from and created to. The From Date and To Date fields are treated as one parameter.

<mark style="color:red;">**Step 2:**</mark> Click on the **Search** button to view the search results.

<mark style="color:red;">**Step 3:**</mark> Click on the **Clear Search** button to renew the search using different parameters.

The Search Result displays the following:

1. Estimate Number/ Revised Estimate Number
2. Project Name
3. Location
4. Prepared by
5. Status
6. Estimated Amount (₹)

<figure><img src="../../../../../../.gitbook/assets/image (238).png" alt=""><figcaption></figcaption></figure>

## View

To view the details of a revised estimate, users can search for the revised estimate using the estimate search screen and then open it by clicking on the corresponding revised estimate ID.

<figure><img src="../../../../../../.gitbook/assets/image (188).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../../../.gitbook/assets/image (189).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../../../.gitbook/assets/image (190).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../../../.gitbook/assets/image (191).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../../../.gitbook/assets/image (192).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../../../.gitbook/assets/image (193).png" alt=""><figcaption></figcaption></figure>

## Revised Estimate PDF

The system facilitates the download of a revised estimate in PDF format from the view details page through the available download option.

## Deviation Statement PDF

The system facilitates the download of a deviation statement in PDF format from the view details page through the available download option.

<figure><img src="../../../../../../.gitbook/assets/image (239).png" alt=""><figcaption></figcaption></figure>
