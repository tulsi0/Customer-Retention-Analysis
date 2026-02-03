#  Customer Retention & Revenue Cohort Analysis

##  Project Overview
This project performs an **end-to-end customer retention, churn, and revenue analysis** using real-world e-commerce transaction data. The analysis focuses on understanding **customer lifecycle behavior**, identifying **early churn**, and uncovering **high-value customer segments** through cohort analysis.

---

##  Business Objectives
- Analyze **customer retention** using cohort analysis  
- Measure **first-month churn** to identify early drop-offs  
- Compare **customer retention vs revenue retention**  
- Identify and analyze **wholesale vs retail customers**  
- Translate analytical results into **actionable business insights**

---

##  Dataset
- **Dataset:** Online Retail II  
- **Business Type:** UK-based non-store online retail  
- **Time Period:** December 2009 – December 2011  
- **Records:** ~500,000 transactions  

### Key Columns
- `InvoiceNo` – Invoice identifier  
- `CustomerID` – Unique customer identifier  
- `InvoiceDate` – Transaction timestamp  
- `Quantity` – Units purchased  
- `UnitPrice` – Price per unit  
- `Country` – Customer location  

---

##  Data Cleaning & Preparation
Real-world data issues were handled carefully:
- Removed **cancelled invoices**
- Dropped records with **missing CustomerID**
- Filtered **invalid quantities and prices**
- Resolved **mixed date formats (UK & US)**
- Removed **exact duplicate transactions**
- Created derived features:
  - `Revenue`
  - `OrderMonth`
  - `CohortMonth`
  - `CohortIndex`

---

##  Analysis Performed

### 1️ Customer Cohort Retention
- Customers grouped by **first purchase month**
- Retention tracked across subsequent months
- Visualized using a **cohort heatmap**

**Insight:**  
Customer retention drops sharply after the first month, then stabilizes among long-term customers.

---

### 2️ First-Month Churn Analysis
- Identified customers who never returned after their first purchase
- Calculated overall and cohort-level churn rates

**Insight:**  
~37% of customers churn after the first month, while some cohorts show exceptionally strong early retention.

---

### 3️ Revenue Retention Analysis
- Measured revenue retention instead of customer count
- Compared revenue behavior across cohorts

**Insight:**  
Revenue retention declines more slowly than customer retention, indicating that a smaller group of high-value customers drives long-term revenue.

---

### 4️ Wholesale vs Retail Customer Analysis
Since customer type was not explicitly available, a **proxy rule** was applied:
- Customers purchasing **≥ 50 units in a single order** were classified as **Wholesale**

#### Segment Comparison

| Metric | Retail | Wholesale |
|------|------|------|
| Customers | ~2,971 | ~1,367 |
| Total Revenue | ~2.6M | ~6.3M |
| Avg Order Value | ~13 | ~32 |

**Insight:**  
Wholesale customers represent a smaller segment but contribute **~70% of total revenue**.

---

## 💡 Business Recommendations
- Improve **early engagement within the first 30 days** to reduce churn  
- Prioritize **high-value and wholesale customers** with loyalty or contract-based incentives  
- Use **revenue retention** alongside customer retention for better performance evaluation  
- Apply customer segmentation for **targeted marketing strategies**

---

##  Tools & Technologies
- **Python:** Pandas, NumPy  
- **Visualization:** Matplotlib, Seaborn  
- **Environment:** Jupyter Notebook  

---

## 📁 Project Structure

customer-retention-analysis/
│
├── data/
│ └── online_retail_II.csv
├── notebooks/
│ └── cohort_analysis.ipynb
├── outputs/
│ └── retention_heatmap.png
└── README.md
