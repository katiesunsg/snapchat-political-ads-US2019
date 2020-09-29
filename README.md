# Predicting Snapchat Political Advertisement Impressions in the U.S. for the Year 2019 based on Spend and Days Running
## Background
Political advertisements have a long history in [mass media.](https://onlinelibrary.wiley.com/doi/abs/10.1002/9781405186407.wbiecp049.pub2) The addition of [Snapchat, a social-media platform,](https://phys.org/news/2018-06-snapchat.html) as a channel for such ads has been a recent development. Ads on Snapchat mostly target a younger audience with voter eligibility, primarily Gen-Z and millenials. It is interesting to consider how the buying power of organizations and the number of days that an ad runs for might influence the number of impressions an ad recieves. We'll take a look at public data provided by Snapchat to determine how these two variables play a role in predicting the succcess of an ad.

## Business Question
***Can we predict the number of impressions for a Snapchat political ad in the United States FY2019 based on amount of money spent and days ad was running?***

## Data Sources
We'll use open data from Snapchat's online [Political Ads Library.](https://www.snap.com/en-US/political-ads/) We took the [raw data](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/Snapchat_Raw_Data.xls) and [filtered it](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/Snapchat_Filtered_Data.xlsx) to only analyze political ads in the U.S. to control for factors such as app usage and number of [users](https://www.statista.com/statistics/545967/snapchat-app-dau/#:~:text=With%20an%20estimated%2046%20million,Snapchat%20easily%20ranks%20among%20the). We then looked at amount spent and calculated days ad was up to perform simple and mulitple [linear regression analysis.](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/Snapchat_Data_Analysis.xlsx)

## Data Analysis
1. Impressions is the number of times the ad has been viewed by Snapchatters.
2. Spend is amount of total money spent in USD.
3. Days Ad Up is the number of days an ad ran for between its start and end date.

**How significant are amount spent and number of days as independent variables?**
![insert](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/SummaryOutputMulitpleRegression.png)

![insert2](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/TopAdsImpressions.png)

![insert3](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/SpendImpressionsScatterGraph.png)

![insert4](https://github.com/katiesunsg/snapchat-political-ads-US2019/blob/master/updatedAdSpendHistogram.png)

## Summary
