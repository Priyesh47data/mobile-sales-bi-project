# 📱 Mobile Sales Dashboard — Power BI

A comprehensive **Mobile Sales Analytics Dashboard** built in Power BI to track and analyze mobile phone sales performance across brands, models, cities, payment methods, and time periods.

---
## 📸 Dashboard Preview

<table>
  <tr>
    <td><img src="https://res.cloudinary.com/dh5wlux0q/image/upload/v1776623798/Screenshot_2026-04-19_235549_pojcie.png" width="500"/></td>
    <td><img src="https://res.cloudinary.com/dh5wlux0q/image/upload/v1776623798/Screenshot_2026-04-19_235536_h8icb0.png" width="500"/></td>
    
  </tr>
  <tr>
    <td align="center"><b>🏠 Main Dashboard</b></td>
    <td align="center"><b>📅 MTD Report</b></td>
    
  </tr>
</table>

<br/>

<table>
  <tr>
    <td><img src="https://res.cloudinary.com/dh5wlux0q/image/upload/v1776623798/Screenshot_2026-04-19_235521_itkj3s.png" width="500"/></td>
    <td><img src="https://res.cloudinary.com/dh5wlux0q/image/upload/v1776623798/Screenshot_2026-04-19_235446_sa8djh.png" width="500"/></td>
  </tr>
  <tr>
    <td align="center"><b>📊 SPLS Report</b></td>
    <td align="center"><b>🗂️ Data Model</b></td>
  </tr>
</table>
 
---

## 📌 Project Overview

This Power BI project analyzes mobile phone sales data to provide business stakeholders with clear, interactive insights. It includes three report pages—a **Main Dashboard**, an **MTD (Month-to-Date) Report**, and an **SPLS (Sales vs. Previous Year Same Period) Report**—each designed for a different level of business analysis.

---

## 🎯 Key Features

- **KPI Cards** — Total Sales, Total Quantity, Transactions, and Average Price at a glance
- **Monthly Trend Line** — Units sold across all 12 months of the year
- **MTD Cumulative Chart** — Day-level running total of sales within a selected month
- **SPLS Comparison** — Current year sales vs same period last year, by quarter and month
- **Payment Method Breakdown** — UPI, Debit Card, Credit Card, and Cash split via pie chart
- **Top Mobile Models** — Horizontal bar chart for best-selling models
- **Customer Ratings** — Distribution of Excellent, Good, and Bad ratings
- **Sales by Day of Week** — Area chart showing which days drive the most revenue
- **Brand-wise Table** — Total Sales and Transactions per brand with drill-down
- **Interactive Filters** — Slicers for Mobile Model, Payment Method, Brand, and Date

---

## 📂 Data Model

The report uses two tables connected by a date relationship:

| Table | Fields |
|---|---|
| `Data_Table` | Brand, City, Customer Age, Customer Name, Customer Ratings, Date, Day Name, Mobile Model, Payment Method, *(+ more)* |
| `Custom_Calendar` | Date |

> **Relationship:** `Custom_Calendar[Date]` → `Data_Table[Date]` (One-to-Many)

---

## 📊 Report Pages

### 1. Dashboard (Main Overview)
The landing page with all high-level KPIs and charts. Supports filtering by Mobile Model, Payment Method, Brand, and Month.

### 2. MTD Report (Month-to-Date)
Shows a cumulative sales trend for a selected month and year. Useful for tracking progress toward monthly targets day by day.

### 3. SPLS Report (Sales vs Previous Year)
Compares current year performance against the same period in the previous year. Includes breakdowns at the Year, Quarter, and Month levels with a visual bar chart comparison.

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| **Power BI Desktop** | Dashboard development & visualization |
| **DAX** | Custom measures (MTD, SPYL, KPIs) |
| **Power Query (M)** | Data transformation & custom calendar |
| **Excel / CSV** | Source data |

---

## 🔢 Key DAX Measures

```dax
-- Total Sales
Total Sales = SUM(Data_Table[Sales Amount])

-- Month-to-Date Sales
MTD Sales = TOTALMTD([Total Sales], Custom_Calendar[Date])

-- Same Period Last Year
SPYL = CALCULATE([Total Sales], SAMEPERIODLASTYEAR(Custom_Calendar[Date]))

-- Total Transactions
Transactions = COUNTROWS(Data_Table)

-- Average Price
Average Price = AVERAGE(Data_Table[Unit Price])
```

---

## 🚀 Getting Started

### Prerequisites
- [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free download)

### Steps to Run

1. **Clone this repository**
   ```bash
   git clone https://github.com/your-username/mobile-sales-dashboard.git
   ```

2. **Open the report**
   - Launch Power BI Desktop
   - Open `Mobile_Sales_Dashboard.pbix`

3. **Refresh the data** *(if using your own dataset)*
   - Go to **Home → Transform Data**
   - Update the data source path
   - Click **Close & Apply**

4. **Explore the dashboard**
   - Use the slicers (Mobile Model, Payment Method, Brand, Month) to filter the visuals
   - Navigate between **Dashboard**, **MTD Report**, and **SPLS Report** using the left navigation buttons

---

## 📁 Project Structure

```
mobile-sales-dashboard/
│
├── Mobile_Sales_Dashboard.pbix    # Main Power BI file
├── data/
│   └── mobile_sales_data.xlsx     # Source dataset
├── screenshots/
│   ├── dashboard_main.png
│   ├── mtd_report.png
│   ├── spls_report.png
│   └── data_model.png
└── README.md
```

---

## 📈 Sample Insights

- 📦 **Total Sales:** ₹769M across all brands and models
- 🔁 **Transactions:** 3,835 total orders
- 🏆 **Top Brand:** Samsung (by total sales)
- 📱 **Best-Selling Model:** iPhone SE (₹60M)
- 💳 **Most Used Payment:** Cash (25.45%) closely followed by UPI (26.22%)
- 📅 **Peak Sales Day:** Monday

---

## 🙋‍♂️ Author


- GitHub: [@Priyesh50data](https://github.com/Priyesh47data)
- LinkedIn: [linkedin.com/in/your-profile](https://linkedin.com/in/priyesh50)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

> ⭐ If you found this project helpful, please give it a star!
