# Testing Guide

Explain how to run tests, structure them, and tools used.

## Running Tests

To execute tests:

```bash
npm test
```

## Test Structure

Tests are located in the `__tests__/` directory:

```txt
__tests__
└── src
    ├── learning
    │   ├── lodash
    │   │   ├── CloneDeep.learning.test.ts
    │   │   └── IsEqual.learning.test.ts
    │   └── typedi
    │       ├── BasicDi.learning.test.ts
    │       ├── BasicUsage.learning.test.ts
    │       ├── InjectDecoratorConstructor.learning.test.ts
    │       ├── InjectDecoratorExplicitTarget.learning.test.ts
    │       └── InjectDecoratorProperty.learning.test.ts
    └── unit
        ├── app
        │   └── use-cases
        │       ├── abstrs
        │       └── impls
        │           └── todo-item
        │               └── create
        │                   ├── InputVldtr.unit.test.ts
        │                   └── UseCase.unit.test.ts
        └── infra
            ├── lib-wrappers
            │   └── lodash
            │       ├── LodashFacadeCloneDeep.unit.test.ts
            │       └── LodashFacadeIsEqual.unit.test.ts
            └── persistence
                └── mem
                    ├── impls
                    │   ├── MemDb.unit.test.ts
                    │   └── Table.unit.test.ts
                    └── repos
                        └── todo-item
                            └── TodoItemRepo.unit.test.ts
```

## Tools Used

- **Jest**: Unit and integration testing.
- **Supertest**: HTTP assertions.
