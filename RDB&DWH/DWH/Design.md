2 methods:
- Inmon
- Kimball

# Inmon
- normalised database
- data model based on all data of organisation
- modeled based on relationships between data that are stable over time rather than based on variable processes
- connections are immutable, should be starting point of design

# Kimball
- normalizing leads to many different tables
- makes query writing complex
- Dimensional modeling solves problems
- database with star-model
- DWh is collection of all star models, which describe all business processes

## StarSchema
=> logical structure that has fact table, surrounded by denormalized dimension tables

### Fact table 
=> table in which quantities that are measurable stored
- multiple foreign keys referring to each of the dimension tables; with 1:N relation
- primary key of fact table = composition of all foreign keys

### Dimensions
=> tables that contain the context that give meaning to the facts
- stores further info about each of the facts
- contains criteria for agregation tthe measurement data, wil be used as constrained to answer querries
- often denormalized, to speed up report generation, avoids joins

### Measures
__Additive measures__
- can be summorized along all dimensions, using addition operators

__Semi-additive measures__
- can only be summarized using adition along some of the dimensions

__Non-additive measures__
- cannot be added along any of the dimensions

## Snowflake Schema
- is a variant of a starschema, with normalized dimensions but more primary-foreign key relations.
- might be considered if the dimensions grow to large
- beneficial if most querries don't use outer dimensions
- more easily stored in memory

## Fact Constellation
- more then one fact table 

# Specific schema issues
## Surogate keys
=> meaningless integers used to connect fact to dimension

why not reuse existing natural or business keys
- if business keys change, all tables would need ot be updated
- surrogate keys buffer DWH from operational enviroment
- surrogate keys link to fact table, business key only in dimensions
- business keys larger => big index => bad :(

## Granularity of fact table 
=> Level of detial 1 row of fact table 
- Higher (lower) granularity implies more (fewer) rows and more (fewer) questions that can be answered
- Trade of between LOD and storage

## Factless Fact tables
=> fact table that only contains foreign keys

# Optimizing dimension table 
- usually smaller number of rows then fact table 
- columns can grow quite large.
- should be heavily indexed
- average dimension 5 to 10

## Junk Dimensions
- how to deal with low cardinality types?
- add to fact table or model as separate dimension
- Alternative: junk dimension, enumerates all possible combinations
- contributes to maintainability and query performance

## Outrigger tables
- defined to store set of attribute types of dimension which are highly correlated, low in cardinality, updated simultaneously
- Drawback: extra join

## Slowly changing dimension
- refers to fact that some attributes change overtime and provides solutions
- kimball describes 3 types
- now 8+, can be combined

### SCD type 1 
- old value is overwritten
- value not maintained historically
![[Pasted image 20250109112659.png]]
### SCD type 2 
- new record is created, current records and closed records
- Duplicating records and adding start & end date 
![[Pasted image 20250109112713.png]]
### SCD type 3 
- current & previous kept in different columns
- only partial historical info
![[Pasted image 20250109112738.png]]

### SCD type 4 
- Create 2 dimensions: ... & ..._history, both linked to the fact table 
![[Pasted image 20250109112753.png]]
## Rapidly changing dimension 
=> dimensions that change rapidly and regularly over a period of time 
- split customer info into stable and rapidly changing info, put in mini-dimension with new surrogate key
2 options to connect both tables
- Additional foreign key in fact table reffering to mini-dimension
- Include foreign key in Customer dimension
![[Pasted image 20250109112830.png]]
## Advantages Dim model
- Efficiency (consistent DB structure, tools have efficient acces)
- handle changing requirements
- Easily adaptive
- Extensibility
- Model common business situations
- Predic table query processing
