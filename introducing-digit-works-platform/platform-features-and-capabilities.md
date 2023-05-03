---
description: Draft (needs review)
---

# Platform Capabilities

## Works Overview

A Works Management System (WMS) typically is used by various departments in the government to track end to end lifecycle of a project (Scope and Finances).

The input to works could be a decision that is taken in the legislature for the construction of new capital works or demand that is generated from within society or officers, for maintenance of existing projects.

* Construction of new metro rail is of nature capital works (New Works)
* Repair of existing roads is of nature operations and maintenance (O\&M)

Read on to learn more about the features and capabilities supported by Works.

## Estimation <a href="#_7lxspous6vj4" id="_7lxspous6vj4"></a>

* [x] Once the project is decided, the first step is to estimate the cost of the project.
* [x] The estimation includes multiple steps.
  1. **Estimate Proposal:**
     * The Estimate proposal is to get in-principal approval for the project. If approved, the concerned engineer can start to make detailed estimates for the project.
     * The estimate Proposal has high-level details like the name of the project, a brief description, a few line items that constitute the project and under which budget heads of finance the project will be funded.
  2. **Detail Estimate:**
     * A detailed Estimate is prepared mostly after the estimate proposal is approved. (In many cases, these may start simultaneously, as the concerned engineer would already know the chances for approvals)
     * A detailed Estimate is generally prepared in offline tools supporting advanced functionalities and methods of doing scope estimation. ( For example, in the case of Civil Projects, an estimation tool/process already has Plinth Area Estimate, Service Unit Method, Floor Area Method, Carpet Area Method, Typical Bay Method, and Cost Comparison Method) With this, it is possible to do a very detailed analysis.
  3. **Abstract Estimate:**
     * An abstract estimate is a grouping and summary of the bill of quantities that evolved from a detailed estimation process.
     * The concerned engineer enters the abstract estimate details into WMS. This goes through an approval process through necessary stakeholders and departments depending on the nature of work, Type of Work, and Estimated Cost.
  4. **Sub Estimate:**
     * An Estimate is sometimes divided into Sub Estimates (For large or multi-location projects etc) for better management purposes.
     * Sub- Estimates are later grouped into Work Packages for an easy tendering process.
  5. **Spill Over Estimate:**
     * For a project that spreads into multiple financial years, a spillover estimate is created for that year. Hence no new request for assetization is needed.
  6. **Revised Estimate:**
     * Under circumstances where the scope & Finances of the project goes beyond the estimated amount and the set buffer, a revised estimate needs to be created and go through the approval process.

## Tendering <a href="#_irv9nx28q2r3" id="_irv9nx28q2r3"></a>

1. **Work Packages**, created from Estimates/Sub Estimates, are essentially Scope & BOQs that give contractors enough information to Bid for the contract.
   * Authorities draft tender papers (DTP) using Work Packages.
2. Bids are invited from contractors between set dates. There is also a negotiation process that happens on the bid amount. The contractor with the lowest bid is selected.
3. The Authority issues a Letter of Intent to do a contract with the Contractor
   * The contractor issues a Letter of Acceptance in response to the LOI

## Contracting <a href="#_yxkefd3kpmer" id="_yxkefd3kpmer"></a>

1. A Work Order is then created and shared with the Contractor
   * A work order is a detailed document that contains Scope, Bill of Quantities, Timelines, Terms and Conditions, Details of Contractor, Liability Periods, Other Documents etc
2. A Work order also goes through the approval process.

## Measurement <a href="#_q6w3dto1rpzh" id="_q6w3dto1rpzh"></a>

1. Before the measurement starts, there are also certain offline checks that need to be done. For example, Acceptance letter issued to date, Letter acknowledged date, Work Order acknowledged and signed Site handover date, Work commenced date etc.
2. Measurement is done of two types.
   * **Tracking Milestones:**
     * Milestones are set up during the contracting phase and before the project starts. These milestones describe by what point of time, and what percentage of work will be completed in various stages.
     * As a milestone is reached, it needs to be tracked in WMS on the completion status.
     * All Milestones need to be in the completed stage to process the final contractor Bill
   * **Tracking Measurement Book:**
     * MBook is also set up for detailed project tracking. M Book measurements are derived from Abstract estimates and track the day-day progress of completed work.
     * MBook measurements can be entered by the vendor and verified by employees or can be entered by ground inspectors/ field staff on a regular basis.

## Contractor Bill and Payments <a href="#_t8dle02vzju0" id="_t8dle02vzju0"></a>

1. As the project progresses, the contractor raises the invoice for which bills are created by the employee in the system under specific budget heads and sent for approval
2. Approved Bills are sent to the Finance department for disbursement.
   * **Advance Bill:**
     * Bill that is raised before the commencement of work. For example, to buy construction materials or to procure labour.
   * **Part Bill:**
     * Bills that are raised during the course of Work.
     * In an ideal scenario, these bills are tightly coupled with the amount of Work that is done (M Book measurements)
   * Final Bill:
     * Last Bill that is raised before completing the project.

## Project Closure <a href="#_pnzn1sroolt" id="_pnzn1sroolt"></a>

Closing the project is a set of activities/checklists (prospective list given below) that are run to ensure all requirements are fulfilled.

1. Assetization request raised
2. Final bill approved
3. Site inspection done
4. Site handover done
5. Contractor feedback submitted etc

## Reports and Dashboards <a href="#_y5y46t164a4t" id="_y5y46t164a4t"></a>

Reports and Dashboards give employees views and ways to analyze project performance within their jurisdiction. This also includes timelines, delays, risks, projections etc.

1. Some of the reports are
   * Work Progress Register
   * Estimate Appropriation Register
   * Estimate Abstract Report by Department
   * Contractor Bill Report
   * Works Utilisation Report
   * Retention Money Recovery Register
2. Each report will be made available to be downloaded in PDF as well as Excel.

DSS Dashboard will also be included.

## Master Records

Many master records are required for the smooth functioning of WMS.

Some of these are listed below:

1. Contractor Class Master
2. Bank Master
3. Department Master
4. Department Category Master
5. Contractor Master
6. Election Ward Master
7. Location Master
8. Work Category Master
9. Beneficiary Master
10. Nature of Work Master
11. Type of Work Master
12. Sub-Type of Work Master
13. Recommended Mode of Entrustment Master
14. Fund Master Master
15. Function Master
16. Budget Head Master
17. Scheme Master
18. Sub-Scheme Master
19. Designations Master
20. User Master

A process flow detailing all steps in Works within various value bundles is given below. Refer to the colour legend on top of the attached diagram for a better understanding.

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>
