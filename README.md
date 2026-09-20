# NYC Airbnb ML Pipeline

## Submission Links

- **W&B Project:** https://wandb.ai/kdweaver324-western-governors-university/nyc_airbnb
- **GitHub Repository:** https://github.com/devonweaver/Project-Build-an-ML-Pipeline-Starter

## Overview

End-to-end ML pipeline for predicting NYC Airbnb prices. Built with MLflow, Hydra, and Weights & Biases.

## Pipeline Steps

1. `download` — Download sample data from W&B
2. `basic_cleaning` — Remove outliers, filter geolocation boundaries, convert dates
3. `data_check` — Validate data against reference distribution
4. `data_split` — Train/val/test split
5. `train_random_forest` — Train Random Forest with hyperparameter search
6. `test_regression_model` — Test on held-out set

## Results

- **Validation MAE:** 34.18
- **Test MAE:** 33.85
- **Best hyperparameters:** max_depth=50, n_estimators=200

## Releases

- **v1.0.0** — Initial pipeline release
- **v1.0.1** — Add geolocation boundary filter to handle out-of-bounds data in sample2.csv

## Project Structure
.
├── components/ # Reusable components (get_data, train_val_test_split, test_regression_model)
├── src/ # Pipeline steps
│ ├── eda/ # Exploratory Data Analysis
│ ├── basic_cleaning/ # Data cleaning
│ ├── data_check/ # Data validation tests
│ └── train_random_forest/ # Model training
├── config.yaml # Hydra configuration
├── main.py # Pipeline orchestrator
└── MLproject # MLflow project definition