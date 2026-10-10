# BCS-ML

This repository contains the source data, trained model parameters, and code used for constructing and evaluating BCS-based machine learning models for predicting the thermochemical conversion behavior of the organic fraction of municipal solid waste (MSW).

## Repository contents

```text
BCS-ML/
├── Train_Validation_Verification_Data_revised.xlsx
├── 1.Data_100 random divisions.ipynb
├── 2.K-Fold test.ipynb
├── 3.Hyperparameter optimization.ipynb
├── 4.DNN Training_Validation_External Verification.ipynb
├── 5.XGB and MQR train and validation.ipynb
├── DNN_para_final.pth
├── LICENSE
└── README.md
```

## Data

The main data file is:

```text
Train_Validation_Verification_Data_revised.xlsx
```

This file contains the experimental and processed data used for model training, validation, cross-validation, and external verification.

The main worksheets include:

- `Train`: training data used for model fitting.
- `Val`: validation data used for model evaluation during model development and early stopping.
- `Verification-inputs`: input features for the 15 independent practical MSW verification experiments.
- `Verification experiments`: experimental results for the 15 independent practical MSW verification experiments.
- `100 divisions_K-folds`: complete dataset used for 100 repeated random divisions and K-fold cross-validation.
- `1BC`: fast-pyrolysis TG data of the nine individual base components.
- `Slow pyrolysis results of BCs`: slow-pyrolysis TG data used for BCS construction and BCS coefficient calculation.

## Code

### 1. Data_100 random divisions

```text
1.Data_100 random divisions.ipynb
```

This notebook evaluates the influence of random data partitioning on model performance. The dataset is randomly divided into training and validation sets at a 7:3 ratio for 100 independent repetitions.

Models included:

- XGB
- DNN
- MQR

### 2. K-Fold test

```text
2.K-Fold test.ipynb
```

This notebook performs group-level K-fold cross-validation using experiment-level splitting.

The evaluated K values are:

- K = 5
- K = 6
- K = 7
- K = 8
- K = 9
- K = 10

Models included:

- XGB
- DNN
- MQR

### 3. Hyperparameter optimization

```text
3.Hyperparameter optimization.ipynb
```

This notebook contains the hyperparameter optimization procedures for XGB and DNN.

For XGB, grid search was used as the main optimization method, and Bayesian optimization was also provided for comparison. For DNN, Bayesian optimization was used to determine the optimized network architecture.

The final optimized DNN architecture is:

- Number of layers: 4
- Hidden size: 48

### 4. DNN Training, Validation, and External Verification

```text
4.DNN Training_Validation_External Verification.ipynb
```

This notebook provides the complete workflow for the final DNN model, including model training, validation-set-based early stopping, checkpoint saving, model evaluation, and prediction for the 15 independent practical MSW verification experiments.

The saved DNN checkpoint is:

```text
DNN_para_final.pth
```

### 5. XGB and MQR train and validation

```text
5.XGB and MQR train and validation.ipynb
```

This notebook contains the training and validation workflows for XGB and MQR, including model construction, prediction, and performance evaluation.

## Model file

```text
DNN_para_final.pth
```

This file contains the saved parameters of the final DNN model trained under the optimized hyperparameters.

## Running the code

Before running the notebooks, place the following file in the working directory or update the `data_path` variable in each notebook:

```text
Train_Validation_Verification_Data_revised.xlsx
```

The notebooks can be run in the following order:

```text
1.Data_100 random divisions.ipynb
2.K-Fold test.ipynb
3.Hyperparameter optimization.ipynb
4.DNN Training_Validation_External Verification.ipynb
5.XGB and MQR train and validation.ipynb
```

The final BCS-DNN prediction and external verification results can be reproduced using:

```text
4.DNN Training_Validation_External Verification.ipynb
```

## Requirements

The code requires Python and the following packages:

- pandas
- numpy
- matplotlib
- scikit-learn
- xgboost
- torch
- scikit-optimize
- openpyxl

The packages can be installed using:

```bash
pip install pandas numpy matplotlib scikit-learn xgboost torch scikit-optimize openpyxl
```

## License

This repository is released under the MIT License.

## Citation

If you use this repository, please cite:

Chen, F. et al. Code for “The Base Component System (BCS) of Thermochemical Conversion of Municipal Solid Waste.” BCS-ML. https://doi.org/10.5281/zenodo.23273634 (2026).
