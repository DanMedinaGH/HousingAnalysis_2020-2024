# 🏠 Analysis of U.S. Housing Market (2004–2024)

## 👋 Introduction:
As a Data Analyst for a residential REIT (Real Estate Investment Trust) company and I am asked to analyze the last 20 years of home price and economic data to support executive decision-making amid housing market uncertainty. The goal is to uncover relationships between housing prices and key economic indicators to guide strategy.

### ❓ Questions to Analyze
In order to support analysis I asked the following questions: 
1. How have home prices evolved over time, and how are they affected by mortgage and interest rates?
2. Which economic indicators appear most strongly connected to home price changes?
3. Do changes in housing construction (permits and starts) impact price trends?
4. Have major economic disruptions—like the 2008 crash and COVID-19—affected housing prices and related indicators?
5. What actionable insights can we take from this analysis?

## 💾 Data Used:

The dataset uses real-world data from the S&P Case-Shiller U.S. National Home Price Index (CSUSHPISA) and 
the Federal Reserve Economic Database (FRED) from 2020-2024. 
The data was sourced from Kaggle: https://www.kaggle.com/datasets/pahuljotsingh/us-home-price-and-economic-indicators-20042024/data

## 🔧 Excel Skills Used:


## 📊 Analysis

### 1️⃣ How have home prices evolved over time, and how are they affected by mortgage and interest rates?


### 🔧 Excel Skills Used: Power Query (ETL), PivotTable & PivotChart & Timeline Visualizations

#### 🧲 Power Query (ETL)

##### 🧲 Extract
I first extracted the original kaggle dataset using Power Query.
![1.Extract_Original_Data.png](/Resources/Question%201%20Resources/1.%20Extract%20Original%20Data.png)

##### 🔄 Transform
Then I performed column profiling to detect irregularities. 
![2. Column Profiling](/Resources/Question%201%20Resources/2.%20Column%20Profiling.png)

After I performed transformations, this included:
- Removed unnecessary columns
- Changed the name of Median_Income to Median_Individual Income
- Changed numbers to percentages and divided by 100.
- Multiplied US population by 1000 (truncated in original CSV).

![3. Transormations](/Resources/Question%201%20Resources/3.%20Transormations.png)

##### 📥 Load
Then I loaded the data into Excel.
![4. Load Data](/Resources/Question%201%20Resources/4.%20Load%20Data.png)

#### 🧲 PivotTable, PivotChart, & Timeline Visualizations

##### 📈 PivotTable and Pivot Chart
After loading my data I created a PivotTable and PivotChart with data comparing the the Case-Shiller Home Price Index with interest rates and mortgage rates. 
I also added a Timeline so users can filter based on key periods.

#### 📊 Analysis
