# Unit 10—A Yen for the Future

![Yen Photo](Images/unit-10-readme-photo.png)

## Background

The financial departments of large companies often deal with foreign currency transactions while doing international business. As a result, they are always looking for anything that can help them better understand the future direction and risk of various currencies. Hedge funds, too, are keenly interested in anything that will give them a consistent edge in predicting currency movements.

In this assignment, you will test the many time-series tools that you have learned in order to predict future movements in the value of the Japanese yen versus the U.S. dollar.

You will gain proficiency in the following tasks:

1. Time Series Forecasting
2. Linear Regression Modeling

## What I Did
The time series analysis forecasts historic daily returns for the Yen currency. I first trimmed my data to begin on January 1st 1990. 

Then I plotted the settlement price for my data set. The plot showed a long-term strengthening of the Japanese Yen against the Dollar. There do seem to be some more medium, 1-3 year consistent trends, but on a daily basis, there are a lot of short-term ups and downs. 

I then used the Hddrick-Prescott Filter to decompose the data into noise and trend series.Smoothing with the HP Filter and plotting the resulting trend against the actual futures returns, we can see that there's a lot of short term fluctuations that deviate around this trend. Perhaps these would represent profitable trading opportunities. 

I then forcasted the returns using the ARMA model, and determined that my model was not a good fit. the coeifficient did not appear to be statistically significant. 

I then forcasted the settlement price using an ARIMA Model. The model forecasted that the price of the Yen will climb in the near term. 
I then Forecasted the volitility using the GARCH model. The model forecasted increasing volitilty in the near term.

## Conclusion
I would not buy the yen now. Although the price is projected to rise in the coming 5 days, this comes with the risk of increased volitilty. 

I question the validity of the models used to come up with these results, since only one coefficient in my GARCH model would be considered statistically significant(a1<.05). 

All other models have no statistically significant coefficients. 

The risk of the yen is expected to increase over the next 5 days. We can determine this by looking at the 5 day forecast of viotility. However higher volatility leads to more risk which can lead to higher returns. Based on the model evaluation I would not feel confident using these models for trading. Both models have p scores larger than .05 showing no statistical significants.

This model performs best on the out of sample data. We infer this from the RMSE is .41 for the out of sample data and .57 for the in smaple data.

## Regression Analysis
Used Regression Analysis to determine Seasonal Effects with SKlearn Linear Regression.
First trimmed the data to begin on January first 1990.

Calculated a percentage change and lagged return. 

Trained, tested and split my data. I then made both out of sample and in sample predicitions using the testing data

- - -

### Files

[Time-Series Starter Notebook](Starter_Code/time_series_analysis.ipynb)

[Linear Regression Starter Notebook](Starter_Code/regression_analysis.ipynb)

[Yen Data CSV File](Starter_Code/yen.csv)

- - -

### Instructions

#### Time-Series Forecasting

In this notebook, you will load historical Dollar-Yen exchange rate futures data and apply time series analysis and modeling to determine whether there is any predictable behavior.

Follow the steps outlined in the time-series starter notebook to complete the following:

1. Decomposition using a Hodrick-Prescott Filter (Decompose the Settle price into trend and noise).
2. Forecasting Returns using an ARMA Model.
3. Forecasting the Settle Price using an ARIMA Model.
4. Forecasting Volatility with GARCH.

Use the results of the time series analysis and modeling to answer the following questions:

1. Based on your time series analysis, would you buy the yen now?
2. Is the risk of the yen expected to increase or decrease?
3. Based on the model evaluation, would you feel confident in using these models for trading?


#### Linear Regression Forecasting

In this notebook, you will build a Scikit-Learn linear regression model to predict Yen futures ("settle") returns with *lagged* Yen futures returns and categorical calendar seasonal effects (e.g., day-of-week or week-of-year seasonal effects).

Follow the steps outlined in the regression_analysis starter notebook to complete the following:

1. Data Preparation (Creating Returns and Lagged Returns and splitting the data into training and testing data)
2. Fitting a Linear Regression Model.
3. Making predictions using the testing data.
4. Out-of-sample performance.
5. In-sample performance.

Use the results of the linear regression analysis and modeling to answer the following question:

* Does this model perform better or worse on out-of-sample data compared to in-sample data?

- - -

### Hints and Considerations

* Out-of-sample data is data that the model hasn't seen before (Testing data).
* In-sample data is data that the model was trained on (Training data).

- - -

### Submission

* Create Jupyter Notebooks for the analysis and host the notebooks on GitHub.

* Include a Markdown that summarizes your models and findings and include this report in your GitHub repo.

* Submit the link to your GitHub project to Bootcampspot.
