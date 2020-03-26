# Predicting-House-Price
This is one of my end-to-end machine learning project. Steps include data inspection, data preprocessing, and final modeling. 
## 1. Data inspection
This steps include load both train data and test data from [Kaggle](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data) using *Pandas*. I also delete the ID since it does not offer extra information for fitting model. 
## 2. Data preprocessing
This part requires effort knowing the industrial knowledge. I just use common sense and statistical knowledge to transform data to fit model better. 
#### 2.1 Outlier
I use *Matplotlib* to plot the predictor versus the target variable, and delete some outliers to reduce bias. 
#### 2.2 Transform target variable 
I use *Seaborn* to plot the distribution plot and QQ-plot for target variable. I find skewness so I transfer the data afterward
#### 2.3 Feature engineering
In this part, I inspect the missingness by visualization and then impute the missing data, plot the correlation plot, label encoding categorical variable and then create dummy variable for these data (One-hot-encoding), use box cox transformation to detect skewness of numerical and transform them, and combining some feature based on common sense. 

## 3. Data Modeling
We first define the metric we will use--RMSE. We use the cross_val_score function of Sklearn. However this function does not have shuffle attribute, we add k-fold cv to shuffle the dataset prior to cross-validation
#### 3.1 Base model
Our base models include lasso, elastic net, kernel ridge regression, gradient boost regression, lightGBM, XGBoost
The result is:

Lasso score: 0.1115 (0.0074)

ElasticNet score: 0.1116 (0.0074)

Kernel Ridge score: 0.1153 (0.0075)

Gradient Boosting score: 0.1176 (0.0081)

Xgboost score: 0.1165 (0.0073)

LGBM score: 0.1154 (0.0071)

#### 3.2 Stacking model
We add a stack model and average our prediction and improve score
Averaged base models score: 0.1090 (0.0076)

#### 3.3 Add meta model 

Split the total training set into two disjoint sets (here train and .holdout )

Train several base models on the first part (train)

Test these base models on the second part (holdout)

Use the predictions from 3) (called out-of-folds predictions) as the inputs, and the correct responses (target variable) as the outputs to train a higher level learner called meta-model.



