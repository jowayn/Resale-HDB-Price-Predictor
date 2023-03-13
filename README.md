# Resale-HDB-Price-Predictor

A tool based on the XGBoost Regressor to predict resale prices of HDB flats in Singapore. Done as part of an assignment in the NUS module EE4802 Learning from Data. 

## Usage

Use this tool with Google Colab by importing this notebook onto Google Colab (File > Open Notebook). Download 201701to202303_processed.csv and place it into the same folder as the notebook before running. 

If running the notebook locally, also make sure 201701to202303_processed.csv is in the same folder.

## Training Background

The strategy taken was to use data from the year 2022 to present time as the testing data, as it is practical to train data based on an earlier time period in order to get a good gauge of the prices in the future. Data from the start of 2017 to the end of 2021 was used as the training data. The resulting split resulted in a training data size of 116, 676 and testing data of size 31, 601, which roughly translates to 78.7% of the dataset used as training data and 21.3% of the total dataset as testing data.

## Methodology

GridSearchCV with 5-Fold Cross Validation was used to tune the hyperparameters in this model. The optimal parameters found are:
{'learning_rate': 0.2 'max_depth': 6 'n_estimators': 500}
After obtaining the best parameters, the model was retrained with the entire dataset to produce this tool. 

## Model Metrics

- R^2 of Training data: 0.971 
- RMSE of Predictions: 47758 
- R^2 of Testing Data: 0.921

### Find information about the valid inputs for town and flat models here:

![inputs](/valid_inputs.png)
