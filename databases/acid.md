# ACID

## [Krzysztof Grzybek](https://github.com/krzysztof-grzybek)

1. Atomicity specifies that if any query in a single transaction fails, the whole transaction also fails and the database is left unchanged. By "fail" we mean not only application errors, but also external factors, like a power outage.
2. Consistency specifies that each transaction has to lead the database from one valid state to another valid state. It has to maintain its invariants.
3. Isolation specifies that each transaction has to be performed in isolation of each other. There are different levels of isolation:
    * "read uncommitted" - no isolation - we can read uncommitted data from another transaction
    * "read committed" - better isolation - we can read only committed data from other transactions. It leads to inconsistencies if a concurrent transaction has been started during another transaction, but has been finished earlier.
    * "repeatable read" - usually "good enough" isolation - each query in the transaction sees only committed updates at the beginning of the transaction. It might be implemented with locks or versioning. Phantom reads might occur.
    * "serializable" - the highest level of isolation - transactions are not executed concurrently, they are executed consecutively.
    
    The performance goes down with the level of isolation. That's why "repeatable read" is used most often.
    Also, presented model is often more complicated in some db engines implementation. You can find the details here https://github.com/ept/hermitage
4. Durability specifies that after a transaction has been committed, the data will remain even after power outage or crash.

