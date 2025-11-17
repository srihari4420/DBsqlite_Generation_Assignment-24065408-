This project creates a small ecommerce database called Ecommerce_db.sqlite.
Everything in it is fake, but the data is built to look realistic so it can be used for practice, analysis, or coursework.

A Python script handles the whole process: setting up the tables, filling them with customers and products, and then creating more than 1500 individual order items.

How the Data Was Made
1. Setting up the tables

The script starts by creating the tables using standard SQL.
Each table has the usual checks you’d expect in a real system — primary keys, foreign keys, unique fields, and rules for numbers that shouldn’t go below zero.

2. Adding customers and products

Using the Faker library, the script generates:

Random customer names and emails

Random product names and prices

These become the base for the rest of the data.

3. Creating order items

After the first two tables are filled, the script generates a large set of transaction rows.
Each row links back to an existing customer and product so everything stays consistent.

Imperfections Added on Purpose

Real datasets often contain mistakes, so a few intentional issues were added:

A small percentage of customer emails are left blank

Some shipping times are missing

A repeated email is inserted twice to check that the unique rule actually blocks duplicates (which it does)

These small flaws make the dataset feel more like something collected from real usage instead of something perfectly clean.

Database Structure
Products

product_id — primary key

name — must be unique

price — must be positive

Customers

customer_id — primary key

name — required

email — unique but allowed to be empty

Order_Items

Uses a combination of order_id and item_number to identify each row.

Includes:

customer and product references

quantity

discount category

warehouse location

shipping time

Data Types Used

The dataset includes a mix of different kinds of values:

Plain categories (like warehouse locations)

Ordered labels (like discount size)

Numbers where the difference matters (shipping time)

Numbers with a real zero point (quantity ordered)

Ethical Notes

Even though the data looks realistic, everything is completely fake.
No personal details from real people were used, and the script only includes fields that are genuinely needed for the tasks in the assignment.

Running the Script

To rebuild the database from scratch:

pip install faker
