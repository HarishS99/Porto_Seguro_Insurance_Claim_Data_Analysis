🚗 Porto Seguro Insurance Claim Risk Prediction

Porto Seguro Safe Driver Dataset
📌 Project Overview

This project focuses on predicting the probability that a policyholder will file an auto insurance claim in the following year using the Porto Seguro Safe Driver Prediction dataset from Kaggle. The objective is to build and compare multiple machine learning models while prioritizing ranking-based performance metrics such as ROC-AUC and the Gini Index, which are standard in insurance risk modeling.

The project demonstrates the complete machine learning pipeline—from data understanding and preprocessing to model evaluation and comparison—while highlighting the trade-offs between interpretability, complexity, and predictive performance.

🎯 Objectives

Predict insurance claim likelihood using anonymized driver, vehicle, and regional features

Handle severe class imbalance effectively

Compare baseline and advanced models using insurance-relevant metrics

Identify the best-performing model aligned with business objectives

Provide insights into model selection for structured tabular data

📂 Dataset Description

Source: Kaggle – Porto Seguro Safe Driver Prediction

Rows: ~595,000

Features: 57 anonymized predictors

Target: Binary (1 = Claim, 0 = No Claim)

Key Characteristics:

Severe class imbalance (~3–4% claims)

Mixed feature types (binary, categorical, continuous)

Missing values encoded as -1

Calculated features (ps_calc_*) with minimal predictive value

🔍 Exploratory Data Analysis (EDA)

EDA was conducted to:

Analyze target imbalance and feature distributions

Identify missing value patterns

Evaluate feature importance and noise

Validate competition insights (e.g., low signal in _calc features)

Key findings:

Predictive signal is largely additive and structured

A small subset of features dominates risk prediction

Proper preprocessing is critical for stable model performance

🧹 Data Preparation

Random under-sampling applied to address class imbalance

High-missing categorical features removed

Numerical features imputed using mean values

Calculated (_calc) features dropped

Categorical variables one-hot encoded

Final processed dataset saved as processed_data.xlsx

🤖 Modeling Strategy
Baseline Models

Logistic Regression

Decision Tree

Naïve Neural Network

Advanced Models

Wide & Deep Neural Network

XGBoost

LightGBM

Parsimonious (feature-reduced) models

Rank-weighted ensemble

⚙️ Hyperparameter Tuning

Grid Search and Random Search

ROC-AUC used as tuning objective

Class-weight optimization for imbalance

Neural network tuning (layers, units, dropout, learning rate)

Feature selection for parsimonious boosting models

📊 Evaluation Metrics

Given the imbalanced nature of the problem, evaluation focused on:

ROC-AUC

Gini Index

Sensitivity and Specificity

Confusion Matrix

Threshold Analysis

Accuracy was reported but not used as a primary metric.

🏆 Results Summary
Model	Gini Index
Decision Tree	0.19
Naïve Neural Network	0.22
Logistic Regression	0.24
LightGBM (Full)	0.2787
XGBoost (Full)	0.2811
LightGBM (Parsimonious)	0.2825
XGBoost (Parsimonious)	0.2850
Rank-Weighted Ensemble	0.2822
Wide & Deep Neural Network	~0.29

Best Performing Model:
✅ XGBoost (Parsimonious Feature Set)

📌 Key Conclusions

Model performance is driven more by data structure and feature quality than algorithmic complexity

Tree-based boosting models outperform deep neural networks on structured insurance data

Feature parsimony improves generalization and stability

Ranking-based evaluation is essential for real-world insurance use cases

🔮 Future Scope

Advanced feature engineering and interaction modeling

Embedding-based neural networks for categorical variables

Model stacking and meta-learning

Cost-sensitive optimization aligned with business loss functions

Integration of temporal or external data sources

👥 Contributors

Group V

Sanket Shah

Tushar Upadhyay

Shambhavi Dubey

Niraj Pawar

Harish Subramanian

Ankur

Kirti

Course: Machine Learning and Big Data
Instructor: Prof. Srikumar Krishnamoorthy
