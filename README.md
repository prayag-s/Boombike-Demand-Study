# Boombikes Demand Study

   <p align="right">By Prayag Sanjay</p>

## Problem Statement
	As a result of recent Corona pandemic, US bike-sharing provider BoomBikes are
  experiencing considerable drop in their revenues,
  making it very difficult to survive in the current market scenario.
	As a part of a clever business plan to up its revenue it wants capitalise on the
  market as soon as lockdown ends. So it needs to
  know the drivers for the demand for the shared bike in American market.

	Hence,

	Goals of Study
		1. To find out which variables are significant in predicting the demand for shared bikes.
		2. How well those variables describe the bike demands.

	Business Goals
		1. To build a model to predict the demand for shared bikes.
		2. To explain the dynamics of the demand using the model.

## Data Set
	We are give a dataset on daily bike rental across America and various probable factors
  affecting the bike rental such as a weather conditions, day types such as weekend, holiday and rental type.

## Approach
	From the problem statement, we can see following characterstics
	
		- Business wants to know the driver variables for a specific target, in this case bike demand.
      So there is an expectation of explainability from the model.
		
		- Business want to predict demand for bikes or dynamics of demand as opposed to forecast the demand for bikes.

	Thus this problem falls in realms of predictive analysis where we want to interpolate the data.
  Aa a result of above two reasons we will employ **Linear Regression** with multple variables
  machine learning method to build the model which will answer the business questions.
	

## Steps
	-	Perform cleaning of data
	-	To exploratory data analysis of data. Use visualization.
	-	Divide the data in test and training sets.
	-	Do modelling on the training set.
	-	Iterate till variables are statistically  coefficient, there is no multicollinearity.
	-	Check the linear regression assumptions on the training data.
	-	Predict using the best model on the test data.
	-	Check that there is under or over fitting using metrics such adjusted R-square.


## Conclusion

### Variables that are significant in predicting the demand for shared bikes.

	Following variables are significant

	**Temperature of the day**

	**Year of rental**

	**Type of weather** (summer, winter)

	**Month of the year** (in particular September)

	**Week day** (specially Sunday)

	**Season** (in particular summer and winter)

	**Windspeed**

	**Weather** (in particular Misty and Cloudy or Light Snow or Thunderstorm)

### Dynamics of the demand

	Based up on above variables and their coefficients, we can group drivers variables in following groups

	**Positive Drivers**

	These variables increase the demand for the rental. So company should check and the plan the stock for these days

	-  **Temperature of the day** (Coeff 0.5672) - This has got big impact of the demand.
     Higher the temperature higher is the demand.

	-  **Year**  (Coeff 0.2335) - Model shows that there is natural increase in demand from one year to another.
      Probably with growing population and awareness for health. So company can plan to increase production to meet this.

	- **Week day 6 or Sunday** (Coeff 0.0246) - This is a weak indicator that demand is more on Sunday being a holiday.

	- **Season** (Coeff 0.0871), - Rental increases particularly in summer and winter as well (Coeff, 0.1254)

	- **Month (September)** (Coeff 0.0790) - There is variatin with month, with september month being strongest in terms of increase in demand

	**Negative Drivers**

	These variables decrease the demand for the rental. So company should check and plan for the lean days.

	- **Adverse weather days** (Coeff -0.2631 and - 0.0781)) - On bad weather days particularly 
     Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds, demand is very low.

	- **Wind speed** (Coeff -0.155), on higer wind speed days demand decreases perhaps due wind chill factor or wind resistance.

### Model to describe the demand

	The model is

	$ count = 0.103 \times constant + 0.2335  \times  year + 0.5672  \times  temperature + 0.0871 \times summer +
            0.1245 \times winter + 0.0790 \times september + 0.0246 \times weekday_6 - 0.155 \times windspeed - 0.0078 \times Mist and Cloudy
            - 0.2631 \times Light Snow and Storms $
