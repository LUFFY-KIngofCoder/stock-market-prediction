# Stock Price Prediction with Polynomial Regression

This project uses historical stock data from Yahoo Finance to predict the future stock prices of Apple (AAPL) using Polynomial Regression with Linear Regression as the base model. The project demonstrates the application of machine learning techniques for financial forecasting.

## Table of Contents

- [Overview](#overview)
- [Data Collection](#data-collection)
- [Preprocessing](#preprocessing)
- [Modeling](#modeling)
- [Evaluation](#evaluation)
- [Results](#results)
- [Installation](#installation)
- [Usage](#usage)


## Overview

In this project, we use historical stock data from Yahoo Finance for Apple Inc. (AAPL). The goal is to predict the stock's closing prices based on various features, such as opening price, high, low, and volume. We apply Polynomial Regression, using Linear Regression models for each polynomial degree, and then evaluate which degree gives the best performance based on cross-validation scores.

## Data Collection

The data is collected from Yahoo Finance using the `yfinance` Python library. The dataset includes the following columns:

- **Open**: Opening price of the stock for the day.
- **High**: Highest price of the stock during the day.
- **Low**: Lowest price of the stock during the day.
- **Volume**: The number of shares traded during the day.
- **Close**: The closing price of the stock (target variable).

We use the historical data for Apple (AAPL) to train and evaluate the model.

## Preprocessing

The following preprocessing steps are applied to the data:

1. **Data Splitting**: The data is split into three sets:
   - Training set (60% of the data)
   - Cross-validation set (20% of the data)
   - Test set (20% of the data)

2. **Feature Scaling**: StandardScaler is used to standardize the features to zero mean and unit variance, ensuring that all features are on the same scale.

3. **Polynomial Feature Transformation**: PolynomialFeatures are used to generate polynomial features for each degree from 1 to 10.

## Modeling

We apply **Linear Regression** models on the polynomial-transformed features. The models are evaluated using **cross-validation** with a scoring method based on negative mean squared error (MSE). The best-performing model is selected based on the lowest MSE.

## Evaluation

The performance of the model is evaluated using the **R2 score** on the test set. The R2 score represents the proportion of variance in the target variable (closing price) that is explained by the model.

The model is also evaluated visually by plotting the **Actual vs Predicted** stock prices for the best-performing polynomial degree.

## Results

- The model is evaluated using the R2 score on the test set.
- A plot is generated comparing the actual closing prices with the predicted values.

## Installation

To run this project, you need to install the required Python libraries. You can install them using `pip`:

```bash
pip install yfinance numpy pandas scikit-learn matplotlib
```

## Usage
1. Clone this repository:

```bash
git clone https://github.com/LUFFY-KingofCoder/stock-price-prediction.git
```

2. Navigate to the project directory:

```bash
cd stock-price-prediction
```

3. Run the script:

```bash
python stock_price_prediction.py
```
The script will fetch the data, train the models, and display the results (R2 score and plot).
