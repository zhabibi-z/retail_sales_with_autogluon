# Retail Sales & RFM Analysis with AutoGluon

findjng the total amount

Exploratory analysis and **RFM customer segmentation** on the Kaggle *Retail Sales* dataset,
plus a **leakage-free AutoGluon** regression benchmark for `Total Amount`.

## Overview

A single notebook ([`Retail_Sales_&_RFM_with_AutoGluon.ipynb`](Retail_Sales_&_RFM_with_AutoGluon.ipynb)):

1. **EDA** — statistical summary, outliers, distributions, age/gender demographics, time-series of sales.
2. **RFM segmentation** — customers scored by Recency, Frequency, and Monetary value and bucketed
   into behavioural segments (Champions, Loyal, At Risk, ...).
3. **AutoGluon regression** — an AutoML benchmark predicting `Total Amount`.

The dataset is pulled at runtime via `kagglehub` (`mohammadtalib786/retail-sales-dataset`).

## Modeling note (target leakage)

`Total Amount == Quantity × Price per Unit` by construction. The modeling section therefore
**excludes** `Quantity`, `Price per Unit`, and any Monetary-derived RFM feature (e.g. `RFM_Level`)
from the predictors — otherwise the target is trivially recoverable and the metrics are
meaningless. It uses only demographics, product category, calendar features, and the non-monetary
RFM signals (Recency, Frequency), with an honest 80/20 train/test split evaluated on the holdout.

Because a transaction's amount is mechanically price × quantity, a leakage-free model has limited
signal — the honest error is high, and the primary value of this dataset is the **RFM
segmentation**, not point prediction of `Total Amount`.

## Getting started

```bash
pip install -r requirements.txt
# Open the notebook and run top to bottom. Data downloads automatically via kagglehub
# (set up your Kaggle credentials for kagglehub if prompted).
```

## Repository layout

```
├── Retail_Sales_&_RFM_with_AutoGluon.ipynb   # EDA + RFM segmentation + leakage-free AutoGluon
├── requirements.txt
└── README.md
```
