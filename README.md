# 🍸 Hotel Bar Inventory Forecasting & Par Level Recommendation System

A demand forecasting and inventory optimization system built for a multi-location
hotel bar chain, designed to reduce stockouts of high-demand items while cutting
excess capital tied up in slow-moving inventory.

## Problem
The hotel chain operates 6 bars carrying overlapping liquor brands and faces two
conflicting issues: **stockouts** of popular items during peak demand (lost revenue,
guest dissatisfaction) and **overstocking** of slow movers (tied-up capital,
limited storage, spoilage risk).

## What This Project Does
- Cleans ~6,575 raw transaction-level records into a daily consumption
  time-series per bar × brand
- Benchmarks three forecasting approaches (rolling-average baseline,
  Holt-Winters exponential smoothing, RandomForest) using WAPE
- Computes a dynamic **par level** per item (forecasted lead-time demand +
  safety stock, based on a 95% service level)
- Backtests the recommended par levels against a naive policy via a
  day-by-day inventory simulation across all 96 bar-brand combinations

## Key Finding
The simple rolling-average baseline outperformed both Holt-Winters and
RandomForest (WAPE 2.19 vs 2.42 vs 2.55) — this dataset has no strong
seasonal pattern for complex models to exploit. The simulation also revealed
that a 30-day trailing window for the par-level formula is too reactive for
this data's volatility, an honest limitation discussed in the write-up along
with concrete next steps.

## Tech Stack
Python · pandas · numpy · matplotlib/seaborn · statsmodels · scikit-learn

## Contents
- `Kristalball_Inventory_Forecasting.ipynb` — full solution: EDA → forecasting →
  par level calculation → simulation → business write-up (all in one notebook)

## Author
Nudurupati Charani ([LinkedIn](your-linkedin-url-here))
