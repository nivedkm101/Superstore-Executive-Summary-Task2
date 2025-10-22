# Power BI Superstore Dashboard
## 📊 Project Overview
The **Superstore Sales Dashboard** is an interactive Power BI project built to analyze sales, profit, and order trends. It uses the *Superstore dataset* to uncover insights into customer behavior, regional performance, and product profitability.

## ⚙️ Data Cleaning & Transformation
Data was imported from a CSV file containing columns such as *Order Date*, *Ship Date*, *Sales*, *Profit*, and *Category*. Common issues fixed:
- Verify data types:
  - `Order Date`, `Ship Date` → Date
  - `Sales`, `Quantity`, `Discount`, `Profit` → Decimal Number
- Remove duplicates and handle nulls.
- Added calculated columns for metrics like **Days to Ship** and **Year**:
```DAX
  OrderYear = YEAR('Superstore'[Order Date])
  OrderMonth = FORMAT('Superstore'[Order Date],"YYYY-MM")
  ShipDelayDays = DATEDIFF('Superstore'[Order Date],'Superstore'[Ship Date],DAY)
  ProfitMargin = DIVIDE('Superstore'[Profit], 'Superstore'[Sales], 0)
```

## 🧮 DAX Measures Used
```DAX
Total Sales = SUM('Superstore'[Sales])
Total Profit = SUM('Superstore'[Profit])
Profit Margin % = DIVIDE([Total Profit], [Total Sales], 0)
Average Order Value = DIVIDE([Total Sales], DISTINCTCOUNT('Superstore'[Order ID]), 0)
Quantity Sold = SUM('Superstore'[Quantity])
Orders Count = DISTINCTCOUNT('Superstore'[Order ID])
```
## 📈 Key Insights
- The **California** contributed the highest sales and profit.
- **Technology** category yields the best profit margins.
- Orders in **December** peak significantly compared to other months.
- The **Average Delivery Time** is 4 days, which can be improved.

## 🖼 Dashboard View
<img width="1409" height="812" alt="Screenshot 2025-10-22 132825" src="https://github.com/user-attachments/assets/c25ed315-4a90-4ea8-92ba-2854326b2e6b" />

## 🚀 Outcome
The dashboard provides an end-to-end analytical solution to visualize key business performance metrics, enabling stakeholders to make **data-driven decisions**.

## 👤 Author
**Nived K M**  
📧 Email: nivedkm101@gmail.com  
🔗 GitHub: [github.com/nivedkm101](https://github.com/nivedkm101)  
💼 LinkedIn: [linkedin.com/in/nivedkm101](https://linkedin.com/in/nivedkm101)

