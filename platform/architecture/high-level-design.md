# High Level Design

The platform architecture illustration below provides a visual representation of the key components and layers that facilitate a seamless flow of information across multiple departments.&#x20;

<figure><img src="../../.gitbook/assets/image (45).png" alt=""><figcaption></figcaption></figure>

The high-level design (refer image above) of the Works System can be divided into three parts:

1. Master(Reference) Data
2. Works Registries(Services)
3. Reused/Enhanced DIGIT Core Services

## Master (Reference) Data

Below are classifications of some of the master data used in the Works platform. For a comprehensive list, please refer to the service documentation

{% hint style="info" %}
DIGIT Core service masters are not covered below.&#x20;
{% endhint %}

1. Simple Masters:
   1. Organisation Class
   2. Organisation Functional Area
   3. Organisation Type
   4. Department
   5. Nature of Work
   6. Wage Seeker Skills
   7. Labour Charges
   8. Overheads
   9. Headcodes
   10. Applicable Charges
   11. Mode of Entrustment&#x20;
   12. Beneficiary Type
   13. Designations
2. Hierarchical Masters&#x20;
   1. Type of work&#x20;
   2. Sub-type of work
3. Location - Same as DIGIT

## Works Registries

1. Individual - stores details of individual citizens. Individuals may or may not be users of the DIGIT system. If they need login access, they will be created in the User registry.&#x20;
2. Organisation - This registry holds details of all types of organisations, their functional areas and class.
3. Bank Accounts - This registry stores bank account details to be used for online payments in a safe and secure manner.&#x20;

## Works Services

The following domain services have been developed/are being planned as part of the Works platform:

1. Project
2. Estimate&#x20;
3. Contracts
4. Attendance
5. Muster roll
6. Expense/Billing
7. JIT Adapter (Roadmap)
8. Milestones (roadmap)
9. Payment Calendar (roadmap)
10. Measurement Book (roadmap)



## Reused/Enhanced DIGIT Services

The following list consists of major core services from DIGIT that will be reused in Works Project. A few of the common core services might have been missed from the list.

* [x] As-is Reused DIGIT Services
  1. Master Data Management Service(MDMS)
  2. Location Service
  3. User Service
  4. Access Control Service
  5. Zuul API Gateway
  6. PDF Service
  7. File Store Service
  8. IdGen Service
  9. Persister&#x20;
  10. Indexer
  11. Inbox Service
  12. Report Service
