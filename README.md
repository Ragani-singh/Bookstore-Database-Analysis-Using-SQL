# Bookstore-Database-Analysis-Using-SQL

Bookstore database analysis project using SQL to analyze customer behavior, order trends, and inventory performance through real-world business queries.

1. Project Overview

This project analyzes a bookstore database using SQL to answer business questions related to customers, orders, inventory, and sales performance.

✅ Database Structure

Tables Used:
Customers → Customer details.
Orders → Purchase records.
Books → Inventory information.

✅ Business Questions Solved

1. Calculate the stock remaining after fulfilling all orders
2. Find the customer who spent the most on orders
3.  Find the most frequently ordered book
4.  List customers who have placed at least 2 orderS
5.  Calculate the total revenue generated from all orders

 
✅ SQL Concepts Used

JOINS
GROUP BY
Aggregate Functions
Subqueries
CASE Statements
Filtering Conditions
Having


✅ Sample Queries

Q. Find the customer who spent the most on orders:

SELECT
	C.CUSTOMER_ID,
	C.NAME,
	SUM(O.TOTAL_AMOUNT) AS MOST_ORDERS
FROM
	CUSTOMERS C
	JOIN ORDERS O ON C.CUSTOMER_ID = O.CUSTOMER_ID
GROUP BY
	C.CUSTOMER_ID,
	C.NAME
ORDER BY
	MOST_ORDERS DESC
LIMIT
	1;

Q. Show the top 3 most expensive books of 'Fantasy' Genre :

SELECT * FROM BOOKS
WHERE genre ='Fantasy'
ORDER BY price DESC
LIMIT 3;

Q.Find the most frequently ordered book:

SELECT B.book_id , B.title, COUNT(O.order_id) AS most_ordered
FROM BOOKS B
JOIN 
ORDERS O 
ON B.book_id = O.book_id
GROUP BY B.book_id , B.title
ORDER BY most_ordered desc
LIMIT 1;


✅ Key Insights

Identified top revenue customers.

Analyzed stock depletion trends.

Customer spending patterns across cities.

