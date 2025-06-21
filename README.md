# 🏠 Analysis of U.S. Housing Market (2004–2024)

## 👋 Introduction:
As a Data Analyst for a residential REIT (Real Estate Investment Trust) company and I am asked to analyze the last 20 years of home price and economic data to support executive decision-making amid housing market uncertainty. The goal is to uncover relationships between housing prices and key economic indicators to guide strategy.

### ❓ Questions to Analyze
In order to support analysis I asked the following questions: 
1. How have home prices evolved over time and are they affected by interest and mortgage rates, inflation, and unemployment?
2. What are the correlations of HPI to these metrics?
3. Have major economic or political events like the 2008 crash and COVID-19—affected HPI and inflation?
4. How has HPI changed since 2004?
5. What actionable insights can we take from this analysis?

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
After loading my data I created a PivotTable and PivotChart with data comparing the the Case-Shiller Home Price Index with interest rates and mortgage rates. 
I also added a Timeline so users can filter based on key periods.

#### 📊 Analysis
**HPI** = how much home prices have increased since 2000. An HPI of 200 means that home prices <br/> 
increased 100%/doubled in price. <br/> <br/>
After Looking at the chart we can see a consistent trend of home prices going up. Interests Rates have fluctuated up and down as well as mortgage rates. <br/><br/>
However, during 2021 and 2023 we saw a signficant increase in interest and mortgage rates as well as home prices. <br/>

<img src="/Resources/Question%201%20Resources/7.%20Q1%20Dashboard.png" alt="7. Q1 Dashboard" width="400" height="300"/>

#### Conclusion
This can mean that HPI increases may be due to causes other than interest and mortgage rates as HPI consistenly increase regardless.<br/>
However, they may increase more when interest rates increase more dramatically . <br/>

### 2️⃣  Which economic indicators appear most strongly connected to home price changes?
### 🔧 Excel Skills Used: Functions & Conditional Formatting

I used functions to calculate the correlation between Interest Rate, Mortgage Rate, Unemployment Rate, Inflation (CPI), Consumer Sentiment Index and Home Price Index.

Consumer Sentiment Index - is the outlook of consumers on the economy and their financial situation. 100 being neutral, > 100 optimisitic, < 100 pessimistic.

Inflation (CPI) - is the Consumer Price Index or the price change for a basket of goods compared to a base year (i.e. 1982-1984). 100 is base (1984). 200 means prices doubled since 1984.

To calculate the correlations I used 
```
=CORREL(us_home_prices_dataset_2004_2024[Home_Price_Index],
us_home_prices_dataset_2004_2024[Consumer_Sentiment])
```

And similarly for the other metrics.

I used color scale conditional formatting for the background color. <br/>
Strong positive correlations used a green color, strong negative used red, neutral used white.

<img src="/Resources/Question 2 Resources/Color Scale.png" alt="Color Scale" width="450" height="150"/>

#### 📊 Analysis
I created a formatted correlations table and it showed a strong positive correlation between HPI and Inflation (CPI). <br/>
There is also a weak negative correlation between HPI and unemployment.

<img src="/Resources/Question 2 Resources/Correlations Formatted.png" alt="Correlations Formatted" width="450" height="250"/>

#### Conclusion
It seems that inflation may be a strong reason housing prices are increasing. <br/>
We may also assume that Housing Prices may increase when there are more people working. <br/>
This may be due to there being more money in the market to buy a home <br/>
