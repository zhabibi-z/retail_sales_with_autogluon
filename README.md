# Retail Sales & RFM Analysis with AutoGluon

Customer segmentation and sales forecasting using RFM (Recency, Frequency, Monetary) analysis and AutoML with AutoGluon.

## Overview

This project applies RFM scoring to segment customers by purchasing behaviour and trains AutoGluon tabular models to forecast sales and predict churn risk.

## Project Structure

```
├── data/          # Raw transaction data
├── notebooks/     # EDA, RFM segmentation, AutoGluon training
├── src/           # Feature engineering and modelling pipeline
├── outputs/       # Trained models, segment reports, figures
└── requirements.txt
```

## Getting Started

```bash
pip install -r requirements.txt
```

## Key Methods

- **RFM Segmentation** — customers ranked by recency, purchase frequency, and total spend
- **AutoGluon Tabular** — automated model selection and ensembling for sales forecasting
- **Cohort Analysis** — retention curves by acquisition month
