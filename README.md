# Coffee Shop Chain Database Design

## Overview

This project involves designing a relational database system for a New York-based coffee shop chain. The goal is to streamline operations and enhance data management in preparation for national expansion. The database will consolidate data from various sources, including accounting software, supplier databases, POS systems, and spreadsheets.

## Objectives

- Design a central database to house operational data from multiple systems.
- Create database objects (tables, relationships) based on the current data sources.
- Load source data into the database.
- Create subsets of data required by business partners.
- Export and load subsets into staging databases using various RDBMS.

## Database Design

### Entities and Relationships

The database includes the following key entities:

1. **Staff**
   - `staff_id`
   - `first_name`
   - `last_name`
   - `position`
   - `start_date`
   - `location`

2. **Sales Outlet**
   - `sales_outlet_id`
   - `sales_outlet_type`
   - `address`
   - `city`
   - `telephone`
   - `postal_code`
   - `manager`

3. **Sales Transaction**
   - `transaction_id`
   - `transaction_date`
   - `transaction_time`
   - `sales_outlet_id` (Foreign Key)
   - `staff_id` (Foreign Key)
   - `customer_id` (Foreign Key)
   - `product_id` (Foreign Key)
   - `quantity`
   - `price`

4. **Customer**
   - `customer_id`
   - `customer_name`
   - `customer_email`
   - `customer_since`
   - `customer_card_number`
   - `birthdate`
   - `gender`

5. **Product**
   - `product_id`
   - `product_name`
   - `description`
   - `price`

6. **Product Type**
   - `product_type_id`
   - `product_category`
   - `product_type`

7. **Sales Detail** (For normalization)
   - `sales_detail_id`
   - `transaction_id` (Foreign Key)
   - `product_id` (Foreign Key)
   - `quantity`
   - `price`

### Relationships

- **Sales Detail to Sales Transaction**: Each sales detail record is associated with a specific sales transaction.
- **Sales Detail to Product**: Each sales detail record is associated with a specific product.
- **Product to Product Type**: Each product belongs to a specific product type.

## Setup Instructions

1. **Clone the Repository**

   ```bash
   git clone https://github.com/YourUsername/Coffee-Shop-Database-Design.git
   cd Coffee-Shop-Database-Design
