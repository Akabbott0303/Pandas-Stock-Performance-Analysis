# Pandas 101: Stock Performance Analysis

This repository contains Python code for analyzing performance of multiple stock portfolios.  After analyzing three given portfolios, I created my own portfolio to see how it stacks up to the professional portfolios.

### Data Cleaning

Three CSV files (included in the [Resources](/Resources) folder) were imported into Pandas as dataframes using Pathlib.  For each dataframe, I dropped the nulls.  For one of the dataframes I also replaced the currency symbols with nothing and converted the objects datatypes to floats.  This dataframe did not include daily returns, so I calculated them using the percent change function.  With the data having been cleaned, I concatenated the dataframes into one dataframe.

### Analysis

The portolios in the dataframe are:

1. Soros Fund Management, LLC
2. Paulson & Co., Inc.
3. Tiger Global Management, LLC
4. Berkshire Hathaway, Inc.
5. Two portfolios containing stocks put together by an algorithmic trading strategy

I also imported historical S&P 500  prices to use for my analysis.

## Performance Analysis

First I calculated and plotted the daily returns of all portfolios.
![Daily_Returns_All_Portfolios](/Screenshots/Daily_Returns_All_Portfolios.PNG)

Next, I calculated and plotted the cumulative returns for all portfolios. 
![Cumulative_Returns_All_Portfolios](/Screenshots/Cumulative_Returns_All_Portfolios.PNG)

Both Berkshire Hathaway and Tiger Global have a higher standard deviation than the S&P500, indicating that they are riskier than the S&P500. This is what I expected based on the drastic up-and-down, above and below the S&P500, nature of their lines in the Cumulative Returns graph.

## Risk Analysis

To start the risk analysis section, I created a box plot for each of the returns.
![Box_Plot_All_Portfolios](/Screenshots/Box_Plot_All_Portfolios.PNG)

Then I calculated the standard deviation for each portfolio.
![Daily_Standard_Deviation](/Screenshots/Daily_Standard_Deviations.PNG)

Algo 2's daily standard deviation is very close to the S&P500. Since its volatility tracks closely with that of the S&P500, it is the least risky portfolio. Soros comes in second with Algo 1 a close third.

As with the Cumulative Returns analysis, both Algo portfolios appear to be doing well.

## Rolling Statistics

I calculatee and plotted the rolling standard deviation for all portfolios using a 21-day window.
![Rolling_Standard_Deviations](/Screenshots/Rolling_Standard_Deviations.PNG)

I also calculated and plotted the correlation between each stock to determine which portfolios may mimick the S&P 500.
![Heatmap_All_Portfolios](/Screenshots/Heatmap_All_Portfolios.PNG)

I selected one portfolio, Algo1, and calcuulated and plotted the 60-day rolling beta between it and the S&P 500.
![Rolling_Beta_Algo1](/Screenshots/Rolling_Beta_Algo1.PNG)

## Sharpe Ratios

I calculated the Sharpe Rations of all portfolio to see how risky each portfolio is.
![Sharpe_Ratios_All_Portfolios](/Screenshots/Sharpe_Ratios_All_Portfolios.PNG)

And the winner is: Algo! Algo 1 is the best performing portfolio when adjusted for risk, and Algo 2 is a solid third. Harold and his firm have winner with their algorithmic trading strategies.

They should still consider hiring Warren Buffet should he decide to make a career change. Berkshire Hathaway is our second best performer by Sharpe Ratio. It's ratio is very close to the S&P 500.

### Introducing the Abbott Portfolio

The portfolio I created contains stock from Amazon (AMZN), Disney (DIS), and Exon Mobil Corp (XOM).

The Abbott portfolio isn't too bad, for an amateur investor! Algo 1 is still the winner, which should make Harold proud. When adjusted for risk, the Abbott portfolio performs well but not as well as Algo 1. The Abbott portfolio is pretty tightly correlated with the S&P 500. The 60-day rolling beta graph is interesting - it shows that my portfolio started off being somewhat volatile but the risk has declined over time.

Here are the Abbott portfolio calculations and graphs:
![Rolling_Standard_Deviations_Incl_Abbott](/Screenshots/Rolling_Standard_Deviations_Incl_Abbott.PNG)

![Heatmap_Incl_Abbott](/Screenshots/Heatmap_Incl_Abbott.PNG)

![Rolling_Beta_Abbott](/Screenshots/Rolling_Beta_Abbott.PNG)

![Sharpe_Ratios_Incl_Abbott](/Screenshots/Sharpe_Ratios_Incl_Abbott.PNG)

