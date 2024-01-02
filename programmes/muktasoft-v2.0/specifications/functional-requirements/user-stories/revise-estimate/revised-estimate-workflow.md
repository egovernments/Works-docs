# Revised Estimate Workflow

## Details

### Role (Actors) - Action Mapping <a href="#role-28actors-29actionmapping" id="role-28actors-29actionmapping"></a>

<table data-header-hidden><thead><tr><th width="64"></th><th width="245"></th><th></th><th></th></tr></thead><tbody><tr><td>#</td><td>Role (Actors)</td><td>Actions</td><td>User Persona</td></tr><tr><td>1</td><td>ESTIMATE_CREATOR</td><td><ul><li>Create</li><li>Submit</li><li>Search</li><li>View</li><li>Edit/ Re-submit</li></ul></td><td>Junior Engineer/ Assistant Engineer/ Implementation Expert</td></tr><tr><td>2</td><td>ESTIMATE_VERIFIER</td><td><ul><li>Search</li><li>View</li><li>Verify and Forward</li><li>Send Back</li></ul></td><td>Executive Engineer</td></tr><tr><td>3</td><td>TECHNICAL_SANCTIONER</td><td><ul><li>Search</li><li>View</li><li>Technical Sanction</li><li>Send Back</li><li>Send Back To Originator</li><li>Reject</li></ul></td><td>Municipal Engineer</td></tr><tr><td>4</td><td>ESTIMATE_ APPROVER</td><td><ul><li>Search</li><li>View</li><li>Approve</li><li>Send Back</li><li>Send Back To Originator</li><li>Reject</li></ul></td><td>Executive Officer/ Municipal Commissioner</td></tr><tr><td>5</td><td>ESTIMATE_VIEWER</td><td><ul><li>Search</li><li>View</li></ul></td><td>Program Coordinator</td></tr></tbody></table>

### Workflow States <a href="#workflowstates" id="workflowstates"></a>

<table data-header-hidden><thead><tr><th width="68"></th><th></th><th></th><th></th><th></th><th></th></tr></thead><tbody><tr><td>#</td><td>Action</td><td>Role</td><td>From State</td><td>To State</td><td>Status</td></tr><tr><td>1 </td><td>Save as Draft</td><td> </td><td> </td><td>Drafted</td><td>Drafted</td></tr><tr><td>2</td><td>Submit</td><td>Estimate Creator</td><td>Drafted</td><td>Pending for verification</td><td>Submitted</td></tr><tr><td>3</td><td>Verify and Forward</td><td>Estimate Verifier</td><td>Pending for verification</td><td>Pending for technical sanction</td><td>Verified</td></tr><tr><td>4</td><td>Technical Sanction</td><td>Technical Sanctioner</td><td>Pending for technical sanction</td><td>Pending for approval</td><td>Technically Sanctioned</td></tr><tr><td>5</td><td>Send Back</td><td>Estimate Verifier</td><td>Pending for verification</td><td>Pending for correction</td><td>Sent Back</td></tr><tr><td>6</td><td>Send Back</td><td>Technical Sanctioner</td><td>Pending for technical sanction</td><td>Pending for verification</td><td>Sent Back</td></tr><tr><td>7</td><td>Send Back</td><td>Estimate Approver</td><td>Pending for approval</td><td>Pending for technical sanction</td><td>Sent Back</td></tr><tr><td>8</td><td>Send Back To Originator</td><td>&#x3C;roles having access></td><td>&#x3C;Current Status></td><td>Pending for correction</td><td>Sent Back</td></tr><tr><td>9</td><td>Edit/ Re-submit</td><td>Estimate Creator</td><td>Pending for correction</td><td>Pending for verification</td><td>Re-submitted</td></tr><tr><td>10</td><td>Approve</td><td>Estimate Approver</td><td>Pending for approval</td><td>Approved</td><td>Approved</td></tr><tr><td>11</td><td>Reject</td><td>&#x3C;any roles having access></td><td>&#x3C;Current Status></td><td>Rejected</td><td>Rejected</td></tr></tbody></table>

## SLAs <a href="#slas" id="slas"></a>

<table data-header-hidden><thead><tr><th width="245"></th><th width="335"></th><th></th></tr></thead><tbody><tr><td><strong>Workflow State/ Event</strong></td><td><strong>Current State</strong></td><td><strong>SLA (In Days)</strong></td></tr><tr><td>Edit/ Re-submit</td><td>Pending for correction</td><td>1</td></tr><tr><td>Verify and Forward</td><td>Pending for verification</td><td>2</td></tr><tr><td>Technical Sanction</td><td>Pending for technical sanction</td><td>1</td></tr><tr><td>Approve</td><td>Pending for approval</td><td>1</td></tr></tbody></table>

## UI <a href="#ui" id="ui"></a>

The UI is same as original estimate.

## Acceptance Criteria <a href="#acceptancecriteria" id="acceptancecriteria"></a>

1. Roles are created as given provided.
2. Actions are configured based on role - action mapping.
3. Workflow states are defined as provided and the state transition done accordingly.
