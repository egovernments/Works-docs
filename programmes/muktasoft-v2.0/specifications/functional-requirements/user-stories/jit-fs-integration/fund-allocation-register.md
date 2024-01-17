# Fund Allocation Register

## Context

Fund allocation details.

## Solution <a href="#solution" id="solution"></a>

### Scope <a href="#scope" id="scope"></a>

Fund Allocation Register

Reports → Fund Allocation Register

### Actors <a href="#actors" id="actors"></a>

Employee

Role: Fund Allocation View

## Details <a href="#details" id="details"></a>

1. Virtual Allotment Details (VA) is the API to fetch the fund allocation details.
2. MUKTA as a scheme has multiple HOAs for which fund is sanctioned and allocated.
3. Fund Allocation Register has to be developed to see and download the details.
4. For Request/ Response parameters, please refer to the [integration approach document](broken-reference).
5. This data is stored and maintained at MUKTASoft for every financial year and used for reporting and reference purposes.
6. APIs will be triggered daily at 10 PM.

### Search Parameters

<table><thead><tr><th width="60.66666666666666">#</th><th width="172">Field </th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Financial Year</td><td>Financial year, by default current financial year is selected.</td></tr><tr><td>2</td><td>Head of Account</td><td>HOAs from the configuration.</td></tr><tr><td>3</td><td>Transaction Type</td><td>Allotment types are, 1) Initial Allotment 2) Additional Allotment 3) Withdrawal 4) Expense 5) Expense Reversed</td></tr></tbody></table>

{% hint style="info" %}
**Note:** Financial Year is mandatory to select, by default current financial year is selected and records are searched.
{% endhint %}

### Search Result

<table><thead><tr><th width="74.66666666666666">#</th><th width="192">Field</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>HOA</td><td>Head of accounts of MUKTA</td></tr><tr><td>2</td><td>Transaction Number</td><td>Transaction number of the transactions fetched from JIT or created in MUKTASoft.</td></tr><tr><td>3</td><td>Transaction Date</td><td>Date of transaction received from JIT-FS in a response of API call or the MUKTASoft PI creation date. Date to be taken care when calling the API again.</td></tr><tr><td>4</td><td>Transaction Type</td><td><p>A transaction type would be anything from the options given below.</p><ol start="1"><li>Initial Allotment</li><li>Additional Allotment</li><li>Withdrawal</li><li>Expense</li><li>Expense (Reversed)<br>First 3 are received from JIT-FS system through API call while the last one is from MUKTASoft when a PI is pushed. A reverse entry of the Expense is made in the case PI is canceled or failed to create.</li></ol></td></tr><tr><td>5</td><td>Transaction Amount</td><td>It is transaction amount.</td></tr><tr><td>6</td><td>Sanctioned Balance</td><td>It is the balance remaining from the sanctioned amount and calculated as given below.<br>Sanctioned Balance = Total Sanctioned Amount - Sum of all the allotments.</td></tr><tr><td>7</td><td>Fund Available</td><td>It the fund available for the expenditure and calculated as given below.<br>Fund Available = Sum of all the allotments - (Sum of all the expenditure + Sum of all the withdrawal)</td></tr></tbody></table>

## Validations <a href="#validations" id="validations"></a>

1. While fetching the details, from date should be taken care of properly.
2. The records/transactions are sorted in chronological order.

## Configurations <a href="#configurations" id="configurations"></a>

### Master Data <a href="#masterdata" id="masterdata"></a>

The master data that needs to be configured.

1. Special Spending Unit
   * SSU ID
   * SSU Name
   * Grantee Code
   * DDO Code
   * Tenant ID
2. Head of Accounts
   * Code
   * Name

* 221705789358641045908 (MUKTA -  SC Component)&#x20;
* 221705800358641045908 (MUKTA -  General Component)
* 221705796358641045908 (MUKTA -  ST Component)

### Attachments <a href="#attachments" id="attachments"></a>

Not applicable.

### Workflow <a href="#workflow" id="workflow"></a>

Not applicable.

### Actions <a href="#actions" id="actions"></a>

Search - Fetch and display the records based on the search parameters.

Clear - Clear the search parameters.

Download - The option to download the report into PDF format is provided as per the attached format.

### Notifications <a href="#notifications" id="notifications"></a>

Not applicable

## User Interface <a href="#userinterface" id="userinterface"></a>

<figure><img src="../../../../../../.gitbook/assets/Fund Allocation Register.jpg" alt=""><figcaption></figcaption></figure>

## Acceptance Criteria <a href="#acceptancecriteria" id="acceptancecriteria"></a>

1. Data fetched is stored for reporting and reference purposes.
2. The report is developed with the option to download it into PDF.
