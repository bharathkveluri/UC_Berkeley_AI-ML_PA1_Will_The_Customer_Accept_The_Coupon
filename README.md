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

# General Data Findings
* The percentage of drivers who accepted the coupon across all coupon types was 56.84%.
  <img width="379" height="399" alt="image" src="https://github.com/user-attachments/assets/1ae039b9-5048-45f8-b177-031bf3d6db7e" />
* Coffee House coupons were the most accepted coupons by the drivers.
  <img width="570" height="521" alt="image" src="https://github.com/user-attachments/assets/51688a51-587d-48cc-84b3-8a4af8da7c81" />
* The coupons acceptance rate was 51.47% on a day with temperature at 80°F. This is a strong indicator that coupons distribution on a day with higher temperature will yield more business.
  <img width="877" height="426" alt="image" src="https://github.com/user-attachments/assets/e1fffc20-d659-486f-8a66-a13420816902" />
 
