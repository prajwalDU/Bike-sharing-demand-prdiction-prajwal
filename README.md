# Seoul-Bike-sharing-demand-prediction-prajwal

# Problem statement :
Currently Rental bikes are introduced in many urban cities for the enhancement of mobility comfort. It is important to make the rental bike available and accessible to the public at the right time as it lessens the waiting time. Eventually, providing the city with a stable supply of rental bikes becomes a major concern. The crucial part is the prediction of bike count required at each hour for the stable supply of rental bikes.

![image](https://user-images.githubusercontent.com/67784512/211485825-280d1b5d-5835-4d8c-95eb-e2cf6ede9f88.png)


# Data Description :
1. Date : year-month-day
2. Rented Bike count - Count of bikes rented at each hour
3. Hour - Hour of he day
4. Temperature-Temperature in Celsius
5. Humidity - %
6. Windspeed - m/s
7. Visibility - 10m
8. Dew point temperature - Celsius
9. Solar radiation - MJ/m2
10. Rainfall - mm
11. Snowfall - cm
12. Seasons - Winter, Spring, Summer, Autumn
13. Holiday - Holiday/No holiday
14. Functional Day - NoFunc(Non Functional Hours), Fun(Functional hours)

**Variables description** :

![Screenshot (72)](https://user-images.githubusercontent.com/67784512/211484621-09b0baee-c979-427b-9cdb-1df8685014c2.png)

# EDA : Exploratory data analysis
 
 Checking data distribution using distplot and boxplot.
 
 And checking outliers in our dataset.
 
 Creating some new features called weekend and timeshift.
 
 Dropping un-wanted features which is not necessary.
 
 Doing Label encoding on categorical variables.
    Seasons, Holiday, Functioning Day, timeshift.
    
Ploting all independent values with respect to Rental Bike Count using regplot.

Checking multicollinearity Heatmap using seaborn libraries.

Checking VIF score for all independent values. And, removing all where VIF score is higher.

And, again ploting the heatmap with our dependent variable.



# Model building part
Know let's move to model building part

before moving on model building part we has to scale our dataset. Here we use MinMaxScaler()

Defining a function to train the input model and print evaluation matrix.
  In the function we Fitting model to test multiple algorithms to find which algorithms gives best result
  write evaluation matrix which contains mse,rmse,r2,etc
  finally we plot the result and return.

Providing the range of values for hyperparameters such as n_estimators, max_depth, min_sample_split, min_sample_leaf, eta.

Building some linear regression model to test which model gives better results.

1. Linear Regression
2. Decision Tree Regressor
3. Random Forest Regressor
4. XGBoost Regressor
5. GradientBoosting Regressor


# We observed following results after completing the task:

* Functioning day is the most influencing feature and temperature is at the second place for LinearRegressor.

* Temperature is the most important feature for DecisionTree, RandomForest and GradientBoosting Regressor.

* Functioning day is the most important feature and Winter is the second most for XGBoostRegressor.

* RMSE Comparisons :

1. LinearRegressor RMSE : 370.46
2. DecissionTreeRegressor RMSE : 302.53
3. RandomForestRegressor RMSE : 290.02
4. XGBoostRegressor RMSE : 242.72
5. GradientBoostingRegressor RMSE : 248.18

* The feature temperature is on the top list for all the regressors except XGBoost.

* XGBoost is acting different from all the regressors as it is considering whether it is winter or not. And is it a working day or not. Though winter is also a function of temperature only but it seems this trick of XGBoost is giving better results.

* XGBoostRegressor has the Least Root Mean Squared Error. So It can be considered as the best model for given problem.


**XGBoost is giving the best accuracy of around 82%**










 
