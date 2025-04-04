# Predicting the House Prices using Linear Regrerssion Model
## Objective: 
This project aims to build a classical Linear Regression model to predict the House prices effectively.
## Dataset:
The dataset used in this study is Kaggle's House prices- Advanced Regression Techniques <br>
https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques
### Data Preprocessing
The preprocessing of dataset is a crucial step in every machine learning project to ensure cleaned and well-structured data is fed to the model. The dataset contain missing values, duplicates and outliers which can impact model performance. The preprocessing taksks involves handling these inconsitencies to improve data quality and reliability.
* Handling Missing values:
  The .isnull() method is used to calculate the total number of NaN (Not a Number) values in each column. However, in this dataset, certain categorical values such as "NA" represent meaningful information rather than actual missing values. For example: In the Alley column, "NA" means no alley access, not a missing value. In the BsmtFinType2 column, "NA" indicates no basement, rather than missing data.

If we treat these "NA" values as missing data and impute or remove them, we may alter the meaning of the dataset and negatively impact model performance. Instead, these values should be retained as valid categories. Here both train and test dataset were seperated based on numerical and categorical columns for handling inconistencies.
The Nan value in the categorical columns cannot be removed or imputed by the statistcal mesures such as median or mode value, they have been replaced with the label "Nil" to retain meaningful data.

* Outlier Detection

Outliers are extreme values in the dataset that can negatively impact the performance of a machine learning model. Detecting and handling outliers is crucial to ensure the model learns from meaningful data and not from extreme, rare cases.
Outliers in these columns may arise due to data entry errors or extreme cases, such as luxury properties with unusually high values. To detect these outliers, boxplots and scatterplots can be used for visual inspection, while statistical methods like IQR method help quantify extreme values

### Encoding caterical Variables:
The categorical variables are encoded using LabelEncoder

### Feature selection using SelectKBest
Feature selection is a technique where we choose those features in our data that contribute most to the target variable. In other words we choose the best predictors for the target variable.
The top 12 features selected using SelectKBest are OverallQual,YearBuilt, YearRemodAdd, TotalBsmtSF, 1stFlrSF, GrLivArea, FullBath, GarageCars, GarageArea, ExterQualencoded,BsmtQualencoded, and KitchenQualencoded

### Splitting the data and Standardization
The data is splitted into train and test sets and then standardized using StandardScalar
### Model Building and Evaluation
A linear regression model is used to predict the house prices and the model exhibits a performance with an R2 score of 84%


