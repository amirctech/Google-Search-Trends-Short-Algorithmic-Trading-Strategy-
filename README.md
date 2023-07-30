# Google Search Trends & Short Algorithmic Trading Strategy Analysis README

Final Project located in files:
- Project 1 Evaluation CVNA.ipynb
- Project 1 Evaluation AMC.ipynb
- Project 1 Evaluation Amazon.ipynb

## Description


Our project focused on analyzing Google search trends and developing a short-position trading algorithm for three stocks. We collected search trend data from Google and stock data from Alpaca APIs. Utilizing Random Forest, we identified the key features from the Google Trend data and built the short-position trading algorithm. To assess potential returns, we backtested the trading model using various financial ratios and metrics over the past three years. To enhance the accuracy of our algorithmic short position strategy, we integrated Logistic Regression as a supervised learning model for predicting buy and sell positions. Ultimately, our research aimed to determine the profitability of the selected stocks in a short position using our algorithmic model.

The tool provides interactive charts and plots using the hvplot library for visualizing various metrics.

## Project Procedure Steps

1. Data Collection: We gathered historical search trend data of the past 3 years for each stock from Google Search Trends.

2. Dimensionality Reduction: Random Forest is applied to the search trend data to reduce its complexity and identify important features.

4. Short List Refinement: From the Random Forest Model we selected the Google Search Trend feature with the most importance to proceed with to push through our algorithmic strategy.

5. Algorithmic Trading: The chosen stocks are traded using the Dual Moving Average Crossover (DMAC) and Simple Moving Average (SMA) strategies.

6. Backtesting and Metrics: The trading algorithm's performance is evaluated through backtesting. Metrics such as annualized return, cumulative returns, annual volatility, Sharpe ratio, and Sortino ratio are calculated.

7. Performance of Trade Evaluations: Based on our set paramaters, we evaluated potential profit and loss of our trading algorthmic strategy.


## Libraries and Imports Used
- pandas
- Google Search Trends
- APIs
- numpy
- pathlib
- Sklearn
- LogisticRegression
- RandomForestClassifier
- datetime
- HvPlot
- StandardScaler
- train_test_split
- confusion_matrix
- accuracy_score
- classification_report

## Requirements
To use this script, you will need to have Python installed along with the libraries mentioned above. 

## How to Use
1. Ensure all dependencies are installed.
2. Clone the repository.
3. Run the script in a Jupyter Notebook environment.
4. Modify the APIs and Google Search Trend data for an analysis on different stocks.
5. Adjust the start and end date variables accordingly for the Google Search Trends and APIs if a different time range is needed.

## Features

### Downloading Ticker Data
The script downloads the data for selected ticker symbols representing our stocks from Alpaca APIs representing the closing price of each stock.





### Sector Analysis and Performance Statistics
The script generates plots for several performance metrics of the ETFs:
- ! [Closing price plotted for the period 2008-2023](Resources/PriceperShare_SectorETFs.png)
- ! [Cumulative Returns](Resources/Sector_Cumulative_Returns.png)
- ! [Sharpe Ratio](Resources/Sharpe_by_Sector.png)
- ! [Riskiness (Standard Deviation of Weekly Returns)](Resources/StDev_by_Sector.png)
- ! [Correlation of Weekly Returns](Resources/Sector_Correlations.png)
- ! [Static Betas for Period 2008-2023](Resources/Static_Sector_Betas.png)
- ! [52-Week Rolling Betas from 2008-2023](Resources/Rolling_Sector_Betas.png)

### Seasonality Analysis
This section analyzes the seasonality in the ETF returns. It fetches daily data for each ticker and assigns a season based on the month of the year. It then calculates the average seasonal returns for each ETF.

- ! [ETF Variance by Season](Resources/sideways_Consolidation.png)
- ! [Seasonal Adjustments - Market Consolidation](Resources/sideways_Consolidation.png)
- ! [Seasonal Adjustments - Bull Market](Resources/bull_market_conditions.png)
- ! [Monthly Returns Box Plot](Resources/boxplot.png)
- ! [Seasonality & 20MA of SPY](Resources/download.png)



### Seasonal Decomposition
Lastly, the script performs a seasonal decomposition analysis of the S&P 500 ETF (SPY).


## Findings and Conclusions

There do appear to be seasonal effects in the stock market. Over the 15 years in the dataset, this effect is most pronounced in Winter, or Q4. 
ETFs experienced greater volatility in these Winter months, and not so much in the Spring.

In terms of climate, the data suggest that increasing surface temperature was correlated with lower returns, while a decrease in surface temperature 
was associated with better returns. More research needs to be done over a greater period of time to determine to what extent climate has a causal
impact on returns.

## Next Steps
- Adding different factors into our analysis - macro economic factors, inflation, interest rates, natural disasters, geopolitical climate
- Diving deeper into what extent climate change effects the performance of different industry stock prices
- Going deeper and broader with seasonality/trends analysis - running more tests on ETF’s, etc.
- Drawing conclusions from our data that will help us facilitate our investment strategy
- For the climate change analysis, we want to dive deeper and  add in other variables, such as natural disasters, and explore further risk ratios to see if there are any trends.
