## Architecture Preference

This project prefers a **lightweight Hexagonal Architecture** (Ports and Adapters) approach.

### Core Principles

- Domain logic must be isolated from external dependencies
- Dependencies point inward (from adapters to domain)
- Use interfaces (ports) to define boundaries between layers

## Directory Structure

```
src/
├── domain/           # Core business logic
├── application/      # Application services / Use cases
└── infrastructure/   # External adapters
```

## Implementation Guidelines

### Domain Layer

- No external dependencies
- Pure business logic only
- Define domain exceptions here

### Application Layer

- Orchestrates domain objects
- Defines port interfaces
- Implements use cases

### Infrastructure Layer

- Implements port interfaces
- Handles external communication
- Contains framework-specific code

## Testing Strategy

- Domain: Unit tests without mocks
- Application: Unit tests with mocked ports
- Infrastructure: Integration tests
