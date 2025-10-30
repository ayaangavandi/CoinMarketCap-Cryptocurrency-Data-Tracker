# 💰 CoinMarketCap Cryptocurrency Data Tracker using Python & API  

## 🧠 Project Overview  
This project focuses on **extracting, processing, and analyzing real time cryptocurrency data** from the **CoinMarketCap API** using Python.  
The goal was to automate crypto data collection, monitor live market trends, and generate insights on top performing cryptocurrencies through API driven analytics.  

---

## 🎯 Objectives  
- Connect to the **CoinMarketCap API** to fetch real-time market data.  
- Extract key metrics such as **price, volume, percentage change, and market capitalization**.  
- Clean and structure the API data for analysis and visualization.  
- Identify **top performing coins** and **market trends** over time.  
- Build an automated pipeline that refreshes data on every API call.  

---

## ⚙️ Tools & Technologies  
- **Python** → Data extraction, cleaning, and visualization  
- **CoinMarketCap API** → Real-time cryptocurrency data  
- **Libraries Used:** `requests`, `pandas`, `json`, `matplotlib`, `time`, `seaborn`  

---

## 🧩 Process & Approach  

### 1️⃣ API Integration  
- Used the **`requests`** library to connect to CoinMarketCap’s REST API.  
- Retrieved JSON data on **top 100 cryptocurrencies** including prices, market caps, and percentage changes.  

### 2️⃣ Data Cleaning & Structuring  
- Parsed and normalized the JSON response using **`pandas.json_normalize()`**.  
- Removed unnecessary fields and renamed columns for better readability.  
- Handled nulls and data type conversions for numeric operations.  

### 3️⃣ Data Analysis  
- Analyzed **top gainers and losers** by 24 hour percentage change.  
- Compared **market capitalization distributions** across coins.  
- Monitored **price volatility** and correlation between trading volume and performance.  

### 4️⃣ Visualization  
- Used **Matplotlib** and **Seaborn** to visualize:  
  - 📈 Top 10 cryptocurrencies by market capitalization  
  - 💹 Percentage change over 24 hours  
  - 📊 Relationship between price and volume  
  - 🪙 Historical trends (if time-series data was fetched)  

---

## 📈 Key Insights

  🥇 Bitcoin and Ethereum dominated market capitalization and daily trading volume.

  📉 Several mid-cap coins exhibited high volatility with significant daily swings.

  📊 The correlation between volume and price movement was positive for top performing coins.

  🔄 API-based automation ensured real time and accurate data updates.

---

## 🧠 Skills Demonstrated

🔹 API Integration & Automation

🔹 JSON Parsing & Data Normalization

🔹 Exploratory Data Analysis (EDA)

🔹 Data Visualization with Matplotlib & Seaborn

🔹 Data Pipeline Development in Python

---

## 🚀 Conclusion

This project showcases how Python and APIs can be combined to automate real time data analysis.
By leveraging the CoinMarketCap API, I built a reusable data pipeline to track and visualize cryptocurrency performance dynamically, a valuable asset for financial analytics and market research.

---


## 🧰 Tools Used
| Tool                                     | Purpose                                     |
| ---------------------------------------- | ------------------------------------------- |
| 🐍 Python                                | Data Extraction, Processing & Visualization |
| 🔗 CoinMarketCap API                     | Real time Cryptocurrency Data               |
| 📚 Pandas, Requests, Matplotlib, Seaborn | Data Cleaning & Analysis                    |



---

## 📫 Connect With Me  
🔗 [LinkedIn](https://www.linkedin.com/in/ayaan-gavandi-a16202218/)  
📧 [Email](mailto:ayaangavandi33@gmail.com)

---

## 📊 Example Code Snippets  

```python
# Import required libraries
import requests
import pandas as pd

# Fetch data from CoinMarketCap API
url = 'https://pro-api.coinmarketcap.com/v1/cryptocurrency/listings/latest'
headers = {'X-CMC_PRO_API_KEY': 'YOUR_API_KEY'}
response = requests.get(url, headers=headers)
data = response.json()

# Normalize and clean data
df = pd.json_normalize(data['data'])
df = df[['name', 'symbol', 'quote.USD.price', 'quote.USD.percent_change_24h', 'quote.USD.market_cap']]
df.columns = ['Name', 'Symbol', 'Price (USD)', '% Change (24h)', 'Market Cap']

# Display top 10 coins
print(df.head(10))
