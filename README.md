# Ex-08-Data-Visualization-
# AIM
To Perform Data Visualization on a complex dataset and save the data to a file.

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
## STEP 1
Read the given Data

## STEP 2
Clean the Data Set using Data Cleaning Process

## STEP 3
Apply Feature generation and selection techniques to all the features of the data set

## STEP 4
Apply data visualization techniques to identify the patterns of the data.

# CODE
```
NAME : SANJAY S 
REG NUMBER : 212222230132


import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
#Load the dataset
df = pd.read_csv('Superstore2.csv', encoding='unicode_escape')
#Data Cleaning: Drop unnecessary columns
df.drop(['Row ID', 'Order ID', 'Ship Date', 'Customer ID', 'Postal Code', 'Product ID'], axis=1,
inplace=True)
#Feature Generation: Extract Year and Month from Order Date
df['Year'] = pd.DatetimeIndex(df['Order Date']).year
df['Month'] = pd.DatetimeIndex(df['Order Date']).month_name()
#1. Which Segment has Highest sales?
segment_sales = df.groupby('Segment')['Sales'].sum().reset_index()
plt.figure(figsize=(8,5))
sns.barplot(x='Segment', y='Sales', data=segment_sales)
plt.title('Segment-wise Sales')
plt.show()
#2. Which City has Highest profit?
city_profit = df.groupby('City')['Profit'].sum().reset_index().sort_values(by='Profit', ascending=False)
plt.figure(figsize=(12,8))
sns.barplot(x='City', y='Profit', data=city_profit.head(10))
plt.title('Top 10 Cities by Profit')
plt.show()
#3. Which ship mode is profitable?
shipmode_profit = df.groupby('Ship Mode')['Profit'].sum().reset_index()
plt.figure(figsize=(8,5))
sns.barplot(x='Ship Mode', y='Profit', data=shipmode_profit)
plt.title('Ship Mode-wise Profit')
plt.show()
#4. Sales of the product based on region
region_sales = df.groupby('Region')['Sales'].sum().reset_index()
plt.figure(figsize=(8,5))
sns.barplot(x='Region', y='Sales', data=region_sales)
plt.title('Region-wise Sales')
plt.show()
#5. Find the relation between sales and profit
plt.figure(figsize=(8,5))
sns.scatterplot(x='Sales', y='Profit', data=df)
plt.title('Sales vs. Profit')
plt.show()
#6. Find the relation between sales and profit based on the following category.
#i) Segment
segment_sales_profit = df.groupby('Segment')['Sales', 'Profit'].mean().reset_index()
plt.figure(figsize=(8,5))
sns.barplot(x='Segment', y='Sales', data=segment_sales_profit, color='blue', alpha=0.5, label='Sales')
sns.barplot(x='Segment', y='Profit', data=segment_sales_profit, color='green', alpha=0.5, label='Profit')
plt.title('Segment-wise Sales and Profit')
plt.legend()
plt.show()
#ii) City
city_sales_profit = df.groupby('City')['Sales', 'Profit'].mean().reset_index().sort_values(by='Profit', ascending=False).head(10)
plt.figure(figsize=(12,8))
sns.barplot(x='City', y='Sales', data=city_sales_profit, color='blue', alpha=0.5, label='Sales')
sns.barplot(x='City', y='Profit', data=city_sales_profit, color='green', alpha=0.5, label='Profit')
plt.title('Top 10 Cities by Sales and Profit')
plt.legend()
plt.show()
#iii) States
plt.figure(figsize=(8,5))
sns.scatterplot(x='Sales', y='Profit', hue='State', data=df)
plt.title('Sales vs. Profit based on State')
plt.show()
#iv) Segment and Ship Mode
plt.figure(figsize=(8,5))
sns.scatterplot(x='Sales', y='Profit', hue='Segment', style='Ship Mode', data=df)
plt.title('Sales vs. Profit based on Segment and Ship Mode')
plt.show()
#v) Segment, Ship mode and Region
plt.figure(figsize=(8,5))
sns.scatterplot(x='Sales', y='Profit', hue='Segment', style='Ship Mode', size='Region', data=df)
plt.title('Sales vs. Profit based on Segment, Ship Mode and Region')
plt.show()
```
# OUTPUT

<img src=https://github.com/22002102/ODD2023-Datascience-Ex-08/assets/119091638/abf46b2e-c8c6-47b7-ab03-a235460f7678 width=450 height=450>
<br>
<img src=https://github.com/22002102/ODD2023-Datascience-Ex-08/assets/119091638/c44340f1-105c-4645-a0e1-48d6ceec3db0 width=450 height=450>
<br>
<img src=https://github.com/22002102/ODD2023-Datascience-Ex-08/assets/119091638/bfc044d5-3127-43b1-964f-02dfcb1ed075 width=450 height=450>
<br>
<img src=https://github.com/22002102/ODD2023-Datascience-Ex-08/assets/119091638/2517ffcc-615f-445a-80ac-a022e5e746f4 width=450 height=450>
<br>
<img src=https://github.com/22002102/ODD2023-Datascience-Ex-08/assets/119091638/e10e4029-65fc-469f-87fd-5baa79190f99 width=450 height=450>
<br>
<img src=https://github.com/22002102/ODD2023-Datascience-Ex-08/assets/119091638/e1e9278b-f000-42c0-bdb3-9e4375ef1d3e width=450 height=450>
<br>
<img src=https://github.com/22002102/ODD2023-Datascience-Ex-08/assets/119091638/eb2adec9-a18b-4414-9208-238ad0eb7ae9 width=450 height=450>
<br>
<img src=https://github.com/22002102/ODD2023-Datascience-Ex-08/assets/119091638/9e91af9b-0529-4113-8419-97da83200ee2 width=450 height=450>
<br>
<img src=https://github.com/22002102/ODD2023-Datascience-Ex-08/assets/119091638/cd5736b2-625e-4c0b-8aa6-ef1066c84862 width=450 height=450>
<br>
<img src=https://github.com/22002102/ODD2023-Datascience-Ex-08/assets/119091638/55350d9f-d828-46f1-a757-ee603a80810d width=450 height=450>



# RESULT:

Hence the data visualization method for the given dataset applied successfully.




