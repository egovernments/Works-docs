# Time Extension

## Overview

A work order is created for an approved estimate to award the work to CBO. CBO starts the work to complete it within a given period.

In case the organization comes to know that they are not in a position to complete the work within the given time frame due to various reasons, they need to inform the same to officer in charge of the project and apply for a time extension which is then subject to approval/ canceling of work order based on the analysis done by the ULB.

Requests for time extension can be directly raised by CBO using the mobile application and by the officer in charge of the project on behalf of CBO using a web application. Once a request is raised it goes for verification and approval.

The Time Extension module has the following screens in the web interface -

* Create Time Extension
* View Time Extension
* Edit Time Extension
* Search Time Extension (Same as search work order screen)
* Inbox (Same as work order inbox)

## Configuration

#### Create Time Extension request - conditions

* Work order must be in the Accepted state
* Existing Time Extension requests, if already created, must not be in the workflow
* At least one muster roll must be approved&#x20;

#### Create a Time Extension Request in Web-Interface - Steps

* Log in with the work order creator role and Navigate to the Home page.&#x20;
* Home > Work Orders > Inbox > Search Work Order >  View Work Order > Request Time Extension (From Action Menu).
* A screen similar to the Work Order View screen is opened along with two new input fields.&#x20;
* Enter the time extension value (in days) and reason in those two inputs and click on the Create action button.
* A workflow popup is opened where users can enter the assignee and relevant comments. Click on the Submit button.
* A response page is opened which shows the newly created revised work order application’s number.

#### Inbox, View and Search Screens For Time Extension in Web Interface

There is no separate inbox for time extension. The work order inbox will list the time extension requests which are INWORKFLOW state. Clicking on the time extension request will open a view time extension screen where the user can take action on the request based on the roles defined in the workflow. Alternatively, users can go to the work order search screen to search for any time extension request.

### Time Extension Workflow&#x20;

| #                   | Action                               | Role                                                       | From State                                 | To State                                   | Status                         |
| ------------------- | ------------------------------------ | ---------------------------------------------------------- | ------------------------------------------ | ------------------------------------------ | ------------------------------ |
| <p>1</p><p><br></p> | <p>Submit </p><p><br></p>            | <p>Work Order Creator/ CBO Admin</p><p><br></p>            | <p><br></p>                                | <p>Pending for verification</p><p><br></p> | <p>Submitted</p><p><br></p>    |
| <p>2</p><p><br></p> | <p>Verify and Forward</p><p><br></p> | <p>Work Order Verifier</p><p><br></p>                      | <p>Pending for verification</p><p><br></p> | <p>Pending for approval</p><p><br></p>     | <p>Verified</p><p><br></p>     |
| <p>3</p><p><br></p> | <p>Send Back</p><p><br></p>          | <p>Work Order Verifier</p><p><br></p>                      | <p>Pending for verification</p><p><br></p> | <p>Pending for correction</p><p><br></p>   | <p>Sent Back</p><p><br></p>    |
| <p>4</p><p><br></p> | <p>Send Back</p><p><br></p>          | <p>Work Order Approver</p><p><br></p>                      | <p>Pending for approval</p><p><br></p>     | <p>Pending for verification</p><p><br></p> | <p>Sent Back</p><p><br></p>    |
| <p>5</p><p><br></p> | <p>Send Back To CBO</p><p><br></p>   | <p>&#x3C;any roles having access of action></p><p><br></p> | <p>&#x3C;Current Status></p><p><br></p>    | <p>Pending for correction</p><p><br></p>   | <p>Sent Back</p><p><br></p>    |
| <p>6</p><p><br></p> | <p>Edit/ Re-submit</p><p><br></p>    | <p>Work Order Creator</p><p><br></p>                       | <p>Pending for correction</p><p><br></p>   | <p>Pending for verification</p><p><br></p> | <p>Re-submitted</p><p><br></p> |
| <p>7</p><p><br></p> | <p>Approve</p><p><br></p>            | <p>Work Order Approver</p><p><br></p>                      | <p>Pending for approval</p><p><br></p>     | <p>Approved</p><p><br></p>                 | <p>Approved</p><p><br></p>     |
| <p>8</p><p><br></p> | <p>Reject</p><p><br></p>             | <p>&#x3C;any roles having access></p><p><br></p>           | <p>&#x3C;Current Status></p><p><br></p>    | <p>Rejected</p><p><br></p>                 | <p>Rejected</p><p><br></p>     |

