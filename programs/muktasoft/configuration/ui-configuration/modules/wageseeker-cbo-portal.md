---
description: Wageseeker TechDocument
---

# WageSeeker (CBO Portal)

## Overview

This module helps create wage seekers.

ROLE: ORG\_ADMIN

This module has 4 associated forms&#x20;

1. [Individual Details](wageseeker-cbo-portal.md#individual-details)
2. [Address Details](wageseeker-cbo-portal.md#address-details)
3. [Financial Details](wageseeker-cbo-portal.md#financial-details)
4. Summary Details

## **Individual Details**

| S.No. | Fields          | Mandatory | Validations                                                       |
| ----- | --------------- | --------- | ----------------------------------------------------------------- |
| 1.    | Aadhaar No.     | Yes       | <p>Input: [0-9]</p><p>Max Length: 12</p><p>Min Length: 12</p>     |
| 2.    | Name            | Yes       | <p>Input: [A-Za-z ]</p><p>Max Length: 128</p><p>Min Length: 2</p> |
| 3.    | Guardian Name   | Yes       | <p>Input: [A-Za-z ]</p><p>Max Length: 128</p><p>Min Length: 2</p> |
| 4.    | Relationship    | Yes       | None                                                              |
| 5.    | Date of Birth   | Yes       | Age shouldn’t be less than 18 years                               |
| 6.    | Gender          | Yes       | None                                                              |
| 7.    | Social Category | No        | None                                                              |
| 8.    | Mobile Number   | Yes       | <p>Input: [0-9]</p><p>Max Length: 10</p><p>Min Length: 10</p>     |
| 9.    | Skills          | Yes       | Can not select multiple skills of same sub skill type             |
| 10.   | Photograph      | No        | File size should be < 5 MB                                        |

## Address Details

| S.No.  | Fields      | Mandatory | Validations                                                 |
| ------ | ----------- | --------- | ----------------------------------------------------------- |
| 1.     | Pincode     | No        | <p>Input: [0-9]</p><p>Max Length: 6</p><p>Min Length: 6</p> |
| 2.     | City        | Yes       | None                                                        |
| 3.     | Ward        | Yes       | None                                                        |
| 4.     | Locality    | Yes       | None                                                        |
| 5.     | Street Name | No        | <p><br></p><p>Max Length: 64</p><p>Min Length: 0</p>        |
| 6.     | Door No     | No        | <p>Max Length: 64</p><p>Min Length: 0</p>                   |

## Financial Details

| S.No.  | Fields                   | Mandatory | Validations                                                                              |
| ------ | ------------------------ | --------- | ---------------------------------------------------------------------------------------- |
| 1.     | Account Holder’s Name    | Yes       | <p>Input: [A-Za-z ]</p><p>Max Length: 128</p><p>Min Length: 2</p>                        |
| 2.     | Account Number           | Yes       | <p>Input: [0-9]</p><p>Max Length: 18</p><p>Min Length: 9</p>                             |
| 3.     | Re-enter Account Number  | Yes       | <p>Input: [0-9]</p><p>Max Length: 18</p><p>Min Length: 9</p>                             |
| 4.     | Account Type             | Yes       | None                                                                                     |
| 5.     | IFSC Code                | Yes       | <p>Valid IFSC Code</p><p>Verified through</p><p>https://ifsc.razorpay.com</p><p><br></p> |

This form combines the details of the previous 3 forms, and users can tap on the respective edit icon to edit the particular details.

On submit, the wage seeker is created successfully.

## **API Details**

| S. no. | API                                                                     | Body/Query Params                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Description                                                    |
| ------ | ----------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------- |
| 1      | <p>'individual/v1/_create'</p><p><br><br><br></p>                       | <p>"Individual": {</p><p> "tenantId":,</p><p> "name": {"givenName": ,</p><p> "dateOfBirth":,</p><p> "gender":,</p><p> "mobileNumber":,</p><p> "address": [</p><p>   {</p><p>     "tenantId":,</p><p>     "pincode":,</p><p>     "street":,</p><p>     "doorNo":,</p><p>     "type": "PERMANENT",</p><p>     "locality": {"code":</p><p> ],</p><p> "fatherName":,</p><p> "husbandName":,</p><p> "relationship":,</p><p> "identifiers": [</p><p>   {</p><p>     "identifierType": "AADHAAR",</p><p>     "identifierId":</p><p>   }</p><p> ],</p><p> "skills": [],</p><p> "photo":,</p><p> "additionalFields": {</p><p>   "fields": [</p><p>     {</p><p>       "key": "SOCIAL_CATEGORY",</p><p>       "value":</p><p>     }</p><p>   ]</p><p> }</p><p>}</p><p><br><br></p> | <p>Create Individual/Wage seekers</p><p><br></p>               |
| 2      | <p>'/bankaccount-service/bankaccount/v1/_create'</p><p><br><br><br></p> | <p> </p><p>"bankAccounts": [</p><p> {</p><p>   "tenantId":,</p><p>   "serviceCode": "IND",</p><p>   "referenceId": individualId,</p><p>   "bankAccountDetails": [</p><p>     {</p><p>       "tenantId":,</p><p>       "accountHolderName":</p><p>"accountNumber":,</p><p>       "accountType":,</p><p>       "isPrimary",</p><p>       "bankBranchIdentifier": {</p><p>         "type": "IFSC",</p><p>         "code":,</p><p>         "additionalDetails": {"ifsccode"}</p><p>       },</p><p>       "isActive": true,</p><p>       "documents": [],</p><p>     }</p><p>   ],</p><p> }</p><p>]</p><p><br><br><br></p>                                                                                                                                                   | To create the bank details for the individual that was created |
