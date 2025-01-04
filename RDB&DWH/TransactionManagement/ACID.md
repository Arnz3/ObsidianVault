# Acid Properties of Transactions
ACID => Atomicity, Consistency, Isolation and Durability

## Atomicity
=> ensures that multiple db operations that alter the db state can be treated as one indivisible unit of work

## Consistency
=> refers to the fact that a transaction, if executed in isolation, renders the db form 1 consistent state into another

## Isolation
=> in situation where multiple transactions are executed concurrently. The outcome should be the same as if every transaction is executed in isolation

## Durability
=> the effects of a commited transaction should always be persisted into the database


