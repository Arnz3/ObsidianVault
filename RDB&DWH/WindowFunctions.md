# OVER clause
- results of a `SELECT` are partitioned
- Numbering, ordering and aggregate functions per partition

```sql
SELECT CategoryID, ProductID, UnitsInStock, 
SUM(UnitsInStock) OVER (PARTITION BY CategoryID ORDER BY ProductID) TotalUnitsInStockPerCategory 
FROM Products
```

# RANGE
=> Apply to a window that shifts over the result set
```sql 
SELECT CategoryID, ProductID, UnitsInStock, 
SUM(UnitsInStock) OVER (PARTITION BY CategoryID ORDER BY ProductID
RANGE BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW) TotalUnitsInStockPerCategory FROM Products
```

![[Pasted image 20250107183051.png]]
# ROWS
=> you might actually want a physical offset
![[Pasted image 20250107183123.png]]

```sql
SELECT EmployeeID, FirstName + ' ' + LastName As FullName, Salary, AVG(Salary) OVER (ORDER BY Salary DESC ROWS BETWEEN 2 PRECEDING AND CURRENT ROW) As AvgSalary2Preceding FROM Employees
```
# Ranking
`ROW_NUMBER()`
numbers output, returns the sequential number of a row within a partition

`RANK()`
simular to above, returns rank within the partition

`DENSE_RANK()`
returns the rank of each row, with no gaps

`PCT_RANK()`
Shows rank on scale from 0-1


# LAG
=> refers to prev line
```sql
WITH cte AS (SELECT EmployeeID, FirstName + ' ' + LastName As FullName, Salary, LAG(Salary) OVER (ORDER BY Salary DESC) As PrecedingSalary FROM Employees)

SELECT *, PrecedingSalary - Salary As EarnsLessThanPreceding FROM cte
```

# LEAD
=> refers to next line
```sql
WITH cte AS (SELECT EmployeeID, FirstName + ' ' + LastName As FullName, Salary, LEAD(Salary) OVER (ORDER BY Salary DESC) As FollowingSalary FROM Employees)

SELECT *, Salary - FollowingSalary As EarnsMoreThanPreceding FROM cte
```



