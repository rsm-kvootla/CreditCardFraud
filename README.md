# CreditCardFraud
Developing a High-Precision Machine Learning Model to Detect Fraud and Maximize Financial Savings

This repository contains the full pipeline for building a high-precision fraud detection model on a dataset of 98,000+ credit card transactions from 2010. The project focuses on data-driven feature engineering and machine learning modeling to maximize financial savings by accurately flagging fraudulent transactions.

**Objective**\
To develop a deployable fraud detection model that:

Surfaces the highest-risk transactions with high precision

Achieves financial efficiency by balancing false positives and true fraud recovery

Leverages behavioral, geographic, and temporal signals in transaction data

**Dataset**\
98,393 credit card transactions from a U.S.-based financial institution

Includes card number, date, merchant info, transaction type, amount, and fraud flag

Contains both categorical and numerical fields

Highly imbalanced with ~2.5% fraud rate

**Workflow Overview**
1. Data Exploration
Initial profiling and visualization of transaction distributions (amounts, locations, types) to identify patterns and anomalies.

2. Data Cleaning & Variable Engineering
Handled missing values using contextual imputations

Removed system artifacts and extreme outliers (e.g., $3M transaction)

Engineered over 1,000 new variables capturing user behavior, merchant patterns, geography, and time-based signals (e.g., Benford's Law, travel distance, transaction surges)

3. Feature Selection
Combined univariate filtering and wrapper-based model evaluation (using LightGBM, Random Forest, CatBoost)

Final model trained on 20 top-performing features selected via forward selection

4. Modeling
Tested various models:

Decision Tree

Random Forest

LightGBM

CatBoost

Neural Network (final model)

The final model, a neural network (MLP with layers [30, 10]), achieved an OOT FDR@3% of 64.6%, delivering an estimated $61M in annual net savings using a cost-benefit cutoff strategy.

**Financial Optimization**\
Score thresholds were evaluated based on a financial cost model:

$400 gain per fraud caught

$20 loss per false positive investigation
Optimal cutoff: Bin 5, maximizing savings while minimizing false positives.

**File Execution Order**\
To reproduce results, run the Jupyter notebooks/scripts in this order:

Data explore vs1_3.ipynb

transactions clean make variables.ipynb

transactions feature selection vs 1_1.ipynb

transaction_models.ipynb

**Results Summary**\
Model	OOT FDR@3%\
Neural Network	0.646\
LightGBM	0.589\
CatBoost	0.614\
Random Forest	0.576\
Decision Tree	0.549

**Data**\
data - card transactions_2025


