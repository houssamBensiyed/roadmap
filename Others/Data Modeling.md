A complete path from zero to advanced data modeling, organized as **Phases → Modules → Sections**, with a hands-on project at the end of every phase.

---

## Phase 1 — Foundations of Data & Databases

**Goal:** Understand what data is, how it's stored, and why modeling matters.

### Module 1.1 — Data Fundamentals

- What is data vs. information vs. knowledge
- Structured, semi-structured, and unstructured data
- Data types: numeric, text, temporal, boolean, binary, spatial
- Files vs. databases: why databases exist


### Module 1.2 — Database Landscape

- Relational (SQL) vs. non-relational (NoSQL) databases
- OLTP vs. OLAP: transactional vs. analytical workloads
- Overview of major systems: PostgreSQL, MySQL, SQL Server, MongoDB, Cassandra, Snowflake, BigQuery
- Where data modeling fits in the data lifecycle


### Module 1.3 — Introduction to Data Modeling

- What is a data model and why it matters (cost of bad models)
- The three levels: **Conceptual → Logical → Physical**
- Entities, attributes, relationships — the core vocabulary
- Roles: data modeler, data engineer, DBA, analyst


### Module 1.4 — SQL Essentials (the modeler's tool)

- DDL: CREATE, ALTER, DROP
- DML: SELECT, INSERT, UPDATE, DELETE
- Joins (INNER, LEFT, RIGHT, FULL), GROUP BY, aggregates
- Constraints: PRIMARY KEY, FOREIGN KEY, UNIQUE, NOT NULL, CHECK


> **📦 Phase 1 Project — Personal Library Database**
Design and build a small database for books, authors, and genres. Write the DDL from scratch, insert sample data, and write 10 queries (e.g., "books per author," "unread books by genre"). Deliverables: schema diagram + SQL scripts.



---

## Phase 2 — Relational Modeling & Normalization

**Goal:** Master the classic discipline of relational design.

### Module 2.1 — Entity-Relationship (ER) Modeling

- Entities: strong vs. weak
- Attributes: simple, composite, derived, multi-valued
- Relationships: 1:1, 1:N, M:N and how to resolve M:N with junction tables
- Cardinality and optionality (participation constraints)
- ER notation systems: Chen, Crow's Foot, UML, IDEF1X


### Module 2.2 — Keys & Integrity

- Candidate, primary, alternate, composite, and surrogate keys
- Natural keys vs. surrogate keys — the eternal debate
- Foreign keys and referential integrity
- Cascading actions: ON DELETE / ON UPDATE (CASCADE, SET NULL, RESTRICT)


### Module 2.3 — Normalization

- Functional dependencies
- 1NF: atomicity and repeating groups
- 2NF: partial dependencies
- 3NF: transitive dependencies
- BCNF, 4NF, 5NF — when they matter (and when they don't)
- Denormalization: when and why to deliberately break the rules


### Module 2.4 — Conceptual → Logical → Physical Workflow

- Requirements gathering and identifying entities from business language
- Translating a conceptual ERD into a logical model
- Mapping the logical model to a physical schema (data types, naming conventions)
- Modeling tools: dbdiagram.io, ERDPlus, Lucidchart, MySQL Workbench, ERwin


> **📦 Phase 2 Project — E-Commerce Database**
Model a full online store: customers, products, categories, orders, order items, payments, shipping addresses, reviews. Start with a conceptual ERD, normalize to 3NF, produce the physical schema in PostgreSQL, and document every design decision (especially key choices and M:N resolutions).



---

## Phase 3 — Advanced Relational Design Patterns

**Goal:** Handle the real-world complexity that textbooks skip.

### Module 3.1 — Advanced Relationship Patterns

- Self-referencing relationships (employees & managers, categories & subcategories)
- Supertype/subtype (inheritance) modeling: single table, class table, concrete table
- Polymorphic associations and their trade-offs
- Ternary and n-ary relationships


### Module 3.2 — Modeling Hierarchies & Graphs in SQL

- Adjacency list
- Path enumeration (materialized path)
- Nested sets
- Closure tables
- Recursive CTEs for traversal


### Module 3.3 — Temporal & Historical Data

- Effective dating (valid_from / valid_to)
- Bitemporal modeling (valid time vs. transaction time)
- Audit tables and change-tracking patterns
- Soft deletes vs. hard deletes


### Module 3.4 — Physical Design & Performance

- Indexing: B-tree, hash, composite, covering, partial indexes
- How the model affects query plans
- Partitioning: range, list, hash
- Views, materialized views
- Anti-patterns: EAV abuse, God tables, over-normalization, keyless tables, storing CSVs in columns


> **📦 Phase 3 Project — Project Management SaaS Schema**
Model a Jira-like system: organizations, teams, users with roles, projects, tasks with unlimited subtask nesting (pick and justify a hierarchy pattern), task history/audit trail, comments, and attachments. Include indexes with justification, and a write-up comparing at least two hierarchy strategies you considered.



---

## Phase 4 — Dimensional Modeling & Data Warehousing

**Goal:** Model for analytics, not transactions.

### Module 4.1 — Analytical Modeling Fundamentals

- Why OLTP models fail for analytics
- The Kimball vs. Inmon philosophies
- Data warehouse, data mart, data lake, lakehouse — definitions and roles


### Module 4.2 — Dimensional Modeling (Kimball)

- Facts and dimensions
- Star schema vs. snowflake schema
- The four-step dimensional design process
- Grain: the single most important decision
- Fact table types: transaction, periodic snapshot, accumulating snapshot, factless


### Module 4.3 — Dimension Design Deep Dive

- Slowly Changing Dimensions: Types 0, 1, 2, 3, 4, 6
- Conformed dimensions and the bus matrix
- Junk, degenerate, role-playing, and bridge dimensions
- Handling late-arriving facts and dimensions
- Date/calendar dimension design


### Module 4.4 — Modern Warehouse Modeling

- Data Vault 2.0: hubs, links, satellites — when to use it
- One Big Table (OBT) and wide tables in cloud warehouses
- Modeling for columnar engines (Snowflake, BigQuery, Redshift): clustering, partitioning, sort keys
- The medallion architecture (bronze/silver/gold) and dbt-style transformation layers


> **📦 Phase 4 Project — Retail Analytics Warehouse**
Take your Phase 2 e-commerce OLTP schema and build a dimensional warehouse from it: define the bus matrix, design a sales fact table (choose and defend the grain), build customer/product/date dimensions with SCD Type 2 on customer, and write analytical queries (revenue trends, cohort analysis, top products by margin). Bonus: implement it with dbt.



---

## Phase 5 — NoSQL & Non-Relational Modeling

**Goal:** Learn to model when the relational rules no longer apply.

### Module 5.1 — NoSQL Modeling Mindset

- Query-first (access-pattern-driven) design vs. entity-first design
- CAP theorem, eventual consistency, and what they mean for models
- Denormalization and duplication as features, not bugs


### Module 5.2 — Document Modeling (MongoDB)

- Embedding vs. referencing — the core decision
- One-to-few, one-to-many, one-to-squillions patterns
- Schema versioning in schemaless stores
- Bucket, outlier, computed, and subset patterns


### Module 5.3 — Wide-Column & Key-Value Modeling

- Cassandra/DynamoDB: partition keys, sort keys, clustering
- Single-table design in DynamoDB
- Modeling access patterns before writing a single attribute
- Hot partitions and how modeling causes/prevents them
- Redis data structures as models: hashes, sorted sets, streams


### Module 5.4 — Graph & Specialized Models

- Property graph model: nodes, edges, properties (Neo4j)
- When graphs beat relational (deep traversals, recommendations, fraud)
- Time-series modeling (TimescaleDB, InfluxDB): wide vs. narrow tables
- Search-oriented modeling (Elasticsearch): documents, mappings, denormalized indexes
- Vector embeddings and modeling for semantic search


> **📦 Phase 5 Project — Social Media Platform (Polyglot)**
Model a Twitter-like app across multiple paradigms: user profiles and posts in a document store (embedding vs. referencing decisions documented), the follower graph in a graph model, timelines/feeds in a wide-column or key-value design (fan-out on write vs. read), and trending hashtags in Redis. Deliver a design doc listing every access pattern and how each model serves it.



---

## Phase 6 — Enterprise, Governance & Real-Time Modeling

**Goal:** Model at organizational scale and in modern architectures.

### Module 6.1 — Enterprise Data Architecture

- Enterprise conceptual models and canonical data models
- Master Data Management (MDM): golden records, survivorship rules
- Data mesh: domain-oriented ownership and data products
- Industry reference models (financial, healthcare/FHIR, retail/ARTS)


### Module 6.2 — Data Governance & Metadata

- Data dictionaries, business glossaries, data catalogs
- Data lineage and impact analysis
- Modeling for privacy: PII classification, GDPR/CCPA, anonymization, right-to-be-forgotten in your schema
- Data quality rules as part of the model (constraints, contracts, expectations)


### Module 6.3 — Modeling for Events & Streaming

- Event modeling and event storming
- Event sourcing and CQRS: separating write models from read models
- Schema design for Kafka: Avro/Protobuf/JSON Schema, schema registry, schema evolution and compatibility rules
- Outbox pattern and change data capture (CDC)


### Module 6.4 — Modern Practice & Career Mastery

- Schema evolution and zero-downtime migrations (expand/contract pattern)
- Data contracts between teams
- Schema-as-code: dbt, Drizzle/Prisma migrations, Liquibase/Flyway
- Modeling for microservices: database-per-service, shared-nothing boundaries
- Reviewing and critiquing models: how to run a design review
- Communicating models to non-technical stakeholders


> **📦 Phase 6 Project — Capstone: Event-Driven Banking Platform**
Design the complete data architecture for a digital bank: an event-sourced ledger (immutable transaction events), CQRS read models for balances and statements, a dimensional warehouse for regulatory reporting, an MDM design for customer golden records, PII handling and retention policies baked into the schema, and versioned event schemas with documented evolution rules. Deliver: full ERDs, event catalog, bus matrix, data dictionary, and an architecture decision record (ADR) set.



---

## How to Use This Roadmap

- **Sequence matters through Phase 3** — relational fundamentals underpin everything. Phases 4 and 5 can be swapped based on whether your goals lean analytics or application engineering.
- **Do every project.** Modeling is a design skill; you only internalize trade-offs by making and defending decisions.
- **Practice critique:** for each project, write down 3 alternatives you rejected and why — that habit is what separates senior modelers.


**Key references along the way:** *Database Design for Mere Mortals* (Hernandez), *SQL Antipatterns* (Karwin), *The Data Warehouse Toolkit* (Kimball), *Designing Data-Intensive Applications* (Kleppmann), *NoSQL Distilled* (Fowler/Sadalage).