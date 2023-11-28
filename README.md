## Used Car Price Prediction*

URL: https://github.com/rfisher133/car_price_prediction.git
Files: 
Data Ananlysis: used_car_price_data_analysis.ipynb 
Model: used_car_price_model.ipynb 


**Project:** This project uses a dataset of 426,000 used car prices and contains 17 features such as year, 
odometer reading, condition, fuel type, etc. 
The purpose is to gain insight into the question "What drives the price of a used car?".


**Business Purpose:** The data analysis and predictive model intends to provide useful information for a used car dealer in
selecting inventory, in particular which features drive the price of the used cars. 

**Data Understaning:** The dataset included 3 numeric features (price, year, odometer) and 14 non-numeric features.
The numeric and non-numeric features provide useful information on the factors that drive the price of a used car. 
The data was explored and those results are summarized in the findings section below. 

**Data Preparation:** The project involved developing regression based models for prediction of the used car price.
The process included data cleaning and then feature engineering.
*Data cleaning:* General clenaup of data for the preparation of modeling included:
- Features that were determined to not provied useful value in predictions were removed, such as VIN numbers. 
- Features with large portions of missing values were removed. Features with smaller portions of missing values will filled in with substituions for the missing values. 
- Individual data entries with sparious data were removed, such as price as "123456" or "9999999". 
**Feature Engineering:** Non-numeric features were 
- Ordinal encoding was used to transformer the condition, fuel type and title status features into ranked numeric values.
- One Hot Encoding was used to generate features for manufacturer and type. 
- The feature model was dropped because of it's very large unstadardized naming.(as discussed in Next Steps, this would be a valuable feature to cleanup for use)

**Modeling:** The dataset was spilt for training and testing. Regresion models were trained and evaluated. These included:
- Multiple linear regression
- Polynomial  Regression with degree = 2
- Cross validation of Polynomial Regression with degree = 2 with 5 features
- Hyperparameter tuning with grid search of Ridge Regression

**Evaluation:** The model accuracy was judged using accuracy scoring and root mean squared error.
The model accuracy improved with listed models and cross validation used. The best scoring model was the
Polynomial Regression. The best fit with out overfitting was a foudn to be a degree 2 polynomial. 
The Sequenstial Selection and Grid Serch CV was not effective due to the large number of features that were
created by the OneHotEncoding of the manufacturer and vehicle type. 

The Polynomial Regression model results were:
- Train Accuracy: 67.5
- Train RMSE: $8,269
- Test Accuracy: 67.2
- Train RMSE $8,288

The top postiive coefficients effecting price were all combinations of Car condition xcar Type as follows: 
Coefficients
- condition x type_bus	
- condition x type_offroad	
- condition x type_van	
- condition x type_coupe	
- condition x type_mini-van	
- condition x type_hatchback	
- condition x type_wagon	
- condition x type_truck	
- condition x type_SUV	
- condition x type_sedan	

**Findings:** The predictive model developed had an accuracy in the test data of $8,288. 
The analysis of the data revealed the following factor regarding features driving the price of a used car: 

- Manucturer: The car maufacturer had the largest impact of price with Saturn and Mercury at the lowest and Ferrari at the top.
- Condition: The condition effects the median price especially if listed as fair or below: Like new = $18.0k, Excellent = $12.0k , Good = $11.5K, Fair = $3.3K 
- Paint Color: Vehicles that are white have an median price that is 29% higher than the overall median price.
- Fuel Type: The fuel type drives the median price: Diesel = $32.5k, Gas = $11.0k, Hybird = $10.5k
- Title: The title status effects the median price: Lien = $16.8k, Clean = $12.0k, Rebuilt = $12.0k, Salavage = $9.3k, Missing $3.5k
- Drive: The drive type effects the median price: 4-wheel = $16.0k, Front-wheel = $15.0k, Rear-wheel = $8.0k
- Type: The type of vehicle drives the price as shown on the graph below:



**Next Steps**
The predictive model for used car prices could be improved by utilizing the model name of the car.
The naming of car models in the dataset is unstandardized with mostly unique names. If the dataset
models names were cleaned, then a calssification model would likely perform well utilizing the manfuacturer 
and model. 
