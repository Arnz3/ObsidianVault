# OVER clause
- results of a `SELECT` are partitioned
- Numbering, ordering and aggregate functions per partition

// ADDPIC

# RANGE
=> Apply to a window that shifts over the result set
// ADDPIC

# ROWS
=> you might actually want a physical offset
// ADDPIC

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
// ADDPIC

# LEAD
=> refers to next line
// ADDPIC



