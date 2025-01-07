# Persistent Stored Modules

__Advantages__
- reduce redundant code
- customization of closed systems
- Security
- Central administration of DB code

__Disadvantages__
- reduce scalability
- Vendor lock-in
- 2 programming languages, debug env

# Stored Procedures SP
=> named collection of SQL ad control-of-flow commands that is stored as a database object

## Local variables
A variable name always starts with `@` 

```sql
DECLARE @name data_type(...)
```
Assign a value to a variable
```sql
SET @name = (expression)
SELECT @name = column FROM ...
```

## Creation of SP

```sql
CREATE PROCEDURE ShowFirstXEmployees @x INT, @missed INT OUTPUT 
AS
BEGIN
	-- procedure
END

-- exec
DECLARE @numberOfMissedEmployees INT
SET @numberOfMissedEmployees = 0
EXEC ShowFirstXEmployees 5, @numberOfMissedEmployees OUT
```

## Return Value

After execution SP returns a value
- type int
- default = 0

`RETURN`statement
- execution of SP stops
- Return value can be specified

## SP with parameters
- A parameter is passed to the SP with an input parameter
- With an ouput you can possibly, pas a value to the SP and get one back

## ErrorHandeling
`RETURN`
- end of execution
`@@error`
- contains error number
- value 0 if OK
`RAISERROR`
- return user defined error or system error
`TRY...CATCH`

# Functions
## Defining

```sql
CREATE OR ALTER FUNCTION CalculateNettoPerMonth (@salary Money)
RETURNS Money 
AS 
BEGIN 
	RETURN 
		CASE --kan ook met IF ... ELSE ... THEN maar dit is mooier.
			WHEN @salary <=40000 THEN @salary *0.7 /12
			WHEN @salary <=55000 THEN @salary *0.65 /12 
			ELSE @salary *0.6 /12 
		END
END
```

## Calling
```sql
dbo.<funcname>
``` 

# Cursors
=> cursors allow to proces individual rows to perform complex row specific operations

## 5 important statements
```sql
DECLARE CURSOR  -- creates and defines cursors
OPEN            -- open declared cursor
FETCH           -- fetches 1 row
CLOSE           -- closes the cursor
DEALLOCATE      -- remove cursor definition
``` 

```sql
DECLARE @supplierID INT, @companyName NVARCHAR(30), @city NVARCHAR(15)

--declare cursor
DECLARE suppliers_cursor CURSOR
FOR 
SELECT SupplierID, CompanyName, City
FROM Suppliers
WHERE Country = 'USA'

--open cursor
OPEN suppliers_cursor

--fetch data
FETCH NEXT FROM suppliers_cursor INTO @supplierID ,@companyName, @city
WHILE @@FETCH_STATUS=0 
BEGIN
	PRINT 'Supplier: ' + str(@SupplierID) + ' ' + @companyName + ' ' + @city
	FETCH NEXT FROM suppliers_cursor INTO @supplierID, @companyName, @city
END

--close cursor
CLOSE suppliers_cursor

--deallocate cursor 
DEALLOCATE suppliers_cursor
```

## Nested Cursor
=> in real life programs you often need to declare and use 2 or more cursors in the same block
- often these are related to eachother by parameters

```sql
DECLARE @supplierID INT, @companyName NVARCHAR(30), @city NVARCHAR(15)

--declare cursor
DECLARE suppliers_cursor CURSOR
FOR 
SELECT SupplierID, CompanyName, City
FROM Suppliers
WHERE Country = 'USA'

--open cursor
OPEN suppliers_cursor

--fetch data
FETCH NEXT FROM suppliers_cursor INTO @supplierID ,@companyName, @city
WHILE @@FETCH_STATUS=0 
BEGIN
	--begin innercursor
	DECLARE products_cursor CURSOR FOR 
	SELECT ProductID, ProductName, UnitPrice 
	FROM Products WHERE SupplierID = @supplierID
	
	OPEN products_cursor --open cursor
	
	FETCH NEXT FROM products_cursor INTO @productID, @productName, @unitPrice
	
	WHILE @@FETCH_STATUS=0 
	BEGIN
		PRINT '-' + STR(@productID) + ' ' + @productName +
		 ' ' + STR(@unitPrice) + 'EUR' 
		FETCH NEXT FROM products_cursor INTO @productID, @productName ,@unitPrice 
	END
	
	CLOSE products_cursor
	DEALLOCATE products_cursor
	--end innercursor
	FETCH NEXT FROM suppliers_cursor INTO @supplierID, @companyName, @city
END

--close cursor
CLOSE suppliers_cursor

--deallocate cursor 
DEALLOCATE suppliers_cursor
```

# Triggers
=> database program; consisting of procedural and declerative instructions, saved in the catalogue and actived by the DMBS if certain operations on the database are executed or conditions are satisfied

comparable with SP but can't be called explicitly
- automatically called by DBMS

## DML Triggers
Can be executed with  
- insert
- update
- delete

Are activated
- before
- instead of
- after

How many times
- for each row
- for each statement

## why?
- Validation of data and complex constrains
- Automatic generation of values
- Support for Alerts

```sql
CREATE OR ALTER TRIGGER updateOrderDetails ON OrderDetails FOR update
AS
--If a record is updated in OrderDetails => check if the new unitPrice is not too low or too high
--If so, rollback the transaction and raise an error 
IF update(unitPrice)
BEGIN
	DECLARE @updatedProductID INT=(SELECT ProductID From inserted) 
	DECLARE @updatedUnitPrice Money=(SELECT UnitPrice From inserted)
	DECLARE @unitPriceFromProducts Money=(SELECT UnitPrice FROM Products WHERE ProductID = @updatedProductID)
	IF @updatedUnitPrice NOT BETWEEN @unitPriceFromProducts *0.85 AND @unitPriceFromProducts *1.15 
	
	BEGIN 
		ROLLBACK TRANSACTION
		RAISERROR ('The updated unit price can''t be correct',14,1)
	END
	END

--If a record is updated in OrderDetails => check if the new discount is not too low or too high
--If so, rollback the transaction and raise an error 
IF update(Discount)
BEGIN
	DECLARE @updatedDiscount REAL=(SELECT Discount FROM inserted) 
	IF @updatedDiscount NOT BETWEEN 0 AND 0.25
	BEGIN
		ROLLBACK TRANSACTION
		RAISERROR ('The updated discount can''t be correct',14,1)
	END
END
```

# Tables & User defined types

## User types
- Abstact data types
- can by used as built in type
- distinct type
- structured type: tables


### Distinct type
- Based on basic type
- Allwos to refine existing data types

```sql
CREATE TYPE IDType FROM INT NOT NULL;
CREATE TYPE NameType FROM NVARCHAR(50) NOT NULL;
```


## Table variables
- Local temporary tables: `#table`
- global temporary tables: `##table` 
- Table variables: `@table`
- Table types

### Local temporary tables
- Stored in tempdb under "System Databases"
- removed if creating level goes out of scope

### Global temporary tables
- Stored in tempdb under "System Databases"
- Visible in all sessions
- Removed if creating session disconnects and there are no more references

### Table Variables
```sql
DECLARE @OrderTotalsByYear AS TABLE
(OrderYear INT NOT NULL PRIMARY KEY,
TotalQuantity INT NOT NULL);
```

### Table types
- table t ypes are stored in the DB
- shorter and cleaner code
- can be passed as variable

```sql
CREATE TYPE TotalOrdersPerYear AS TABLE
(OrderYear INT NOT NULL PRIMARY KEY,
TotalQuantity INT NOT NULL);
```


