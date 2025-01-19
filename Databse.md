# ACID Properties
* ACID is an acronym that refers to the set of 4 key properties that define a transaction: Atomicity, Consistency, Isolation, and Durability.
### Atomicity
* Atomicity defines the data as atomic. This means that if any operation is performed on the data, it should either be performed completely or not be executed at all.
* There is no midway i.e. transactions do not occur partially. Each transaction is considered as one unit and either run to completion or is not executed at all.
### Consistency
* Consistency ensures that a transaction takes the database from one consistent state to another consistent state.
* Consistency ensures that a database remains in a valid state before and after a transaction.
* After each transaction, consistency is checked to ensure nothing has gone wrong.
### Isolation
* Isolation is defined as a state of separation when multiple transactions occur concurrently.
* Isolation guarantees particular transaction will not be visible to any other transaction until that change in that transaction is written to memory or has been committed. 
* Isolation ensures that when multiple transactions run at the same time, the result will be the same as if they were run one after another in a specific order.
### Durability
* Durability ensures the permanency of Data by providing recovery options even in case of system failure or crashes.
* Durability promises that updates and modifications to the database are stored in and written to disk when a transaction is completed.

# CAP Threom
# Joins
* A JOIN clause is used to combine data or rows from one or more tables based on a common field between them
* There are seven types of joins they are: INNER JOIN, LEFT JOIN, RIGHT JOIN, FULL OUTER JOIN, NATURAL JOIN, CROSS JOIN, SELF JOIN.
### Inner Join
Inner Join returns rows from both tables where there is a match followed by a specified join condition.

![](https://tembo.io/_astro/inner-join.B4pP8qsy_Z2q4xDc.webp)

produces only the set of records that match in both Table A and Table B.

### Left Join
Left Join return all rows from left table and matching rows from the right table. Null values will be returned for the right table if there are no matching rows.

![](https://tembo.io/_astro/left-join.COVU_UQS_Ze8XHF.webp)

It produces a complete set of records from Table A, with the matching records in Table B. If there is no match, the right side will contain null.

### Right Join
Right Join return all rows from right table and matching rows from the left table. Null values will be returned for the left table if there are no matching rows.

![](https://tembo.io/_astro/right-join.BzEzv8my_Z1GAL3O.webp)

It produces a complete set of records from Table B, with the matching records in Table A. If there is no match, the left side will contain null.

### Full Outer Join

Full Outer Join returns all the rows where there is match in both the left and the right table. Null values are returned for the columns where there is not any match.

![](https://tembo.io/_astro/full-outer-join.Cm9Or3zm_gUPIz.webp)

It produces the set of all records in Table A and Table B, with matching records from both sides where available. If there is no match, the missing side will contain null.

### Natural Join

A natural join is a join that creates an implicit join based on the same column names in the joined tables.

### Cross Join

Cross Join returns the result of Cartesian multiplication between the both tables. It combines the every row of left table to the every row of right table and gives the final result.

![](https://tembo.io/_astro/cross-join.q4blTKZt_zMgh4.webp)

It does not require any condition.
### Self Join
Self Join joins the table with itself and returns the final output. Self joins is commonly used to compare rows within the same table.

# Aggregations, Filters in queries



