# 🏍️ Territory Lookup – Bike Spare Parts Sales Dashboard (Power BI)

This Power BI project visualizes and analyzes **bike spare parts sales** across multiple **territories and bike brands**, helping stakeholders understand regional performance, product demand, and customer trends.

---

## 📊 Project Overview

The **Territory Lookup Dashboard** provides a comprehensive view of sales performance across different geographical territories.  
It helps the management team track **which regions**, **bike models**, and **spare parts** contribute most to overall revenue.

This dashboard was designed to support **data-driven decision-making** in supply chain, inventory management, and regional marketing.

---

## 🎯 Objectives

- Analyze sales of bike spare parts across multiple regions  
- Identify top-performing territories and underperforming areas  
- Track sales by **bike model**, **product category**, and **sales representative**  
- Visualize trends to optimize **inventory** and **distribution strategy**

---

## 🧰 Tools & Technologies

| Tool | Purpose |
|------|----------|
| **Power BI** | Dashboard creation and data visualization |
| **Excel / CSV** | Source data (sales, products, and territories) |
| **Power Query** | Data cleaning and transformation |
| **DAX (Data Analysis Expressions)** | Custom measures and KPIs |
| **SQL (optional)** | Data extraction and preparation |

---

## 🗂️ Dataset Description

The dataset includes information on **bike spare parts**, their sales, and distribution details.

| Column | Description |
|---------|-------------|
| **Order_ID** | Unique order identifier |
| **Date** | Transaction date |
| **Territory** | Sales region or zone |
| **Dealer_Name** | Authorized dealer or distributor |
| **Bike_Model** | Model name (e.g., Pulsar, Apache, Splendor) |
| **Part_Name** | Spare part sold (e.g., brake pad, chain, clutch plate) |
| **Quantity** | Number of items sold |
| **Unit_Price** | Price per unit |
| **Total_Sales** | Total amount (Quantity × Unit Price) |
| **Sales_Rep** | Sales representative handling the territory |

---

## 📈 Dashboard Features

### 🔹 **Territory Performance View**
- Regional sales comparison by total revenue  
- Map visualization to highlight high-performing territories  

### 🔹 **Product Analysis**
- Top-selling spare parts  
- Sales by bike model and part category  

### 🔹 **Dealer Performance**
- Dealer contribution to sales by territory  
- Profitability metrics and dealer ranking  

### 🔹 **Time-Based Analysis**
- Monthly and yearly sales trends  
- Seasonal demand patterns for specific spare parts  

### 🔹 **KPIs**
- 💰 Total Revenue  
- 📦 Total Quantity Sold  
- 🏆 Top Territory & Best-Selling Product  
- 📅 Monthly Growth %

---

## 🧮 Key DAX Measures Used

```DAX
Total Sales = SUM('Sales'[Total_Sales])

Total Quantity = SUM('Sales'[Quantity])

Average Selling Price = DIVIDE([Total Sales], [Total Quantity])

Monthly Growth % =
VAR CurrentMonth = [Total Sales]
VAR PreviousMonth = CALCULATE([Total Sales], DATEADD('Calendar'[Date], -1, MONTH))
RETURN DIVIDE(CurrentMonth - PreviousMonth, PreviousMonth)
