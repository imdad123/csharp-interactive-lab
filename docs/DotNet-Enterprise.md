# .NET Enterprise Development

## 1. Solution structure
A practical HospitalApp solution can evolve toward:
- HospitalApp.Domain — core entities, value objects, business rules.
- HospitalApp.Application — use cases, interfaces, DTOs, validation.
- HospitalApp.Infrastructure — SQL Server, EF Core, ADO.NET, integrations.
- HospitalApp.Api — ASP.NET Core endpoints, authentication, middleware.
- HospitalApp.Console — early learning interface and manual test harness.
- HospitalApp.Tests — unit tests.
- HospitalApp.IntegrationTests — tests against real infrastructure.

Start smaller when appropriate. Add projects when they create useful boundaries, not merely to follow a diagram.

## 2. ADO.NET
- SqlConnection, SqlCommand, SqlParameter.
- ExecuteReader, ExecuteScalar, ExecuteNonQuery.
- SqlDataReader and forward-only reading.
- DataTable, DataRow, DataSet.
- Parameterized stored procedure calls.
- Connection pooling and disposal.
- Async database methods and cancellation.
- Transactions with SqlTransaction.
- Mapping rows to DTOs.
- Avoid string-concatenated SQL.

Understand ADO.NET even when using EF Core: it explains underlying database interaction and remains useful for specialized queries.

## 3. Entity Framework Core
- DbContext and DbSet<T>.
- Entity configuration and conventions.
- Data annotations versus Fluent API.
- Primary keys, foreign keys, relationships.
- Migrations and database updates.
- Seeding reference data.
- Tracking versus AsNoTracking.
- LINQ translation and IQueryable.
- Projection into DTOs.
- Eager, explicit, and lazy loading; avoid accidental N+1 queries.
- Transactions and concurrency tokens.
- Raw SQL and stored procedure integration.
- Pagination and query performance.
- Context lifetime and dependency injection.

## 4. ASP.NET Core request lifecycle
- WebApplication.CreateBuilder.
- Service registration and dependency injection.
- Kestrel web server.
- Middleware pipeline and ordering.
- Routing and endpoint execution.
- Model binding and validation.
- Filters and endpoint filters.
- Dependency injection into handlers.
- Configuration and environment-specific settings.
- Logging and exception handling middleware.
- OpenAPI generation and Scalar/Swagger-style API exploration.
- Health checks and readiness endpoints.

## 5. Minimal APIs and HTTP
- HTTP methods and status codes.
- Resource-oriented route design.
- MapGet, MapPost, MapPut, MapDelete.
- Route groups and shared metadata.
- Request DTOs and response DTOs.
- Validation and consistent error responses.
- Pagination, filtering, and sorting.
- Cancellation tokens.
- Authentication and authorization.
- CORS, HTTPS, rate limiting.
- API versioning concepts.
- Idempotency for important write operations.

## 6. Security
- Authentication versus authorization.
- Claims, roles, and policies.
- JWT bearer authentication concepts.
- Password hashing and credential storage.
- Secret management and environment variables.
- Input validation and output encoding.
- SQL injection prevention.
- Least-privilege database accounts.
- Protecting patient and financial information.
- Audit trails for sensitive operations.
- Avoid logging secrets or unnecessary personal data.

## 7. Configuration, logging, and operations
- appsettings.json and environment-specific configuration.
- Environment variables and secret stores.
- Options pattern and validation.
- ILogger<T> and structured logging.
- Correlation IDs and request tracing.
- Global exception handling.
- Health checks.
- Metrics and distributed tracing concepts.
- Deployment configuration and connection strings.
- Graceful shutdown and cancellation.

## 8. Application patterns
- DTOs: why UI/API models should not be domain or database models by default.
- Dependency injection and constructor injection.
- Service and use-case boundaries.
- Repository pattern trade-offs with EF Core.
- Unit of Work concepts.
- Validation pipeline.
- Result types and error contracts.
- Domain events and integration events overview.
- Background services and hosted services.
- Caching: memory and distributed cache concepts.
- Resilience: timeout, retry, circuit breaker, and careful retry of non-idempotent operations.

## 9. Practical HospitalApp milestones
1. Console menu and in-memory patient registration.
2. Domain classes and validation rules.
3. Doctor and appointment workflows.
4. SQL Server schema and stored procedures.
5. ADO.NET repository implementation.
6. Unit tests for business rules.
7. EF Core implementation and migrations.
8. Minimal API endpoints.
9. Authentication and role/policy authorization.
10. Integration tests and logging.
11. Reports, pagination, and query optimization.
12. Deployment and operational documentation.