# Subscription Performance and Churn Prediction – Ted & Poppy Pet Store

## Overview
This project implements an end-to-end machine learning pipeline to predict customer churn for a subscription-based business.  
It identifies at-risk customers and quantifies the key factors driving churn to support targeted retention strategies.

---

## Project Files

| File / Folder | Description |
|---------------|-------------|
| `Dataset/` | Contains the raw dataset and supporting metadata used for churn analysis |
| `Dataset/tedpoppydata_final.csv` | Customer-level subscription dataset (~200,000 rows, 29 variables) |
| `Dataset/ted and poppy metadata.csv` | Variable definitions, feature categories, and modeling assumptions |
| `Subscription model - predictive analysis.qmd` | Main Quarto file containing data preprocessing, EDA, model training, evaluation, and interpretation |
| `Poster.pdf` | Executive-level visual summary of the problem, methodology, results, and recommendations |
| `README.md` | Project documentation and technical overview |

---

### Quick Access Links
- **Dataset & Metadata:**  
  https://github.com/Raghuraman-24/SUBSCRIPTION-PERFORMANCE-AND-CHURN-PREDICTION-OF-TED-AND-POPPY-PET-STORE/tree/main/Dataset
- **Model Code (R / Quarto):**  
  https://github.com/Raghuraman-24/SUBSCRIPTION-PERFORMANCE-AND-CHURN-PREDICTION-OF-TED-AND-POPPY-PET-STORE/blob/main/Subcription%20model%20-%20predictive%20analysis.qmd
- **Poster (Results Summary):**  
  https://github.com/Raghuraman-24/SUBSCRIPTION-PERFORMANCE-AND-CHURN-PREDICTION-OF-TED-AND-POPPY-PET-STORE/blob/main/Poster.pdf
---

## Problem Statement
Subscription-based businesses often lack early warning signals to identify customers who are likely to churn, resulting in reactive and inefficient retention efforts.

This project addresses:
- Poor visibility into churn drivers
- Over-reliance on blanket retention campaigns
- Difficulty prioritizing customer outreach

**Who needs this system:**
- Business teams managing subscription performance
- Data and analytics teams supporting customer retention

**Assumptions and constraints:**
- Batch-based analysis (no real-time inference)
- Static historical dataset
- Emphasis on interpretability and business relevance over low-latency deployment

---

## Design and Architecture
The system is structured as a reproducible analytical pipeline implemented in R.

**High-level architecture:**
- Static data ingestion (CSV)
- Feature engineering and preprocessing
- Exploratory data analysis
- Model training and comparison
- Model evaluation and interpretation
- Business-facing outputs

**Key components:**
- **Data Layer:** Subscription, satisfaction, payment, and support data
- **Feature Engineering Layer:** Variable categorization and transformation
- **Modeling Layer:** Supervised classification models
- **Evaluation Layer:** Performance metrics and confusion matrix
- **Output Layer:** Predictions, insights, and visual summaries

**Data flow:**
Raw data → Cleaning & feature engineering → Model training → Evaluation → Insights

---

## Dataset and Metadata

### Dataset
- **Location:**  
  - https://github.com/Raghuraman-24/SUBSCRIPTION-PERFORMANCE-AND-CHURN-PREDICTION-OF-TED-AND-POPPY-PET-STORE/blob/main/Dataset/tedpoppydata_final.csv

- **Description:**  
  Customer-level subscription data for a fictional pet food subscription service (Ted & Poppy Pet Store), representing Q4 2024 activity.

- **Size:**
  - ~200,000 customer records (full dataset)
  - 50,000 customers used for model evaluation

- **Structure:**
  - **Rows:** Customer-level observations
  - **Columns:** 29 variables
  - **Target variable:** Customer churn (binary)

- **Data types:**
  - Numeric (usage, frequency, tenure)
  - Categorical (location, subscription type)
  - Binary indicators (payment issues, support tickets, survey response)

- **Feature categories:**
  - Demographics
  - Purchase behavior
  - Customer engagement
  - Customer satisfaction
  - Payment and support interactions

- **Data characteristics:**
  - Tabular, structured CSV format
  - No personally identifiable information (PII)
  - No external or real-time data dependencies

### Metadata - 
- **Location:**  
  Included within the same `Dataset/` directory 
  - https://github.com/Raghuraman-24/SUBSCRIPTION-PERFORMANCE-AND-CHURN-PREDICTION-OF-TED-AND-POPPY-PET-STORE/blob/main/Dataset/ted%20and%20poppy%20metadata.csv

- **Purpose:**  
  Documents variable definitions, assumptions, and feature categorization to improve transparency, auditability, and interpretability.

---

## Key Technical Decisions
- **R + Quarto (`.qmd`)** chosen for reproducible, well-documented analysis
- **Multiple model comparison** to reduce model-selection bias
- **LightGBM selected** based on performance and scalability
- **Recall and F1-score prioritized** to minimize missed churners
- **75/25 train-test split** to prevent data leakage

**Tradeoffs:**
- No streaming or real-time inference
- No automated hyperparameter tuning
- Static dataset instead of continuously refreshed data

---

## Implementation Details
- Variables categorized into logical business groups before modeling
- Feature engineering applied consistently across all models
- Churn treated as a binary classification problem
- Confusion matrix used to assess false positives vs false negatives
- All transformations and assumptions explicitly documented in code

**Code (R / Quarto):**  
https://github.com/Raghuraman-24/SUBSCRIPTION-PERFORMANCE-AND-CHURN-PREDICTION-OF-TED-AND-POPPY-PET-STORE/blob/main/Subcription%20model%20-%20predictive%20analysis.qmd

---

## Output and Key Takeaways

### Model Performance (Based on Poster Results)
- **Final model:** LightGBM
- **Prediction accuracy:** 83%
- **Customers predicted to churn:** 23.5%
- **Churners correctly identified:** 90%
- **Low-risk customers correctly identified:** 86%

### Key Business Insights
Insights derived directly from model outputs and summarized in the project poster:

1. **Customer satisfaction is the strongest churn driver**  
   A significant share of churners either reported dissatisfaction or did not respond to satisfaction surveys.

2. **Customer issues matter even without payment failures**  
   33% of satisfied customers churned without payment issues, indicating non-transactional drivers of churn.

3. **Geography influences churn behavior**  
   Location-based patterns suggest market-specific retention strategies are required.

4. **Opportunity window for proactive retention**  
   Customers with no payment issues but low engagement present a clear intervention opportunity.

**Poster (Visual Summary):**  
https://github.com/Raghuraman-24/SUBSCRIPTION-PERFORMANCE-AND-CHURN-PREDICTION-OF-TED-AND-POPPY-PET-STORE/blob/main/Poster.pdf

---

## Testing Strategy
This project emphasizes analytical validation over application-level testing.

- Fixed train/test split
- Cross-model performance comparison
- Metric-based evaluation (Accuracy, Recall, F1-score)
- Manual inspection of confusion matrices to validate business impact

---

## Setup and Usage

### Requirements
- **Language:** R (>= 4.x)
- **Libraries:** tidyverse, caret, lightgbm, xgboost, randomForest, class, ggplot2
- **Format:** Quarto (`.qmd`)



