# kreativebi
# Python with Power BI: Analyzing Financial Data
#This project Imports Financial data from Yahoo Finance directly in Power BI using Python
#Then Visualizes financial data using line charts, area charts, scatter plots, box plots, violin plots and histogram in Python within Power BI

#Importing Real time Financial Data into Power BI using Python Library


import pandas as pd
import yfinance as yf
ticker= "AAPL"


data= yf.download(ticker, start="2019-01-01", end= "2022-12-31")
data.reset_index(inplace=True)
data




![image](https://github.com/kirankampli/kreativebi/assets/143105817/7668ab78-6516-4b9e-8a86-b1efe5587506)

#Analyzing Historical trends using Line and Area charts

#dataset= pandas.DataFrame(Close.Date)
#dataset= dataset.drop_duplicates()

import matplotlib.pyplot as plt
plt.fill_between(dataset['Date'],dataset['Close'], color='skyblue')
plt.plot(dataset['Date'],dataset['Close'], color= 'blue')
plt.show()


![image](https://github.com/kirankampli/kreativebi/assets/143105817/01b77f2f-8215-404f-8a56-9a20df790f23)

![image](https://github.com/kirankampli/kreativebi/assets/143105817/708379f4-428c-49f3-8cbc-89219a5a8cd0)

#Visualizing Price using Box and Violin charts

import seaborn as sns
sns.boxplot(data=dataset, y= 'Close')
sns.violinplot(data=dataset, y= 'Close')
plt.show()

![image](https://github.com/kirankampli/kreativebi/assets/143105817/dd79985d-4d53-4d34-847f-8fde2ef8a856)

![image](https://github.com/kirankampli/kreativebi/assets/143105817/378945d5-f8f6-4555-9282-e04998b87a45)

#Visualizing Volume using Histogram and Violin charts
sns.violinplot(data=dataset, x= 'Year', y= 'Volume')
sns.violinplot(data=dataset, x= 'Year', y= 'Volume', hue= 'Quarter')
sns.histplot(data=dataset, x= 'Volume', hue= 'Year', kde=True)
plt.show()



![image](https://github.com/kirankampli/kreativebi/assets/143105817/0942656f-9354-40c0-9f17-ed84388ac56a)

![image](https://github.com/kirankampli/kreativebi/assets/143105817/e71b75d4-54c2-4a7d-96c3-7c7c99915768)

![image](https://github.com/kirankampli/kreativebi/assets/143105817/a94b1a25-a30d-41ce-bef7-965afad67c48)

![image](https://github.com/kirankampli/kreativebi/assets/143105817/1f088ef4-8cb6-4f96-8fc8-3610ac9e3f3e)

#Visualizing Yearly, Quarterly, Monthly, Daily Variations using Scatter Plots

volume=dataset['Volume']
close=dataset['Close']
date=dataset['Day']

dataset['up_down']= ['Up' if price> 0 else 'Down' for price in
(close-close.shift(1))]
sns.scatterplot(data=dataset, x=date, y=volume, sizes=(20,200), alpha=0.7,
hue='up_down', palette= {'Up':'green', Down: 'red'})



![image](https://github.com/kirankampli/kreativebi/assets/143105817/6a3864a9-7a4b-483f-ba30-16495943948c)


![image](https://github.com/kirankampli/kreativebi/assets/143105817/cb6b88bd-82e6-4ce1-9031-9be650712030)












