# Predicting likelihood of churn and understanding factors that cause churn, with the aim of reducing churn

##### Author: Mrunal Dodhiwala
##### Big Data Analytics - Classification Project

### Repository Content
This repository contains the code for EDA, Predictive analysis using Logistic Regression model, Random Forest model (will be uploaded later) and Gradient Boosted (XGBoost) Regression model (will be uploaded later), along with evaluation of the performance metrics of these models

### Table of Contents
- Abstract
- Requirements
- Repository Content
- Data Preparation
- Methodology
- Model Evaluation
- Conclusions

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
-	Random Forest (later)
-	XGBoost (later)

The models will be evaluated on the following metrics:
-	Recall, primary metric since the aim is to reduce churn
-	Accuracy
-	Precision
-	F1score
-	Execution Time


### Requirements
-	Python – along with the following packages: Pandas, NumPy, MatPlotLib, Seaborn, Scikitplot
-	R – along with following packages: caret, corrplot, plotrix, lessR, janitor, ggplot2, dplyr, sm


### Repository Content
The content of this repository is:
-	README.md file explaining the overall project structure
-	RMD file includes code to perform Exploratory Data Analysis, including pre-processing, One-Hot encoding, Univariate analysis of each attribute, Bi-variate analysis to show the relation of each attribute with class attribute, and correlation matrix
-	HTML format of the above RMD file
-	IPYNB file includes code to predict which customers are likely to churn. The models used for prediction include Logistic Regression model, Random Forest model and Gradient Boosted (XGBoost) Regression model. The models are evaluated over mean recall, accuracy, precision, F1 scores and execution time.
-	HTML format of the above IPYNB file

### Data Preparation
The dataset is available on Kaggle link given above. The dataset has no missing values. Pre-preparation involved converting attributes into categorical factors, one-hot encoding for categorical variables, removing redundant variables, balancing the dataset by oversampling the minority class.

### Methodology

| Step	            | Description                                                            |
| ----------------- | ---------------------------------------------------------------------- |
| Objective	| Identify business context, define research questions and related objective |
| Data Pre-Preparation	| Checking for missing values, converting to factors, One-Hot encoding |
|EDA	| Data overview, Descriptive statistics, Univariate analysis, Bi-variate analysis, Correlation matrix |
| Experimental Design	| Oversampling with SMOTE, 10-fold Cross-validation while train/test split |
| Modelling	| Logistic Regression, Random Forest, XGBoost |
| Model Evaluation	| Evaluate all the models for Recall, accuracy, precision F1 scores and the time taken |
| Conclusions	| Interpret results against evaluation metrics, conclude business insights and present findings |

### Model Evaluation
Currently, only 1 model was tested i.e. Logistic Regression. The other models will be tested later. The model was run on the original dataset that was imbalanced, and after balancing the training dataset. The balancing technique used was oversampling with SMOTE. Dataset is split into train/test set in the ratio of 70:30, and then 10-fold cross validation is done. The average scores of 10-fold cross-validation before and after SMOTE are tabulated below:

| Model   | Logistic Regression before SMOTE | Logistic Regression after SMOTE |
| ------- | -------------------------------- | ------------------------------- |
| Recall	| 0.42	| 0.78	|
| Accuracy	| 0.87	| 0.81	|
| Precision	| 0.68	| 0.45	|
| F1 score	| 0.52	| 0.57	|
| Mean ROC AUC	| 0.88	| 0.88 |
| Execution Time	| 0.25 sec	|	10.7 sec	|


### Conclusions





