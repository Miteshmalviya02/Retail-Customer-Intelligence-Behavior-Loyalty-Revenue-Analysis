# Retail Customer Intelligence — Behavior, Loyalty & Revenue Analysis
### Retail Consumer Study | 3,900 Customers | Python · SQL · Power BI

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Problem Statement](#problem-statement)
3. [Dashboard Preview](#Dashboard-Preview)
4. [Methodology](#methodology)
5. [Key Insights & Recommendations](#key-insights--recommendations)
6. [Detailed Insights](#detailed-insights)
7. [Recommendations](#recommendations)

---

## Project Overview

A leading retail company wanted to better understand its customers' shopping behavior to improve sales, customer satisfaction, and long-term loyalty. This project analyzes a dataset of **3,900 customers** across demographics, product categories, purchase patterns, and sales channels to answer one core business question:

> *"How can the company leverage consumer shopping data to identify trends, improve customer engagement, and optimize marketing and product strategies?"*

**Tools Used:** Python (Pandas) · MySQL · Power BI

---

## Problem Statement

The management team noticed changes in purchasing patterns and needed clarity on:

- Which demographics drive the most revenue
- Which product categories and items perform best
- Whether discounts actually drive purchase decisions
- What factors lead to repeat purchases and long-term loyalty
- Why loyal customers are not converting to subscriptions

---

## Dashboard Preview

<img width="1078" height="759" alt="image" src="https://github.com/user-attachments/assets/def6df00-0c67-43e0-829a-a1d4bd4d36c5" />

---
## Methodology

### End-to-End Project Flow

```
Raw CSV Data → Python (Cleaning & Feature Engineering) → MySQL (SQL Analysis) → Power BI (Dashboard)
```

### Step 1 — Python: Data Cleaning & Feature Engineering
- Loaded raw dataset of 3,900 customers with 18 columns
- Handled 37 missing values in `review_rating` by filling with **category-level median** (not overall median) to preserve category-specific rating patterns
- Discovered `discount_applied` and `promo_code_used` were **100% identical columns** — dropped the redundant column
- Created `age_group` column using `pd.qcut` — segmented customers into Young Adults, Adults, Middle Aged, and Senior
- Mapped `frequency_of_purchases` text values (Weekly, Monthly etc.) to **numeric days** for quantitative analysis
- Standardized all column names to lowercase with underscores
- Exported cleaned data as `customer_cleaned_data.csv`

### Step 2 — MySQL: SQL Analysis
- Pushed cleaned data from Python directly into MySQL using SQLAlchemy
- Wrote **10 business-focused SQL queries** using CTEs, window functions, subqueries, and aggregations
- Answered questions on revenue by gender, customer segmentation, discount behavior, subscription impact, and product performance

### Step 3 — Power BI: Dashboard
- Connected Power BI directly to the cleaned dataset
- Built an interactive dashboard with filters for Gender, Category, Subscription Status, and Shipping Type
- Visualized revenue by category, sales by age group, subscription breakdown, and KPI cards

---

## Key Insights & Recommendations

---

### Top Findings

- **Males generate 67.74% of total revenue** ($157,890) vs females at 32.26% ($75,191) — a 2x gap
- **80% of customers are Loyal** (3,116 with 10+ purchases) but only 1,053 are subscribed — biggest missed opportunity
- **2,518 repeat buyers are not subscribed** — loyal customers are not converting to the subscription program
- **Clothing dominates** with $104K revenue and 1,737 sales — Outerwear lags at just $19K
- **Hat, Sneakers & Coat have ~50% discount dependency** — nearly every 2nd purchase requires a discount
- **Young Adults lead revenue** at $62,143 (26.66%) but all age groups are remarkably balanced (23–26% each)
- Non-subscribers generate **$170K total revenue vs $62K for subscribers** — subscription program is underperforming

---

### Key Recommendations

- Launch a **loyalty-to-subscription conversion campaign** — 2,518 loyal non-subscribers are the highest ROI target
- **Redesign the subscription program** with exclusive perks, early access, or member-only discounts to add real value
- **Stop blanket discounting** on Hat, Sneakers & Coat — target discounts only to price-sensitive segments
- Invest more in **Clothing & Accessories** marketing — they drive 75%+ of total revenue
- **Investigate Outerwear underperformance** — low sales ($19K, 324 orders) needs a pricing or variety fix
- Run **female-targeted marketing campaigns** — 32% revenue share suggests an untapped growth segment
- All age groups spend equally — **do not narrow marketing to one age group**, keep campaigns broad

---

## Detailed Insights

### Q1 — Revenue by Gender
Males drive **67.74% of total revenue** ($157,890) compared to females at 32.26% ($75,191). While males dominate, females represent a significant and likely underserved segment worth targeting with dedicated campaigns.

### Q2 — Discount but High Spenders
A notable customer segment used discounts but still spent **above the average purchase amount of $59.76**. These are high-value buyers who respond to offers but do not need discounts to make a purchase — discounting to them is margin loss.

### Q3 — Product Review Ratings
Shirt (3.62), Jeans (3.65), and Blouse (3.68) are the lowest rated products. Hoodie and Pants top ratings at 3.72. Overall ratings are tightly clustered — no product stands out strongly positive or negative, suggesting a consistent but average product experience across the board.

### Q4 — Shipping Type vs Spend
Express shipping customers spend **$60.48 on average vs $58.46 for Standard** — a marginal $2 difference. Premium shipping users spend slightly more but the gap is not significant enough to use shipping type as a spend predictor.

### Q5 — Subscribers vs Non-Subscribers
Non-subscribers (2,847 customers) generate **$170,436 in total revenue** vs subscribers at $62,645. However, average spend is nearly identical — $59.87 (non-subscribers) vs $59.49 (subscribers). The revenue gap is driven by volume, not behavior — the subscription program is not increasing individual spend.

### Q6 — Discount Dependency by Product
Hat (50%), Sneakers (49.66%), Coat (49.07%), Sweater (48.17%), and Pants (47.37%) have the highest discount rates. Nearly **1 in 2 purchases of these products requires a discount** — a clear signal of pricing issues or customer price sensitivity for these items.

### Q7 — Customer Segmentation
**80% of customers are Loyal** (3,116 with 10+ purchases). Only 701 are Returning and just 83 are New customers. Strong retention but dangerously low new customer acquisition — the business is running on its existing base with minimal growth pipeline.

### Q8 — Top Products by Category
- **Accessories:** Jewelry (171), Sunglasses (161), Belt (161)
- **Clothing:** Blouse (171), Pants (171), Shirt (169)
- **Footwear:** Sandals (160), Shoes (150), Sneakers (145)
- **Outerwear:** Jacket (163), Coat (161)

### Q9 — Repeat Buyers & Subscription Gap
Of customers with more than 5 previous purchases, **2,518 are NOT subscribed** vs only 958 who are. The most loyal customers — who already trust and regularly buy from the brand — are not enrolled in the subscription program. This is the single biggest revenue gap in the entire dataset.

### Q10 — Revenue by Age Group
Young Adults lead at **$62,143 (26.66%)**, followed by Middle Aged at $59,197 (25.40%), Adults at $55,978 (24.02%), and Senior at $55,763 (23.92%). All four groups contribute almost equally — no single age segment dominates, making age-based targeting less effective than behavioral targeting.

---

## Recommendations

### 1. Fix the Subscription Gap — Highest Priority
3,116 loyal customers, only 1,053 subscribed. Convert even 20% of the 2,518 loyal non-subscribers and subscription revenue grows significantly. Offer exclusive member perks, early sale access, or a first-month free trial to drive sign-ups.

<img width="611" height="189" alt="image" src="https://github.com/user-attachments/assets/fdb30604-131d-40f8-bc93-ea953255acc7" />


### 2. Stop Blanket Discounting
Hat, Sneakers, and Coat are being discounted on nearly every other purchase. Identify which buyers genuinely need a discount to convert vs which would buy anyway — and stop discounting the latter. Protect margins without losing sales.

<img width="433" height="519" alt="image" src="https://github.com/user-attachments/assets/53aa5bee-8a5c-4f21-8b1b-2f9078b381a9" />


### 3. Invest in Female-Targeted Marketing
Females contribute 32% of revenue but are likely underrepresented in current marketing. A dedicated campaign targeting female shopping patterns (preferred categories, payment methods, seasonal trends) could meaningfully shift this ratio.

### 4. Fix New Customer Acquisition
Only 83 new customers in the dataset vs 3,116 loyal ones. The business is over-relying on its existing base. Invest in top-of-funnel marketing — referral programs, social ads, influencer partnerships — to build a growth pipeline.

### 5. Double Down on Clothing & Accessories
These two categories drive 75%+ of revenue. Prioritize inventory depth, seasonal launches, and targeted promotions here before expanding into weaker categories like Outerwear.

### 6. Investigate Outerwear
$19K revenue and 324 orders is significantly below all other categories. Determine if this is a pricing, variety, seasonality, or visibility problem — and either fix it or reallocate resources to stronger categories.
