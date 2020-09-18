# Bike_Sharing_Demand Project Overview:

* Applying various regression models to historical bike share usage patterns and weather data. 
* Models can then be used to forecast bike rental demand in the Capital Bikeshare program in Washington, D.C.
* Extensive Exploratory Data Analysis performed to understand the data and inform feature engineering.
* Target data 'count' was normalized using a log transformation.
* An initial Linear Regression model and Random Forest regressor were used to gauge a baseline performance.
* Gradient Boosting Regresser and Support Vector Machine Regressor were optimized using GridSearchCV.
* Optimized Gradient Boosting Regressor offered the best performance with an R^2 value of 0.945 and RMSLE of 0.100
## Code and Resources Overview:
* **Python Version:** 3.7.6
* **Packages:** pandas, numpy, sklearn, matplotlib and seaborn
## Data Collection
*The data was sourced from the Bike Sharing Demand competition on Kaggle:
https://www.kaggle.com/c/bike-sharing-demand/overview
* **Original data:** 
* datetime - hourly date + timestamp.  
* season -  1 = spring, 2 = summer, 3 = fall, 4 = winter.
* holiday - whether the day is considered a holiday.
* workingday - whether the day is neither a weekend nor holiday.
* weather - 1: Clear, Few clouds, Partly cloudy, Partly cloudy.
2: Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist
3: Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds
4: Heavy Rain + Ice Pallets + Thunderstorm + Mist, Snow + Fog. 
* temp - temperature in Celsius.
* atemp - "feels like" temperature in Celsius.
* humidity - relative humidity.
* windspeed - wind speed.
* casual - number of non-registered user rentals initiated.
* registered - number of registered user rentals initiated.
* count - number of total rentals.
## Data Cleaning


