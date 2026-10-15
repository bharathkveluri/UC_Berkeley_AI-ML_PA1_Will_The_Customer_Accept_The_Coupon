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

Key Findings:
* Only 6 of 26 columns have gaps
* car is missing data for 12,576 of 12,684 rows (99.15%). So, if the column is dropped, there won't be any impact and it will improve the data quality
* The remaining 5 columns (CoffeeHouse, Restaurant20To50, CarryAway, RestaurantLessThan20 and Bar) are missing data between 0.84 % and 1.71%. This is a small percentage gap and the valules can be substituted without compromising the data quality.
* The second column is named as "Passanger" instead of "Passenger".
