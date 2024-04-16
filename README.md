# Currency Exchange Rate Forecasting

This repository contains code and resources for building a time-series model to Forecast Currency Exchange Rates between INR-USD using SARIMAX algorithm.

## Overview

The goal of this project is to develop a forecasting model that can forecast future exchange rates between INR and USD currencies. The model will be trained on historical exchange rate data and evaluated on its ability to make accurate predictions on new unseen data. The model is been created using SARIMAX algorithm.

## Dataset

The dataset used for this project is the [INR-USD.csv](INR-USD.csv), which contains historical exchange rate data between INR and USD currencies over a specific time period.

You can download the dataset from [link to dataset](https://www.kaggle.com/datasets/bhanupratapbiswas/usd-inr-conversion-rate-case-study).

## Project Structure

The project is organized as follows:

- `Plots/`: This directory contains the plots of relationship between INR-USD exchange rates under differet parameters.
- `Currency Exchange Rate Forecasting.ipynb`: This file contains the code which is used for data exploration, preprocessing, model training, and evaluation.
- `INR-USD.csv`: This file contains contains the dataset which we used for the training the model.
  

## Dependencies

The project requires the following Python libraries:

- numpy : for handling the arrays
- pandas : for using the data in dataframes
- matplotlib : to plot the visible graphs
- seaborn : to use it on top of the Matplotlib
- statsmodel : for the SARIMAX algorithm and seasonal_decompose method (Used for removing the seasonality)
- pmdarima : to find out the non-seasonal order

You can install the dependencies using the following command:

pmdarima : **!pip install pmdarima**

## SARIMAX model : 
- **S**easonal **A**uto**R**egressive **I**ntegrated **M**oving **A**verage e**X**ogenous regressor
- Is a class used for fitting and forecasting time series data
- SARIMAX models allow you to model and forecast time series data that exhibit both trend and seasonality, and they can also handle exogenous variables, which are external factors that may influence the time series
- Example :
    ![image](https://github.com/Prajwal-1718/Currency-Exchange-Rate-Forecasting/assets/68771962/19d41813-0371-4490-b44f-7f54f549c505)
    In this example:
      **data** represents your time series data.
      **order** specifies the **non-seasonal ARIMA parameters (p, d, q)**.
      **seasonal_order** specifies the **seasonal ARIMA parameters (P, D, Q, s)**.

- Parameters :
    * **AutoRegressive Order (p or P)** : The autoregressive component models the **relationship between an observation and a number of lagged observations**. The **p** parameter specifies the **number of lag observations** included in the model. For example, p=1 means that the current observation is related to the previous observation, p=2 means it's related to the previous two observations, and so on
      
    * **Differencing Order (d or D)** : The differencing component involves **differencing the time series dat**a to make it **stationary**, **removing trends or seasonality**. The **d** parameter specifies the **number of differences** needed to make the series stationary. For example, d=1 means the first difference (i.e., subtracting each observation from the previous one), d=2 means the second difference (i.e., applying the difference operator twice), and so on
      
    * **Moving Average Order (q or Q)** : The moving average component models the **relationship between an observation and a residual error** from a moving average model **applied to lagged observations**. The **q** parameter specifies the **size of the moving average window**. For example, q=1 means that the current observation is related to the residual error from the previous observation, q=2 means it's related to the residual errors from the previous two observations, and so on.
      
    * **Seasonal Period (s)** : This is the **number of observations per seasonal cycle**. For example, if you have monthly data with yearly seasonality, s would be 12.

- In SARIMAX models, the seasonal order is specified along with the non-seasonal order (p,d,q). For example, a SARIMAX(1, 1, 1) × (1, 1, 1, 12) model has the following parameters:
  * Non-seasonal order: p=1, d=1, q=1
  * Seasonal order: P=1, D=1, Q=1, s=12.


## Plots : 
1. **USD - INR Conversion Rate over the years** :
   
    ![USD - INR Conversion Rate over the years](https://github.com/Prajwal-1718/Currency-Exchange-Rate-Forecasting/assets/68771962/482cdd18-b1c0-41eb-bdef-69b466e84de5)

3. **Yearly Growth of USD - INR Conversion Rate** :

    ![Yearly Growth of USD - INR Conversion Rate](https://github.com/Prajwal-1718/Currency-Exchange-Rate-Forecasting/assets/68771962/07bbc0cd-9789-4838-9a89-8da92eb319eb)

5. **Aggregated Monthly Growth Conversion Rate of USD - INR** :

    ![Aggregated Monthly Growth Conversion Rate of USD - INR](https://github.com/Prajwal-1718/Currency-Exchange-Rate-Forecasting/assets/68771962/b1ab9a57-cd2c-4bac-a7f6-934528787216)

7. **INR Rate - Training Data and Predictions** :

    ![INR Rate - Training Data and Predictions](https://github.com/Prajwal-1718/Currency-Exchange-Rate-Forecasting/assets/68771962/ba32c2e4-c3bf-4daf-86c8-b13b3efbc581)

