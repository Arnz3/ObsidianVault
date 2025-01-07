# Subqueries

- Always executed first
- Always between ()
- can be nested at >1 level

## Subquery returns single value
Results can be used anywhere with the use of operators:
``` = , > , <, <=, >= , <> ```

```sql
SELECT LastName,FirstName
FROM Employees 
WHERE Country ='USA' 
AND BirthDate = (SELECT MAX(BirthDate) FROM Employees WHERE Country = 'USA')
```

## Subquery returns single column
The resulting column can be used as list with operators:
``` IN, NOT IN, ANY, ALL ```

```sql
SELECT e.EmployeeID, e.FirstName + ' ' + e.LastName As Name 
FROM Employees e
WHERE e.EmployeeID IN (SELECT DISTINCT EmployeeID FROM Orders)
```

# Advanced DML
## Transactions
```sql
BEGIN TRANSACTION 

-- DML INSTRUCTIONS

ROLLBACK; --> undo
COMMIT;   --> save
```

## MERGE
=> you can combine `INSERT, UPDATE, DELETE` 

![[Pasted image 20250107182137.png]]

## Views
=> a View is a saved select statement
No data is saved in the view itself, the select statement is just re-executed

```sql
--Create a view with the number of orders per employee per year
CREATE OR ALTER VIEW vw_number_of_orders_per_employee_per_year 
AS 
SELECT EmployeeID, YEAR(OrderDate) As OrderYear, COUNT(OrderID) As NumberOfOrders FROM Orders GROUP BY EmployeeID, YEAR(OrderDate)
```

## Common Table Expressions (CTEs)
=> using the WITH-component you can give subqueries their own name
```sql
WITH CategoryMinPrice(CategoryID,MinPrice)
AS (SELECT CategoryID, MIN(UnitPrice) FROM Products AS p GROUP BY CategoryID)
```

### CTEs vs Views
- Both are virtual tables
- CTE only exists during the SELECT statement
- CTE not visible for other users and applications

### CTEs vs Subqueries
- Both are virtual tables
- CTE can be reused in the same query
- Subquery is definded in the clause where it is used
- CTE is definded on top of the query
- A simple subquery can always be replaced by a CTE


