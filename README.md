## Predicting Credit Card Default

This project aims to predict credit card defaults using demographic and credit information from 30,000 clients in Taiwan. The data encompasses 24 distinct features including demographic details and historical payment records from April to September 2005. The primary challenge of this project is to predict whether a client will default on their next month's payment, framing it as a binary classification problem.

## Project Overview

**1. Introduction:**

Credit card default prediction is crucial for financial institutions to mitigate losses and refine their lending practices. This project employs the Default of Credit Card Clients Dataset, which includes 24 features capturing demographic and credit information of clients from April to September 2005. 

**2. Goals:**

* Achieve an F1-score surpassing a baseline classifier for the minority class (potential defaulters).
* Employ feature engineering techniques to enhance model performance.
* Uncover key factors driving credit card defaults for informed decision-making.

**3. Data Exploration and Understanding:**

* Analyzed categorical variables (sex, education, marital status) to understand their influence on default rates.
* Examined numerical variables (credit limit, age, bill amounts, payment amounts) and visualized their distributions.
* Identified a significant class imbalance, highlighting the need for appropriate handling during model training.

* ![iScreen Shoter - Arc - 240609163239](https://github.com/olyaiy/credit-default-prediction/assets/97487352/fefd0ef3-288e-484e-903a-c2b046cc9478)

* ![iScreen Shoter - Arc - 240609163247](https://github.com/olyaiy/credit-default-prediction/assets/97487352/5223ffd0-4fe1-43e5-90f0-6c9b5116e677)



**4. Data Preparation and Transformation:**

* Addressed inconsistencies in categorical variables (education and marriage).
* Split data into training and testing sets (70/30 split).
* Implemented preprocessing steps:
    * Standardized numerical features using `StandardScaler`.
    * One-hot encoded binary and categorical features using `OneHotEncoder`.
    * Ordinal encoded payment status features using `OrdinalEncoder`.

**5. Model Selection and Evaluation:**

* Established a baseline using a `DummyClassifier` with the 'most_frequent' strategy.
* Trained and evaluated various models:
    * **Logistic Regression:** Implemented with `SMOTE` oversampling and `GridSearchCV` for hyperparameter tuning.
    * **XGBoost:**  Utilized `GridSearchCV` to optimize hyperparameters over a stratified k-fold cross-validation, resulting in the best performance.
    * **SVM:** Employed `RandomizedSearchCV` due to computational intensity, exploring 'rbf' and 'poly' kernels.
    * **Decision Tree:** Optimized using `GridSearchCV` for hyperparameters like `max_depth`, `min_samples_split`, and `min_samples_leaf`.

**6. Final Model Evaluation and Interpretation:**

* Selected the optimized XGBoost model as the final model based on its superior performance.
* Evaluated the final model on the test set, achieving an accuracy of 80.89% and an F1-score of 0.50.
* Analyzed feature importances to understand the most influential factors driving predictions.
* Visualized feature importances, revealing key predictors such as recent payment delays, gender, marital status, and education level.

![iScreen Shoter - 20240609163258559](https://github.com/olyaiy/credit-default-prediction/assets/97487352/8ff9ad44-ebe8-4ac6-9b62-b599abf13b1e)


**7. Conclusion and Recommendations:**

* The project successfully developed an XGBoost model capable of predicting credit card defaults with reasonable accuracy.
* Further research could explore:
    * Incorporating a larger, more diverse dataset across different regions and timeframes.
    * Experimenting with advanced techniques like deep learning.
    * Utilizing real-time transaction data and more detailed behavioral profiles.

## Getting Started

1. Clone the repository: `git clone https://github.com/your-username/credit-card-default-prediction.git`
2. Navigate to the project directory.
3. Install the required libraries.
4. Explore the Jupyter notebooks or Python scripts to understand the project workflow.

## Acknowledgments

* The project utilizes the Default of Credit Card Clients Dataset from the UCI Machine Learning Repository.
* The code implementation draws inspiration from various online resources and libraries like scikit-learn, XGBoost, and Imbalanced-learn. 
