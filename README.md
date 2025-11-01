# DAiSEE Dataset Analysis and Preprocessing

This project focuses on the preprocessing and analysis of the DAiSEE (Dataset for Affective States in E-Environments) dataset. The goal is to prepare the data for training a model to predict student engagement levels.

## Dataset

The dataset consists of the following files:

- `daisee_train_features.csv`: Features for the training set.
- `daisee_test_features.csv`: Features for the test set.

The original dataset also included `daisee_val_features_balanced.csv` and `daisee_test_features_balanced.csv`, which contained synthetic data and were deleted to ensure the model is trained and evaluated on real data.

## Preprocessing and Exploratory Data Analysis (EDA)

The preprocessing and EDA were performed in the `01-EDA-and-Preprocessing.ipynb` Jupyter notebook. The following steps were taken:

1.  **Data Loading:** The training and test datasets were loaded into pandas DataFrames.
2.  **Data Inspection:** The `head()` and `info()` methods were used to inspect the data and check for missing values.
3.  **Visualization:** The distribution of the target variable, 'engagement', was visualized using count plots to understand the class distribution.

## Class Imbalance

The initial analysis revealed a significant class imbalance in both the training and test datasets. The distribution of the 'engagement' levels was heavily skewed towards certain classes.

## Class Balancing using SMOTE

To address the class imbalance, the Synthetic Minority Over-sampling Technique (SMOTE) was used. SMOTE creates synthetic samples from the minority class instead of creating duplicates. This technique was applied to both the training and test datasets to create balanced class distributions.

The `imblearn` library was used to implement SMOTE. The steps were as follows:

1.  The features (X) and target (y) variables were separated.
2.  The `SMOTE` algorithm was fitted to the data.
3.  The resampled data was visualized to confirm the balanced class distribution.

## File Deletion

The following files containing synthetic data were deleted:

- `daisee_val_features_balanced.csv`
- `daisee_test_features_balanced.csv`

## How to Run

To reproduce the analysis, you can run the `01-EDA-and-Preprocessing.ipynb` notebook in a Jupyter environment. Make sure you have the required libraries installed:

- pandas
- matplotlib
- seaborn
- scikit-learn
- imblearn
