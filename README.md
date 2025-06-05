# Energy Consumption Prediction of Home Appliances

##  Introduction

Energy consumption is a critical concern in today's world, where efficient usage and conservation are key priorities. This project aims to develop a predictive model that can estimate the energy consumed by home appliances based on various environmental and operational conditions. Accurate predictions can help users monitor and optimize their electricity usage, contributing to smarter and more sustainable homes.

## 🎯 Aim

To build and evaluate a machine learning model that predicts **home appliance energy consumption (in Wh)** using historical and contextual data, thereby aiding in better energy management strategies.

##  Dataset Overview

* **Source**: UCI Machine Learning Repository
* **Total Records**: \~19,735
* **Target Variable**: `Appliances` (energy consumption in Wh)
* **Features**:

  * Environmental metrics: `T1` to `T9`, `RH_1` to `RH_9` (temperature and humidity)
  * Weather conditions: `T_out`, `Press_mm_hg`, `RH_out`, `Windspeed`, `Visibility`, `Tdewpoint`
  * Timestamp: `date`
  * Random data column: `rv1`, `rv2` (used as synthetic features)

##  Steps Followed

1. **Data Loading & Exploration**

   * Loaded the dataset
   * Performed exploratory data analysis (EDA)

2. **Data Preprocessing**

   * Dropped irrelevant columns
   * Handled datetime features
   * Checked and handled missing values (if any)

3. **Feature Selection**

   * Used `SelectKBest` with `f_regression` for identifying important features

4. **Model Building & Training**

   * Implemented a **Pipeline** for clean workflow:

     * Imputation
     * Scaling
     * Model fitting
   * Tried multiple regression models:

     * Linear Regression
     * Random Forest
     * Gradient Boosting
     * Support Vector Regressor (SVR)
   * Hyperparameter tuning using GridSearchCV for optimal performance

5. **Model Evaluation**

   * Evaluated models using:

     * R² Score
     * Mean Absolute Error (MAE)
     * Root Mean Squared Error (RMSE)

6. **Model Saving & Deployment**

   * Saved the final model using `joblib` for future use

##  Methods Used

* **Pipeline** from `sklearn.pipeline`
* **Feature Selection**: `SelectKBest`, `f_regression`
* **Regression Models**: `LinearRegression`, `Ridge`, `Lasso`, `RandomForestRegressor`, `GradientBoostingRegressor`
* **Hyperparameter Tuning**: `GridSearchCV`
* **Model Persistence**: `joblib`

## 📊 Key Insights

* Some environmental factors like temperature and humidity in certain rooms significantly affect appliance energy usage.
* Ridge and Gradient Boosting models performed better than simple Linear Regression in terms of generalization.
* Hyperparameter tuning improved model accuracy and reduced error metrics.

##  Conclusion

This project successfully developed a predictive pipeline for home appliance energy consumption using environmental and weather-related features. With further improvements like real-time data integration and feature engineering, such models can be deployed in smart homes for energy-saving recommendations and automation.

