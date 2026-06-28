# Identifying Revenue Inconsistency, Poor Performance and Lack of Visibility  for Improved Productivity, 2026
## Title: Revenue and Performance Analysis

## Project Overview:
This data analysis provide a transparent view from product review, production to region and channel performances; revealing the extent of revenue generation. This will aid stakeholders in understanding inconsistencies across all indicators and making informed decisions.

## Data Source:
The dataset deployed for the purpose of this analysis was provided via a secondary data source on Kaggle.com. It contained 5 sheets, 34 columns.[Dataset](Regional_Sales_Dataset.xlsx)

## Tools:
- ### Microsoft Excel & Power Query Editor: Data cleaning and formatting)
 1. Excerpt of Uncleaned Dataset:<img width="1348" height="806" alt="Uncleaned png" src="https://github.com/user-attachments/assets/e0f5ffda-bc27-42c8-b1dd-70bac5cd9499" />

 2. Excerpt of Cleaned Dataset:<img width="1350" height="811" alt="Cleaned png" src="https://github.com/user-attachments/assets/18fc2264-6539-4e95-a7d0-9fd4a7d96fa6" />

- ### Python Colab Notebook: Data analysis
- ### Power BI: Data visualization and reporting

## Data Processing & Analysis:
I deployed Python Colab Notebook, pandas, numpy and matplotlib libraries to track KPI metrics amongst essential data fields, such as product type, channel, unit price and region.
I identified key revenue drivers, demographics and SKU performance, to gain a clear understanding and uncover various flaws and inadequacies therein.


## Dashboard Overview:
<img width="1127" height="708" alt="Dashboard" src="https://github.com/user-attachments/assets/8b54860e-45ef-4031-9234-a029665e9693" />

## Key Insights:

### Data Quality
1. Outliers: No outliers detected.
2. Stationarity: Used a python code to test whether the data is stationary. A p-value of 0.72 indicates that the data is not stationary, in other words, seasonality & trend patterns are present
3. Correlation: A correlation test revealed a strong relationship between the unit price and revenue


### Revenue
1.Year 2018 experienced an astronomical down surge in revenue. This flags a significant change, and could be highly detrimental.
2. Total revenue generated was $1.24bn from 2014 to 2018, with 2018 having the lowest return.
3. Constant Revenue targets between $290k-$299k from 2014 to 2017, with an average of $295.7k.
Peak season at the beginning of the year, in January with an above average performance 0f 20%; and February with 11%. Lowest season at the middle year, in April, June, July, with a below average performance of 6-8%. 


### Product Performance
1. Products 26, 25, 13, 14, 5, are the best performing products, with products 26 and 25 having a combined 18.55% in percentage revenue.
2. Over 63% of monitored products are significantly underperforming, with an average revenue turnover of 1-3%. This also shows that the yearly revenue is heavily reliant on sales of the best performing product.

### Channel Performance
1. Amongst the 3 channels, Wholesale has the greatest contribution of 54%, and Export the weakest has just 15%, revealing a heavy reliance on Wholesale channel, across all regions and products. 

### Region Performance
1. Average revenue contribution of  27.7% across West, South and Midwest regions, with the greatest contributor being the west region. The weakest region is the Northeast region, which only generates only about half as much as the West region generates.


### Problem Statement
Revenue Inconsistency, poor performance and lack of visibility into seasonal wings.
1. Revenue is largely inconsistent across regions and products.
2. Certain products and channel are performing poorly
3. Seasonality is visibly suppressed in some regions with no clear growth and pattern.


### RECOMMENDATIONS
1. Implement CRM strategies to understand customer's dissatisfaction about certain underperforming products.
2. Improve quality of underperforming products based on the CRM implemented.
2. Enhance marketing of underperforming products in high performing regions, to improve low profit returns.
5. Allocate more resources to the underperforming products. More resources/cost would result in a drastic improvement in revenue for these products, hence better performance.
4. Channel equal resources into the Export channel. Reduce overwhelming reliance on wholesale by at least 10%.
5. Target the peak season period to make sales. Invest heavily in production for peak season periods.
6. Introduce seasonality heatmap to understand patterns and peak seasons and plan inventory for different regions.

   
### PREDICTIVE ANALYSIS
1. Data shows expected revenue to be $295k in 2019, shrugging off any sign of continuation of the economic down surge in 2018, and also meeting the company's target average in yearly revenue 


## Python Code for EDAs
With exploratory data analysis, solved business question with python codes. See [codes](Revenue_&_Performance_Analysis.ipynb)

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import google.colab

sheets=pd.read_excel('/content/Regional_Sales_Dataset.xlsx', sheet_name=None)

# Name sheets

df_sales=sheets['Sales Orders']
df_customers=sheets['Customers']
df_products=sheets['Products']
df_regions=sheets['Regions']
df_state_reg=sheets['State Regions']
df_budgets=sheets['2017 Budgets']
