# Detailed Measurement Book

The Measurement Book holds paramount significance as a record, serving as the foundation for all accounts related to the quantities of work completed and purchases made. It is imperative that this record is comprehensive, containing detailed and factual information to serve as conclusive evidence in a court of law.

This record acts as the cornerstone for accounting the quantities, encompassing the work executed by contractors, laborers employed departmentally, and materials received. The meticulous documentation ensures that all transactions are easily traceable, contributing to the transparency and accuracy of the overall accounting process.

The completion of an item is determined by the exhaustion of the total quantity specified in the estimate within the Measurement Book. Once the entire quantity of a specific item mentioned in the estimate is consumed and recorded in the MB, that particular item is considered completed. This systematic approach ensures accurate tracking and verification of the completion status of each item in the construction project.

## Inbox

The Measurement Book (MB) inbox, dedicated to managing MB, is also utilized for tracking and processing the workflow related to Measurement Books.

<figure><img src="../../../../../../.gitbook/assets/image (172).png" alt=""><figcaption><p>MB Inbox</p></figcaption></figure>

## Create Measurement Book

The system enables users to capture measurements of completed work items, whether they are part of the Schedule of Rates (SOR) or Non-SOR items. This recorded information serves as a crucial record and becomes the foundation for payment processes involving wage seekers, suppliers, and supervisors (CBOs).

<figure><img src="../../../../../../.gitbook/assets/image (174).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../../../.gitbook/assets/image (175).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../../../.gitbook/assets/image (176).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../../../.gitbook/assets/image (177).png" alt=""><figcaption></figcaption></figure>

## Search Measurement Book

The "Search MB" functionality allows users to search for a specific Measurement Book (MB) created for a particular period. Upon locating the relevant MB, users can open it to view comprehensive details and take the necessary actions based on the information contained within the record.

<figure><img src="../../../../../../.gitbook/assets/image (167).png" alt=""><figcaption></figcaption></figure>

## View Measurement Book

The "View MB" feature empowers users to access and review the details as well as the workflow status of a Measurement Book (MB).

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

