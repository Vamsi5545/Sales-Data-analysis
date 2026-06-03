# 🛒 ElectroHub – Sales Analytics Dashboard (Power BI)

### Dashboard Link : (https://app.powerbi.com/links/HMZQwfE5a-?ctid=ac63a538-7ef9-43d0-b529-7819df5117ab&pbi_source=linkShare)

---
### Data Set Used : <a href = "https://github.com/Vamsi5545/Sales-Data-analysis/blob/main/Store%2BData.xlsx">Store + Data</a>
---
## 📋 Problem Statement

This dashboard helps **ElectroHub** understand their sales performance across multiple product categories. It enables the business to identify top and bottom performing products, track sales trends over time, and analyze profitability across regions and customer segments.

Through various visuals and filters, the dashboard highlights key improvement areas — such as underperforming categories, high-discount but low-profit products, and cities with low sales penetration — allowing the business to make data-driven decisions.

Since a significant portion of orders may fall in low-margin segments, ElectroHub can use these insights to optimize pricing, promotions, and inventory strategies.

---

## 📦 Product Categories Covered

| Category | Category |
|---|---|
| 🖥️ Electronics | 👟 Footwear |
| 👗 Clothing | 🏠 Home Appliances |
| 💍 Accessories | 🍳 Kitchenware |
| 👜 Bags | 🧴 Personal Care |

---

## 🪜 Steps Followed

- **Step 1** : Loaded data into Power BI Desktop; dataset is a CSV/Excel file.
- **Step 2** : Opened Power Query Editor. Under the **View** tab → **Data Preview** section, enabled **Column Distribution**, **Column Quality**, and **Column Profile** options.
- **Step 3** : Set column profiling to be based on the **entire dataset** (default is only 1000 rows).
- **Step 4** : Checked for errors and empty values across all columns; minor null values were found in discount-related fields and handled appropriately.
- **Step 5** : In the **Report View**, selected a theme under the **View** tab to maintain consistent styling.
- **Step 6** : Added **Visual Filters (Slicers)** for the following fields:
  - 🛍️ Product
  - 📅 Date
  - 👤 Customer ID
  - 🎟️ Promotion Categories
- **Step 7** : Added **KPI Card** visuals for:
  - Total Number of Orders
  - Total Sales
  - Total Profit
  - Average Discount %
- **Step 8** : Created a **Stacked Bar Chart** to display Top 5 & Bottom 5 products by Sales, Profit, and Quantity Sold.
- **Step 9** : Built a **line chart** for Sales Trends across Daily, Monthly, Quarterly, and Annual time periods using a date hierarchy.
- **Step 10** : Added a **scatter chart** to show the relationship between Sales and Profit at the product level.
- **Step 11** : Created a **period comparison visual** using two date slicers, allowing users to compare Sales, Profit, and Quantity Sold across any two custom periods.
- **Step 12** : Added a **Stacked bar chart** to display average discount offered in each discount/promotion category.
- **Step 13** : Built a **detailed order table** showing Sales, Profit, Discount, Net Sales, and all remaining fields — filterable by Product, Date, Customer ID, and Promotion Categories.
- **Step 14** : Added a **map / filled map visual** to show Sales distribution across different cities.
- **Step 15** : Created a **calculated column** to derive Net Sales:

  ```DAX
  Net Sales = Orders[Sales] - Orders[Discount Amount]
  ```

- **Step 16** : Created key **DAX measures** (see below).
- **Step 17** : The report was published to **Power BI Service**.

---

## 📌 Key DAX Measures Used

```DAX
Total Sales = SUM(Orders[Sales])

Total Profit = SUM(Orders[Profit])

Net Sales = [Total Sales] - SUM(Orders[Discount Amount])

Total Orders = COUNTROWS(Orders)

Avg Discount % = AVERAGE(Orders[Discount %])

Profit Margin % = DIVIDE([Total Profit], [Total Sales], 0)

Quantity Sold = SUM(Orders[Quantity])
```

---

## 📊 Dashboard Features & Visuals

### 1. 🏆 Top / Bottom 5 Products
Identifies the **Top 5 and Bottom 5 products** ranked by Sales, Profit, and Quantity Sold — quickly highlighting best-performing and underperforming products.

### 2. 📅 Sales Trends Over Time
Visualizes how sales evolve across **Daily, Monthly, Quarterly, and Annual** time granularities to identify seasonal patterns and growth trends.

### 3. 🔗 Sales vs. Profit Relationship
A scatter chart displaying the **correlation between Sales and Profit**, helping identify high-revenue but low-margin products.

### 4. 🔄 Period-over-Period Comparison
A dynamic comparison tool allowing users to **select any two time periods** and compare Sales, Profit, and Quantity Sold side by side.

### 5. 🏷️ Average Discount by Category
Shows the **average discount percentage** offered within each promotion/discount category to evaluate promotional cost-effectiveness.

### 6. 🔢 Total Number of Orders
A **KPI card** displaying the total order count, adjustable via all global visual filters.

### 7. 📋 Order-Level Detail Table
A detailed filterable table showing per-order metrics: **Sales, Profit, Discount, Net Sales**, and all remaining fields. Filters: Product | Date | Customer ID | Promotion Categories.

### 8. 🗺️ Sales by City
A **geographic visualization** of sales distribution across different cities for regional performance comparison.


---

## 🗂️ File Structure

```
ElectroHub-PowerBI/
│
├── Sales Data.pbix     # Main Power BI report file
├── README.md                     # Project documentation
└── Data/
    └── Store+Data.xlsx      # Source dataset
```

---

## 🚀 Getting Started

1. **Clone or download** this repository.
2. Open <a href="https://github.com/Vamsi5545/Sales-Data-analysis/blob/main/Sales%20Data.pbix">'Sales Data.pbix`</a> using [Power BI Desktop](https://powerbi.microsoft.com/desktop/).
3. If prompted, update the **data source path** to point to the local dataset.
4. Refresh the data and start exploring the dashboard.

---

## 🛠️ Tools & Technologies

- **Power BI Desktop** – Report development
- **DAX** – Calculated columns, measures, and KPIs
- **Power Query (M)** – Data transformation and cleaning
- **Excel / CSV** – Source data

---

## 💡 Insights

A single-page report was created on Power BI Desktop and published to Power BI Service.

The following inferences can be drawn from the dashboard:

### [1] Sales & Orders Overview
- Total orders and sales figures are displayed via KPI cards.
- Net Sales accounts for discounts applied across all orders.

### [2] Top & Bottom Products
- The top 5 products by sales contribute disproportionately to overall revenue.
- Bottom 5 products by profit may need pricing or inventory review.

### [3] Sales Trends
- Sales show seasonal fluctuations when viewed monthly and quarterly.
- Annual trends indicate overall business growth or decline.

### [4] Discount Analysis
- Certain promotion categories carry significantly higher average discounts.
- High discount categories do not always correlate with higher sales volume, indicating potential margin loss.

### [5] City-wise Sales
- Sales are concentrated in a few major cities.
- Smaller cities represent untapped growth opportunities.

### [6] Period Comparison
- Users can compare any two custom time periods to assess campaign effectiveness or seasonal impact on Sales, Profit, and Quantity Sold.

---

## 📷 Dashboard Preview


![Overview Page](<img width="1151" height="643" alt="Image" src="https://github.com/user-attachments/assets/13c59f6e-81f3-467d-8c2e-a1abb5080b3e" />)
![Trends Page](<img width="694" height="318" alt="Image" src="https://github.com/user-attachments/assets/7383555c-2319-45a5-9a58-71b7e5a20624" />)
![Order Details](<img width="1170" height="648" alt="Image" src="https://github.com/user-attachments/assets/df4dc087-9b8a-41e3-a0c8-064d0b191711" />)

---

## 🙋 Author

**Tamminedi Satya Vamsi**

- GitHub: [@Vamsi5545](https://github.com/Vamsi5545)
- LinkedIn: [Tamminedi Satya Vamsi](https://www.linkedin.com/in/satyavamsi5545)
---


