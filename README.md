# Ex-08 Data Visualization 1
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
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
plt.title("Segment vs Sales ->LinePlot")
sns.lineplot(x="Segment",y="Sales",data=df,marker='o')
plt.title("Segment vs Sales ->BarPlot")
sns.barplot(x="Segment",y="Sales",data=df)
plt.show()
df1 = df[(df.Profit >= 300)]
st=df1.loc[:,["City","Profit"]]
st=st.groupby(by=["City"]).sum()
          .sort_values(by="Profit")
sns.barplot(x=st.index,y="Profit",data=st)
plt.xticks(rotation = 90)
plt.xlabel=("City")
plt.ylabel=("Profit")
plt.show()
sns.barplot(x="Ship Mode",y="Profit",data=df)
plt.title("ShipMode vs Profit Barplot")
sns.lineplot(x="Ship Mode",y="Profit",data=df)
plt.title("ShipMode vs Profit Lineplot")
plt.show()
st=df.loc[:,["Region","Sales"]]
st=st.groupby(by=["Region"]).sum().sort_values(by="Sales")
sns.barplot(x=st.index,y="Sales",data=st)
plt.xticks(rotation = 90)
plt.xlabel=("Region")
plt.ylabel=("Sales")
plt.title("Region vs Sales BarPlot")
plt.show()
df.groupby(['Region']).sum().plot(kind='pie',y='Sales',
      figsize=(3,6),pctdistance=.5,labeldistance=1.2)
df["Sales"].corr(df["Profit"])
df_corr = df.copy()
df_corr = df_corr[["Sales","Profit"]]
df_corr.corr()
sns.pairplot(df_corr, kind="scatter")
plt.show()
gd=df.groupby('Segment')[['Sales', 'Profit']].mean()
ax.bar(gd.index,gd['Sales'],label='Sales')
ax.bar(gd.index,gd['Profit'],bottom=gd['Sales'],label='Profit')
ax.set_xlabel('Segment')
ax.set_ylabel('Value')
plt.title("Based on Segments")
ax.legend()
plt.show()
gd=df.groupby('City')[['Sales','Profit']].mean()
ax.bar(gd.index,gd['Sales'],label='Sales')
ax.bar(gd.index,gd['Profit'],bottom=gd['Sales'],label='Profit')
ax.set_xlabel('City')
ax.set_ylabel('Value')
plt.title("Based on City")
ax.legend()
plt.show()
gd = df.groupby('State')[['Sales', 'Profit']].mean()
fig,ax=plt.subplots(figsize=(3,3))
ax.bar(gd.index,gd['Sales'],label='Sales')
ax.bar(gd.index,gd['Profit'],bottom=gd['Sales'],label='Profit')
ax.set_xlabel('State')
ax.set_ylabel('Value')
plt.title("Based on States")
ax.legend()
plt.show()
gd=df.groupby(['Segment','Ship Mode'])[['Sales','Profit']].mean()
pp=gd.reset_index().pivot(index='Segment',
  columns='Ship Mode',values=['Sales','Profit'])
fig,ax=plt.subplots(figsize=(5,5))
pd.plot(kind='bar',ax=ax)
ax.set_xlabel('Segment')
ax.set_ylabel('Value')
plt.title("Segment And Ship")
plt.legend()
plt.show()
gd=df.groupby(['Segment','Ship Mode','Region'])
    [['Sales','Profit']].mean()
pd=gd.reset_index().pivot(index=['Segment','Ship Mode'
        ],columns='Region',values= ['Sales','Profit'])
sns.set_style("whitegrid")
sns.set_palette("Set1")
pd.plot(kind='bar',stacked=True,figsize=(10,5))
plt.xlabel('Ship Mode')
plt.ylabel('Value')
plt.legend(title='Region')
plt.show()

```
# OUTPUT


![image](https://github.com/22002102/ODD2023-Datascience-Ex-08/assets/119091638/7554b528-0622-4881-a52a-7e65149d9960)
<br>

![image](https://github.com/22002102/ODD2023-Datascience-Ex-08/assets/119091638/6fe6b67c-550e-4572-937d-ca3cae8748d5)
<br>
![image](https://github.com/22002102/ODD2023-Datascience-Ex-08/assets/119091638/e804cfa8-f8e0-49d5-bce6-c093d3cda350)
<br>
### 1. Segment with Highest Sales:
![image](https://github.com/22002102/ODD2023-Datascience-Ex-08/assets/119091638/ad82c56f-becf-41a1-862d-47eac077abd6)
<br>

### 2. City with Highest Profit:
![image](https://github.com/22002102/ODD2023-Datascience-Ex-08/assets/119091638/cd4b480d-094d-4215-adc9-7d95d70f4ef6)
<br>

### 3. Profitable Ship Mode:
![image](https://github.com/22002102/ODD2023-Datascience-Ex-08/assets/119091638/0948e68c-8575-4f6e-bda3-16b03102b266)
<br>

### 4. Sales of the Product Based on the Region:
![image](https://github.com/22002102/ODD2023-Datascience-Ex-08/assets/119091638/4f6d9378-2c56-49f3-a4e6-3283e41d492f)
<br>

### 5. Relation Between Sales and Profit:
![image](https://github.com/22002102/ODD2023-Datascience-Ex-08/assets/119091638/dae57975-d53a-4dfc-b57d-f912aa4cf251)
<br>

### 6. Relation Between Sales and Profit Based on:
### Segment:
![image](https://github.com/22002102/ODD2023-Datascience-Ex-08/assets/119091638/233c5247-00f1-4490-aa0f-e1c43d0869fc)
<br>
### City:
![image](https://github.com/22002102/ODD2023-Datascience-Ex-08/assets/119091638/c8570fa9-8f05-482c-8bac-d165ab60f825)
<br>
### States:
![image](https://github.com/22002102/ODD2023-Datascience-Ex-08/assets/119091638/bcc8d489-9629-4408-bf8d-2b5f61bd957b)
<br>
### Segment and Ship Mode:
![image](https://github.com/22002102/ODD2023-Datascience-Ex-08/assets/119091638/c68f5d41-7970-4527-8814-c41c67dda130)
<br>
### Segment,Ship mode and Region
![image](https://github.com/22002102/ODD2023-Datascience-Ex-08/assets/119091638/12d3720b-d4fd-402d-aaf2-aa1163d33795)
<br>


# RESULT:

Hence the data visualization method for the given dataset applied successfully.




