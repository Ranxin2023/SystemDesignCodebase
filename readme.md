# System Design
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
### 3. Load Balancing
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