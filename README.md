# Detailed-Analysis-and-Strategic-Recommendations-Telecom-Customer-Churn-Report
This report dives into the Telecom Churn Rate Dataset, uncovering key insights on customer behavior, service usage, and payment preferences. It identifies primary churn drivers, such as monthly charges and contract types, and presents a predictive model with 86% accuracy. Practical recommendations help enhance customer retention and satisfaction.

![image](https://github.com/user-attachments/assets/be675f19-872b-4f3f-90dc-102bc2d9bdbe)

### Welcome to the Analyst League Challenge
In today’s fiercely competitive telecom industry, understanding customer behavior and predicting churn is essential for retaining customers and sustaining growth. This report delves deep into customer data from the Telecom Churn Rate Dataset, uncovering valuable insights and strategies for improving customer retention and satisfaction within the telecom sector.

# Dataset Overview

The Telecom Churn Rate Dataset provides comprehensive information on **customer demographics, service usage, contract details, and churn status. It includes customer ID, gender, senior citizen status, partner and dependent status, service usage metrics (e.g., phone service, internet service), contract types, payment methods, monthly charges, total charges, tenure, customer satisfaction metrics, and churn status.**

# Key columns include:

- customerID: Unique identifier for each customer.
- gender, SeniorCitizen, Partner, Dependents: Demographic details.
- tenure, PhoneService, MultipleLines, InternetService, OnlineSecurity, OnlineBackup, TechSupport: Service usage details.
- Contract, PaperlessBilling, PaymentMethod, MonthlyCharges, TotalCharges: Payment and contract details.
- Churn: Target variable indicating if the customer churned.

# Key Questions for Analysis

## Demographic Analysis
- How does the distribution of customers vary by gender and senior citizen status?
- What percentage of customers have partners or dependents?

## Service Usage
- What are the most and least used services among customers (PhoneService, MultipleLines, InternetService, etc.)?
- How does the tenure of customers correlate with their service usage?

## Payment and Contract Analysis
- What payment methods are most commonly used by customers?
- How do monthly charges and total charges vary across different contract types?
- Is there a significant difference in churn rates based on payment methods?

## Churn Prediction
- What is the churn rate among the customers?
- Which factors are most strongly associated with customer churn (e.g., monthly charges, tenure, contract type)?
- Can we build a predictive model to identify customers at high risk of churning?

## Ticket Analysis
- How many administrative and technical tickets have been raised by customers?
- Is there a correlation between the number of tickets and customer churn?

## Service Quality and Satisfaction
- How does the presence of online security, backup, and tech support services affect customer satisfaction and churn?

# Results and Interpretations

## Demographic Analysis:

![image](https://github.com/user-attachments/assets/e8cf9f1f-16b7-4bfa-a7a0-8a8439cb304c)

- Gender and Senior Citizen Status: The distribution of customers by gender is nearly equal, with a slightly higher number of female customers. About 16% of customers are senior citizens.
- Partners and Dependents: Approximately 49% of customers have partners, and 30% have dependents.

# Service Usage:

- Most and Least Used Services: Most customers use phone services, with around 90% having a phone service. Internet services are also widely used, with nearly 80% of customers having either DSL or Fiber optic connections. Services like online security and tech support are less utilized, with usage rates below 50%.

- Tenure and Service Usage Correlation: Longer-tenured customers are more likely to subscribe to multiple services. Tenure positively correlates with the number of services used.

# Payment and Contract Analysis:

![image](https://github.com/user-attachments/assets/228b9933-fafd-4ec1-a2e6-aa415ecda92c)

- Common Payment Methods: The most common payment methods are electronic checks and mailed checks. Credit cards and bank transfers are also popular.

- Monthly and Total Charges by Contract Types: Customers on month-to-month contracts tend to have higher monthly charges. Total charges vary significantly based on contract length, with longer contracts generally leading 
to higher total charges.

- Churn Rates by Payment Methods: Electronic check users have the highest churn rates, while bank transfer and credit card payment methods are associated with lower churn rates.

# Churn Prediction:

![image](https://github.com/user-attachments/assets/d61ea8ba-aef9-406e-8bea-c2ebe3c34861)

- Churn Rate: The overall churn rate is around 27%.

- Factors Associated with Churn: Monthly charges, tenure, and contract type are strongly associated with churn. Higher monthly charges and shorter tenure increase churn likelihood. Month-to-month contracts have the highest churn rates.

- Predictive Model: A Random Forest Classifier was trained, achieving an accuracy of 86%. The model’s confusion matrix helps in understanding the classification performance.

  Here are the processes for the model development:

# Predictive Model Development

To predict customer churn effectively, I employed a robust machine learning approach using the Random Forest Classifier. This section provides a detailed walkthrough of the predictive model development, evaluation, and insights drawn from the analysis.

## Data Preparation

- Feature Selection: The dataset was divided into features (X) and the target variable (y). Features included demographic information, service usage, and payment details, while the target variable was ‘Churn’.

- Handling Categorical and Numerical Data: Features were classified into categorical and numerical types. Numerical features included tenure, monthly charges, and total charges, while categorical features encompassed gender, senior citizen status, partner status, dependents, service subscriptions, contract type, payment method, and paperless billing.

## Preprocessing Pipeline

To prepare the data for the Random Forest Classifier, a preprocessing pipeline was designed:

- Numerical Features: A StandardScaler was applied to normalize the numerical data, ensuring each feature had a mean of 0 and a standard deviation of 1.

- Categorical Features: Categorical data was encoded using OneHotEncoder, which converted categorical variables into a format that could be provided to machine learning algorithms to do a better job in prediction.

  ![image](https://github.com/user-attachments/assets/e1ea176a-e7ac-4ec4-b8c0-c7af24cdec56)

# Model Training and Validation

- Data Split: The dataset was split into training (80%) and testing (20%) sets using train_test_split. This ensured that the model was trained on one portion of the data and validated on another to evaluate its generalization capability.

- Model Definition: The Random Forest Classifier, known for its robustness and accuracy, was selected as the predictive model. It consists of multiple decision trees and aggregates their predictions to enhance performance and reduce overfitting.

- Pipeline Construction: A pipeline was constructed to streamline the preprocessing and model training steps.

  ![image](https://github.com/user-attachments/assets/62176a4d-319c-4e44-90f4-ce93c7549bc8)

# Hyperparameter Tuning

To optimize the model, hyperparameter tuning was conducted using GridSearchCV. This method exhaustively searches over specified parameter values for the estimator to find the best combination:

- n_estimators: Number of trees in the forest.
- max_depth: Maximum depth of the tree.
- min_samples_split: Minimum number of samples required to split an internal node.
- min_samples_leaf: Minimum number of samples required to be at a leaf node.
- bootstrap: Method for sampling data points (with or without replacement).

## The best parameters identified were:

- n_estimators: 300
- max_depth: None
- min_samples_split: 10
- min_samples_leaf: 2
- bootstrap: True
- These parameters significantly improved the model’s performance.

## These parameters significantly improved the model’s performance.

# Model Evaluation

- Prediction and Accuracy: The trained model was used to predict the churn status on the test set. The accuracy of the model was evaluated using accuracy_score.
- Classification Report: A detailed classification report was generated to assess the precision, recall, f1-score, and support for each class (Churn/No Churn).

  ![image](https://github.com/user-attachments/assets/025b38fe-39ce-49e4-9397-2a389dbfe87b)


**Accuracy**: The model achieved an accuracy of 86%, indicating that it correctly predicted the churn status 86% of the time.

**Classification Report**: The classification report provided the following metrics:

- Precision: The ratio of true positive predictions to the total predicted positives. It indicates how many of the predicted churns were correct.
- Recall: The ratio of true positive predictions to the total actual positives. It measures the ability of the model to capture actual churn cases.
- F1-Score: The harmonic mean of precision and recall, providing a balance between the two.
- Support: The number of actual occurrences of each class in the test set.

# Confusion Matrix Visualization

To further understand the model’s performance, a confusion matrix was visualized using Seaborn. The confusion matrix helps in identifying the number of correct and incorrect predictions for each class, providing a comprehensive view of the model’s classification capability.


## The confusion matrix revealed:

- True Positives (TP): The number of customers correctly predicted to churn.
- True Negatives (TN): The number of customers correctly predicted not to churn.
- False Positives (FP): The number of customers incorrectly predicted to churn.
- False Negatives (FN): The number of customers incorrectly predicted not to churn.


# Insights and Interpretations

- High Accuracy: With an accuracy of 86%, the Random Forest model is reliable for predicting customer churn, offering a robust tool for the business to identify at-risk customers.
- Key Factors Influencing Churn: The analysis indicated that factors like monthly charges, tenure, and contract type are critical in determining churn. Customers with higher monthly charges and shorter tenure, especially those on month-to-month contracts, are more likely to churn.
- Misclassification Analysis: The confusion matrix highlights areas where the model could be improved, such as reducing false positives and false negatives. This can guide further tuning and model enhancement efforts.

# Ticket Analysis:
- Number of Tickets: Customers have raised numerous administrative and technical tickets, with a slight correlation observed between the number of tickets and churn.
- Correlation with Churn: Customers with higher ticket volumes tend to churn more while the correlation weakens.

# Service Quality and Satisfaction:

- Impact of Services on Churn: Services like online security, backup, and tech support positively impact customer satisfaction and reduce churn rates.

# Recommendations

Based on the insights gained from the Telecom Churn Rate Dataset, here are actionable recommendations:

- Targeted Marketing: Tailor marketing campaigns based on demographic insights to address specific customer segments vulnerable to churn.

- Service Enhancements: Improve service offerings, especially internet reliability and streaming quality, to enhance customer satisfaction and retention.

- Contract Strategies: Encourage longer-term contracts with incentives to reduce churn associated with month-to-month contracts.

- Payment Methods: Promote alternative payment methods to electronic checks to potentially reduce churn rates.
