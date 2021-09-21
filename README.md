# Customer-Lifetime-Value-Prediction

## PROBLEM STATEMENT / AIM
The objective of this project is the prediction of Customer Life-time Value (CLV). CLV is the lifetime value of a customer, or in other words it represents the total amount of money a customer is expected to spend in business, or on products, during their lifetime. CLV is an important metric because it provides the business groups with a customer-centric perspective to guide some critical marketing and sales strategies, thereby enhancing important business decisions.

## WORKFLOW
Initially in this project we have analysed the data through various exploratory data analysis techniques to explain the relationship between Customer Lifetime Value that is the target variable with the other explanatory variables. Further after rigorous analysis the most appropriate model is chosen and fitted to the data, which provides the highest accuracy.

## UNDERSTANDING THE DATA

* Data columns and values: There are a total of 24 data columns including the target variable that is the CLV. The columns are Customer, State , CLV , Response, Coverage, Education, EffectiveToDate, EmploymentStatus, Gender, Income, LocationCode ,MaritalStatus, MonthlyPremiumAuto , MonthsSinceLastClaim, MonthsSincePolicyInception, NumberofOpenComplaints, NumberofPolicies, PolicyType, Policy , RenewOfferType, SalesChannel , TotalClaimAmount , VehicleClass and VehicleSize. There are a total of 9134 Observations in the dataset.

* The dataset consists of a blend of both categorical and numeric columns: The categorical columns are : Customer, State , Response, Coverage, Education, EffectiveToDate, EmploymentStatus, Gender, LocationCode, MaritalStatus, PolicyType, Policy , RenewOfferType, SalesChannel , VehicleClass and VehicleSize. The numeric columns are: CLV, Income, MonthlyPremiumAuto, MonthsSinceLastClaim, MonthsSincePolicyInception, NumberofOpenComplaints, NumberofPolicies and TotalClaimAmount.

* There are no missing values in the dataset hence there is no treatment of missing values.


## FINAL MODEL - LINEAR REGRESSION WITH XGBOOST MODEL
In order to get a better accuracy (better than 80% as achieved by the previous model) we applied the Linear Regression Model with XGBoost.

* To fit XGBOOST to the data, features (X) and label (Y) sets were prepared to perform the train and test split.

*  The train and test data are used to create a dense matrix.

*  Further, all real-valued variables in the dataset were standardised as the non-standardized variables might have an influence on the model.

* Owing to the large dimension of the dataset, it is not possible to execute the dense matrix directly, so for that we constructed a sparse model or a “design” matrix.

* Further, the data frame is internal to the principal user level function, which generates the transposed model matrix for one factor.

* The following metrics were applied to the model to get a better accuracy:

   ➔  1.max.depth = 6: the trees won’t be deep, because our case is very simple ; 2.nthead = 4: the number of cpu threads we are going to use; 3.nround : max number of boosting iterations. 4.eval.metric: allows us to monitor two new metrics for each round, logloss and error. 5.eta : It controls the learning rate. 6.verbose = 1: print evaluation metric.

* Moreover, in order to get a Simple and a sophisticated model, we trained our model using the xgboost (simple) and xgb.train() methods, respectively. Hence by learning on one dataset and testing the model on another, it is possible to monitor a few metrics after each cycle of learning.

* The watchlist parameter has been used in the model, which provides a list of XGB and as far as the DMatrix is concerned ,each of them is tagged with a name.

## PREDICTION ON THE TEST DATA
* In order to predict the target variable various functions have been used such as -

* Gain shows the improvement in accuracy brought by a feature to the branches it is on.

* Cover measures the relative quantity of observations concerned by a feature.

* Frequency displays the number of times a feature is used in all generated trees.

* Displays the model’s approach is an acronym for extreme gradient boosting (XGBoost). We have used an optimization approach for regression problems which combines weak prediction models into a single strong prediction model thereby improving the insurance risk classifier’s performance by combining multiple models.

## CONCLUSION 

According to MAPE (Mean and Median Error Percentage), our regression model properly predicts the result 87.96 percent (Mean) and 95.63 percent (Median), with error percentages ranging from 3 percent to 12 percent. As of this writing, the R-square value is 0.7689372. Considering that these values range from 0.5 to 0.95, this is a decent predictive model to have in place.

