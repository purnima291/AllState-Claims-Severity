# AllState-Claims-Severity
## 1. Description/Overview
Allstate Corporation is one of the largest insurance companies in the United State. The main products that Allstate offers are car insurance, recreational vehicles insurance, home, property, condo, renters insurance, and so on. In order to provide better claims service for Allstate’s customers, the company is developing automated methods to predict claims serverity.<br> 

This problem has been picked from [kaggle](https://www.kaggle.com/c/allstate-claims-severity) and this is the [data source](https://www.kaggle.com/c/allstate-claims-severity/data).

## 2. Real world Business Objective
Aim of this challenge is to build a Machine Learning model that can help Allstate to automate the process of predicting the severity of the claims accurately and hence *ensuring a worry-free customer experience* and *saving both time and money invested to do this task manually.*

**Real-time Constraint**:
* No strict latency requirements.
* Interpretability is important. 

## 3. Mapping the real-world problem to a Machine Learning Problem 
This is a regression problem. To solve this challenge, we have to predict loss/cost of claim for each of the data point given to us. 

### 3.1. Performance Metrics
Models are evaluated on the [mean absolute error (MAE)](https://en.wikipedia.org/wiki/Mean_absolute_error) between the predicted loss and the actual loss.


### 3.2. Data Overview
We have train dataset and test dataset. Each dataset consists of columns (both categorical and continuous) containing accident information. <br>
<br>
 **Shape of train data: 188318 rows and 132 columns**<br>
 **Shape of test data: 125546 rows and 131 columns**<br>
 <br>
So there are total 136 features/columns and having following details:
* *id*: Unique id assingned to each row
* *cat1, cat2,..., cat116*: These are 116 anonymized categorical features.
* *cont1, cont2,...,cont14*: These are 14 anonymized continuous features.
* *loss*: Target variable that needs to be predicted. Amount of cost for each claim.

### 3.3. Some useful resources:
https://www.kaggle.com/sharmasanthosh/exploratory-study-on-ml-algorithms<br>
https://www.kaggle.com/achalshah/allstate-feature-analysis-python

# EDA
In eda, I did some simple analysis on both categorical and continuous features(See EDA.ipynb). By using Cramer's V method, I found that there are many pairs of categorical columns which have high association/correlation among them. Similarly, by using pearson's correlation coefficient, I got to know that few pairs of continuous features have high correlation. 

# Feature Engineering
This section is the heart of this project. As this competition from kaggle is few years old, so people had already shared there method that they used to solve this problem. Keeping those ways in mind, I tried to come up with my own method of doing feature engineering, which is quiet different from the pre-existing ones. 
<For more details check out *Final_feature_engineering.ipynb* notebook and *Feature-set-selection.ipynb* notebook.

# Modelling Section
This section contains which Machine learning algorithm is applied to predict the loss. Xgboost performed better and MAE is reduced till 1228. For further details check *Model_building_part.ipynb* notebook.

# Link to the Technical Blog desrcibing complete case study: 
