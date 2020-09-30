# Predicting Snapchat Political Advertisement Impressions in the U.S. for the Year 2019 based on Amount Spent and Number of Days
## Background
Political advertisements have a long history in [mass media.](https://onlinelibrary.wiley.com/doi/abs/10.1002/9781405186407.wbiecp049.pub2) It is interesting to consider how the amount spent and number of days that an ad runs for might influence the number of impressions. We'll take a look at public data provided by [Snapchat, a social-media platform,](https://phys.org/news/2018-06-snapchat.html) to determine how these two variables play a role in predicting the success of an ad.

## Business Question
***Can we predict the number of impressions for a political ad on Snapchat in the United States FY2019 based on amount of money spent and days ad was running?***

## Data Sources
We used open data from Snapchat's [Political Ads Library.](https://www.snap.com/en-US/political-ads/) We took the [raw data](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/Snapchat_Raw_Data.xls) and [filtered it](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/Snapchat_Filtered_Data.xlsx) to analyze U.S. ads only to control for factors such as app usage and number of [users](https://www.statista.com/statistics/545967/snapchat-app-dau/#:~:text=With%20an%20estimated%2046%20million,Snapchat%20easily%20ranks%20among%20the). We calculated how long ads ran for and looked at total spending to perform simple and mulitple [linear regression analysis.](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/Snapchat_Data_Analysis.xlsx)

## Data Analysis
1. "Impressions" is the number of times the ad has been viewed by Snapchatters.
2. "Spend" is amount of total money spent in USD.
3. "Days_Ad_Up" is the number of days an ad ran from its start to end date.

**How significant are amount spent and number of days as independent variables?**
![insert](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/SummaryOutputMulitpleRegression.png)

The output summary gives us a R Squared value of 0.738, with the best fit line accounting for 74% of the data points. The F significance of 0 means that there is a very low probability that none of our variables matter. The standard error of 4,055,869.73 represents the average distance that our points lie from the best fit line. Given that it is in units of our response variable, this is fair as the number of Impressions range from [3 to 234,901,755.](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/Snapchat_Data_Analysis.xlsx) A coefficient of 334.37 for Spend implies a positive relationship while -2225.54 for Days_Ad_Up tells us that number of days has a negative relationship with Impressions.

![image](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/TopAdsImpressions.png)

We see that p-value < 0.01 for Spend adheres to p-value < 0.05, the criteria to determine statistical significance. Days gives us a p-value of 0.3 which is greater than 0.05, implying that we can not reject the null hypothesis and that Days is not statistically significant. The top 10 advertisements table shows the number of days does not seem to relate to the number of impressions, with one ad running for 28 days recieving more impressions than another ad running for 191 days.

**Can we predict number of impressions based on Spend?**

![graph](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/SpendImpressionsScatterGraph.png)

Creating a linear regression scatter graph with Spend as our significant independent variable shows that most ads receive less than 50 million impressions. However, a majority of ads that are more successful spend upwards of $100,000. Using the equation **Impressions = 24494.67 + 333.71(Spend)**, we can calculate predicted impressions and error to find outliers where error is > 2 * (Standard Error of Regression). The number of high outliers is [16, which is 1.36% of all outliers.](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/Snapchat_Data_Analysis.xlsx)

![insertalso](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/finalHistogramSpend.png)

Our histogram graph further reinforces our findings in finding that most organizations spend around $250. Yet, as evidenced by the lower number of advertisements that spend more, higher paying seems to have a higher correlation with increased number of impressions.

## Summary
We can conclude that amount spent is a significant variable when it comes to predicting the number of impressions that a political advertisement recieves. For an ad to be successful in reaching the largest audience, organizations that are able to spend more are more likely to have a competitive edge. Our linear regression shows us that for an ad to be a high outlier, hundreds of thousands of dollars . While we are confident in Spend as a significant variable, more data such as how often Snap displays these ads, prominence of the ad's position, and user actions after viewing is needed. For now, this tells us that organizations with higher buying power are associated with higher levels of effectiveness in terms of their ad's reach.
