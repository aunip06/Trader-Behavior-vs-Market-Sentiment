# Trader-Behavior-vs-Market-Sentiment
1.Introduction

Crypto markets are highly influenced by emotions like fear and greed. The Bitcoin Fear & Greed Index is commonly used to understand overall market sentiment.
In this project, I analyze how trader behavior and performance changes under different market sentiment conditions by combining:
historical trader data from Hyperliquid
Bitcoin Fear & Greed Index data
The aim is to understand whether market sentiment has a measurable impact on trading outcomes.

2.Objective

The main objectives of this analysis are:
To study the relationship between market sentiment and trader profitability
To analyze how trade size, win rate, and risk behavior change during Fear vs Greed
To extract insights that could help in building sentiment-aware trading strategies

3.Datasets

1. Bitcoin Fear & Greed Index
This dataset provides daily sentiment information for Bitcoin.
Important columns:
date – Date of the sentiment value
classification – Market sentiment (Fear, Extreme Fear, Greed, Extreme Greed)
value – Numerical index value
The data is available at a daily level.

2. Historical Trader Data (Hyperliquid)
This dataset contains individual trade-level data.
Some important columns used:
Account – Trader identifier
Coin – Asset traded
Execution Price
Size USD – Trade size
Side – Buy or Sell
Timestamp – Trade execution time
Closed PnL – Profit or loss from the trade
This data is intraday, meaning multiple trades can occur on the same day.

4.Data Cleaning & Preparation

The trade Timestamp column was stored as a UNIX epoch value and initially got parsed incorrectly.
After identifying this issue, timestamps were converted using the correct unit.
Since sentiment data is daily and trade data is intraday, both datasets were aligned to daily dates.
The datasets were merged on the date column to associate each trade with the corresponding market sentiment.

5.Feature Engineering

Created a profitability flag based on Closed PnL
Simplified sentiment categories:
Fear + Extreme Fear → Fear
Greed + Extreme Greed → Greed
Aggregated metrics like:
Average PnL
Win rate
Trade count
Average trade size

6.Exploratory Data Analysis

The following analyses were performed:
Comparison of PnL distributions during Fear and Greed periods
Win rate comparison across different sentiment regimes
Analysis of trade size behavior under different sentiments
Buy vs Sell performance under Fear and Greed
Trade activity levels during different market conditions
Multiple visualizations were used to support these analyses.

7.Key Observations

Traders tend to take larger positions during Greed, indicating higher risk appetite.
PnL volatility is noticeably higher during Greed phases.
During Fear, traders appear more conservative with smaller trade sizes.
Win rate differences between Fear and Greed are present but not very large.
Some top traders show relatively stable performance regardless of sentiment, suggesting better risk control.

8.Limitations
Sentiment data is only available on a daily basis, while trades are intraday.
PnL values are not adjusted for leverage or account size.
Other market factors like volatility or funding rates were not considered.

9.Future Improvements

Include leverage-adjusted or risk-adjusted returns.
Perform trader clustering based on behavior and sentiment sensitivity.
Extend the analysis to other assets and longer time periods.
Explore predictive models using sentiment as a feature.

10.How to Run

Install required libraries:

pip install pandas numpy matplotlib seaborn


Open the Jupyter notebook and run the cells sequentially.

11.Conclusion

This analysis shows that market sentiment has a clear impact on how traders behave and take risk. Combining sentiment indicators with trade-level data can provide useful insights for building more disciplined and informed trading strategies.

12.Author

Aunip Mishra
Junior Data Scientist Applicant
