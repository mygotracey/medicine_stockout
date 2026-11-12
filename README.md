# Medicine Stock-Out Prediction and Refill Support

BSc Data Science project (JKUAT): predicting medicine stock-outs in hospitals and supporting patient refill adherence.

**Status:** proposal stage. Data cleaning is complete; forecasting begins after proposal approval.

## Project overview

The project has four parts:

1. **Demand forecasting:** weekly demand by drug category, comparing baselines (naïve, seasonal naïve, ETS, SARIMA) with machine learning (random forest, XGBoost).
2. **Stock-out risk and reorder points:** risk classification and safety-stock reorder points by medicine criticality.
3. **Supplier-failure simulator:** replays demand under different supplier fill rates and lead times.
4. **Refill reminder module:** demonstrated on simulated patient data only.

## Repository contents

| File | Description |
|---|---|
| `01_data_exploration.ipynb` | Data checks, weekly aggregation, outlier check, plots and train/test split |
| `weekly_sales.csv` | Cleaned weekly sales for 8 drug categories |

## Data preparation summary

- Source data: 2,106 daily rows (2 Jan 2014 to 8 Oct 2019), with no missing values or missing days
- Daily sales added up into **300 complete weeks** (12 Jan 2014 to 6 Oct 2019); partial weeks removed
- Outliers kept, because they are consistent with seasonal demand
- Time-ordered split: **248 training weeks and 52 test weeks**, with no shuffling

## Data Source

Zdravković, M. (2020). *Pharma Sales Data* [Data set]. Kaggle.
https://www.kaggle.com/datasets/milanzdravkovic/pharma-sales-data

The dataset contains six years (2014–2019) of pharmacy sales, grouped into 8 ATC drug categories. All credit for the data goes to the original author. The raw file is not modified in this project.

## Limitations

The data comes from one pharmacy, not a hospital, and contains no stock-on-hand records. Patient-level data for the refill module is simulated.
