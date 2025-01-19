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
Left Join returns all rows from the left table and matching rows from the right table. Null values will be returned for the right table if there are no matching rows.

![](https://tembo.io/_astro/left-join.COVU_UQS_Ze8XHF.webp)

It produces a complete set of records from Table A, with the matching records in Table B. If there is no match, the right side will contain null.

### Right Join
Right Join returns all rows from the right table and matching rows from the left table. Null values will be returned for the left table if there are no matching rows.

![](https://tembo.io/_astro/right-join.BzEzv8my_Z1GAL3O.webp)

It produces a complete set of records from Table B, with the matching records in Table A. If there is no match, the left side will contain null.

### Full Outer Join

Full Outer Join returns all the rows where there is a match in both the left and the right table. Null values are returned for the columns where there is no match.

![](https://tembo.io/_astro/full-outer-join.Cm9Or3zm_gUPIz.webp)

It produces the set of all records in Table A and Table B, with matching records from both sides where available. If there is no match, the missing side will contain null.

### Natural Join

A natural join is a join that creates an implicit join based on the same column names in the joined tables.

### Cross Join

Cross Join returns the result of Cartesian multiplication between both tables. It combines every row of the left table with every row of the right table and gives the final result.

![](https://tembo.io/_astro/cross-join.q4blTKZt_zMgh4.webp)

It does not require any condition.
### Self Join
Self Join joins the table with itself and returns the final output. Self joins is commonly used to compare rows within the same table.

# Aggregations, Filters in queries

### Aggregate Functions
* Aggregate functions perform a calculation on a set of rows and return a single row.
* Aggregate functions are often used with the GROUP BY clause in the SELECT statement.
* GROUP BY clause divides the result set into groups of rows and the aggregate function performs a calculation on each group.
* PostgreSQL provides various Aggregate functions like SUM, COUNT, MIN, MAX, AVG, BOOL_OR, BOOL_AND, ARRAY_AGG, and STRING_AGG.
 ##### SUM()
  Calculates the total sum of numeric values in a column.
##### MIN()
  Returns the minimum value in a column.
##### MAX()
  Returns the maximum value in a column.
##### COUNT()
  Counts the number of rows in each group. It can also count non-null values in a specific column.
##### AVG()
  Calculates the average value of a numeric column.
##### BOOL_OR()
  Returns true if any value is true in a column.
##### BOOL_ALL()
  Returns true if all values are true otherwise returns false in a column.
##### ARRAY_AGG()
   Returns an array of the values in a column. We can use the ORDER BY clause in this function.
##### STRING_AGG()
  Concatenates values in a column into a single string, optionally separated by a delimiter. We can use the ORDER BY clause in this function.
### Filters
Filters are used to restrict the rows returned by a query based on specific conditions. There are various types of filters they are as follows
`
##### WHERE Clause:
The WHERE clause is used to filter rows based on a condition before any grouping or aggregation. we can't use the aggregate functions inside WHERE CLAUSE.
##### HAVING Clause
The HAVING clause is used to filter rows after aggregation, it filters groups of data that have been aggregated with GROUP BY. we can use aggregate functions inside WHERE CLAUSE.
##### DISTINCT
The DISTINCT keyword removes duplicate rows from the result set. It is used to filter unique records based on one or more columns.
##### LIMIT and OFFSET
The LIMIT clause restricts the number of rows returned, and OFFSET skips a specific number of rows.
##### IN Operator
The IN operator is used to filter rows where a column value matches any value in a list.
##### BETWEEN Operator
The BETWEEN operator filters rows where the column value is within a specified range.
##### LIKE and ILIKE
The LIKE operator is used to filter rows based on pattern matching, and ILIKE does it case-insensitively.
##### IS NULL / IS NOT NULL
Filters rows with or without NULL values in a column.
##### EXISTS
The EXISTS operator is used to filter based on the existence of a subquery that returns rows.
##### ARRAY Filtering
PostgreSQL supports filtering based on array data types using ANY, ALL, and array functions.
##### FILTER with Aggregate Functions
FILTER clause with aggregate functions to apply a filter condition directly within the aggregation.

# Normalization
Normalization is the key way to avoid database anomalies and redundancy.
##### The First Normal Form(1NF)
* 1NF requires that each column in a table contains atomic values, meaning each value is indivisible. 
* It eliminates repeating groups and ensures that each row and column contains only one value.
##### Second Normal Form(2NF)
* 2NF builds upon 1NF by addressing functional dependencies.
* It ensures that non-key attributes depend on the entire primary key.
##### Third Norma Form(3NF)
* 3NF further updates the normalization process by addressing transitive dependencies. 
* It ensures that non-key attributes depend solely on the primary key and not on other non-key attributes. 
* To achieve 3NF, any transitive dependencies are eliminated by splitting the table into additional tables.
##### Boyce-Codd normal form (3.5NF)
* It must be in first, second, and third normal form.
* Every value in a table should be dependent on every candidate key.

# Indexes
* Indexes are special lookup tables that the database search engine can use to speed up data retrieval. 
* Simply put, an index is a pointer to data in a table.
* An index in a database is very similar to an index in the back of a book.
* An index helps to speed up SELECT queries and WHERE clauses and it slows down data input, with UPDATE and INSERT statements.
* Indexes can be created or dropped with no effect on the data.
### Index Types
* PostgreSQL provides several index types: B-tree, Hash, GiST, SP-GiST, and GIN. Each Index type uses a different algorithm that is best suited to different types of queries.
* By default, the CREATE INDEX command creates B-tree indexes, which fit the most common situations.
* 
##### Single-Column Indexes
A single-column index is created based on only one table column.

`    CREATE INDEX index_name ON table_name (column_name);    `

##### Multicolumn Indexes
A multicolumn index is defined on more than one column of a table. 

`    CREATE INDEX index_name
ON table_name (column1_name, column2_name); `
##### Unique Indexes
* Unique indexes are used not only for performance but also for data integrity. 
* A unique index does not allow any duplicate values to be inserted into the table.

`    CREATE UNIQUE INDEX index_name
on table_name (column_name);    `
##### Partial Indexes
* A partial index is an index built over a subset of a table; the subset is defined by a conditional expression (called the predicate of the partial index). 
* The index contains entries only for those table rows that satisfy the predicate. 

`    CREATE INDEX index_name
on table_name (conditional_expression);    `

##### Implicit Indexes
* Implicit indexes are indexes that are automatically created by the database server when an object is created.
* Indexes are automatically created for primary key constraints and unique constraints.

##### DROP INDEX Command
* An index can be dropped using the PostgreSQL DROP command. 
* Care should be taken when dropping an index because performance may be slowed or improved.
* 
`    DROP INDEX index_name;    `

# Transactions
* A transaction is a logical unit of work that contains one or more than one SQL statement where either all statements will succeed or all will fail. 
* The SQL statements are NOT visible to other user sessions, and if something goes wrong, it won’t affect the database.

### Transaction Control
##### BEGIN
* The BEGIN keyword is used to start a transaction block.  
* All the SQL statements that follow BEGIN will be executed as a single transaction unit. 
* The transaction block will end after it reaches the COMMIT or ROLLBACK keywords, which we need to provide explicitly.
##### COMMIT
The COMMIT keyword saves changes to the database. 
##### ROLLBACK 
ROLLBACK undoes the changes that were issued in the transaction block.
##### SAVEPOINT
* SAVEPOINT is a boundary defined within a transaction that allows for a partial rollback.
* It gives the user the ability to roll the transaction back to a certain point without rolling back the entire transaction.
##### END TRANSACTION
End transaction will end the transaction as a single unit of work.
# Trigers
* A PostgreSQL trigger is a powerful tool that allows automatic invocation of a function whenever a specified event occurs on a table. 
* Events that can trigger a function include INSERT, UPDATE, DELETE, or TRUNCATE. 
* Triggers help maintain data integrity and automate complex database operations.
### Types of Triggers
##### Row-Level Triggers
Invoked once for each row affected by the event. For example, an ‘UPDATE' statement affecting 20 rows will invoke the row-level trigger 20 times.
##### Statement-Level Triggers
Invoked once per SQL statement, regardless of the number of rows affected.
### Timing of Trigger Invocation
##### BEFORE Trigger
Invoked before the event occurs. Can be used to modify or skip the operation.
##### AFTER Trigger
Invoked after the event occurs. All changes made by the event are available to the trigger.





