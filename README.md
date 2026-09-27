# SpendDNA_Vedant
# 💳 SpendDNA — Personal Financial Intelligence

> *"Spotify Wrapped for your bank statement & UPI transactions."*

[![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![NumPy](https://img.shields.io/badge/NumPy-Numerical-013243?style=for-the-badge&logo=numpy&logoColor=white)](https://numpy.org/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557c?style=for-the-badge&logo=python&logoColor=white)](https://matplotlib.org/)

---

## 📌 Executive Summary

Every Indian student and working professional uses UPI multiple times a day, frequently wondering *"where did all my money go?"* **SpendDNA** decodes 6 months of raw, unformatted bank and UPI transaction exports to extract merchant patterns, categorize spending across 12 categories, detect anomalous transactions via statistical z-scores, and generate spending personality archetypes.

This tool builds a complete financial audit dashboard entirely using core Python, NumPy, Pandas, and Matplotlib—demonstrating raw analytical constraint discipline without relying on third-party APIs, machine learning, or automated profiling libraries.

---

## 🎨 Financial Intelligence Dashboard

![SpendDNA Dashboard](Priyanka_SpendDNA_Final_Dashboard.png)

---

## 🚀 Key Features

1. **Robust Multi-Format Transaction Parser**
   * Parses 4 mixed date formats (`DD/MM/YY`, `YYYY-MM-DD`, `DD-Mon-YY`, `DD Mon YYYY`) without day/month swapping errors.
   * Cleans mixed currency strings (e.g., `₹2,462`, `Rs. 1,200`, plain floats) into standardized numeric representations.
   * Standardizes transaction type variants (`DR`/`CR`, `Debit`/`Credit`) and drops exact duplicates.

2. **Merchant Normalization (Vendor Extractor)**
   * Maps dozens of raw string patterns to canonical merchant names (e.g., `BUNDL Tech`, `POS SWIGGY` $\rightarrow$ `Swiggy`).
   * Handles edge cases including P2P transfers, cash withdrawals, utility bills, and salary credits.

3. **12-Category Tagger & Time-of-Day Behavioral Profiling**
   * Categorizes spending into Food Delivery, Quick Commerce, E-commerce, Investments, Subscriptions, Transport, etc.
   * Extracts hourly transaction buckets to identify late-night order clusters (9 PM – 1 AM) vs. morning coffee runs (8 AM – 11 AM).

4. **Statistical Anomaly Detection (Z-Score)**
   * Detects unusual category-relative spending outliers using standard deviation distance ($z > 2.0$) computed entirely with Pandas/NumPy vector arithmetic.

5. **Spending Archetype Assignment**
   * Multi-condition engine that automatically detects financial behavioral personas such as **THE SHOPAHOLIC** and **THE YOLO SPENDER**.

---

## 📊 Key Analytics Overview

| Metric | Output Value | Financial Interpretation |
| :--- | :--- | :--- |
| **Total Credits** | `Rs. 509,774` | Monthly salary & income inflows |
| **Total Debits** | `Rs. 1,678,901` | Cumulative 6-month outflow |
| **Net Savings Rate** | `-229.3%` | Significant capital burn rate (~Rs. 1.94L/mo) |
| **Top Category** | **E-commerce** (36.0%) | Dominates wallet share (Rs. 603,877 total) |
| **Top Vendor** | **Amazon** (86 orders) | Highest individual spending destination (Rs. 328,530) |
| **Late-Night Spending** | **21%** | Food delivery orders occurring between 9 PM and 1 AM |

---

## 📄 Formatted Text Output

```text
==================================================================
 SpendDNA REPORT  -  RAHUL SHARMA
 6 months   -  1,310 transactions   -   Jan to Jun 2024
==================================================================

 EXECUTIVE SUMMARY
   Total credits     : Rs. 509,774
   Total debits      : Rs. 1,678,901
   Net change        : -Rs. 1,169,127    (overspending)
   Savings rate      : -229.3%       (BURNING SAVINGS)
   Transactions      : 1,310
   Unique vendors    : 38

 TOP CATEGORIES (% of debit total)
   E-commerce       #################  36.0%   Rs.  603,877
   Investments      #######            14.8%   Rs.  248,160
   Food Delivery    ####                9.5%   Rs.  159,667
   Restaurants      ###                 7.0%   Rs.  117,737
   Rent             ###                 6.4%   Rs.  108,000

 TOP VENDORS
   Amazon          Rs.  328,530    ( 86 orders)
   Zerodha         Rs.  218,511    ( 16 SIPs)
   Flipkart        Rs.  177,510    ( 47 orders)
   Rent            Rs.  108,000    (  6 orders)
   Swiggy          Rs.  104,351    (243 orders)

 TIME-OF-DAY PATTERNS
   Food Delivery peaks: 21:00 - 01:00  (21% of orders)
   Cafe peaks:          09:00 - 11:00  (morning runs)
   Quick Commerce:      evenly distributed

 MONTHLY TREND (Food Delivery)
   Jan  Rs. 23,692  #########
   Feb  Rs. 26,458  ##########
   Mar  Rs. 25,918  ##########
   Apr  Rs. 30,092  ############
   May  Rs. 26,598  ##########
   Jun  Rs. 26,909  ##########

 TOP ANOMALIES (3+ stddev from category mean)
   26 Jun - Amazon           Rs. 22,008   (z=4.1)
   07 Feb - Amazon           Rs. 21,986   (z=4.1)
   26 Feb - Local Restaurant Rs.  8,383   (z=3.9)

 RAHUL'S SPENDING ARCHETYPES
   -> THE SHOPAHOLIC            (36.0% on e-commerce)
   -> THE YOLO SPENDER          (savings rate -229%)
==================================================================
 KEY INSIGHTS
 1. Rahul is burning through his savings at Rs. 194,854 per month.
 2. 21% of his food-delivery spend happens after 9 PM,
    suggesting stress eating or single-living patterns.
 3. Investments are healthy, but discretionary spend dominates his wallet.
==================================================================

````
---

## 🛠️ Tech Stack & Technical Constraints

* Language: Python 3.11+

* Data Wrangling: pandas, numpy

* (Visualization: matplotlib (Dark Neon Card layout)

* Date Parsing: pd.to_datetime with mixed format detection

---

## Strict Constraint Discipline

* ❌ No Machine Learning Libraries (scikit-learn, scipy.stats) — Z-scores calculated manually.

* ❌ No Profiling Tools (pandas-profiling, sweetviz) — Analytics pipelines built from scratch.

* ❌ No Regex (re) — String cleaning executed strictly via standard string/Pandas methods.

---

## 📂 Repository Structure

├── rahul_transactions.csv              # Raw input transaction dataset

├── SpendDNA_Priyanka.ipynb             # Main Jupyter Notebook containing end-to-end analysis

├── Priyanka_SpendDNA_Final_Dashboard.png  # Generated dark-mode visual dashboard image

├── .gitignore                          # Configured to ignore personal data exports

└── README.md                           # Project documentation

---

## 💻 How to Run

1.**Clone the repository:**

Bash
````
git clone [https://github.com/](https://github.com/)<your-username>/SpendDNA.git
cd SpendDNA
````

2.**Install dependencies:**

Bash
````
pip install pandas numpy matplotlib
````

3.**Execute the analysis:**

Bash

Open SpendDNA_Vedant.ipynb in Jupyter Notebook, VS Code, or Google Colab and run all cells sequentially.

## 👤 Author

**Name: Vedant**

**Degree: Bachelor of Technology in Artificial Intelligence and Data Science**

**Institution: Savitribai Phule Pune University**







