# 📊 Dashboard Design Rationale — Telecom Customer Churn Analysis

## Screenshot of the Dashboard
![Dashboard Screenshot](https://github.com/SruthiSivakumar/Visualizations/blob/main/Dashboard%20Screengrab.png))


##  Data used:
https://www.kaggle.com/datasets/abdullah0a/telecom-customer-churn-insights-for-analysis 
---

## 🎯 Objective
The dashboard was built to let a viewer explore which customer characteristics are associated with churn at a glance and help make data-driven decisions on retention periodically. It is designed to be easily perused by various teams during their strategy and monthly KPI discussions.

The design follows a **top-down structure**:  
- Title  
- Filters  
- Topline metrics  
- Diagnostic charts led by the strongest driver  
- Supporting detail and summary tables  

---

## 🧩 Structure and Layout Choices
- **Filter panel** (Age Group, Tenure Cohort, Gender, Contract Type, Internet Service, Tech Support Availability, Churn status) sits directly under the title.  
- All charts share these slicers and cross-filter natively in Power BI.  
- **Top row of cards**: customer count, churn count, churn rate, tenure, monthly charges, and LTV measures.  

---

## 🔄 Interactions
- **Potential Lost LTV** card turns **red** if greater than Active LTV, **green** if less.  
- **Churn rate** shown in gradient: green → yellow → red (0%–50%–100%).  
- Clicking any data point filters all other visuals.  

---

## 📈 Chart-Level Choices
- **Churn % by Contract Type & Tech Support**: placed top-left as strongest finding.  
- **Donut charts**: Male/Female churn split side by side for immediate comparison.  
- **Potential Churn LTV vs Active LTV**: stacked bar for value at risk.  
- **Avg Monthly Charges by Tenure**: line chart showing price sensitivity.  
- **Churn % by Internet Service**: combo chart pairing churn rate with Potential Lost LTV.  
- **Age Group × Tenure Cohort heatmap**: highlights churn concentration.  
- **Total Customers by Tenure Cohort and Churn**: area chart showing spread across cohorts.  

---

## 💰 LTV Methodology
- **Active LTV** = Tenure × Monthly Charges  
- **Potential Churn LTV** = Average Active Tenure × Monthly Charges  
- **Potential Lost LTV** = Potential Churn LTV – Sum of Total Charges for Churn  

---

## ⚠️ Next Steps
- Extend price-sensitivity view into churn-rate-by-charge-band chart.  
- Add summary callout stating top driver (Contract type & Tech Support).  
- Incorporate predictive elements to flag potential churners.  
