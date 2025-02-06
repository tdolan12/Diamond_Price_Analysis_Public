# Diamond Price Analysis

## Overview

This repository contains an in-depth analysis of **diamond pricing** based on **carat weight and other attributes**. The study aims to provide insights into how **carat, cut, clarity, and color** influence a diamond’s market value.

## Problem Addressed

The **diamond industry** maintains secrecy in pricing strategies, making it difficult for **diamond cutters** to optimize their processes for maximum profitability. This project investigates how **carat weight** influences a diamond’s **selling price**, particularly in **luxury retail markets**. Using a dataset of **Tiffany & Co.’s 2017 price list**, this analysis models the relationship between key diamond attributes and their corresponding price points.

## Highlights

- **Best Model**: The final model achieved an **adjusted R-squared of 0.984**, demonstrating strong predictive power.
- **Carat Dominance**: **Carat weight alone** explains **93% of price variance**, highlighting its critical role in valuation.
- **Confounding Variables**: Clarity, color, and cut significantly impact price when included in the model.
- **Log-Transformation**: Carat and price were log-transformed to reduce skewness and improve model performance.
- **Feature Engineering**: One-hot encoding was applied to ordinal variables (cut, color, clarity) for regression modeling.
- **Statistical Significance**: The final model shows that increasing carat by **1%** leads to an approximate **1.89% increase** in price.
- **Comparative Model Evaluation**: Multiple models were tested, with **Model 4** (including all predictors) yielding the best performance.

## Technical Notes

### **Dataset & Preprocessing**
- **Source**: Kaggle dataset compiled from **Tiffany & Co. 2017 price list**.
- **Size**: **53,940 observations** with detailed attributes on cut, color, clarity, and price.
- **Data Cleaning**:
  - Removed **20 records** with zero values in dimensional attributes.
  - Carat and price were **log-transformed** to mitigate skewness.
  - Multimodal distributions suggest **carat preferences align with market symmetry trends**.

### **Regression Model Development**
- **Baseline Model**: A simple regression using **carat weight alone** achieved an **R² of 0.932**.
- **Final Model**: Included **carat, cut, color, and clarity**, achieving an **R² of 0.984**.
- **Regression Formula**:
  ```
  log(price) = β0 + β1 * log(carat) + β2 * cut + β3 * color + β4 * clarity
  ```
- **Findings**:
  - **Carat** remains the dominant predictor.
  - **Clarity improvements (I1 → IF)** increase price by a factor of **3.19**.
  - **Color upgrades (J → D)** increase price by **66%**.
  - **Cut upgrades (Fair → Very Good)** increase price by **16%**.
  
### **Model Comparison & Performance**
- **Model 1**: Carat only (**R² = 0.932**)
- **Model 2**: Carat + Clarity (**R² = 0.969**)
- **Model 3**: Carat + Clarity + Color (**R² = 0.982**)
- **Model 4**: Carat + Clarity + Color + Cut (**R² = 0.984**, best-performing model)

### **Limitations**
- **Dataset Bias**: Focused on **luxury-grade diamonds**, limiting generalizability.
- **Omitted Features**: Diamond **shape** was not included but likely influences pricing.
- **Market Fluctuations**: Prices may have changed since **2017**, affecting model accuracy.

## License
This project is released under an open-source license. See [LICENSE](LICENSE) for details.

## Contact
For any questions or discussions regarding this project, feel free to reach out to the authors:
- **Thomas Dolan**
- **Kemalcan Jimmerson**
- **Curtis Escobar Rood**
- **Sean Kenny**

