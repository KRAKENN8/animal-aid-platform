---
status: Accepted
date: 19.10.2026
decision-makers: Ivan Petrov & Maksim Koroljov
---

# Application Structure Choice

## Context and Problem Statement

The backend of the platform must be structured: its code can be organized as a single codebase with or without explicit module boundaries, or as several independent services. The team is small, the deadline is fixed and the expected load is moderate.

## Decision Drivers

* Small team and fixed diploma deadline
* Low operational complexity and hosting cost
* Transactions across domain data (animals, requests, users)
* Clear module boundaries for maintainability and testing
* Ability to extract services later

## Considered Options

* Monolith
* Modular monolith
* Layered
* Microservices

## Decision Outcome

Chosen option: "Modular monolith", because it is deployed as one unit, keeps transactions local, is fast to develop and debug, requires little infrastructure, explicit module boundaries keep the code maintainable and allow extracting services later.

### Consequences

* Good, because deployment is simple, one database transaction covers a whole operation, local development and testing are easy, hosting cost is low, debugging is simpler
* Bad, because the whole backend scales together, module boundaries depend on team discipline, a failure in one module can affect the whole process, any change requires redeploying everything, all modules share one technology stack

### Confirmation

"Modular monolith" was chosen as the most comfortable option of all those considered, having the most advantages for the team members: simple deployment and debugging, local transactions, low infrastructure cost, clear division of the code into modules.

## Pros and Cons of the Options

### Monolith

* Good, because it is the simplest to build and deploy, infrastructure cost is low, debugging is easy, transactions are local, the start is fast
* Bad, because module boundaries erode, coupling grows over time, splitting later requires refactoring, isolated testing is harder, a large codebase becomes hard to navigate

### Modular monolith

* Good, because deployment is simple, transactions are local, development is fast, boundaries allow later extraction, infrastructure cost is low
* Bad, because boundaries rely on discipline, scaling is not per module, one failure can affect the whole process, a shared database tempts cross-module queries, modules must be designed up front

### Layered

* Good, because it is familiar and simple, concerns are separated (API, services, repositories), each layer is testable, it is easy to explain, it fits typical frameworks
* Bad, because it organizes code by technical layers rather than by domain, layers can leak, one change often touches every layer, it does not define module boundaries, business logic can end up in thin layers

### Microservices

* Good, because services are deployed and scaled independently, failures are isolated, each service can use its own technology, domain ownership is clear, teams can work on services in parallel
* Bad, because of distributed data consistency problems, network failures between services, complex deployment and monitoring, high overhead for a small team, harder local development and testing
