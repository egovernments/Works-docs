# Muster Roll Workflow

## **Context**

Map workflows to roles for muster rolls.

## **Actors**

Employees, Admins.

## **Actions**

### **Scope**

Muster roll is created by CBO weekly and then sent for approval and payment to JE/AE.

### **Details**

#### Role (Actors) - Action Mapping

<table><thead><tr><th width="89">#</th><th>Role</th><th width="249">Action</th><th>User Persona</th></tr></thead><tbody><tr><td>1</td><td>CBO ADMIN</td><td><ul><li>Create </li><li>View </li><li>Edit/ Re-submit</li><li>Submit </li></ul></td><td>CBO User</td></tr><tr><td>2</td><td>MUSTER ROLL VERIFIER</td><td><ul><li>Search</li><li>View </li><li>Edit</li><li>Verify and Forward </li><li>Send Back To CBO</li></ul></td><td>Junior Engineer/ Assistant Engineer</td></tr><tr><td>3</td><td>MUSTER ROLL APPROVER</td><td><ul><li>Search</li><li>View </li><li>Approve</li><li>Send Back </li></ul></td><td>Municipal Engineer</td></tr></tbody></table>

#### Workflow States

<table><thead><tr><th width="101">#</th><th>Action</th><th>Role</th><th>From State</th><th>To State </th><th>Status</th></tr></thead><tbody><tr><td>1</td><td>Submit</td><td>CBO ADMIN</td><td> </td><td>Pending for verification</td><td>Submitted</td></tr><tr><td>2</td><td>Verify and Forward</td><td>MUSTER ROLL VERIFIER</td><td>Pending for verification</td><td>Pending for approval</td><td>Verified</td></tr><tr><td>4</td><td>Send Back</td><td>MUSTER ROLL APPROVER</td><td>Pending for approval</td><td>Pending for verification</td><td>Sent Back</td></tr><tr><td>5</td><td>Send Back To CBO</td><td><strong>&#x3C;any roles having access></strong></td><td><strong>&#x3C;Current Status></strong></td><td>Pending for correction</td><td>Sent Back</td></tr><tr><td>6</td><td>Edit/ Re-submit</td><td>CBO ADMIN</td><td>Pending for correction</td><td>Pending for verification</td><td>Re-submitted</td></tr><tr><td>7</td><td>Edit/ Re-submit</td><td>MUSTER ROLL VERIFIER</td><td>Pending for verification</td><td>Pending for approval</td><td>Re-submitted</td></tr><tr><td>8</td><td>Approve</td><td>MUSTER ROLL APPROVER</td><td>Pending for approval</td><td>Approved</td><td>Approved</td></tr></tbody></table>

#### SLAs

| Service Name | Action             | Current State            | SLAs (In Days) |
| ------------ | ------------------ | ------------------------ | -------------- |
| MUSTER ROLL  | Edit/ Re-submit    | Pending for correction   | 1              |
|              | Edit/ Re-submit    | Pending for verification | 1              |
|              | Verify and Forward | Pending for verification | 1              |
|              | Approve            | Pending for approval     | 1              |

## **User Interface**

UI design is going to be the same as the estimates workflow. The workflow states will be displayed as per the table given above.

## **Acceptance Criteria**

<table><thead><tr><th width="216">Acceptance Criteria</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Actions are configured based on role - action mapping.</td></tr><tr><td>2</td><td>Workflow states are defined as provided and the state transition is done accordingly.</td></tr></tbody></table>

