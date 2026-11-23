# System Design Interview Questions

> A structured guide to system design interviews, brought to you by [Aced](https://www.aced.io). Check out the full [system design course](https://www.aced.io/courses/system-design-interviews).

---

## Table of contents

- [About this guide](#about-this-guide)
- [How to use this resource](#how-to-use-this-resource)
- [Preparation timeline](#preparation-timeline)
- [Core fundamentals](#core-fundamentals)
- [System design questions](#system-design-questions)
- [Interview framework](#interview-framework)
- [Additional resources](#additional-resources)
- [Contributing](#contributing)

---

## About this guide

This open-source primer gives you a structured path through system design interview prep:

- Learning paths for the fundamentals, organized by topic
- Example questions organized by difficulty
- A framework for structuring your answer in the room

## How to use this resource

**New to system design:** start with [Core fundamentals](#core-fundamentals), work through the Easy questions, then practice the framework end to end.

**Experienced engineers:** skim the fundamentals, focus on Medium and Hard questions, and drill the trade-off discussions interviewers actually grade you on.

| Timeline | Focus | Hours/week |
|----------|-------|------------|
| 2 weeks | Fundamentals + Easy questions | 10-15 |
| 4 weeks | All fundamentals + Easy/Medium | 8-12 |
| 8 weeks | Complete prep + mock interviews | 6-10 |

## Preparation timeline

**Weeks 1-2: Foundations**
- [ ] Core building blocks: load balancing, caching, databases
- [ ] 2-3 easy design questions
- [ ] Learn the interview rubric: what interviewers grade

**Weeks 3-4: Core patterns**
- [ ] Common architectural patterns (see fundamentals below)
- [ ] 5-7 medium questions, whiteboarded out loud
- [ ] Capacity estimation drills

**Weeks 5-6: Advanced concepts**
- [ ] Scaling techniques, consistency models
- [ ] Hard questions
- [ ] 2-3 [mock interviews](https://www.aced.io/practice)

**Weeks 7-8: Polish**
- [ ] Timed practice sessions
- [ ] Review recent [interview experiences](https://www.aced.io/questions)

## Core fundamentals

### 1. Basics

| Topic | Key concepts |
|-------|--------------|
| Design requirements | Functional vs non-functional requirements, constraints |
| Capacity estimation | Back-of-the-envelope math: traffic, storage, bandwidth |
| Interview rubric | What interviewers look for, evaluation criteria |

Practice: estimate storage for 1B users uploading 5 photos/day; bandwidth for a video service with 10M DAU.

### 2. Networking and communication

| Topic | Key concepts |
|-------|--------------|
| HTTP/HTTPS | Request/response, REST, status codes |
| WebSockets | Real-time bidirectional communication |
| TCP vs UDP | Connection-oriented vs connectionless |
| DNS and CDN | Domain resolution, content delivery |
| Load balancing | L4 vs L7, round-robin, least connections |

### 3. Databases and storage

| Topic | Key concepts |
|-------|--------------|
| SQL vs NoSQL | Relational vs document/key-value/column/graph |
| Sharding | Horizontal partitioning, shard keys, consistent hashing |
| Replication | Leader-follower, multi-leader, read replicas |
| Indexing | B-trees, hash indexes, full-text search |
| CAP theorem | Consistency, availability, partition tolerance |
| ACID | Atomicity, consistency, isolation, durability |

**Database selection guide:**

| Use case | Database type | Examples |
|----------|---------------|----------|
| Structured data with relationships | SQL | PostgreSQL, MySQL |
| High write throughput | Wide-column | Cassandra, HBase |
| Caching layer | Key-value | Redis, Memcached |
| Document storage | Document | MongoDB |
| Social graphs | Graph | Neo4j, Neptune |
| Time-series data | Time-series | InfluxDB, TimescaleDB |

### 4. Caching

| Topic | Key concepts |
|-------|--------------|
| Cache types | Local, distributed, CDN |
| Cache patterns | Cache-aside, write-through, write-back |
| Eviction policies | LRU, LFU, FIFO, TTL |
| Invalidation | Time-based, event-based, manual |

### 5. Architecture patterns

| Topic | Key concepts |
|-------|--------------|
| Microservices | Service decomposition, API gateway, service mesh |
| Message queues | Async processing, decoupling, pub/sub |
| Event-driven design | Event sourcing, CQRS, streams |
| API design | REST, GraphQL, gRPC |

### 6. Scalability, reliability, security

| Topic | Key concepts |
|-------|--------------|
| Horizontal vs vertical scaling | Scale out vs scale up, autoscaling |
| Redundancy and failover | Active-active, active-passive, graceful degradation |
| Circuit breakers | Failure detection, fallbacks |
| Rate limiting | Token bucket, leaky bucket, sliding window |
| AuthN/AuthZ | OAuth, JWT, RBAC |

Each topic above maps to a lesson in the [full course](https://www.aced.io/courses/system-design-interviews).

## System design questions

### Easy (entry-level and new grad)

| Question | Key concepts |
|----------|--------------|
| URL shortener | Hashing, database design, redirects |
| Key-value store | Hash tables, distributed storage, consistency |
| Rate limiter | Token bucket, sliding window, distributed counters |
| Pastebin | Text storage, URL generation, expiration |
| Web crawler | BFS/DFS, URL frontier, robots.txt, dedup |

### Medium (mid-level)

| Question | Key concepts |
|----------|--------------|
| Twitter | Timeline generation, fanout, pub/sub, caching |
| Instagram | Image storage, feed generation, CDN |
| WhatsApp | Real-time messaging, WebSockets, queues |
| YouTube | Streaming, transcoding, CDN, recommendations |
| Uber | Geospatial indexing, matching, real-time tracking |
| Dropbox | File chunking, sync, dedup, conflict resolution |
| Ticketmaster | Concurrency control, inventory, payments |

### Hard (senior and staff)

| Question | Key concepts |
|----------|--------------|
| Google Search | Inverted index, distributed crawling, query processing |
| Google Maps | Spatial indexing, routing, real-time traffic |
| TikTok | Video processing, recommendation ML, real-time analytics |
| Notification system | Multi-channel delivery, priority queues, dedup, retries |
| Ad click aggregator | Stream processing, real-time analytics, pipelines |

Worked solutions for these are in the [course](https://www.aced.io/courses/system-design-interviews), and you can browse hundreds more real questions in the [system design question bank](https://www.aced.io/questions?type=system-design).

## Interview framework

**RADIO:**

1. **R**equirements: functional, non-functional, out of scope (5-7 min)
2. **A**rchitecture: high-level components and data flow (10-15 min)
3. **D**ata model: schema, relationships, partitioning
4. **I**nterface: API endpoints, request/response shapes
5. **O**ptimization: bottlenecks, scaling, trade-offs (15-20 min)

**Trade-offs interviewers expect you to discuss:**

| Trade-off | Choose A when | Choose B when |
|-----------|---------------|---------------|
| SQL vs NoSQL | Complex queries, transactions | High write throughput, flexible schema |
| Consistency vs availability | Financial transactions, inventory | Feeds, analytics |
| Normalize vs denormalize | Write-heavy | Read-heavy |
| Sync vs async | Immediate feedback needed | Decoupling, user experience |

## Additional resources

**Papers:** [MapReduce](https://research.google/pubs/pub62/), [Bigtable](https://research.google/pubs/pub27898/), [Dynamo](https://www.allthingsdistributed.com/files/amazon-dynamo-sosp2007.pdf), [Raft](https://raft.github.io/raft.pdf)

**Books:** Designing Data-Intensive Applications (Kleppmann); Site Reliability Engineering (Google)

**Practice:** [Aced mock interviews](https://www.aced.io/practice) with peers and experts

**Top company guides on Aced:** [Anthropic SWE](https://www.aced.io/guides/anthropic-software-engineer-interview) · [Google SWE](https://www.aced.io/guides/google-software-engineer-interview) · [OpenAI SWE](https://www.aced.io/guides/openai-software-engineer-interview)

## Contributing

PRs welcome: new questions you've been asked, clearer explanations, corrections. Follow the existing format and keep it interview-focused.

## License

MIT. Maintained by [Aced](https://www.aced.io), the interview prep platform formerly known as Exponent.

---

**Related guides:** [AI/ML Engineer](https://github.com/jacobsimon/ai-engineer-interview-questions) · [Product Manager](https://github.com/jacobsimon/product-manager-interview-questions)
