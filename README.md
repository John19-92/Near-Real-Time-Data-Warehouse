# Near Real-Time DataWarehouse Analysis

## Project Description

The objective of this project is to design, implement, and analyze a near-real-time Data Warehouse (DW) prototype for METRO Shopping Store in Pakistan. As one of the biggest superstore chains in Pakistan, METRO has thousands of customers, and it is important for the store to analyze the shopping behavior of their customers in real-time. Based on that, the store can optimize their selling strategies, such as giving promotions on different products.

To make this analysis of shopping behavior practical, there is a need for building a near-real-time DW, and customers’ transactions from Data Sources (DSs) are required to reflect into DW as soon as they appear in DSs. To build a near-real-time DW, we need to implement a near-real-time ETL (Extraction, Transformation, and Loading) tools. Since the data generated by customers is incomplete as it required by DW, it needs to be completed in the transformation layer of ETL. For example, enriching some information from Master Data (MD) as shown in Figure 2.

<p align="center">
  <img src="https://user-images.githubusercontent.com/72251313/233678721-da8921bd-183a-42d2-9e55-6c07cc88c542.png">
</p>

## Approach:

1. Understanding the project requirements:
The first step in approaching this project is to thoroughly understand the project requirements, including the objectives, deliverables, and timeline. It is important to review the project overview, MESHJOIN algorithm, star schema, and data specifications in detail.

2. Setting up the development environment:
The next step is to set up the development environment. This involves installing and configuring the necessary software, such as Eclipse IDE and MySQL database, and creating the required project folders and files.

3. Implementing the MESHJOIN algorithm:
The core of this project is implementing the MESHJOIN algorithm using Java with Eclipse IDE. This involves writing code to load disk partitions into memory, store customer transactions in the hash table, organize incoming data in a queue, and probe for matching tuples to generate join output. It is important to test the code thoroughly to ensure that it works correctly.

4. Designing the star schema:
The star schema is used to map multidimensional decision support data into a relational database. In this step, I designed the star schema based on the project requirements, including identifying the facts, dimensions, attributes, and classification levels. We will use this schema to create multiple aggregated data sources that represent different aspects of business operations.

5. Creating and populating the database:
In this step, I created a database in MySQL and use the provided SQL script to create tables for transaction data and master data. I also populated the tables with data based on the specifications provided in the script.

6. Building the near-real-time DW prototype:
Using the MESHJOIN algorithm and star schema, I built a near-real-time DW prototype for METRO shopping store in Pakistan. This involves implementing a near-real-time ETL tool to reflect customer transactions from data sources into the DW as soon as they appear in the data sources. I will test the DW prototype thoroughly to ensure that it meets the project requirements and delivers the desired results.

7. Analyzing the DW prototype:
In this step, I will analyze the DW prototype to evaluate its performance and effectiveness in optimizing the store's selling strategies. I will use tools such as data visualization and reporting to extract meaningful insights from the DW and provide recommendations for improving the store's operations.

8. Finalizing and presenting the project:
The final step is to finalize the project, including documentation, code cleanup, and presentation preparation. I will ensure that all deliverables are completed on time and to a high standard, and present the project findings to the relevant stakeholders.

## MESHJOIN (Mesh Join)
The MESHJOIN (Mesh Join) algorithm has been introduced by Polyzotis in 2008 with the objective of implementing the Stream-Relation join operation in the transformation phase of ETL.

The main components of MESHJOIN are:
The disk-buffer, which will be an array and used to load the incoming stream tuples from the stream relation.
The in-memory buffer, which will be a hash table and used to load
the tuples from the relation that will be joined with the incoming stream.
The Mesh, which is a graph structure that maps the incoming stream
tuples to the tuples in the relation buffer that they may join with.
The Join engine, which is responsible for performing the actual join
operation between the incoming stream tuples and the relation tuples that are mapped to them by the Mesh.

The MESHJOIN algorithm works as follows:
1. The incoming stream tuples are loaded into the disk-buffer.
2. The relation tuples that will be joined with the stream are loaded into the in-memory buffer.
3. The Mesh is constructed by hashing the relation tuples in the in-memory buffer to their corresponding Mesh nodes.
4. The incoming stream tuples are then processed and mapped to the Mesh nodes.
5. The Join engine uses the Mesh to identify the relation tuples that can be joined with the incoming stream tuples.
6. The Join engine performs the join operation between the incoming stream tuples and the identified relation tuples.
7. The joined tuples are then sent to the output.

The MESHJOIN algorithm provides an efficient solution for performing Stream-Relation join operation during ETL transformations. By using a combination of disk-buffer, in-memory buffer, Mesh, and Join engine, it reduces the I/O operations and improves the performance of the join operation.

<p align="center">
  <img src="https://user-images.githubusercontent.com/72251313/233680766-03f697a8-e951-4214-80a9-18990076d61c.png">
</p>

## Star-schema
The star schema (which you will use in this project) is a data modeling technique that is used to map multidimensional decision support data into a relational database. Star-schema yields an easily implemented model for multidimensional data analysis while still preserving the relational structures on which the operational database is built.
The star schema represents aggregated data for specific business activities. Using the schema, one can create multiple aggregated data sources that will represent different aspects of business operations. For example, the aggregation may involve different levels of product hierarchies, geographic locations, time dimensions, and customer types.
In this project, I implemented a star schema for the METRO shopping store. The schema will include the following dimensions:

Time: including the year, month, day, hour, minute, and second of each transaction.
Product: including the product ID, name, supplier ID, and supplier name.
Customer: including the customer ID and name.
Store: including the store ID and name.
And the fact table will contain the following measures:
Quantity: the quantity of each product purchased.
Price: the price of each product.
Sale: the total sale amount (quantity x price) for each transaction.

<p align="center">
  <img src="https://user-images.githubusercontent.com/72251313/233682695-8b679d20-1674-406d-9dc2-51e3cd9af2bd.png">
</p>

## Enrichment

After completing the ETL and DW analysis, the next step is to enrich the data by adding additional information to enhance the data quality and usefulness. The following steps will be performed in the Enrichment phase:

1. Data profiling to identify data quality issues and inconsistencies.
2. Data cleansing to remove duplicates, missing values, and inconsistencies.
3. Data transformation to create new features or modify existing ones.
4. Data augmentation to add new data from external sources.
5. Data integration to combine data from multiple sources.

Enriching the data can help to uncover hidden insights, improve data accuracy, and enhance decision-making capabilities.

<p align="center">
  <img src="https://user-images.githubusercontent.com/72251313/233685738-d1516b66-a012-4dbc-b9d8-69b85b407bd1.png">
</p>

## Getting Started
These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites
You will need to have MySQL installed on your machine. You can download the latest version of [MySQL](https://www.mysql.com/downloads/) here.
</br>
You will also need to have Java on your machine. You can download the latest version of [Java](https://www.oracle.com/pk/java/technologies/javase/javase8-archive-downloads.html) here.

### Installing
Clone this repository onto your local machine.
```
git clone https://github.com/MuhammadAhmedSuhail/Near-Real-Time-DataWarehouse-Analysis.git
```
Follow the Steps below to run the project:
1. Run Transactional_MasterData Generator.sql to create master data.
2. Run createDW.sql to create the Data Warehouse.
3. Run mj.java upon running it will ask for database credientials default are
  database name:db
  username: root
  password: ""
  This file will populate the data in the data warehouse after implementing the meshjoin.
4. Run queriesDW.sql to extract information from the Data warehouse using OLAP queries.
5. Open the report to view the project overview, mesh join algorithm, shortcomings of this algorithm and
  the learning outcomes of this project.

## DW Analysis
After the data is loaded into the DW, the next step is to analyze the data. This section of the project involves applying OLAP queries to analyze the data in the DW. The following OLAP queries should be applied to the DW:

### Q1. Top 3 Store Names with the Highest Sales in September 2017
This query is intended to determine the top 3 stores that generated the highest sales in September 2017. The output of the query should show the names of the stores along with their respective sales figures.
```
SELECT store.store_name,round(SUM(total_sale)) as revenue FROM sales 
JOIN store on store.store_id = sales.store_id 
JOIN date on date.time_id = sales.time_id where date.month = "september" 
and date.year = 2017 group by sales.store_id order by revenue desc LIMIT 3;
```

<p align="center">
  <img src="https://user-images.githubusercontent.com/72251313/233683228-b83b647a-01b0-41fd-b20b-c3c97cb80440.png">
</p>

### Q2. Top 10 Suppliers that Generated Most Revenue Over the Weekends
The goal of this query is to find the top 10 suppliers that generated the most revenue over the weekends. In addition to finding the top 10 suppliers, the query should also explain how we can forecast the top suppliers for the next weekend.
```
SELECT supplier.supplier_name,round(SUM(total_sale)) as Revenue FROM sales 
JOIN date on date.time_id = sales.time_id 
JOIN supplier on supplier.supplier_id = sales.supplier_id where date.weekend = 1 
group by supplier.supplier_id order by Revenue desc LIMIT 10;
```

<p align="center">
  <img src="https://user-images.githubusercontent.com/72251313/233683517-dfd85630-b3af-4635-a33b-ebf2fefdaf4f.png">
</p>

### Q3. Total Sales of All Products Supplied by Each Supplier with Respect to Quarter and Month
This query aims to present the total sales of all products supplied by each supplier with respect to quarter and month. The output of the query should be organized by supplier and should show the total sales figures for each quarter and month.
```
SELECT sales.product_id,product.product_name,date.month,date.quarter,SUM(total_sale) as Revenue 
FROM sales JOIN product on product.product_id = sales.product_id 
JOIN date on date.time_id = sales.time_id 
group by sales.product_id, date.quarter,date.month;
```

<p align="center">
  <img src="https://user-images.githubusercontent.com/72251313/233683616-a1facd9a-d028-46b4-a671-28a8bd20e7be.png">
</p>

### Q4. Total Sales of Each Product Sold by Each Store
This query is designed to present the total sales of each product sold by each store. The output of the query should be organized by store and then product, with sales figures shown for each store and product.
```
SELECT store.store_name,product.product_name,round(SUM(total_sale)) as Revenue FROM sales 
JOIN store on store.store_id = sales.store_id JOIN product on product.product_id = sales.product_id 
group by sales.store_id,sales.product_id;
```

<p align="center">
  <img src="https://user-images.githubusercontent.com/72251313/233683771-de367c8d-3cd8-4486-a233-30c5d7e7818e.png">
</p>

### Q5. Quarterly Sales Analysis for All Stores Using Drill Down Query Concepts
The purpose of this query is to present the quarterly sales analysis for all stores using drill down query concepts. The output of the query should show the quarterly sales figures for each store, and it should be possible to drill down into the data to see the monthly sales figures for each store.
```
SELECT store.store_name,date.quarter,round(SUM(total_sale)) as Revenue FROM sales 
JOIN date on date.time_id = sales.time_id 
JOIN store on store.store_id = sales.store_id group by store.store_id,date.quarter;
```

<p align="center">
  <img src="https://user-images.githubusercontent.com/72251313/233683886-fc55ac63-b824-4aa6-81e2-1ddb93ca241c.png">
</p>

### Q6. Top 5 Most Popular Products Sold Over the Weekends
The goal of this query is to find the 5 most popular products sold over the weekends. The output of the query should show the names of the products along with their respective sales figures.
```
SELECT product.product_name,round(SUM(total_sale)) as Revenue FROM sales 
JOIN date on date.time_id = sales.time_id 
JOIN product on product.product_id = sales.product_id where date.weekend = 1 group by sales.product_id order by Revenue desc limit 5;
```

<p align="center">
  <img src="https://user-images.githubusercontent.com/72251313/233683992-343fbf17-fecd-46e4-bb88-8a6f77d3b2fd.png">
</p>

### Q7. ROLLUP Operation to Store, Supplier, and Product
This query involves performing a ROLLUP operation to store, supplier, and product. The output of the query should show the total sales figures for each store, supplier, and product.
```
SELECT store_id,supplier_id,product_id from sales group by store_id,supplier_id,product_id with rollup;
```

<p align="center">
  <img src="https://user-images.githubusercontent.com/72251313/233684091-85ddaa97-e424-4b36-8fdc-57b58f5f1068.png">
</p>

### Q8. Total Sales of Each Product for the First and Second Half of Year 2017 Along with Total Yearly Sales
This query aims to extract the total sales of each product for the first and second half of year 2017, along with its total yearly sales. The output of the query should show the total sales figures for each product for each half of the year and for the whole year.
```
SELECT product.product_name,date.half_of_year,round(SUM(total_sale)) as Revenue FROM sales 
JOIN product on product.product_id = sales.product_id 
JOIN date on date.time_id = sales.time_id where date.year = 2017 group by sales.product_id, half_of_year;
```

<p align="center">
  <img src="https://user-images.githubusercontent.com/72251313/233684348-d1e9e22f-422c-442e-8674-9c9bd1379b94.png">
</p>

### Q9. Finding Anomalies in the DW Dataset
This query involves finding an anomaly in the DW dataset. The output of the query should show the anomaly, and the query should be explained in the project report.
```
SELECT * FROM dw.product where product_name = "Tomatoes";
```

<p align="center">
  <img src="https://user-images.githubusercontent.com/72251313/233684675-e7666c87-98de-4ec7-9ffb-65b26f4bebcc.png">
</p>

### Q10. Creating a Materialized View with Name “STORE_PRODUCT_ANALYSIS”
This query involves creating a materialized view with the name "STORE_PRODUCT_ANALYSIS" that presents store and product wise sales. The output of the query should be ordered by store name and then product name. The query should also explain how the materialized view helps in OLAP query optimization.
```
CREATE TABLE `STORE_PRODUCT_ANALYSIS` AS 
SELECT store_name,product_name,total_sale FROM sales JOIN store on sales.store_id = store.store_id 
JOIN product on sales.product_id = product.product_id order by store_name,product_name;
```
```
SELECT * from STORE_PRODUCT_ANALYSIS;
```

<p align="center">
  <img src="https://user-images.githubusercontent.com/72251313/233684826-4005f3a5-efb6-433a-9b38-33b50fc04e12.png">
</p>

## Technologies Used
The following technologies were used in this project:

1. Java: for implementing the MESHJOIN algorithm and other components.
2. Eclipse IDE: for developing and testing the Java code.
3. MySQL: for storing and analyzing the data warehouse.

## Limitations of MESH-JOIN:
1. Largely depend on memory which doesn’t make it optimal.
2. Search almost entire master data for every tuple which makes it costly (No use of indexing).
3. Not resource friendly if the number of tables in the master data are increased.

## Author:
- Muhammad Ahmed Suhail

## Acknowledgments:
- This project was completed for **Data Warehousing** at FAST - NUCES Islamabad.








