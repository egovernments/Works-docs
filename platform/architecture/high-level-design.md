# High Level Design

The platform architecture illustration below provides a visual representation of the key components and layers that facilitate a seamless flow of information across multiple departments.&#x20;

<figure><img src="../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

The high-level design (refer image above) of the Works System can be divided into three parts:

1. Master(Reference) Data
2. Works Registries(Services)
3. Reused/Enhanced DIGIT Core Services

## Master (Reference) Data

Based on the complexity required to maintain Master Data it is categorized into the following:

1. Simple Masters:
   1. Contractor Class
   2. Department
   3. Nature of Work
   4. Mode of Entrustment&#x20;
   5. Beneficiary Type
   6. Designations
2. Hierarchical Masters&#x20;
   1. Type of work&#x20;
   2. Sub-type of work
3. Finance Masters - Same as DIGIT
   1. Budget Head&#x20;
   2. Scheme&#x20;
   3. Sub-scheme&#x20;
   4. Fund&#x20;
   5. Function
4. Location - Same as DIGIT

## Works Registries

1. Individual
2. Organisation
3. Financial

## Works Services

The following domain services are developed as part of the Works platform:

1. Project
2. Estimate&#x20;
3. Work Package
4. Contracts
5. Milestones
6. Payment Calendar
7. Measurement Book
8. Expenditure or Billing

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
