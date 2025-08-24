# [Myntra Online Retail Customer Segmentation](./notebooks/segmentation.ipynb)

## 📖 Project Overview

This repository implements an end-to-end unsupervised machine-learning pipeline to segment Myntra Gifts Ltd.’s UK e-commerce customers (Dec 2009–Dec 2011). By grouping customers based on **Recency, Frequency, and Monetary (RFM)** behavior, we deliver actionable insights for targeted marketing, optimized pricing, and smarter inventory planning.

We applied **K-Means clustering** on RFM features and identified **three distinct customer segments**:

* **Cluster 0 – High-Value Loyal Customers**
* **Cluster 1 – At-Risk/Lapsed Customers**
* **Cluster 2 – Moderate/Occasional Buyers**

These segments highlight clear behavioral differences in purchase recency, order frequency, and spending, enabling **personalized marketing, retention strategies, and demand-driven stocking decisions**.

---

## 🎯 Problem Statement

Myntra Gifts Ltd. faces challenges in understanding its diverse customer base, leading to:

* untargeted marketing spend
* inefficient inventory stocking
* limited retention of high-value customers

The goal is to leverage transactional data to uncover **customer segments** that can power:

* retention strategies,
* reactivation campaigns, and
* data-driven product stocking.

---

## 🎯 Key Objectives

* Identify distinct **customer personas** via clustering
* Reveal **purchasing trends and product performance**
* Enable **targeted retention, upsell, and win-back campaigns**
* Improve **inventory efficiency and pricing decisions**

---

## 🔧 Installation & Setup

1. Clone this repository

```bash
git clone https://github.com/pandey-rakshit/myntra-gifts-segmentation.git
```

2. Go to the project directory

```bash
cd myntra-gifts-segmentation
```

3. Create & activate a virtual environment

```bash
python3 -m venv venv
source venv/bin/activate
```

4. Install all required libraries

```bash
pip install -r requirements.txt
```

5. Run the notebook

* `notebooks/segmentation.ipynb`

---

## 🛠️ Methodology

* **Data Cleaning**

  * Removed duplicates (≈5.2k rows)
  * Excluded missing CustomerIDs (\~25% rows)
  * Imputed missing product descriptions as *“Unknown”*
  * Removed negative `Quantity` & `UnitPrice` (returns)

* **Feature Engineering**

  * Built **RFM metrics** per customer
  * Applied log transformation + scaling

* **Clustering**

  * Used **K-Means** with elbow + silhouette analysis → optimal **k=3**
  * Evaluated clusters on RFM distribution + PCA visualization

---

## 📊 Results

We identified **3 distinct customer clusters**:

| Cluster | Segment                      | Characteristics                                | Share of Customers | Recommended Action                              |
| ------- | ---------------------------- | ---------------------------------------------- | ------------------ | ----------------------------------------------- |
| **0**   | High-Value Loyal Customers   | Recent, frequent, highest spend                | \~28%              | Retain with loyalty programs, upsell, VIP perks |
| **1**   | At-Risk / Lapsed Customers   | Long recency, very low spend & frequency       | \~21%              | Win-back campaigns, personalized discounts      |
| **2**   | Moderate / Occasional Buyers | Moderate recency & spend, low-medium frequency | \~44%              | Targeted promotions to increase repeat orders   |

---

## 📊 Key Findings (Business-Friendly Summary)

**Cluster 0 – High-Value Loyal Customers (\~28%)**

* Recent purchasers, high order frequency, highest spend.
* Generate majority of revenue.
* **Action:** Retention via VIP perks, upsell opportunities.

**Cluster 1 – At-Risk / Lapsed Customers (\~21%)**

* Haven’t purchased in a long time, very low frequency & spend.
* High churn risk, least engaged.
* **Action:** Reactivation with win-back offers, personalized campaigns.

**Cluster 2 – Moderate / Occasional Buyers (\~44%)**

* Average recency, moderate spend, low-medium frequency.
* Middle segment, strong potential if engaged.
* **Action:** Targeted promotions & engagement campaigns.

---

## 💡 Business Insights

* **Revenue Distribution:** High-value customers (Cluster 0) contribute disproportionately (\~60%+ revenue).
* **Purchasing Trends:** Seasonal giftware SKUs dominate across segments.
* **Product Behavior:** Loyal customers buy more diverse SKUs; lapsed buyers purchase rarely.
* **Pricing Power:** High-value customers tolerate higher basket sizes.
* **Inventory Optimization:** Segment-wise demand helps avoid overstocking for low-value cohorts.
