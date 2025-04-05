**DATA MANAGEMENT**

---

**Contents**:

- [ACID principles](#acid-principles)
- [Data warehouse](#data-warehouse)

---

# ACID principles
<details><summary>Atomicity</summary>An atomic transaction is a data creation/modifying operation that ensures that any commit made either finishes the entire operation successfully or rolls back the database to its state prior to the commit being initiated (e.g. in case of a lost connection in the middle of an operation). This is important for preventing crashes or outages from creating uncertainty about the state of the data storage system (e.g. if a crash occurs during a transaction without atomicity, it can be impossible to know how far along the transaction had progressed before it was interrupted). Evidently, atomicity is key in maintaining clarity about the contents of a data storage system amid data creation/modifying operations.</details>

<details><summary>Consistency</summary>Consistency refers to maintaining data integrity constraints. A consistent transaction does not violate integrity constraints placed on the data by the data storage system's rules. Enforcing consistency ensures that if a data storage system enters an illegal state (i.e. if a violation of data integrity constraints occurs) the transaction is aborted and data storage system is rolled back to its previous legal state. Evidently, consistency is key in maintaining the integrity of the data as defined by the data storage system's constraints, which are often applied to ensure that the data is meaningful (e.g. in a bank's database, a customer cannot have negative balance).</details>

<details><summary>Isolation</summary>Isolation refers to the isolation of the effect of each transaction on the functioning of other transations. In other words, reads or writes performed on the database are not to be impacted by other reads and writes of separate transactions on the same database. To this end, a global order is created with each transaction queueing up in line to ensure that the transactions complete in their entirety before another one begins. This does not mean two transactions cannot happen simultaneously; multiple transactions can happen simultaneously as long as they have no possibility of impacting each other.</details>

<details><summary>Durability</summary>Durability ensures that changes made to the database (transactions) that are successfully committed will survive permanently, even in the case of system failures. This ensures that the data within the database will not be corrupted by service outages, crashes or other cases of failure.</details>

> **Reference**: [_ACID Explained: Atomic, Consistent, Isolated & Durable_ by Stephen Watts from **bmc.com**](https://www.bmc.com/blogs/acid-atomic-consistent-isolated-durable/)

# Data warehouse
A data warehouse is a data storage system that aggregates data from multiple (possibly disparate) sources into a single central and consistent data store. Data warehouses help prepare data for data analytics, business intelligence (BI), data mining, machine learning (ML) and artificial intelligence (AI) initiatives.

> **Reference**: [_What is a data warehouse?_ by Jim Holdsworth and Matthew Kosinski from **IBM.com**](https://www.ibm.com/topics/data-warehouse)