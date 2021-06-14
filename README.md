# Congress Members Stock Trades


## **Problem Statement**

The Stop Trading on Congressional Knowledge (STOCK) Act was enacted in 2012 to combat insider trading in Congress. The law was designed to stop the use of non-public information for individual profit. Congress members have never been prosecuted based on information they acquired as members of Congress. However, in January 2020, a former US Congressman from New York, Chris Collins, was convicted of insider trading for activities outside of Congressional duties and sentenced to prison. Additionally, in February 2020, several Congress members sold large quantities of stock shares in the month prior to a large stock market drop due to COVID-19. The Justice Department investigated this incident, but eventually dropped its investigations.

We explore stock investment performance by members of Congress from 2013 through 2020. The performance of these investments are investigated from a variety of angles, listed below:



1. Do Congress members have exceptional stock market returns? Do their stock investments beat the market average (measured by the S&P 500, typically a 10% annual return) if we view their investments at intervals of 30 days, 90 days, and 180 days?
2. What variables are highly correlated to stock performance
3. Can individuals follow the investments of Congress members (with a 30-60 day delay) and beat the average market return?
4. Are there any Congress members who have exceptional stock performance?
5. Is there a difference in the investment performance of junior versus senior members of Congress?
6. Do congress members who receive more corporate donations have better stock performance?

Through this analysis we hope to determine how congress’ stock investments compare to the average investor.


## **Data Dictionary**



1. Data was obtained from the following sources:
2. 1) house stocks from housestockwatcher.com
3. 2) senate stocks from senatestockwatcher.com
4. 3) congress person years was scraped from congress.gov
5. 4) congress person party was scraped from congress.gov
6. 5) congress donations was from [opensecrets.org](https://www.opensecrets.org/elections-overview/large-vs-small-donations)

<table>
  <tr>
   <td>
Feature
   </td>
   <td>Type
   </td>
   <td>Dataset
   </td>
   <td>Description
   </td>
  </tr>
  <tr>
   <td>transaction_date
   </td>
   <td><em>datetime</em>
   </td>
   <td>House_stocks.csv & senate_stocks.csv & house_senate_years_donations.csv
   </td>
   <td>This field provides the date that a congressperson purchased or sold a stock from senatestockwatcher.com and housestockwatcher.com
   </td>
  </tr>
  <tr>
   <td>ticker
   </td>
   <td><em>string</em>
   </td>
   <td>House_stocks.csv & senate_stocks.csv & house_senate_years_donations.csv
   </td>
   <td>This field provides the name of the company or investment, typically a stock ticker from senatestockwatcher.com and housestockwatcher.com
   </td>
  </tr>
  <tr>
   <td>asset_description
   </td>
   <td><em>object</em>
   </td>
   <td>House_stocks.csv & senate_stocks.csv & house_senate_years_donations.csv
   </td>
   <td>This text provides a description of the asset
   </td>
  </tr>
  <tr>
   <td>type
   </td>
   <td><em>object</em>
   </td>
   <td>House_stocks.csv & senate_stocks.csv & house_senate_years_donations.csv
   </td>
   <td>This provides information on whether the asset was purchased or sold (partially or in full)
   </td>
  </tr>
  <tr>
   <td>amount
   </td>
   <td><em>object</em>
   </td>
   <td>House_stocks.csv & senate_stocks.csv & house_senate_years_donations.csv
   </td>
   <td>This provides the monetary range for the size of the investment
   </td>
  </tr>
  <tr>
   <td>representative
   </td>
   <td><em>object</em>
   </td>
   <td>House_stocks.csv & senate_stocks.csv & house_senate_years_donations.csv
   </td>
   <td>This provides the name of congressperson that made the investment
   </td>
  </tr>
  <tr>
   <td>state
   </td>
   <td><em>obj</em>
   </td>
   <td>congresspeople_years_party_state.csv
   </td>
   <td>The states of each representative
   </td>
  </tr>
  <tr>
   <td>party_x
   </td>
   <td><em>obj</em>
   </td>
   <td>congresspeople_years_party_state.csv
   </td>
   <td>The political party of the representative
   </td>
  </tr>
  <tr>
   <td>total_senate_years
   </td>
   <td><em>int</em>
   </td>
   <td>congresspeople_years_party_state.csv
   </td>
   <td>The total years served in the Senate as of 2021, if applicable
   </td>
  </tr>
  <tr>
   <td>total_house_years
   </td>
   <td><em>int</em>
   </td>
   <td>congresspeople_years_party_state.csv
   </td>
   <td>The total years served in the house as of 2021, if applicable
   </td>
  </tr>
  <tr>
   <td>total_years
   </td>
   <td><em>int</em>
   </td>
   <td>congresspeople_years_party_state.csv
   </td>
   <td>The total years combining house and senate positions
   </td>
  </tr>
  <tr>
   <td>total_raised
   </td>
   <td><em>obj</em>
   </td>
   <td>house_senate_years_donations.csv
   </td>
   <td>Total money raised by a congress member
   </td>
  </tr>
  <tr>
   <td>total_from_small_donors
   </td>
   <td><em>obj</em>
   </td>
   <td>house_senate_years_donations.csv
   </td>
   <td>Amount raised by a congress member from small donors
   </td>
  </tr>
  <tr>
   <td>percent_from_small_donors
   </td>
   <td><em>obj</em>
   </td>
   <td>house_senate_years_donations.csv
   </td>
   <td>Percentage of the money a congress member raised that came from small donors
   </td>
  </tr>
  <tr>
   <td>total_money_raised
   </td>
   <td><em>obj</em>
   </td>
   <td>house_senate_years_donations.csv
   </td>
   <td>Whether a congress member raised more or less than $100k
   </td>
  </tr>
  <tr>
   <td>Day_30 (60, 90, 180)
   </td>
   <td><em>float</em>
   </td>
   <td>stock_percentage_difference.csv
   </td>
   <td>Ticker stock price at 30, 60, 90 and 180 days from purchase.
   </td>
  </tr>
  <tr>
   <td>Sp_30 (60, 90,  180)
   </td>
   <td><em>float</em>
   </td>
   <td>stock_percentage_difference.csv
   </td>
   <td>S&P 500 index price at 30, 60, 90 and 180 days from purchase of congress member stock.
   </td>
  </tr>
  <tr>
   <td>Day_30_stock_perc_diff (60, 90, 180)
   </td>
   <td><em>float</em>
   </td>
   <td>stock_percentage_difference.csv
   </td>
   <td>A measure of the stock performance: percentage change in the stock price - subtracting the percentage change in the S&P 500 index. The result is the performance difference from S&P 500 average over 30, 60, 90 and 180 days.
   </td>
  </tr>
  <tr>
   <td>Sp_30_sp_perc_diff (60, 90, 180)
   </td>
   <td><em>float</em>
   </td>
   <td>stock_percentage_difference.csv
   </td>
   <td>S&P 500 index price percentage difference in price measured over 30, 60, 90 and 180 days.
   </td>
  </tr>
</table>



## **Executive Summary**

Our notebook begins by gathering data from multiple sources.

<span style="text-decoration:underline;">Stock Information on Congress Members:</span>

To evaluate the stock purchases of members of congress, we downloaded tables provided by Housestockwatcher.com and Senatestockwatcher.com. These tables included transactions from December 2018 to May 2021 for Representatives and transactions from June 2012 to May 2021 for Senators. The tables contained rows for each transaction. These rows included the name of the congress member, transaction date, stock ticker, whether the transaction was a purchase or sale, and the general size of the investment. We used this information. The tables also contain information about whether the stock was owned by the member or their spouse, a description of the asset, and the asset type. We did not use this information in our analysis. The asset types listed included municipal securities, corporate bonds, and other types of assets, but these were a small portion of the data. When we pulled stock performance data, these other transaction types were left out and removed from the data used to analyze and model stock performance. To clean the data, we needed to harmonize the columns for sale/purchase type between the senator and  representative data. We also converted the date columns to a pandas datetime format.

<span style="text-decoration:underline;">Congress Member information:</span>

Beautiful soup was used to scrape each of the pages of congress members. Their names, state, party and years served in house or senate as applicable were saved to a dataframe. To merge the newer data on names, Fuzzywuzzy was used to find the corresponding names despite different transcriptions.

<span style="text-decoration:underline;">Stock Data:</span>

We used the yfinance API to pull stock information. We iterated through each row of the dataframe and pulled the price of the stock and the S&P 500 at the date of the transaction. We also pulled the stock prices at multiple rolling timer intervals: 30 days later, 60 days later, 90 days later and 180 days later. Some asset types like corporate bonds, or stocks traded on foreign markets were unable to be pulled due to the API we used. Finally, we calculated the percentage difference in the stocks value over each one of these timeframes, and compared it to the same timeframe as if the congress person had invested in the S&P 500 Index (a typical investment that serves as an average for the market).  We then calculated the difference in performance by subtracting the S&P 500’s percentage difference from our congress members stock performance. This measure provided us a measure of how far above average the congress member’s stock’s performed.

<span style="text-decoration:underline;">EDA:</span>

Before looking at stock performance data, we performed some EDA on the data for stock transactions and donations for congress members. The data had similar numbers of purchases and sales. For most congress members, much less money was raised from small donors than large donors. In looking for correlations between years in congress, money raised, and percent of money from small donors, the only strong correlation was a positive one between the total money raised and the percent from small donors, but the variance was not stable, so it was tough to interpret. The transaction amount data was in bins or groups of amounts that varied. The distribution of the transaction amount data showed that most transactions were between $1,000 and $50,000.

<span style="text-decoration:underline;">Modeling:</span>

We built Classification Models to predict whether or not a congressperson would be expected to beat the market over 180 days based only on features of the congressperson. The baseline model is 52% accurate and predicts that the congressperson will not beat the market. We used a voting classifier model and a Random Forest model for our predictions. Both of our models were 56% accurate. The strength over baseline is minor, but any advantage can be valuable when predicting stock prices. We hope that if combined with data on the stock tickers in question, these findings could help an investor find profitable investments.


## **Conclusions and Recommendations**

There is no clear evidence for widespread insider trading with Congress. The majority of congress members in our analysis underperformed the market over a six month timeframe. We hypothesize that this is because members of congress do not regularly possess insider information.  When we look at the frequency of trades during the Coronavirus pandemic, we do see a clear increase in the frequency of trades starting around January 2020, which may indicate insider knowledge that the stock market would decline.

In general, congressmen and congresswomen had an average return of 14.89% over 180 days. If we compare the S&P 500 index as the average market performance during the investment timespan, it performed slightly worse at 13.87% on average.  We also measured the side-by-side performance of congress members’ stock purchases against the S&P 500 performance at 30, 60, and 90 days.

Congress’ stock investments did not beat the S&P 500 over a 30 day timespan, but Congress did beat the S&P 500 at the 60 day, 90 day, and 180 day time periods. The best and worst performing investors in Congress had very few transactions. We chose to remove congressmen who had two or fewer trades during our timespan from 2013 through 2020.  After our filtering, the investors with the best average returns over the S&P 500 from 2013-2020 were: Brian Mast, Doug Lamborn, Michael Garcia, Alan Lowenthal, Roger Marshall, and Nancy Pelosi. These members of congress had investments that beat the market average by 15% over ~six months.

We also noticed that some members of Congress made a large quantity of stock trades.  This was particularly notable for David Perdue, Jr, who had over 1600 stock trades between 2015 and 2020.  This was ~3-4x higher than the congress member with the next most trades. However, this did not result in him beating the market average over six months.

We created a model to predict whether or not an investment would be able to beat the S&P 500 using features of the Congressperson who bought it. The goal of this was twofold. First, to see if there are common predictors that suggest congress members will be able to beat the market, and second, to see if savvy investors could use the data from the STOCK Act to improve their investing strategy. The baseline accuracy for predicting if a transaction would beat the market was 52%. The model has an accuracy of 56% and a precision of 57%. This is not a strongly predictive model, but it beats the baseline and any potential advantage can be helpful when investing. The features that stand out as significant are the total amount of money raised while campaigning, the percent of donations from small donors, and the number of years spent in office.

Unfortunately, several key members of Congress were absent from our datasets.  These members include Chris Collins, who pleaded guilty to insider trading in 2019. However, it was deemed that his insider knowledge was acquired outside of his role as a Senator.  Additionally, three senators who voted ‘no’ on the Stock Act of 2012 did not have any records in the databases we used, but we do know that they did disclose their stock sales activity.  One of these Senators was under investigation last year for selling most of his stock holdings directly following a classified briefing on the severity of the coronavirus in February 2020, but the Justice Department closed this investigation last year. Even without this Senators’ stock information included, we see a large increase in the frequency of stock sales at the beginning of 2020.

The Stock Act was passed in 2012 to prevent Congress members from profiting on private knowledge. Several members of Congress had suspicious transactions in the lead-up to coronavirus shutting down the U.S. economy.  Curiously, some of these congress members were not present in our data sources. Additionally, of the 435 members of Congress only 138 unique members of Congress were present in our data.  It is possible that our primary data source may be missing records, but we believe that the absence of many members means that many members do not invest in individual stocks.  They may instead prefer to invest in index funds, or other investment vehicles.  If our thesis is true, this means that most members of congress prefer low-risk, long-term investments, and are not investing in a way that could be characterized as insider-trading.   If we were pressed to highlight suspicious activity, we would highlight unique times when congress members did have more information than the public. The coronavirus is one such unique event.


### **Sources**

[Stock Act](https://www.congress.gov/112/plaws/publ105/PLAW-112publ105.htm)

[Financial Disclosure by Federal Officials](https://fas.org/sgp/crs/misc/R43186.pdf)

[Chris Collins - Insider Trading Case](https://www.cityandstateny.com/articles/politics/news-politics/rep-chris-collins-flip-flops-on-his-guilt.html)

[Average Stock Market Return:](https://www.nerdwallet.com/article/investing/average-stock-market-return)

[Senators who voted no on the STOCK Act ](https://www.politico.com/story/2012/02/insider-trading-bill-heads-to-house-072391)

[2020 congressional insider trading scandal](https://en.wikipedia.org/wiki/2020_congressional_insider_trading_scandal)

[Congress.gov](https://www.congress.gov/members?searchResultViewType=expanded)

[Congress Donations](https://www.opensecrets.org/elections-overview/large-vs-small-donations)

[House Stock Watcher](https://housestockwatcher.com/)

[Senate Stock Watcher ](https://senatestockwatcher.com/)
