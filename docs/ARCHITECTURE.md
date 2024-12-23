# Architecture Overview

Explain the project's structure, logic, and design.

## High-Level Design

This project follows a **Model-View-Controller (MVC)** architecture.

### Directory Structure

```txt
/src
│
├── /core                     # Core domain logic (DDD)
│   ├── /entities             # Domain entities
│   │   └── User.ts
│   ├── /value-objects        # Domain-specific value objects
│   │   └── Email.ts
│   ├── /aggregates           # Aggregate roots and related entities
│   │   └── UserAggregate.ts
│   ├── /repositories         # Repository interfaces for persistence
│   │   └── UserRepository.ts
│   ├── /services             # Domain services (business logic)
│   │   └── UserService.ts
│   ├── /events               # Domain events and handlers
│   │   ├── UserCreatedEvent.ts
│   │   └── UserCreatedHandler.ts
│   └── /specifications       # Domain specifications
│       └── UserSpecifications.ts
│
├── /application              # Application logic (Use Cases, DTOs)
│   ├── /use-cases            # Application use cases
│   │   └── CreateUserUseCase.ts
│   ├── /dto                  # Data Transfer Objects (DTOs)
│   │   └── CreateUserDTO.ts
│   ├── /interfaces           # Interfaces for service inputs and outputs
│   │   └── IUserService.ts
│   └── /mappers              # Mappers to convert between domain and application layers
│       └── UserMapper.ts
│
├── /infrastructure           # Frameworks, external services, and implementation details
│   ├── /database             # Database interaction implementations (using TypeORM)
│   │   ├── /repositories     # Implementations of repository interfaces
│   │   │   └── UserRepositoryImpl.ts
│   │   ├── /entities         # TypeORM entities
│   │   │   └── UserEntity.ts
│   │   └── /migrations       # Database migrations
│   │       └── CreateUsersTable.ts
│   ├── /config               # Configuration files (e.g., environment variables)
│   │   └── data-source.ts    # TypeORM data source configuration
│   ├── /services             # External service implementations (e.g., API clients, cloud services)
│   │   └── EmailService.ts
│   ├── /adapters             # Adapter implementations for external systems (e.g., file storage, messaging)
│   │   └── S3Adapter.ts
│   └── /utils                # Infrastructure-specific utility functions
│       └── Logger.ts
│
├── /presentation             # Presentation layer (API, CLI, UI)
│   ├── /rest                 # RESTful API
│   │   ├── /controllers      # REST controllers
│   │   │   └── UserController.ts
│   │   ├── /middlewares      # Middlewares for RESTful API request handling
│   │   │   └── AuthMiddleware.ts
│   │   └── /routes           # RESTful API routes
│   │       └── UserRoutes.ts
│   ├── /graphql              # GraphQL API
│   │   ├── /resolvers        # GraphQL resolvers
│   │   │   └── UserResolver.ts
│   │   ├── /middlewares      # Middlewares for GraphQL request handling
│   │   │   └── GraphQLAuthMiddleware.ts
│   │   └── /schemas          # GraphQL schema definitions
│   │       └── UserSchema.ts
│   └── /cli                  # Command-Line Interface (CLI)
│       ├── /commands         # CLI commands
│       │   └── CreateUserCommand.ts
│       └── /handlers         # CLI command handlers
│           └── CreateUserHandler.ts
│
├── /shared                   # Shared modules, utilities, and types
│   ├── /utils                # Utility functions used across the application
│   │   └── HashUtils.ts
│   ├── /types                # Shared TypeScript types
│   │   └── CustomTypes.ts
│   └── /constants            # Shared constants
│       └── AppConstants.ts
│
└── index.ts                  # Entry point of the application
```

### Design Patterns

- **Dependency Injection**: Used to decouple services.
- **Singleton**: Applied for shared configurations and instances.

## Flow Diagram

1. User sends an HTTP request.
2. Routes delegate the request to a controller.
3. Controller interacts with the service layer.
4. Service interfaces with the database or external API.
5. Response is returned to the client.
