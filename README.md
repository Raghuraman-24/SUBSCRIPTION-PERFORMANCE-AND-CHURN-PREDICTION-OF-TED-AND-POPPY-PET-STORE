# Subscription Performance and Churn Prediction for a Pet Food Subscription Service

## Executive Summary

This project analyzes subscription performance and predicts customer churn for an international pet food subscription service operating under the Ted & Poppy Pet Store brand. The analysis uses a structured customer-level dataset containing demographic, behavioral, engagement, payment, and satisfaction-related variables. A combination of descriptive analytics and supervised classification models was applied to understand churn drivers and identify customers at risk of cancelling their subscriptions. Multiple models were evaluated, with LightGBM selected based on predictive performance and computational efficiency. The results indicate that customer satisfaction, support interactions, payment-related issues, and geographic location are key factors associated with churn, with approximately 23.5 percent of customers predicted to churn in the evaluated period.

## Problem Statement

The analysis supports the business decision of how to reduce customer churn in a subscription-based pet food delivery service. As the company expands internationally, churn directly impacts recurring revenue, customer lifetime value, and operational planning. The project focuses on identifying key variables associated with churn and building a predictive model to flag at-risk customers for targeted retention strategies. The scope is limited to historical subscription and interaction data for a single analysis period, and results are intended to inform tactical retention actions rather than long-term demand forecasting.

## Data Overview

The dataset consists of a transformed customer-level table containing 29 variables related to demographics, purchase behavior, customer engagement, satisfaction survey responses, payment activity, and support tickets. The data represents approximately 50,000 customers drawn from a larger base of roughly 200,000 active subscriptions during Q4 2024. The data is a fictional study case created for academic analysis and does not represent real customer records. Known limitations include survey non-response, potential class imbalance between retained and churned customers, and the absence of longitudinal behavioral history beyond the analysis window.

## Methodology

The analytical workflow began with data ingestion and cleaning, including variable categorization, consistency checks, and preparation for modeling. Exploratory data analysis was conducted to examine churn rates across satisfaction levels, payment status, support ticket activity, subscription packages, and geographic regions. Feature engineering focused on grouping variables into interpretable categories and conducting bivariate analysis to assess relationships with churn. The dataset was partitioned into training (75 percent) and testing (25 percent) subsets. Multiple classification models were trained and evaluated, including logistic regression, k-nearest neighbors, random forest, XGBoost, and LightGBM. Model evaluation used accuracy, sensitivity, F1-score, and confusion matrix analysis, with additional consideration given to scalability and computational efficiency.

## Results and Insights

Approximately 15 percent of customers in the observed period churned, while 85 percent were retained. The final LightGBM model achieved an accuracy of approximately 83 percent on the test set and identified around 86 percent of retained customers and 90 percent of churners with reduced false positives. The model predicts that roughly 23.5 percent of customers in the evaluation cohort are at risk of churning. Key observations include high churn rates among customers who did not respond to satisfaction surveys and among some satisfied customers who churned without recorded payment issues. Customer satisfaction, support ticket activity, payment reliability, and location emerged as the most influential predictors. These findings suggest opportunities for targeted retention interventions, particularly for disengaged or underserved customer segments.

## Repository Structure

The repository is organized to separate data, analysis, and outputs for clarity and reproducibility. Processed data files are stored under the data directory. Analytical notebooks and scripts implementing exploratory analysis, feature engineering, and modeling are located in the notebooks and scripts directories. Model artifacts are saved in a dedicated models folder, while generated figures, tables, and reports are stored under outputs. Supporting documentation and project summaries are included in the docs directory, and the root contains configuration files such as the README and environment specifications.

## Technologies and Dependencies

The project is implemented in R. Core libraries include tidyverse for data manipulation and visualization, caret for model training and evaluation, and machine learning libraries supporting tree-based and gradient boosting models. The analysis assumes a local R environment with standard statistical and modeling packages installed. Exact package versions are documented in the project environment configuration.

## How to Run the Project

To reproduce the analysis locally, install R and the required packages listed in the environment configuration file. Clone the repository and ensure the processed dataset is available in the expected data directory. Execute the notebooks or scripts in sequential order, starting with data preparation and exploratory analysis, followed by feature engineering and model training. Model evaluation outputs and figures will be generated in the outputs directory. The project is designed for local execution without external service dependencies.

## Assumptions and Limitations

The analysis assumes independent customer observations and no severe multicollinearity among selected predictors. The fictional nature of the dataset limits external validity and generalizability to real-world subscription businesses. Churn is treated as a binary outcome within a fixed observation window, and temporal dynamics are not explicitly modeled. Survey non-response and potential reporting bias may affect the interpretation of satisfaction-related findings. Predictive performance is evaluated on a holdout test set but not validated on external data.

## Future Work

Future extensions could incorporate longitudinal customer behavior to model churn over time and estimate customer lifetime value. Additional feature engineering using interaction terms or temporal aggregates may improve predictive performance. Model calibration and threshold optimization could better align predictions with specific business objectives. Incorporating cost-sensitive learning or uplift modeling would support more targeted and efficient retention strategies.
