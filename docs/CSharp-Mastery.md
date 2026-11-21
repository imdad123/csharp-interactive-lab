# C# Mastery

A practical sequence for professional C# development. Focus on understanding, usage, and trade-offs.

## 1. Language foundations
- Program structure, namespaces, using directives, top-level statements.
- Variables, constants, var, type inference.
- Value types and reference types; stack/heap as a simplified mental model, not an absolute rule.
- Built-in types, numeric conversions, casting, parsing, TryParse.
- Strings, interpolation, formatting, StringBuilder.
- Operators, boolean logic, null checks, conditional expressions.
- if, switch, switch expressions, pattern matching.
- for, foreach, while, do while, break, continue.
- Methods, parameters, return values, optional and named arguments, ref, out, in.
- Arrays, multidimensional arrays, ranges and indexes.

Practice: build a console patient-registration flow with validation, menu choices, and formatted output.

## 2. Methods and reusable code
- Method signatures, overloads, scope, local variables.
- Static versus instance members.
- Parameter passing and when ref/out are justified.
- Expression-bodied members and local functions.
- Extension methods.
- Separation of input/output from business logic.

Professional rule: methods should have clear responsibilities. Pass input as parameters and return results rather than reading directly from UI controls.

## 3. Collections and data handling
- List<T>, Dictionary<TKey,TValue>, HashSet<T>.
- Queue<T>, Stack<T>.
- IEnumerable<T> and iteration.
- ICollection<T>, IList<T>, IReadOnlyCollection<T>, IReadOnlyList<T>.
- Generic versus non-generic collections.
- Equality, comparers, sorting, and searching.
- Choose collections based on lookup, ordering, uniqueness, and mutation needs.

Practice: store patients by ID, prevent duplicate IDs, and search by registration number.

## 4. Object-oriented programming
- Classes and objects: state plus behavior.
- Fields, properties, auto-properties, backing fields.
- Constructors, constructor chaining, object initializers.
- Encapsulation and invariants.
- Access modifiers: public, private, protected, internal, protected internal, private protected.
- static, readonly, const.
- Inheritance and base classes.
- Overriding, virtual/abstract members, polymorphism.
- Interfaces and interface-based design.
- Composition versus inheritance.
- Sealed classes and members.
- Records and value-based equality.
- Structs and when value types are appropriate.
- object, ToString, Equals, GetHashCode.

Practice: model Patient, Doctor, Appointment, Department, and Billing concepts. Keep validation rules close to domain behavior.

## 5. Exceptions and robust code
- What exceptions represent and why they are not ordinary control flow.
- try, catch, finally.
- Catch specific exception types.
- Throwing exceptions; preserve stack traces by rethrowing correctly.
- Custom exceptions only when they add meaningful context.
- Exception filters.
- Validation errors versus unexpected system failures.
- Logging at the correct boundary.
- Avoid swallowing exceptions or exposing internal details to users.

Practice: handle invalid input, missing records, and database failures differently.

## 6. Generics and type-safe design
- Why generics exist: reusable algorithms without losing compile-time type safety.
- Generic classes, methods, interfaces, and constraints.
- where constraints.
- Generic collections.
- Covariance and contravariance (out/in) at an applied level.
- Nullable reference types and nullability annotations.

Practice: create a reusable result or paged-result model only where it improves clarity.

## 7. Delegates, events, and lambdas
- Delegates solve the problem of passing behavior as data.
- Delegate declarations and Action, Func, Predicate<T>.
- Lambda expressions.
- Events and publisher/subscriber relationships.
- Subscription and unsubscription.
- EventHandler patterns.
- Closures and captured variables.
- Practical uses in callbacks, UI events, and application notifications.

## 8. LINQ
- Why LINQ exists: consistent querying over in-memory and provider-backed data.
- Query syntax and method syntax.
- Where, Select, SelectMany.
- OrderBy, ThenBy, Distinct.
- First, FirstOrDefault, Single, SingleOrDefault.
- Any, All, Contains.
- Count, Sum, Average, Min, Max.
- GroupBy, Join, GroupJoin.
- Skip, Take, pagination.
- Deferred versus immediate execution.
- IEnumerable<T> versus IQueryable<T>.
- Performance traps: repeated enumeration, premature materialization, and loading too much data.

Practice: filter appointments by doctor, date, status, and department; create daily summaries.

## 9. Asynchronous programming
- Why async exists: waiting for I/O should not block a request or UI thread unnecessarily.
- Task, Task<T>, async, await.
- Async call chains and exception propagation.
- I/O-bound versus CPU-bound work.
- CancellationToken and cooperative cancellation.
- Task.WhenAll and Task.WhenAny.
- Avoid async void except event handlers.
- Avoid .Result and .Wait() in normal async application code.
- Avoid unnecessary Task.Run for I/O.
- Timeouts and cancellation in service calls.

Practice: make repository and API calls asynchronous and pass cancellation tokens through the call chain.

## 10. Modern C# features
- Tuples and named tuple elements.
- Records and with expressions.
- Pattern matching and property patterns.
- Switch expressions.
- Target-typed new.
- Null-coalescing and null-conditional operators.
- Init-only setters and required members.
- File-scoped namespaces and global using directives.
- Span<T> and ReadOnlySpan<T> at an awareness and practical-use level.
- IDisposable, IAsyncDisposable, using, await using.
- Attributes and reflection: metadata, practical uses, and costs.
- yield return and iterator methods.

## 11. Runtime and memory fundamentals
- C# compiler and Roslyn overview.
- IL and assemblies.
- CLR responsibilities.
- JIT compilation and Native AOT overview.
- Garbage collection and generations.
- Managed versus unmanaged resources.
- Stack frames, heap allocations, object references.
- Boxing and unboxing.
- IDisposable for deterministic resource cleanup.
- Basic profiling and allocation awareness.

Learn enough runtime detail to debug and make sound design decisions; do not let implementation trivia delay practical work.

## 12. .NET application foundations
- Solution and project structure.
- SDK-style projects and project files.
- NuGet packages and dependency versions.
- Build, restore, run, publish.
- Environments and configuration providers.
- Options pattern.
- Built-in dependency injection.
- Service lifetimes: transient, scoped, singleton.
- Logging abstractions and structured logging.
- Host and Generic Host.
- Configuration secrets and environment variables.

## 13. Architecture and design
- Separation of concerns.
- DTOs and mapping.
- Domain models versus persistence models.
- Repository pattern: when useful and when redundant.
- Service layer and application use cases.
- Dependency inversion and constructor injection.
- SOLID principles as guidance, not ceremony.
- Clean Architecture concepts and dependency direction.
- Validation and error-result patterns.
- Avoid over-engineering; choose based on actual domain complexity.

## Recommended order
Complete sections 1–5 first. Then collections, generics, LINQ, async, testing, and .NET foundations. Study advanced runtime and architecture topics alongside real project needs.