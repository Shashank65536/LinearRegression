# Delivery Duration Prediction

This project focuses on predicting the delivery duration using polynomial regression models and Ridge Regression. The dataset includes various features related to delivery orders, and the target variable is the total seconds between the `created_at` and `actual_delivery_time`.

## Table of Contents
- [Overview](#overview)
- [Dataset](#dataset)
- [Data Cleaning and Preprocessing](#data-cleaning-and-preprocessing)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Modeling](#modeling)
- [Results](#results)
- [Usage](#usage)
- [Dependencies](#dependencies)
- [Contributing](#contributing)
- [License](#license)

## Overview
This project aims to predict the delivery duration for food delivery orders using various polynomial regression models and Ridge Regression. We perform data cleaning, preprocessing, exploratory data analysis (EDA), and modeling to achieve this.

## Dataset
The dataset contains the following columns:
- `market_id`
- `created_at`
- `actual_delivery_time`
- `store_id`
- `store_primary_category`
- `order_protocol`
- `total_items`
- `subtotal`
- `num_distinct_items`
- `min_item_price`
- `max_item_price`
- `total_onshift_dashers`
- `total_busy_dashers`
- `total_outstanding_orders`
- `estimated_order_place_duration`
- `estimated_store_to_consumer_driving_duration`

The target variable to predict is the `delivery_duration_seconds`.

## Data Cleaning and Preprocessing
- Convert `created_at` and `actual_delivery_time` to datetime.
- Calculate the `delivery_duration_seconds` as the difference between `created_at` and `actual_delivery_time`.
- Drop rows with missing target values.
- Handle missing values for other columns by filling with median or empty strings.
- Drop rows where `total_onshift_dashers` are 0.
- Encode categorical variables and scale numerical features using a pipeline.

## Exploratory Data Analysis (EDA)
- Visualize the distribution of the `delivery_duration_seconds`.
- Plot relationships between numerical features and the target variable.

## Modeling
- Fit polynomial regression models of degrees 2, 3, and 4 using Ridge Regression and Linear Regression.
- Evaluate the models using RMSE, MAE, and R² scores.

## Results
- The performance of each polynomial regression model is evaluated on both training and test sets.
- Visualizations are provided to compare the actual vs. predicted delivery durations.

## Usage
To run this project locally:
1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/delivery-duration-prediction.git
    cd delivery-duration-prediction
    ```
2. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```
3. Run the data preprocessing and modeling script:
    ```bash
    python main.py
    ```

## Dependencies
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn

You can install these dependencies using `pip`:
```bash
pip install pandas numpy scikit-learn matplotlib seaborn
