# Kenya Smallholder Maize Yield Prediction

**Author:** Clement Ongera Nyangoya  
**Date:** April 2026  
**Location:** Nakuru County, Kenya (0.3066°S, 35.9668°E)

## Overview
Pilot machine learning study predicting smallholder maize yield from CHIRPS 
satellite rainfall estimates. Conducted on the author's own farm across three 
growing seasons (2023–2024).

## Key Findings
- **Dataset:** 3 plot-seasons from one smallholder farm in Kenya's Rift Valley
- **Model:** Random Forest regression
- **Top predictor:** Growing-season rainfall (`rain_growing_mm`, importance = 0.166)
- **Performance:** R² = 0.774, RMSE = 296 kg/ha (training evaluation)
- **Insight:** Rainfall during the growing season is the dominant yield-limiting 
  factor, confirming farmer knowledge with quantitative evidence

## Data
- **Yield records:** Farmer-reported maize yields (bag counts), planting dates, 
  harvest dates from author's farm
- **Rainfall:** CHIRPS daily precipitation estimates extracted via Climate Engine 
  (0.05° resolution, ~5.5 km)
- **Study site:** Semi-arid highland, ~1,900 m elevation

## Methods
- Agronomic feature engineering: pre-season, growing-season, and flowering-period 
  rainfall; dry-day count; peak daily rainfall; rainfall coefficient of variation
- Random Forest regression with conservative hyperparameters (max_depth=3) to 
  prevent overfitting on small sample
- Feature importance analysis and predicted-vs-observed visualization

## Limitations
- Small sample size (N=3 plot-seasons) — pilot study only
- Farmer-reported yields (not formally weighed)
- Single plot — no spatial generalization
- CHIRPS resolution (5.5 km) much coarser than plot size
- Training-on-all evaluation — no independent test set
