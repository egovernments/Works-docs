# Estimate Workflow (Role Action Mapping)

## **Context**

For any project, an estimate is prepared and then sent for the approval process. The approval process contains various workflow levels and states associated with those levels.

## **Scope**

Estimate preparation for a work, by the Estimate Creator and then its verification and approval by other users (actors) in the workflow.

## **Details**

### Role (Actors) - Action Mapping

<table><thead><tr><th width="83">S.No.</th><th width="206">Role (Actors)</th><th width="285">Actions</th><th>User Persona</th></tr></thead><tbody><tr><td>1</td><td>ESTIMATE_CREATOR</td><td><ul><li>Create</li><li>Submit</li><li>Search</li><li>View</li><li>Edit/ Re-submit</li></ul></td><td>Junior Engineer/ Assistant Engineer</td></tr><tr><td>2</td><td>ESTIMATE_VERIFIER</td><td><ul><li>Search</li><li>View</li><li>Verify and Forward</li><li>Send Back</li></ul></td><td>Executive Engineer</td></tr><tr><td>3</td><td>TECHNICAL_SANCTIONER</td><td><ul><li>Search</li><li>View</li><li>Technical Sanction</li><li>Send Back</li><li>Send Back To Originator</li><li>Reject</li></ul></td><td>Municipal Engineer</td></tr><tr><td>4</td><td>ESTIMATE_ APPROVER</td><td><ul><li>Search</li><li>View</li><li>Approve</li><li>Send Back</li><li>Send Back To Originator</li><li>Reject</li></ul></td><td>Executive Officer/ Municipal Commissioner</td></tr><tr><td>5</td><td>ESTIMATE_VIEWER</td><td><ul><li>Search</li><li>View</li></ul></td><td>MUKTA Cordinator</td></tr></tbody></table>

### Workflow States

<table><thead><tr><th width="70">#</th><th>Action</th><th>Role</th><th>From State</th><th>To State</th><th>Status</th></tr></thead><tbody><tr><td>1</td><td>Submit</td><td>Estimate Creator</td><td> </td><td>Pending for verification</td><td>Submitted</td></tr><tr><td>2</td><td>Verify and Forward</td><td>Estimate Verifier</td><td>Pending for verification</td><td>Pending for technical sanction</td><td>Verified</td></tr><tr><td>3</td><td>Technical Sanction</td><td>Technical Sanctioner</td><td>Pending for technical sanction</td><td>Pending for approval</td><td>Technically Sanctioned</td></tr><tr><td>4</td><td>Send Back</td><td>Estimate Verifier</td><td>Pending for verification</td><td>Pending for correction</td><td>Sent Back</td></tr><tr><td>5</td><td>Send Back</td><td>Technical Sanctioner</td><td>Pending for technical sanction</td><td>Pending for verification</td><td>Sent Back</td></tr><tr><td>6</td><td>Send Back</td><td>Estimate Approver</td><td>Pending for approval</td><td>Pending for technical sanction</td><td>Sent Back</td></tr><tr><td>7</td><td>Send Back To Originator</td><td><strong>&#x3C;roles having access></strong></td><td><strong>&#x3C;Current Status></strong></td><td>Pending for correction</td><td>Sent Back</td></tr><tr><td>8</td><td>Edit/ Re-submit</td><td>Estimate Creator</td><td>Pending for correction</td><td>Pending for verification</td><td>Re-submitted</td></tr><tr><td>9</td><td>Approve</td><td>Estimate Approver</td><td>Pending for approval</td><td>Approved</td><td>Approved</td></tr><tr><td>10</td><td>Reject</td><td><strong>&#x3C;any roles having access></strong></td><td><strong>&#x3C;Current Status></strong></td><td>Rejected</td><td>Rejected</td></tr></tbody></table>

## **SLAs**

<table><thead><tr><th width="156">Service Name</th><th width="177">Workflow State/Event</th><th width="285">Current State</th><th>SLA (In Days)</th></tr></thead><tbody><tr><td>Estimate</td><td>Edit/ Re-submit</td><td>Pending for correction</td><td>1</td></tr><tr><td> </td><td>Verify and Forward</td><td>Pending for verification</td><td>2</td></tr><tr><td> </td><td>Technical Sanction</td><td>Pending for technical sanction</td><td>1</td></tr><tr><td> </td><td>Approve</td><td>Pending for approval</td><td>1</td></tr></tbody></table>

## **UI**

[<img src="https://static.figma.com/uploads/b6df2735e4cb368306acf5480b50f96e69f96099" alt="" data-size="line">DIGIT-Works](https://www.figma.com/file/M2P3O9WlKtxuLCjQKxLLDg/DIGIT-Works?node-id=2168%3A32051\&t=v7XALjtyM4MwBoaO-4)

## **Acceptance Criteria**

<table><thead><tr><th width="207">Acceptance Criteria</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Roles are created as given provided.</td></tr><tr><td>2</td><td>Actions are configured based on role-action mapping.</td></tr><tr><td>3</td><td>Workflow states are defined as provided and the state transition is done accordingly by updating the status appropriately.</td></tr></tbody></table>

