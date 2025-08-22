# [Myntra Online Retail Customer Segmentation](./notebooks/segmentation.ipynb)


## 📖 Project Overview

This repository implements an end‑to‑end unsupervised machine‑learning pipeline to segment Myntra Gifts Ltd.’s UK e‑commerce customers (Dec 2009–Dec 2011). By grouping customers based on Recency, Frequency, and Monetary (RFM) behavior, we deliver actionable insights for targeted marketing, optimized pricing, and inventory planning.

> We applied **unsupervised machine learning** to segment Myntra Gifts Ltd.’s UK online retail customers (Dec 2009–2011). Using RFM (Recency, Frequency, Monetary) features, we identified **three distinct customer segments**: High-Value Loyal Customers, Moderate Customers, and At-Risk/Lapsed Customers. These segments reveal actionable differences in purchasing behavior, product affinity, and geographic spread, enabling **personalized marketing, optimized pricing strategies, and more efficient inventory management**.

---

## 🎯 Problem Statement

> Myntra Gifts Ltd. faces challenges in understanding its diverse customer base, leading to untargeted marketing, inefficient inventory management, and suboptimal pricing. The goal is to analyze transactional data to uncover **customer segments** that can support retention strategies, reactivation campaigns, and product-level stocking decisions.

---

## 🎯 Key Objectives

-   Identify distinct customer segments
-   Reveal purchasing trends and product performance
-   Inform targeted retention, upsell, and reactivation strategies
-   Improve inventory efficiency and pricing decision

---

## 🔧 Installation & Setup

1. clone this repository

```bash
    git clone https://github.com/pandey-rakshit/myntra-gifts-segmentation.git
```

2. Go to the project directory

```bash
    cd myntra-gifts-segmentation
```

3. create & activate environment

```bash
    python3 -m venv venv
    source venv/bin/activate
```

4. Install all the required libraries

```bash
    pip install -r requirements.txt
```

5. Execute file

-   `notebooks/segmentation.ipynb`


## 🛠️ Methodology

* **Data Cleaning**:

  * Removed duplicates (5,268 rows)
  * Excluded missing CustomerIDs (\~25% of rows)
  * Imputed missing product descriptions as *“Unknown”*
  * Filtered out negative `Quantity` and `UnitPrice` (returns)
* **Feature Engineering**:

  * Built **RFM metrics** per customer
  * Scaled features and applied log transformations
* **Clustering**:

  * Used **K-Means** with elbow + silhouette analysis → optimal k=3
  * Evaluated clusters on RFM metrics, product preferences, and geography

---

## 📊 Results

-   **3 Customer Segments** identified (High‑Value Loyal, Moderate, At‑Risk/Lapsed)
-   **High‑Value Loyal** customers (≈21%) generate ~60% of revenue
-   **Recommendations**:
    -   Retention & upsell for Cluster 1
    -   Targeted promotions for Cluster 0
    -   Win‑back campaigns for Cluster 2

Outputs (CSV + serialized model) are saved under `data/` and `models/` respectively.

---

## 📊 Key Findings (your clusters, simplified for business readers)

**Cluster 1 – High-Value Loyal Customers (922 customers)**

* Recent purchasers, high frequency, highest spend (\~₹7,255 avg).
* Most revenue-generating group, highly engaged.
* **Action:** Retain via loyalty perks, upselling, VIP programs.

**Cluster 0 – Moderate Customers (2,384 customers)**

* Average recency (\~50 days), moderate spend.
* Middle segment, good upsell opportunity.
* **Action:** Targeted promotions to encourage repeat purchases.

**Cluster 2 – At-Risk/Lapsed Customers (1,032 customers)**

* Long recency (~~250 days), lowest spend (~~₹404 avg).
* High churn risk, least engaged.
* **Action:** Win-back campaigns, personalized discounts.

---

## 💡 Business Insights

* **Purchasing Trends:** Seasonal giftware SKUs dominate across all segments.
* **Product Performance:** Core SKUs (e.g., T-Light Holders, Lanterns) drive the bulk of revenue.
* **Customer Behavior:** Loyal cluster buys most frequently and diversely; lapsed customers buy rarely and in low amounts.
* **Pricing Optimization:** High-value customers tolerate higher average basket sizes.
* **Inventory Management:** Segment demand guides stock allocation, avoiding overstock in low-value cohorts.
