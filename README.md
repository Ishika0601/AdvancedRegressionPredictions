# Bike Sharing
> The main aim of this project is to build a regression model using regularisation in order to predict the actual value of the prospective properties and decide whether to invest in them or not.


## Table of Contents
* [Problem Statement](#problem-statement)
* [Problem Solving Methodology](#problem-solving-methodology)
* [Conclusions](#conclusions)
* [Technologies Used](#technologies-used)


## Problem Statement
A US-based housing company named Surprise Housing has decided to enter the Australian market. The company uses data analytics to purchase houses at a price below their actual values and flip them on at a higher price. For the same purpose, the company has collected a data set from the sale of houses in Australia. 

The company is looking at prospective properties to buy to enter the market. The company wants to know:

Which variables are significant in predicting the price of a house, and

How well those variables describe the price of a house.


## Problem Solving Methodology
* Data Sourcing & Understanding -
> Source the dataset which contains the complete data for the sale of houses in Australia.
> Making use of the data dictionary and understanding the columns and their domain specific uses.
* Data Cleaning -
> Handling null values, creating derived variables, changing the data types of the columns, checking the data frame for skewness, outlier detection.
* EDA -
> Visualize correlation between the variables using pair plots and heat map and visualize categorical variables with target variable w.r.t. sale price.
* Data preparation for modelling -
> Create dummy variables, split data into training and testing set, perform feature scaling.
* Model Building -
> Use RFE to find top 25 variables and then use statsmodel api to build models and remove columns based on their VIF and p-values, finally build a advanced regression model (Lasso Regression & Ridge Regression) using the columns shortlisted after building models with statsmodel api.
* Model Evaluation -
> Evaluate the models by chekcing the R-squared value for training and testing set by building the model using the most appropriate hyperparameter obtaine dusing grid search.


## Conclusions
- Finally, the preferred model is Ridge Regression with alpha = 4 built on 25 parameters. It has a r2-score of 0.854 on the test data.

Ridge is prefered over Lasso because Lasso doesn't perform any kind of feature elimination on its own and its computation cost is also quite high. The difference in the r2-score on test data is not much high so it can be ignored easily in case of Lasso Regression.

- The top 10 parameters taken for prediction in case of Ridge Regression are :-

1. OverallCond_7 - 1.321460
2. OverallQual_Excellent - 0.556113
3. OverallQual_7 - 0.473171
4. house_age - 0.411751
5. Neighborhood_OldTown - 0.335486
6. Neighborhood_NridgHt - 0.311692
7. OverallCond_Excellent - 0.214961
8. OverallQual_8 - 0.182313
9. GrLivArea - 0.008203
10. Neighborhood_Edwards - -0.175749


## Technologies Used
- Numpy        - version 1.21.6
- Pandas       - version 1.3.5
- Seaborn      - version 0.11.2
- Matplotlib   - version 3.2.2
- Scipy        - version 1.7.3
- Sklearn      - version 1.0.2
- Statsmodels  - version 0.12.2
