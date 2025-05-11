# Inventory Tracking System

## Description
A MySQL-based Inventory Tracking System that manages:
- **Products** (with categories & suppliers)  
- **Inventory** levels (1-to-1 with products)  
- **Customers** & **Orders** (many-to-many via OrderItems)  
- Automatic constraints (PK, FK, NOT NULL, UNIQUE, CHECK)

Perfect for small retail or warehouse operations to track stock, suppliers, and sales.

## Features
- Relational schema with 1–1, 1–many, and many–many relationships  
- Enforced data integrity via primary keys, foreign keys, unique constraints, and checks  
- Order management with detailed line items  
- Automatic timestamping and status enumeration for orders  

## Prerequisites
- MySQL Server (v5.7+ or 8.0+)  
- MySQL client or GUI tool (e.g. MySQL Workbench, phpMyAdmin)  
- Git (for cloning the repo)

## Installation & Setup

1. **Clone the repository**  
   ```bash
   git clone https://github.com/gich254/week-eight-database-assignment.git
   cd inventory-tracking

2. **Create (or choose) a MySQL database**
CREATE DATABASE inventory_db;

3.  **Import the schema**
mysql -u YOUR_MYSQL_USER -p inventory_db < inventory_management.sql

.Enter your MySQL password when prompted.
4. **Verify tables**
Connect to inventory_db and run:
SHOW TABLES;

You should see:
Customers, Suppliers, Categories, Products, Inventory, Orders, OrderItems
      **Usage**
     1. Add Suppliers
    INSERT INTO Suppliers (name, contact_name, phone, email)
VALUES ('Acme Co.', 'Alice Smith', '+123456789', 'alice@acme.com');
     2.  Add Categories
INSERT INTO Categories (name, description)
VALUES ('Electronics', 'Gadgets and devices');
     3. ## Add Products
    INSERT INTO Products (name, sku, category_id, supplier_id, unit_price)
VALUES ('Wireless Mouse', 'WM-100', 1, 1, 19.99);
     4. Initialize Inventory (1-to-1 with Products)
INSERT INTO Inventory (product_id, quantity, reorder_level)
VALUES (1, 50, 10);
     5. Create Orders
INSERT INTO Orders (customer_id, status)
VALUES (1, 'Pending');

INSERT INTO OrderItems (order_id, product_id, quantity, unit_price)
VALUES (1, 1, 2, 19.99);

     


