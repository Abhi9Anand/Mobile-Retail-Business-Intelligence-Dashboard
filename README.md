# Mobile-Retail-Business-Intelligence-Dashboard
**🔗 Dashboard Link :**  [Click here to view dashboard](https://app.powerbi.com/view?r=eyJrIjoiZGI1YTczM2ItMjUzNi00Y2E4LTg2Y2YtYmQ4ZjY3NjYxMTQwIiwidCI6IjEzOGVlZmNmLTdkOTMtNGVhNS1hMTc2LTUxMjU0MDFhODVmNSJ9)
## 📌 Project Overview  

This project presents an end-to-end cloud-based Business Intelligence solution for analyzing mobile retail sales performance.  

The solution integrates **AWS S3 (data storage)**, **Snowflake (cloud data warehouse)**, and **Power BI (data visualization)** to transform raw transactional data into actionable business insights.  

The dashboard provides a 360° analytical view of:  

- 📊 Revenue performance  
- 📱 Brand & model contribution  
- 🌍 Regional sales distribution  
- 📅 Monthly & weekday trends  
- 💳 Payment method usage  
- ⭐ Customer satisfaction ratings  
## 🏗️ End-to-End Data Architecture  

This project follows a modern cloud-based data stack architecture:

- ☁️ Raw sales data stored in **AWS S3 bucket**
- ❄️ Data loaded and transformed in **Snowflake**
- 🧩 Data modeling performed using **SQL** (Fact & Dimension structure)
- 📊 Power BI connected directly to **Snowflake**
- 📈 Interactive dashboard built for business analysis

### 🔄 Architecture Flow  

AWS S3 → Snowflake → Power BI → Business Insights  

This architecture demonstrates practical cloud integration, scalable data warehousing, and real-world Business Intelligence implementation.
## 📂 Dataset Description  

The dataset contains transactional mobile sales data with the following key attributes:

- 📱 Brand  
- 📲 Mobile Model  
- 🌍 City  
- 📅 Date  
- 📦 Units Sold  
- 💰 Price Per Unit  
- 🧾 Transaction ID  
- 💳 Payment Method  
- ⭐ Customer Rating  
- 👤 Customer Age  

A separate **Calendar table** was created to enable time intelligence analysis, including:

- Year  
- Month Name  
- Day Name
  
This structure supports detailed time-based analysis such as monthly trends, weekday performance, and seasonal sales insights.


## 📐 Data Modeling  

The data model follows a **Star Schema** approach to ensure optimized performance and scalability.

### 🔹 Fact Table  
**MOBILE_SALES_DATA**  
Contains transactional-level sales data including:
- Units Sold  
- Price Per Unit  
- Transaction ID  
- Payment Method  
- Customer Rating  
- Customer Age  
- Date  

### 🔹 Dimension Table  
**Calendar**  
Created to enable time intelligence analysis and includes:
- Date  
- Year  
- Month Name  
- Day Name  

### 🔗 Relationships  

- Relationship established between `MOBILE_SALES_DATA[Date]` and `Calendar[Date]`
- One-to-many relationship (Calendar → Mobile Sales Data)
- Time hierarchy enabled for month-wise and weekday analysis  

This modeling approach improves query performance, ensures clean separation of transactional and descriptive data, and supports scalable analytical reporting.
## 📊 Key Performance Indicators (KPIs)  

The dashboard highlights the following core business metrics:

- 💰 **Total Sales:** 769M  
- 📦 **Total Quantity Sold:** 19.15K  
- 🧾 **Total Transactions:** 4K  
- 📊 **Average Order Value:** 40K  

These KPIs provide a high-level executive summary of overall sales performance and business health.

## 🧮 DAX Measures Implemented  

### 💰 Revenue Calculation (Dynamic)

```DAX
Total Sales = 
SUMX(
    'MOBILE_SALES_DATA',
    'MOBILE_SALES_DATA'[Units Sold] * 
    'MOBILE_SALES_DATA'[Price Per Unit]
)

Total Quantity = SUM(MOBILE_SALES_DATA[Units Sold])

Transactions = DISTINCTCOUNT(MOBILE_SALES_DATA[Transaction ID])

Average Order Value = DIVIDE([Total Sales], [Transactions])
```

## 📈 Dashboard Analysis & Insights  

### 1️⃣ Monthly Sales Trend  

- 📊 Peak sales observed around **July (~1700 units)**  
- 📉 Lowest performance recorded in **February (~1450 units)**  
- Indicates seasonal demand fluctuations  

📌 **Insight:** Mid-year performance spike suggests potential promotional or demand-driven growth during this period.

---

### 2️⃣ Brand Performance  

- 🏆 **Apple and Samsung** lead in total revenue contribution  
- 📦 Mid-range brands like **Xiaomi, Vivo, and OnePlus** show strong volume performance  

📌 **Insight:** Revenue is driven by premium brands, while mid-range brands contribute significantly to overall sales volume.

---

### 3️⃣ Model-Level Analysis  

Top performing models include:

- 📱 iPhone SE (~60M)  
- 📱 OnePlus Nord (~58M)  
- 📱 Samsung Galaxy (~56M)  

📌 **Insight:** Competitive pricing and brand value significantly influence model-level revenue contribution.

---

### 4️⃣ City-Wise Sales Distribution  

- 🌆 Metro cities dominate revenue contribution  
- 📍 Strong urban market dependency observed  

📌 **Insight:** Business performance is heavily concentrated in metropolitan regions, indicating potential expansion opportunities in Tier-2 cities.

---

### 5️⃣ Payment Method Distribution  

- 💳 UPI leads (~26%)  
- 💳 Debit Card (~24%)  
- 💳 Credit Card (~24%)  
- 💵 Cash (~24%)  

📌 **Insight:** High digital payment adoption reflects strong consumer preference for cashless transactions.

---

### 6️⃣ Weekday Sales Pattern  

- 📅 Weekend sales significantly higher (**Saturday highest**)  
- 📉 Mid-week performance relatively lower  

📌 **Insight:** Opportunity to implement mid-week promotional campaigns to balance demand.

---

### 7️⃣ Customer Ratings  

- ⭐ Majority ratings between **4 and 5**  
- ❗ Very low negative ratings  

📌 **Insight:** Overall customer satisfaction remains strong, supporting brand trust and repeat purchases.

## 🧠 Skills Demonstrated  

### 📊 Business Intelligence  
- KPI development  
- Interactive dashboard design  
- Data storytelling  
- Insight generation  

### 📐 Data Modeling  
- Star schema implementation  
- Date dimension creation  
- Relationship optimization  

### 🧮 DAX & Analytics  
- Iterator functions (`SUMX`)  
- Aggregation measures  
- Dynamic KPI calculations  
- Time-based analysis  

### ☁️ Cloud & Data Warehousing  
- AWS S3 data storage  
- Snowflake SQL transformations  
- Cloud-to-BI connectivity  

---

## 💡 Business Value Delivered  

This solution enables management to:

- 📈 Monitor revenue performance in real time  
- 🏆 Identify high-performing brands and regions  
- 📅 Detect seasonal sales trends  
- 📦 Optimize inventory planning  
- 💰 Improve pricing strategy  
- 💳 Promote digital payment channels  

The dashboard supports data-driven decision-making and enhances operational efficiency.

---

## 🚀 Future Improvements  

- 📊 Implement Year-over-Year (YoY) growth analysis  
- 🔮 Add forecasting model using time intelligence  
- 🔐 Apply Row-Level Security (RLS)  
- ⚙️ Automate data pipeline using Snowpipe  
- 🔄 Enable incremental data refresh  
- ⚡ Deploy near real-time dashboard version  


