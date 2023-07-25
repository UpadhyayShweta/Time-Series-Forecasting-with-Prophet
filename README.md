Forecasting Net Prophet

![Decorative image.](Images/unit-11-readme-photo.png)

## Background

In this notebook, we are analysing a company's financial and user data(as growth analyst) in an attempt to find ways to help the company grow. Company is known as [Mercado Libre](http://investor.mercadolibre.com/investor-relations), with over 200 million users, it is the most popular e-commerce site in Latin America. 

This notebook contains the following:

* Visual depictions of seasonality (as measured by Google Search traffic) that are of interest to the company.

* An evaluation of how the company stock price correlates to its Google Search traffic.

* A Prophet forecast model that can predict hourly user search traffic.

* Answers to the questions in the instructions that you write in your Jupyter notebook.

* A plot of a forecast for the company’s future revenue.

## Files

[Forecasting Net Prophet notebook](forecasting_net_prophet.ipynb)

[Data files](Resources)

---

## Tasks Performed/Resources used


1. Analysis is done in [Google Colab](https://colab.research.google.com/) notebook.

2. Tasks performed:

* Step 1: Find unusual patterns in hourly Google search traffic.

* Step 2: Mine the search traffic data for seasonality.

* Step 3: Relate the search traffic to stock price patterns.

* Step 4: Create a time series model by using Prophet.

* Step 5: Forecast the revenue by using time series models.

The following subsections detail these steps.

### Step 1: Find Unusual Patterns in Hourly Google Search Traffic

1. Read the search data into a DataFrame, and then slice the data to just the month of May 2020. (During this month, Mercado Libre released its quarterly financial results.) Use hvPlot to visualise the results. Do any unusual patterns exist?

2. Calculate the total search traffic for the month, and then compare the value to the monthly median across all months. Did the Google search traffic increase during the month that Mercado Libre released its financial results?

### Step 2: Mine the Search Traffic Data for Seasonality

1. Group the hourly search data to plot the average traffic by the day of the week (for example, Monday vs. Friday).

2. Using hvPlot, visualise this traffic as a heatmap, referencing `index.hour` for the x-axis and `index.dayofweek` for the y-axis. Does any day-of-week effect that you observe concentrate in just a few hours of that day?

3. Group the search data by the week of the year. Does the search traffic tend to increase during the winter holiday period (weeks 40 through 52)?

### Step 3: Relate the Search Traffic to Stock Price Patterns

1. Read in and plot the stock price data. Concatenate the stock price data to the search data in a single DataFrame.

2. Note that market events emerged during 2020 that many companies found difficult. But after the initial shock to global financial markets, new customers and revenue increased for e-commerce platforms. So, slice the data to just the first half of 2020 (`2020-01` to `2020-06` in the DataFrame), and then use hvPlot to plot the data. And check if both time series indicate a common trend that’s consistent with this narrative?

3. Create a new column in the DataFrame named “Lagged Search Trends” that offsets, or shifts, the search traffic by one hour. Create two additional columns:

   * “Stock Volatility”, which holds an exponentially weighted four-hour rolling average of the company’s stock volatility

   * “Hourly Stock Return”, which holds the percentage of change in the company stock price on an hourly basis

4. Review the time series correlation, to understand if a predictable relationship exist between the lagged search traffic and the stock volatility or between the lagged search traffic and the stock price returns?

### Step 4: Create a Time Series Model by Using Prophet

1. Set up the Google search data for a Prophet forecasting model.

2. After estimating the model, plot the forecast. What is the near-term forecast for the popularity of Mercado Libre?

3. Plot the individual time series components of the model to answer the following questions:

   * What time of day exhibits the greatest popularity?

   * Which day of the week gets the most search traffic?

   * What's the lowest point for search traffic in the calendar year?

### Step 5 : Forecast the Revenue by Using Time Series Models


1. Read in the daily historical sales (that is, revenue) figures, and then apply a Prophet model to the data.

2. Interpret the model output to identify any seasonal patterns in the company revenue. For example, what are the peak revenue days? (Mondays? Fridays? Something else?)

3. Produce a sales forecast for the finance group. Give them a number for the expected total sales in the next quarter. Include the best- and worst-case scenarios to help them make better plans.

---
