# Kimia_Farma_Performance_Analytics
This is my Google BigQuery + Looker Studio project, developed as part of the Project-Based Internship with Kimia Farma x Rakamin Academy. I worked on the end-to-end process, including data cleaning, SQL queries, business analysis, and visualization.

The project focuses on analyzing Kimia Farma store transactions across Indonesia from 2020 to 2023, with the main goal of calculating net profit. The analysis highlights performance trends by year, region, and product categories, and the results are presented through an interactive dashboard built in Looker Studio to support business decision-making.
# 🎯 Project Objectives
Kimia Farma operates a nationwide network of stores, generating sales across multiple provinces in Indonesia. Transactions include various product categories and span from 2020 to 2023. The management requested insights into overall business performance, with a focus on net profit. This project answers:
- Comparison of Kimia Farma’s revenue year by year
- Top 10 branches by total transactions per province
- Top 10 branches by net sales per province
- Geo map visualization of total profit across Indonesian provinces
# 🛠️ Tools Used
- Google BigQuery (SQL) → for data cleaning, querying, grouping, and calculating net profit
- Google Looker Studio → for creating interactive dashboards and visualizing insights
# 🔎 Analysis Focus
- Revenue trends: Comparing Kimia Farma’s revenue year by year (2020–2023)
- Branch performance: Identifying the top 10 branches by total transactions and net sales per province
- Geographic insights: Visualizing total profit distribution across Indonesian provinces with a geo map
# 💻 Sample SQL Query
```
WITH laba_final_transaction AS
(
  SELECT 
    *,
    CASE 
      WHEN nett_sales <= 50000 THEN 0.1
      WHEN nett_sales > 50000 AND nett_sales <= 100000 THEN 0.15
      WHEN nett_sales > 100000 AND nett_sales <= 300000 THEN 0.2
    ....
```
📂 For the full set of queries, check the [SQL_code](SQL/sql_code.sql)
# 📊 Visualization
An interactive Google Looker Studio dashboard was created to display:
- Year-over-year revenue comparison (2020–2023)
- Top 10 branches by total transactions per province
- Top 10 branches by net sales per province
- Geo map of total profit across Indonesian provinces

# 📚 Credit
- This project was developed as part of a Project-Based Internship at Kimia Farma.
- All datasets used in this project are © Kimia Farma.
- All SQL queries, analysis, visualizations, key business insights, and recommendations were created by me.
- This repository is intended solely for learning and portfolio purposes.
