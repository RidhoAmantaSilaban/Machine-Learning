# Project Titanic Survival Prediction

This notebook explores various supervised learning models (KNN, Naive Bayes, Decision Tree) to predict Titanic survival. It includes data loading, exploratory data analysis, feature engineering, model training, and evaluation.

## Models Implemented:

*   **K-Nearest Neighbors (KNN)**
*   **Naive Bayes (GaussianNB)**
*   **Decision Tree Classifier**

## Key Steps:

1.  **Data Preparation**: Loading `titanic.xlsx` and initial inspection.
2.  **Exploratory Data Analysis (EDA)**: Visualizing distributions and relationships (e.g., survival by sex, pclass, age).
3.  **Feature Engineering**: Handling missing values (imputing age) and encoding categorical features (sex, embarked).
4.  **Model Training**: Splitting data into train/test sets and training the models.
5.  **Evaluation**: Assessing model performance using accuracy, confusion matrices, and classification reports.
6.  **Hyperparameter Tuning (for KNN)**: Using `GridSearchCV` to find optimal parameters.

## Requirements:

*   `pandas`
*   `numpy`
*   `matplotlib`
*   `seaborn`
*   `scikit-learn`