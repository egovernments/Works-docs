# Measurement Book

The Measurement Book holds paramount significance as a record, serving as the foundation for all accounts related to the quantities of work completed and purchases made. It is imperative that this record is comprehensive, containing detailed and factual information to serve as conclusive evidence in a court of law.

This record acts as the cornerstone for accounting the quantities, encompassing the work executed by contractors, laborers employed departmentally, and materials received. The meticulous documentation ensures that all transactions are easily traceable, contributing to the transparency and accuracy of the overall accounting process.

The completion of an item is determined by the exhaustion of the total quantity specified in the estimate within the Measurement Book. Once the entire quantity of a specific item mentioned in the estimate is consumed and recorded in the MB, that particular item is considered completed. This systematic approach ensures accurate tracking and verification of the completion status of each item in the construction project.

## Inbox

The Measurement Book (MB) inbox, dedicated to managing MB, is also utilized for tracking and processing the workflow related to Measurement Books.

**Home Page > Measurement Books**

To access the measurement book inbox, follow these steps:

<mark style="color:red;">**Step 1:**</mark> Navigate to the home page.

<mark style="color:red;">**Step 2:**</mark> Look for and click on the "Measurement Books" option. This action navigates you to the measurement books inbox, where you can manage and view the measurement books.

<figure><img src="../../../../../../.gitbook/assets/image (243).png" alt=""><figcaption></figcaption></figure>

<mark style="color:red;">**Step 3:**</mark> Select and apply the filters and search parameters as applicable.&#x20;

* The feature menus are displayed on the top left side.
* The bottom panel displays the filters on the left.
  1. Assigned to Me - The panel on the right side displays the estimates assigned to the logged-in user.
  2. Assigned to All - This option is selected by default and displays all the estimates along with the assignee names.
  3. Ward- This filters and displays the applications based on the selected ward on the right side window.
  4. Workflow States - This option is displayed only when the application type filter is selected. It filters and displays the applications based on the selected application status on the right side window.
* The search parameters are displayed on the top right. Search the measurement book by Measurement Book Number, Project ID, and Project Type.

<mark style="color:red;">**Step 4:**</mark> The window on the bottom right lists the measurement books based on the default settings, applied filters and search parameters.

## Create Measurement Book

The system enables users to capture measurements of completed work items, whether they are part of the Schedule of Rates (SOR) or Non-SOR items. This recorded information is crucial and becomes the foundation for payment processes involving wage seekers, suppliers, and supervisors (CBOs).

**Home Page > Measurement Books > Create MB**

1. It will open the search work order screen to search a WO to create a MB.

<figure><img src="../../../../../../.gitbook/assets/image (253).png" alt=""><figcaption></figcaption></figure>

2. Click on WO number to open the WO to see the details and from action menu select create MB.

<figure><img src="../../../../../../.gitbook/assets/image (254).png" alt=""><figcaption></figcaption></figure>

3. It will take the use to the create MB screen as given below.

<figure><img src="../../../../../../.gitbook/assets/image (174).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../../../.gitbook/assets/image (175).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../../../.gitbook/assets/image (176).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../../../.gitbook/assets/image (255).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../../../.gitbook/assets/image (223).png" alt=""><figcaption></figcaption></figure>

### Validations

Measurement books cannot be created if the estimate's revision status is in the workflow for a given project.

## Search Measurement Book

The "Search MB" functionality allows users to search for a specific Measurement Book (MB) created for a particular period. Upon locating the relevant MB, users can open it to view comprehensive details and take the necessary actions based on the information contained within the record.

<figure><img src="../../../../../../.gitbook/assets/image (167).png" alt=""><figcaption></figcaption></figure>

## View Measurement Book

The "View MB" feature empowers users to access and review the details as well as the workflow status of a Measurement Book (MB).

<figure><img src="../../../../../../.gitbook/assets/image (244).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../../../.gitbook/assets/image (245).png" alt=""><figcaption></figcaption></figure>

MB Hist

<figure><img src="../../../../../../.gitbook/assets/image (246).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../../../.gitbook/assets/image (247).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../../../.gitbook/assets/image (248).png" alt=""><figcaption></figcaption></figure>



<figure><img src="../../../../../../.gitbook/assets/image (250).png" alt=""><figcaption></figcaption></figure>

## Workflow

The workflow of the Measurement Book (MB) comprises three key roles: the creator, verifier, and approver. Each role is associated with specific actions that contribute to the overall processing and approval of the MB. The workflow typically involves a sequence of actions performed by these roles to ensure accurate documentation, verification, and approval of measurements within the MB.

### Creator

#### Save as Draft

The "Save as Draft" feature provides users with the capability to create a Measurement Book (MB) and retain it in the creator's inbox for subsequent updates. This functionality allows users to initiate the MB creation process, save the work in progress as a draft, and revisit it later for additional edits or finalization before submission.

#### Submit

When a MB is created, it is submitted to the next user in the workflow for verification. Upon selecting the 'submit' action, the system provides the user with the option to either choose a specific user as the verifier or submit it without selecting a verifier.

#### Edit

If a MB is sent back to the creator for correction, MB is placed into the creator's inbox, allowing them to make edits and subsequently re-submit it for verification.

### Verifier

#### Verify and Forward

The 'Verify and Forward' action enables the verifier to forward MB to the approver after completing the verification process and adding the comments if required.

#### Send Back

The 'Send Back' action provides the verifier with the capability to send the MB back to the creator for necessary corrections.

### Approver

#### Approve

The 'Approve' action bestows upon the approver the authority to approve the Measurement Book (MB). Upon approval, the MB attains an immutable status, meaning that it becomes unalterable or resistant to further changes. This step typically signifies the finalization and confirmation of the recorded measurements and associated details within the MB.

#### Reject

The 'Reject' action empowers the approver to decline the MB. Once rejected, no further action can be taken on the MB, necessitating the creation of a new MB.

#### Send Back

The 'Send Back' action permits the approver to send the MB back to the previous user in the workflow for necessary corrections, MB is placed into the verifier's inbox, allowing them to take necessary action.

#### Send Back To Originator

The 'Send Back To Originator' action enables the approver to return the MB to the creator for necessary corrections. Request is placed into the creator's inbox, allowing them to make edits and subsequently re-submit it for verification.

## Validations

The amounts in Muster Roll and Purchase Bill are validated against the corresponding utilization amount in the Measurement Book (MB).

### Muster Roll

The approval of the muster roll is restricted if a Measurement Book (MB) for the same period is either missing or pending approval. Additionally, if the labor utilization amount does not match the muster roll wage amount, the approver of muster roll is presented with an alert message.

### Purchase Bill

The creation of the purchase bill is restricted if no Measurement Book (MB) has been created and approved. Furthermore, if the material/machinery utilization amount does not match the muster roll wage amount, the creator is alerted with an alert message.

## Measurement Book PDF

The system facilitates the download of a abstract measurement in PDF format from the view details page through the available download option.

