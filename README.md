# Predicting Snapchat Political Advertisement Impressions in the U.S. for the Year 2019 based on Spend and Days Running
## Background
Political advertisements have a long history in [mass media.](https://onlinelibrary.wiley.com/doi/abs/10.1002/9781405186407.wbiecp049.pub2) The addition of [Snapchat, a social-media platform,](https://phys.org/news/2018-06-snapchat.html) as a channel for such ads has been a recent development. Ads on Snapchat mostly target a younger audience with voter eligibility, primarily Gen-Z and millenials. It is interesting to consider how the buying power of organizations and the number of days that an ad runs for might influence the number of impressions an ad recieves. We'll take a look at public data provided by Snapchat to determine how these two variables play a role in predicting the succcess of an ad.

## Business Question
***Can we predict the number of impressions for a Snapchat political ad in the United States FY2019 based on amount of money spent and days ad was running?***

## Data Sources
We'll use open data from Snapchat's online [Political Ads Library.](https://www.snap.com/en-US/political-ads/) We took the [raw data](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/Snapchat_Raw_Data.xls) and [filtered it](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/Snapchat_Filtered_Data.xlsx) to only analyze political ads in the U.S. to control for factors such as app usage and number of [users](https://www.statista.com/statistics/545967/snapchat-app-dau/#:~:text=With%20an%20estimated%2046%20million,Snapchat%20easily%20ranks%20among%20the). We then focused on amount spent and calculated days ad was up to perform simple and mulitple [linear regression analysis.](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/Snapchat_Data_Analysis.xlsx)

## Data Analysis
1. Impressions is the number of times the ad has been viewed by Snapchatters.
2. Spend is amount of total money spent in USD.
3. Days Ad Up is the number of days an ad ran for between its start and end date.

**How significant are amount spent and number of days as independent variables?**
![insert](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/SummaryOutputMulitpleRegression.png)

The output summary gives us a R Squared value of 0.738, with the best fit line accounting for 74% of the data points. The F significance of 0 means that there is a very low probability that none of our variables matter. The standard error of 4,055,869.73 represents the average distance that our data points lie from the best fit line. Given that it is in units of our response variable, impressions, this is fair as the number of impressions range from [3 to 234,901,755.](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/Snapchat_Data_Analysis.xlsx) A coefficient of 334.37 for Spend implies a positive relationship while -2225.54 for Days_Ad_Up tells us that number of days has a negative relationship with impressions. Looking at the p-value, we can see that while p-value < 0.01 for Spend, Days gives us a p-value of 0.3 which is larger than 0.05, the value to determine significance. 

![image](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/TopAdsImpressions.png)

Looking at the data for the top 10 advertisements based on number of impressions, we can see that Days being an insignificant variable is validated. The number of days does not seem to be related to the number of impressions, with one ad up for 28 days recieving more impressions than another ad running for 191 days.

**Can we predict number of impressions based on the significant variable Spend?**
![graph](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/SpendImpressionsScatterGraph.png)

Creating a linear regression scatter graph with Spend as our independent variable shows us that around $50,000 is spent for most ads with these ads recieving less than 50 million impressions. Using the predicted impressions equation **Impressions = 24494.67 + 333.71(Spend)** based on our slope and intercept, we can calculate predicted impressions, find the error, and determine the number of outliers where error is > 2 * (Standard Error of Regression). The number of outliers is 16, which is 1.36% of all outliers.

![insert4](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/updatedAdSpendHistogram.png)

Our histogram graph further reinforces our findings 



## Summary
