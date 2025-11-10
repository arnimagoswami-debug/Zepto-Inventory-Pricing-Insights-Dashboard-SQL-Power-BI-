# 🧾 Zepto Inventory & Pricing Insights Dashboard (SQL + Power BI)

### 📊 Project Overview
This end-to-end analytics project explores **Zepto’s product, pricing, and inventory data** using **SQL** for data preparation and **Power BI** for visualization.  
The goal is to uncover insights about revenue trends, pricing effectiveness, and stock performance.

---

### 🛠 Tools & Technologies
- **SQL** – Data cleaning, joins, aggregation, and filtering  
- **Power BI** – Data modeling, DAX calculations, and dashboard visualization  
- **Excel** – Data preprocessing and export from SQL  
- **DAX Measures** – For revenue, discounts, and stock KPIs  

---

### 🧠 Project Workflow
1. **Data Extraction (SQL):**  
   - Connected Zepto’s product data from SQL database  
   - Used joins to merge product, category, and stock tables  
   - Filtered invalid and missing values for clean analysis  

2. **Data Transformation:**  
   - Exported SQL output to Power BI  
   - Built data model and defined relationships  
   - Created calculated columns (e.g., *Price per Gram, Discount%*)  

3. **Data Visualization (Power BI):**  
  
📈 Dashboard Pages & Screenshots
🏠 Page 1: Overview Dashboard

KPIs: Total Revenue, Avg Discount %, Out of Stock Products, Total Weight
Bar chart: Revenue by Category
Pie chart: Stock Status (In Stock vs Out of Stock)
Navigation buttons for next pages



💰 Page 2: Pricing Insights

Table: Top 10 Best Discounted Products
KPI Cards: Avg Price per Gram, Avg Discount %, Total MRP Value
Clustered column chart: MRP vs Selling Price
Navigation button to move between Overview ↔ Stock


📦 Page 3: Stock & Inventory Insights

KPI: Total Inventory Weight (kg)
Treemap: Inventory Weight by Category
Bar Chart: Quantity by Category
KPI: Out of Stock Count (highlighting missing inventory)


---

### 📈 Key Insights
- 🔸 **Average Discount:** 7.63% across all categories  
- 🔸 **High-value items (> ₹2000)** show **46% average discount**  
- 🔸 **Cooking Essentials & Munchies** generate maximum revenue (~₹337K each)  
- 🔸 **~88% products are Out of Stock**, highlighting inventory optimization needs  
- 🔸 **Total Inventory Weight:** 1,447 kg | **Total Quantity:** 15K units  

---

🗂️ File 
- <a href= "https://github.com/arnimagoswami-debug/Zepto-Inventory-Pricing-Insights-Dashboard-SQL-Power-BI-/blob/main/ZeptoProject.sql"> Dataset View
## 📷 Dashboard Preview
![Dashboard Screenshot](https://github.com/arnimagoswami-debug/Zepto-Inventory-Pricing-Insights-Dashboard-SQL-Power-BI-/blob/main/Dashboard%20Overview.png)
## 📷 Pricing Insights Preview
![Pricing Insights Preview](https://github.com/arnimagoswami-debug/Zepto-Inventory-Pricing-Insights-Dashboard-SQL-Power-BI-/blob/main/Pricing%20Insight.png)
## 📷 Stock & Inventory Insights Preview
![Stock & Inventory Insights Preview](https://github.com/arnimagoswami-debug/Zepto-Inventory-Pricing-Insights-Dashboard-SQL-Power-BI-/blob/main/Stocks%20Insight.png)


### 🧩 DAX Measures Used
```DAX
Total Revenue = SUM(zepto[discountsellingprice])
Avg Discount % = AVERAGE(zepto[discountPercent])
Total Products = DISTINCTCOUNT(zepto[Name])
Total Inventory Weight (kg) = DIVIDE(SUM(zepto[weightInGms]), 1000)
Out of Stock Products = COUNTROWS(FILTER(zepto, zepto[outOfStock] = TRUE))
Price per Gram = DIVIDE(zepto[discountsellingprice], zepto[weightInGms])

✨ Created by Arnima | Data Analyst Project
