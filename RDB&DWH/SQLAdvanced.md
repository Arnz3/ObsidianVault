# Subqueries

- Always executed first
- Always between ()
- can be nested at >1 level

## Subquery returns single value
Results can be used anywhere with the use of operators:
``` = , > , <, <=, >= , <> ```

// ADDPIC

## Subquery returns single column
The resulting column can be used as list with operators:
``` IN, NOT IN, ANY, ALL ```

// ADDPIC

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

//ADDPIC


## Views
=> a View is a saved select statement
No data is saved in the view itself, the select statement is just re-executed

//ADDPIC

## Common Table Expressions (CTEs)
=> suig the WITH-component you can give subqueries their own name

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


