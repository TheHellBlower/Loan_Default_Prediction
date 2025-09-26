# Loan Default Prediction

---

## Project Motivation

Banks earn major revenue from lending loans, but this is often associated with the risk of borrowers defaulting. To mitigate this issue, this project aims to develop a robust Machine Learning model to classify if a new borrower is likely to default or not. The objective is to understand the provided dataset, clean it, build various classification models, fine-tune their hyperparameters, and compare their evaluation metrics to find the best performing model.

---

## Dataset

The dataset contains past data on loan borrowers. After initial loading and cleaning, the dataset consists of **255,347 rows** and **33 columns**.

The data includes various features about the borrowers, such as:
* Demographics (age, gender, etc.)
* Financial information (income, loan amount, credit history, etc.)
* Loan details (loan purpose, interest rate, etc.)
* A **`Default`** column which is the target variable (1 if the borrower defaulted, 0 otherwise).

---

## Preprocessing Steps

Several preprocessing steps were performed to clean and prepare the data for modeling:
1.  **Handling Missing Values**: Missing values in various columns were identified and handled appropriately.
2.  **Feature Engineering**: New features were created from existing ones to potentially improve model performance.
3.  **Encoding Categorical Variables**: Categorical features were converted into a numerical format using one-hot encoding.
4.  **Feature Scaling**: Numerical features were scaled using `StandardScaler` to bring them to a similar range, which is important for many machine learning algorithms.
5.  **Handling Imbalanced Data**: The dataset was imbalanced, so the `SMOTE` (Synthetic Minority Over-sampling Technique) was used on the training data to create a balanced dataset.

---

## Model Architecture

Several classification models were built and compared:
* **Logistic Regression**
* **Random Forest Classifier**
* **K-Nearest Neighbors (KNN) Classifier**
* **Support Vector Classifier (SVC)**
* **XGBoost Classifier**

The models were trained on the preprocessed and balanced training data.

---

## Training Details

* The dataset was split into a **training set (70%)** and a **testing set (30%)**.
* The split was stratified to maintain the same proportion of defaulters and non-defaulters in both sets.
* SMOTE was applied *only* to the training set to avoid data leakage.

---

## Evaluation Metrics

The models were evaluated using the following metrics:
* **Accuracy Score**
* **ROC AUC Score**
* **F1 Score**
* **Classification Report** (including precision and recall)
* **Confusion Matrix**

---

## Results & Conclusions

The performance of all the models was compared, and the **XGBoost Classifier** was found to be the best performing model with the highest accuracy and ROC AUC score on the test set. The project successfully demonstrates the use of machine learning to build a reliable model for predicting loan defaults, which can help banks mitigate risk and make better lending decisions.
