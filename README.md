🚖 Uber Trip Analysis – Machine Learning Project
📘 Project Overview

This project analyzes Uber trip data from New York City to uncover travel patterns, identify high-demand periods, and forecast trip counts using machine learning models.

It uses data from the NYC Taxi & Limousine Commission (TLC) and FiveThirtyEight’s Uber datasets (2014–2015).
The final model predicts trip demand using Random Forest, Gradient Boosting, and XGBoost, achieving a forecasting accuracy (MAPE) below 9%.

🎯 Objectives

Perform exploratory data analysis (EDA) to identify trends in Uber pickups.

Build machine learning models to predict hourly trip demand.

Compare the performance of XGBoost, Random Forest, and Gradient Boosting.

Use ensemble averaging to further improve accuracy.

Visualize and interpret demand trends for actionable insights.

🧠 Dataset Description

File Used: Uber-Jan-Feb-FOIL.csv
Source: NYC TLC FOIL Response
 via FiveThirtyEight

Columns:
Column	Description
Date/Time	Timestamp of the Uber pickup
Lat	Latitude of pickup
Lon	Longitude of pickup
Base	TLC base company code
(2015 data) locationID	NYC Taxi Zone ID
(Aggregated) Trips	Count of pickups per hour/day
🧩 Tools & Technologies

Programming Language: Python

Libraries: pandas, numpy, seaborn, matplotlib, scikit-learn, xgboost, statsmodels

Machine Learning Models:

XGBoost

Random Forest Regressor

Gradient Boosted Regression Trees (GBRT)

Ensemble Model (weighted average)

IDE: Jupyter Notebook

Domain: Data Analytics / Machine Learning

⚙️ Project Workflow
1. Data Preprocessing

Merged multiple monthly CSV files (Apr–Sep 2014).

Converted Date/Time to datetime format.

Extracted features: hour, day, weekday, month.

Resampled data to hourly intervals for time series forecasting.

2. Exploratory Data Analysis (EDA)

Plotted trips per hour, day of week, and month.

Detected rush hour peaks and weekday/weekend trends.

Decomposed time series into trend, seasonality, and residuals.

3. Feature Engineering

Created lagged features (past trip counts).

Prepared sliding windows for model training.

Ensured chronological train-test split (time-series safe).

4. Model Training

Three regression models were trained and fine-tuned using GridSearchCV with TimeSeriesSplit cross-validation:

XGBoost Regressor

Random Forest Regressor

Gradient Boosted Tree Regressor (GBRT)

5. Ensemble Model

Weighted ensemble built as:

Final_Prediction = 0.368*XGBoost + 0.322*RandomForest + 0.310*GBRT

📊 Results & Evaluation
Model	Mean Absolute Percentage Error (MAPE)	Notes
XGBoost	8.37%	Best individual performance
Random Forest	9.61%	Robust baseline
GBRT	10.02%	Consistent but slightly less accurate
Ensemble	8.60%	Stable and balanced predictions

✅ XGBoost provided the most accurate and efficient forecasts.
✅ The ensemble produced smoother and more reliable results across time intervals.

📈 Key Visualizations

Trips per Hour

Trips per Day of Week

Seasonal Decomposition (Trend, Seasonality, Residuals)

Predicted vs. Actual Trips (for all models)

Ensemble Prediction Overlay

💡 Insights

Peak Hours: 6 AM–9 AM and 5 PM–8 PM.

Busiest Days: Fridays and Saturdays.

Steady Growth: Trip volume increased significantly after mid-2014.

XGBoost captured non-linear demand patterns effectively.

Temporal Cross-validation improved generalization for real-world forecasting.
