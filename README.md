# Digital-Transactions-Dashboard

### Dashboard Link :https://app.powerbi.com/groups/me/reports/33861ffd-a88b-4b6c-bca7-316e1698c413/63c58641ac93052a1b7c?experience=power-bi&bookmarkGuid=effd0bb304d5a8a92999

## Problem Statement

This dashboard helps analyze digital/UPI payment transactions to understand customer spending behavior, transaction trends, and account balance movement over time. It allows filtering transactions by bank, city, device type, gender, age group, merchant, payment method, purpose, and transaction type, making it easy to drill into specific customer segments or transaction patterns.

The dashboard tracks how transaction volume (Amount) and remaining account balance change over time, helping spot spending trends, peak transaction periods, and balance fluctuations at a monthly/yearly level. A detailed pivot table view also allows transaction-level inspection by city and currency.

### Steps followed

- Step 1: Loaded transaction data into Power BI Desktop. The data uses a single flat **DATA** table containing all transaction, customer, and merchant details — no separate dimension tables or relationships were required for this dataset.
- Step 2: Built a `Date Hierarchy` on `TransactionDate` (Year → Quarter → Month → Day) to support drill-down trend analysis.
- Step 3: Created a calculated column `Age Groups` to bucket customers by age for segment-level analysis.
- Step 4: Added 10 slicers to **Page 1** and **Page 2** for interactive filtering: Bank Name Sent, Bank Name Received, City, Device Type, Gender, Age Groups, Merchant Name, Payment Method, Purpose, and Transaction Type.
- Step 5: Built **Page 1** with two bookmark-toggled chart pairs:
  - **Transaction by year** — line chart and column chart showing `Amount` over `TransactionDate`
  - **Balance by month** — line chart and column chart showing `RemainingBalance` over `TransactionDate`
  
  A bookmark navigator was added to let users switch between line and column chart views for each metric.
- Step 6: Built **Page 2** with a detailed pivot table breaking down `Amount`, `City`, `Currency`, `RemainingBalance`, and `TransactionDate` for granular, transaction-level exploration.
- Step 7: The report was then published to Power BI Service.

## Data Model

A single table, **DATA**, containing the following fields:

| Field | Description |
|---|---|
| `TransactionID` | Unique transaction identifier |
| `TransactionDate` | Date of transaction (with Year/Quarter/Month/Day hierarchy) |
| `TransactionTime.2` | Time of transaction |
| `TransactionType` | Type of transaction (e.g., transfer, payment) |
| `Amount` | Transaction amount |
| `Currency` | Currency of the transaction |
| `RemainingBalance` | Account balance remaining after the transaction |
| `Status` | Transaction status (e.g., success/failed/pending) |
| `CustomerAccountNumber` | Customer's account number |
| `CustomerAge` | Customer's age |
| `Age Groups` | Calculated column bucketing customers by age range |
| `Gender` | Customer gender |
| `City` | Customer/transaction city |
| `DeviceType` | Device used to make the transaction |
| `BankNameSent` | Sending bank |
| `BankNameReceived` | Receiving bank |
| `MerchantAccountNumber` | Merchant's account number |
| `MerchantName` | Merchant name |
| `PaymentMethod` | Method used for payment |
| `PaymentMode` | Mode of payment |
| `Purpose` | Purpose of the transaction |

> No DAX measures were used in this project — all visuals are built directly off the raw and calculated columns in the DATA table.

# Report Pages / Snapshots



## Page 1 — Transaction & Balance Trends
![Page 1](https://github.com/user-attachments/assets/b99b1611-338d-4ccc-b7fa-099c4de33f6a)

## Page 2 — Detailed Transaction Table
![Page 2](https://github.com/user-attachments/assets/e08fabaa-f552-48c3-9b7e-9feada710872)

# Insights

A two-page report was created in Power BI Desktop and published to Power BI Service.

The following can be explored through the dashboard :

### [1] Transaction Trends
- The **Transaction by year** chart on Page 1 shows how total transaction amount changes over time, helping identify peak spending periods.

### [2] Balance Trends
- The **Balance by month** chart tracks how remaining account balance moves over time, useful for spotting cash flow patterns.

### [3] Segment-Level Analysis
- Slicers for Age Groups, Gender, City, Device Type, and Payment Method allow quick comparison of transaction behavior across different customer segments.

### [4] Bank & Merchant Flow
- Bank Name Sent/Received and Merchant Name slicers help trace which banks and merchants are most active in the dataset.

### [5] Detailed Drill-Down
- The pivot table on Page 2 supports city- and currency-level transaction inspection for deeper analysis.

---

## Tools & Technologies
- Power BI Desktop
- Power Query
- Power BI Service

## Getting Started
1. Clone this repository
2. Open `Project_3.pbix` in [Power BI Desktop](https://powerbi.microsoft.com/desktop/)
3. If using a live data connection, update credentials under **Transform Data → Data Source Settings**
4. Refresh data and explore

