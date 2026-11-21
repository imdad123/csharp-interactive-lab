# T-SQL & SQL Server Mastery

The goal is to write correct, maintainable, secure, and performant SQL Server code—and understand how to operate it safely.

## 1. Relational database foundations
- Tables, rows, columns, schemas.
- Primary keys, foreign keys, unique constraints.
- Relationships: one-to-one, one-to-many, many-to-many.
- NULL semantics.
- Data types: integer, decimal/numeric, money considerations, date/time, character, Unicode, binary, uniqueidentifier.
- Identity columns and sequences.
- Defaults, check constraints, computed columns.
- Normalization and practical denormalization.
- Naming conventions and schema organization.

Practice: design Hospital, Department, Doctor, Patient, Appointment, Room, Bed, Invoice, and Payment tables with keys and constraints.

## 2. Core querying
- SELECT, aliases, expressions.
- WHERE, AND, OR, NOT, IN, BETWEEN, LIKE.
- NULL checks with IS NULL / IS NOT NULL.
- ORDER BY, TOP, DISTINCT.
- CASE, COALESCE, ISNULL, NULLIF.
- String, date, numeric, and conversion functions.
- CAST, CONVERT, TRY_CAST, TRY_CONVERT.
- Correct date-range filtering; prefer half-open ranges for datetime intervals.

## 3. Joins and aggregation
- INNER JOIN, LEFT JOIN, RIGHT JOIN, FULL JOIN.
- CROSS JOIN and self joins.
- Join predicates versus filters in WHERE.
- One-to-many duplication and aggregate correctness.
- GROUP BY, HAVING.
- COUNT, COUNT_BIG, SUM, AVG, MIN, MAX.
- Conditional aggregation with SUM(CASE...).
- UNION, UNION ALL, INTERSECT, EXCEPT.

Practice: doctor-wise appointments, department-wise patient counts, bed occupancy, and monthly collection reports.

## 4. Subqueries, CTEs, and window functions
- Scalar and correlated subqueries.
- EXISTS and NOT EXISTS.
- Common Table Expressions (CTEs).
- Recursive CTEs for hierarchies.
- Window functions: OVER, PARTITION BY, ORDER BY.
- ROW_NUMBER, RANK, DENSE_RANK, NTILE.
- LAG, LEAD.
- Running totals and moving aggregates.
- Window frames and ROWS versus RANGE.
- Top-N-per-group patterns.

Practice: latest appointment per patient, running daily revenue, and rank doctors by completed visits.

## 5. Data modification and safe operations
- INSERT, multi-row inserts, INSERT...SELECT.
- UPDATE and DELETE with safe predicates.
- OUTPUT clause.
- MERGE awareness and concurrency caveats; explicit update/insert patterns may be safer.
- TRUNCATE TABLE versus DELETE.
- IDENTITY_INSERT.
- Transactions for multi-step business operations.
- Preview affected rows before destructive changes.
- Use constraints to protect data integrity.

## 6. Programmability
- Stored procedures and parameters.
- Input and output parameters.
- Return codes.
- Local variables and control flow.
- IF, WHILE, TRY...CATCH.
- THROW and RAISERROR awareness.
- Scalar and table-valued user-defined functions.
- Views and indexed views awareness.
- Temporary tables (#temp) and table variables.
- Table-valued parameters.
- Dynamic SQL with sp_executesql and parameterization.
- Avoid SQL injection; never concatenate untrusted input into executable SQL.
- SCOPE_IDENTITY() and generated key retrieval.

Practice: create stored procedures for appointment booking, invoice posting, payment collection, and bed allocation.

## 7. Transactions and concurrency
- ACID properties.
- BEGIN TRAN, COMMIT, ROLLBACK.
- TRY...CATCH transaction patterns and XACT_STATE().
- Isolation levels: Read Uncommitted, Read Committed, Repeatable Read, Serializable, Snapshot.
- Read Committed Snapshot Isolation (RCSI).
- Dirty reads, non-repeatable reads, phantom reads.
- Locks, blocking, deadlocks.
- Deadlock graphs and retry strategy.
- Optimistic concurrency and rowversion.
- Keep transactions short and consistent.

Practice: ensure two users cannot allocate the same bed or over-collect an invoice.

## 8. Indexing and query performance
- Heap versus clustered index.
- Nonclustered indexes and included columns.
- Composite index key order.
- Unique and filtered indexes.
- Covering indexes.
- Index selectivity and cardinality.
- SARGable predicates.
- Avoid functions on indexed filter columns where possible.
- Implicit conversions.
- Statistics and cardinality estimation.
- Actual versus estimated execution plans.
- Scans, seeks, key lookups, joins, sorts, spools.
- Nested Loops, Hash Match, Merge Join.
- Parameter sniffing and parameter-sensitive plans.
- Query Store and plan comparison.
- SET STATISTICS IO, TIME ON.
- Evidence-based index maintenance.

## 9. SQL Server objects and administration
- Databases, schemas, users, roles, permissions.
- Backup and restore: full, differential, log.
- Recovery models: simple, full, bulk-logged.
- Point-in-time recovery prerequisites.
- SQL Server Agent jobs and schedules.
- Maintenance plans versus scripted maintenance.
- Integrity checks with DBCC CHECKDB.
- Database files, filegroups, growth settings.
- Monitoring sessions, requests, waits, and blocking.
- SQL Server logs and error diagnosis.
- Import/export and data migration basics.

## 10. Advanced and applied SQL Server
- Dynamic pivoting and PIVOT / UNPIVOT.
- JSON support: FOR JSON, OPENJSON, JSON_VALUE.
- Temporal tables awareness.
- Change Tracking and CDC overview.
- Full-text search awareness.
- Service Broker awareness for asynchronous database messaging.
- Linked servers and distributed query risks.
- Partitioning concepts.
- Row-level security and data masking awareness.
- Encryption options and secure handling of sensitive patient data.
- High availability and disaster recovery concepts.

## 11. Reporting and business queries
- Date dimensions and calendar tables.
- Month-wise and day-wise summaries.
- Opening, debit, credit, closing balance patterns.
- Trial balance and ledger-style queries.
- Outstanding invoices and aging.
- Payment reconciliation.
- Occupancy and utilization reports.
- Parameterized reporting procedures.
- Pagination and stable ordering.

## 12. SQL coding standards
- Use explicit column lists; avoid SELECT * in production interfaces.
- Schema-qualify objects, e.g. dbo.TableName.
- Use consistent aliases and readable formatting.
- Use parameters for values.
- Handle NULL deliberately.
- Avoid cursors unless set-based alternatives are unsuitable.
- Avoid unnecessary scalar UDFs in hot paths.
- Design indexes from measured query patterns.
- Test procedures with boundary cases and concurrent calls.
- Include transaction and error-handling strategy for multi-step writes.