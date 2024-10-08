# Flight-Passenger-Clustering
In this project. I tried to group flight passengers into several clusters. <br>

## Data Modelling Outline
The following are a few steps in the modeling technique used on this project:
1. Import dataset
2. Data understanding
3. Data cleaning & preprocessing
4. Feature Engineering
5. Machine learning modeling
6. Conclusion

## Load the Dataset
The dataset contains 23 columns and 62988 rows. The dataset is about the flight information of each member.

## Data Understanding
Below is the description for each column or feature:
* MEMBER_NO: ID Member.
* FFP_DATE: Frequent Flyer Program Join Date.
* FIRST_FLIGHT_DATE: Member first flight date?
* GENDER: Gender of member.
* FFP_TIER: Frequent Flyer Program Tier.
* WORK_CITY: Member's hometown.
* WORK_PROVINCE: Member's home province.
* WORK_COUNTRY: Member's home country.
* AGE : Member's age.
* LOAD_TIME: The date data taken.
* FLIGHT_COUNT: Member flight count.
* BP_SUM: Flight plan.
* SUM_YR_1: Fare revenue.
* SUM_YR_2: Votes price.
* SEG_KM_SUM: Total flight distances.
* LAST_FLIGHT_DATE: Member last flight date
* LAST_TO_END: The time from the last flight to the end of the observation window.
* AVG_INTERVAL: average flight time interval.
* MAX_INTERVAL: Maximum flight interval.
* EXCHANGE_COUNT: Number of points exchanged.
* avg_discount: Average discount rate.
* Points_Sum: Total cumulative points
* Point_NotFlight: Points not used by the customer.

## Data cleaning & preprocessing
Data cleaning is used to identify data that has a NaN value so that it can be processed further using machine learning modeling. The preprocessing process is used to convert the value of a specific column into the appropriate value for modeling purposes. Data preprocessing will therefore include a data cleaning process to detect any missing values in each column. There are missing value in features 'WORK_PROVINCE','WORK_CITY','SUM_YR_1','AGE','SUM_YR_2','WORK_COUNTRY','GENDER'. For 'AGE' we will fill the missing value with the mean of 'AGE' data and the rest with the median.

## Exploratory Data Analysis
* FFP tier distribution based on age. <br>
<img src="https://user-images.githubusercontent.com/89758536/220881525-092ea4a7-edd4-4ec4-aa61-aa189488c743.png" width="500"> <br>

As we can see most people belong on FFP tier 4 and the highest user of FFP tier 6 is on group age of 41-60. The airlines can focus more on advertising FFP tier 4 and FFP tier 6 spesifically for group age of 41-60. <br>

## Feature Engineering
Feature engineering is used to create new features such as new columns and dummy variables to make the data more precise. The goal of feature engineering is to create a new set of columns that will produce more accurate results for machine learning modeling. According to Tao, Y. (2020). We will use LRFMC analysis. LRFMC analysis is a method used to rank and group customers based on the length of customer relationship, recency, frequency, monetary total of their recent transactions and average discount to identify the best customers and perform targeted marketing campaigns. Recency can be known from 'LAST_TO_END' column. Frecuency can be known from 'FLIGHT_COUNT' column. Monetary can be known from 'SEG_KM_SUM' column. The length of customer relationship can be known by substracting the FPP join date from the date data is taken (LOAD_DATE) and average discount that can be gotten from 'avg_discount'

## Result and Visualization
### Elbow plot
<img src="https://github.com/user-attachments/assets/a5934848-43ff-4854-8318-c3cf8b7114c9" width="1000"><br>

The elbow looked like when the value of K is equal to 4 or 5.

### Silhouette method
<img src="https://github.com/user-attachments/assets/6c734607-988f-43c1-bea4-d12f7d7e9480" width="1000"><br>

As we can see K = 4 gives as the highest score. So for this data we decide to use K = 4

### Clustering & RFM chart
<img src="https://github.com/user-attachments/assets/6cfa5b6a-5318-4dc7-b300-238c5a90a2da" width="500"><br>

<img src="https://github.com/user-attachments/assets/201cfc03-6e41-4782-ab32-9675dcce5a6c" width="500"><br>

The graphs show the classification of each cluster based on length of customer relationship, recency, frequency, monetary total of their recent transactions and average discount

## Conclussion
After we did clustering, there are four type of customers.

* Group 1: This group consist of 11921 customers. This is a low valued customer. It has low value of all element of LRFMC. For these users, they should be maintained as much as possible, and then stimulate their consumption to stimulate their consumption vitality.
* Group 2: This group consist of 8013 customers. Others low except high L. This means these customers have been joining our FFP program for so long but they are not very active. It could mean that they are seasonal reasons or related to promotional activities. For such users, it is necessary to maintain and stimulate consumption as much as possible.
* Group 3: This group consist of 7884 customers. R is high while L, F, and M is relatively low. It means this group is a 'new customer' group. We should treat this group with a good care and give them a various offer to make them keep with us.
* Group 4: This group consist of 7563 customers. It has moderate value of L and high value of F and M but low value of R. It indicates that they are 'valuable customers' but we also consider consider them as 'lost customers'. we should try to grasp the latest information of these customers, ask them if there was anything that made them uncomfortable when using our airlines so we could fix it. Give them the best offer to make them come back to us.
