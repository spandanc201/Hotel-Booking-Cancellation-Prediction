# Hotel-Booking-Cancellation-Prediction

## Overview

Predict based on various given categorical and quantitative variables whether or not a customer is likely to cancel their booking with a hotel.


## Dataset

The dataset is stored in `Data/booking.csv` file with both categorical and numerical features.

### Target Variable

We want to preict `booking status` as to whether or not a booking was canceled or not.

### Features

There are different features included in the dataset: 

- `number of adults`
- `number of children`
- `number of weekend nights`
- `number of week nights`
- `type of meal`
- `car parking space`
- `room type`
- `lead time`
- `market segment type`
- `repeated`
- `P-C` (amount of previous bookings canceled by customer)
- `P-not-C` (amount of previous bookings not canceled by customer)
- `average price`
- `special requests`
- `date of reservation`

## Preprocessing

### Steps

1. **Data Cleaning**
    - Null values were imputed using the most frequent value in teh feature column
    - Any duplicate rows were removed
2. **Feature Engineering**:
    - Categorical features were converted ot numerical features using one hot encoding
3. **Target Mapping**:
    - The `booking status` column was mapped to two binary values
4. **Train and Test Data Splitting**:
    - Split the training and test data
5. **Mitigate the Dummy Variable Trap from one-hot encoding**:
    - Avoided multicollinearity by deleting one dummy column for each categorical feature

## Model

Predictions are made using a **Random Forest Classification Model** on the processed dataset.

## Important Libraries

The important libraries are as follows:
- `scikit-learn`: used in preprocessing and model creation and also used in evaluation of the model
- `pandas`: data storage and manipulation
- `seaborn`: data visualization

## Evaluation

The performance of the model was analyzed through various metrics, as described below:

- **Accuracy**: simply how well the model performed
- **Precision**: out of all the predicted positives, how many were true positives
- **Recall**: out of all the true positives, how many were correctly predicted
- **F1-Score**: precision and recall harmonic mean
- **ROC-AUC Score**: a classification model metric to describe how well the model can distinguish between classes



Model metrics are provided below:

Confusion Matrix: 
[[4565  314]
 [ 498 1880]]

Classification Report: 
              precision    recall  f1-score   support

           0     0.9016    0.9356    0.9183      4879
           1     0.8569    0.7906    0.8224      2378

    accuracy                         0.8881      7257
   macro avg     0.8793    0.8631    0.8704      7257
weighted avg     0.8870    0.8881    0.8869      7257


ROC-AUC Score: 0.9450


## Usage

### Prerequisites

- Python 3.7 or higher
- Required libraries: `pandas`, `scikit-learn`, `seaborn`, `statsmodels`

### Steps to Run Code

1. Please clone the repository

```bash git clone <repository-url> cd Hotel-Booking-Cancellation-Prediction```

2. Install all dependencies

`pip install -r requirements.txt

3. Run Jupyter Notebook

`jupyter notebook main.ipynb`

The model had a ~89% accuracy and a 0.9450 ROC-AUC score, suggesting that the model performed very well in predicting cancellations.

In the future, I will be experimenting with Neural Netowkrs and Gradient Boosting and also hyperparameter tuning to make the model further accurate.


