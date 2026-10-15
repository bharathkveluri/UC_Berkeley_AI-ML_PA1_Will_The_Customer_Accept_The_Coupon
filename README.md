# UC Berkeley ML/AI Professional Certificate - Practical Application 1: Will the Customer Accept the Coupon?

# Goal:
Goal of this assignment is to use the knowledge about visualizations and probability distributions to distinguish between customers who accepted a driving coupon versus those who did not.

# Dataset:

coupons.csv stored in below location will be used to perform this analysis.
**Link**: https://github.com/bharathkveluri/UC_Berkeley_AI-ML_PA1_Will_The_Customer_Accept_The_Coupon/blob/main/data/coupons.csv

# Jupyter Notebook:

Below is the Jupyter Notebook written in Python that contains the code required to perform the analysis.
**Link:** https://github.com/bharathkveluri/UC_Berkeley_AI-ML_PA1_Will_The_Customer_Accept_The_Coupon/blob/main/UCB_Practical_Application_1.ipynb

# Exploratory Data Analysis:
Exploratory Data Analysis was performed to understand the data and the data quality. The dataset contains 12684 rows and 26 columns.

**Missing Data:**
Dataset was analyzed to understand if there are any null values in any columns and identified below findings:
* Only 6 of 26 columns have gaps
* car is missing data for 12,576 of 12,684 rows (99.15%). So, if the column is dropped, there won't be any impact and it will improve the data quality
* The remaining 5 columns (CoffeeHouse, Restaurant20To50, CarryAway, RestaurantLessThan20 and Bar) are missing data between 0.84 % and 1.71%. This is a small percentage gap and the valules can be substituted without compromising the data quality.
* The second column is named as "Passanger" instead of "Passenger".
  
Below visualization shows the percentage of rows missing the data in 6 columns that contains null values.
<img width="882" height="425" alt="image" src="https://github.com/user-attachments/assets/b6ece662-89eb-4750-84d4-a1fa2485e056" />

**Problematic Data:**
Dataset was analyzed to understand if there any duplicate rows. 
* Duplicate Records: There are 74 duplicate rows in the dataset. The data doesn't have an identifier that specifically outlines that the records are unique. it is possible that two people that submitted responses have similar profile or present similar characteristics.

# Data Cleaning:

Below cleanup actions were taken to improve the data quality:
* Duplicate Records: Dropping these records from the dataset doesn't improve missing data quality sharply. So, we are going to assume that the 74 duplicate rows are indeed genuine records.
* Drop "car" column since 99.15% users do not have the data.
* Replace missing data using "Mode" in columns remaining 5 columns (CoffeeHouse, Restaurant20To50, CarryAway, RestaurantLessThan20 and Bar). "Mean" is not an appropriate choice because the data in these columns is not numeric in nature. "Median" is not appropriate either because it provides a value which is at the middle. Instead, Mode will be able to substitute the missing data with the most frequent value that appeared in the dataset.

# General Data Findings:
* The percentage of drivers who accepted the coupon across all coupon types was 56.84%.
  <img width="379" height="399" alt="image" src="https://github.com/user-attachments/assets/1ae039b9-5048-45f8-b177-031bf3d6db7e" />
* Coffee House coupons were the most accepted coupons by the drivers.
  <img width="570" height="521" alt="image" src="https://github.com/user-attachments/assets/51688a51-587d-48cc-84b3-8a4af8da7c81" />
* The coupons acceptance rate was 51.47% on a day with temperature at 80°F. This is a strong indicator that coupons distribution on a day with higher temperature will yield more business.
  <img width="877" height="426" alt="image" src="https://github.com/user-attachments/assets/e1fffc20-d659-486f-8a66-a13420816902" />
 
# Bar Coupons: 
Performed analysis on Bar Coupon type to understand what driver characteristics demonstrate strong coupon acceptance rates.
**Key Findings:**
* Drivers who accept bar coupons are mainly people who already go to bars regularly. Only 41.0% of bar coupons were accepted and this compares poorly against 56.84% of the drivers who accepted coupons across all coupon types.
  <img width="369" height="385" alt="image" src="https://github.com/user-attachments/assets/0399dc59-5ea8-465a-9d13-57d23dff5f35" />
* Drivers who go to bar atleast 3 or more times are most likely to accept bar coupons. The acceptance rate (in%) for this groups is 76.88% meaning 3 out of 4 people will accept the coupons if they are visiting the bar 3 or more times in a month.
* Drivers who are over age 25 and visit bar atleast one time a month are mostly likely to accept Bar Coupons. The coupon acceptance rate (in %) for this group is 69.52%. This acceptance rate increases to 72.17% for drivers who are under 30 years of age.
* Drivers who visit more than once a month and don't have a kid and not from farming, fishing, or forestry occupation are most likely to accept the coupon. The acceptance rate (in%) for this groups is 71.32% meaning nearly 3 out of 4 people will accept the coupons
* Drivers who visit more than once a month and don't have a kid and not a widower are most likely to accept the coupon. The acceptance rate (in%) for this groups is 72.17% meaning nearly 3 out of 4 people will accept the coupons

**Hypothesis:**
* Bar Visit Frequency: Bar visiting frequency is key influencer of whether the drivers will accept the coupon or not. This may be because regular visitors want to reduce what they already spend at bars by using coupons.
* Age: Drivers under 30 accepted 48.9% of bar coupons, compared with 34.6% of drivers aged 30 and over, against an overall rate of 41.0%. The effect is strongest when youth combines with bar-going habits: drivers under 30 who visit bars more than once a month accepted 72.2%. This could indicate that younger drivers are more inclined to meet friends or family at bar, and so are more likely to take advantage of discount coupons.
* Marital Status or Occupation: Nearly 3 out of 4 Drivers who visit bar more than once a month and do not have kids and are not widower or not working in farming, fishing or forestry occupation are most likely to accept coupons. This could indicate that drivers who are fathers to kids will find little time to engage in social activites or visit bars very often.

# Coupon House Coupons:
Performed analysis on Coffee House Coupon type to understand what driver characteristics demonstrate strong coupon acceptance rates.

**Key Findings:**
* Coffee house coupons were accepted by drivers about half the time (49.92%). This is slightly lower than coupon acceptance rate across all coupon types (56.84%)
* Drivers who visit Coffee House around 10 AM are most likely to accept coffee coupons. The acceptance rate (in%) for this category is 64.07%. The next best time is 2 PM where acceptance rate (in%) stood at 54.79%
* Drivers under 21 are most likely to accept coffe house coupons. The acceptance rate for this category stood at 69.68% meaning nearly 7 out of 10 people who visit coffee house and are under age 21 will accept coupons.
* Drivers who visit a Coffee House on a day with high temperature (80°F) are most likely to accept cofee house coupons. 52.98% of from this category accept the coupons. However, this is a minor factor as the value is just 3% more than coupon coupon acceptance rate.
* Drivers who are male and single as well as female and have a married partner are most likely accept the coupons than others.

**Hypothesis:**
* General: Coffee house coupons were accepted about half the time (49.92%), below the 56.84% rate across all coupon types. Based on other data points in findings, acceptance depends more on the driver's situation than on the offer itself.
* Time: Time is an important factor to drive coupon acceptance. Coffee House coupon acceptance peaked when the coupon arrived at 10AM (64.07%) and 2PM (54.79%). This will indicate that acceptance rate rises during driver's spare time rather than busy time like commuting to or fro from work or at home.
  <img width="883" height="430" alt="image" src="https://github.com/user-attachments/assets/041cdcc3-0651-487c-ba52-98e764c23a4c" />

* Age: Age appears to matter in driving coffee house coupon acceptance. Drivers under age 21 are most likely to accept coupons and also majority of the users represented in this category are "Students". The adoption might be more due to social engagement with friends during or after school/college time.
