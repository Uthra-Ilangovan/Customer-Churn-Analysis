# Customer-Churn-Analysis
# 📊 Customer Churn Analysis (Power BI Dashboard)

A comprehensive Customer Churn Analysis project built using Power BI to understand customer attrition patterns, identify key drivers of churn, and provide actionable insights to improve customer retention for a telecom company.

---

# 📌 Overview

This project analyzes customer churn behavior using a telecom dataset containing customer demographics, account information, and service subscriptions.

The goal is to:
- Understand why customers leave
- Measure churn rate and revenue impact
- Identify high-risk customer segments
- Support data-driven retention strategies

---

# 🧠 Key Concepts

## What is Churn?
Churn refers to customers stopping their relationship with a company or service, usually expressed as a percentage of total customers.

---

## What is Churn Rate?
Churn Rate (attrition rate) measures the percentage of customers lost over a specific period.

**Formula:**
Churn Rate = (Churned Customers / Total Customers) × 100%

---

## What is Customer Churn?
Customer churn is the natural process of losing customers due to:
- Poor service experience
- Pricing issues
- Competitive alternatives
- Changing customer needs

---

# 📦 Dataset

- File Type: Excel  
- Rows: 7,043  
- Columns: 23  

## Includes:

### 👤 Customer Demographics
- Gender  
- Senior Citizen / Young Citizen  
- Partner  
- Dependents  

### 💳 Account Information
- Tenure  
- Contract type  
- Payment method  
- Monthly charges  

### 📡 Services
- Phone service  
- Internet service  
- Online security  
- Streaming services  

---

# 🧹 Data Preparation

Data cleaning and transformation was done using Power Query in Power BI:

- Standardized data types  
- Renamed columns for consistency  
- Cleaned categorical values  
- Created calculated columns:
  - Citizenship Status (Senior / Young Citizen)  
  - Churn Status (Churned / Retained)  

---

# 📊 Measures Used (DAX)

```DAX
Total Customers = COUNT(ChurnDataset[CustomerID])
Churned Customers =
CALCULATE(
    COUNTA(ChurnDataset[CustomerID]),
    ChurnDataset[Churn] IN { "Yes" }
)

Retained Customers =
CALCULATE(
    COUNTA(ChurnDataset[CustomerID]),
    ChurnDataset[Churn] IN { "No" }
)
