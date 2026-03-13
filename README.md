# 🛍️ Customer Shopping Behavior Analysis

A data analysis project exploring customer shopping patterns, spending behavior, and product preferences using a dataset of **3,900 transactions** across multiple product categories.

---

## 📋 Project Overview

This project uncovers actionable insights into:
- Customer spending patterns by demographics
- Product category and item performance
- Subscription behavior and its impact on revenue
- Discount usage and its effect on purchases
- Customer segmentation (New, Returning, Loyal)

---

## 📁 Dataset

| Property | Details |
|---|---|
| **Rows** | 3,900 |
| **Columns** | 18 |
| **Missing Data** | 37 values in `Review Rating` column |

### Key Features

- **Demographics** — Age, Gender, Location, Subscription Status
- **Purchase Details** — Item Purchased, Category, Purchase Amount, Season, Size, Color
- **Behavior** — Discount Applied, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type

---

## 🧰 Tech Stack

| Tool | Purpose |
|---|---|
| **Python (pandas)** | Data cleaning & feature engineering |
| **PostgreSQL** | Structured SQL analysis |
| **Power BI** | Interactive dashboard |

---

## 🔧 Data Preprocessing (Python)

- **Missing Data** — Imputed `Review Rating` nulls using per-category median
- **Column Standardization** — Renamed all columns to `snake_case`
- **Feature Engineering**
  - `age_group` — binned customer ages into groups
  - `purchase_frequency_days` — derived from purchase timestamps
- **Redundancy Check** — Dropped `promo_code_used` (redundant with `discount_applied`)
- **Database Integration** — Loaded cleaned DataFrame into PostgreSQL for SQL analysis

---

## 📊 SQL Analysis (PostgreSQL)

Ten business queries were executed to answer key questions:

| # | Analysis | Key Finding |
|---|---|---|
| 1 | Revenue by Gender | Male: $157,890 — Female: $75,191 |
| 2 | High-Spending Discount Users | 839 customers used discounts yet spent above average |
| 3 | Top 5 Products by Rating | Gloves (3.86), Sandals (3.84), Boots (3.82), Hat (3.80), Skirt (3.78) |
| 4 | Shipping Type Comparison | Express avg: $60.48 — Standard avg: $58.46 |
| 5 | Subscribers vs Non-Subscribers | Avg spend nearly equal (~$59.49 vs ~$59.87) |
| 6 | Discount-Dependent Products | Hat (50%), Sneakers (49.66%), Coat (49.07%) |
| 7 | Customer Segmentation | Loyal: 3,116 — Returning: 701 — New: 83 |
| 8 | Top 3 Products per Category | Jewelry, Blouse, Sandals, Jacket lead their categories |
| 9 | Repeat Buyers & Subscriptions | 2,518 repeat buyers are non-subscribers |
| 10 | Revenue by Age Group | Young Adult: $62,143 — Middle-aged: $59,197 — Adult: $55,978 — Senior: $55,763 |

---

## 📈 Power BI Dashboard

An interactive dashboard was built with filters for:
- Subscription Status
- Gender
- Product Category
- Shipping Type

**Key KPIs displayed:** Total Customers (3.9K) · Average Purchase Amount ($59.76) · Average Review Rating (3.75)

---

## 💡 Business Recommendations

1. **Boost Subscriptions** — Only 27% of customers subscribe; promote exclusive subscriber benefits to grow this segment
2. **Customer Loyalty Programs** — Reward repeat buyers to convert them from Returning → Loyal
3. **Review Discount Policy** — ~50% of purchases for some products use discounts; balance promotional spend with margin control
4. **Product Positioning** — Highlight top-rated items (Gloves, Sandals, Boots) in marketing campaigns
5. **Targeted Marketing** — Focus on Young Adults (highest revenue group) and Express-shipping users (higher avg spend)

---

## 🗂️ Project Structure

```
├── data/
│   └── shopping_behavior.csv        # Raw dataset
├── notebooks/
│   └── eda_cleaning.ipynb           # Python EDA & preprocessing
├── sql/
│   └── analysis_queries.sql         # All 10 business SQL queries
├── dashboard/
│   └── customer_behavior.pbix       # Power BI dashboard file
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites
- Python 3.8+
- PostgreSQL
- Power BI Desktop

### Setup

```bash
# Clone the repository
git clone https://github.com/your-username/customer-shopping-behavior.git
cd customer-shopping-behavior

# Install Python dependencies
pip install pandas sqlalchemy psycopg2

# Run the preprocessing notebook
jupyter notebook notebooks/eda_cleaning.ipynb
```

> Configure your PostgreSQL connection string in the notebook before running the database integration step.

