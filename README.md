# 🏠 Analysis of U.S. Housing Market (2004–2024)

## 👋 Introduction:
As a Data Analyst for a residential REIT (Real Estate Investment Trust) company and I am asked to analyze the last 20 years of home price and economic data to support executive decision-making amid housing market uncertainty. The goal is to uncover relationships between housing prices and key economic indicators to guide strategy.

### ❓ Questions to Analyze
In order to support analysis I asked the following questions: 
1. How have home prices evolved over time and are they affected by interest and mortgage rates, inflation, and unemployment?
2. What are the correlations of HPI to these metrics?
3. Was HPI impacted by major economic or societal events and was correlation with inflation still present?
4. What are the minimum and maximum HPI?

## 💾 Data Used:

The dataset uses real-world data from the S&P Case-Shiller U.S. National Home Price Index (CSUSHPISA) and 
the Federal Reserve Economic Database (FRED) from 2020-2024. 
The data was sourced from Kaggle: https://www.kaggle.com/datasets/pahuljotsingh/us-home-price-and-economic-indicators-20042024/data

## 🔧 Excel Skills Used:


## 📊 Analysis

### 1️⃣ How have home prices evolved over time and are they affected by interest and mortgage rates, inflation, and unemployment?


### 🔧 Excel Skills Used: Power Query (ETL), PivotTable & PivotChart & Timeline Visualization

#### 🧲 Power Query (ETL)

##### 🧲 Extract
I first extracted the original kaggle dataset using Power Query.

##### 🔄 Transform
Then I performed column profiling to detect irregularities. <br/>
<img src="/Resources/Question%201%20Resources/2.%20Column%20Profiling.png" alt="2. Column Profiling" width="300"/>

After I performed transformations, this included:
- Removed unnecessary columns
- Changed the name of Median_Income to Median_Individual Income
- Changed numbers to percentages and divided by 100.
- Multiplied US population by 1000 (truncated in original CSV).

<img src="/Resources/Question%201%20Resources/3.%20Transormations.png" alt="3. Transformations" width="200" />

##### 📥 Load
Then I loaded the data into Excel.

#### 🧲 PivotTable, PivotChart, & Timeline Visualizations & Conditional Formatting

##### 📈 PivotTable and Pivot Chart & Conditional Formatting
After loading my data I created a PivotTable and PivotChart with data comparing the the Case-Shiller Home Price Index with interest rates and mortgage rates as well as inflation (CPI) and unemployment rate. 
I also added a Timeline so users can filter based on key periods.

#### 📊 Analysis
**HPI** = how much home prices have increased since 2000. An HPI of 200 means that home prices <br/> 
increased 100%/doubled in price. <br/> <br/>
After Looking at the chart we can see a consistent trend of home prices going up. However, interest rates have fluctuated up and down as well as mortgage rates. <br/><br/>
During 2021 and 2023 we saw a signficant increase in HPI and interest and mortgage rates. <br/>

<img src="/Resources/Question%201%20Resources/7.%20Q1%20Dashboard.png" alt="7. Q1 Dashboard" width="400" height="300"/>

Inflation (CPI) - is the Consumer Price Index or the price change for a basket of goods compared to a base year (i.e. 1982-1984). 100 is base (1984). 200 means prices doubled since 1984.

HPI and inflation have both consistently increased.

HPI appears to increase when unemployment decreases. However, during the 2020-2021 period, unemployment and HPI both increased significantly.

#### Conclusion
This means interest and mortgage rates are not good indicators of increasing HPI. However, when there is a dramatic spike in interest rates like during 2020-2021, this may indicate HPI may increase.

Since, HPI and inflation increases consistently, this can mean home prices may not be increasing in innate value, but it is more related to the purchasing power of the dollar.

Lastly, since HPI and unemployment have inverse decreasing/increasing behavior, this may mean that when there are more people working, then home prices increase due to more demand. Also, when there are less people working, HPI decreases because there is less demand.

However, during 2020-2021 (COVID) both HPI and unemployment increased. This can mean that there was still a large demand for housing by a portion of the population. This may mean COVID affected people disproportionately.   

### 2️⃣  What are the correlations of HPI to these metrics?
### 🔧 Excel Skills Used: Functions & Conditional Formatting

I used functions to calculate the correlation between Interest Rate, Mortgage Rate, Unemployment Rate, and Inflation (CPI) to Home Price Index. I used these to create a correlations table.

To calculate the correlations I used 
```
=CORREL(us_home_prices_dataset_2004_2024[Home_Price_Index],
us_home_prices_dataset_2004_2024[Consumer_Sentiment])
```

And similarly for the other metrics.

I used color scale conditional formatting for the background color. <br/>
Stronger correlations used a blue color and weaker used white.

<img src="/Resources/Question 2 Resources/Color Scale.png" alt="Color Scale" width="450" height="150"/>

#### 📊 Analysis
The correlations table showed a strong positive correlation between HPI and Inflation (CPI). <br/>
There is also a weak negative correlation between HPI and unemployment.

<img src="/Resources/Question 2 Resources/Correlations Formatted.png" alt="Correlations Formatted" width="450" height="250"/>

#### Conclusion
This supports the assumption that inflation may be a strong reason HPI increases. <br/>
This also supports the assumption that HPI increases when unemployment is down. <br/>
This can be due to there being more money in the market to buy a home and the value of the dollar going down.<br/>

### 3️⃣ Was HPI impacted by major economic or societal events?
### 🔧 Excel Skills Used: Clustered column timeline, Excel Functions

I used the below array to create the clustered column timeline:

To create the data label value I used the below function for each event:
```
=A3&CHAR(10)&CONCAT("AVG HPI: ", TEXT(D3, "0"))
&CHAR(10)&CONCAT("AVG Inflation: ",
TEXT(E3, "0"))&CHAR(10)&TEXT(B3, "yyy")
```

CHAR(10) is the newline character in Excel.

<img src="/Resources/Question 2 Resources/Color Scale.png" alt="Color Scale" width="450" height="150"/>

#### 📊 Analysis
After the Great Recession (2008) HPI hit a low in 2012 and then started rising again shortly after. After the COVID pandemic (2020) HPI hit a high in 2024.

<img src="/Resources/Question 2 Resources/Correlations Formatted.png" alt="Correlations Formatted" width="450" height="250"/>

#### Conclusion
We can conclude that major economic or societal events can affect HPI and their affects last for years. 
Since the great recession hit a low after 4 years, we can expect the 2020 post pandemic HPI rise to hit a peak soon.


### 4️⃣ What are the minimum and maximum HPI?
### 🔧 Excel Skills Used: Excel Functions

I used below functions to calculate MIN and MAX HPI:
```
= MIN(us_home_prices_dataset_2004_2024[Home_Price_Index])
```

```
= MAX(us_home_prices_dataset_2004_2024[Home_Price_Index])
```

<img src="/Resources/Question 2 Resources/Color Scale.png" alt="Color Scale" width="450" height="150"/>

#### 📊 Analysis
The minimum and maximum HPI occurred a few years after the Great Recession and the COVID-19 pandemic.
However, 5 years after the Great Recession HPI began to increase.

<img src="/Resources/Question 2 Resources/Correlations Formatted.png" alt="Correlations Formatted" width="450" height="250"/>

#### Conclusion
If the current trend follows the inverse of what happened after the Great Recession we can expect HPI to decrease soon.
This would mean it is currently not a good idea to invest in residential real estate, but may be soon.

## Final Conclusion
From my findings I found HPI is mostly affected by inflation and that major event may cause it to increase and decrease. Additionally, high unemployment can cause it to decrease as well. 

Based off these findings I would advice my boss that it may be good idea to start planning on buying exisiting residential real estate in the near future. However building new real estate may not be a good idea. However, more historical data would be needed to support this since this is the only consistent period of HPI increase since 2004.
