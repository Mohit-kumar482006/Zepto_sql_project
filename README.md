# Zepto_sql_project
 
A SQL-based data analysis project on Zepto's product catalog, covering data exploration, cleaning, and business insights.

---

## Database

**Table:** `zepto`

| Column | Type | Description |
|---|---|---|
| sku_id | SERIAL | Primary key |
| category | VARCHAR | Product category |
| name | VARCHAR | Product name |
| mrp | NUMERIC | Original price |
| discountPercent | NUMERIC | Discount percentage |
| availableQuantity | INTEGER | Stock quantity |
| discountedSellingPrice | NUMERIC | Final selling price |
| weightInGms | INTEGER | Weight in grams |
| outOfStock | BOOLEAN | Stock status |
| quantity | INTEGER | Quantity |

---

## Data Cleaning

- Removed rows where `mrp = 0`
- Converted prices from **paise to rupees** (divided by 100)

---

## Analysis Queries

| # | Question |
|---|---|
| Q1 | Top 10 best-value products by discount % |
| Q2 | High MRP (>₹300) products that are out of stock |
| Q3 | Estimated revenue per category |
| Q4 | Products with MRP > ₹500 and discount < 10% |
| Q5 | Top 5 categories by average discount % |
| Q6 | Price per gram for products above 100g |
| Q7 | Total inventory weight per category |

---

## SQL Concepts Used

| Concept | Where Used |
|---|---|
| `CREATE TABLE` / `DROP TABLE` | Table setup |
| `SELECT`, `WHERE`, `ORDER BY` | All queries |
| `DISTINCT` | Avoiding duplicate product names |
| `COUNT`, `SUM`, `AVG`, `ROUND` | Aggregations in Q3, Q5, Q7 |
| `GROUP BY` | Category-level aggregations |
| `HAVING` | Filtering grouped results (duplicate names) |
| `UPDATE` | Converting paise to rupees |
| `DELETE` | Removing zero-price rows |
| `IS NULL` | Null value checks |
| `LIMIT` | Top N results in Q1, Q5 |
| Arithmetic expressions | Price per gram (Q6), revenue estimate (Q3) |
| Boolean filtering | Stock status checks (Q2) |

---

## How to Run

1. Set up a PostgreSQL database
2. Run the SQL file to create the table and load data
3. Execute individual queries as needed

```bash
psql -U your_user -d your_database -f zepto_sql_project.sql
```
