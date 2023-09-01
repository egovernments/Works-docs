# Bill Workflow

## **Context**

Bills are created for the work which is in progress and then send for approval process. The approval process contains various workflow levels and states associated with those levels.

## **Action**

Bill is prepared for any work by the Bill Creator (CBO/ JE) and then sent for its verification and approval by the users (actors) in the workflow.

**Wage Bill** - Approved on create.

**Purchase Bill** - Sent for verification on create.

**Supervision Bill** - Approve on create.

#### **Details**

#### Role (Actors) - Action Mapping

<table><thead><tr><th width="99">#</th><th width="174">Role</th><th width="228">Action</th><th>User Persona</th></tr></thead><tbody><tr><td>1</td><td>BILL CREATOR</td><td><ul><li>Create</li><li>Search</li><li>View</li><li>Edit</li><li>Submit/ Re-submit</li></ul></td><td>Junior Engineer</td></tr><tr><td>2</td><td>BILL VERIFIER</td><td><ul><li>Search</li><li>View</li><li>Edit</li><li>Verify and Forward</li><li>Send Back</li></ul></td><td>Municipal Engineer</td></tr><tr><td>3</td><td>BILL APPROVER</td><td><ul><li>Search</li><li>View</li><li>Approve</li><li>Send Back</li><li>Send Back To Originator</li><li>Reject</li></ul></td><td>Executive Officer/ Municipal Commissioner</td></tr></tbody></table>

#### Workflow States - Applicable to all 3 types of bills

<table><thead><tr><th width="83">#</th><th>Action</th><th>Role</th><th>From State</th><th>To State</th><th>Status</th></tr></thead><tbody><tr><td>1</td><td>Submit</td><td>Bill Creator</td><td> </td><td>Pending for verification</td><td>Submitted</td></tr><tr><td>2</td><td>Verify and Forward</td><td>Bill Verifier</td><td>Pending for verification</td><td>Pending for approval</td><td>Verified</td></tr><tr><td>3</td><td>Send Back</td><td>Bill Verifier</td><td>Pending for verification</td><td>Pending for correction</td><td>Sent Back</td></tr><tr><td>4</td><td>Send Back</td><td>Bill Approver</td><td>Pending for approval</td><td>Pending for verification</td><td>Send Back</td></tr><tr><td>5</td><td>Send Back To Originator</td><td><strong>&#x3C;roles having access></strong></td><td><strong>&#x3C;Current Status></strong></td><td>Pending for correction</td><td>Sent Back</td></tr><tr><td>6</td><td>Re-submit</td><td>Bill Creator</td><td>Pending for correction</td><td>Pending for verification</td><td>Re-submitted</td></tr><tr><td>7</td><td>Approve</td><td>Bill Approver</td><td>Pending for approval</td><td>Approved</td><td>Approved</td></tr><tr><td>8</td><td>Reject</td><td><strong>&#x3C;roles having access></strong></td><td><strong>&#x3C;Current Status></strong></td><td>Rejected</td><td>Rejected</td></tr></tbody></table>

## **User Interface**

The workflow UI component is the same as given for estimate. The only difference is the status update that is displayed as per the details given in the above table.

## **Acceptance Criteria**

<table><thead><tr><th width="184">Acceptance Criteria</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Actions are configured based on role-action mapping.</td></tr><tr><td>2</td><td>Workflow states are defined as provided and the state transition is done accordingly.</td></tr></tbody></table>
