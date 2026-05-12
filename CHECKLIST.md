# Learning Checklist

Each item maps to one or more roadmap bullets. Check off as you complete them.

---

## Phase 1: Foundation 🔧

### 1.1 Solution Structure
- [ ] Create multi-project solution with Clean Architecture layers
- [ ] Configure `Directory.Build.props` for centralized MSBuild properties
- [ ] Set up project references respecting dependency flow (Domain ← Application ← Infrastructure ← Api)
- [ ] Build with zero warnings (`TreatWarningsAsErrors = true`)

### 1.2 Domain Layer
- [ ] Define entities as sealed records/classes with private constructors
- [ ] Implement value objects with invariant validation (`Money`, `DateRange`)
- [ ] Use factory methods (`static Create(...)`) instead of public constructors
- [ ] Enums in dedicated folder, semantically named
- [ ] No external dependencies (no EF, no ASP.NET)

### 1.3 Application Layer
- [ ] Define repository interfaces (not implementations)
- [ ] Define service interfaces
- [ ] Implement CQRS with MediatR (Commands, Queries, Handlers)
- [ ] Add FluentValidation for every command/query
- [ ] Add pipeline behaviors (logging, validation, transaction)
- [ ] Use Mapperly for DTO mapping (source-generated)

### 1.4 Infrastructure & Persistence
- [ ] Set up EF Core DbContext
- [ ] Map domain entities using Fluent API (IEntityTypeConfiguration)
- [ ] Create and run initial migration
- [ ] Implement repository pattern
- [ ] Add Dapper for read-optimized queries

### 1.5 API Layer
- [ ] Configure Program.cs with top-level statements
- [ ] Set up middleware pipeline (error handling, Serilog, CORS)
- [ ] Implement controllers or FastEndpoints
- [ ] Configure Swagger/OpenAPI
- [ ] Add health checks endpoint
- [ ] Configure JWT authentication and authorization

---

## Phase 2: Production Quality 📊

### 2.1 Logging & Observability
- [ ] Replace log4net with Serilog
- [ ] Configure structured logging (JSON format)
- [ ] Add OpenTelemetry for distributed tracing
- [ ] Export traces to Jaeger
- [ ] Configure Prometheus metrics endpoint
- [ ] Set up health checks UI

### 2.2 Testing
- [ ] Write unit tests with xUnit
- [ ] Use NSubstitute for mocking
- [ ] Use Bogus for fake data generation
- [ ] Write integration tests with WebApplicationFactory
- [ ] Use TestContainers for real database in tests
- [ ] Write architecture tests (layer dependencies, naming conventions)
- [ ] Add snapshot testing with Verify

### 2.3 Error Handling
- [ ] Implement global exception middleware
- [ ] Use ProblemDetails for API errors
- [ ] Implement validation error response

### 2.4 Validation & Mapping
- [ ] FluentValidation with automatic validation pipeline
- [ ] Mapperly for compile-time mapping
- [ ] Custom DTOs per use case (not shared)

---

## Phase 3: Advanced Patterns 🧠

### 3.1 CQRS & MediatR
- [ ] Separate read and write models
- [ ] Implement MediatR pipeline behaviors
- [ ] Add transaction behavior per command
- [ ] Implement domain events

### 3.2 Caching
- [ ] Add Redis via StackExchange.Redis
- [ ] Implement OutputCache for response caching
- [ ] Implement HybridCache for distributed + in-memory
- [ ] Cache invalidation strategies

### 3.3 Background Jobs
- [ ] Add Hangfire for background processing
- [ ] Move email sending to background job
- [ ] Move report generation to background job
- [ ] Add Hangfire dashboard with auth

### 3.4 Resilience
- [ ] Add Polly retry policies for HTTP calls
- [ ] Add circuit breaker pattern
- [ ] Implement timeout policies
- [ ] Use Microsoft Resilience library

### 3.5 Messaging
- [ ] Add MassTransit with RabbitMQ or Azure Service Bus
- [ ] Implement publish-subscribe for domain events
- [ ] Implement outbox pattern for reliable messaging
- [ ] Implement saga pattern for long-running workflows

---

## Phase 4: Cloud & DevOps ☁️

### 4.1 Containerization
- [ ] Write Dockerfile for API
- [ ] Write docker-compose with SQL Server, Redis, Seq
- [ ] Add health checks for container orchestration

### 4.2 CI/CD
- [ ] Create GitHub Actions workflow
- [ ] Build → Test → Docker image → Push steps
- [ ] Add quality gates (code coverage, linting)

### 4.3 API Gateway
- [ ] Add YARP reverse proxy
- [ ] Configure routing, rate limiting, load balancing

### 4.4 Infrastructure as Code
- [ ] Write Terraform configuration for Azure/AWS
- [ ] Manage secrets via Azure Key Vault

### 4.5 Cloud Deployment
- [ ] Deploy to Azure Container Apps or AKS
- [ ] Configure auto-scaling
- [ ] Set up monitoring dashboards

---

## Validation Criteria

A skill is "mastered" when you can:

1. **Explain it** — to a junior developer in 2 minutes
2. **Defend the choice** — state when NOT to use it
3. **Write it from scratch** — without copying from memory
4. **Test it** — prove it works in CI

---

## Resources

- [Anton Martyniuk's .NET Roadmap 2026](https://antondevtips.com)
- [Julio Casal's .NET Backend Developer Roadmap](https://juliocasal.com)
- [Microsoft .NET Architecture Guides](https://learn.microsoft.com/en-us/dotnet/architecture/)
- [Clean Architecture by Jason Taylor](https://github.com/jasontaylordev/CleanArchitecture)
- [Modular Monolith by Milan Jovanovic](https://www.milanjovanovic.tech/)
