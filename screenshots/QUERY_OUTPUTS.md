# SQL Query Output Screenshots

This folder contains screenshots of SQL query executions demonstrating various SQL concepts.

## Screenshots Captured

### 1. GROUP BY Query - Customer Count by Country
**File:** `query1_groupby_country.png`

**Query:**
```sql
SELECT country, COUNT(*) as customer_count
FROM Customers
GROUP BY country
ORDER BY customer_count DESC;
```

**Output:**
| country | customer_count |
|---------|---------------|
| USA     | 2             |
| UK      | 2             |
| UAE     | 1             |

**Concepts Demonstrated:**
- GROUP BY clause
- COUNT() aggregate function
- ORDER BY with DESC
- Data grouping and aggregation

---

### 2. SELECT with WHERE and ORDER BY
**File:** `query2_select_where_orderby.png`

**Query:**
```sql
SELECT customer_id, first_name, last_name, age, country
FROM Customers
WHERE age >= 25
ORDER BY age DESC;
```

**Output:**
| customer_id | first_name | last_name  | age | country |
|-------------|------------|------------|-----|------| |
| 1           | John       | Doe        | 31  | USA     |
| 5           | Betty      | Doe        | 28  | UAE     |
| 4           | John       | Reinhardt  | 25  | UK      |

**Concepts Demonstrated:**
- SELECT with specific columns
- WHERE clause with comparison operator (>=)
- ORDER BY with DESC sorting
- Filtering and sorting data

---

### 3. Aggregate Functions - Statistical Analysis
**File:** `query3_aggregate_functions.png`

**Query:**
```sql
SELECT 
    COUNT(*) as total_customers,
    AVG(age) as average_age,
    MIN(age) as youngest_customer,
    MAX(age) as oldest_customer
FROM Customers;
```

**Output:**
| total_customers | average_age | youngest_customer | oldest_customer |
|----------------|-------------|-------------------|----------------|
| 5              | 25.6        | 22                | 31             |

**Concepts Demonstrated:**
- COUNT() - counting total records
- AVG() - calculating average
- MIN() - finding minimum value
- MAX() - finding maximum value
- Multiple aggregate functions in single query

---

## How to Add Screenshot Images

To complete this folder with actual screenshot images:

1. Take screenshots of the query outputs from the SQL editor
2. Save them with the filenames mentioned above
3. Upload to this `screenshots/` folder using:
   - GitHub web interface: Click "Add file" → "Upload files"
   - Git command line:
     ```bash
     git add screenshots/*.png
     git commit -m "Add query output screenshots"
     git push
     ```

## Screenshot Guidelines

- **Format:** PNG or JPG
- **Quality:** Clear and readable
- **Content:** Include both the SQL query and its output
- **Naming:** Use descriptive names (e.g., `query1_groupby_country.png`)

## Additional Queries to Screenshot

Consider adding screenshots for:
- JOIN operations (INNER, LEFT, RIGHT)
- Subqueries
- CREATE VIEW examples
- Complex queries with multiple JOINs
- HAVING clause with GROUP BY
- Date/time functions

---

**Note:** The screenshots demonstrate successful execution of SQL queries and validate the database schema and sample data.
