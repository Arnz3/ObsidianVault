# Purpose of Locking
- Acces is only granted to transaction in such way no conflict occur
- Lock is variable with db object, value constrains what types of operations are allowed
- Lock manager responsible for granting locks and releasing

## Exclusive Lock
A single transaction aquires sole privilege to interact with db object

## Shared Lock
guarantees that no other transaction will update object

# Isolation levels
__Long-term__
is granted and released acording to a protocol, and held for longer time until transaction is commited
__Short-term__
only held during interval to complete operation (can be used to improve throughput)

![[Pasted image 20250109113903.png]]

## Read uncommited
- lowest isolation level
- Reader doesn't ask for shared lock
- Reader never in conflict with other writer
- Reader reads uncomitted data
- Long-term locks not taken into account

## Read commited
- Default isolation level
- Lowest level that prevents dirty reads
- Reader reads only commited data
- Reader claims shared lock
- If writer hold exclusive lock, reader has to wait
- Reader keeps shared lock until data is obtained

## Repeatable read
- Reader claims shared lock and holds until end of transaction
- Other transactions can't get exclusive lock until end of transaction
- Repeatable read = consistent analysis
- Avoid lost update by claiming shared lock at begin

## Serializable
- Repeatable read only locks rows foudn with first `SELECT`
- Same `SELECT` can give new row (phantoms)
- Serializable avoids phantoms
- Locks all keys that correspond to `WHERE` clause

# Deadlocks
A deadlock occurs when 2 or more transactions are waiting for one anothers lock to be released

Prevention can be achieved by static 2PL:
- Transactions must acquire all its locks upon the start

## Lock Granularity
- trade-off between locking overhead and transaction throughput
- Many DBMS provide option to have optimal granularity levle determent by DMBS


