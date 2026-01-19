# System Design
## Table Of Contents
- [Foundational System Design Concepts](#foundational-system-design-concepts)
    - [Data Storage and Management](#1-data-storage-and-management)
    - [Caching](#2-caching)
    - [Load Balancing](#3-load-balancing)
    
- [Reshaded Frameworks](#reshaded-frameworks)
    - [Requirements](#r--requirements)
    - [Estimation](#e--estimation)
## Foundational System Design Concepts
### 1. Data Storage and Management
#### What it is
- How data is stored, structured, accessed, scaled, protected, and maintained.
#### Key decisions
- SQL vs NoSQL
- Schema design (normalized vs denormalized)
- Sharding & replication
- Consistency guarantees
- Backups and recovery

### 2. Caching
#### What it is
- Storing frequently accessed data in **fast storage** to reduce latency and load.
#### Common cache locations
- Client (browser cache)
- CDN
- Application cache (Redis)
- Database cache

### 3. Load Balancing
#### What it is
- Distributing traffic across multiple servers to avoid overload.
#### Types
- Layer 4 (TCP/UDP)
- Layer 7 (HTTP/HTTPS)
#### Algorithms
- Round robin
- Least connections
- Hash-based
#### Benefits
- Scalability
- High availability
- Fault tolerance
## Reshaded Frameworks
### R — Requirements
- Clarify **what you are building**.
    - Functional requirements (features, user actions)
    - Non-functional requirements (latency, availability, scalability, security)
    - Constraints (traffic, cost, consistency model)
    
### E — Estimation
- Estimate scale and load.
    - Daily active users (DAU)
    - QPS / RPS (reads vs writes)
    - Storage size
    - Bandwidth

### S — Storage Schema (Data Model)
- Design **how data is stored**.
    - SQL vs NoSQL
    - Tables / collections
    - Indexes
    - Relationships

### H — High-Level Design
- Create the **big picture architecture**.
    - Clients
    - Load balancers
    - Services
    - Databases
    - Caches
    - Message queues
- 👉 Goal: Show system components and data flow.

### A — API Design
- Define **how components talk to each other**.
    - REST / GraphQL / gRPC
    - Request & response formats
    - Idempotency
    - Pagination
- 👉 Goal: Make interactions clear and scalable.

### E — Evaluation
- Analyze **trade-offs and risks**.
    - Bottlenecks
    - SPOFs (Single Points of Failure)
    - CAP trade-offs
    - Cost vs performance

### D — Distinctive Components
- Add **advanced or unique improvements**.
    - Rate limiting
    - CDN
    - Search indexing
    - Recommendation systems
    - Monitoring & alerting
## Why RESHADED Is Powerful in Interviews
- 