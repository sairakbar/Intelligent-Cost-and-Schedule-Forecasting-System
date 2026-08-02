# Intelligent Construction Project Risk Prediction Platform

## Project Overview

This project develops an end-to-end machine learning risk prediction platform designed to identify construction activities that are likely to become overdue.

The objective was to transform traditional reactive project monitoring into a proactive risk management approach by using historical project data to predict potential delays before they occur.

The platform combines data preprocessing, feature engineering, machine learning classification, model evaluation, and risk categorisation to generate actionable insights for project decision-making.

---

# Business Problem

Construction projects generate large amounts of operational data, including task statuses, actions, priorities, workflow information, and historical delays.

However, project teams often identify risks only after delays have already affected project timelines.

The key business question:

**Can historical project activity data be used to predict which activities are likely to become overdue before the delay occurs?**

The goal of this project was to build a predictive early-warning system that helps project teams:

- identify high-risk activities earlier
- prioritise resources effectively
- improve project visibility
- reduce reactive problem-solving

---

# Dataset Overview

The dataset contains historical construction project activity records.

Dataset size:

**12,424 records**

Features include:

## Activity Information

- Status
- Type
- Priority
- Cause
- Task Group

## Timeline Information

- Days Open
- Days Since Status Change

## Project Workload Information

- Project Total Forms
- Project Total Actions
- Project Open Actions
- Project Overdue Forms

## Supporting Information Indicators

- Has Image
- Has Comment
- Has Document

---

# Target Variable

## Overdue Activity Prediction

This project was designed as a binary classification problem.

Target:

**Overdue**

Classes:

- 0 = Activity is not overdue
- 1 = Activity becomes overdue

The dataset contained a significant class imbalance, with overdue activities representing approximately 7% of total observations.

Because of this imbalance, model evaluation focused on risk detection metrics rather than accuracy alone.

---

# Machine Learning Workflow

## 1. Data Preparation

The raw project dataset was transformed into a machine-learning-ready format.

Steps included:

- data quality checks
- datatype validation
- missing value analysis
- feature selection
- numerical and categorical feature processing
- preprocessing pipeline creation

---

# 2. Exploratory Data Analysis

Analysed:

- overdue activity distribution
- feature relationships
- project workflow patterns
- operational risk indicators

Key finding:

A model predicting only the majority class would achieve high accuracy but fail to identify genuine project risks.

Therefore, the focus was placed on correctly identifying overdue activities.

---

# 3. Feature Engineering

Created predictive features representing project risk behaviour.

## Time-Based Features

Examples:

- Days Open
- Days Since Status Change

These captured activity ageing and workflow stagnation.

---

## Project Complexity Features

Examples:

- Project Total Actions
- Project Open Actions
- Project Total Forms

These represented workload and operational pressure.

---

## Information Availability Features

Examples:

- Has Image
- Has Comment
- Has Document

These represented supporting information available for each activity.

---

# 4. Model Development

## Algorithm Used

**XGBoost Classifier**

XGBoost was selected because it performs well on structured tabular datasets and captures complex relationships between operational variables.

Advantages:

- handles nonlinear relationships
- captures feature interactions
- performs strongly on classification problems
- widely used in risk modelling applications

---

# 5. Model Evaluation

Because the dataset was imbalanced, performance was evaluated using:

- Precision
- Recall
- F1-score
- ROC-AUC

## Final Model Performance

ROC-AUC:

**0.991**

The model demonstrated excellent ability to distinguish between overdue and non-overdue activities.

Overdue activity detection:

Precision:

**0.59**

Recall:

**0.96**

F1-score:

**0.73**

The high recall indicates that the model successfully identified the majority of activities that were likely to become overdue.

---

# Model Insights

## Feature Importance

The most influential features were:

1. Task Group

Certain project workstreams demonstrated higher delay risk patterns.

2. Days Open

Long-running activities showed increased probability of becoming overdue.

3. Type

Different activity categories displayed different risk profiles.

4. Days Since Status Change

Activities with limited recent progress were more likely to become delayed.

---

# Risk Categorisation

Model predictions were converted into business-friendly risk categories.

Risk Levels:

## Low Risk

2,117 activities

## Medium Risk

146 activities

## High Risk

222 activities

This enables project stakeholders to quickly identify where intervention may be required.

---

# Visual Results

## Model Performance

![Model Performance](./images/model_performance.png)

## Risk Distribution

![Risk Distribution](./images/risk_output.png)

## Feature Importance

![Feature Importance](./images/feature_importance.png)

---

# Project Structure

---

# Technologies Used

## Programming

- Python

## Data Analysis

- Pandas
- NumPy

## Machine Learning

- Scikit-learn
- XGBoost

## Visualisation

- Matplotlib
- Seaborn

## Development Tools

- Jupyter Notebook
- VS Code
- Git
- GitHub

---

# Key Skills Demonstrated

- Predictive modelling
- Risk analytics
- Classification algorithms
- Feature engineering
- Handling imbalanced datasets
- Model evaluation
- Machine learning pipelines
- Business-focused data interpretation
- Version control and documentation

---

# Future Improvements

Potential improvements include:

- implementing time-based validation
- adding SHAP model explainability
- deploying the model through an API
- creating an interactive risk dashboard
- integrating live project management data
- implementing model monitoring and retraining pipelines

---

# Business Impact

This project demonstrates how machine learning can enhance traditional project risk management by providing early-warning signals, helping teams identify potential delays earlier and supporting proactive decision-making.