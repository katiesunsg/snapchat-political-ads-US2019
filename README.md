# Predicting Snapchat Political Advertisement Impressions in the U.S. FY2019 based on Amount Spent and Number of Days
## Background
Political advertisements have a long history in [mass media.](https://onlinelibrary.wiley.com/doi/abs/10.1002/9781405186407.wbiecp049.pub2) It is interesting to consider how the amount spent and number of days an ad runs for might influence the number of impressions. We'll take a look at public data provided by [Snapchat](https://phys.org/news/2018-06-snapchat.html) to determine how these two variables play a role in predicting an ad's success.

## Business Question
***Can we predict the number of impressions for a political ad on Snapchat in the U.S. FY2019 based on amount spent and number of days ad ran?***

## Data Sources
We used open data from Snapchat's [Political Ads Library.](https://www.snap.com/en-US/political-ads/) We took the [raw data](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/Snapchat_Raw_Data.xls) and [filtered it](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/Snapchat_Filtered_Data.xlsx) to analyze U.S. ads only to control for factors such as app usage and number of [users](https://www.statista.com/statistics/545967/snapchat-app-dau/#:~:text=With%20an%20estimated%2046%20million,Snapchat%20easily%20ranks%20among%20the). We calculated how long ads ran for and looked at total spending to perform simple and multiple [linear regression analysis.](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/Snapchat_Data_Analysis.xlsx)

## Data Analysis
1. "Impressions" is the number of times the ad has been viewed by Snapchatters.
2. "Spend" is amount of total money spent in USD.
3. "Days_Ad_Up" is the number of days an ad ran from its start to end date.

**How significant are amount spent and number of days as independent variables?**
![insert](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/SummaryOutputMulitpleRegression.png)

The output summary gives us a R Squared value of 0.738, with the best fit line accounting for 74% of the data points. The F significance of 0 means that there is a very low probability that none of our variables matter. The standard error of 4,055,869.73 represents the average distance that our points lie from the best fit line. Given that it is in units of our response variable, this is fair as the number of Impressions range from [3 to 234,901,755.](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/Snapchat_Data_Analysis.xlsx) A coefficient of 334.37 for Spend implies a positive relationship while -2225.54 for Days_Ad_Up suggests that number of days has a negative relationship with Impressions.

![image](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/TopAdsImpressions.png)

A p-value < 0.01 for Spend adheres to p-value < 0.05, the criteria to determine statistical significance. Days gives us a p-value of 0.3 which is greater than 0.05, implying that we can not reject the null hypothesis and that Days is not statistically significant. The top 10 advertisements table suggests the number of days does not relate to higher impressions, with one ad running for 24 days receiving more impressions than another ad running for 191 days.

**Can we predict number of impressions based on Spend?**

![graph](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/SpendImpressionsScatterGraph.png)

Creating a scatter graph with Spend as our independent variable shows us that most ads receive fewer than 5 million impressions and spend less than $25,000. Using the equation **Impressions = 333.71(Spend) + 24495**, we can calculate predicted impressions and error to find outliers where error is > 2 * (Standard Error of Regression). The number of high outliers is [16, which is 1.36% of all outliers.](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/Snapchat_Data_Analysis.xlsx)

![insertalso](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/finalHistogramSpend.png)
![alsoinsert](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/final3impressions.png)

Our histograms above delves deeper to find that 76% of organizations spent less than $1,000 and 88% of total ads received fewer than 1 million impressions. However, ads that are successful spend at least ~$10,000, with the top 5 successful ads spending upwards of $250,000 and receiving 50 million impressions with a high of ~235 million impressions on a budget of $450 million. This implies that higher amount spent generally seems to correlate with higher impressions.

## Summary
We can conclude that amount spent is a significant variable when it comes to predicting the number of impressions that a political advertisement receives. For an ad to be successful in reaching the most people, organizations that spend more are more likely to have a competitive edge. While we are confident in Spend as a significant variable, more data such as how often Snap displays these ads, prominence of the ad, and user actions after viewing is needed. For now, this tells us that organizations with higher buying power are able to reach higher levels of ad impressions.
