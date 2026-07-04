# BCS-ML(under construction)
# README

This repository provides the source data, trained model parameters, and code used for constructing and evaluating the BCS-based machine learning models for predicting the thermochemical conversion behavior of the organic fraction of municipal solid waste (MSW).

## 1. Data_100 random divisions

This folder contains the code and results for evaluating the influence of random data partitioning on model performance.

For the complete experimental dataset, the data were randomly divided into training and test sets at a ratio of 7:3 for 100 independent repetitions. The performance of each model was evaluated on both the training and test sets for each random division.

The folder includes results for three models:

- XGB
- DNN
- MQR

This analysis was used to examine the stability of the constructed dataset distribution and to evaluate whether model performance was strongly affected by a specific random train/test split.

## 2. K-Fold tests

This folder contains the code and results for K-fold cross-validation.

The complete experimental dataset was evaluated using K-fold cross-validation with different values of K:

- K = 5
- K = 6
- K = 7
- K = 8
- K = 9
- K = 10

For each K value, the final performance metrics were calculated as the average results over the K training and test processes.

The folder includes results for three models:

- XGB
- DNN
- MQR

This analysis was used to further examine the stability of the dataset distribution and the influence of different train/test partition ratios on model evaluation.

## 3. Hyperparameter optimization

This folder contains the code and results for hyperparameter optimization.

For XGB, grid search was used as the main hyperparameter optimization method. In addition, Bayesian optimization code for XGB is also provided to demonstrate the consistency between the two optimization strategies.

For DNN, Bayesian optimization was used to determine the optimal network architecture and training-related hyperparameters.

The detailed hyperparameter settings are consistent with those described in the main manuscript and Supplementary Information.

## 4. DNN model train and test and verification

This folder contains the complete workflow for the DNN model under the optimized hyperparameters, including:

- Model training
- Model testing
- Prediction on the verification experiments
- Final verification of the BCS-DNN model

This part corresponds to the final BCS-DNN model used for the main prediction and verification results reported in the manuscript.

## 5. XGB and MQR train and test

This folder contains the code for constructing, training, and testing the XGB and MQR models.

The folder includes:

- XGB model training and prediction
- MQR model construction and prediction
- Model evaluation on the training and test sets

## 6. DNN_BP_4_48_final

This file contains the saved parameters of the final DNN model trained under the optimized hyperparameters.

The optimized DNN architecture is:

- Number of layers: 4
- Hidden size: 48

This saved model can be loaded directly for prediction and verification.

## 7. Train_Test_Verification_Data

This file contains all source data obtained from experiments and used for model construction, testing, and verification.

The file includes the following data:

### (1) Slow pyrolysis data of BCs

This sheet contains the slow-pyrolysis data of the nine base components (BCs), which were used for calculating the BCS coefficients.

The calculation method is described in detail in the Methods section of the manuscript. Briefly, after determining the category of an MSW component, the corresponding BCs were selected for coefficient calculation. The BCS coefficients were determined by setting a coefficient step size within the range of 0–1 and then using a traversal method to identify the coefficient combination that produced the curve closest to the experimental conversion curve of the MSW component.

### (2) Experimental data of all BCs

This part contains the experimental data of all base components (1BC, 2BCs,3BCs and ≥4BCs), which were used for dataset construction and dataset-distribution analysis.

### (3) Data for model training and testing

This part contains the processed input and output data required for model training and testing.

### (4) Data for model verification

This part contains the model inputs for the verification experiments and the corresponding experimental results used for independent model verification.

