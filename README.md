
# House Prices - Advanced Regression Techniques

With 79 explanatory variables describing (almost) every aspect of residential homes in Ames, Iowa, this competition challenges you to predict the final price of each home.

# Dataset Description

## Dataset Source

The dataset was collected from Kaggle.

## Dataset Description

The dataset consisted of 1461 rows and 81 unnamed features.  This is a regression problem to predict the final price of the house.

## Data Pre-processing

1. Columns with 50 percent or more null values were dropped.

2. Rows with null values and which make up less than 2 Percent data where removed.

3. Categorical values were filled with mean and numerical values were filled with mode.


## Exploratory Data Analysis 

Regular shaped houses are the least expensive. Price increases as the house architecture becomes more and more abstract.

'LandContour' has no effect on the sale price.

'LotConfig' has no effect on Sale price.

House foundation effects price with pure concrette selling for the most.

'LandSlope' has no impact either

Housing price varies from neighborhood to neighborhood.

House Exterior and Veneer have an effect on the price

Also, buyers prefer a good quality kitchen and driveway

Newer houses and new designed houses with complete construction sells for the most.

Houses price increases with the condition.

Housing price also depends on the number of bedrooms and bathrooms.
## Feature Engineering of numerical values

1. The dataset has a lot of features. So, lets drop some of them. First lets drop them due to the presence of two columns of the same kind :

a. OverallQual cause its related to OverallCond

b. YearBuilt cause YearRemodAdd

c. ExterQual cause ExterCond

d. GarageCars cause GarageArea

e. GarageQual cause GarageCond

The features which are irrelevant were also removed:

'Street', 'RoofStyle', 'RoofMatl', 'Exterior1st', 'Condition1', 'Heating', 'BsmtQual', 'BsmtCond', 'BsmtExposure', 'BsmtFinType1', 'BsmtFinSF1', 'BsmtFinType2', 'BsmtUnfSF', 'GarageType', 'GarageYrBlt', 'GarageFinish', 'GarageYrBlt, 'MiscVal', 'MoSold'


2. The features which were 80% correlated with each other were also dropped.

3. Sweetviz was used to perform EDA

The following features were removed.

[‘PoolArea’, ‘Utilities’, ‘LandSlope’, ‘Condition2’, ‘HouseStyle’, ‘KitchenAbvGr’, ‘GarageCond’, ‘3SsnPorch’, ‘ScreenPorch’, ‘BldgType’, ‘MSZoning’, ‘YearRemodAdd’, ‘ MasVnrArea’, ‘HalfBath’, ‘BsmtFullBath’, ‘Electrical’, ‘CentralAir’, ‘Functional’]

Reasons:

a. 2ndFloorSF correlates with HouseStyle and HalfBath
b. BldgType correlates with 2ndFloorSF and MSSubClass
c. MSZoning and YearRemodAdd relates with neighborhood
d. MasVnrArea correlates with MasVnrType
BsmtFullBath correlates FullBath
e. The rest were dropped due to having the same values in 93% or more cases.

# Feature Engineering of CATEGORICAL DATA

This dataset has Categorical Data. So, they need to be encoded. The challenge here is a lot of categorical data have some kind of relationship with them while others dont. To solve this a mixture of get_dummies and label encoding will be used.





## Classifier

Linear Regression was used to predict the House price. It had an Root Mean Square Log Error is  0.18.

Important Features:

1. LotArea:Lot Area
2. HeatingQC: Quality
3. GrLivArea: Above grade (ground) living area square feet
4. FullBath: Number of Full Bathrooms
5. Foundation_PConc: Houses with poured concrete foundation
6. SaleTypeWd: Warranty Deed - Conventional
SaleCondition_Normal
