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

// ADDPIC

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

// ADDPIC

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
// ADDPIC

## Nested Cursor
=> in real life programs you often need to declare and use 2 or more cursors in the same block
- often these are related to eachother by parameters

// ADDPIC

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
// ADDPIC

# Tables & User defined types

## User types
- Abstact data types
- can by used as built in type
- distinct type
- structured type: tables


### Distinct type
- Based on basic type
- Allwos to refine existing data types

// ADDPIC


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
// ADDPIC

### Table types
- table t ypes are stored in the DB
- shorter and cleaner code
- can be passed as variable
// ADDPIC


