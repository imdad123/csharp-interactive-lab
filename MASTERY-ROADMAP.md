# C# & T-SQL Mastery Roadmap

## Mission
Build practical, enterprise-level skills with C#, modern .NET, SQL Server, and T-SQL. The goal is not to memorize every feature. It is to understand the concepts used repeatedly and build the ability to design, test, debug, secure, optimize, and maintain real systems.

## Learning principles
1. Learn the problem before the syntax: why was the feature introduced?
2. Master the common 20% first—the concepts used in most day-to-day development.
3. Prefer concise explanations and practical code over unnecessary academic detours.
4. Use one evolving project: HospitalApp.
5. Separate UI/API, application logic, domain rules, and infrastructure.
6. Test behavior at the correct level: unit, integration, and end-to-end when appropriate.
7. Treat SQL as an engineering skill: correctness, data integrity, performance, and operations matter.

## Roadmap at a glance
| Track | Outcome |
|---|---|
| C# foundations | Readable, safe, maintainable C# |
| Object-oriented design | Model business behavior with appropriate abstractions |
| Modern C# | Use LINQ, generics, delegates, events, async, and modern language features |
| .NET platform | Understand runtime, assemblies, DI, configuration, and logging |
| Testing | Verify isolated behavior and real infrastructure integration |
| ASP.NET Core | Build secure, maintainable HTTP APIs |
| Data access | Use ADO.NET and EF Core appropriately |
| T-SQL | Query, modify, model, and protect relational data |
| SQL performance | Diagnose plans, indexes, blocking, and slow queries |
| Enterprise operations | Deploy, monitor, back up, recover, and maintain applications |

## Suggested sequence
### Phase 1 — C# core
Types, variables, operators, conditions, loops, methods, arrays, collections, strings, exceptions, classes, objects, properties, constructors, and interfaces.

### Phase 2 — Professional C#
OOP principles, composition, inheritance, polymorphism, generics, delegates, events, LINQ, nullable reference types, records, pattern matching, async/await, cancellation, and resource management.

### Phase 3 — SQL Server and T-SQL
Relational design, SELECT, filtering, joins, aggregation, subqueries, CTEs, window functions, data modification, transactions, stored procedures, views, functions, indexes, execution plans, and security.

### Phase 4 — Application engineering
ADO.NET, EF Core, dependency injection, configuration, logging, validation, DTOs, service boundaries, and error handling.

### Phase 5 — Testing and ASP.NET Core
Unit and integration tests, mocks and fakes, Kestrel, middleware, routing, Minimal APIs, authentication, authorization, and API documentation.

### Phase 6 — Enterprise practice
Build and refine HospitalApp, optimize SQL, handle concurrency, add reporting, create deployment workflows, and document operations.

## Definition of done
You should be able to explain a concept and the problem it solves; choose an implementation and explain trade-offs; keep business logic out of UI event handlers; design tables with keys and constraints; write readable SQL and diagnose inefficient queries; test business rules without a real form; test API/database integration; debug using logs and diagnostics; and deliver a feature from schema through API, tests, and deployment.