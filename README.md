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

### Google Search Trend Data
For creating the Google Search Trend data, we pulled in historical data for specific phrases for each stock from the past 3 years and broke them down into 2 categories:

- Profit Trends: "(Stock Name) Profit", "(Stock Ticker) Buy", & "(Stock Name) Stock up"
- Loss Trends: "(Stock Name) Loss", "(Stock Ticker) Sell", & "(Stock Name) Stock down"

For each week, we notated a "1" for the trend column when the total of the loss trends were a higher numerical value than total of the profit trends.


### Sector Analysis and Performance Statistics

AMZN:
- ! [Amazon Google Search Trend & Closing Prices](Resources/AmazonGoogleSearchTrendClosingPrices.png)
- ! [Amazon Google Search Trend & Cumulative Returns](Resources/AmazonGoogleSearchTrendCumulativeReturns.png)
- ! [AMZN Algo Portfolio Evaluation Metrics](Resources/AMZNAlgorithmicTradeEvaluationMetrics.png)
- ! [AMZN Algorithmic Trade Evaluation](Resources/AMZNAlgorithmicTradeEvaluation.png)
- ! [Amazon VAQ Short Position Algo & Google Search Trend](Resources/AMCVAQShortPositionAlgoGoogleSearchTrend.png)
- ! [Backtest Logistic Regression Model AMZN](Resources/BacktestLogisticRegressionModelAMZN.png)
- ! [Random Forest Classifier AMZN](Resources/RandomForestClassifierAMZN.png)
- ! [Random Forest Classifier Feature Importance AMZN](Resources/RandomForestClassifierFeatureImportanceAMZN.png)


AMC:
- ! [AMC Google Search Trend & Closing Prices](Resources/AMCGoogleSearchTrendClosingPrices.png)
- ! [AMC Google Search Trend & Cumulative Returns](Resources/AMCGoogleSearchTrendCumulativeReturns.png)
- ! [AMC Algo Portfolio Evaluation Metrics](Resources/AMCAlgoPortfolioEvaluationMetrics.png)
- ! [AMC Algorithmic Trade Evaluation](Resources/AMCAlgorithmicTradeEvaluation.png)
- ! [AMC VAQ Short Position Algo & Google Search Trend.](Resources/AMCVAQShortPositionAlgoGoogleSearchTrend.png)
- ! [Backtest Logistic Regression Model AMC](Resources/BacktestLogisticRegressionModelAMC.png)
- ! [Random Forest Classifier AMC](Resources/RandomForestClassifierAMC.png)
- ! [Random Forest Classifier Feature Importance AMC](Resources/RandomForestClassifierFeatureImportanceAMC.png)

CVNA:
- ! [Carvana Google Search Trend & Closing Prices](Resources/CarvanaGoogleSearchTrendClosingPrices.png)
- ! [Carvana Google Search Trend & Cumulative Returns](Resources/CarvanaGoogleSearchTrendCumulativeReturns.png)
- ! [CVNA Algo Portfolio Evaluation Metrics](Resources/CVNAAlgoPortfolioEvaluationMetrics.png)
- ! [CVNA Algorithmic Trade Evaluation](Resources/CVNAAlgoPortfolioEvaluation.png) 
- ! [Carvana VAQ Short Position Algo & Google Search Trend](Resources/CarvanaVAQShortPositionAlgoGoogleSearchTrend.png)
- ! [Backtest Logistic Regression Model CVNA](Resources/BacktestLogisticRegressionModelCVNA.png)
- ! [Random Forest Classifier Report CVNA](Resources/RandomForestClassifierReportCVNA.png)
- ! [Random Forest Classifier Feature Importance CVNA](Resources/RandomForestClassifierFeatureImportanceCVNA.png)



### Seasonal Decomposition
Lastly, the script performs a seasonal decomposition analysis of the S&P 500 ETF (SPY).


## Findings and Conclusions: 

### CVNA Google Search Trend & Algo Short Position

The Random Forest Classifier identifies "Carvana Loss" as a crucial trend related to CVNA stock. The hypothesis suggests that an increase in searches for "Carvana Loss" might indicate an impending price decrease, aligning with a potential buy opportunity in the short position strategy. To verify the correlation between "Carvana Loss" and closing price, we examine the highest closing price and search trend data from 2021.

On 2021-08-10, CVNA reached its highest closing price of 370.1. Interestingly, on 2021-08-08, "Carvana Loss" was not searched at all, coinciding with an uptick in the stock's closing price. Conversely, a surge of 100 searches for "Carvana Loss" on 2021-08-29 preceded a price drop, as the stock price declined from 370.1 to 337.6 on 2021-08-30. This suggests that an increase in searches for "Carvana Loss" may indeed indicate an upcoming price decrease, offering a potential entry signal for the short position strategy to yield high profits.

Following the prediction of buy and sell positions through the Logistic Regression model, we also consider the Google Search Trend alongside the signals and algorithmic cumulative returns of Carvana stock. Our strategy suggests buying when closing prices and cumulative returns are on a downturn, with the predicted_signal reading 1 during the review of the 2021 trends.

For instance, on 2021-08-10, the highest cumulative returns were 2.664123, and the predicted signal was 1, signifying a buy opportunity. Subsequently, the stock was bought at the highest cumulative returns and closing price, and the CVNA shares were immediately sold, preparing for the short position strategy. As the "Carvana Loss" search trend reached a value of 100, algorithmic cumulative returns declined to 2.431327 on 2021-08-30. The corresponding predicted signal of 1 during the decline in closing price and cumulative returns prompted us to buy CVNA stock, ultimately leading to profits in the short position strategy.

Additionally, in the analysis of the Dual Moving Average Crossover strategy, we evaluated closing prices, cumulative returns, buy/sell signals, and Google search trends from 2022-01-30 to 2022-02-20. This further substantiates the hypothesis that the Google Search Trend of "Carvana Loss" serves as a reliable indicator of price decrease, supporting the algorithmic short position strategy.

For example, on 2022-02-03, the single short moving average intersected with the single long moving average at approximately 278, indicating a buy position, followed by an instant sell to build the algorithmic short position strategy. The closing price on that date was 146.94, with cumulative returns at 1.057731. The search trend value of "Carvana Loss" was 23 on 2022-01-30, and as it increased to 39 by 2022-02-20, the closing price declined to 126.40, and cumulative returns dropped to 0.909876 within just 17 days. This considerable drop in closing prices and cumulative returns further supports the potential for a buy signal or entry position into the market for an effective short on Carvana stock.

In conclusion, the study reinforces the hypothesis that specific Google search trends, such as "Carvana Loss," can be indicative of stock price fluctuations, allowing the development of a profitable position in the algorithmic short strategy. Investors should remain vigilant, buying at lower prices, returning the stocks, and holding profits to execute the algorithmic short position strategy successfully. Based on the analysis, tracking Carvana for about a year and taking the predicted buy signal at 1 or an entry position at 2.0 on 2022-01-03 could result in a profit of 1869.0. Moreover, the Dual Moving Average Crossover analysis in 2022 could lead to a profit of 10,730.0 on 2022-05-04, a mere three months after the "Carvana Loss" trend experiences an uptick. In conclusion, Carvana’s google search trends correlate with fluctuations of stock prices which can develop into a profitable position in the algorithmic short strategy.

### CVNA, AMC, AMZN Financial Ratio Analysis

The annual volatility is moderate for Carvana and AMC at 0.654138 and 0.187133 and huge for Amazon at 39.130301.
 
The downside volatility, or Sortino Ratio, is rather low for Carvana at 0.015189 and high at 0.989772 for AMC, but this is where that works in our favor.  

Sortino ratio is negative for Amazon.  A negative Sortino ratio means that the risk free rate is higher than the stock’s return.  A negative Sortini ratio is considered terrible because it indicates that the investor could have gotten a better return with no risk by investing in a risk-free option like government bonds / treasures.

Given the information depicted in the portfolio evaluation DataFrame, and given the right market conditions, it would make sense for a risk-averse investor to make a small allocation to short trading strategy with AMC’s stock.

Based on the trade evaluation metrics, this trading algorithm strategy produced mixed results for Carvana and AMC with alternating profits and losses - probably looking a little better in total for Carvana.It consistently brought losses for Amazon’s stock.

## Next Steps
- More precise semantic analysis.
- Incorporate more metrics into the model.
- Try different machine learning models to increase our profits for our algorithmic trading model.
