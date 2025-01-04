# Transaction, Recovery and Concurency control
Most databases are multi user databases. 
Concurrent acces to the same data may induce different types of anomalies
DBMS must support ACID

## Transaction
=> set of database operations induced by a single user or application
- Transaction always "succeeds" or "fails"
- Renders database from 1 consistent into another

## Recovery
=> Activity of ensuring that, which ever of the problems occured, the database is returned to a consistent state without any dataloss afterwards

## Concurency control
=> coordination of transaction that execute simultaniously on the same data so they do not cause inconsistency in the data


