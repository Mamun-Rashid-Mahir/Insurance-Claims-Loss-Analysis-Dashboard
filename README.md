# Insurance Corporate Claims & Loss Intelligence Dashboard

## 📊 Business Performance & Risk Portals
An enterprise financial risk monitoring framework designed for property and casualty (P&C) insurance providers to optimize underwriting guidelines, isolate exposure risks, and track operational claims performance.

<p align="center">
  <img src="Insurance Co. loss Analysis_Home.jpg" width="49%" alt="Landing Portal View" />
  <img src="Insurance Co. loss Analysis.jpg" width="49%" alt="Analytical Workspace View" />
</p>

### 🔗 Public Interactive Link
* [👉 Click Here to Explore the Live Interactive Corporate Insurance Portfolio](YOUR_POWER_BI_SERVICE_OR_NOVYPRO_LINK_HERE) *

---

## 📈 Strategic KPI Matrix & Actuarial Insights

### 1. Macro Risk Exposures & Financial Health
* **Total Claim Ingestion:** Monitors an enterprise database of **15K Active Claims**, tracking a combined premium pool value of **$21.46M**.
* **Financial Loss Severity:** Systematically captures **$32.48M in Total Claims Losses**, establishing a critical baseline to review current premium underwriting pricing.
* **Operational Turnaround:** Tracks corporate processing efficiency, displaying an **Average Days to Settle of 17.5 Days**.

### 2. Policyholder Demographics & Risk Profiling
* **Age Group Concentrations:** Pinpoints high-exposure policyholder risk bands. The **18-30 Age Cohort ($11.51M)** and the **31-45 Age Cohort ($11.05M)** account for the vast majority of all financial losses.
* **Gender Distributions:** Displays clear claims equity tracking with **Male Policyholders ($16.4M)** and **Female Policyholders ($16.08M)** splitting exposures symmetrically.

### 3. Geographic Loss Analysis
* **Regional Claims Mapping:** Isolates regional risk profiles across major operating zones, ranking regional claim distributions cleanly (**Dhaka: 4.54K claims**, **Chittagong: 3.65K**, **Khulna: 2.27K**, and **Sylhet: 1.54K**). This spatial analysis alerts underwriters to tighten local structural risk guidelines.

### 4. Continuous Loss Volatility Trends
* **Monthly Claims Run-Rate:** A continuous trend graph tracking financial claim movements over the rolling financial calendar. It identifies an operational risk spike during **October (1.4K Claims)**, alerting management to balance resource capacities during recurring seasonal weather or traffic anomalies.

---

## 🛠️ Advanced ETL Ingestion & Schema Data Modeling
* **Data Schema Design:** Modeled on a robust Star Schema architecture, connecting transactional claims fact tables (`Fact_Claims`) directly to master dimensions for Geography (`Dim_Regions`), Time Intelligence (`Dim_Calendar`), and Customer Profiles (`Dim_Policyholders`) using strict **1-to-Many (`1:*`) relationships**.
* **ETL Transformations:** Filtered raw irregular string variations in policy claim descriptions, explicitly converted claim settlement data durations, and handled missing values across premium inputs to eliminate calculation errors.

### Centralized Explicit DAX Performance Metrics

#### Actuarial Underwriting Loss Ratio
```dax
Loss Ratio % = 
VAR TotalLosses = SUM('Fact_Claims'[LossAmount])
VAR TotalPremiums = SUM('Fact_Claims'[PremiumAmount])
RETURN
DIVIDE(TotalLosses, TotalPremiums, 0)
