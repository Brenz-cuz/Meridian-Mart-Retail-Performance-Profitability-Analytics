# Meridian-Mart-Retail-Performance-Profitability-Analytics

**Tableau retail analytics Project | Executive reporting, discount strategy and operational performance**

**Tools:** Tableau Desktop · Tableau Calculated Fields · FIXED Level of Detail (LOD) Expressions · Interactive Dashboards  
**Business focus:** Sales performance · Profitability · Discount strategy · Customer segments · Regional performance · Fulfilment

## Project Overview

I developed two interactive Tableau dashboards to analyse Meridian Mart's retail performance across four US regions. I combined sales, product, customer and geographical dimensions to investigate where revenue translates into profit, where margins are being eroded, and how discounting and shipping patterns differ across the business. The outcome is a decision-support view linking commercial performance with operational considerations.

The work focuses on a retail business scenario and its supplied analytical dataset. The findings reflect that project data; they should not be represented as live results from an operating company.

## Dashboard previews

### 1. Executive Performance

![Meridian Mart Executive Performance dashboard](Meridian%20Mart%20Overview%20Dashboard.png)

The first dashboard consolidates key commercial performance indicators, state-level sales and profit, monthly and yearly trends, product/category comparisons, top and bottom cities, and customer-segment performance. Category and Year filters support exploration.

### 2. Profitability & Operations

![Meridian Mart Profitability and Operations dashboard](Meridian%20Mart%20Dashboard.png)

The second dashboard examines loss-making subcategories, discount bands and average profit, regional discount variation, shipping-mode use, delivery time and top customers. Region and Segment filters support focused analysis.

## Project overview

| Item | Detail |
|---|---|
| Tool | Tableau Desktop |
| Period displayed | 2022–2025 |
| Scope | US retail business across Central, East, South and West regions |
| Product categories | Furniture, Office Supplies and Technology |
| Customer segments | Consumer, Corporate and Home Office |
| Deliverables | Two dashboards, Tableau workbook, methodology and calculated-fields reference |

## Business problem

Meridian Mart needed a clearer understanding of how sales performance, pricing decisions and fulfilment outcomes varied by region, category and customer segment. Looking only at sales could mask products and locations with weak or negative profitability. Discounting and delivery performance also required closer attention to inform commercial decisions.

## Project Objectives

- Build an accessible view of sales, profit, profit margin and unique orders.
- Compare commercial performance across time, states, cities, categories and customer segments.
- Identify loss-making subcategories and quantify their contributions to losses.
- Explore observed relationships between discount levels and average profit.
- Review shipping-mode usage, delivery duration and customer performance.
- Translate analytical findings into practical, testable recommendations.

## Dataset Description

The analytical structure consists of a **Sales** fact table and three supporting dimensions: **LocationDim**, **CustomerDim** and **ProductDim**. The documented fields include order ID, order date, shipping date and mode, customer and segment, state and region, product category and subcategory, sales, profit, quantity and discount. The dashboard covers **2022–2025** and the **Central, East, South and West** regions.

## Data Preparation and Modelling

I worked with a sales-centred analytical model, bringing customer, product and location attributes into the Tableau views. The Tableau workbook contains aggregate KPIs, date-difference calculations, FIXED LOD expressions, discount-bin calculations and table calculations. I used these to support two related dashboard pages, with filters for category, year, region and segment.

See the [methodology](Meridian_Mart_Methodology.pdf) for the modelling assumptions and validation checks.


## Calculated Fields and Analysis

```tableau
// Total Sales
SUM([Sales])

// Total Profit
SUM([Profit])

// Profit Margin
SUM([Profit]) / SUM([Sales])

// Unique Orders
COUNTD([Order ID])

// Shipping duration
DATEDIFF("day", [Order Date], [Ship Date])

// Profit by subcategory, independent of view granularity
{ FIXED [Sub-Category] : SUM([Profit]) }
```
See the [Tableau calculated-fields reference](Meridian_Mart_Calculated_Fields.pdf) for the original workbook formulas and explanations.

## Key Performance Indicators

| Measure | Final dashboard |
| --- | ---: |
| Total sales | **$4.47M** |
| Total profit | **$480.05K** |
| Profit margin | **10.74%** |
| Distinct orders | **2,100** |
| Loss-making subcategories | **2** |
| Combined negative subcategory profit | **Approximately $125.24K** |

## Key Insights

### 1. Strong sales do not always translate into profit

**California:**

Sales - **$531.8K**

Profit - **$66.6K **

**New York :**

Sales - **$300.8K**

Profit - **$42.5K** 

**Colorado :**

Sales - **$119.4K** 

Profit - **-$4.5K in losses**. 

**Implications:** Strong revenue alone is not a reliable indicator of healthy margin.

### 2. Subcategory losses are concentrated

**Tables : -$88.7K** (**71% Losses**)

**Machines - (-$36.5K)**

**Implications:** Both account for roughly **$125.2K** of combined negative subcategory profit. These are high-priority areas for deeper cost, pricing and product-level investigation.

### 3. Profit deteriorates across higher observed discount bands

Average profit = **$379 at 0% discount**,

**$81 at 20%**

 **-$116 at 40%**.

**Implications:** This is an association in the dataset, not proof that discounts alone caused losses. The dashboard's displayed approval cue of **less than 30%** is a working commercial indicator, **not a statistically validated break-even discount**.

### Customer segments

**Consumer:**
**Sales** - **$2.22M**

**Profit** - **$221K**

**Corporate:**

**Sales** - **$1.42M**

**Profits** - **$156K**

**Home Office:**

Sales - **$0.83M **

Profit - **$103K**

**Implications** : Home Office had the highest approximate margin of these segments despite its smaller sales base.

### Yearly trends

2024 recorded approximately **$1.22M sales and $151.5K profit**, the strongest year shown. The presented analysis indicates that sales declined about **17% in 2025** compared with 2024.

### Fulfilment

Standard Class handled the largest displayed order volume (**1,235**), while First Class had the highest displayed profit per order (**approximately $301**). Same Day averaged roughly **0.5–0.6 days** across regions; Standard Class averaged about **5.4–5.5 days**.

## Strategic recommendations

1. **Investigate Tables and Machines first:** review selling prices, product-level profitability, discount patterns and costs before changing the product range.
2. **Review discounts by margin, not revenue:** introduce an evidence-based approval process for unusually deep discounts and validate the threshold with more granular profitability tests.
3. **Prioritise profitable growth markets:** examine whether approaches used in California and New York could transfer to comparable markets, while investigating Colorado's losses.
4. **Grow high-margin segments carefully:** test targeted offers for Home Office customers without sacrificing margin.
5. **Improve operational planning:** track Standard Class service levels and test whether premium shipping is profitable after fulfilment costs.
6. **Track profit alongside sales:** monitor category, city, region and segment profit trends to avoid rewarding volume that erodes margin.


