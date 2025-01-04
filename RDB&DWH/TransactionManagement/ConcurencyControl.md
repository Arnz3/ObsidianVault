# Typical Concurency problems
Scheduler is responsible for execution of transactions
=> simple serial executions are very inefficient

## Lost update
A succesfull update of data gets overwritten by another transaction unaware of the first update

## Dirty read
A transaction reads updated ata from transaction that gets rollbacked

## Non repeatable read
Transaction T1 reads the smae row multiple times, but obtains different values, because T2 updated this row. 

## Phanthom read
T2 is executing insert or delete on set of rows being read by T1

# Schedules and Serial Schedules
=> a set of n transactions, and sequential ordering over the statements of these transaction, with the following property.
"For each transaction that participates in a schedule and for all statements si and sj that are part of the same transaction: 
if si precedes sj in T, si is executed before sj in S"

a Schedule preserves the ordering of the individual statements within each transaction but allows an arbirary ordering of statements between transactions.

## Serial schedulars
- S is _Serial_ if all statements si of the same transaction T are scheduled consecutively, wihtout any interleave with statements from other transactions.
- Serial schedules prevent parrallel transaction execution.

## Optimistic and Pessimistic Schedulers
__Pessimistic protocol__
- likely that transactions will interfere
- execution delayed until sheduler can schedule in way that conflict is minimized
- will reduce throughput

