# What Drives the Price of a Car?

## Project Summary

This project aims to analyze and model the factors that influence the price of a car using a publicly available dataset. Through data cleaning, exploratory data analysis (EDA), and regression modeling, we explore the relationships between vehicle features (such as model, condition, fuel type, and transmission) and car price.

The goal is to provide insights for businesses—such as used car dealerships—to make data-driven pricing decisions.

## Notebook

👉 [Click here to view the full Jupyter notebook](https://github.com/AriAlas/ml-price-of-car-analysis/blob/main/practical_application_II_starter/what-drives-the-price-of-a-car.ipynb)

## Model Evaluation & Business Insights

After training multiple regression models, our best-performing model was a Random Forest Regressor with the following hyperparameters:

```python
Best RF Parameters:
- max_depth: 30
- min_samples_leaf: 6
- n_estimators: 352

Cross-Validation RMSE: 5522.28
Test Set RMSE: 5253.20
```

This model significantly outperformed simpler linear and ridge models in both cross-validation and holdout test data, suggesting that non-linear relationships and interactions between features (such as model year, condition, odometer, and manufacturer) are important in predicting car prices.

## Key Insights

Based on the feature importance analysis from the tuned Random Forest model, the following variables are the strongest predictors of used car price:
- Model Year (year) is by far the most important feature, accounting for ~40% of the model’s decision-making. This confirms that newer vehicles tend to retain more value, making year a critical factor in pricing.
- Model (model) contributes to the prediction. This indicates that individual vehicle models have substantial influence, likely due to brand reputation, feature sets, and demand.
- Odometer (odometer) explains ~11% of the variation in price. As expected, vehicles with lower mileage tend to be more valuable.
- Cylinders (cylinders) and Fuel Type (fuel_diesel) are meaningful but less dominant predictors. This suggests that engine size and fuel efficiency/preferences play a role in price perception, especially for diesel-powered vehicles.
- Manufacturer and Region also influence price, though to a lesser extent. This could reflect brand premium and regional market differences in vehicle demand.
- Condition, while still relevant, ranks lower than expected. This may be due to inconsistent or subjective labeling of condition across listings, which could be worth further investigation or data enrichment.
- Drive type (4WD and FWD) also has marginal predictive power, hinting at preferences for certain drivetrains in specific markets or conditions.