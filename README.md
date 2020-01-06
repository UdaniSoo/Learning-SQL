# Learning-SQL  
## SQL Joins
SQL Joins are used to combine rows from different tables based on related columns between them.  
Different Types of SQL JOINs  
1. (Inner) Join: Returns records that have matching values in both tables.
2. Left Join: Returns all records from the left table and matched records from right table.
3. Right Join: Returns all records from the right table and matched records from the left table.
4. Full Outer Join: Returns all records when there is a match in either left or right tables.

### Inner join  

```sql
SELECT column_name(s)
FROM table1
INNER JOIN table2
ON table1.column_name = table2.column_name;
```  
The INNER JOIN keyword selects all rows from both tables as long as there is a match between the columns. If there are records in the "Orders" table that do not have matches in "Customers", these orders will not be shown!

JOIN Three Tables;  

Q.) Selects all orders with customer and shipper information:  

```sql
Select Orders.OrderID, Customers.CustomerName, Shippers.ShipperName
From ((Orders
Inner join Customers ON Orders.CustomerID=Customers.CustomerID)
Inner join Shippers ON Orders.ShipperID=Shippers.ShipperID);
```  
### SQL LEFT JOIN Keyword  

The LEFT JOIN keyword returns all records from the left table (table1), and the matched records from the right table (table2). The result is NULL from the right side, if there is no match.

Q. select all customers, and any orders they might have:

```sql
Select Customers.CustomerID, Customers.CustomerName
From Customers
Left join Orders ON Customers.CustomerID=Orders.OrderID
```  
Note: The LEFT JOIN keyword returns all records from the left table (Customers), even if there are no matches in the right table (Orders).  

### SQL RIGHT JOIN Keyword  
The RIGHT JOIN keyword returns all records from the right table (table2), and the matched records from the left table (table1).  
  
Q. Return all employees, and any orders they might have placed:

```sql  
SELECT Orders.OrderID, Employees.LastName, Employees.FirstName
FROM Orders
RIGHT JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID
ORDER BY Orders.OrderID;
```

Note: The RIGHT JOIN keyword returns all records from the right table (Employees), even if there are no matches in the left table (Orders).

### SQL FULL OUTER JOIN Keyword  
The FULL OUTER JOIN keyword returns all records when there is a match in left (table1) or right (table2) table records.
  
```sql
SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
FULL OUTER JOIN Orders ON Customers.CustomerID=Orders.CustomerID
ORDER BY Customers.CustomerName;
```  
Note: The FULL OUTER JOIN keyword returns all matching records from both tables whether the other table matches or not.  

