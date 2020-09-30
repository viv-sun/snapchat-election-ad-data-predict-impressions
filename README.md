# snapchat-election-ad-data-predict-impressions
## Background Information
In this project, I am looking at __Spend__, __Age Range__, and __Run Time__. Spend refers to the amount (in USD) spent by the advertiser over the course of the campaign (from the start to the end date). Age Range refers to the ages that are being targeted in the advertisement. Run Time refers to how long the ad was run on the platform (from start to end date). 

Age Range was categorized on a scale of 0-2 to simplify the data. If an age was not specified, it received a 0. If the age range was under 18, it received a 1 and if it was 18+, it received a 2. If the age range was mixed/spanned both under 18 and 18+ ages, then it received a 1.5. 

### Business Question

## Data Sources
[Snapchat Political Ads Library] (https://www.snap.com/en-US/political-ads/) provides open-source data for download. The data for the years 2018, 2019, and 2020 can be downloaded here (although I only focused on 2018 and 2020). 

## Data Analysis/Metrics 

### Correlation
#### Correlation: 2018
![alt text](https://github.com/viv-sun/snapchat-election-ad-data-predict-impressions/blob/master/Correlation%20-%202018%20Snapchat%20Data.jpg)

#### Correlation: 2020
![alt text](https://github.com/viv-sun/snapchat-election-ad-data-predict-impressions/blob/master/Correlation%20-%202020%20Snapchat%20Data.jpg)

#### Multiple Linear Regressions
##### Multiple Linear Regressions: 2018
![alt text](https://github.com/viv-sun/snapchat-election-ad-data-predict-impressions/blob/master/Multiple%20Linear%20Regression%20-%202018%20Snapchat%20Data.jpg)

##### Multiple Linear Regressions: 2020
![alt text](https://github.com/viv-sun/snapchat-election-ad-data-predict-impressions/blob/master/Multiple%20Linear%20Regression%20-%202020%20Snapchat%20Data.jpg) 

#### Predicting Impressions 
##### Predicting Impressions: 2018
![alt text](https://github.com/viv-sun/snapchat-election-ad-data-predict-impressions/blob/master/Predicting%20Impressions%20-%202018%20Snapchat%20Data.jpg)

##### Predicting Impressions: 2020
![alt text](https://github.com/viv-sun/snapchat-election-ad-data-predict-impressions/blob/master/Predicting%20Impressions%20-%202020%20Snapchat%20Data.jpg)

## Summary
