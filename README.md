# Mastering .NET 🚀

A structured, roadmap-driven journey to master the .NET ecosystem at Senior/Lead level.

## Why This Repo Exists

This is not a toy project. It's a deliberate learning path built by applying two professional .NET roadmaps to a real-world application rewrite:

- **[Anton Martyniuk's .NET Roadmap 2026](ROADMAP.md#anton-martyniuks-net-roadmap-2026)** — comprehensive .NET ecosystem, from ASP.NET Core to cloud-native
- **[Julio Casal's .NET Backend Developer Roadmap](ROADMAP.md#julio-casals-net-backend-developer-roadmap)** — focused backend and infrastructure skills

Every commit, every pattern, every library choice is mapped to a specific roadmap item.

## Structure

```
MasteringDotNet/
├── Project1/          # Coursatee — learning vehicle
│   ├── Api/           # ASP.NET Core Web API
│   ├── Application/   # CQRS, validation, use cases
│   ├── Domain/        # Entities, value objects, business rules
│   └── Infrastructure/# EF Core, external services, caching
├── ROADMAP.md         # Both roadmaps with coverage tracking
├── CHECKLIST.md       # Sequential learning checklist
└── README.md          # This file
```

## The Approach

1. **Architecture-first** — Clean Architecture with vertical slices
2. **Patterns follow need** — No pattern is added for its own sake
3. **Tested at every step** — Unit, integration, and architecture tests
4. **Observable by default** — OpenTelemetry, structured logging, health checks

## Status

| Phase | Status |
|---|---|
| Foundation (structure, DI, build) | ✅ Complete |
| Domain Layer | 🔜 Next |
| Application Layer | ⏳ |
| Infrastructure & Persistence | ⏳ |
| API & Security | ⏳ |
| Testing | ⏳ |
| Observability | ⏳ |
| Caching & Messaging | ⏳ |
| CI/CD & Deployment | ⏳ |

## How to Use This

Each project folder (`Project1/`, `Project2/`, ...) represents a distinct application built to progressively deeper roadmap coverage. Start with `Project1/` and work through the [CHECKLIST.md](CHECKLIST.md).
