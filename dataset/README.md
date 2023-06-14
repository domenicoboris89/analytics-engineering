# Use Case: Build a modern Data Warehouse for Northwind Traders 

This folder contains an extract of a MySQL Database from a fictional enterprise called Northwind Traders, that we will model into a Dimensional Data Warehouse.<br>
https://www.geeksengine.com/article/northwind.html<br>

This folder contains two SQL script to `CREATE` and Populate a BigQuery dataset.<br>

1. `northwind_oltp_bq_schema` creates the schema of the Database
2. `northwind_oltp_bq_data` a series of `INSERT` statements, simulating an OLTP system, to populate the tables

## Details about the UC

- Northwind Traders is an import export food company 
- All their existing architecture is on-premise and their main DMBS is MySQL
- MySQL has been primarily set as OLTP system to record sales, but it's used also as OLAP system to produce reports. However this solution has very poor performances and it's not scalable.<br>

## Objective

The goal is to build a modern DWH on Google Cloud Platform consisting in CloudSQL (MySQL managed) as OLTP system and BigQuery as OLAP system.

## Requirement

- Create a new GCP account to get free $300 credits for 90 days, then create a new project
- Create a new Bigquery dataset which represents the Data Lake of the company
- Create and populate the dataset tables using the scripts in this folder