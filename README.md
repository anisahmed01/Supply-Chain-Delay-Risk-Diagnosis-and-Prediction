# 🚚 End-to-End Supply Chain Analysis  
### Diagnosing a systemic delivery failure impacting $2.1M in profit using EDA + Machine Learning

---

## 📌 Problem Statement  
A global e-commerce business is facing a **critical operational breakdown**:

- **54.71% of orders are delivered late**
- Customer trust is declining  
- **$2.1M profit is at risk due to delivery delays**

The challenge is not just identifying delays — but understanding **why delays happen at scale** and **how to prevent them before dispatch**.

---

## 🎯 Objectives  

- Quantify **financial impact of delayed deliveries**
- Identify **root cause of operational bottlenecks**
- Analyze delay patterns across **time, region, and shipping modes**
- Build a **predictive model to flag high-risk orders before shipment**

---

## 📊 Dataset Overview  

- **172,765 orders** (2015–2018)  
- Key features:
  - Shipping Mode  
  - Order & Delivery Dates  
  - Customer Segment  
  - Region  
  - Department  
  - Payment Type


## 🗄️ Dataset

The dataset used in this project is sourced from Kaggle.

- **Source:** [DataCo Supply Chain Dataset](https://www.kaggle.com/datasets/saicharankomati/dataco-supply-chain-dataset)
- **Provider:** Kaggle — saicharankomati

> 📎 Click the link above to access and download the original dataset.
---

## 🔍 Key Insights  

### 1. System-Wide Failure (Not Localized)  
- Delay rate is consistent across:
  - Regions: **55–59%**
  - Customer Segments: **54–55%**  

➡️ Not a warehouse or customer issue — **company-wide failure**

---

### 2. Shipping Mode is the Root Bottleneck  
- **First Class → 100% delayed**  
- **Second Class → 79.8% delayed**  

➡️ Premium shipping performs worse than standard  

---

### 3. Root Cause: Business Logic Failure  
- ERP promises **1-day delivery (First Class)**  
- Actual processing time = **2 days (constant)**  

➡️ Impossible SLA → **system design flaw, not execution issue**

---

### 4. Profit Impact is a Volume Problem  
- Avg profit/order ≈ **$22 (stable)**  
- Loss driven by:
  - Too many delayed orders  
  - Not severity of delay  

➡️ Fix = reduce delay volume  

---

### 5. Time-Based Patterns  
- Peak months: **Aug, Sep, Dec**  
- Peak delay hour: **9 PM (57.1%)**  

➡️ Likely missing carrier cutoff  

---

## 🤖 Machine Learning Model  

**Model:** Random Forest Classifier  
**Technique:** SMOTE (class imbalance handling)

| Metric | Score |
|-------|------|
| Accuracy | 74% |
| Precision (Late Orders) | 79% |
| Recall | 75% |

### Interpretation  
- When model predicts "Late" → **80% accuracy**  
- Identifies **75% of risky orders before dispatch**  

➡️ Suitable for **real-time operational use**

---

## 💡 Business Recommendations  

### 🔴 Critical  
- Fix First Class SLA → change **1 day → 2–3 days**  
➡️ Eliminates 100% failure segment  

---

### 🟠 High  
- Deploy ML model into **Order Management System (OMS)**  
➡️ Prioritize high-risk orders  

---

### 🟡 Medium  
- Review **carrier performance (First & Second Class)**  
- Increase staffing for **9 PM surge**

---

## 📈 Expected Impact  

- Reduce late deliveries: **54.71% → <30%**  
- Protect **$2.1M profit**  
- Improve **customer trust**

---

## 🛠️ Tech Stack  

- Python (Pandas, NumPy)  
- Data Visualization (Matplotlib, Seaborn)  
- Machine Learning (Scikit-learn, Random Forest)  
- Feature Engineering & SMOTE  

---

## 📂 Project Structure  
```
├── data link kaggle
├── notebook.ipynb
├── report PDF
│ └── Supply-Chain-Delay-Risk-Diagnosis-and-Prediction.pdf
├── README.md
```
---
## 🔑 Key Takeaways  

- **Systemic Failure > Local Issue**  
  Delay rates are consistent across regions and customer segments → confirms a **company-wide operational flaw**, not isolated inefficiencies  

- **Shipping Logic is the Root Cause**  
  First Class shows **100% delay rate** due to an **impossible 1-day SLA vs 2-day processing reality**  

- **Business Logic Misalignment (Not Execution Failure)**  
  The issue stems from **ERP design**, not workforce or warehouse performance  

- **Profit Risk is Driven by Volume, Not Severity**  
  Avg profit/order remains stable (~$22) → losses occur because **too many orders are delayed**, not because delays are extreme  

- **Time-Based Operational Gaps Exist**  
  Peak delays at **9 PM orders** indicate **carrier cutoff and staffing inefficiencies**  

- **Predictive Model Enables Proactive Operations**  
  Random Forest model identifies **high-risk orders with ~79% precision**, enabling **pre-dispatch intervention**  

- **Single Fix Can Eliminate Major Failure Segment**  
  Correcting First Class SLA (1 → 2–3 days) directly addresses the **largest source of delays**

---

## 📊 Dashboard

![Dashboard 1](https://raw.githubusercontent.com/anisahmed01/Supply-Chain-Delay-Risk-Diagnosis-and-Prediction/main/Dashboard%20Images/Screenshot%202026-05-01%20155440.png)
![Dashboard 2](https://raw.githubusercontent.com/anisahmed01/Supply-Chain-Delay-Risk-Diagnosis-and-Prediction/main/Dashboard%20Images/Screenshot%202026-05-01%20155241.png)
![Dashboard 3](https://raw.githubusercontent.com/anisahmed01/Supply-Chain-Delay-Risk-Diagnosis-and-Prediction/main/Dashboard%20Images/Screenshot%202026-05-01%20155656.png)

---

## 👤 Author
**Anis Ahmed**

---
