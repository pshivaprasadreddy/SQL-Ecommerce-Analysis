# SQL E-Commerce Database Analysis Project

## 📊 Project Overview
This project demonstrates comprehensive SQL querying and data analysis skills using an e-commerce database. It showcases database schema design, data manipulation, and advanced SQL concepts including JOINs, subqueries, aggregate functions, views, and query optimization.

## 🗄️ Database Schema
The database consists of 6 interconnected tables:

### Tables:
1. **Customers** - Customer information (ID, name, email, location, registration date)
2. **Categories** - Product categories (Electronics, Clothing, Books, etc.)
3. **Products** - Product catalog with pricing, stock, and category references
4. **Orders** - Customer orders with status and amounts
5. **Order_Items** - Individual line items for each order
6. **Payments** - Payment transaction records with methods and dates

### Entity Relationships:
- Customers → Orders (One-to-Many)
- Categories → Products (One-to-Many)
- Orders → Order_Items (One-to-Many)
- Products → Order_Items (Many-to-Many through Order_Items)
- Orders → Payments (One-to-One)

## 🛠️ Technologies Used
- **Database**: SQLite / MySQL / PostgreSQL compatible
- **Tools**: Online SQL Editor (Programiz), GitHub
- **Concepts**: DDL, DML, DQL, Joins, Subqueries, Aggregation, Indexing

## 📁 Repository Structure
```
SQL-Ecommerce-Analysis/
├── README.md                    # Project documentation
├── 01_schema.sql               # Database schema creation
├── 02_data_insertion.sql       # Sample data insertion
├── 03_analysis_queries.sql     # Analysis queries
└── screenshots/                # Query output screenshots
    ├── query1_select_where.png
    ├── query2_aggregates.png
    └── query3_groupby.png
```

## 💡 SQL Concepts Demonstrated

### 1. Basic Queries
- ✅ SELECT with specific columns
- ✅ WHERE clauses with multiple conditions
- ✅ ORDER BY (ASC/DESC)
- ✅ LIMIT for pagination
- ✅ DISTINCT for unique values
- ✅ LIKE operator for pattern matching

### 2. Aggregate Functions
- ✅ COUNT() - Counting records
- ✅ SUM() - Calculating totals
- ✅ AVG() - Finding averages
- ✅ MIN() / MAX() - Finding extremes

### 3. Grouping & Filtering
- ✅ GROUP BY with aggregates
- ✅ HAVING clause for filtered groups
- ✅ Complex grouping scenarios

### 4. JOIN Operations
- ✅ INNER JOIN - Matching records
- ✅ LEFT JOIN - All records from left table
- ✅ RIGHT JOIN - All records from right table
- ✅ Multiple JOINs - Complex relationships

### 5. Advanced Concepts
- ✅ Subqueries (nested queries)
- ✅ CREATE VIEW - Reusable queries
- ✅ CREATE INDEX - Query optimization
- ✅ Date functions and formatting

## 📊 Sample Query Examples

### Example 1: Customers Filtered by Age
```sql
SELECT * FROM Customers 
WHERE age > 25 
ORDER BY age DESC;
```
**Result**: Returns 2 customers (John Doe, 31 and Betty Doe, 28)

### Example 2: Statistical Analysis
```sql
SELECT 
    COUNT(*) as total_customers,
    AVG(age) as average_age,
    MIN(age) as youngest,
    MAX(age) as oldest
FROM Customers;
```
**Result**: 5 customers, avg age 25.6, youngest 22, oldest 31

### Example 3: Customer Distribution by Country
```sql
SELECT country, COUNT(*) as customer_count
FROM Customers
GROUP BY country
ORDER BY customer_count DESC;
```
**Result**: USA (2), UK (2), UAE (1)

### Example 4: Revenue Analysis with JOIN
```sql
SELECT 
    c.first_name || ' ' || c.last_name as customer_name,
    SUM(o.total_amount) as total_spent
FROM Customers c
INNER JOIN Orders o ON c.customer_id = o.customer_id
GROUP BY c.customer_id
ORDER BY total_spent DESC;
```

### Example 5: Product Sales Performance
```sql
SELECT 
    p.product_name,
    cat.category_name,
    COUNT(oi.order_item_id) as times_sold,
    SUM(oi.quantity * oi.unit_price) as total_revenue
FROM Products p
LEFT JOIN Order_Items oi ON p.product_id = oi.product_id
INNER JOIN Categories cat ON p.category_id = cat.category_id
GROUP BY p.product_id
ORDER BY total_revenue DESC;
```

## 🚀 How to Run

### Option 1: Online SQL Editor
1. Visit [Programiz SQL Compiler](https://www.programiz.com/sql/online-compiler/)
2. Copy contents of `01_schema.sql` and run
3. Copy contents of `02_data_insertion.sql` and run
4. Execute queries from `03_analysis_queries.sql`

### Option 2: Local Database
```bash
# For SQLite
sqlite3 ecommerce.db < 01_schema.sql
sqlite3 ecommerce.db < 02_data_insertion.sql
sqlite3 ecommerce.db < 03_analysis_queries.sql

# For MySQL
mysql -u username -p < 01_schema.sql
mysql -u username -p < 02_data_insertion.sql
mysql -u username -p < 03_analysis_queries.sql
```

## 📸 Screenshots
All query outputs are documented in the `/screenshots` folder with annotated results.

## 🎯 Key Insights from Analysis
1. **Customer Base**: 8 customers across 4 countries (USA, UK, Canada, Australia)
2. **Product Range**: 12 products across 5 categories
3. **Revenue**: Total revenue of $4,423.82 from 10 orders
4. **Top Category**: Electronics generates highest revenue
5. **Average Order Value**: $442.38
6. **Most Purchased**: T-Shirts (10 units sold)

## 🔍 Query Optimization Techniques
- Indexed foreign key columns for faster JOINs
- Indexed frequently queried columns (email, order_date)
- Used appropriate data types to minimize storage
- Created views for commonly used complex queries

## 📝 Learning Outcomes
This project demonstrates proficiency in:
- Database design and normalization
- Writing efficient SQL queries
- Data analysis and reporting
- Query optimization
- Understanding business metrics through data

## 👨‍💻 Author
**P Shiva Prasad Reddy**
- GitHub: [@pshivaprasadreddy](https://github.com/pshivaprasadreddy)
- Created for SQL learning and demonstration purposes

## 📄 License
This project is open source and available for educational purposes.

## 🤝 Contributing
Feel free to fork this repository and submit pull requests for improvements!

---
*Last Updated: November 2025*
