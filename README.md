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

|Name|ID|
|Udani|2|