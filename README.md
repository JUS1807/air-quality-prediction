# Air Quality Prediction (PM2.5)

## Overview
This project predicts PM2.5 air pollution levels across cities using environmental and geospatial data.

## Problem
Air pollution varies significantly across regions and time.  
The goal is to model and predict monthly PM2.5 levels based on weather and location-based features.

## Data
- Air quality data (IQAir)
- Weather data (Meteostat)
- Geolocation data (Geocoding API)
- Economic data (World Bank Group)
- Airport data (ourairports)
- Demographic data (Demographia World Urban Areas)
- Congestion data (openstreetmap & TomTom)

The final dataset is aggregated on a monthly level.

## Methodology
- Data collection and integration from multiple APIs
- Data cleaning and preprocessing
- Feature engineering
- City-based train/test split (to avoid data leakage)
- Model training and comparison
- Evaluation using R² score

## Models
- Linear Regression
- Random Forest
- Gradient Boosting
- MLP

## Results
Best model achieved:
- R² ≈ 0.6

## Project Structure
- `notebooks/`: Exploratory analysis and model development
- `src/`: Modular pipeline components
- `data/`: Raw and processed datasets
- `results/`: Model outputs and plots

## How to run
```bash
pip install -r requirements.txt
python src/train.py
