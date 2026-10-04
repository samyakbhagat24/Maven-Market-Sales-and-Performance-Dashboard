 # 🛒 Maven Market Sales & Performance Dashboard

_Analyzing retail sales, profit margins, returns, and global regional performance to support executive decision-making and revenue growth strategies using Power BI, DAX, and Data Modeling._

---
## 📌 Table of Contents
- <a href="#overview">Overview</a>
- <a href="#business-problem">Business Problem</a>
- <a href="#dataset">Dataset</a>
- <a href="#tools--technologies">Tools & Technologies</a>
- <a href="#project-structure">Project Structure</a>
- <a href="#data-cleaning--preparation">Data Cleaning & Preparation</a>
- <a href="#exploratory-data-analysis-eda">Exploratory Data Analysis (EDA)</a>
- <a href="#research-questions--key-findings">Research Questions & Key Findings</a>
- <a href="#dashboard">Dashboard</a>
- <a href="#how-to-run-this-project">How to Run This Project</a>
- <a href="#final-recommendations">Final Recommendations</a>
- <a href="#author--contact">Author & Contact</a>

--- 
<h2><a class="anchor" id="overview"></a>Overview</h2>
This project provides an end-to-end business intelligence solution for Maven Market, a multi-national retail grocery chain. By transforming raw transactional, product, customer, and regional data into interactive Power BI analytics, the business can monitor month-over-month (MoM) performance targets, assess return rates across product brands, and visualize geographical revenue growth across the USA, Mexico, and Canada.

---
<h2><a class="anchor" id="business-problem"></a>Business Problem</h2>

Retail chains require continuous tracking of high-level KPIs and granular product-level performance to optimize supply chain, pricing, and regional strategy. 

This project addresses the following objectives:

 - Tracking current month performance for Transactions, Profit, and Returns against dynamic goals.
   
 - Identifying high-profit product brands vs. brands with high return rates.
   
 - Mapping sales footprint and transaction distribution geographically across North America.
   
 - Monitoring revenue trends over time to identify seasonal spikes or dips.
   
 - Evaluating regional revenue contributions to allocate marketing and operational resources.

---
<h2><a class="anchor" id="dataset"></a>Dataset</h2>

 - Sales Data: Transactional records containing quantity sold, store IDs, customer IDs, and product IDs.
   
 - Returns Data: Product return logs tracking return quantities and dates.
   
 - Product Hierarchy: Product brands, categories, wholesale costs, and retail prices.
   
 - Customer & Stores Lookup: Demographics, store regions, and country locations (USA, Mexico, Canada).
   

---
<h2><a class="anchor" id="tools--technologies"></a>Tools & Technologies</h2>

 - Power BI Desktop: Interactive reporting, visual design, and dashboard deployment
   
 - DAX (Data Analysis Expressions): Custom calculated columns and time-intelligence measures (KPI Targets, MoM Growth, Return Rates)
   
 - Power Query (M Language): Data extraction, cleaning, type transformation, and merging
   
 - Data Modeling: Star schema relational model connecting fact and dimension tables.

---
<h2><a class="anchor" id="project-structure"></a>Project Structure</h2>

```
maven-market-analysis/
│
├── README.md
├── .gitignore
├── Maven Market Executive Summary.pdf
│
├── data/                       # Raw and processed CSV data files
│   ├── MavenMarket_Transactions.csv
│   ├── MavenMarket_Products.csv
│   ├── MavenMarket_Customers.csv
│   └── MavenMarket_Returns.csv
│
├── dashboard/                  # Power BI dashboard file
│   └── maven_market_dashboard.pbix
│
└── images/                     # Screenshots and assets
└── dashboard.png
```

---
<h2><a class="anchor" id="data-cleaning--preparation"></a>Data Cleaning & Preparation</h2>

 - Data Transformation:
   
   - Validated and formatted data types across date, currency, integer, and text fields.
     
   - Handled missing and zero values in transaction and return records.
     
 - Calculated Columns & DAX Measures:
   
   - Total Transactions = COUNT(Sales_Data[Quantity])
     
   - Total Profit = SUMX(Sales_Data, Sales_Data[Quantity] * (Product[Retail_Price] - Product[Wholesale_Cost]))
     
   - Profit Margin = DIVIDE([Total Profit], [Total Revenue])
    
   - Return Rate = DIVIDE([Total Quantity Returned], [Total Quantity Sold])
  
   - Current Month Targets: Calculated dynamic MoM goals for Transactions (17,339), Profit (67.87K), and Returns (482).

---
<h2><a class="anchor" id="exploratory-data-analysis-eda"></a>Exploratory Data Analysis (EDA)</h2>

KPI Highlights:

 - Current Month Transactions: 18,325 (Exceeded goal of 17,339 by +5.69%)
   
 - Current Month Profit: $71,682 (Exceeded goal of $67.87K by +5.61%)
   
 - Current Month Returns: 496 (Exceeded max threshold target of 482 by +2.9%)
   
Brand Performance Insights:
 - Top brands such as Hermanos (5,342 transactions, $21,753 profit) and Ebony (5,238 transactions, $20,354 profit) consistently achieve high sales volumes with solid margins (~58%–60%).
   
 - Brands like Horatio (1.26%) and Nationeel (1.18%) showed higher-than-average return rates compared to the portfolio benchmark of 1.00%.

---
<h2><a class="anchor" id="research-questions--key-findings"></a>Research Questions & Key Findings</h2>

 - Did Maven Market meet its current monthly operational targets?
   
   - Yes, both transaction volume (+5.69%) and net profit (+5.61%) beat targets, though product return volume slightly missed the desired target (+2.9%).
     
 - Which product brands generate the highest overall profit margin?
   
   - Plato (63.55%) and BBB Best (62.12%) yield the highest profit margins among high-volume brands.
     
 - What is the overall regional revenue distribution?
   
   - The USA represents the primary share of revenue, followed by Mexico and Canada, as highlighted in the regional treemap and map visualization.
     
 - How does revenue trend on a weekly basis?
   
   - Weekly revenue consistently fluctuates around $10K–$20K, showing strong baseline revenue stability throughout the year with periodic promotional surges.

---
<h2><a class="anchor" id="dashboard"></a>Dashboard</h2>

The Power BI Executive Dashboard includes interactive visual features:
 - Executive KPI Cards
   
 - Product Brand Matrix
   
 - Geographic Map & Country Filter
   
 - Weekly Revenue Trending Column Chart
 
 - Revenue vs. Target Gauge

![Maven Market Sales & Performance Dashboard](Image/Maven%20Market%20Dashboard.png) 
 
---
<h2><a class="anchor" id="how-to-run-this-project"></a>How to Run This Project</h2>
 1. Clone the repository:
 
 ```bash
  git clone https://github.com/samyakbhagat24/Maven-Market-Sales-and-Performance-Dashboard
 ```

2. Download/Inspect the Data:
   - Ensure the raw datasets are placed inside the /data/ folder.
3. Open the Power BI Dashboard:
   - Launch Power BI Desktop.
   - Open dashboard/Maven_Market_Dashboard.pbix.
   - Update data source paths if prompted to refresh background connections.

---
<h2><a class="anchor" id="final-recommendations"></a>Final Recommendations</h2>

 - Quality Control on High-Return Brands: Investigate supply chain and quality standards for brands like Horatio and Nationl to lower return rates under 1.00%.
   
 - Expand Margin Leaders: Increase shelf placement and promotional focus for high-margin brands such as Plato and BBB Best.
   
 - Regional Market Strategy: Continue expansion strategies in Mexico and Canada to match the mature market performance seen across USA store locations.

---
<h2><a class="anchor" id="author--contact"></a>Author & Contact</h2>

**Samyak Bhagat**
Data Analyst
📧 Email: samyakbhagat03@gmail.com.com
🔗 [LinkedIn](https://www.linkedin.com/in/samyakbhagat)
🔗 [github](https://www.github.com/samyakbhagat24)


