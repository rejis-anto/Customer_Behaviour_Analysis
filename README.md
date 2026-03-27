# 🛍️ Customer Shopping Behavior Analysis

> An end-to-end data analytics project analyzing 3,900 retail transactions to uncover insights on customer spending patterns, product preferences, segmentation, and subscription behavior.

---

## 🧰 Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)

---

## 📌 Project Overview

This project follows a complete data analytics pipeline:

1. **Data Cleaning & EDA** — Python & Pandas in Jupyter Notebook
2. **Feature Engineering** — Age grouping, frequency derivation, redundancy removal
3. **Database Integration** — Loaded cleaned data into MySQL via SQLAlchemy
4. **SQL Analysis** — 10 business queries to answer key retail questions
5. **Dashboard** — Interactive Power BI dashboard with slicers and KPI cards

---

## 📂 Repository Structure

```
customer-shopping-behavior-analysis/
│
├── data/
│   └── customer_shopping_behavior.csv        # Raw dataset (3,900 records, 18 features)
│
├── notebooks/
│   └── Customer_behaviour_analysis.ipynb     # Full EDA + MySQL integration notebook
│
├── dashboard/
│   └── customer_behaviour_analysis_dashboard.pbix  # Power BI dashboard file
│
├── report/
│   └── Customer_Shopping_Behavior_Analysis_Report.docx  # Full project report
│
└── README.md
```

---

## 📊 Dataset Summary

| Attribute | Details |
|-----------|---------|
| Total Records | 3,900 transactions |
| Total Features | 18 columns |
| Missing Data | 37 values in `review_rating` (imputed using category median) |
| Age Range | 18 – 70 years |
| Purchase Amount | $20 – $100 (Mean: $59.76) |
| Avg. Review Rating | 3.75 / 5.0 |

**Feature Groups:**
- **Demographics** — Age, Gender, Location, Subscription Status
- **Purchase Details** — Item, Category, Amount, Season, Size, Color, Shipping Type
- **Behavior** — Discount Applied, Previous Purchases, Frequency, Review Rating, Payment Method

---

## 🔬 Exploratory Data Analysis (Python)

Performed in `Customer_behaviour_analysis.ipynb`:

- ✅ Loaded dataset using `pandas.read_csv()`
- ✅ Inspected structure with `df.info()` and `df.describe()`
- ✅ Imputed 37 missing `review_rating` values using **per-category median**
- ✅ Renamed all columns to `snake_case` for SQL compatibility
- ✅ Engineered `age_group` column (Young Adult / Adult / Middle-aged / Senior)
- ✅ Engineered `purchase_frequency_days` from purchase frequency data
- ✅ Dropped redundant `promo_code_used` column (fully correlated with `discount_applied`)
- ✅ Exported cleaned DataFrame to MySQL using `SQLAlchemy` + `pymysql`

---

## 🗄️ SQL Analysis (MySQL)

10 business queries executed in MySQL on the `customer_behaviour` database:

| # | Query | Key Finding |
|---|-------|-------------|
| 1 | Revenue by Gender | Males generate ~68% of total revenue ($157,890 vs $75,191) |
| 2 | High-Spending Discount Users | 839 discount users still spent above average ($59.76) |
| 3 | Top 5 Products by Rating | Gloves (3.86), Sandals (3.84), Boots (3.82) |
| 4 | Shipping Type Comparison | Express ($60.48) vs Standard ($58.46) avg spend |
| 5 | Subscribers vs Non-Subscribers | Similar avg spend (~$59.49 vs $59.87) |
| 6 | Discount-Dependent Products | Hat (50%), Sneakers (49.66%), Coat (49.07%) |
| 7 | Customer Segmentation | Loyal: 3,116 — Returning: 701 — New: 83 |
| 8 | Top 3 Products per Category | Jewelry, Blouse, Sandals, Jacket lead each category |
| 9 | Repeat Buyers & Subscriptions | 2,518 repeat buyers are still non-subscribers |
| 10 | Revenue by Age Group | Young Adults top revenue at $62,143 |

---

## 📈 Power BI Dashboard

The dashboard (`customer_behaviour_analysis_dashboard.pbix`) includes:

**KPI Cards**
- 👥 Total Customers: **3,900**
- 💰 Avg Purchase Amount: **$59.76**
- ⭐ Avg Review Rating: **3.75**

**Visuals**
- Subscription Status — Donut Chart (27% Yes / 73% No)
- Revenue by Category — Bar Chart
- Sales by Category — Bar Chart
- Revenue by Age Group — Horizontal Bar Chart
- Sales by Age Group — Horizontal Bar Chart

**Slicers (Filters)**
- Subscription Status, Gender, Category, Shipping Type

---

## 💡 Key Findings

- 📌 **80% of customers are Loyal** (3,116 out of 3,900) — very high retention
- 📌 **Only 27% are subscribers** despite the majority being repeat buyers — a major conversion opportunity
- 📌 **Young Adults (18–30)** are the highest revenue-generating age group at $62,143
- 📌 **Male customers** account for ~68% of total revenue
- 📌 **Hat, Sneakers, and Coat** have ~50% discount dependency — margin risk
- 📌 **Express shipping users** spend more per transaction than standard users

---

## 🚀 Business Recommendations

| Recommendation | Action |
|----------------|--------|
| 📣 Boost Subscriptions | Introduce exclusive subscriber benefits to convert 73% non-subscribers |
| 🎯 Target Young Adults | Increase marketing budget on platforms used by 18–30 age group |
| 🏷️ Review Discount Policy | Cap discount rates on high-dependency products (Hat, Sneakers, Coat) |
| 🏆 Launch Loyalty Program | Introduce tiered rewards (Bronze/Silver/Gold) to deepen engagement |
| 🌟 Spotlight Top Products | Feature Gloves, Sandals, and Boots in campaigns based on high ratings |
| 🚚 Upsell Express Shipping | Prompt express shipping upgrades at checkout to raise average order value |
| 👩 Target Female Customers | Create gender-specific bundles to grow female customer revenue share |

---

## ▶️ How to Run

### Prerequisites
```bash
pip install pandas  sqlalchemy pymysql jupyter 
```

### Steps
1. Clone the repository
```bash
git clone https://github.com/your-username/customer-shopping-behavior-analysis.git
cd customer-shopping-behavior-analysis
```

2. Launch Jupyter Notebook
```bash
jupyter notebook notebooks/Customer_behaviour_analysis.ipynb
```

3. Set up MySQL — update the connection string in the notebook with your credentials:
```python
engine = create_engine("mysql+pymysql://<username>:<password>@localhost:3306/customer_behaviour")
```

4. Open the Power BI dashboard
```
dashboard/customer_behaviour_analysis_dashboard.pbix
```
> Requires Power BI Desktop (free download from Microsoft)

---

## 👤 Author

REJIS ANTO.M

Aspiring Data Analyst

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/rejisanto/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/rejis-anto/)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
