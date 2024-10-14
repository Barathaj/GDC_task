# Loan Approval Prediction

## Overview

This project aims to predict whether a loan will be approved or not based on several personal and loan-related attributes. The machine learning model developed here uses a dataset with features such as age, income, employment length, and loan intent. The model will help financial institutions automate and streamline the loan approval process.

## Dataset

The dataset contains the following columns:

- `id`: Unique identifier for each record
- `person_age`: Age of the applicant
- `person_income`: Annual income of the applicant
- `person_home_ownership`: Type of home ownership
- `person_emp_length`: Employment length in years
- `loan_intent`: Purpose of the loan
- `loan_grade`: Credit grade assigned to the applicant
- `loan_amnt`: Amount of the loan requested
- `loan_int_rate`: Interest rate on the loan
- `loan_percent_income`: Percentage of the applicant's income being used to repay the loan
- `cb_person_default_on_file`: Whether the applicant has defaulted on their credit file
- `cb_person_cred_hist_length`: Length of the applicant's credit history
- `loan_status`: Target variable (Loan approved or not)

The target variable for prediction is the `loan_status`.

## Project Workflow

1. **Data Collection**:
   - The data was collected and loaded into the project environment. The features include applicant personal details, loan details, and credit history data.

2. **Data Cleaning**:
   - Cleaned the dataset by handling missing values and converting the necessary columns to appropriate data types for the model.

3. **Data Visualization**:
   - Visualized the relationships between features using **Matplotlib** and **Seaborn** to better understand the data.

4. **Model Building**:
   - The model used for prediction is **CatBoostClassifier**, chosen for its strong performance on categorical data.
   - The data was split using **StratifiedKFold** to maintain the balance of classes (approved vs. not approved) across all folds.
   - The model was evaluated using **Area Under the Curve (AUC)** to measure its ability to distinguish between approved and non-approved loans.

5. **Training Process**:
   - The model was trained with the following hyperparameters:
     - `depth`: 8
     - `learning_rate`: 0.1979
     - `iterations`: 300
     - `bagging_temperature`: 0.7779
     - `l2_leaf_reg`: 5
     - `eval_metric`: AUC
   - The training process involved 5-fold cross-validation to ensure consistent and reliable results.

6. **Model Evaluation**:
   The model was evaluated on both training and validation sets for each fold. The AUC scores for the cross-validation folds are as follows:

   - **Fold 1**: Train AUC: 0.9744, Validation AUC: 0.9548
   - **Fold 2**: Train AUC: 0.9773, Validation AUC: 0.9650
   - **Fold 3**: Train AUC: 0.9809, Validation AUC: 0.9608
   - **Fold 4**: Train AUC: 0.9730, Validation AUC: 0.9632
   - **Fold 5**: Train AUC: 0.9792, Validation AUC: 0.9597

   **Overall Results**:
   - **Train AUC**: 0.9770
   - **Validation AUC**: 0.9607

   The model achieved an overall validation accuracy of **97%**, indicating strong performance in predicting loan approvals.

## Submission

After training, the model was used to generate predictions on the test set. The submission file contains the following columns:
- `id`: Unique identifier for each record
- `loan_status`: Predicted loan status (approved or not)

The model's submission file reflects an accuracy of **97%**, making it highly effective in predicting loan approvals.

### Performance Metrics

The model was evaluated using the **AUC (Area Under the Curve)** metric. Here are the results for each fold:

| **Fold** | **Train AUC** | **Validation AUC** |
|:--------:|:-------------:|:------------------:|
| Fold 1   | 0.9744        | 0.9548             |
| Fold 2   | 0.9773        | 0.9650             |
| Fold 3   | 0.9809        | 0.9608             |
| Fold 4   | 0.9730        | 0.9632             |
| Fold 5   | 0.9792        | 0.9597             |

- **Overall Train AUC**: 0.9770
- **Overall Validation AUC**: 0.9607

### Test Predictions

The final predictions on the test data were generated, and the model achieved a **97% accuracy** on the test set.

## Submission

The model's predictions were saved in a CSV file that includes:
- **id**: The loan applicant's ID.
- **loan_status**: The predicted loan approval status (probability score).

## Google Colab Link :

**https://colab.research.google.com/drive/1EhEJNdYW1z1AZ8-72kV28_ATdiJlEiYi?usp=sharing**

## Conclusion

This project successfully demonstrates the process of building a machine learning model to predict loan approval status. With a validation AUC score of **96.07%** and test set accuracy of **97%**, the model performs well in predicting loan approvals.


## Code Execution

### Steps to run the code:
Clone the repository:
   ```bash
   git clone https://github.com/yourusername/loan-approval-prediction.git
   #Run
   app.ipynb
  ```
