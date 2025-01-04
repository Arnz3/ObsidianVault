# Types of failures
## Transaction failure
- results from error in the logic that drives the transactinos operations and/or application logic

## System failure
- occurs if the operating system or the database system crashes

## Media failure
- occurs if the secondary storage is damaged or inaccessible

# System recovery
In case of system failure, there are 2 types of transactions
- already been commited
- still active

Logfile is essential to take account which updates were made by which transaction and keep track of before and after images needed for the `UNDO` and `REDO`

Database buffer flushing strategy has impact on `UNDO` and `REDO`

# Media Recovery
Trade off between cost to maintian the redundant data and time needed to restore the system

## Disk mirroring
- real time, write same data to 2 or more disks
- limited failover time, costlier then archiving
- worse write perfomance, but parrallel acces possible

## Archiving
- db files are periodically copied ot other storage media
- trade off between cost of more frequent backups and cost of lost data
- full vs incremental backups

## Rollforward recovery
- Archiving database fiels and mirroring log files. Backup data can be restored with redo of the more recent transactions. 

