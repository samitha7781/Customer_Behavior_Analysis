# Customer Shopping Behavior Analysis

End-to-end analysis of 3,900 retail transactions using **Python, PostgreSQL and Power BI**: clean the data, answer business questions with SQL, and present the results in an interactive dashboard.

## Project Overview

The goal is to understand spending patterns, customer segments, product preferences and subscription behavior, and to turn the findings into practical business recommendations.

## Dataset

- **Rows:** 3,900 purchases
- **Columns:** 18
- **Customer demographics:** age, gender, location, subscription status
- **Purchase details:** item purchased, category, purchase amount, season, size, color
- **Shopping behavior:** discount applied, promo code used, previous purchases, frequency of purchases, review rating, shipping type, payment method
- **Data quality issue:** 37 missing values in `Review Rating`

Dataset source: *add link here*

## Tools Used

- **Python** (pandas, Jupyter Notebook) for cleaning and EDA
- **PostgreSQL** with SQLAlchemy and psycopg2 for storage
- **SQL** for business analysis
- **Power BI** for the dashboard

## Workflow

### 1. Data cleaning and feature engineering (Python)
- Loaded the data and explored it with `df.info()` and `df.describe()`
- Filled missing `Review Rating` values with the **median rating of each product category**
- Renamed columns to **snake_case**
- Created `age_group` by binning customer ages
- Created `purchase_frequency_days` from the purchase frequency data
- Confirmed `discount_applied` and `promo_code_used` matched in every row, then dropped `promo_code_used`
- Loaded the cleaned DataFrame into PostgreSQL

### 2. Business analysis (SQL)
1. Revenue by gender
2. High-spending customers who used discounts
3. Top 5 products by average rating
4. Average purchase amount: Standard vs Express shipping
5. Subscribers vs non-subscribers
6. Products most dependent on discounts
7. Customer segmentation: New, Returning, Loyal
8. Top 3 products per category
9. Repeat buyers and subscription status
10. Revenue by age group

### 3. Dashboard (Power BI)
An interactive dashboard with filters for subscription status, gender, category and shipping type. It shows the number of customers, average purchase amount, average review rating, and revenue and sales by category and age group.

## Key Findings

- Male customers generate about **68%** of revenue (157,890 vs 75,191).
- Only **27%** of customers subscribe, and subscribers spend about the same per purchase as non-subscribers (59.49 vs 59.87).
- Express orders average slightly more than Standard (60.48 vs 58.46).
- About **80%** of customers (3,116) fall in the Loyal segment.
- Young Adults bring in the most revenue (62,143), though all age groups are close.
- Hat, Sneakers, Coat, Sweater and Pants have the highest share of discounted purchases (47% to 50%).
- Top-rated products: Gloves, Sandals, Boots, Hat and Skirt.

## Business Recommendations

- **Boost subscriptions:** promote exclusive benefits for subscribers.
- **Loyalty programs:** reward repeat buyers to keep them in the Loyal segment.
- **Review discount policy:** balance sales boosts against margin.
- **Product positioning:** feature top-rated and best-selling products in campaigns.
- **Targeted marketing:** focus on high-revenue age groups and express-shipping users.

## Repository Structure

```
├── data/          # raw and cleaned datasets
├── notebooks/     # Python cleaning and EDA notebook
├── sql/           # PostgreSQL queries
├── dashboard/     # Power BI file and screenshots
└── README.md
```

## How to Run

1. Clone the repository and open the notebook in Jupyter.
2. Install the requirements: `pip install pandas sqlalchemy psycopg2-binary matplotlib seaborn`
3. Create a PostgreSQL database and enter your own connection details in the notebook.
4. Run the notebook to clean the data and load it into the database.
5. Run the queries in `sql/`, then open the Power BI file.
