# [Myntra Online Retail Customer Segmentation](./notebooks/segmentation.ipynb)

## 📖 Project Overview

This repository implements an end‑to‑end unsupervised machine‑learning pipeline to segment Myntra Gifts Ltd.’s UK e‑commerce customers (Dec 2009–Dec 2011). By grouping customers based on Recency, Frequency, and Monetary (RFM) behavior, we deliver actionable insights for targeted marketing, optimized pricing, and inventory planning.

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

## 📊 Results

-   **3 Customer Segments** identified (High‑Value Loyal, Moderate, At‑Risk/Lapsed)
-   **High‑Value Loyal** customers (≈21%) generate ~60% of revenue
-   **Recommendations**:
    -   Retention & upsell for Cluster 1
    -   Targeted promotions for Cluster 0
    -   Win‑back campaigns for Cluster 2

Outputs (CSV + serialized model) are saved under `data/` and `models/` respectively.

---
