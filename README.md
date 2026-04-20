# Air Quality Prediction in Cities around the World (PM2.5)

## Overview
This project applies statistical analysis and machine learning to predict monthly PM2.5 concentrations in cities worldwide using openly available environmental, socio-economic, and infrastructural data.
The goal is to understand which factors drive urban air pollution and how accurately global air quality can be modeled using data-driven approaches.

## Problem Statement
Air pollution is a major global health risk, causing millions of premature deaths annually. Among pollutants, PM2.5 (fine particulate matter ≤ 2.5 µm) is particularly harmful due to its ability to penetrate deep into the respiratory system.

This project addresses the following question:
> How accurately can monthly PM2.5 concentrations be predicted for cities worldwide using open data and machine learning models?

## Data
The dataset combines multiple openly available data sources to enable a global, multi-dimensional analysis of urban air quality. All datasets are merged at city level and used for both statistical analysis and machine learning prediction.

### Data Sources
- Air quality data: IQAir  
- Weather data: Meteostat  
- Geolocation data: Geocoding API  
- Economic data: World Bank Group  
- Airport data: OurAirports  
- Demographic data: Demographia World Urban Areas  
- Traffic congestion data: OpenStreetMap & TomTom  
- Vegetation index (NDVI): Google Earth Engine  
- Energy data: Ember Energy  

### Target Variable
- Monthly average PM2.5 concentration (µg/m³), aggregated at city level for the year 2024

### Dataset Characteristics
- 95 cities worldwide  
- 1,139 monthly observations  
- Cross-domain feature integration (environmental, economic, infrastructural, demographic)

> Note: While the dataset provides broad global coverage, it is slightly biased towards cities in economically developed regions due to data availability constraints.

## Methodology

### 1. Exploratory Data Analysis
- Distribution analysis of PM2.5 (strong right-skew, extreme outliers)
- Regional and seasonal pollution patterns
- Correlation analysis between features and target variable

### 2. Statistical Analysis
- Multicollinearity handling using correlation thresholds (|r| ≥ 0.7)
- Multiple linear regression (adjusted R² ≈ 0.53)
- Hypothesis test (Mann–Whitney U) confirming significantly higher PM2.5 in low-income countries (p ≈ 5.28e-61)

## Machine Learning Models
All models were trained using an 80/20 train-test split and evaluated via cross-validation.

### Linear Models
- Linear Regression
- Ridge / Lasso / ElasticNet
Result:
- Limited predictive power (best R² ≈ 0.37)
- Unable to capture nonlinear pollution dynamics

### Tree-Based Models
- Decision Tree
- Random Forest
- Gradient Boosting
Result:
- Strong improvement over linear models
- Best tree-based model: Gradient Boosting (R² ≈ 0.58)
- Robust handling of nonlinear interactions

### Neural Network
- Multilayer Perceptron (MLP)
Result:
- Best overall performance (R² ≈ 0.61)
- Strong predictive capability for low and medium pollution levels
- Weakness: systematic underestimation of extreme pollution events

## Model Comparison
| Model Type          | Best R² |
|--------------------|--------|
| Linear Regression   | 0.37   |
| Decision Tree       | 0.47   |
| Random Forest       | 0.50   |
| Gradient Boosting   | 0.58   |
| MLP (Neural Net)    | 0.61   |

## Key Findings
- Economic development is strongly associated with lower PM2.5 levels
- Meteorological conditions (wind, precipitation) significantly influence pollution dispersion
- Tree-based and neural models outperform linear models due to nonlinear relationships
- Data imbalance across regions limits predictive accuracy in highly polluted areas
- Extreme pollution events remain difficult to capture with available features

## Key Limitations
- Uneven geographical distribution (overrepresentation of developed regions)
- Some features only available at national rather than city level
- Limited temporal resolution for stable indicators (e.g. NDVI, GDP)
- Missing extreme-event variables (e.g. wildfires, dust storms)
  
## Project Structure
```
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
```

## How to run
1. install Dependencies:
```
pip install -r requirements.txt
```
2. Run the notebooks in the following order:
   * notebooks/Data_analysis.ipynb
    → performs exploratory data analysis on final_dataset2.csv
   * notebooks/ML_models.ipynb
    → trains and evaluates models using processed_data.csv

## Author Note
This project was developed as part of an academic research project combining statistical analysis and machine learning to study global air pollution patterns.
