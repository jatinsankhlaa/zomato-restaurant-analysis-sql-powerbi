# Zomato Restaurant Analysis | MySQL + Power BI

*Built by Jatin Sankhla | [LinkedIn](https://www.linkedin.com/in/jatin-sankhla-073b25441/)*

Analysis of the Zomato restaurant dataset (9,551 restaurants across 141 cities): business questions answered with **MySQL**, and an interactive 2-page **Power BI** dashboard on restaurant distribution, cuisines, ratings, votes and pricing.

## Tools
- **MySQL:** aggregations, grouping, filtering, ranking (12 business queries)
- **Power BI:** KPI cards, slicers, charts, drill-down tables

## Dashboard

### 1. Overview
![Overview](screenshots/page1_overview.png)

### 2. Restaurant & Customer Insights
![Restaurant & Customer Insights](screenshots/page2_restaurant_customer_insights.png)

## Dataset
`data/Zomato_Restaurant_Dataset.csv`: 9,551 rows, 21 columns (restaurant name, city, cuisines, average cost for two, currency, table booking, online delivery, price range, aggregate rating, rating text, votes and more).

## Key findings
| Metric | Value |
|---|---|
| Restaurants | 9,551 in 141 cities |
| Total votes | ~1.5M |
| Average rating (all restaurants) | 2.67 |
| Average rating (rated restaurants only) | 3.44 |
| Unrated restaurants (rating 0) | 2,148 (22.5%) |
| Excellent-rated restaurants | 301 (3.2%) |
| Online delivery available | 2,451 (25.7%) |
| Table booking available | 1,158 (12.1%) |

- **Geography:** New Delhi alone has 5,473 restaurants (57%). With Gurgaon, Noida, Faridabad and Ghaziabad, Delhi NCR holds about 83% of the dataset.
- **Ratings:** "Average" (3,737) is the largest rating category, followed by "Not rated" (2,148) and "Good" (2,100). Only 301 restaurants are rated "Excellent".
- **Pricing:** price range 1 (cheapest) is the biggest group with 4,444 restaurants (46.5%).
- **Services:** only about 1 in 4 restaurants offers online delivery, and about 1 in 8 offers table booking.
- **Cuisines:** North Indian is the most common listing (936 restaurants), and North Indian + Chinese the most common combination (511).

## Data notes
- **Unrated restaurants:** 2,148 restaurants have a rating of 0 ("Not rated"). Including them lowers the average from 3.44 to 2.67, so the SQL ratings queries exclude them.
- **Currencies:** the dataset covers many countries and `Average Cost for two` is in local currency (rupees, dollars, rand, lira and others). Cost averages across all rows mix currencies, so cost comparisons are most meaningful within one currency (about 90% of rows are in Indian rupees).
- **Cuisines** are stored as combined strings (for example "North Indian, Chinese"), so cuisine queries count each combination as one value.
- **Text encoding:** some restaurant names contain non-UTF-8 characters. Import the CSV with the correct encoding to avoid garbled names.

## Repository structure
```
data/         Zomato restaurant dataset (CSV)
sql/          MySQL analysis queries
powerbi/      Power BI file (.pbix)
screenshots/  dashboard page images
docs/         SQL business analysis report (Word)
```

## How to run
1. In MySQL, create a table named `zomato_restaurant` and import `data/Zomato_Restaurant_Dataset.csv` (Table Data Import Wizard in MySQL Workbench).
2. Run `sql/zomato_sql_analysis.sql`.
3. Open `powerbi/zomato_dashboard.pbix` in Power BI Desktop and refresh the data source.

## About Me
**Jatin Sankhla** | Aspiring Data Analyst

I built this project to practise the full analytics workflow: querying data in SQL and presenting insights in Power BI.

- LinkedIn: [Jatin Sankhla](https://www.linkedin.com/in/jatin-sankhla-073b25441/)
- Email: jatinsankhla980@gmail.com
