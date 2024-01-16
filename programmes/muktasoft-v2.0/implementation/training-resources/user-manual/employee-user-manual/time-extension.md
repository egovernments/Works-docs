# Time Extension

The time extension feature enables users to request an extension for the completion period of a project. This request becomes necessary when, for various reasons, the CBO is unable to complete the project within the initially specified time frame. The capability to request a time extension is available to both the CBO and the Officer in-charge of the project.

## Inbox

The same inbox used for managing work orders is also utilized to track and process time extension requests.

**Home Page > Work Orders**

From the Home Page on click of the Work Orders, Inbox Page is displayed.

<figure><img src="../../../../../../.gitbook/assets/image (240).png" alt=""><figcaption></figcaption></figure>

1. On the left side on the top feature menus are displayed.
2. On the left side on the bottom Filters Panel is displayed with the filters.
   1. Assigned to Me - The only work orders assigned to the logged-in user are displayed on the right side window.
   2. Assigned to All - It is default selected and hence the work orders assigned to anyone are displayed on the right side window.
   3. Ward- It filters the application based on the ward selected and then displays the result on the right side window.
   4. Workflow States - It appears only when the application type filter is selected and filters the application based on the application status selected and then displays the result on the right side window.
3. On the right side of the top, search parameters are displayed, which allow you to search the work order by Work Order Number, Project ID, and Project Type.
4. On the right side on the bottom, a window is provided to list the work orders based on default setting and applied filters and search parameters.

## Search Time Extension Request

The search screen for work orders is also utilized to search for time extension requests.

**Home Page > Work Orders> Inbox > Search Work Order**

The search work order enables ULB employees to search for a specific work order using different search parameters.

**Search Criteria**

1. Ward
2. Project Type
3. Project Name
4. Work Order Number/ Time Extension Number
5. Status
6. Created From Date
7. Created To Date

<figure><img src="../../../../../../.gitbook/assets/image (241).png" alt=""><figcaption></figcaption></figure>

1. At Least one parameter is mandatory. Enter anyone for more to search for a work order.
2. The system fetches the work order created between the specified period by entering the date range in created from and created to. From Date and To Date considered as one parameter.
3. Click on the Search button to view the search results.
4. Click on the Reset button to renew the search using different parameters.

**Search Result**

1. Work Order Number/ Time Extension Number
2. Project Name
3. Name of CBO
4. Role of CBO
5. Location
6. Status
7. Amount

<figure><img src="../../../../../../.gitbook/assets/image (242).png" alt=""><figcaption></figcaption></figure>

## View Time Extension Request

To view the details of a time extension request, users can search for the request using the work order search screen and then open it by clicking on the corresponding time extension request ID.

<figure><img src="../../../../../../.gitbook/assets/image (201).png" alt=""><figcaption><p>Time Extension Header</p></figcaption></figure>

<figure><img src="../../../../../../.gitbook/assets/image (202).png" alt=""><figcaption><p>Time Extension Details</p></figcaption></figure>

<figure><img src="../../../../../../.gitbook/assets/image (203).png" alt=""><figcaption><p>Time Extension Workflow</p></figcaption></figure>

## Create Time Extension Request

To initiate a time extension request, users can search for the original work order, view its details, and then, from the actions menu, select 'Create Time Extension.' This action opens the time extension page for users to fill in and submit the request.

<figure><img src="../../../../../../.gitbook/assets/image (204).png" alt=""><figcaption><p>Work Order Details</p></figcaption></figure>

<figure><img src="../../../../../../.gitbook/assets/image (206).png" alt=""><figcaption><p>Create TE Header</p></figcaption></figure>

<figure><img src="../../../../../../.gitbook/assets/image (208).png" alt=""><figcaption><p>Create TE Details</p></figcaption></figure>

## Workflow

### Creator

#### Submit

When a time extension request is created, it is submitted to the next user in the workflow for verification. Upon selecting the 'submit' action, the system provides the user with the option to either choose a specific user as the verifier or submit the request without selecting a verifier.

#### Edit

If a time extension request is sent back to the CBO for correction, the request is placed into the creator's inbox, allowing them to make edits. Simultaneously, the CBO has the ability to edit the request and subsequently re-submit it for verification.

### Verifier

#### Verify and Forward

The 'Verify and Forward' action enables the verifier to forward the time extension request to the approver after completing the verification process and adding the comments if required.

#### Send Back To CBO

The 'Send Back To CBO' action provides the verifier with the capability to send the time extension request back to the CBO for necessary corrections. CBO has the ability to edit the request and subsequently re-submit it for verification.

### Approver

#### Approve

The 'Approve' action grants the approver the authority to approve the time extension request. Upon approval, the changes in the project completion period become effective.

#### Reject

The 'Reject' action empowers the approver to decline the time extension request. Once rejected, no further action can be taken on the request, necessitating the creation of a new request if a time extension is indeed required.

#### Send Back

The 'Send Back To CBO' action permits the approver to send the time extension request back to the previous user in the workflow, typically the CBO, for necessary corrections, request is placed into the creator's inbox, allowing them to make edits. Simultaneously, the CBO has the ability to edit the request and subsequently re-submit it for verification.

#### Send Back To CBO

The 'Send Back To CBO' action enables the approver to return the time extension request to the CBO for necessary corrections. Request is placed into the creator's inbox, allowing them to make edits. Simultaneously, the CBO has the ability to edit the request and subsequently re-submit it for verification.
