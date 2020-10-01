# snapchat-election-ad-data-predict-impressions
## Background Information
In this project, I looked at Political Advertisement Data from [Snapchat](https://www.snap.com/en-US/political-ads/) and focused on data from the United States. I considered __Spend__, __Age Range__, and __Run Time__ as factors that might affect the number of impressions an advertisement receives. I analyzed data from 2018 and 2020, 2018 being a midterm election year and 2020 being the presidential election year. 2019 is an off-year for elections and was omitted. 

I thought __Spend__ would be ideal to consider because, as paid advertisements go, the the number of impressions should correspond to the amouont spent on running ads. I was interested in considering the __Age Range__ given that Snapchat caters toward a younger audience but not all US Snapchat users are eligible to vote. I also wondered if the __Run Time__ would affect the number of impressions and if it would be as strong of a factor as, say, __Spend__ might be in predicting impressions. 

__Spend__ data was not filtered or manipulated in any way. It refers to the amount (in USD) an advertiser spends on an advertisement. 

__Age Range__ refers to the target age range, if specified, for an advertisement. The data was categorized on a scale of 0-2 to simplify the values. If an age was not specified, it received a 0. If the age range was under 18, it received a 1 and if it was 18+, it received a 2. If the age range was mixed/spanned both under 18 and 18+ ages (ex: 17-19), then it received a 1.5. 

__Run Time__ is how long an advertisement ran for on Snapchat in days. It is calculated by subtrating the Start Date from the End Date and its unit is days. Some advertisers put their end date under the Start Date category and their start date under the End Date category, so I reversed the calculation to obtain a positive value. 

### Business Question
How do the average amount advertisers spend on an advertisement (__Spend__), the target age range for an advertisement (__Age Range__), and the amount of time for which an advertisement runs (__Run Time__) affect the number of impressions an advertisement receives on Snapchat?

## Data Sources
The [Snapchat Political Ads Library](https://www.snap.com/en-US/political-ads/) provides open-source data for download. 

[Instructions for Filtering Data](https://github.com/viv-sun/snapchat-election-ad-data-predict-impressions/blob/master/Instructions%20for%20Filtering%20Data.docx) provides step-by-step instructions on how I filtered and cleaned the data.

[Snapchat Political Ads Raw Data 2018](https://github.com/viv-sun/snapchat-election-ad-data-predict-impressions/blob/master/Snapchat%20Political%20Ads%20Raw%20Data%202018.xlsx) shows the 2018 raw data downloaded from Snapchat's website. 

[Snapchat Political Ads Raw Data 2020](https://github.com/viv-sun/snapchat-election-ad-data-predict-impressions/blob/master/Snapchat%20Political%20Ads%20Raw%20Data%202020.xlsx) shows the 2020 raw data downloaded from Snapchat's website. 

[Snapchat Political Ads Filtered Data 2018](https://github.com/viv-sun/snapchat-election-ad-data-predict-impressions/blob/master/Snapchat%20Political%20Ads%20Filtered%20Data%202018.xlsx) shows the 2018 data after I did some data cleaning. 

[Snapchat Political Ads Filtered Data 2020](https://github.com/viv-sun/snapchat-election-ad-data-predict-impressions/blob/master/Snapchat%20Political%20Ads%20Filtered%20Data%202020.xlsx) shows the 2018 data after I did some data cleaning. 


## Data Analysis/Metrics 
For both data sets, I conducted correlation analyses for the three dependent variables (__Spend__, __Age Range__, and __Run Time__). I then conducted a multiple linear regression with these three dependent variables and __Impressions__ as the independent variable. 

### Charts: Advertisement Run Time vs Impressions (2018)
![alt text](https://github.com/viv-sun/snapchat-election-ad-data-predict-impressions/blob/master/Advertisement%20Run%20Times%20and%20Impressions%20(2018)%20chart.jpg) 

I compared only one variable (the __Run Time__) against the impressions data from 2018. The R squared is really low, implying that perhaps it is not the line of best fit. This may be due to the outliers, though. Perhaps the __Run Time__ may not have as large of an effect on impressions as I would have assumed... 

### Charts: Advertisement Run Time vs Impressions (2020)
![alt text](https://github.com/viv-sun/snapchat-election-ad-data-predict-impressions/blob/master/Advertisement%20Run%20Times%20and%20Impressions%20(2020)%20chart.jpg)

I compared only one variable (the __Run Time__) against the impressions data from 2020. The R squared is really low, implying that perhaps it is not the line of best fit. This may be due to the outliers, though. Perhaps the __Run Time__ may not have as large of an effect on impressions as I would have assumed... 

### Correlation: 2018
![alt text](https://github.com/viv-sun/snapchat-election-ad-data-predict-impressions/blob/master/Correlation%20-%202018%20Snapchat%20Data.jpg)

The correlations between these three variables are fairly low/close to zero, which means that they likely do not have a huge influence on each other (which is ideal). 

### Correlation: 2020
![alt text](https://github.com/viv-sun/snapchat-election-ad-data-predict-impressions/blob/master/Correlation%20-%202020%20Snapchat%20Data.jpg)

The correlations between these three variables are fairly low/close to zero, which means that they likely do not have a huge influence on each other (which is ideal). 

### Multiple Linear Regressions: 2018
![alt text](https://github.com/viv-sun/snapchat-election-ad-data-predict-impressions/blob/master/Multiple%20Linear%20Regression%20-%202018%20Snapchat%20Data.jpg)

The R squared value here is 0.803, which means that the line (our final formula, created with the intercept and coefficients noted here) is a good fit for about 80.3% of the data. 

The standard error is 356684.84 and shows how spread out our data points are for predicting impressions. This means that the data is really spread out. 

The coefficients and the intercept can be used to create our final formula to predict impressions. Please scroll down to see the formula. 

The p-values tell us if the varaibles are significant in predicting the independent variable (the impressions). Here, they are all extremely small, less than 0.05, which mean that there is likely a relationship between our dependent variable(s) and our independent variable. This means that the __Spend__, __Age Range__, and __Run Time__ all likely have some effect on predicting the number of impressions. 

The F significance shows the probability that none of these variables matter for the final formula to predict impressions. The lower it is, the more it means that our variables might contribute something to the final formula. This F significance is extremely low (7.4 x 10^-154), which is great - it means that our variables are likely great contributors to and have some influence on predicting impressions. 

### Multiple Linear Regressions: 2020
![alt text](https://github.com/viv-sun/snapchat-election-ad-data-predict-impressions/blob/master/Multiple%20Linear%20Regression%20-%202020%20Snapchat%20Data.jpg) 

The R squared value here is 0.0007, which means that the line (our final formula, created with the intercept and coefficients noted here) is not a good fit for our data at all. It's an extremely low R squared value and is extremely concerning. 

The standard error is 4251059.42 and shows how spread out our data points are for predicting impressions. This means that the data is really spread out. 

The coefficients and the intercept can be used to create our final formula to predict impressions. Please scroll down to see the formula. 

The p-values are really high for all three of the dependent variables, and are highest for the __Spend__ and __Run Time__. This was interesting since the smallest p-value was for the __Age Range__ variable, which I thought might be the one that has the highest p-value because of my simplifying the data. Te high p-values mean that I cannot use these three variables for my final formula. This likely explains why the R squared is so low - if the formula is just y = b, b being the intercept, then it's just a straight line and can't be very accurate. 

The F significance is 0.923, which means that the variables are not likely to be great contributors in terms of predicting impressions. This matches our previous results. 

 
### Predicting Impressions: 2018
![alt text](https://github.com/viv-sun/snapchat-election-ad-data-predict-impressions/blob/master/Predicting%20Impressions%20-%202018%20Snapchat%20Data.jpg) 

In this formula, we can see that as the age range increases, the number of impressions decreaases. However, as the __Spend__ and the __Run Time__ increase, the number of impressions increase as well. We can tell from the higher coefficient for  __Run Time__  that __Run Time__ has a larger effect on the number of impressions than the __Spend__ variable. As such, the amount of time an ad runs for (followed by the amount spent on the ad) will have a big impact on the number of impressions it receives. 

### Predicting Impressions: 2020
![alt text](https://github.com/viv-sun/snapchat-election-ad-data-predict-impressions/blob/master/Predicting%20Impressions%20-%202020%20Snapchat%20Data.jpg)

As mentioned in the multiple linear regressions section for 2020, the formula for this only included the intercept because I had to omit these variables from the equation. This final formula is just a straight line, which likely explains why the R squared is so low; it is not a good representation nor predictor for impressions for 2020. 

## Summary

We have to keep in mind that the 2018 raw data is incomplete and starts in June. The 2020 data is also incomplete, as 2020 is not yet over (as of the time of writing this summary in September 2020). This may have an effect on how accurate the data is for predicting the number of impressions. 

Something to keep in mind as well are potential reasons for why the 2020 formula to predict impressions is wonky. Does it really mean that the amount of money spent on an ad, the amount of time an ad runs for, and the target age range of an ad have no bearing on the impressions an ad gets? It goes against the inherent nature of paid advertising and the results for 2018. This raises the following questions. 

For the __Run Time__ variable in 2020, could the ads have run during unopportune times, like at 3am or during the workday/classes when fewer people are on Snapchat? Did they stretch over a period of time during which Snapchat saw a decrease in daily usage? Were advertisers targeting the right geographic locations? Were some times of day or geographic regions more expensive than others? This could then tie into the __Spend__ variable - if advertisers are spending money but not targeting the right people in the right locations or during the right times, then it would not affect impressions. 

Ultimately, more research needs to be done to consider the other extenuating factors for 2020, too - things like targeted geographic location, how long users looked at the ads, and the age ranges (consider a 17-19 age range and a 17-40 age range, which both received the same score of 1.5). Would the fact that 2020 is a presidential election year have any bearing on the results? 
