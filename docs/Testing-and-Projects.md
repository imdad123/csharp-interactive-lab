# Testing & Project Practice

## 1. Why testing matters
Testing protects behavior as the application changes. It is not limited to unit tests, and developers should not test only individual functions. Choose the test level that proves the behavior you care about.

## 2. Unit testing
- Test one unit of behavior in isolation.
- Arrange, Act, Assert.
- Test public behavior, not private implementation details.
- Test normal cases, boundary cases, and invalid input.
- Keep tests deterministic and independent.
- Use meaningful names describing condition and expected result.
- Avoid tests that merely repeat the implementation.

HospitalApp examples: patient validation, appointment scheduling rules, invoice totals, payment allocation, and bed availability decisions.

## 3. DTOs and testability
When data arrives from a form, API, or UI, map it into a request DTO or command. Test the business method using the DTO directly; the test should not need to open a form or make an HTTP request.

Keep responsibilities separate:
- UI/API: receive and validate the request shape.
- Application service: coordinate the use case.
- Domain logic: enforce business rules.
- Infrastructure: persist and retrieve data.

## 4. Test doubles
- Stub: supplies controlled input.
- Fake: lightweight working implementation, such as an in-memory repository.
- Mock: verifies an interaction when that interaction is part of the contract.
- Avoid mocking every dependency; prefer real objects for simple domain logic.

## 5. Integration testing
Integration tests verify components working together with real or realistic infrastructure.

Examples:
- API endpoint + dependency injection + database.
- EF Core mapping + SQL Server provider.
- Stored procedure + SQL Server behavior.
- Authentication middleware + authorization policy.
- Transaction rollback and concurrency behavior.

Use a dedicated test database or isolated containers/environments. Never run destructive integration tests against production data.

## 6. API testing
- Success response and correct status code.
- Invalid request and validation response.
- Missing resource.
- Unauthorized and forbidden access.
- Duplicate request and conflict behavior.
- Pagination and filtering.
- Cancellation and timeout behavior.
- Database failure and safe error response.

## 7. HospitalApp project backlog

### Core domain
- Patient registration and search.
- Doctor and department management.
- Appointment booking and cancellation.
- Appointment conflict rules.
- Room and bed allocation.
- Invoice creation and payment collection.

### SQL Server
- Normalized schema and constraints.
- Stored procedures for important workflows.
- Transactions for invoice posting and bed allocation.
- Reports using joins, CTEs, and window functions.
- Indexes and execution plan analysis.

### .NET application
- DTOs and validation.
- Service/use-case layer.
- ADO.NET and EF Core data access.
- Minimal APIs and consistent responses.
- Authentication, roles, and policies.
- Logging and exception handling.

### Quality
- Unit tests for domain rules.
- Integration tests for persistence and APIs.
- Concurrency tests for booking/allocation.
- Performance tests for critical reports.
- Deployment checklist and backup/restore rehearsal.

## 8. Definition of done for a feature
- Requirements and edge cases are clear.
- Database constraints protect important invariants.
- Business logic is not trapped in UI event handlers or endpoint lambdas.
- Input is validated and errors are meaningful.
- SQL is parameterized.
- Appropriate unit and integration tests pass.
- Logs support diagnosis without exposing secrets or sensitive patient data.
- Performance is checked for important queries.
- The feature is documented.