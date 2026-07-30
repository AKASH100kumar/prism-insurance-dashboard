# PRISM Insurance – Claims & Policy Analytics Dashboard (Power BI)

An interactive Power BI dashboard built for **PRISM Insurance Pvt. Ltd.**, analyzing policy and claims data across 10,000+ customer records. The dashboard gives management a single view of premiums, coverage, claims performance, and policyholder demographics to support underwriting and claims-management decisions.

---

## 📌 Project Overview

The dashboard was designed to answer key questions insurance stakeholders care about:

1. What is the total Premium, Coverage, and Claim Amount across the business?
2. How is the customer base split by Gender and Age Group?
3. How are policies distributed across Policy Types (Auto, Health, Home, Life, Travel)?
4. What proportion of policies are Active vs. Inactive?
5. How many claims fall into each status — Settled, Rejected, or Pending — and what's the trend?
6. How does Claim Amount vary by policyholder Age Group?
7. What is the breakdown of Pending / Rejected / Settled claim amounts by Policy Type?
8. Can individual policies and claims be looked up and filtered on demand?

---

## 🗃️ Dataset

**`InsuranceData.csv`** — ~10,000 policy/claim records with the following fields:

| Column | Description |
|---|---|
| `PolicyNumber` | Unique policy identifier |
| `CustomerID` | Unique customer identifier |
| `Gender`, `Age` | Policyholder demographics |
| `PolicyType` | Auto, Health, Home, Life, or Travel |
| `PolicyStartDate`, `PolicyEndDate` | Policy validity period |
| `PremiumAmount` | Premium paid by the customer |
| `CoverageAmount` | Total sum insured |
| `ClaimNumber`, `ClaimDate` | Claim identifier and filing date |
| `ClaimAmount` | Amount claimed |
| `ClaimStatus` | Settled, Rejected, or Pending |

The `.pbix` file (`Project2-Insurance_Data_Analysis.pbix`) contains the full data model, DAX measures, and report visuals built on top of this dataset.

---

## 📊 Dashboard Pages

### 1. PRISM Insurance – Executive Overview
![PRISM Insurance Dashboard Overview](images/01_dashboard_overview.png)

The main dashboard page gives a complete performance snapshot in a single view:

- **KPI Cards** – Total Premium Amount (5.98M), Total Coverage Amount (600.55M), and Total Claim Amount (16.91M), giving leadership an instant read on business scale and exposure.
- **Gender Split Table** – A near-even customer base (5,001 Female vs. 5,003 Male policyholders).
- **Number of Claims by Claim Status** – A funnel-style area chart showing claims decreasing in volume from Rejected (4.4K) → Settled (3.4K) → Pending (2.3K), highlighting where claims are getting stuck in the pipeline.
- **Premium Amount by Policy Type** – A bar chart ranking policy lines by premium collected: Travel leads at 2.5M, followed by Health, Auto, Life, and Home — useful for spotting which product lines drive the most revenue.
- **Count of Active/Inactive Policies** – A donut chart showing 58.13% of policies are Active (5.82K) versus 41.87% Inactive (4.19K), flagging retention/renewal opportunities.
- **Claim Amount by Age Group** – A trend line showing claim amounts are highest for Adults (8.8M), dropping for Elders (6.4M) and dropping sharply for Young Adults (1.7M) — useful for risk-based premium pricing.
- **Policy Type × Claim Status Matrix** – A detailed table cross-tabulating Pending, Rejected, and Settled claim amounts against each Policy Type, with row totals, giving a granular financial breakdown of claims liability by product line.

### 2. Policy & Claims Detail Table
![Transaction Detail Table](images/02_transaction_detail_table.png)

A record-level, filterable table exposing every policy and its associated claim:

`PolicyNumber | CustomerID | ClaimNumber | Age | Gender | CoverageAmount | PremiumAmount | PolicyStartDate | PolicyEndDate | PolicyType | ClaimStatus | ClaimDate | ClaimAmount`

Slicers for **PolicyNumber**, **ClaimNumber**, and **CustomerID** let users drill down to a single policyholder's full record — supporting customer-service and audit use cases where a specific policy or claim needs to be investigated directly.

---

## 🛠️ Tools & Techniques Used

- **Power BI Desktop** – data modeling, DAX measures, and dashboard design
- **DAX** – calculated measures for Total Premium, Total Coverage, Total Claims, and Active/Inactive policy counts
- **Dark-themed custom report design** for a professional, boardroom-ready look
- **Donut, funnel/area, bar, and line charts** for multi-angle KPI storytelling
- **Cross-filterable slicers** (PolicyNumber, ClaimNumber, CustomerID) for record-level lookup

---

## 📂 Repository Contents

```
prism-insurance-dashboard/
├── README.md
├── InsuranceData.csv                        # Source dataset
├── Project2-Insurance_Data_Analysis.pbix     # Power BI report file
└── images/
    ├── 01_dashboard_overview.png
    └── 02_transaction_detail_table.png
```

---

## 🔑 Key Insights

- Travel policies generate the highest premium revenue, despite Health and Auto typically having higher claim volumes in the industry — worth investigating pricing strategy.
- Claims skew toward "Rejected" more than any other status, which could indicate either strict underwriting or a documentation/process gap worth auditing.
- Adults (vs. Elders and Young Adults) file the highest total claim amounts, useful input for actuarial/age-based risk pricing.
- Nearly 42% of policies are Inactive — a sizeable base for potential renewal or win-back campaigns.

---

## 👤 Author

Built as a Power BI portfolio project demonstrating data modeling, DAX, and dashboard design for insurance/claims analytics.
