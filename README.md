# 📊 Sales Dashboard | Overview (Tableau)

This project showcases an interactive **Sales Performance Dashboard** built using **Tableau**, designed to analyze **yearly sales trends, profit performance, customer segments, and regional contributions** across the United States.

The dashboard helps users compare **Current Year (CY) vs Previous Year (PY)** performance using advanced KPI tracking, trend analysis, and state-level insights.

![Sales Dashboard Overview | Tableau]()

---


## 🎯 Project Objectives

- Analyze **Total Sales, Profit, and Quantity** trends over time.
- Compare **2022 vs 2021 (CY vs PY)** performance.
- Identify **Max & Min months** for sales and profit.
- Track **YOY (Year-Over-Year) change indicators**.
- Visualize **Sales & Profit distribution by U.S. states**.
- Segment performance by **Consumer, Corporate, and Home Office**.
- Display **Top sales by manager and region** for strategic decisions.

---

## 📁 Dataset Details

- **Region** – U.S States
- **Order Date**
- **Sales**
- **Quantity**
- **Profit**
- **Segment**
- **Manager Name**
- **Region Zone** (Central, East, South, West)

---

## 📊 Dashboard Highlights

### 🔹 KPI Trend Overview
- **2022 vs 2021 (CY vs PY)**
- Shows **CY Sales, Profit, and Quantity**
- YOY percentage change (up/down indicators)

### 🔹 Regional Sales Visuals
- **Sales & Profit distribution by US States (map view)**
- Highlighted states **above and below average**
- Color-coded indicators

### 🔹 Monthly Sales by Segment
- Trend chart split into:
  - **Consumer** (50.23K)
  - **Corporate** (44.64K)
  - **Home Office** (29.71K)

### 🔹 Sales by Location & Manager
Ranked horizontal bar chart showing:
| Manager | Region | Sales |
|--------|--------|-------|
| Sadie Pawthorne | West | 250K |
| Chuck Magee | Central | 213K |
| Roxanne Rodriguez | East | 147K |
| Fred Suzuki | South | 123K |

---

## 🎛 Filter Controls

| Filter | Description |
|--------|-------------|
| Year Selector | Choose CY or PY for analysis |
| Measure | Sales / Profit / Quantity |
| Segment | Consumer / Corporate / Home Office |
| Region | Central / East / South / West |
| State | Geographic drill-down |

---

## 🧮 Calculated Fields / DAX Logic Used

```DAX
-- YOY Sales
YOY Sales = [Total CY Sales] - [Total PY Sales]

-- YOY Sales Indicator
YOY Sales Indicator =
IF([YOY Sales] > 0, "↑", "↓")

-- YOY Profit
YOY Profit = [Total CY Profit] - [Total PY Profit]

-- YOY Profit Indicator
YOY Profit Indicator =
IF([YOY Profit] > 0, "↑", "↓")

-- YOY Quantity
YOY Qty = [Total CY Qty] - [Total PY Qty]

-- YOY Quantity Indicator
YOY Qty Indicator =
IF([YOY Qty] > 0, "↑", "↓")

-- Average Sales (Overall)
Avg Sales Overall = AVERAGE('Sales Data'[Sales])

-- Average Profit by State
Avg Profit State Wise =
AVERAGE('Sales Data'[Profit])

-- Min/Max Sales & Profit
Min Max Sales = MIN('Sales Data'[Sales])
Min Max Profit = MAX('Sales Data'[Profit])
