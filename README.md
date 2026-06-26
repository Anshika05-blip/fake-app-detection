# Fake App Detection

A machine learning project that identifies fake or suspicious apps on the Google Play Store using app metadata. Five classical ML models are trained and compared, with XGBoost coming out on top.

## How it works

App metadata (rating, reviews, installs, price, size, category, etc.) is cleaned and used to generate a `Fake` label based on a weighted scoring system. Multiple models are then trained on this data and evaluated against each other.

**Models compared:**
- Logistic Regression
- SVM
- Naive Bayes
- KNN
- XGBoost

## Dataset

Uses the [Google Play Store Apps dataset](https://www.kaggle.com/datasets/lava18/google-play-store-apps) from Kaggle.

## Setup

```bash
pip install pandas numpy scikit-learn xgboost matplotlib seaborn kaggle
```

## Usage

1. Add your Kaggle API key (`kaggle.json`) to `/content/`
2. Run all cells in order — the notebook handles download, cleaning, training, and evaluation automatically

## Results

| Model               | Precision (%) | Recall (%) | F1 (%) | Accuracy (%) |
|---------------------|--------------|-----------|--------|-------------|
| Logistic Regression | 87.00        | 50.83     | 64.17  | 81.05       |
| SVM                 | 89.95        | 51.93     | 65.85  | 82.02       |
| Naive Bayes         | 36.25        | 99.59     | 53.15  | 41.40       |
| KNN                 | 79.21        | 66.85     | 72.51  | 83.08       |
| XGBoost             | 96.23        | 95.17     | 95.69  | 97.14       |

XGBoost achieved the best overall performance across all metrics.

## Features used

`Rating` · `Reviews` · `Size` · `Installs` · `Price` · `Type` · `Category` · `Content Rating` · `Genres` · `Days Since Last Update`

## Tech Stack

Python · pandas · NumPy · scikit-learn · XGBoost · matplotlib · seaborn
