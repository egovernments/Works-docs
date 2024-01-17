# SOR Uploader

## Overview

SOR Uploader is a Bulk Upload Service that helps in uploading all  the SOR description at state level and their respective rates at ULB level in a single go.

## Dependency&#x20;

* MDMS-V2
* SOR Description And Rates Sheet
* &#x20;Create the Overheads, Type,Variants,UOM first before trigerring the bulk upload api.
* Create the requried excel from the provided excel once the above point is completed.

## Code

[Bulk-Upload](https://github.com/odisha-muktasoft/MUKTA\_IMPL/tree/UAT/utilities/bulk-upload)

[ces](https://github.com/egovernments/DIGIT-Works/tree/measurement-ui/utilities/mukta-services)

## Deployment

* [Helm Chart](https://github.com/odisha-muktasoft/DIGIT-DevOps/tree/mukta-1.22-changes/deploy-as-code/helm/charts/digit-works/utilities/bulk-upload)

## Role Action&#x20;

For this api --/bulk-upload/\_bulkUpload , there is no role mapping as such because for the first time upload it will be used by our internal team as no UI is developed for it as of now. But as we are calling mdms-V2 Sor (/mdms-v2/v2/\_create/WORKS-SOR.SOR) and rates(/mdms-v2/v2/\_create/WORKS-SOR.Rates) apis so need roles specific to that.

## Bulk Upload Service Requirements.

This service is not developed on a generic level so it requires some human intervention to setup the data in the required format. As the field teams provide us the data  without bifurcating it in State specific and ULB specific sheets.

This is the sheet provied by the field team - [https://docs.google.com/spreadsheets/d/13D54ifHgaIGqGAAkJEjIpqJx3TrJSxr3tcG2kX52JUo/edit#gid=15557893](https://docs.google.com/spreadsheets/d/13D54ifHgaIGqGAAkJEjIpqJx3TrJSxr3tcG2kX52JUo/edit#gid=15557893)

So to incorporate the changes required for the bulk upload service to work properly we need to create  and maintain the SOR description sheet and SOR rates sheet differently.

Excel Maintained for Uploading Sor Description--\
[https://docs.google.com/spreadsheets/d/1GPTWmUZI\_YB\_-O-K1VZxfK-96sFGFPTfKkStt19GDQE/edit#gid=0](https://docs.google.com/spreadsheets/d/1GPTWmUZI\_YB\_-O-K1VZxfK-96sFGFPTfKkStt19GDQE/edit#gid=0)



To generate the below sheet we need the SOR ids which we will get for each of the above SOR description in the bulk upload response , and we need  all the heads(Overheads, UOM) which we have already created earlier .

\
Excel Maintained for Uploading Sor Rates --\
[https://docs.google.com/spreadsheets/d/1bw-\_6tm8mx4PiIOBST2caqGPcFgxchL5t03NKh6p7-Q/edit#gid=0](https://docs.google.com/spreadsheets/d/1bw-\_6tm8mx4PiIOBST2caqGPcFgxchL5t03NKh6p7-Q/edit#gid=0)

