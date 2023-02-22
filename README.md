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
Data cleaning is used to identify data that has a NaN value so that it can be processed further using machine learning modeling. The preprocessing process is used to convert the value of a specific column into the appropriate value for modeling purposes. Data preprocessing will therefore include a data cleaning process to detect any missing values in each column. There are missing value in features 'WORK_PROVINCE','WORK_CITY','SUM_YR_1','AGE','SUM_YR_2','WORK_COUNTRY','GENDER'. For now we will decide to
