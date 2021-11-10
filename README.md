# XAI-Shapash

## Description

This Jupyter Notebook can be used to create a Shapash Dashboard with an existing model. It can also generate comparison plots to compare specific instances in the dataset.

## Setup

`pip install shapash`

## Notes

Please take note that the your model should be saved as a pickle file and the dataset to load is in csv format. A file dialog pop-up is used to choose the respective files. 

## Introduction

We have identified a shortcoming of using advanced machine learning models – interpretability. The predictive model that we have built involves predicting recidivism and it is especially important to understand how a specific prediction of an inmate is being made. In the field of criminology, many researchers have described AI as “narrow” as it can be used as a tool to accomplish goals, but it is not aligned with interests of the persons they affect. To tackle the opacity of explanations behind every conclusion, a lot of effort is diverted to XAI which will be a requirement for using AI in criminology. 

## Instructions

### Choose model pickle file:

Choose a model pickle file to use for the Shapash Dashboard. Shapash is compatible with most sklearn, lightgbm, xgboost, catboost models. 

### Choose X_test csv or new X data:

Choose a csv file for your X_test or new data (with the same variables that the model is trained on) to be used for analysis.

### Enter Shapash Dashboard Title:

Enter the title to be shown at the top of the dashboard when prompted.

### Create Shapash Dashboard:

When the function `create_shapash()` is ran, a Shap TreeExplainer backend is used. The dashboard will be loaded on http://localhost:8050/. Open a new tab/ window to view it.

### Closing the Dashboard:

To stop running the dashboard, the function `app.kill()` can be ran to close it.

### Compare Local Explanation of Selected Indices:

To further analyse and compare instances (i.e. indices) across various features, the function `compare_local()` can be used. 

When prompted, input each index separated by commas (e.g. 1,2,3) and press enter.

The parameters for `compare_local()` function are:
* xpl - SmartExplainer object that is declared earlier
* index_list - a list of indices (of instances) to analyse
* max_features - maximum number of features to display (default = 10)
