# Food Price Recommendation Strategy

## Background
Agricultural markets are inherently volatile — prices of food commodities fluctuate due to factors such as seasonality, transportation costs, supply chain inefficiencies, and regional demand differences.
For FarmGrow Naija LTD, an agritech startup, understanding these variations is crucial for:
- Setting competitive yet profitable prices for their products.
- Anticipating market changes and managing risk.
- Supporting farmers and vendors with fair and transparent pricing recommendations.
Currently, FarmGrow Naija LTD lacks a structured approach to analyzing historical and regional food price data. This project addresses that gap by developing a data-driven framework to monitor and interpret price movements and suggest pricing strategies to the stakeholders.

## 📁 Table of Contents
- [Background](#background)
- [Aim](#aim)
- [Objectives](#objectives)
- [About the Dataset](#about-the-dataset)
- [Project Workflow](#project-workflow)
- [Tools and Technologies](#tools-and-technologies)
- [Dashboard](#dashboard)
- [Insights from Analysis](#insights-from-analysis)
- [Pricing Recommendations](#pricing-recommendations)
- [Conclusion](#conclusion)

## Aim
To understand food price trends and derive actionable insights that can inform pricing strategies.

## Objectives
- Data Exploration & Cleaning – Assess data quality, handle missing values, and ensure consistency.
- Trend Analysis – Examine historical price movements across products, regions, and time periods.
- Seasonality & Volatility – Identify cyclical patterns and price fluctuations.
- Price Correlations – Analyze relationships between different food items and market factors.
- Predictive Insights – (Optional) Build forecasting models to estimate future price trends.
- Business Recommendations – Translate findings into clear, actionable insights for strategic decision-making.

## About the Dataset
- Source: Food Prices from the National Bureau of Statistics, Nigeria.
- Format: CSV
- Key Fields: Date (Recording date of food price, 2024 - 2025), Food Item (Food Item Name), Outlet Type (Market type where food item is sold), State (Geographic location of market), Price (Item price in Nigerian Naira per Kg)
- N/B: Dataset was filtered to only capture food prices in Lagos, Ogun, and Oyo, as these were the target states for FarmyHub Naija LTD.

## Project Workflow
- Data Collection & Understanding
- Data Cleaning & Preprocessing
- Exploratory Data Analysis (EDA)
- Visualization of Price Trends
- Pricing recommendation
- Statistical and Predictive Modeling (Optional)

## Tools and Technologies
- Power Query for Data Cleaning.
- PowerBI for Visualisation. 
- Python (Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn) for Predictive Modelling.

## Dashboard
An interactive dashboard for the food price analysis can be accessed [here](https://app.powerbi.com/view?r=eyJrIjoiYzY1OWE2ZDktMTY5OC00ZGM4LWJiOWYtZDc0M2ZlOGExZDg1IiwidCI6IjJjYzg3ZmM4LTY5NDQtNDUzMC1hNThlLTFjMDY0MTE4NTYzMCJ9)

![dashboard](farmgrow_dashboard.png)

## Insights from Analysis
### 1. Overall Average Food Prices
- Brown Beans, White Beans and Imported Rice ranked the most expensive foods across all states and sectors
- Garri was the cheapest.

| Observation             | Likely Explanation                                                                                                                                                                                                       |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Beans (Brown/White)** | High protein content makes beans a staple protein substitute; production may have declined in many areas due to pest infestation (e.g., Maruca pod borer). |
| **Imported Rice**       | Affected by exchange rate fluctuations, import duties, logistics costs, and demand for “premium” quality compared to local rice.                                                                                         |
| **Garri (Cheapest)**    | Cassava is abundant, with short farm-to-market supply chains; high local production and low storage cost keep prices stable.                                                                                             |  
---

### 2. Overall Average Food Prices by Sector
- Average food prices in Lagos state was higher in urban markets.
- Surprisingly, Oyo and Ogun state showed higher average food prices in rural markets.

| State     | Possible Reason for Rural > Urban Prices                                                                                                                                                                                     |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Oyo**   | Rural markets may have **lower market density** and less competition, leading to sellers dictating higher margins. Poor infrastructure increases **transport and storage costs**.                                   |
| **Ogun**  | Many rural areas near Lagos act as **supply corridors**. Traders may buy in bulk for resale to Lagos markets, inflating local prices. Limited access to wholesalers or aggregation centers can also push prices up. |
| **Lagos** | Urban demand, rent, storage and logistics costs naturally increase market prices.                                                                                                                                           |  
---

### 3. Overall Average Food Prices by LGA
- In Lagos state, average food prices were highest in Ibeju Lekki and lowest in and Ajeromi/Ifelodun, Ojo, Ikorodu.
- In Ogun state, average food prices were highest in Ifo and lowest in Ipokia.
- In Oyo state, average food prices were highest in Akinyele and lowest in and Irepo.

| **State** | **Highest Price LGA(s)** | **Lowest Price LGA(s)**        | **Likely Causes**                                                                                                                                                                                  |
| --------- | ------------------------ | ------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Lagos** | Ibeju-Lekki              | Ajeromi/Ifelodun, Ojo, Ikorodu | Ibeju-Lekki is undergoing rapid urbanisation and infrastructural development (e.g., Dangote refinery corridor). Demand outpaces supply. Coastal logistics costs and land speculation raise prices. |
| **Ogun**  | Ifo                      | Ipokia                         | Ifo borders Lagos and serves as a commuter belt; higher cost of living and demand from Lagos spillover. Ipokia is remote and more agrarian, with easier access to locally grown produce.           |
| **Oyo**   | Akinyele                 | Irepo                          | Akinyele is near Ibadan’s urban fringe — urban demand and warehouse activity could inflate prices. Irepo, being rural and agrarian, benefits from proximity to production centers.                       |

---

### 4. Overall Average Food Prices by Outlet Type
- Overall average food prices were lowest (N1.24K) in 'City Markets'. This is surprisingly lower than the average prices of food gotten 'Directly from Farmers'.
- 'Supermarkets' had the highest average food price, followed by 'Local Village Markets'.

| Observation                        | Explanation                                                                                                                                                                                                                                                      |
| ---------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **City Market < Direct-from-Farm** | Middlemen and wholesalers in city markets often buy at scale, benefiting from **bulk discounts** and **better logistics**, which reduces per-unit cost. Direct-from-farm buyers may face **high first-mile costs**, poor road networks, and smaller batch sizes. |
| **Supermarket Prices (Highest)**   | Reflect **value-added packaging, refrigeration, retail rent, and convenience markups**.                                                                                                                                                                          |
| **Local Village Market Prices**    | Often reflect **supply unpredictability** and **smaller-scale retailing** rather than consistent bulk pricing.                                                                                                                                                   |
---

## Pricing Recommendations
### 1. Dynamic, Location-Based Pricing.

#### **Rationale**
Prices differ widely across states and LGAs due to logistics, competition, and demand.

#### **Implementation**
- Use spatial clustering (e.g., K-Means) to define **regional price zones**.  
- Automate weekly updates of average market prices by LGA and sector.  
- Adjust prices dynamically based on demand, stock, and competitor trends.

#### **Outcome**
- Keeps FarmGrow prices aligned with local market realities.  
- Prevents overpricing in rural zones and underpricing in high-demand regions.

---

### 2. Fair Price Guarantee for Farmers

#### **Problem**
Farmers often undersell due to lack of market price visibility.

#### **Solution**
- Provide **real-time price comparison tools** on the FarmGrow platform.  
- Guarantee minimum buy prices (e.g., ≥90% of 7-day market average).  
- Reward consistent, high-quality suppliers with **bonus incentives** or **discounted input prices**.

#### **Outcome**
- Strengthens farmer trust and loyalty.  
- Encourages stable supply chains.

---

### 3. Predictive Pricing and Forecasting

#### **Method**
Use machine learning models to forecast:
- Seasonal price trends  
- Supply shortages or surpluses  
- Impact of fuel or logistics shocks  

#### **Implementation Workflow**
1. Aggregate historical food price data by item and location.  
2. Train a predictive model on time-stamped average prices.  
3. Use forecast outputs to preemptively adjust FarmGrow prices.

#### **Outcome**
- Reduces losses from sudden market shocks.  
- Enables proactive decision-making in procurement and inventory.

---

### 4. Seasonal & Behavioral Pricing

#### **Approach**
- Adjust prices around **seasonal cycles** (e.g., harvest vs. lean season).  
- Use **event-based demand triggers** (e.g., Ramadan, Christmas).  
- Offer **discounts or loyalty points** for bulk buyers or recurring customers.

---

### 5. Regional Product Strategy

#### **Recommendation**
- Identify **high-demand products** per region (e.g., rice in Lagos, cassava in Oyo).  
- Tailor pricing and promotion accordingly.  
- Implement **regional bundle pricing** — affordable combos of staple foods in lower-income markets.

---

### 6. Continuous Pricing Feedback Loop

#### **Action Steps**
1. Build a **Pricing Analytics Dashboard** (for e.g Power BI).  
2. Display live KPIs: Average price per LGA, farmer margin, customer affordability index.  
3. Enable weekly model retraining with new data inputs.  
4. Incorporate AI recommendations for price updates.

---

## Conclusion
FarmGrow should implement a **Dynamic + Fair-Price Hybrid Model**, powered by analytics and local intelligence. This approach ensures:
- **Farmers** receive fair and transparent earnings.  
- **Consumers** access affordable, competitive prices.  
- **FarmGrow** maintains profitability and data-driven market leadership.
---
