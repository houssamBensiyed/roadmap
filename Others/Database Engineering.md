# 🗄️ Database Engineering Mastery Roadmap (2025+)

---

## PHASE 1: FOUNDATIONS (Basic)
*Duration: ~4-6 months*

---

### ==Module 1.1: Computer Science Foundations for Databases==
#### 1.1.1 Data Structures (Database-Relevant)
- Arrays, linked lists, hash tables (hash collisions, chaining, open addressing)
- **Trees:**
  - Binary Search Trees (BST) — search, insert, delete complexity
  - Balanced BSTs (AVL, Red-Black — self-balancing concepts)
  - **B-Trees** (the index structure — order, splitting, merging, disk-oriented)
  - **B+ Trees** (leaf-linked, range queries, the actual database index structure)
  - Tries (prefix trees — text indexing awareness)
  - LSM Trees (Log-Structured Merge Trees — write-optimized, compaction)
- **Heaps** (priority queues — used in query execution)
- **Bloom filters** (probabilistic membership testing — used in LSM stores, caching)
- **Skip lists** (alternative to balanced trees — used in Redis, MemTable)
- **Consistent hashing** (distributed data placement)

#### 1.1.2 Operating Systems & Storage
- Memory hierarchy (registers → L1/L2/L3 cache → RAM → SSD → HDD)
- Virtual memory, paging, memory-mapped files (`mmap`)
- Disk I/O: sequential vs. random access (why it matters for databases)
- SSD vs. HDD (IOPS, latency, write amplification)
- File systems (ext4, XFS, ZFS — database-relevant characteristics)
- Page cache and buffer pool concepts
- `fsync`, `fdatasync`, `O_DIRECT` (durability guarantees)
- RAID levels (0, 1, 5, 6, 10 — trade-offs for databases)
- I/O schedulers (awareness — how OS manages disk requests)

#### 1.1.3 Networking Fundamentals
- TCP/IP (connection lifecycle, latency, throughput)
- Network latency impact on database operations
- Connection pooling (why, how, sizing)
- Client-server communication protocols (wire protocols)
- TLS/SSL for database connections
- Unix domain sockets vs. TCP (local vs. remote connections)

#### 1.1.4 Programming for Database Engineers
- **SQL** (obviously — covered in depth later)
- **Python** (scripting, automation, data analysis):
  - `psycopg` / `asyncpg` (PostgreSQL drivers)
  - `sqlalchemy` (ORM and core)
  - `pandas` (data analysis, CSV/Parquet processing)
  - Script writing for migrations, data validation, monitoring
- **Bash** (system administration, automation):
  - Cron jobs, log parsing, backup scripts
  - `grep`, `awk`, `sed`, `jq` for log analysis
- **Go or Rust** (awareness — many modern database tools are written in these)

---

### ==Module 1.2: Relational Database Theory==
#### ==1.2.1 The Relational Model==
- Edgar Codd's 12 rules (historical context)
- Relations, tuples, attributes, domains
- Keys: candidate, primary, foreign, composite, surrogate, natural
- Relational algebra: selection (σ), projection (π), join (⋈), union (∪), difference (−), cartesian product (×)
- Relational calculus (awareness — declarative query specification)
- Set theory foundations (unions, intersections, differences)
- NULL semantics (three-valued logic: TRUE, FALSE, UNKNOWN)
- Closed-world assumption

#### ==1.2.2 Normalization==
- Functional dependencies (what they are, how to identify them)
- **1NF:** Atomic values, no repeating groups
- **2NF:** No partial dependencies (on part of composite key)
- **3NF:** No transitive dependencies
- **BCNF (Boyce-Codd Normal Form):** Every determinant is a candidate key
- **4NF:** No multi-valued dependencies
- **5NF:** No join dependencies (awareness)
- **Denormalization:** When and why to break normal forms
  - Read performance vs. write complexity
  - Reporting/analytics use cases
  - Materialized views as controlled denormalization
  - Document-style embedding in RDBMS (JSONB columns)

#### 1.2.3 Entity-Relationship Modeling
- Entities, attributes, relationships
- Cardinality (1:1, 1:N, M:N)
- Participation (total vs. partial)
- Weak entities and identifying relationships
- Specialization/generalization (inheritance in ER)
- ER to relational mapping rules
- Tools: draw.io, dbdiagram.io, ERDPlus, pgModeler

---

### ==Module 1.3: SQL Mastery==
#### ==1.3.1 Data Definition Language (DDL)==
- `CREATE TABLE` (data types, constraints, defaults, generated columns)
- **Data types deep dive (PostgreSQL focus):**
  - Numeric: `integer`, `bigint`, `smallint`, `numeric`/`decimal`, `real`, `double precision`, `serial`/`bigserial`
  - Text: `varchar(n)`, `text`, `char(n)` (prefer `text` or `varchar`)
  - Date/Time: `timestamp`, `timestamptz` (**always use `timestamptz`**), `date`, `time`, `interval`
  - Boolean: `boolean`
  - UUID: `uuid` (with `gen_random_uuid()`)
  - JSON: `json` vs. `jsonb` (**prefer `jsonb`**)
  - Arrays: `integer[]`, `text[]`
  - Enums: `CREATE TYPE status AS ENUM (...)`
  - Ranges: `int4range`, `tstzrange`
  - Network: `inet`, `cidr`, `macaddr`
  - Binary: `bytea`
- **Constraints:**
  - `PRIMARY KEY`, `FOREIGN KEY` (with `ON DELETE`/`ON UPDATE`: CASCADE, SET NULL, RESTRICT, NO ACTION)
  - `UNIQUE`, `NOT NULL`, `CHECK`
  - `EXCLUDE` (exclusion constraints — PostgreSQL)
  - Deferred constraints (`DEFERRABLE INITIALLY DEFERRED`)
- `ALTER TABLE` (add/drop/modify columns, constraints, rename)
- `DROP TABLE`, `TRUNCATE` (differences)
- `CREATE SCHEMA`, `CREATE DATABASE`
- Sequences (`CREATE SEQUENCE`, `nextval`, `currval`)
- Domains (`CREATE DOMAIN` — reusable column types)

#### ==1.3.2 Data Manipulation Language (DML)==
- `INSERT` (single, multi-row, `INSERT INTO ... SELECT`, `ON CONFLICT` / upsert)
- `UPDATE` (with `FROM`, `RETURNING`, conditional updates)
- `DELETE` (with `USING`, `RETURNING`)
- `MERGE` (SQL standard upsert — PostgreSQL 15+)
- `COPY` and `\copy` (bulk data loading — fastest PostgreSQL import)
- `RETURNING` clause (get affected rows without extra query)

#### ==1.3.3 Queries (SELECT — Deep)==
- **Fundamentals:** `SELECT`, `FROM`, `WHERE`, `GROUP BY`, `HAVING`, `ORDER BY`, `LIMIT`/`OFFSET`
- **Joins:**
  - `INNER JOIN`, `LEFT JOIN`, `RIGHT JOIN`, `FULL OUTER JOIN`
  - `CROSS JOIN`, `NATURAL JOIN` (avoid natural joins)
  - Self-joins
  - Lateral joins (`LATERAL` — correlated subqueries as joins)
  - Multiple join conditions
  - Join order and optimization
- **Subqueries:**
  - Scalar subqueries (single value)
  - Table subqueries (`IN`, `EXISTS`, `ANY`, `ALL`)
  - Correlated vs. uncorrelated subqueries
  - Subqueries in `FROM` (derived tables)
  - `EXISTS` vs. `IN` (performance implications)
- **Aggregation:**
  - `COUNT`, `SUM`, `AVG`, `MIN`, `MAX`
  - `DISTINCT` (in aggregates and in queries)
  - `FILTER` clause (`COUNT(*) FILTER (WHERE ...)`)
  - `GROUPING SETS`, `ROLLUP`, `CUBE` (multi-dimensional aggregation)
  - `STRING_AGG`, `ARRAY_AGG`, `JSON_AGG`, `JSONB_AGG`
- **Set operations:** `UNION`, `UNION ALL`, `INTERSECT`, `EXCEPT`

#### ==1.3.4 Advanced SQL==
- **Common Table Expressions (CTEs):**
  - Non-recursive CTEs (readability, query organization)
  - Recursive CTEs (hierarchical data, graph traversal, series generation)
  - Materialized vs. non-materialized CTEs (PostgreSQL optimization fences)
- **Window functions:**
  - `ROW_NUMBER()`, `RANK()`, `DENSE_RANK()`, `NTILE()`
  - `LEAD()`, `LAG()` (previous/next row access)
  - `FIRST_VALUE()`, `LAST_VALUE()`, `NTH_VALUE()`
  - `SUM() OVER`, `AVG() OVER`, `COUNT() OVER` (running aggregates)
  - `PARTITION BY` and `ORDER BY` in window specification
  - Window frame: `ROWS BETWEEN`, `RANGE BETWEEN`, `GROUPS BETWEEN`
  - Named windows (`WINDOW w AS (...)`)
- **JSON operations (PostgreSQL):**
  - `->`, `->>`, `#>`, `#>>` (JSON path operators)
  - `jsonb_extract_path`, `jsonb_set`, `jsonb_insert`
  - `jsonb_each`, `jsonb_array_elements` (expanding JSON)
  - JSON path queries (`@?`, `@@`)
  - Indexing JSONB (GIN indexes)
- **Full-text search (PostgreSQL):**
  - `tsvector`, `tsquery`, `to_tsvector()`, `to_tsquery()`
  - `@@` (match operator)
  - Ranking: `ts_rank`, `ts_rank_cd`
  - GIN indexes for full-text search
  - Dictionaries and configurations
- **Date/time operations:**
  - `date_trunc`, `extract`, `age`
  - Interval arithmetic
  - Time zone handling (`AT TIME ZONE`)
  - Generate series (`generate_series` for dates)
- **Conditional expressions:** `CASE WHEN`, `COALESCE`, `NULLIF`, `GREATEST`, `LEAST`
- **Regular expressions:** `~`, `~*`, `!~`, `SIMILAR TO`, `regexp_matches`

---

### ==Module 1.4: PostgreSQL Deep Dive (Primary Database)==
#### ==1.4.1 PostgreSQL Architecture==
- Process model (postmaster, backend processes, background workers)
- Shared memory (shared buffers, WAL buffers, work_mem, maintenance_work_mem)
- Storage: tablespaces, databases, schemas, tables, indexes
- TOAST (The Oversized-Attribute Storage Technique — large column handling)
- Catalog tables (`pg_class`, `pg_attribute`, `pg_index`, `pg_stat_*`)
- System views (`pg_stat_user_tables`, `pg_stat_user_indexes`, `pg_stat_activity`)
- Configuration (`postgresql.conf`, `pg_hba.conf`, `ALTER SYSTEM`)

#### 1.4.2 PostgreSQL-Specific Features
- **JSONB** (document storage within relational DB — when to use)
- **Arrays** (native array type, operations, indexing)
- **Range types** (date ranges, integer ranges, overlap, containment)
- **Generated columns** (`GENERATED ALWAYS AS`)
- **Table inheritance** (legacy — prefer partitioning)
- **Table partitioning** (declarative: RANGE, LIST, HASH)
- **Foreign Data Wrappers (FDW)** — querying external data sources
- **Materialized views** (`CREATE MATERIALIZED VIEW`, `REFRESH`)
- **Row-level security (RLS)** policies
- **Advisory locks** (application-level locking)
- **Listen/Notify** (async notifications between sessions)
- **Logical decoding** (change data capture)
- **Extensions:** `uuid-ossp`, `pgcrypto`, `pg_trgm`, `postgis`, `pgvector`, `pg_stat_statements`

#### 1.4.3 PostgreSQL Administration Basics
- Installation and initial configuration
- `psql` command-line client mastery
- User/role management (`CREATE ROLE`, `GRANT`, `REVOKE`)
- Database/schema management
- `pg_hba.conf` (client authentication configuration)
- Basic monitoring (`pg_stat_activity`, `pg_stat_user_tables`)
- `VACUUM` and `ANALYZE` (what they do, when they run, autovacuum)
- Backup basics (`pg_dump`, `pg_dumpall`, `pg_restore`)
- `pg_stat_statements` (query statistics)
- Log configuration and analysis
- `pgAdmin` and `DBeaver` (GUI tools)

---

### Module 1.5: Database Design
#### ==1.5.1 Schema Design Principles==
- Naming conventions (snake_case, plural/singular tables, consistent patterns)
- Primary key strategies:
  - Auto-increment (`SERIAL`, `BIGSERIAL`, `IDENTITY`)
  - UUID (`uuid`, `uuid_v7` — time-sortable)
  - Natural keys vs. surrogate keys (trade-offs)
  - Composite keys (when appropriate)
- Foreign key design (naming, `ON DELETE`/`ON UPDATE` actions)
- Timestamp columns (`created_at`, `updated_at` — `DEFAULT NOW()`, triggers)
- Soft deletes (`deleted_at TIMESTAMPTZ`) vs. hard deletes vs. archive tables
- Audit columns (`created_by`, `updated_by`)
- Schema versioning and evolution

#### ==1.5.2 Common Design Patterns==
- **One-to-Many:** Parent-child with foreign key
- **Many-to-Many:** Junction/association table (with possible extra columns)
- **One-to-One:** Shared PK or unique FK (table splitting for performance)
- **Self-referencing:** Categories, org charts, comment threads
- **Polymorphic associations:**
  - Single Table Inheritance (discriminator column)
  - Class Table Inheritance (table per subtype with shared PK)
  - Concrete Table Inheritance (independent tables)
- **EAV (Entity-Attribute-Value):** When to use (rarely), and JSONB as alternative
- **Temporal data:** SCD Type 1 (overwrite), Type 2 (history rows), Type 3 (previous column), temporal tables
- **Multi-tenancy:**
  - Database per tenant
  - Schema per tenant
  - Shared table with `tenant_id`
  - Row-level security (RLS)
- **Tags/Labels:** Junction table vs. array column vs. JSONB
- **Hierarchical data:** Adjacency list, nested set, materialized path, closure table, `ltree`
- **State machines:** Status columns, valid transitions, history tables

#### 1.5.3 Anti-Patterns to Avoid
- God tables (too many columns — split into related tables)
- Stringly-typed data (using `varchar` for everything — use proper types)
- Implicit columns (`SELECT *` in production code)
- Missing indexes on foreign keys
- Over-indexing (too many indexes slow writes)
- EAV when not needed (use JSONB or proper columns)
- Storing calculated data without materialized views
- Using `float` for money (use `numeric`/`decimal`)
- Nullable foreign keys everywhere (design issue)
- Comma-separated values in columns (violates 1NF)

---

### 🗄️ Phase 1 Project: Database Design & Implementation
> Design and implement a database for a SaaS project management platform:
> - **Schema design:**
>   - Organizations (multi-tenant), Users, Teams, Projects, Tasks, Comments, Labels, Attachments, Activity Log
>   - Proper normalization (3NF minimum), then strategic denormalization
>   - ER diagram and schema documentation
>   - All relationship types (1:1, 1:N, M:N, self-referencing)
>   - Hierarchical tasks (subtasks using adjacency list + recursive CTEs)
>   - Temporal data (task status history — SCD Type 2)
>   - Soft deletes, audit columns, timestamps
> - **Advanced SQL:**
>   - Dashboard queries (tasks per status, overdue tasks, team workload)
>   - Window functions (running completion rate, ranking by performance)
>   - Recursive CTEs (task hierarchy, project tree)
>   - JSONB for custom fields (flexible per-organization configuration)
>   - Full-text search on task titles and descriptions
> - **Multi-tenancy:** `tenant_id` on all tables + RLS policies
> - **Migrations:** Alembic or Flyway migration scripts (versioned)
> - **Seed data:** Script to generate realistic test data (10K+ records)
> - **Documentation:**
>   - ER diagram (dbdiagram.io or pgModeler)
>   - Data dictionary (table/column descriptions)
>   - Design decision document (why each choice was made)
> - **Testing:** SQL test scripts validating constraints, triggers, and business rules
>
> **Why:** Covers relational modeling, normalization, advanced SQL, multi-tenancy, temporal data, hierarchical data, JSONB, and full-text search — the complete database design foundation.

---

### ✅ After Phase 1 — You Can:
- [ ] Explain B-tree and B+ tree indexing structures and their disk I/O implications
- [ ] Design normalized database schemas and make informed denormalization decisions
- [ ] Write complex SQL (CTEs, window functions, JSONB, full-text search, recursive queries)
- [ ] Navigate PostgreSQL architecture, configuration, and administration
- [ ] Implement common database design patterns (multi-tenancy, hierarchies, temporal data)
- [ ] Create and manage database migrations
- [ ] Identify and avoid common database design anti-patterns
- [ ] Model data relationships and translate ER diagrams to SQL schemas

---
---

## PHASE 2: QUERY OPTIMIZATION & DATABASE INTERNALS (Intermediate)
*Duration: ~6-9 months*

---

### ==Module 2.1: Indexing Deep Dive==
#### ==2.1.1 B-Tree Indexes (The Default)==
- B-tree structure (balanced tree, sorted keys, leaf pages, internal pages)
- How B-tree lookups work (root → internal → leaf → heap tuple)
- Index scan vs. sequential scan (when the optimizer chooses each)
- **Index types by column usage:**
  - Single-column indexes
  - Composite/multi-column indexes (**column order matters** — leftmost prefix rule)
  - Covering indexes (`INCLUDE` — index-only scans)
  - Partial indexes (`WHERE` clause — index a subset of rows)
  - Expression indexes (`CREATE INDEX ON ... ((lower(email)))`)
  - Unique indexes (enforcing uniqueness)
- Index-only scans (when visibility map allows skipping heap)
- Index ordering (`ASC`, `DESC`, `NULLS FIRST`, `NULLS LAST`)
- Fillfactor (leaving space for updates — HOT updates)

#### ==2.1.2 Specialized Index Types (PostgreSQL)==
- **GIN (Generalized Inverted Index):**
  - Full-text search (`tsvector`)
  - JSONB containment and existence queries
  - Array containment
  - `pg_trgm` similarity searches
  - Trade-off: fast reads, slower writes
- **GiST (Generalized Search Tree):**
  - Geometric/spatial data (PostGIS)
  - Range type operations (overlap, containment)
  - Full-text search (alternative to GIN)
  - Nearest-neighbor searches
- **SP-GiST (Space-Partitioned GiST):**
  - Non-balanced data structures (quadtrees, radix trees)
  - IP address lookups
- **BRIN (Block Range Index):**
  - Physically ordered data (timestamps, auto-increment IDs)
  - Very small index size (block-level min/max)
  - Excellent for append-only tables (logs, time-series)
  - When to use vs. B-tree
- **Hash indexes:**
  - Equality-only lookups (no range queries)
  - Rarely better than B-tree in modern PostgreSQL
- **HNSW & IVFFlat (pgvector):**
  - Vector similarity search indexes
  - Approximate nearest neighbor (ANN)
  - Distance metrics (L2, cosine, inner product)

#### 2.1.3 Index Management
- When to create indexes (query patterns, not guessing)
- When NOT to index (small tables, low-cardinality columns, write-heavy tables)
- Index bloat detection and mitigation (`REINDEX`, `pg_repack`)
- Concurrent index creation (`CREATE INDEX CONCURRENTLY` — non-blocking)
- Monitoring index usage (`pg_stat_user_indexes`, unused index detection)
- Index maintenance cost (write overhead, storage, vacuum)
- Index selection strategy (analyze query patterns → identify missing indexes → test → measure)

---

### ==Module 2.2: Query Optimization & Performance==
#### ==2.2.1 EXPLAIN & Query Plans==
- `EXPLAIN` output reading (node types, costs, rows, width)
- `EXPLAIN ANALYZE` (actual execution times, row counts, loops)
- `EXPLAIN (ANALYZE, BUFFERS, FORMAT JSON)` (buffer hits/reads, structured output)
- **Scan types:**
  - Sequential Scan (full table scan — not always bad)
  - Index Scan (B-tree lookup + heap fetch)
  - Index Only Scan (no heap fetch — covering index)
  - Bitmap Index Scan + Bitmap Heap Scan (combining multiple indexes)
  - TID Scan (direct tuple access)
- **Join algorithms:**
  - Nested Loop (small tables, indexed lookups)
  - Hash Join (equality joins, medium-large tables)
  - Merge Join (pre-sorted inputs, large tables)
  - When the optimizer chooses each
- **Aggregation:** HashAggregate, GroupAggregate, Sort + Aggregate
- **Sort operations:** External sort (disk-based), quicksort, top-N sort
- Cost model: `seq_page_cost`, `random_page_cost`, `cpu_tuple_cost`, `effective_cache_size`

#### ==2.2.2 Query Optimization Techniques==
- **Index optimization:**
  - Adding missing indexes (based on slow query analysis)
  - Composite index column ordering (selectivity-based)
  - Covering indexes to avoid heap fetches
  - Partial indexes for common WHERE patterns
- **Query rewriting:**
  - `EXISTS` vs. `IN` vs. `JOIN` (performance comparison)
  - Avoiding correlated subqueries (rewrite as JOINs)
  - Predicate pushdown (filtering early)
  - CTE materialization control (`MATERIALIZED`/`NOT MATERIALIZED`)
  - Avoiding `SELECT *` (only needed columns)
  - Avoiding `OFFSET` for pagination (use keyset/cursor pagination)
- **Statistics and planner:**
  - `ANALYZE` (updating table statistics)
  - `pg_stats` (column statistics, most common values, histogram bounds)
  - Extended statistics (`CREATE STATISTICS` — multi-column correlations)
  - Planner hints (`SET enable_seqscan = off` — debugging only, never production)
  - `default_statistics_target` (increasing sample size for skewed data)
- **Connection and resource optimization:**
  - `work_mem` (per-operation memory for sorts, hashes)
  - `shared_buffers` (PostgreSQL buffer pool sizing)
  - `effective_cache_size` (OS page cache hint for planner)
  - `random_page_cost` (adjusting for SSDs — lower than default)
  - Connection pooling (PgBouncer — transaction vs. session mode)

#### 2.2.3 Slow Query Analysis Workflow
1. Enable `log_min_duration_statement` (log queries slower than threshold)
2. Use `pg_stat_statements` (identify top queries by total time, calls, mean time)
3. `EXPLAIN ANALYZE` the slow query
4. Identify the bottleneck (scan type, join algorithm, sort, missing index)
5. Test fix (add index, rewrite query, adjust statistics)
6. Measure improvement (compare before/after execution plans)
7. Monitor ongoing (alert on regression)

---

### ==Module 2.3: Database Internals==
#### ==2.3.1 Storage Engine Internals (PostgreSQL)==
- **Page structure:**
  - 8KB pages (header, item pointers, tuples, free space)
  - Heap tuples (column values, null bitmap, header)
  - CTID (physical tuple identifier)
  - Visibility information (xmin, xmax — which transactions can see this tuple)
- **MVCC (Multi-Version Concurrency Control):**
  - How MVCC works (multiple versions of rows coexist)
  - Transaction IDs (xid), snapshots
  - Tuple visibility rules (is this tuple visible to my transaction?)
  - Phantom reads, non-repeatable reads, dirty reads (which isolation level prevents which)
  - Serializable Snapshot Isolation (SSI)
  - MVCC overhead (dead tuples, bloat)
- **Write-Ahead Logging (WAL):**
  - WAL concept (write log first, then data pages)
  - WAL segments, LSN (Log Sequence Number)
  - Checkpoints (writing dirty pages to disk)
  - `full_page_writes` (preventing torn pages)
  - WAL archiving (for PITR and replication)
  - `synchronous_commit` settings (durability vs. performance)
- **VACUUM:**
  - Why VACUUM exists (reclaiming dead tuples from MVCC)
  - Regular VACUUM (marks space reusable, doesn't return to OS)
  - `VACUUM FULL` (rewrites table, returns space, locks table)
  - Autovacuum (configuration: `autovacuum_vacuum_threshold`, `autovacuum_vacuum_scale_factor`)
  - Transaction ID wraparound (the VACUUM must-run scenario)
  - Monitoring vacuum progress and tuning
  - `pg_repack` (online table rewrite without locks)

#### 2.3.2 Transaction Management
- **ACID properties:**
  - Atomicity (all or nothing — WAL ensures this)
  - Consistency (constraints enforced)
  - Isolation (MVCC provides this)
  - Durability (WAL + fsync ensures this)
- **Isolation levels (deep understanding):**
  - `READ UNCOMMITTED` (PostgreSQL treats as READ COMMITTED)
  - `READ COMMITTED` (default — each statement sees latest committed data)
  - `REPEATABLE READ` (snapshot at transaction start, serialization failure on conflict)
  - `SERIALIZABLE` (SSI — detects dependency cycles, may throw serialization failure)
  - When to use each level (trade-offs: consistency vs. concurrency)
- **Locking:**
  - Row-level locks (FOR UPDATE, FOR SHARE, FOR NO KEY UPDATE, FOR KEY SHARE)
  - Table-level locks (ACCESS SHARE, ROW SHARE, ROW EXCLUSIVE, SHARE UPDATE EXCLUSIVE, SHARE, SHARE ROW EXCLUSIVE, EXCLUSIVE, ACCESS EXCLUSIVE)
  - Advisory locks (application-level, cooperative locking)
  - Deadlock detection (`deadlock_timeout`, deadlock cycle detection)
  - Lock monitoring (`pg_locks`, `pg_stat_activity`, blocked queries)
- **Optimistic vs. pessimistic concurrency:**
  - Optimistic: version column, check-and-set, retry on conflict
  - Pessimistic: `SELECT FOR UPDATE`, row locking
  - When to use each (read-heavy vs. write-contention scenarios)

#### 2.3.3 Other Storage Engine Models (Awareness)
- **InnoDB (MySQL):** Clustered index, buffer pool, redo/undo logs, gap locking
- **LSM Trees (RocksDB, LevelDB, Cassandra):** Write-optimized, compaction, read amplification
- **In-memory engines (Redis, VoltDB):** No disk I/O for reads, persistence options
- **Column-oriented storage (ClickHouse, DuckDB):** Compression, analytical queries
- Comparing storage models (when each excels)

---

### ==Module 2.4: High Availability & Replication==
#### ==2.4.1 PostgreSQL Replication==
- **Streaming replication:**
  - Primary → Standby (async and sync)
  - WAL shipping (continuous archiving)
  - Hot standby (read queries on replicas)
  - Synchronous commit modes (`on`, `remote_apply`, `remote_write`, `local`, `off`)
  - Replication slots (preventing WAL removal before replica catches up)
  - Lag monitoring (`pg_stat_replication`, `replay_lag`)
- **Logical replication:**
  - Publication/subscription model
  - Table-level selective replication
  - Cross-version replication
  - Use cases: zero-downtime upgrades, data distribution, CDC
- **Failover:**
  - Manual failover (`pg_ctl promote`)
  - Automated failover (Patroni, repmgr, pg_auto_failover)
  - Split-brain prevention (fencing, quorum)
  - Failover testing procedures

#### 2.4.2 Backup & Recovery
- **Backup strategies:**
  - `pg_dump` / `pg_dumpall` (logical — portable, slow for large DBs)
  - `pg_basebackup` (physical — fast, full cluster)
  - Continuous archiving + PITR (Point-in-Time Recovery)
  - `pgBackRest` (production-grade: parallel, incremental, differential, compression, encryption)
  - `barman` (alternative backup tool)
- **Recovery procedures:**
  - PITR (restore to specific timestamp)
  - Timeline management
  - Recovery testing (regularly restore backups — untested backups are not backups)
- **Backup scheduling and retention:**
  - RPO (Recovery Point Objective) — how much data can you lose?
  - RTO (Recovery Time Objective) — how fast must you recover?
  - Retention policies (daily, weekly, monthly)
  - Off-site backup storage (S3, GCS)

#### 2.4.3 Connection Pooling
- **PgBouncer:**
  - Modes: session, transaction, statement (trade-offs)
  - Configuration tuning (`max_client_conn`, `default_pool_size`, `pool_mode`)
  - Monitoring (`SHOW STATS`, `SHOW POOLS`, `SHOW CLIENTS`)
  - Authentication pass-through
- **pgcat** (modern alternative — built in Rust)
- **Application-level pooling** (HikariCP, SQLAlchemy pool, asyncpg pool)
- Pool sizing formula: connections = ((core_count * 2) + effective_spindle_count)

---

### ==Module 2.5: NoSQL Databases==
#### ==2.5.1 Redis (Key-Value / Data Structure Store)==
- **Core data types:** Strings, Hashes, Lists, Sets, Sorted Sets, Streams, HyperLogLog, Bitmaps
- **Commands mastery:** `GET/SET`, `HGET/HSET`, `LPUSH/RPUSH/LPOP`, `SADD/SMEMBERS`, `ZADD/ZRANGE`
- **Advanced features:**
  - TTL and expiration (`EXPIRE`, `EXPIREAT`, `PERSIST`)
  - Pub/Sub (real-time messaging)
  - Lua scripting (`EVAL` — atomic multi-command execution)
  - Pipelining (batch commands, reduce round trips)
  - Transactions (`MULTI/EXEC/WATCH`)
  - Streams (append-only log, consumer groups)
- **Persistence:** RDB snapshots, AOF (Append-Only File), hybrid
- **Eviction policies:** `noeviction`, `allkeys-lru`, `volatile-lru`, `allkeys-lfu`, `volatile-ttl`
- **Replication:** Primary-replica, Redis Sentinel (HA), Redis Cluster (sharding)
- **Use cases:** Caching, sessions, leaderboards, rate limiting, distributed locks, pub/sub, queues
- **Anti-patterns:** Using Redis as primary database, large keys, hot keys, unbounded collections

#### ==2.5.2 MongoDB (Document Store)==
- Document model (BSON, flexible schema, embedded documents, references)
- **Schema design patterns:**
  - Embedding vs. referencing (trade-offs: read vs. write, data duplication)
  - Subset pattern, bucket pattern, outlier pattern
  - Extended reference pattern, computed pattern
- **CRUD operations:** `insertOne/Many`, `find`, `updateOne/Many`, `deleteOne/Many`
- **Aggregation pipeline:** `$match`, `$group`, `$project`, `$sort`, `$lookup` (join), `$unwind`, `$facet`
- **Indexing:** Single-field, compound, multikey (array), text, geospatial, TTL, unique
- **Transactions:** Multi-document transactions (4.0+), session-based
- **Replication:** Replica sets (primary, secondaries, arbiters), elections, read preferences
- **Sharding:** Shard key selection (range, hashed), chunks, balancer
- **Change Streams:** Real-time change notifications (CDC for MongoDB)
- **When to use:** Flexible schemas, rapid prototyping, document-centric data, hierarchical data

#### 2.5.3 Elasticsearch (Search Engine)
- **Architecture:** Nodes, indices, shards (primary + replicas), segments
- **Mappings:** Field types, analyzers, tokenizers, filters
- **Indexing:** Document ingestion, bulk API, index lifecycle management (ILM)
- **Search:**
  - Full-text: `match`, `multi_match`, `match_phrase`
  - Term-level: `term`, `range`, `exists`, `prefix`, `wildcard`
  - Bool queries: `must`, `should`, `must_not`, `filter`
  - Aggregations: `terms`, `date_histogram`, `range`, `avg`, `sum`, nested
  - Suggesters: completion, phrase, term
  - Highlighting, pagination (search_after for deep pagination)
- **Relevance:** BM25 scoring, boosting, function scores
- **Performance:** Index optimization, shard sizing, cache management
- **When to use:** Full-text search, log analytics, real-time analytics, autocomplete

#### 2.5.4 Cassandra (Wide-Column Store — Awareness)
- Architecture: peer-to-peer, no single point of failure, tunable consistency
- Data model: keyspaces, tables, partition keys, clustering keys
- CQL (Cassandra Query Language)
- Write path: memtable → SSTable (LSM tree-based)
- Consistency levels (ONE, QUORUM, ALL)
- When to use: massive write throughput, time-series, IoT, geo-distributed

---

### 🗄️ Phase 2 Project: Database Performance Lab
> Build a comprehensive database performance testing and optimization lab:
> - **Performance Test Suite:**
>   - Generate 10M+ rows of realistic data (users, orders, products, reviews)
>   - Write 20+ queries of varying complexity (simple lookups, joins, aggregations, window functions, recursive)
>   - Benchmark each query (timing, buffer hits, disk I/O)
> - **Optimization Exercise:**
>   - Start with no indexes (except PKs)
>   - Analyze slow queries with `EXPLAIN ANALYZE`
>   - Add indexes incrementally (measure impact of each)
>   - Rewrite queries for performance (EXISTS vs IN, JOIN order, CTE materialization)
>   - Document before/after execution plans and timing
>   - Write optimization report (what was slow, why, what fixed it, how much improvement)
> - **Replication Setup:**
>   - Primary + 2 replicas (streaming replication)
>   - Configure read routing (reads from replicas, writes to primary)
>   - Failover test (promote replica, verify continuity)
>   - Monitoring setup (replication lag, connection counts, query stats)
> - **Redis Integration:**
>   - Implement cache-aside pattern for hot data
>   - Session storage with Redis
>   - Rate limiter with Redis sorted sets
>   - Leaderboard with sorted sets
>   - Benchmark: cache hit ratio, latency improvement
> - **Monitoring Dashboard:**
>   - Grafana + Prometheus (pg_exporter, redis_exporter)
>   - Dashboards: query performance, connection pool, replication lag, cache hit ratio
>   - Alerts: slow queries, high connection count, replication lag > 5s
> - **Backup & Recovery:**
>   - pgBackRest setup (full + incremental backups)
>   - PITR test (restore to specific timestamp)
>   - Recovery time measurement
>
> **Why:** Hands-on performance optimization with real data at scale. Covers indexing, query optimization, replication, caching, monitoring, and backup — the core skills that separate good DBAs from great database engineers.

---

### ✅ After Phase 2 — You Can:
- [ ] Read and interpret EXPLAIN ANALYZE output to identify bottlenecks
- [ ] Design optimal indexing strategies (B-tree, GIN, GiST, BRIN, partial, covering)
- [ ] Optimize SQL queries systematically (rewriting, indexing, statistics tuning)
- [ ] Understand PostgreSQL internals (MVCC, WAL, vacuum, page structure)
- [ ] Configure and manage streaming replication and failover
- [ ] Implement backup and recovery with PITR
- [ ] Design and implement Redis caching strategies
- [ ] Model data for MongoDB and design effective aggregation pipelines
- [ ] Build search solutions with Elasticsearch
- [ ] Monitor database performance with Prometheus and Grafana

---
---

## PHASE 3: DISTRIBUTED DATABASES & DATA ARCHITECTURE (Advanced)
*Duration: ~6-12 months + ongoing*

---

### ==Module 3.1: Distributed Database Theory==
#### ==3.1.1 CAP Theorem & Beyond==
- CAP theorem (Consistency, Availability, Partition tolerance — pick 2 under partition)
- PACELC (Partition: Availability/Consistency; Else: Latency/Consistency)
- Consistency models:
  - Strong (linearizable) — all reads see latest write
  - Sequential — all operations appear in some total order
  - Causal — causally related operations ordered correctly
  - Eventual — all replicas converge given no new updates
  - Read-your-writes — see your own writes immediately
  - Monotonic reads — don't see older data after seeing newer
- Practical implications (choosing consistency level per use case)
- Jepsen testing (distributed systems correctness verification — awareness)

#### ==3.1.2 Consensus & Replication==
- **Consensus algorithms:**
  - Raft (leader election, log replication, safety — understand the protocol)
  - Paxos (historical, more complex — conceptual awareness)
  - Multi-Paxos (for replicated state machines)
- **Replication strategies:**
  - Leader-follower (primary-replica)
  - Multi-leader (conflict resolution: LWW, vector clocks, CRDTs)
  - Leaderless (quorum reads/writes, sloppy quorum, hinted handoff — Dynamo-style)
- **Quorum:** W + R > N (ensuring overlap for consistency)
- **Conflict resolution:**
  - Last-Writer-Wins (LWW — simple, data loss risk)
  - Vector clocks (detecting concurrent updates)
  - CRDTs (Conflict-free Replicated Data Types — automatic merge)
  - Application-level merge
- **Split-brain:** Detection, prevention, fencing

#### 3.1.3 Distributed Transactions
- **Two-Phase Commit (2PC):** Prepare → Commit/Abort (blocking, coordinator failure problem)
- **Three-Phase Commit (3PC):** Non-blocking but complex (rarely used)
- **Saga pattern:** Choreography and orchestration (compensating transactions)
- **Outbox pattern:** Reliable event publishing from database
- **Change Data Capture (CDC):** Database log → event stream
- **Why distributed transactions are hard** (and why most systems avoid them)

---

### ==Module 3.2: Partitioning & Sharding==
#### 3.2.1 Table Partitioning (Single Node)
- **PostgreSQL declarative partitioning:**
  - Range partitioning (dates, IDs — most common)
  - List partitioning (status, region, category)
  - Hash partitioning (uniform distribution)
  - Multi-level (sub-partitioning)
- Partition pruning (optimizer skips irrelevant partitions)
- Partition-wise joins and aggregation
- Partition maintenance (creating new, detaching old, archiving)
- When to partition (table size thresholds, query patterns)
- Partitioning vs. indexing (they solve different problems)

#### ==3.2.2 Sharding (Multi-Node)==
- **Sharding strategies:**
  - Hash-based sharding (consistent hashing, modulo)
  - Range-based sharding (date ranges, ID ranges)
  - Geographic sharding (data locality)
  - Directory-based sharding (lookup table)
- **Shard key selection** (the most critical decision):
  - Cardinality (high cardinality required)
  - Distribution (uniform distribution, avoid hotspots)
  - Query patterns (shard key in most queries)
  - Growth pattern (even growth across shards)
- **Cross-shard operations:**
  - Cross-shard queries (scatter-gather)
  - Cross-shard joins (expensive — denormalize to avoid)
  - Cross-shard transactions (2PC or saga)
  - Distributed aggregation
- **Resharding** (adding shards, rebalancing — operational complexity)
- **Sharding middleware:**
  - Vitess (MySQL sharding — used by YouTube, Slack)
  - Citus (PostgreSQL sharding extension — distributed tables)
  - ProxySQL (MySQL proxy with query routing)

---

### ==Module 3.3: Distributed SQL & NewSQL==
#### 3.3.1 CockroachDB
- Architecture: multi-active availability, Raft consensus per range
- Distributed SQL (standard PostgreSQL wire protocol)
- Automatic sharding and rebalancing
- Serializable isolation by default
- Geo-partitioning (pin data to specific regions)
- When to use: global applications, strong consistency, PostgreSQL compatibility

#### 3.3.2 YugabyteDB
- Architecture: DocDB (document storage), Raft per tablet
- PostgreSQL-compatible (YSQL) and Cassandra-compatible (YCQL) APIs
- Distributed transactions, strong consistency
- Geo-distributed clusters
- When to use: PostgreSQL migration to distributed, multi-region

#### 3.3.3 TiDB
- Architecture: TiDB (SQL layer) + TiKV (storage) + PD (placement driver)
- MySQL-compatible
- HTAP (Hybrid Transactional/Analytical Processing) with TiFlash
- When to use: MySQL scale-out, real-time analytics on transactional data

#### 3.3.4 Comparison & Decision Framework
- When to use distributed SQL vs. sharded PostgreSQL vs. NoSQL
- CAP trade-offs per system
- Operational complexity considerations
- Cost analysis (distributed DB vs. vertical scaling vs. read replicas)

---

### ==Module 3.4: Data Streaming & Change Data Capture==
#### ==3.4.1 Change Data Capture (CDC)==
- **Debezium** (open-source CDC platform):
  - PostgreSQL connector (logical decoding)
  - MySQL connector (binlog)
  - MongoDB connector (change streams)
  - Message format (before/after images, operation type)
  - Schema evolution handling
  - Configuration and deployment (Kafka Connect)
- **Use cases:**
  - Materializing read models (CQRS)
  - Elasticsearch indexing (keeping search in sync)
  - Cache invalidation (event-driven cache updates)
  - Cross-service data synchronization
  - Data warehousing (streaming ETL)
  - Audit logging (immutable event stream)

#### 3.4.2 Kafka for Database Engineers
- Kafka as a database log (append-only, partitioned, replicated)
- Log compaction (latest value per key — changelog topic)
- Kafka Connect (source and sink connectors)
- Kafka Streams (stream processing — awareness)
- Event sourcing with Kafka
- Kafka as the source of truth (log-centric architecture)
- Schema Registry (Avro, Protobuf — schema evolution)

#### 3.4.3 Event-Driven Data Architecture
- Outbox pattern implementation:
  - Database table as outbox
  - Polling publisher or CDC-based relay
  - Guaranteed delivery with deduplication
- Event sourcing:
  - Event store design (append-only table, sequence numbers)
  - Projections (materializing read models from events)
  - Snapshots (optimization for long event streams)
  - Event versioning and schema evolution
- CQRS with databases:
  - Write database (normalized, optimized for transactions)
  - Read database (denormalized, optimized for queries — different technology)
  - Sync mechanism (events, CDC, dual-write with outbox)

---

### ==Module 3.5: Data Warehousing & Analytics==
#### 3.5.1 OLTP vs. OLAP
- OLTP characteristics (normalized, row-oriented, many small transactions)
- OLAP characteristics (denormalized, column-oriented, few complex queries)
- Star schema (fact tables + dimension tables)
- Snowflake schema (normalized dimensions)
- Slowly Changing Dimensions (SCD Type 1, 2, 3)
- ETL vs. ELT pipelines

#### 3.5.2 Columnar Databases
- **ClickHouse:**
  - MergeTree engine family
  - Column-oriented storage and compression
  - Materialized views (real-time aggregation)
  - Distributed tables
  - When to use: log analytics, real-time analytics, time-series aggregation
- **DuckDB:**
  - In-process analytical database (SQLite for analytics)
  - Columnar, vectorized execution
  - Parquet, CSV, JSON native support
  - When to use: local analytics, embedded analytics, data exploration
- **Amazon Redshift / Google BigQuery / Snowflake** (cloud data warehouses — awareness):
  - Architecture and storage model
  - Pricing model (compute vs. storage separation)
  - When to use (enterprise analytics, BI workloads)

#### 3.5.3 Data Lake & Lakehouse
- Data lake concept (store everything, query later — S3/GCS/ADLS)
- Table formats: Apache Iceberg, Delta Lake, Apache Hudi
- Lakehouse architecture (lake + warehouse features — ACID on object storage)
- Parquet file format (columnar, compressed, schema evolution)
- When lakehouse vs. traditional warehouse

---

### ==Module 3.6: Cloud Database Services==
#### 3.6.1 AWS Database Services
- **RDS** (managed PostgreSQL, MySQL, MariaDB, Oracle, SQL Server):
  - Multi-AZ (high availability)
  - Read replicas (scaling reads)
  - Performance Insights (query-level monitoring)
  - Automated backups and PITR
- **Aurora** (PostgreSQL/MySQL-compatible, cloud-native):
  - Storage architecture (distributed, auto-scaling)
  - Aurora Serverless v2 (auto-scaling compute)
  - Global Database (cross-region replication)
  - When Aurora vs. RDS
- **DynamoDB** (fully managed NoSQL — key-value/document):
  - Partition key and sort key design
  - GSI and LSI (Global/Local Secondary Indexes)
  - Single-table design patterns
  - DynamoDB Streams (CDC)
  - On-demand vs. provisioned capacity
  - DAX (in-memory caching)
- **ElastiCache** (managed Redis/Memcached)
- **Redshift** (data warehouse — columnar, MPP)
- **DocumentDB** (MongoDB-compatible)
- **Neptune** (graph database)
- **Timestream** (time-series)

#### 3.6.2 GCP & Azure (Awareness)
- **GCP:** Cloud SQL, AlloyDB, Cloud Spanner, Bigtable, Firestore, BigQuery
- **Azure:** Azure SQL, Cosmos DB, Azure Database for PostgreSQL, Azure Synapse

#### 3.6.3 Database Migration to Cloud
- Assessment (compatibility, size, downtime tolerance)
- Migration strategies (dump/restore, DMS, logical replication, CDC)
- AWS DMS (Database Migration Service)
- Zero-downtime migration patterns (dual-write, CDC, blue-green)
- Testing and validation (data integrity, performance comparison)
- Cost optimization (right-sizing, reserved instances, serverless)

---

### ==Module 3.7: Database Security==
#### 3.7.1 Authentication & Authorization
- Password management (`pg_hba.conf`, SCRAM-SHA-256, certificate auth)
- Role-based access control (`GRANT`, `REVOKE`, role hierarchy)
- Row-level security (RLS) policies
- Column-level permissions
- Schema-level isolation
- LDAP/Active Directory integration
- SSL/TLS for connections (client and server certificates)

#### 3.7.2 Data Protection
- Encryption at rest (Transparent Data Encryption, filesystem encryption, cloud KMS)
- Encryption in transit (SSL/TLS, certificate management)
- Column-level encryption (`pgcrypto`, application-level)
- Data masking (static masking for non-prod, dynamic masking)
- Data anonymization techniques (k-anonymity, differential privacy — awareness)
- PII management and GDPR compliance (right to erasure, data portability)

#### 3.7.3 Audit & Compliance
- Audit logging (`pgAudit` extension — statement and object-level auditing)
- Query logging and monitoring
- Change tracking (trigger-based, CDC-based)
- Compliance frameworks (SOC 2, HIPAA, PCI DSS — database implications)
- Vulnerability scanning and hardening (CIS benchmarks for PostgreSQL)

---

### 🗄️ Phase 3 Project: Distributed Data Platform
> Build a multi-database platform with streaming data synchronization:
> - **Primary database:** PostgreSQL (multi-tenant, partitioned by date)
>   - 50M+ rows, realistic data
>   - Table partitioning (monthly partitions for time-series data)
>   - Optimized indexing (B-tree, GIN for JSONB, BRIN for timestamps)
>   - Connection pooling (PgBouncer)
>   - Streaming replication (1 primary + 2 replicas)
>   - Automated failover (Patroni)
> - **CDC Pipeline:**
>   - Debezium capturing changes from PostgreSQL
>   - Kafka as event backbone
>   - Events materializing into:
>     - Elasticsearch (search index — real-time sync)
>     - Redis (cache — invalidation on change)
>     - ClickHouse (analytics — aggregated views)
> - **CQRS Architecture:**
>   - Write path: Application → PostgreSQL
>   - Read path: Application → Elasticsearch (search), Redis (cached), ClickHouse (analytics)
>   - Sync via Debezium → Kafka → consumers
> - **Analytics:**
>   - ClickHouse for real-time dashboards
>   - DuckDB for ad-hoc analysis on Parquet exports
>   - Star schema for reporting
> - **Security:**
>   - RLS policies for multi-tenancy
>   - `pgAudit` for compliance logging
>   - Encrypted connections (SSL/TLS)
>   - Data masking for non-production environments
> - **Monitoring:**
>   - pg_exporter + redis_exporter + Kafka metrics → Prometheus → Grafana
>   - Custom dashboards: query performance, replication lag, CDC lag, cache hit ratio
>   - Alerting: slow queries, failover events, replication lag
> - **Disaster Recovery:**
>   - pgBackRest (full + incremental, encrypted, to S3)
>   - PITR testing (restore to specific timestamp)
>   - Documented runbook for disaster recovery
> - **Documentation:** Architecture diagram, data flow diagram, runbooks, capacity plan
>
> **Why:** This is the database engineering mastery capstone — multi-database architecture, CDC, CQRS, streaming, analytics, security, monitoring, and disaster recovery in one cohesive system.

---

### ✅ After Phase 3 — You Can:
- [ ] Design distributed database architectures with appropriate consistency trade-offs
- [ ] Implement sharding and partitioning strategies for large-scale data
- [ ] Build CDC pipelines with Debezium and Kafka
- [ ] Design CQRS architectures with multiple specialized databases
- [ ] Evaluate and select from distributed SQL options (CockroachDB, YugabyteDB, TiDB)
- [ ] Build analytical data pipelines with columnar databases (ClickHouse, DuckDB)
- [ ] Manage cloud database services (RDS, Aurora, DynamoDB)
- [ ] Implement database security (encryption, RLS, auditing, compliance)
- [ ] Plan and execute disaster recovery with PITR
- [ ] Design and monitor production database infrastructure

---
---

## PHASE 4: AI-ERA DATABASE ENGINEERING
*Duration: ~4-6 months*

---

### ==Module 4.1: Vector Databases & Embeddings==
#### ==4.1.1 Vector Search Fundamentals==
- Embeddings: dense vector representations of data (text, images, audio)
- Distance metrics:
  - Euclidean (L2) — geometric distance
  - Cosine similarity — angle between vectors (normalized)
  - Inner product (dot product) — unnormalized cosine
  - When to use each (normalized vs. unnormalized embeddings)
- Approximate Nearest Neighbor (ANN) algorithms:
  - **HNSW (Hierarchical Navigable Small World):** Graph-based, high recall, fast search, memory-intensive
  - **IVF (Inverted File Index):** Partition-based, trainable, trade-off recall vs. speed
  - **Product Quantization (PQ):** Compression, reduces memory, lossy
  - **Flat/Brute-force:** Exact, slow, baseline for comparison
- Indexing trade-offs: recall vs. speed vs. memory vs. build time

#### ==4.1.2 pgvector (PostgreSQL Extension)==
- Installation and configuration
- Column type: `vector(dimensions)` (e.g., `vector(1536)`)
- Distance operators: `<->` (L2), `<=>` (cosine), `<#>` (inner product)
- **Indexes:**
  - HNSW (`CREATE INDEX ... USING hnsw (embedding vector_cosine_ops)`)
  - IVFFlat (`CREATE INDEX ... USING ivfflat (embedding vector_cosine_ops) WITH (lists = 100)`)
  - Index parameters (HNSW: `m`, `ef_construction`; IVFFlat: `lists`, `probes`)
- Hybrid search: vector similarity + SQL filtering (metadata, permissions, dates)
- Integration with existing PostgreSQL features (joins, CTEs, window functions)
- Performance tuning:
  - `work_mem` for vector operations
  - `maintenance_work_mem` for index building
  - Partitioning vector tables (by tenant, by collection)
  - Approximate vs. exact search (controlling `probes` and `ef_search`)
- When pgvector is enough vs. when to use dedicated vector DB

#### 4.1.3 Dedicated Vector Databases
- **Qdrant:**
  - Architecture (segments, HNSW+quantization, WAL)
  - Collections, points, payloads, filtering
  - Multi-tenancy (payload-based or collection-based)
  - Quantization (scalar, product, binary — memory optimization)
  - Distributed deployment (sharding, replication)
- **Weaviate:**
  - Schema definition, vectorizers, modules
  - Hybrid search (BM25 + vector)
  - Multi-modal (text, image in same vector space)
  - Generative search (built-in RAG)
- **Pinecone, Milvus, Chroma** (awareness — cloud vs. self-hosted trade-offs)
- **Comparison framework:**
  - Managed vs. self-hosted
  - Scalability (billions of vectors)
  - Filtering capabilities (metadata, geo, temporal)
  - Hybrid search support
  - Operational complexity
  - Cost model

#### 4.1.4 RAG Data Architecture
- Document chunking and storage:
  - Chunk storage (vector DB vs. PostgreSQL vs. object storage)
  - Metadata schema design (source, page, section, permissions, tenant)
  - Parent-child relationships between chunks
- Embedding pipeline:
  - Batch embedding (offline ingestion)
  - Real-time embedding (on document creation/update)
  - Embedding model selection and versioning
  - CDC-triggered re-embedding (Debezium → embedding worker → vector store)
- Multi-tenant vector storage (namespace isolation, collection-per-tenant, filtered search)
- Vector index lifecycle management (rebuilding, compaction, upgrades)

---

### ==Module 4.2: Graph Databases==
#### 4.2.1 Graph Database Fundamentals
- Property graph model (nodes, edges, properties, labels)
- Graph vs. relational (when graphs excel: relationship-heavy queries)
- Graph query patterns: traversal, pathfinding, pattern matching
- Use cases: social networks, fraud detection, recommendation engines, knowledge graphs, dependency analysis

#### ==4.2.2 Neo4j==
- **Cypher query language:**
  - Pattern matching: `MATCH (a:Person)-[:KNOWS]->(b:Person)`
  - `CREATE`, `MERGE`, `SET`, `DELETE`
  - Aggregation, sorting, pagination
  - Path operations: `shortestPath`, `allShortestPaths`
  - Variable-length relationships: `-[:KNOWS*1..5]->`
  - `UNWIND`, `WITH`, `CALL` (subqueries)
- **Indexing:** B-tree, full-text, range indexes on node/relationship properties
- **Graph algorithms:**
  - Centrality (PageRank, betweenness, closeness)
  - Community detection (Louvain, label propagation)
  - Pathfinding (Dijkstra, A*)
  - Similarity (node similarity, Jaccard)
- **Graph Data Science (GDS) library**
- **Performance:** Query profiling (`PROFILE`, `EXPLAIN`), index optimization

#### 4.2.3 PostgreSQL as a Graph Database
- Recursive CTEs for graph traversal
- `ltree` extension (hierarchical data)
- `pg_graphql` (GraphQL interface — awareness)
- Apache AGE (graph extension for PostgreSQL — Cypher support)
- When PostgreSQL graph features are sufficient vs. dedicated graph DB

#### 4.2.4 Knowledge Graphs for AI
- Knowledge graph construction (entities, relationships, ontology)
- Graph + Vector hybrid search (GraphRAG pattern)
- Entity extraction → knowledge graph → RAG retrieval
- Neo4j + LangChain integration

---

### ==Module 4.3: Time-Series Databases==
#### 4.3.1 Time-Series Fundamentals
- Time-series data characteristics (append-heavy, time-ordered, often immutable)
- Downsampling and aggregation (rollups, retention policies)
- Compression techniques (delta, gorilla, dictionary encoding)
- Write patterns (high ingest rate, batch writes)
- Query patterns (range scans, aggregation over time windows)

#### 4.3.2 TimescaleDB (PostgreSQL Extension)
- Hypertables (automatic time-based partitioning)
- Continuous aggregates (materialized views that auto-refresh)
- Compression (columnar compression on old data)
- Data retention policies (automatic partition dropping)
- Hyperfunctions (time-weighted averages, percentile calculations)
- Standard SQL (full PostgreSQL compatibility)
- When to use: IoT, monitoring, financial data, event logging

#### 4.3.3 InfluxDB & Prometheus
- **InfluxDB:** Flux query language, TSM storage, retention policies, tasks
- **Prometheus:** Pull-based metrics, PromQL, time-series for monitoring
- **VictoriaMetrics:** Drop-in Prometheus replacement, long-term storage
- Comparison: TimescaleDB vs. InfluxDB vs. Prometheus (SQL vs. specialized)

---

### ==Module 4.4: AI-Powered Database Engineering==
#### 4.4.1 AI for Query Optimization
- AI-driven index recommendation (automated index suggestion based on workload)
- Learned query optimization (ML models predicting query costs — research area)
- Automated performance tuning (PGTune, automated knob tuning)
- Natural language to SQL (Text-to-SQL with LLMs):
  - Schema-aware prompt engineering
  - Few-shot examples with database schema
  - SQL validation and safety checks
  - Tools: `vanna.ai`, custom implementations
- AI-assisted schema design and review

#### 4.4.2 AI for Database Operations
- Anomaly detection in database metrics (query latency, connection count, replication lag)
- Predictive capacity planning (ML-based growth forecasting)
- Automated incident response (detect → diagnose → remediate)
- AI-powered log analysis (pattern recognition in PostgreSQL logs)
- Intelligent backup scheduling (based on change rate, risk assessment)

#### 4.4.3 Databases for AI/ML Workloads
- Feature stores (Feast, Tecton — serving ML features from databases)
- Training data management (versioning, lineage, quality)
- Model metadata storage (experiment tracking, model registry)
- Embedding storage and management at scale
- AI workload patterns (batch inference, real-time inference, training pipelines)

---

### ==Module 4.5: Database Platform Engineering==
#### 4.5.1 Database as a Service (Internal Platform)
- Self-service database provisioning (Terraform, Crossplane, custom operators)
- Database templates and blueprints (standardized configurations)
- Automated database creation, migration, and decommissioning
- Multi-tenant database management
- Cost attribution and showback per team/service

#### 4.5.2 Infrastructure as Code for Databases
- Terraform for database infrastructure (RDS, Aurora, ElastiCache, Elasticsearch)
- Kubernetes operators for databases (CloudNativePG, Zalando Postgres Operator)
- GitOps for database configuration
- Schema migration in CI/CD (Alembic/Flyway + automated testing)

#### 4.5.3 Database Reliability Engineering
- SLOs for databases (availability, latency percentiles, durability)
- Error budgets (balancing reliability with velocity)
- Chaos engineering for databases (failure injection, partition testing)
- Capacity planning and forecasting
- Incident management (runbooks, postmortems, retrospectives)
- On-call procedures for database emergencies
- Game days (practiced disaster recovery)

#### 4.5.4 Future of Databases
- Serverless databases (Aurora Serverless, Neon, PlanetScale, CockroachDB Serverless)
- Edge databases (SQLite at the edge, Turso/libSQL, Durable Objects)
- HTAP (Hybrid Transactional/Analytical Processing — TiDB, AlloyDB)
- AI-native databases (databases designed for AI workloads)
- Disaggregated storage and compute (cloud-native architectures)
- Multi-model databases (single system supporting multiple data models)

---

### 🗄️ Phase 4 Project: AI-Ready Data Platform
> Build a data platform that serves AI/ML workloads:
> - **Vector Search Platform:**
>   - pgvector on PostgreSQL for vector storage and search
>   - Multi-tenant vector collections (isolated per tenant)
>   - HNSW index with tuned parameters
>   - Hybrid search: vector similarity + metadata filtering + full-text (BM25)
>   - Benchmark: recall@10, latency (p50, p95, p99), throughput (QPS)
>   - Comparison: pgvector vs. Qdrant (same dataset, same queries)
> - **Knowledge Graph:**
>   - Neo4j for entity relationships (or Apache AGE on PostgreSQL)
>   - Entity extraction pipeline (from documents → graph)
>   - Graph traversal queries (recommendations, related entities)
>   - GraphRAG pattern: graph context + vector retrieval → LLM
> - **Time-Series Pipeline:**
>   - TimescaleDB for application metrics and AI model performance metrics
>   - Continuous aggregates (hourly, daily rollups)
>   - Data retention (raw: 30 days, aggregated: 1 year)
>   - Grafana dashboards for AI service monitoring
> - **CDC Pipeline for AI:**
>   - Debezium capturing PostgreSQL changes
>   - Kafka pipeline → embedding service → pgvector update
>   - Real-time search index sync (PostgreSQL → Elasticsearch)
>   - Change-triggered re-embedding (content changes → re-embed → update vectors)
> - **Text-to-SQL Service:**
>   - LLM-powered natural language querying over your database
>   - Schema-aware prompt with table/column descriptions
>   - SQL validation and safety checks (read-only, query timeout)
>   - Explain query results in natural language
> - **Monitoring & Operations:**
>   - AI-powered anomaly detection on database metrics
>   - Automated slow query analysis and index recommendation
>   - Capacity forecasting dashboard
>   - Automated backup verification (daily PITR test)
> - **Documentation:**
>   - Data architecture diagram (all databases, data flows, sync mechanisms)
>   - Runbooks for common operations (failover, backup restore, schema migration)
>   - Capacity planning document
>
> **Why:** This project bridges traditional database engineering with AI-era requirements — vector search, knowledge graphs, time-series, CDC for AI, and Text-to-SQL. These are the skills that define the next generation of database engineers.

---

### ✅ After Phase 4 — You Can:
- [ ] Design and operate vector search infrastructure (pgvector, Qdrant)
- [ ] Build hybrid search systems (vector + keyword + metadata filtering)
- [ ] Model and query graph data (Neo4j, recursive CTEs, knowledge graphs)
- [ ] Implement time-series data solutions (TimescaleDB, InfluxDB)
- [ ] Build Text-to-SQL interfaces with LLMs
- [ ] Apply AI for database operations (anomaly detection, tuning, capacity planning)
- [ ] Design data platforms that serve AI/ML workloads
- [ ] Manage database infrastructure as code (Terraform, Kubernetes operators)
- [ ] Define and monitor database SLOs with reliability engineering practices
- [ ] Evaluate and adopt emerging database technologies

---
---

## 📚 ESSENTIAL RESOURCES

### Must-Read Books (In Order)
| Phase | Book | Author |
|-------|------|--------|
| 1 | The Art of PostgreSQL | Dimitri Fontaine |
| 1 | Learning SQL (3rd Ed.) | Alan Beaulieu |
| 1 | SQL Performance Explained | Markus Winand |
| 2 | PostgreSQL 14 Internals | Egor Rogov (free) |
| 2 | Database Internals | Alex Petrov |
| 2 | High Performance MySQL (4th Ed.) | Silvia Botros & Jeremy Tinley |
| 3 | Designing Data-Intensive Applications | Martin Kleppmann |
| 3 | Database Reliability Engineering | Laine Campbell & Charity Majors |
| 3 | Streaming Systems | Akidau, Chernyak, Lax |
| 4 | Graph Databases (2nd Ed.) | Robinson, Webber, Eifrem (free) |
| 4 | AI Engineering | Chip Huyen |

### Key Websites & Documentation
- **[use-the-index-luke.com](https://use-the-index-luke.com/)** — SQL indexing and tuning (essential)
- **[PostgreSQL Documentation](https://www.postgresql.org/docs/)** — The best database docs ever written
- **[pganalyze Blog](https://pganalyze.com/blog)** — PostgreSQL performance deep dives
- **[Percona Blog](https://www.percona.com/blog)** — MySQL, PostgreSQL, MongoDB best practices
- **[Redis University](https://university.redis.com/)** — Free Redis courses
- **[MongoDB University](https://university.mongodb.com/)** — Free MongoDB courses
- **[Explain.dalibo.com](https://explain.dalibo.com/)** — Visual EXPLAIN ANALYZE tool
- **[pgMustard](https://www.pgmustard.com/)** — EXPLAIN plan advisor

### Certifications
```
PostgreSQL:   EDB PostgreSQL Associate/Professional
AWS:          AWS Database Specialty
MongoDB:      MongoDB Associate Developer / DBA
Redis:        Redis Certified Developer
Cloud:        AWS Solutions Architect (database-heavy)
```

### Practice Platforms
| Platform | Focus | Level |
|---|---|---|
| **PostgreSQL Exercises (pgexercises.com)** | SQL practice | Beginner → Intermediate |
| **SQLZoo / SQLBolt** | SQL fundamentals | Beginner |
| **HackerRank SQL** | SQL challenges | All levels |
| **LeetCode Database** | SQL problems | Intermediate |
| **StrataScratch** | Real-world SQL problems | Intermediate → Advanced |
| **Kaggle** | Data analysis with SQL | All levels |
| **MongoDB University** | MongoDB courses + labs | All levels |
| **Redis University** | Redis courses + labs | All levels |
| **CockroachDB University** | Distributed SQL courses | Advanced |

### YouTube Channels
- **Hussein Nasser** — Database internals and concepts
- **CMU Database Group** — Academic database courses (Andy Pavlo)
- **pganalyze** — PostgreSQL performance
- **Percona** — Database administration
- **Citus Data (Microsoft)** — PostgreSQL scaling
- **Neo4j** — Graph database tutorials
- **Timescale** — Time-series database

### Blogs & Newsletters
- **Postgres Weekly** — Weekly PostgreSQL newsletter
- **DB Weekly** — Weekly database newsletter
- **pganalyze Blog** — PostgreSQL performance articles
- **Haki Benita** — Advanced SQL and PostgreSQL techniques
- **Franck Pachot** — Database internals and Oracle/PostgreSQL
- **Brandur Leach** — PostgreSQL best practices
- **CockroachDB Blog** — Distributed systems and databases
- **Timescale Blog** — Time-series and PostgreSQL

### Communities
- **PostgreSQL mailing lists** (pgsql-general, pgsql-performance)
- **Reddit:** r/PostgreSQL, r/database, r/SQL, r/dataengineering
- **Discord:** PostgreSQL, Database Engineering communities
- **Stack Overflow:** postgresql, sql, database-design tags
- **Conferences:** PGConf, Percona Live, re:Invent (database sessions), Data Council

---

## 🗺️ VISUAL ROADMAP SUMMARY

```
PHASE 1 (4-6 mo)           PHASE 2 (6-9 mo)           PHASE 3 (6-12 mo)          PHASE 4 (4-6 mo)
─────────────────────  ─────────────────────────  ─────────────────────────  ─────────────────────────
│ CS Foundations     │  │ Indexing Deep Dive    │  │ Distributed DB       │  │ Vector Databases     │
│   (Trees, Storage) │  │ Query Optimization    │  │   Theory & Practice  │  │ Graph Databases      │
│ Relational Theory  │→ │ Database Internals    │→ │ Sharding &           │→ │ Time-Series DBs      │
│ SQL Mastery        │  │   (MVCC, WAL, Vacuum) │  │   Partitioning       │  │ AI-Powered DB Ops    │
│ PostgreSQL Deep    │  │ HA & Replication      │  │ CDC & Streaming      │  │ DB Platform          │
│ Database Design    │  │ NoSQL (Redis, Mongo,  │  │ Data Warehousing     │  │   Engineering        │
│                    │  │   Elasticsearch)      │  │ Cloud Databases      │  │ Emerging Tech        │
│                    │  │                       │  │ Database Security    │  │                      │
─────────────────────  ─────────────────────────  ─────────────────────────  ─────────────────────────
  🗄️ Schema Design &    🗄️ Performance Lab        🗄️ Distributed Data       🗄️ AI-Ready Data
     Implementation                                  Platform                  Platform
```

---

## 🎯 KEY PRINCIPLES FOR SUCCESS

```
 1. DATA OUTLIVES CODE              — Schemas last decades; applications get rewritten
 2. NORMALIZE FIRST, DENORMALIZE LATER— Understand the rules before you break them
 3. EVERY QUERY NEEDS A PLAN        — Never deploy SQL without EXPLAIN ANALYZE
 4. INDEXES ARE NOT FREE             — They speed reads but slow writes; be intentional
 5. BACKUP OR IT DOESN'T EXIST      — Untested backups are hopes, not backups
 6. MEASURE, DON'T GUESS            — pg_stat_statements is your best friend
 7. NULL IS NOT NOTHING             — Three-valued logic will bite you; understand it
 8. CONNECTIONS ARE EXPENSIVE        — Always use connection pooling in production
 9. THE BEST DATABASE IS THE ONE YOU KNOW— Master one deeply before collecting many
10. DATA MODELING IS A DESIGN SKILL  — The schema IS the architecture; treat it with respect
```

---

> **⏱️ Estimated total time to expert level: 3–5 years of dedicated, consistent effort.**
> Databases are the foundation of every software system. Code changes, frameworks change, architectures change — but **your data model and your data survive.** The best database engineers understand that their decisions echo for years. A missing index costs seconds per query. A bad schema costs months of refactoring. A lost backup costs everything. **Master the fundamentals: relational theory, SQL, indexing, transactions, and PostgreSQL internals.** These haven't changed in 40 years, and they won't change in the next 40. Then build outward: NoSQL for the right use cases, distributed systems when scale demands it, vector databases as AI transforms how we store and query knowledge. **The database engineer who understands *why* things work — not just *how* — is the one who builds systems that last.**