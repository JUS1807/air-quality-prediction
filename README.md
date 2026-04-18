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
- Vegetation index (Google Earth Engine)
- Energy data (Ember Energy)

Two datasets are included in this repository:
- `final_dataset2.csv` → raw integrated dataset used for analysis  
- `processed_data.csv` → cleaned and processed dataset used for modeling  

The final dataset is aggregated on a monthly level.

## Methodology
The project follows a two-step workflow:
1. **Exploratory Data Analysis (EDA)**
   - Data inspection and cleaning
   - Type conversion and validation
   - Initial feature exploration

2. **Modeling**
   - Feature preparation
   - City-based train/test split (to avoid data leakage)
   - Training and comparison of multiple regression models
   - Evaluation using R²

## Models
- Linear Regression
- Random Forest
- Gradient Boosting
- Multi-Layer-Perceptron (MLP)

## Results
Best model achieved:
- R² ≈ 0.6
Model performance is limited by high variability in environmental data and missing external influencing factors.

## Project Structure
air-quality-prediction/
│
├── README.md
├── requirements.txt
│
├── data/
│   ├── final_dataset2.csv
│   └── processed_data.csv
│
└── notebooks/
    ├── Data_analysis.ipynb
    └── ML_models.ipynb

## How to run
1. install Dependencies:
  bash
  pip install -r requirements.txt
  python src/train.py

2. Run the notebooks in the following order:
   * notebooks/Data_analysis.ipynb
    → performs exploratory data analysis on final_dataset2.csv
   * notebooks/ML_models.ipynb
    → trains and evaluates models using processed_data.csv

## Key Learnings
* Integration of heterogeneous environmental data sources
* Importance of spatial data splitting (city-based) to avoid leakage
* Limitations of classical ML models under real-world data constraints
