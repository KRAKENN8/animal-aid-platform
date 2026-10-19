---
status: Proposed
date: 19.10.2026
decision-makers: Ivan Petrov & Maksim Koroljov
---

# Database Choice

## Context and Problem Statement

The platform stores users, animals, shelters, requests and their statuses. These data are relational and need integrity guarantees. A database management system must be chosen.

## Decision Drivers

* Relational data with constraints
* Transactions across the application
* Possible geographic search ("animals nearby")
* Free and widely supported tooling
* Support for migrations and schema versioning

## Considered Options

* PostgreSQL
* MySQL / MariaDB
* MongoDB
* SQLite

## Decision Outcome

Chosen option: "PostgreSQL", because the data are relational, it provides ACID transactions and strong integrity constraints, supports JSONB for flexible fields, has the PostGIS extension for geographic queries, is free and mature.

### Consequences

* Good, because data integrity is enforced by the database, complex queries and indexes are supported, geo search is possible without another system, one instance is enough for the whole application, flexible fields are possible through JSONB
* Bad, because the schema requires migrations from the start, tuning is needed under load, a single database is a single point of failure, administration is more complex than file-based databases, backups must be organized

### Confirmation

"PostgreSQL" was chosen as the most comfortable option of all those considered, having the most advantages for the team members: relational data model that fits the project, strong integrity constraints, transactions, free and widely documented tooling.

## Pros and Cons of the Options

### PostgreSQL

* Good, because of ACID transactions, strong constraints, JSONB, PostGIS, full-text search
* Bad, because of more complex administration than SQLite, tuning required under load, horizontal scaling requires extra tools, a separate server process is needed, backups must be organized

### MySQL / MariaDB

* Good, because it is popular and simple, hosting is widely available, a large community, good performance on simple read queries, mature replication
* Bad, because geo features are weaker than in PostgreSQL, JSON features are weaker, fewer advanced SQL features, a smaller extension ecosystem, behavior depends on the storage engine and server mode

### MongoDB

* Good, because the schema is flexible, horizontal scaling is easy, documents map naturally to JSON, prototyping is fast, geo queries are built in
* Bad, because the data are relational, joins are weaker, integrity constraints are weaker, multi-document transactions are more limited, data is often duplicated

### SQLite

* Good, because it needs no server, setup is trivial, the database is a single file, no administration is needed, it is fast for local reads
* Bad, because concurrent writes are limited, it is unsuitable for a multi-user production platform, it has no network access by default, fewer data types and features, no built-in user management
