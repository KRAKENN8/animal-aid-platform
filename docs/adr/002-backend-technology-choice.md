---
status: Accepted
date: 19.10.2026
decision-makers: Ivan Petrov & Maksim Koroljov
---

# Backend Technology Choice

## Context and Problem Statement

The backend exposes a REST API for the frontend. It must handle authentication, roles (guest, volunteer, shelter, moderator), animals, requests, moderation and notifications, and work with a relational database. A backend language and framework must be chosen.

## Decision Drivers

* Automatic API documentation and request validation
* Clear project structure with the ability to split code into modules
* Testability
* Development speed
* Small team and fixed deadline

## Considered Options

* Python + FastAPI
* PHP
* Node.js
* Go
* Java

## Decision Outcome

Chosen option: "Python FastAPI", because it generates OpenAPI documentation automatically, validates data through Pydantic, supports async I/O, has dependency injection that simplifies testing, Python code is concise and readable, a quick start.

### Consequences

* Good, because API contracts are documented and typed, tests are easy to write, development is fast, the Python ecosystem is available, async I/O is supported
* Bad, because authentication and roles must be built manually, there is no built-in admin panel, project structure depends on team discipline, async code requires care, ORM and migration tools must be chosen and integrated separately

### Confirmation

"Python FastAPI" was chosen as the most comfortable option of all those considered, having the most advantages for the team members: fast development, concise Python code, automatic API documentation, simple validation and testing.

## Pros and Cons of the Options

### Python FastAPI

* Good, because of automatic OpenAPI, Pydantic validation, async support, fast development, a lightweight core
* Bad, because there is no built-in admin, there is no built-in auth, more manual assembly, a younger ecosystem than Django or Spring, project structure depends on discipline

### PHP

* Good, because hosting is cheap and widespread, mature frameworks (Laravel, Symfony), auth and ORM included in frameworks, a large community, easy deployment
* Bad, because of weaker typing, inconsistent legacy code in the ecosystem, API documentation needs extra tooling, limited async support, less suited for long-running background tasks

### Node.js

* Good, because it uses one language with the frontend, a large ecosystem, a good async model, a quick start, many ready-made packages
* Bad, because of a dynamic ecosystem with many dependencies, project structure is not enforced (without NestJS), type safety requires TypeScript, dependency security risks, API documentation needs extra tooling

### Go

* Good, because of high performance, simple deployment as one binary, strong concurrency, static typing, low memory usage
* Bad, because of more verbose code, a smaller choice of ready-made libraries, slower development for CRUD-heavy applications, verbose error handling, less mature ORM options

### Java

* Good, because of maturity, strong typing, the Spring ecosystem (security, data, validation), suitability for large systems, extensive tooling
* Bad, because it is heavy and verbose for a small project, development is slower, a high learning curve, higher memory consumption, longer build and startup times
