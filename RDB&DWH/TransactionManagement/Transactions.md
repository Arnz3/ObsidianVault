# Delineating Transactions
Transaction boundries can be specified: implicitly or explicitly

__Explicitly:__ Dev determines (begin tr, rollback/commit)

Once the first operation is executed, the transaction is active
If the transaction is completed succesfully, it can be commited, if not it needs to be rolled back

# Logfile
registers
- unique log sequence
- unique transaction identifier

may also contain checkpoints

__write ahead__ log strategy
- all updates are registered on log before written to disk



