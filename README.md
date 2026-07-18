# 💻 Flipkart Laptop Market Analysis — Power BI Dashboard

An interactive Power BI dashboard analyzing **960 laptop listings scraped from Flipkart**, exploring pricing, discounting, brand positioning, and customer ratings across the Indian laptop market.

> 📊 Built with: Python (Web Scraping) → Pandas (Cleaning) → Power BI (Modeling & Visualization)

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Problem Statement](#-problem-statement)
- [Objectives](#-objectives)
- [Dataset](#-dataset)
- [Tech Stack](#-tech-stack)
- [Data Model](#-data-model)
- [Dashboard Walkthrough](#-dashboard-walkthrough)
- [Key Insights](#-key-insights)
- [How to Use](#-how-to-use)
- [Repository Structure](#-repository-structure)
- [Future Enhancements](#-future-enhancements)
- [Author](#-author)

---

## 📖 Overview

E-commerce platforms like Flipkart list thousands of laptops from dozens of brands, each with different pricing, discounting, and rating patterns. For a shopper, seller, or analyst, it's hard to make sense of this at a glance from the raw listing pages.

This project scrapes live laptop listing data from Flipkart, cleans and structures it, and builds a multi-page **Power BI dashboard** to answer questions about brand performance, pricing tiers, discount strategy, and customer satisfaction — turning raw e-commerce data into a decision-ready visual story.

## ❓ Problem Statement

Flipkart hosts laptops from a wide range of brands at varying price points, discount levels, and customer rating profiles, but this information is scattered across hundreds of individual product pages with no consolidated view. There is no easy way to:

- Compare brands on price, rating, and discount strategy side by side
- Identify which price segment (budget / mid-range / premium) dominates the market
- Understand whether discounting correlates with better ratings or is used more by budget brands
- Spot the most competitively priced or highest-rated brands at a glance

This project addresses that gap by scraping, structuring, and visualizing the data into a single interactive dashboard.

## 🎯 Objectives

- Scrape structured laptop product data (name, price, MRP, discount, rating, reviews, brand) from Flipkart
- Clean and engineer features such as **Price Category**, **Rating Category**, and **Discount Range** for segment-level analysis
- Build an interactive, multi-page Power BI report with KPI cards, charts, slicers, and a pivot table
- Surface actionable insights on brand performance, pricing intelligence, and discount behavior

## 🗂 Dataset

| | |
|---|---|
| **Source** | Flipkart.com (laptop category listings) |
| **Collection method** | Python web scraping |
| **Size** | 960 laptop product records |
| **Format** | Structured tabular data loaded into Power BI (table: `Flipcart_WS_Use`) |

**Fields captured per product:**

| Field | Description |
|---|---|
| `Product` | Laptop/product name |
| `Brand Name` | Manufacturer / brand |
| `Price` | Current selling price |
| `M.R.P` | Original listed price (before discount) |
| `Discount` | Discount percentage applied |
| `Discount Range` | Binned discount tier (engineered) |
| `Ratings` | Average customer rating (out of 5) |
| `Rating Category` | Binned rating tier (engineered) |
| `Review` | Number of customer reviews |
| `Price Category` | Binned price segment — Budget / Mid-Range / Premium (engineered) |

## 🛠 Tech Stack

- **Python** — data collection
  - `Requests` — fetching page content
  - `BeautifulSoup` — HTML parsing / scraping
  - `Pandas` — data cleaning, transformation, and feature engineering
- **Power BI Desktop** — data modeling, DAX, and dashboard visualization
- **DAX** — calculated columns/measures for category binning and KPI cards

## 🧩 Data Model

The report runs on a single fact table, **`Flipcart_WS_Use`**, containing the fields listed above. Categorical fields (`Price Category`, `Rating Category`, `Discount Range`) are engineered/binned to enable segment-level slicing without cluttering the visuals with raw continuous values.

## 📑 Dashboard Walkthrough

The report contains **6 pages**:

1. **Home** — Landing page with title and branded navigation into the report
2. **Introduction** — Describes the data source, scraping methodology, and dataset size
3. **Dashboard 1 — Laptop Market Overview & Brand Performance**
   - KPI Cards: Unique Laptop Count, Average Price, Average Rating, Average Discount %, Most Expensive Brand, Highest Rated Brand
   - Top 5 Brands by Laptop Count (donut chart)
   - Top 5 Brands by Average Price (column chart)
   - Average Rating by Brand (clustered bar chart)
   - Average Price by Ratings (area chart)
   - Slicers: Brand, Rating, Price
4. **Dashboard 2 — Pricing & Discount Intelligence**
   - KPI Cards: Average MRP, Max Price, Max Discount %, Total Discounted Products, Average Reviews, Min Price
   - Price Distribution (column chart)
   - Average Discount by Brand (column chart)
   - Brand-wise Price Distribution (pivot table)
   - Trend line chart
   - Slicers: Brand, Rating, Price, Discount
5. **Insights** — Written summary of key takeaways from the analysis
6. **Thank You** — Closing / credits page

## 💡 Key Insights

- **960** laptop products were analyzed from Flipkart via Python web scraping
- **HP (29.89%)** and **ASUS (28.65%)** are the leading brands by product count
- The **Mid-Range** segment contains the highest number of laptops, indicating strong market demand
- **Apple** is the highest-rated brand, with an average rating of **4.7 / 5**
- **Alienware** has the highest average laptop price, positioning it as a premium brand
- The average laptop price across all products is approximately **₹80,044**
- The overall average customer rating is **4.0 / 5**
- **840** products are available with active discounts, showing extensive promotional activity
- The highest discount observed in the dataset is **64%**
- **Ultimus, Motorola, and Samsung** offer the highest average discounts
- Premium brands like **Apple** and **Alienware** rely less on discounting and more on brand equity
- Ratings appear more strongly tied to product quality and brand reputation than to discount depth
- Discounts appear to matter more for competitiveness in the **budget and mid-range** segments
- Overall, the laptop market is highly competitive, with **pricing, ratings, and brand positioning** as the key performance drivers

## 🚀 How to Use

1. Clone or download this repository
2. Make sure you have **[Power BI Desktop](https://www.microsoft.com/en-us/power-platform/products/power-bi/desktop)** installed (Windows only)
3. Open `Flipcart_WS_Dashboard.pbix` in Power BI Desktop
4. Use the slicers (Brand, Price, Rating, Discount) on each dashboard page to filter and explore the data interactively
5. Navigate between pages using the on-page buttons (Home → Introduction → Dashboard 1 → Dashboard 2 → Insights → Thank You)

## 🔮 Future Enhancements

- Automate the scraper to refresh data on a schedule and track price/discount trends over time
- Publish the report to Power BI Service and embed a live/interactive link in this README
- Add brand-level sentiment analysis using review text (if scraped)
- Expand scraping to other product categories for cross-category comparison

## 👩‍💻 Author

**Tanvi Yeram**

If you found this useful, consider ⭐ starring the repo!
