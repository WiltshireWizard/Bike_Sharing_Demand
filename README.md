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
 **Original data:** 
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
* Made Columns for Hour, Day of the Week, Month and Year, extracting these from the datetime object.
* Convert season data from numbers to season names.
* Weather data converted from numbers to simplified description of weather conditions : {1: Clear, 2: Cloudy, 3: Light rain, 4: Heavy rain}

## EDA
* I looked at the distributions of the data and the value counts for the various categorical variables. 
* Created Boxplots to explore how categorical variables relate to the count column (demand).

![alt text](https://github.com/WiltshireWizard/Bike_Sharing_Demand/blob/master/Box_plots.png)

* Identified unusual seasonal variation with peak usage in the autumn. After further analysis seasons were found to be poorly defined and seasons were redefined to contain the correct months.

* Point plots to explore how demand varies with time of the day and other variables.

![alt text](https://github.com/WiltshireWizard/Bike_Sharing_Demand/blob/master/pp1.png)


* Rush hour variable created to capture the peaks in usage at typical commuting times.
* Explored continuos weather variables relationship with demand by creating regression plots

![alt text](https://github.com/WiltshireWizard/Bike_Sharing_Demand/blob/master/regplot.png)


* Identified that windspeeds of 0 were likely due to faults in data collection.
* Created a function to fill in faulty windspeeds: 
   1. Humidty shows the highest correaltion with windspeed.
   2. Data grouped into humidity bins.
   3. Average windspeed calculated for each humidity bin.
   4. Windspeeds of 0 are replaced by the average windspeed of the associated humidity bin.
* Windspeed also appeared to show a different relationship with count for windspeeds above and below 20mph.

![alt text](https://github.com/WiltshireWizard/Bike_Sharing_Demand/blob/master/windspeed.png)
 
 
 * Normalized the count data using a log transformation.
 
 ![alt text](https://github.com/WiltshireWizard/Bike_Sharing_Demand/blob/master/count_distribution.png)
 ![alt text](https://github.com/WiltshireWizard/Bike_Sharing_Demand/blob/master/Normalized.png)



## Model building
* Categorical variables converted to dummy variables.
* Data split into a training and testing set with a test size of 30%.

* I tried Three different models:
  1. **Multiple Linear Regression -** as a baseline model.
  2. **Random Forest -** Is a robust model that is less influenced by outliers.
  3. **GradientBoosting Regressor-** Boosting reduces error mainly by reducing bias. GridSearchCV used to optimize parameters
  
## Model Performance
The GradientBoosting regressor was the best performing model.

* **GradientBoosting Regressor:** RMSLE:  0.100   R^2: 0.945
* **Random Forest:** RMSLE:  0.161   R^2:  0.915 
* **Multiple Linear Regression:** RMSLE: 0.275 R^2: 0.856

                          
  


