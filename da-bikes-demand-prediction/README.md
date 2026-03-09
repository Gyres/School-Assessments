# Bike Demand Prediction with Linear Regression

This project analyses daily shared-bike rental demand using Python and linear regression to identify how weather, seasonality, and calendar-related factors influence bike usage. It focuses on building an interpretable baseline model rather than a black-box predictor.

## Project Overview
- **Institution:** Singapore University of Social Sciences (SUSS)
- **Project Type:** Group
- **Academic Term:** Jan 2025
- **Status:** Completed

## Problem Statement
Shared-bike operators need to anticipate daily rental demand so they can plan fleet availability, improve service reliability, and better understand what drives customer usage. This project explores whether temporal and weather-related variables can explain changes in daily bike demand, and uses multiple linear regression to quantify those relationships.

## Objectives
- Analyse the shared-bike dataset and understand its structure, quality, and key patterns.
- Explore relationships between bike demand and explanatory variables such as temperature, humidity, weather condition, season, and calendar effects.
- Build an interpretable regression model to estimate daily bike demand and evaluate its explanatory power.

## Dataset
### Source
- Course-provided dataset stored in the repository as `Shared-Bikes-Demand-Dataset.csv`. :contentReference[oaicite:1]{index=1}

### Description
- **Number of rows:** 730 daily observations
- **Number of columns:** 16
- **Target variable:** `cnt` (total bike rentals)
- **Key variables:** `dteday`, `season`, `yr`, `mnth`, `holiday`, `weekday`, `workingday`, `weathersit`, `temp`, `atemp`, `hum`, `windspeed`, `casual`, `registered`
- **Data type:** Tabular time-series

### Notes
- No missing values were found in the notebook checks.
- The dataset combines temporal, weather, and usage variables.
- The analysis is conducted at the daily level, so it does not capture within-day demand fluctuations.

## Tools and Technologies
- **Programming Language:** Python
- **Environment:** Jupyter Notebook
- **Libraries / Frameworks:** pandas, numpy, matplotlib, seaborn, statsmodels, scikit-learn
- **Other Tools:** Git, GitHub

## Methodology
1. Load the CSV dataset and inspect the data structure.
2. Check for missing values and confirm basic data quality.
3. Prepare predictors for modelling, including handling categorical/calendar-related variables for regression analysis.
4. Perform exploratory data analysis using scatter plots, box plots, a correlation heatmap, and a time-series line chart.
5. Fit a linear regression model using scikit-learn and an OLS regression model using statsmodels.
6. Interpret model coefficients and evaluate diagnostics using residual plots and regression summary statistics.

## Repository Structure
```text
school-assessments/
└── da-bikes-demand-prediction/
    ├── README.md
    ├── Shared-Bikes-Demand-Dataset.csv
    └── bikes-demand-prediction.ipynb
```

The repository currently contains a README file, the dataset CSV, and the notebook used for the analysis. :contentReference[oaicite:2]{index=2}

## How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/Gyres/school-assessments.git
   ```
2. Navigate to the project folder:
   ```bash
   cd school-assessments/da-bikes-demand-prediction
   ```
3. Install the required libraries:
   ```bash
   pip install pandas numpy matplotlib seaborn statsmodels scikit-learn jupyter
   ```
4. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
5. Open `bikes-demand-prediction.ipynb` and run the cells in sequence.

## Results
### Key Findings
- The regression model explains a substantial portion of the variation in daily bike demand.
- Demand is generally higher in the later year of the dataset and under more favorable riding conditions.
- Higher humidity, stronger wind, poorer weather conditions, and holidays are associated with lower bike demand.

### Model Summary Metrics
| Metric | Value |
|--------|------:|
| R-squared | 0.801 |
| Adjusted R-squared | 0.798 |
| F-statistic | 262.8 |

## Visualisations / Outputs
Refer to `bikes-demand-prediction.ipynb` for visualisations and outputs.

## Limitations
- The project uses a linear model, which may not fully capture non-linear demand patterns.
- The feature set is limited to the variables available in the provided dataset.
- The analysis is done at daily granularity and does not account for hourly demand behaviour, station-level effects, or external events.

## Future Improvements
- Compare performance with more advanced models such as regularized regression, tree-based models, or time-series methods.
- Add richer features such as holidays by type, lag variables, promotions, or event indicators.
- Strengthen evaluation with train/test validation and additional prediction metrics such as RMSE or MAE.

## License
This repository is shared for portfolio purposes only.

Please do not copy, reuse, or submit this work as your own academic assignment.

## Contact
- **Name:** Ou Yang Yu
- **GitHub:** [Gyres](https://github.com/Gyres)
- **Linktree:** https://linktr.ee/yuouyang
