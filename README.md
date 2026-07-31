# 📊 Churn & Revenue Impact Analysis

## 📌 TL;DR
- Built a full pipeline (SQLite → pandas → cleaned, merged dataset) and calculated **20+ KPIs** across customer, subscription, and support data
- Found an **overall churn rate of 28.6%**, with **monthly-contract users churning at 55.6%** — **6.7× higher** than annual-contract users (8.3%)
- Quantified the cost of inaction: at-risk customers represent **$73.94/mo in MRR exposure** and **$2,047 in projected CLTV erosion**

---

## 🎯 Problem
Subscription businesses don't just lose customers when they churn — they lose recurring revenue and future lifetime value. This project asks three questions of a sample OTT (streaming) subscription business:
- Who is churning, and how much variation is there across contract types and plans?
- What is that churn actually costing the business in revenue terms?
- What's one concrete action the business could take to reduce it?

---

## 🗂 Dataset
Data was provided as a SQLite database (`customer_churn.db`) with three relational tables:
- `db_customer` – demographics: name, country, state, gender, date of birth
- `db_subscription` – plan type, contract type, monthly charges, CLTV, churn score, cancellation info
- `db_support` – support complaints, escalations, CSAT scores

> **Note:** this is a small sample dataset (21 customers), used to demonstrate the analytical pipeline and methodology end to end. Findings illustrate the approach rather than a statistically robust business result.

---

## 🔍 Key Findings
**Churn is heavily concentrated in monthly contracts and lower-tier plans:**

| Segment | Churn rate |
|---|---|
| Monthly contract | 55.6% |
| Annual contract | 8.3% |
| Basic plan | 60.0% |
| Standard plan | 22.2% |
| Premium plan | 14.3% |

Monthly-contract customers churn **6.7× more often** than annual-contract customers — the single strongest predictor of churn found in this analysis.

**Revenue impact of at-risk customers** (elevated churn score, still active):
- **$73.94/mo** in monthly recurring revenue currently exposed
- **$2,047** in projected customer lifetime value at risk of erosion

---

## 📈 Tools & Libraries Used
- **Python** – data processing & analysis
- **Pandas** – data manipulation
- **NumPy** – numerical calculations
- **SQLite3** – source data extraction
- **Matplotlib & Seaborn** – data visualization
- **Jupyter Notebook** – analysis workflow

---

## 📊 Sample Insights
- Contract type and plan type stand out as the strongest churn indicators in the correlation analysis — consistent with the KPI findings above
- Premium-plan customers pay the most per month but churn the least, suggesting perceived value outweighs price sensitivity for retained users
- Annual-contract customers are consistently the lowest-risk segment across every cut of the data (plan type, state, and churn score)

---

## 🖼 Visualizations
- Time-series trend of monthly cancellations
- Bar charts for **churn rate by plan type** and **by state**
- Correlation heatmap across churn score, plan type, contract type, and escalations
- Pairplot across encoded churn features
- Faceted category plot: monthly charges by plan type, split by gender and churn risk
