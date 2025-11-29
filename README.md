# Crime Detection in Syracuse Using Machine Learning

This repository contains an end-to-end machine learning project that analyzes and predicts crime patterns in Syracuse, New York. Using historical crime data and socio-economic indicators, the project identifies high-risk locations and time periods to support data-driven decision-making for public safety and urban planning.

---

## Table of Contents

- [Project Summary](#project-summary)
- [Objectives](#objectives)
- [Data Sources](#data-sources)
- [Methodology](#methodology)
  - [Time-Series Forecasting](#time-series-forecasting)
  - [Spatial Classification](#spatial-classification)
- [Results](#results)
- [Repository Structure](#repository-structure)
- [Tech Stack](#tech-stack)
- [Limitations](#limitations)
- [Future Enhancements](#future-enhancements)
- [Team](#team)
- [License](#license)

---

## Project Summary

Urban crime exhibits complex spatial and temporal patterns that require more than descriptive statistics to understand. This project integrates:

- Historical crime incident data (2023–2024)
- Socio-economic indicators (unemployment rates)
- Time-series forecasting
- Supervised machine learning
- Geospatial analysis and visualization

The outcome is a predictive framework capable of forecasting crime trends and classifying geographic risk zones across Syracuse.

---

## Objectives

- Analyze historical crime trends by **hour, day, month, and season**
- Forecast future crime volumes using **time-series models**
- Identify geographic **crime hotspots** using spatial classification
- Classify city regions into **Low / Medium / High crime-risk** zones
- Provide **interpretable visual outputs** for law enforcement and city planners

---

## Data Sources

- **Crime Data**  
  - Syracuse Open Data Portal  
  - Includes reported offenses with timestamps and latitude/longitude coordinates

- **Socio-Economic Data**  
  - Monthly unemployment rates (2023–2024)

### Key Features

- Crime type  
- Date and hour of occurrence  
- Latitude and longitude  
- Grid-based spatial identifier (Grid ID)  
- Unemployment rate  
- Engineered temporal features (day of week, month, year)

---

## Methodology

### Time-Series Forecasting

- **Model:** SARIMA / SARIMAX  
- **Goal:** Predict monthly and hourly crime trends  
- **Approach:**  
  - Aggregate crime counts by time period  
  - Model seasonality and trend using crime count time series  
- **Evaluation Metrics:**  
  - Mean Absolute Error (MAE)  
  - Root Mean Squared Error (RMSE)  
  - Mean Absolute Percentage Error (MAPE)  
  - R² Score  

### Spatial Classification

- **Model:** Random Forest Classifier  
- **Goal:** Classify city grid cells into crime-risk categories (Low / Medium / High)  
- **Input Features:**  
  - Hour of day  
  - Day of week  
  - Grid ID  
  - Crime type (encoded)  
  - Unemployment rate  
- **Techniques:**  
  - Label Encoding for categorical variables  
  - SMOTE oversampling to handle class imbalance  
  - Cross-validation for model robustness  

### Spatial Processing

- Latitude/longitude values were bucketed into **uniform grid cells** to standardize spatial regions and enable grid-wise crime frequency analysis.

---

## Results

- Accurate forecasting of **monthly and hourly crime trends** using SARIMA  
- Strong detection of **seasonal patterns** and recurring high-crime hours  
- High classification performance for **major crime categories**  
- Identification of **persistent high-risk zones** across Syracuse  
- Interactive geospatial visualizations showing:
  - Crime density by grid
  - Predicted risk zones (Low / Medium / High)

These outputs can help stakeholders prioritize patrols, resource allocation, and long-term planning.

---

## Repository Structure

> _Adjust this section to match your actual folder names._

```text
.
├── data/                 # Raw and processed datasets (not committed if large/sensitive)
├── notebooks/            # Jupyter notebooks for EDA, modeling, and evaluation
├── src/                  # Python scripts (data prep, modeling, evaluation, visualization)
├── visuals/              # Exported plots and map screenshots
├── models/               # Saved model artifacts (if applicable)
├── README.md             # Project documentation
└── requirements.txt      # Python dependencies
