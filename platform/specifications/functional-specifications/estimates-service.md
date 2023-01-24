# Estimates Service

## Overview

Estimates are created for each project/sub-project entity.

## Features & Scope

Multiple estimate types for each project are prepared with different levels of abstraction.

| Estimate Type | Definition                                                                                                                                                                                                                                                                            |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Proposal      | A single line item having the overall project cost against the project title. This will go for in-principal Admin sanction. Once Approved Detailed Estimate for the same will be created                                                                                              |
| Detailed      | A Detailed Estimate contains of engineering drawings done on AutoCAD & other drwawing tools. Modern tools also abstract out many measurements and materials from drawings created in these tools.                                                                                     |
| Abstract      | Abstract Estimate is prepared using standard SOR & Non SOR Items defined by PWD (manytimes ULBs customise SOR and have their own copies). SOR items is created internally using Item rates                                                                                            |
| Revised       | When a project finances is increasing than to what is initially estimated, revision estimates are created and approved. revision estimates may or may not have same SORs as initial estimates. Revised estimate line items added to initial line items will give overall project cost |
| Deviation     | Deviation statement is a type of estimation when scope of the project changes but project cost is meant to remain same. Deviation statement and revised estimate are same as far as estimation process is concered. Only approving authority will change                              |
| Spill Over    | For a Multi year project, an estimate is financially broken down into pieces and budget allocation is done for each year instead of allocating entire budget in first year.                                                                                                           |

**Abstract Estimate:** An abstract estimate is done by the junior engineers using SOR, and Non-SORd overhead items.

## Functional Requirements

1. After creating the project (and getting approved if there is a workflow) JE will start estimating the project.&#x20;
2. To create an estimate following details are required.
   * Line Items from SOR
   * Non-SOR Line items
   * Overheads
3. To select line items for SOR, select the SOR category, search for the SOR line item by SOR code or SOR description and select the SOR.
   * To the SOR line item, add the quantity that is required for this project.&#x20;
   * SOR standard amount multiplied by this quantity gives the line item-wise cost.&#x20;
4. Measurements can be captured at the SOR line item level directly by the specified UOM or length, breadth, height, quantity can be captured and stored in an empty measurement book so as to utilise it later for m book recordings.&#x20;
   * Multiplication of L,B,H,Q will give the required quantity of the line item for the estimate.&#x20;
5. A non-SOR line item will not be defined in MDMS and hence will not be searchable using the SOR category or Code.&#x20;
   * Rate, Quantity, and Description have to be entered manually.&#x20;
   * Just like SOR, instead of quantity directly, L,B,H,Q can also be captured.&#x20;
6. All SOR and Non-SOR items in the way captured in the estimates will be created as empty records in the Measurement Book to capture readings later.&#x20;
7. Overheads are predefined masters.&#x20;
   * The cost of the project becomes the cost of SOR and Non-SOR items plus overheads.
   * Overheads are added on top of project costs so as to come to the overall estimated amount.&#x20;
   * Overheads amount will not be going to the contractor but will be going to specific heads defined in the Master for respective overheads. (GST 12% to GST department, Cess 1% to labour dept etc)

## Use Cases

##

## Mockups

![](https://lh6.googleusercontent.com/P6rNxBib9dejLbPHHliUWizLC1-H\_nz9lEC4IQdwYePcVqhSn9cb\_gfLUhJWC2vPGg6obdvIXhndKIZOveDYc\_ReudamDJia1cB60O1d5OAHHCox4WX7-\_bi-0Gz6X1g6hDk9GjV680PSVVtvFEiT1yr\_sa-lDixdHhuZrbtkrjRgOOKGxlipfRS6c2rGw)
