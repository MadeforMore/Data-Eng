## 18. Important Manager & Interview Questions

This section contains important questions related to the E-Commerce Sales Data Warehouse project.

### A. Data Warehousing Concepts

**Q1. What is a Data Warehouse?**

A Data Warehouse is a centralized system that stores organized data from different sources for reporting and business analysis.

**Q2. What is Star Schema?**

Star Schema is a Data Warehousing design where one central Fact Table connects to multiple Dimension Tables.

**Q3. What is a Fact Table?**

A Fact Table stores measurable business information such as sales amount, quantity and discounts.

**Q4. What is a Dimension Table?**

A Dimension Table stores descriptive information such as customer details, product names, dates and locations.

**Q5. What is the grain of your Fact Table?**

One row in my FACT_SALES table represents one product line item within a customer order.

### B. Database Keys

**Q6. What is a Primary Key?**

A Primary Key uniquely identifies a record in a table.

**Q7. What is a Foreign Key?**

A Foreign Key represents a relationship between two tables.

**Q8. What is a Surrogate Key?**

A Surrogate Key is a unique identifier generated inside the Data Warehouse.

**Q9. What is a Business Key?**

A Business Key is an original identifier received from the business system, such as CUSTOMER_ID or PRODUCT_ID.

**Q10. Why do we use Surrogate Keys?**

They help identify records independently of the original source systems and make it easier to integrate data from multiple sources.

### C. Snowflake Concepts

**Q11. What is a Virtual Warehouse?**

A Virtual Warehouse provides computing power to execute SQL queries in Snowflake.

**Q12. What is the difference between Database and Schema?**

A Database contains schemas, while a Schema organizes tables and other database objects.

**Q13. What is AUTO_SUSPEND?**

It automatically suspends a Virtual Warehouse after a specified period of inactivity.

**Q14. What is AUTO_RESUME?**

It automatically resumes a suspended Virtual Warehouse when required.

**Q15. Does Snowflake enforce Primary Key and Foreign Key constraints?**

For standard Snowflake tables, Primary Key, Foreign Key and UNIQUE constraints are informational and are not enforced. NOT NULL and CHECK constraints are enforced.

Therefore, we must validate unique records and table relationships ourselves.

### D. SQL and Data Engineering

**Q16. What is JOIN in SQL?**

JOIN combines information from two or more tables using related columns.

**Q17. Why did you use INNER JOIN while loading FACT_SALES?**

INNER JOIN retrieves records that have matching values in the related Dimension Tables.

**Q18. What is INSERT INTO SELECT?**

It is an SQL operation that retrieves data using SELECT and inserts the results into another table.

**Q19. What is GROUP BY?**

GROUP BY groups records having the same value so that we can perform calculations using functions like COUNT(), SUM() and AVG().

**Q20. What is ETL?**

ETL stands for:

- Extract: Collect data from source systems.
- Transform: Clean and modify the data.
- Load: Insert the processed data into the Data Warehouse.

**Q21. Why is data validation important?**

It helps identify duplicate records, missing values, incorrect calculations and invalid relationships before using the data for reporting.

### E. Project-Specific Questions

**Q22. Why did you choose an E-Commerce project?**

I chose this project because e-commerce companies generate different types of business data, including customer, product, order, payment and location information. It provides a practical way to understand Data Warehousing concepts.

**Q23. Why did you create five Dimension Tables?**

Each Dimension Table stores a different type of descriptive information, helping us analyze sales from different business perspectives.

**Q24. Why does ORDER_ID appear multiple times in FACT_SALES?**

One order can contain multiple products. Since our Fact Table stores one row per product line item, the same ORDER_ID can appear multiple times.

**Q25. How do you calculate total sales?**

Total sales are calculated using:

```sql
(QUANTITY * UNIT_PRICE) - DISCOUNT_AMOUNT
```

**Q26. How will you find the highest-selling product?**

I will JOIN FACT_SALES with DIM_PRODUCT, group the records by product name, calculate total revenue using SUM(), and sort the results in descending order.

**Q27. What happens if a Customer ID does not exist in DIM_CUSTOMER?**

The INNER JOIN will not return that source record. In a proper ETL pipeline, I would identify such records and handle them separately rather than silently losing data.

### 19. Key Learnings

Through this project, I am learning:

- How to configure a Snowflake environment.
- How to design a Data Warehouse using Star Schema.
- How Fact and Dimension Tables work.
- How Primary Keys, Foreign Keys and Surrogate Keys work.
- How to create and manage database tables.
- How to write SQL queries and perform JOIN operations.
- How to insert data using INSERT INTO SELECT.
- How to validate records and check data quality.
- How Data Warehousing supports business analysis.

### 20. Future Improvements

The following features are planned for future development:

- Load larger datasets using CSV files.
- Create Snowflake Stages and File Formats.
- Implement ETL pipelines using COPY INTO.
- Handle missing and duplicate records.
- Implement Slowly Changing Dimensions (SCD).
- Use MERGE for repeatable data loading.
- Perform advanced SQL analysis using CTEs and Window Functions.
- Connect Snowflake with Power BI.
- Develop interactive business dashboards.
- Learn query optimization and Snowflake cost management.

### 21. Final Project Status

**Project:** E-Commerce Sales Analytics Data Warehouse

**Platform:** Snowflake

**Database:** ECOMMERCE_DB

**Schema:** ANALYTICS

**Data Modelling:** Star Schema

**Fact Table:** FACT_SALES

**Dimension Tables:** DIM_CUSTOMER, DIM_PRODUCT, DIM_DATE, DIM_LOCATION, DIM_PAYMENT

**Current Status:** In Progress

The database design and table creation have been completed. The sample Fact Table data loading is being verified. ETL development, business analysis and dashboard development are planned next.

---

### Conclusion

This project is my first practical step towards learning Data Engineering and Data Warehousing.

Instead of only learning theoretical concepts, I am implementing them using Snowflake and SQL.

My goal is to understand how real companies organize their business data and use it to generate meaningful insights.

**Thanks for visiting my project!**
