# Power BI Project: PowerBI DataModel & SchemaHub

## Project Overview
This project demonstrates effective data modeling practices in Power BI using different schema designs (Star Schema, Snowflake Schema) and illustrates both active and inactive relationships.

## Contents
- Star Schema example (student, department, office, library, canteen)
- Snowflake Schema example (revenue, customers, products, categories, location, date)
- Active & Inactive Relationship scenarios (sales, orders, calendar/dates)

## Schemas and Relationships

### Star Schema
Central fact table (`student`) connected to dimension tables (`department`, `office`, `library`, `canteen`). This design supports fast queries and simple relationships.

- **Fact Table:** student (Canteen id, Dept id, Lib id, office id, Roll NO, Student Name)
- **Dimension Tables:**
  - Department (Dept id, Dept name)
  - Office (office id, office name)
  - Library (Book Name, Lab ID)
  - Canteen (Canteen id, Menu)

## Star Schema Diagram

<img src="https://github.com/omkarshinde25/PowerBI-DataModel-SchemaHub/blob/main/Pictures/Star%20Schema.PNG" width="800" />

### Snowflake Schema
Normalized version of the star schema, where dimensions are split into related tables:

- **Fact Table:** Revenue (amount, cust_id, lid, pid)
- **Dimension Tables:**
  - Customers (cust_id, cust_email)
  - Products (cid, pid, pname)
  - Categories (cid, cname)
  - Location (lid, lname)
  - Date (dates)

## Snowflake Schema Diagram

<img src="https://github.com/omkarshinde25/PowerBI-DataModel-SchemaHub/blob/main/Pictures/Snowflake%20Schema.PNG" width="800" />

### Active & Inactive Relationships
Models where tables may have multiple relationships (e.g., OrderDate and StockDate with Calendar in the sales table), but only one is active at a time to avoid ambiguity.

- **Example:** Sales/Orders tables having multiple date columns tied to a calendar/date dimension.

## Active & Inactive Relationships Diagram

<img src="https://github.com/omkarshinde25/PowerBI-DataModel-SchemaHub/blob/main/Pictures/Active%20%26%20Inactive%20Relationships.PNG" width="800" />

## How to Use This Power BI Model
1. Import tables as per schemas shown in the diagrams.
2. Establish relationships between fact and dimension tables:
   - For star schema: Simple one-to-many links from dimension tables to fact.
   - For snowflake schema: Use intermediate/join tables.
   - For active/inactive: Mark only one relationship as active. Others can be used in DAX via USERELATIONSHIP.
3. Use Power BI visualizations to analyze and report on your data.
4. When using inactive relationships, activate them in DAX as needed.

## Schema & Relationship Diagram

<img src="https://github.com/omkarshinde25/PowerBI-DataModel-SchemaHub/blob/main/Pictures/Scheam%20%26%20Relationship.PNG" width="800" />

