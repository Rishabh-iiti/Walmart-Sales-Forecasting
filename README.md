# 📊 Walmart Sales Forecasting 

## 📝 Project Overview  
Walmart, one of the largest retail chains in the world, faces challenges in **inventory management** due to unpredictable demand, unemployment rates, seasonal fluctuations, and pricing pressures.  

The goal of this project is to analyze Walmart’s **weekly sales data** to uncover key insights and build forecasting models. The analysis helps in:  
- Understanding how external factors impact sales  
- Identifying top and underperforming stores  
- Forecasting sales for the next **12 weeks**  

---

## ❓ Problem Statements  
This project addresses the following business questions:  

1. Are weekly sales impacted by **unemployment**? Which stores are most sensitive?  
2. Do sales show a **seasonal trend**? When do they peak and why?  
3. How does **temperature** affect sales?  
4. What is the relationship between **CPI (Consumer Price Index)** and weekly sales?  
5. Which are the **top-performing stores** historically?  
6. Which is the **lowest-performing store**, and how wide is the gap?  
7. Can we **forecast sales for each store** for the next 12 weeks?  

---

## 📂 Dataset Information  
- **Entries:** 6,435 weekly records  
- **Stores:** Multiple outlets across the U.S.  
- **Features:**  
  - Store ID  
  - Date (weekly timeline)  
  - Weekly Sales  
  - Holiday Flag (holiday week vs. non-holiday week)  
  - Temperature  
  - Fuel Price  
  - CPI (Consumer Price Index)  
  - Unemployment Rate  

---

## 🔧 Methodology  
1. **Data Preprocessing** – Converted dates, checked for missing values (none found).  
2. **Outlier Handling** – Detected with boxplots and capped using the IQR method.  
3. **Exploratory Data Analysis (EDA)** – Analyzed trends, seasonality, and correlations.  
4. **Feature Engineering** – Added rolling averages, lag features, and holiday season markers.  
5. **Predictive Modeling** – Built ARIMA, SARIMAX, and Holt-Winters models.  
6. **Model Evaluation** – Used RMSE and MAE for accuracy measurement.  

---

## 📈 Key Insights  
- 📉 **Unemployment Effect**: Store 44 showed the strongest negative correlation (-0.78), meaning its sales drop sharply when unemployment rises.  
- 🎄 **Seasonality**: Sales consistently spike in **November–December** (holiday shopping season) and dip during mid-year months.  
- 🌡️ **Temperature Impact**: Minimal overall effect, but extreme heat or cold influences certain stores’ sales.  
- 💰 **CPI Influence**: Rising CPI slightly reduces weekly sales, indicating price sensitivity among customers.  
- 🏆 **Top Performer**: Store 20 with ~299M total sales.  
- 🚨 **Lowest Performer**: Store 33 with ~37M total sales (262M gap from the best store).  

---

## 📊 Visualizations and Their Insights  

### 🔹 Correlation Heatmap  
A heatmap was created to show how numerical features (Weekly Sales, CPI, Temperature, Fuel Price, and Unemployment) relate to each other.  
👉 Key takeaway: **Unemployment and CPI** showed noticeable correlation with sales, while fuel price had little effect.  

---

### 🔹 Seasonal Trend (Monthly Sales)  
A line plot was used to compare monthly sales trends across years.  
👉 Insight: Sales **peak in November and December** due to Thanksgiving and Christmas, showing strong seasonal behavior.  

---

### 🔹 Holiday vs Non-Holiday Sales  
A boxplot was plotted to compare sales during holiday weeks versus normal weeks.  
👉 Observation: **Holiday weeks clearly have higher median sales**, proving that holidays drive significant revenue.  

---

### 🔹 Forecasting Example (Store 1)  
Forecasting was performed using Exponential Smoothing for the last 12 weeks of Store 1.  
👉 Results: Forecast captured both **trend and seasonal spikes** accurately.  
- RMSE ≈ 32,071  
- MAE ≈ 25,520  

This methodology was repeated for each store to generate **12-week forecasts**.  

---

## 🔮 Forecasting  
- Models: **Exponential Smoothing (Holt-Winters)** and **SARIMAX**  
- Forecast horizon: **12 weeks** per store  
- Evaluation Metrics:  
  - **RMSE** – Root Mean Squared Error  
  - **MAE** – Mean Absolute Error  

Forecast plots showed good alignment with actual sales, especially during seasonal peaks.  

---

## 🛠️ Tech Stack  
- **Language:** Python 🐍  
- **Libraries:** Pandas, NumPy, Matplotlib, Seaborn, Statsmodels, Scikit-learn  
- **Models Used:** ARIMA, SARIMAX, Holt-Winters  

---

## 📌 Recommendations  
- 📦 Stock more inventory in **holiday months (Nov–Dec)**.  
- 👷 Focus on regions where sales are **highly sensitive to unemployment**.  
- 💰 Adjust pricing strategies when CPI rises to remain competitive.  
- 🏬 Audit and improve **lowest-performing stores** (e.g., Store 33).  
- 🔮 Integrate **12-week forecasts** into supply chain and staffing plans.  

---

## 🚀 Future Enhancements  
- Implement **machine learning models** (XGBoost, LSTM, Prophet).  
- Add **external data sources** like promotions, competitor pricing, demographics.  
- Build an **interactive dashboard** using Tableau or Power BI.  

---

## Conclusion  

This project helped me understand how different factors affect Walmart’s sales and how forecasting can support better planning.  
Some of the clear patterns I found were:  

- Sales increase sharply during the holiday season (especially November and December).  
- Stores in areas with higher unemployment are more affected, with Store 44 showing the strongest negative impact.  
- Inflation (CPI) has some effect on sales, while temperature didn’t show much overall influence.  
- The difference between the best performing store (Store 20) and the weakest (Store 33) was very large, which highlights how uneven performance can be across locations.  

On the forecasting side, methods like Holt-Winters and SARIMAX gave good results and were able to capture trends and seasonal changes quite well. These forecasts can be applied for the next 12 weeks to help with inventory and staffing decisions.  

Overall, the project showed me how data analysis can give practical insights and how predictive models can be useful for making business decisions in retail.  
