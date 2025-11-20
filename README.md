# COVID-19 Predictor

Predictive modeling of COVID-19 hospital admissions and deaths in the UK using Google mobility data as predictor variables.

## Overview

This project implements a rolling-window time-series forecasting approach to predict:
- Hospital admissions (1-4 weeks ahead)
- Deaths (1-4 weeks ahead)

Using publicly available data sources:
- **Google COVID-19 Community Mobility Reports** (predictors)
- **UK Health Security Agency COVID-19 data** (targets)

## Key Features

- **Temporal data preprocessing**: Interpolation and 14-day smoothing to handle reporting artifacts
- **Rolling window forecasting**: Fixed training windows with linear regression
- **Training window sensitivity analysis**: Comparison of 2, 4, 8, and 16-week windows
- **Visual lag analysis**: Identification of 2-3 week mobility→hospitalization lag

## Results

- **Hospital Cases (4-week ahead)**: R² = 0.858 (8-week training window)
- **Deaths (4-week ahead)**: Lower accuracy due to increased downstream variability

## Limitations

⚠️ **No train/test split**: All metrics computed on overlapping data; R² values likely overestimate true performance

## Requirements

```
pandas
numpy
scikit-learn
matplotlib
seaborn
```

## Data Sources

- [Google COVID-19 Mobility Data](https://www.google.com/covid19/mobility/)
- [UK COVID-19 Archive](https://ukhsa-dashboard.data.gov.uk/covid-19-archive-data-download) (not included; 1.6GB)

## Usage

1. Download UK COVID-19 archive and extract to `covid-19-archive/`
2. Run all cells in `Covid-predictor.ipynb`

## License

Educational project for Applied Machine Learning coursework.
