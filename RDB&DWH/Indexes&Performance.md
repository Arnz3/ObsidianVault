# Space allocation by SQL SErver
- SQL server uses random acces files
- Space allocation in __extents__ and __pages__
- page = 8kB block of contiguous space
- extent = 8 logical consecutive pages
- Unifom extents : from 1 db object
- Mixed extents : can be shared by 8 db objects
- New table or index: allocation in mixed extent
- Extension 8 > pages : in uniform extent


## Creation of indexes
```sql
CREATE [UNIQUE] [| NONCLUSTERED]
INDEX index_name ON table (kolom [,...n])
INCLUDE(kolom [,...n])
```
# Clustered vs Non-clustered indexes
## Table scan 
- Heap: unordered collection of data-pages without clustered index (default)
- Acces via Index Allocation Map (IAM)
- Table scan: query fetches all pages of the table

## Clustered index
table data is put in physical order, Server builds index pages that allow queries to navigate to data directly.
Entire cluster is called clustered index

- contains the base table data, yo u can only create 1
- Leafs of the index are the acctual data

## Non-clustered index
Seperate physical structure, same index tree like clustered index. 
At the leafs theres a set of pointer to the base data.

- seperate from base table data, so can create multiple 

## Filtered index
Only contains row that meet user defined predicate using `WHERE`
- can't be clustered index

## INCLUDE
includes columns add coppies of non-key column values to the leaf level of index tree
- clustered index doesn't need `INCLUDE`

# What's the difference
__What?__
- ordered structure imposed on records from table
- Fast acces through tree structure

__Why?__
- can speed up data retrieval
- can force unicity of rows

__Why not?__
- indexes consume storage (overhead)
- can slow updates, deletes and inserts

## Covering idnex
non-clustered index containing all collumns necessary for a certain query

# When to use index?
__Which colmuns should be indexed?__
- primary and unique columns are indexed automatically
- foreign keys often used in joins
- columns often used in search conditions or joins
- columns used in the `ORDER BY` clause

__Which should NOT?__
- rarely used in queries
- small number of possible values (eg. gender)
- columns in small tables
- columns of type bit, text, or image


