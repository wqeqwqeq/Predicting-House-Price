# Predicting-House-Price
This is one of my end-to-end machine learning project. Steps include data inspection, data preprocessing, and final modeling. 
### 1. Data inspection
This steps include load both train data and test data from [Kaggle](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data) using *Pandas*. I also delete the ID since it does not offer extra information for fitting model. 
### 2. Data preprocessing
This part requires effort knowing the industrial knowledge. I just use common sense and statistical knowledge to transform data to fit model better. 
#### 2.1 Outlier
I use *Matplotlib* to plot the predictor versus the target variable, and delete some outliers to reduce bias. 
#### 2.2 Transform target variable 
I use *Seaborn* to plot the distribution plot and QQ-plot for target variable. I find skewness so I transfer the data afterward 

