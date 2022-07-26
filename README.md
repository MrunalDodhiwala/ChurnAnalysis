# Predicting likelihood of churn and understanding factors that cause churn, with the aim of reducing churn

##### Author: Mrunal Dodhiwala
##### Big Data Analytics - Classification Project

### Repository Content
This repository contains the code for EDA; and Predictive modelling using Logistic Regression model, Random Forest model and XGBoost model, along with evaluation of the performance metrics of these models

### Table of Contents
- Abstract
- Requirements
- Repository Content
- Data Preparation
- Methodology
- Model Evaluation
- Conclusion
- Recommendations

### Abstract
#### Context
Consumer spending is a huge driver of macroeconomic conditions. Substantial portion of consumer spending is through credit cards. Credit card is a profitable business for banks; as it generates not only fee income, but also interest income.
While it is critical for banks to acquire new customers to achieve business growth, it is also imperative to plug the backdoor and retain as many profitable customers as possible. It is common knowledge that the cost of acquiring new customers is five times the cost of retaining and existing customer. The focus of banks should be to project itself as customer-driven and one that invests in building long-term relationships with customers. There may be many reasons for customers to leave a bank, and it may not be feasible to address each one of them even if the bank may find out the exact reasons. But the banks can find out which customers are more likely to churn, and can assimilate the reasons of churn, then the bank can design the products/services to reduce churn. When banks discover and address the reasons of customer churn in the pursuit of retaining customers, it will earn a positive reputation that may attract more new customers to join the organization.
Given this backdrop, banks are increasingly turning to data mining techniques for attrition analysis.

#### Research Questions
The primary questions that I aim address are:
1.	Which customers are more likely to churn?
2.	What factors impact customer attrition the most?
3.	What plan of action can be implemented to reduce customer attrition?

#### Data
The dataset is available on Kaggle at the following url:
https://www.kaggle.com/datasets/sakshigoyal7/credit-card-customers
This dataset contains 10,127 customers and 21 attributes, including the class attribute ‘Attrition_Flag’. The attributes include:
-	Demographic details like Age, Gender, Number of Dependents, Education Level, Marital Status, Income Category, 
-	Business info including Card category, Months the customer has been with the bank, Total relationships of customer with the bank, number of times customer has contacted the bank
-	Credit Card usage info including Months of inactivity in last 12 months, Credit limit, Revolving balance, Average open to buy, Total transaction amount, Amt change in Q4 compared to Q1, Total transaction count, count change in Q4 compared to Q1, Utilization ratio.
The dataset has no missing values.

#### Techniques and Tools
R has been used for Exploratory Data Analysis. This includes:
-	Data Overview / Snapshot
-	Univariate Analysis
-	Bivariate Analysis, understanding which attributes impact churn
-	Correlation Matrix

Python has been used for modelling, predictive analysis, and model evaluation. The models used for classification prediction are:
-	Logistic Regression
-	Random Forest
-	XGBoost

The models will be evaluated on the following metrics:
-	Recall, primary metric since the aim is to reduce churn
-	Precision
-	F1score
- ROC AUC
-	Accuracy
-	Execution Time


### Requirements
-	Python – along with the following packages: Pandas, NumPy, MatPlotLib, Seaborn, Scikitplot
-	R – along with following packages: caret, corrplot, plotrix, lessR, janitor, ggplot2, dplyr, sm


### Repository Content
The content of this repository is:
-	README.md file explaining the overall project structure
-	RMD file includes code to perform Exploratory Data Analysis, including pre-processing, One-Hot encoding, Univariate analysis of each attribute, Bi-variate analysis to show the relation of each attribute with class attribute, and correlation matrix
-	HTML format of the above RMD file
-	IPYNB file includes code to predict which customers are likely to churn. The models used for prediction include Logistic Regression model, Random Forest model and XGBoost model. The models are evaluated over mean recall, precision, F1 scores, ROC, accuracy and execution time.
-	HTML format of the above IPYNB file

### Data Preparation
The dataset is available on Kaggle link given above. The dataset has no missing values. Pre-preparation involved converting attributes into categorical factors, one-hot encoding for categorical variables, removing redundant variables, balancing the dataset by oversampling the minority class.

### Methodology

| Step	            | Description                                                            |
| ----------------- | ---------------------------------------------------------------------- |
| Objective	| Identify business context, define research questions and related objective |
| Data Pre-Preparation	| Checking for missing values, converting to factors, Descriptive statistics, One-Hot encoding |
|EDA	| Univariate analysis, Bi-variate analysis, Correlation matrix |
| Experimental Design	| Train/test split, Oversampling with SMOTE, 10-fold Cross-validation |
| Modelling	| Logistic Regression, Random Forest, XGBoost |
| Model Evaluation	| Confusion Matrix, Recall, Precision, F1 score, ROC AUC, Accuracy and the time taken |
| Conclusions	| Interpret results against evaluation metrics, conclude business insights and present findings |

### Model Evaluation
The models were run on the original dataset that was imbalanced, and after balancing the training dataset. The balancing technique used was oversampling with SMOTE. The average scores after 10-fold cross-validation of each model, before and after SMOTE-balancing, are tabulated below:

##### Original dataset (before SMOTE-balancing)

| Model   | Logistic Regression | Random Forest | XGBoost |
| ------- | --------------------| ------------- |-------- |
| Recall	| 0.42	| 0.75	| 0.84	|
| Precision	| 0.68	| 0.92	| 0.93	|
| F1 score	| 0.52	| 0.82	| 0.88	|
| Mean ROC AUC	| 0.88	| 0.99 | 0.99	|
| Accuracy	| 0.87	| 0.95	| 0.97	|
| Execution Time	| 0.3 sec	|	1.3 sec	| 0.9 sec	|


##### After SMOTE-balancing

| Model   | Logistic Regression | Random Forest | XGBoost |
| ------- | --------------------| ------------- |-------- |
| Recall	| 0.78	| 0.87	| 0.90	|
| Precision	| 0.45	| 0.83	| 0.86	|
| F1 score	| 0.57	| 0.85	| 0.88	|
| Mean ROC AUC	| 0.88	| 0.98 | 0.99	|
| Accuracy	| 0.81	| 0.95	| 0.96	|
| Execution Time	| 10.7 sec	|	2.2 sec	| 1.5 sec	|

### Conclusions
Dataset balancing through SMOTE produces much better results as compared to the original imbalanced dataset. This is true for all the three models of Logistic Regression, Random Forest and XGBoost. The time taken for training the models on the SMOTE-balanced dataset is considerably higher than on the original imbalanced dataset. That is a trade-off that the bank will have to make for better predictive ability. One of the solutions can to be train the model each month on a superior system.
XGBoost has the highest Recall among the three models trained. XGBoost has performed well across all the metrics evaluated i.e., Recall, Precision, F1 score, ROC AUC, Accuracy. Hence XGBoost is the most effective model among the three models. So, XGBoost is also the most efficient model.

From the EDA, we can draw the conclusion that the following factors impact churn the most:
-	Total Relationships the customer has with the bank. Adding 3 more relationships reduces churn by 50%
-	Contact Count. Chrun for customers calling for 5th time is 33%, and churn goes to 100% for the 6th call.
-	Transactions Count. 4 transactions per month reduces churn from 38% to 8%
-	Utilization Ratio. Churn for Nil Utilization is more than double than portfolio churn.

### Recommendations
- Bank can set-up an out-reach team to contact clients with Nil relationships except for the card, and offer them additional services. Based on the output of XGBoost model, the out-reach team can contaact customers predicted to churn to address thier issues/concerns. This team should also be tasked with encouraging customers to set-up pre-authorised payments on the card.
- The 4th service call should be directed to the team leader for resolution.
- Promotional scheme for setting up pre-authorized payments, and introductory offer for Nil Utilization customers to start using the card.






