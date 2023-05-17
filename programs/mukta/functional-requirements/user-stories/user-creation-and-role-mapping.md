# User Creation & Role Mapping

## Scope

Employees users creation and role mapping

## Actors

Employees

## Details

1. HRMS module to be used to create the employee users and mapping of roles.
2. Roles are created from the back end and actions are mapped as per role requirements.&#x20;
3. Once an employee user is created, an SMS notification is sent to the user with a username and first-time password. The user is asked to reset the password login for the first time.
4. The user resets the password and then logs in to the system using the username and password.
5. HRMS is packaged with MUKTA and the HRMS access is provided to MUKAT\_ADMIN.
6. Use the UAT for initial testing. Testing credentials and URLs are available on request.&#x20;
7. Once the HRMS is packaged with MUKTA, it is tested thoroughly with MUKTA-specific role and action mapping.

## Validations

Not applicable

## Configurations

Not applicable

## Actions

### Login

1. On successful login, the user is taken to Home Page.
2. On failure due to incorrect credentials, an appropriate message is displayed.

### Forgot Password

1. It will take the user to the password reset page.

## Notifications

Not applicable.

## User Interface



## Acceptance Criteria

| Acceptance Criteria  | Description                                                              |
| -------------------- | ------------------------------------------------------------------------ |
| 1                    | User creation flows to be tested and validated for working without error |
| 2                    |                                                                          |
|                      |                                                                          |



