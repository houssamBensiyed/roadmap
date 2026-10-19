# 🍃 THE ULTIMATE SPRING BOOT ROADMAP
### From Zero to Production-Grade Spring Boot Mastery

> **Structure:** Phase → Modules → Sections
> **Estimated Duration:** ~6-10 Months (Dedicated Study)
> **Prerequisites:** Solid Java fundamentals (Phase 0–8 of the Java roadmap), basic SQL, basic HTTP/REST understanding
> *Spring Boot is not just a framework. It's the backbone of enterprise Java. If Java is the language, Spring Boot is the operating system of Java backend development.*

---

## ⚡ PHASE 0 — PREREQUISITES & SPRING ORIENTATION
> *"You cannot learn Spring Boot without understanding what Spring solved. The history IS the lesson."*

---

### 📦 Module 0.1: Understanding the Spring Ecosystem

#### § 0.1.1 — The Problem Before Spring
  - Traditional Java EE / J2EE: heavyweight, XML-heavy, application server-dependent
  - EJBs (Enterprise JavaBeans): complex, over-engineered, hard to test
  - Tight coupling: objects created dependencies with `new` everywhere
  - Configuration hell: hundreds of XML files for simple applications
  - Testing nightmare: required a running application server

#### § 0.1.2 — What Spring Framework Solved
  - Created by Rod Johnson (2003), born from the book *Expert One-on-One J2EE Design and Development*
  - **Inversion of Control (IoC)**: the framework manages object creation
  - **Dependency Injection (DI)**: objects receive their dependencies, don't create them
  - **POJO-based development**: plain Java objects, no framework interfaces to implement
  - **Testability**: DI makes unit testing trivial
  - **Modularity**: pick and choose what you need

#### § 0.1.3 — What Spring Boot Solved
  - Spring Framework still required significant configuration
  - Spring Boot (2014, by Pivotal/VMware): "opinionated defaults + auto-configuration"
  - **Convention over configuration**: sensible defaults, override when needed
  - **Auto-configuration**: detects classpath and configures beans automatically
  - **Embedded servers**: no WAR deployment, just `java -jar`
  - **Starter dependencies**: curated dependency sets (`spring-boot-starter-web`)
  - **Production-ready**: Actuator for monitoring, externalized configuration

#### § 0.1.4 — The Spring Ecosystem Map
  - **Spring Framework** — core (IoC, DI, AOP, MVC)
  - **Spring Boot** — rapid application development
  - **Spring Data** — database access (JPA, MongoDB, Redis, etc.)
  - **Spring Security** — authentication & authorization
  - **Spring Cloud** — microservices (config, discovery, gateway, circuit breaker)
  - **Spring WebFlux** — reactive/non-blocking web
  - **Spring Batch** — batch processing
  - **Spring Integration** — enterprise integration patterns
  - **Spring Session** — distributed sessions
  - **Spring AMQP / Kafka** — messaging
  - **Spring GraphQL** — GraphQL support
  - **Spring AI** — AI/ML integration (emerging)

#### § 0.1.5 — Spring Boot Version History
  - **Spring Boot 1.x** (2014) — the beginning
  - **Spring Boot 2.x** (2018) — Spring Framework 5, reactive support, Java 8+ baseline
  - **Spring Boot 3.0** (2022) — Java 17+ baseline, Jakarta EE 9+ (`javax` → `jakarta`), GraalVM native support, Observability
  - **Spring Boot 3.1-3.4+** (2023-2025) — virtual threads support, enhanced Testcontainers, SSL bundle management, RestClient
  - Always use the latest Spring Boot 3.x for new projects

---

### 📦 Module 0.2: Java Prerequisites Checklist

#### § 0.2.1 — Must-Know Java Concepts
  - OOP: classes, interfaces, abstract classes, inheritance, polymorphism
  - Generics: `List<T>`, bounded types, wildcards
  - Annotations: `@Override`, custom annotations, retention policies
  - Functional programming: lambdas, `Stream` API, `Optional`
  - Collections Framework: `List`, `Map`, `Set`, `Queue`
  - Exception handling: checked vs unchecked, try-with-resources
  - Concurrency basics: threads, `ExecutorService`, `CompletableFuture`
  - Records, sealed classes, pattern matching (Java 17+)

#### § 0.2.2 — Must-Know Non-Java Concepts
  - HTTP protocol: methods, status codes, headers, body
  - REST API design: resources, verbs, status codes
  - JSON format: structure, data types
  - SQL basics: SELECT, INSERT, UPDATE, DELETE, JOINs, indexes
  - Relational database concepts: tables, primary keys, foreign keys, normalization
  - Git: branching, committing, pushing, pull requests
  - Terminal / command line basics

---

### 📦 Module 0.3: Setting Up the Development Environment

#### § 0.3.1 — JDK Installation
  - Java 17+ required for Spring Boot 3.x (Java 21 recommended)
  - Eclipse Temurin (Adoptium) or Amazon Corretto
  - Verify: `java --version` (must be 17+)

#### § 0.3.2 — IDE Selection
  - **IntelliJ IDEA Ultimate** — best Spring Boot experience (Spring-specific features, bean navigation, configuration assistance)
  - **IntelliJ IDEA Community** — works but lacks Spring-specific features
  - **VS Code + Spring Boot Extension Pack** — lightweight alternative
  - **Eclipse + Spring Tool Suite (STS)** — free, Spring-focused
  - Strong recommendation: IntelliJ Ultimate (free for students, 30-day trial)

#### § 0.3.3 — Build Tool Selection
  - **Gradle (Kotlin DSL)** — faster, more flexible, modern (recommended for new projects)
  - **Maven** — widely used, XML-based, extensive ecosystem
  - Both work perfectly with Spring Boot
  - This roadmap will reference both, prefer Gradle

#### § 0.3.4 — Spring Initializr
  - **start.spring.io** — the official project generator
  - Select: Spring Boot version, language, build tool, packaging, Java version
  - Add dependencies: what starters to include
  - Generate, download, import into IDE
  - CLI alternative: `spring init` command or IntelliJ's built-in Spring Initializr

#### § 0.3.5 — Essential Tools
  - **Postman** / **Insomnia** / **Bruno** — API testing
  - **curl** / **httpie** — command-line HTTP
  - **Docker Desktop** — for databases, infrastructure
  - **DBeaver** / **DataGrip** — database management
  - **Git** — version control

> ### 🛠️ Phase 0 Project: **"Hello Spring Boot"**
> Create your first Spring Boot application from start.spring.io:
> - Generate a project with: Spring Web, Spring Boot DevTools, Lombok
> - Create a simple REST endpoint that returns a greeting
> - Explore the generated project structure: `main`, `test`, `resources`
> - Explore `application.properties` — change the server port
> - Run the application from IDE, from CLI with `./gradlew bootRun`, and as a JAR with `java -jar`
> - Access the endpoint with curl, browser, and Postman
> - Enable DevTools auto-restart: modify code, see it reload
> - Read the auto-generated `pom.xml` / `build.gradle.kts` and understand every dependency

---

## ⚡ PHASE 1 — SPRING CORE: IoC, DI & THE BEAN LIFECYCLE
> *"If you don't understand Dependency Injection, you don't understand Spring. Period."*

---

### 📦 Module 1.1: Inversion of Control (IoC) Container

#### § 1.1.1 — What is IoC
  - Traditional: your code creates dependencies (`new ServiceImpl()`)
  - IoC: the container/framework creates and provides dependencies
  - You define WHAT you need, Spring decides HOW and WHEN to create it
  - The `ApplicationContext` — Spring's IoC container

#### § 1.1.2 — The Application Context
  - `ApplicationContext` — the central interface to the Spring IoC container
  - `AnnotationConfigApplicationContext` — annotation-based configuration
  - `SpringApplication.run()` — bootstraps the context in Spring Boot
  - Context hierarchy: parent-child contexts (rarely used directly)
  - Context events: `ContextRefreshedEvent`, `ContextClosedEvent`

---

### 📦 Module 1.2: Dependency Injection — Deep Dive

#### § 1.2.1 — Types of Dependency Injection
  - **Constructor injection** — dependencies provided via constructor (RECOMMENDED)
    - Immutable: fields can be `final`
    - Testable: easy to pass mocks
    - Fail-fast: missing dependency = startup error
    - No `@Autowired` needed (single constructor auto-detected since Spring 4.3)
  - **Setter injection** — dependencies provided via setter methods
    - Use case: optional dependencies
    - `@Autowired` required on setter
  - **Field injection** — `@Autowired` directly on fields
    - Convenient but discouraged: untestable without reflection, hides dependencies
    - Cannot make fields `final`
    - Still used in tests and prototypes

#### § 1.2.2 — Why Constructor Injection Wins
  - Immutability: `private final` fields
  - Explicit dependencies: constructor signature IS the dependency list
  - No circular dependencies possible (fails at startup)
  - No reflection needed (faster startup)
  - Framework-agnostic: plain Java constructor works without Spring
  - Spring team officially recommends constructor injection

#### § 1.2.3 — Resolving Ambiguity
  - Multiple beans of the same type → `NoUniqueBeanDefinitionException`
  - `@Primary` — mark one bean as the default
  - `@Qualifier("beanName")` — specify which bean by name
  - Custom qualifier annotations: create your own `@Qualifier` annotation
  - `@Profile` — activate beans based on environment

---

### 📦 Module 1.3: Bean Definition & Registration

#### § 1.3.1 — Stereotype Annotations (Component Scanning)
  - `@Component` — generic Spring-managed bean
  - `@Service` — business logic layer (semantic, same as `@Component`)
  - `@Repository` — data access layer (adds exception translation)
  - `@Controller` — web layer (Spring MVC)
  - `@RestController` — web layer for REST APIs (`@Controller` + `@ResponseBody`)
  - `@Configuration` — configuration class (defines `@Bean` methods)
  - Component scanning: `@ComponentScan` (auto-included by `@SpringBootApplication`)

#### § 1.3.2 — Java-Based Configuration (`@Bean`)
  - `@Configuration` class with `@Bean` methods
  - Each `@Bean` method returns an instance managed by Spring
  - Method name = bean name (customizable)
  - Parameters in `@Bean` methods are auto-injected by Spring
  - Use case: third-party library classes you can't annotate, complex initialization
  - `@Bean` vs `@Component`: `@Bean` for external classes, `@Component` for your own classes

#### § 1.3.3 — Bean Naming & Aliases
  - Default name: class name in camelCase (`UserService` → `userService`)
  - Custom name: `@Component("customName")`
  - Aliases: `@Bean(name = {"bean1", "alias1"})` — multiple names for one bean

---

### 📦 Module 1.4: Bean Scopes

#### § 1.4.1 — Standard Scopes
  - `@Scope("singleton")` — one instance per ApplicationContext (DEFAULT)
  - `@Scope("prototype")` — new instance every time it's requested
  - Singleton is the default — most beans should be singletons (stateless services)

#### § 1.4.2 — Web Scopes (Web Applications Only)
  - `@RequestScope` — one instance per HTTP request
  - `@SessionScope` — one instance per HTTP session
  - `@ApplicationScope` — one instance per `ServletContext`
  - Scoped proxies: injecting a request-scoped bean into a singleton

#### § 1.4.3 — Scope Gotchas
  - Injecting a shorter-lived bean into a longer-lived bean (prototype into singleton)
  - Solution: `ObjectFactory<T>`, `ObjectProvider<T>`, or `@Scope(proxyMode = ...)`
  - `ObjectProvider<T>` — lazy, optional bean lookup (preferred approach)

---

### 📦 Module 1.5: Bean Lifecycle

#### § 1.5.1 — Lifecycle Phases
  - Instantiation → Dependency Injection → Initialization → Ready → Destruction
  - `@PostConstruct` — runs after DI is complete (initialization logic)
  - `@PreDestroy` — runs before bean is destroyed (cleanup logic)
  - `InitializingBean.afterPropertiesSet()` — Spring-specific callback (avoid, prefer `@PostConstruct`)
  - `DisposableBean.destroy()` — Spring-specific callback (avoid, prefer `@PreDestroy`)
  - `@Bean(initMethod = "init", destroyMethod = "cleanup")` — external classes

#### § 1.5.2 — Bean Post-Processors
  - `BeanPostProcessor` — intercept bean creation (before and after initialization)
  - `BeanFactoryPostProcessor` — modify bean definitions before instantiation
  - How AOP, `@Transactional`, `@Async` work: through proxies created by post-processors
  - Understanding: you rarely write custom post-processors, but you must understand the concept

---

### 📦 Module 1.6: Configuration & Externalized Properties

#### § 1.6.1 — `application.properties` & `application.yml`
  - Key-value configuration in `src/main/resources/`
  - YAML support: hierarchical, cleaner for complex configuration
  - `server.port=8080`, `spring.datasource.url=...`
  - Property precedence: command line → environment variables → application.properties → defaults

#### § 1.6.2 — Accessing Configuration Values
  - `@Value("${property.name}")` — inject single property
  - `@Value("${property.name:default}")` — with default value
  - SpEL expressions: `@Value("#{systemProperties['java.version']}")`
  - `Environment` object: `env.getProperty("key")`

#### § 1.6.3 — `@ConfigurationProperties` (Type-Safe Configuration)
  - Bind a group of properties to a POJO/record
  - `@ConfigurationProperties(prefix = "app.mail")`
  - `@EnableConfigurationProperties(MailProperties.class)` or `@ConfigurationPropertiesScan`
  - Validation with Bean Validation: `@NotBlank`, `@Min`, `@Max` on fields
  - Records as configuration properties (Java 17+): immutable config
  - Nested properties, lists, maps
  - Relaxed binding: `app.mail-host`, `APP_MAIL_HOST`, `app.mailHost` all map to `mailHost`

#### § 1.6.4 — Profiles
  - `application-dev.yml`, `application-prod.yml`, `application-test.yml`
  - Activate: `spring.profiles.active=dev` (env var, CLI, or properties)
  - `@Profile("dev")` — beans active only in specific profiles
  - Profile groups (Spring Boot 2.4+): `spring.profiles.group.prod=prod,metrics`
  - Default profile: `spring.profiles.default=dev`

#### § 1.6.5 — Advanced Configuration
  - `@PropertySource` — load additional property files
  - Configuration trees (Kubernetes): `spring.config.import=configtree:/etc/config/`
  - Config import: `spring.config.import=optional:file:./external.yml`
  - Encrypted properties: Jasypt, Spring Vault
  - `@ConditionalOnProperty` — conditional bean creation based on properties

---

### 📦 Module 1.7: Spring AOP (Aspect-Oriented Programming)

#### § 1.7.1 — AOP Concepts
  - Cross-cutting concerns: logging, security, transactions, caching
  - **Aspect**: the module that implements cross-cutting concern
  - **Join point**: a point during execution (method call)
  - **Advice**: the action taken at a join point (before, after, around)
  - **Pointcut**: expression that matches join points
  - **Proxy**: the object created by AOP to wrap the target

#### § 1.7.2 — AOP in Spring
  - `@Aspect` + `@Component` — define an aspect
  - `@Before("execution(* com.example.service.*.*(..))")` — before advice
  - `@After` — after advice (always runs)
  - `@AfterReturning` — after successful return
  - `@AfterThrowing` — after exception
  - `@Around` — most powerful: wraps the method call completely
  - Pointcut expressions: `execution`, `within`, `@annotation`, `bean`
  - Custom annotations as pointcut markers: `@LogExecutionTime`

#### § 1.7.3 — How Spring AOP Works (Proxies)
  - **JDK Dynamic Proxy**: for interfaces (default when interface exists)
  - **CGLIB Proxy**: for classes (default in Spring Boot — `spring.aop.proxy-target-class=true`)
  - Self-invocation problem: calling `this.method()` bypasses the proxy (no AOP applied!)
  - Solution: inject self, use `AopContext.currentProxy()`, or restructure code
  - Understanding proxies is essential for: `@Transactional`, `@Cacheable`, `@Async`, `@Secured`

> ### 🛠️ Phase 1 Project: **"SpringCore Playground"**
> Build an application that demonstrates every Spring Core concept:
> - Multiple beans with different scopes: singleton service, prototype helper
> - Constructor injection throughout (no field injection)
> - `@Primary` and `@Qualifier` for resolving multiple implementations of an interface
> - `@ConfigurationProperties` with a `record` for type-safe app config
> - Profile-specific beans: `@Profile("dev")` with mock data, `@Profile("prod")` with real data
> - Bean lifecycle: `@PostConstruct` to log startup info, `@PreDestroy` for cleanup
> - Custom AOP aspect: `@LogExecutionTime` annotation that measures and logs method execution time
> - Custom AOP aspect: `@RateLimit` annotation that limits how often a method can be called
> - Demonstrate the self-invocation proxy problem and its solution
> - Externalized configuration: load from `application.yml`, environment variables, and command-line arguments
> - Verify everything with `@SpringBootTest` integration test

---

## ⚡ PHASE 2 — BUILDING REST APIs
> *"Spring MVC is the most battle-tested REST framework in the Java ecosystem."*

---

### 📦 Module 2.1: Spring MVC Architecture

#### § 2.1.1 — How Spring MVC Works
  - `DispatcherServlet` — front controller: receives ALL requests
  - Handler mapping: determines which controller handles the request
  - Handler adapter: invokes the controller method
  - View resolver: resolves the response (JSON, HTML, etc.)
  - For REST APIs: `@RestController` short-circuits view resolution → returns data directly

#### § 2.1.2 — The Request Processing Flow
  - HTTP Request → DispatcherServlet → Handler Mapping → Interceptors → Controller → Service → Repository → Response
  - Filters (Servlet level) → Interceptors (Spring level) → Controller advice → Controller

---

### 📦 Module 2.2: Controllers & Request Handling

#### § 2.2.1 — Defining Controllers
  - `@RestController` — REST API controller (`@Controller` + `@ResponseBody`)
  - `@RequestMapping("/api/v1/users")` — base path for all endpoints
  - `@GetMapping`, `@PostMapping`, `@PutMapping`, `@PatchMapping`, `@DeleteMapping`
  - Method-level path: `@GetMapping("/{id}")`

#### § 2.2.2 — Request Parameters
  - `@PathVariable` — extract from URL path: `/users/{id}`
  - `@RequestParam` — query parameters: `/users?name=Alice&page=1`
  - `@RequestParam(required = false, defaultValue = "0")` — optional with default
  - `@RequestHeader` — extract HTTP headers
  - `@CookieValue` — extract cookies
  - `@RequestBody` — deserialize JSON request body to Java object
  - `@RequestPart` — multipart file upload

#### § 2.2.3 — Response Handling
  - Return objects directly → auto-serialized to JSON (Jackson)
  - `ResponseEntity<T>` — full control over status code, headers, body
  - `ResponseEntity.ok(body)`, `ResponseEntity.created(uri).body(body)`
  - `ResponseEntity.noContent().build()`, `ResponseEntity.notFound().build()`
  - `@ResponseStatus(HttpStatus.CREATED)` — annotation-level status code
  - Void returns with `@ResponseStatus`

#### § 2.2.4 — Content Negotiation
  - `Accept` header determines response format
  - Default: JSON (Jackson auto-configured)
  - XML support: add `jackson-dataformat-xml` dependency
  - `produces = MediaType.APPLICATION_JSON_VALUE` — restrict response type
  - `consumes = MediaType.APPLICATION_JSON_VALUE` — restrict request type

---

### 📦 Module 2.3: Request Validation

#### § 2.3.1 — Bean Validation (Jakarta Validation)
  - `spring-boot-starter-validation` dependency
  - `@Valid` / `@Validated` on `@RequestBody` parameter → triggers validation
  - Field annotations: `@NotNull`, `@NotBlank`, `@NotEmpty`, `@Size`, `@Min`, `@Max`, `@Email`, `@Pattern`, `@Positive`, `@Past`, `@Future`
  - Nested validation: `@Valid` on nested objects
  - Validation groups: different rules for create vs update

#### § 2.3.2 — Custom Validators
  - Create annotation + `ConstraintValidator<A, T>` implementation
  - Cross-field validation: class-level annotation
  - `@Validated` on method parameters for `@PathVariable` / `@RequestParam` validation
  - Programmatic validation: `Validator.validate(object)`

#### § 2.3.3 — Handling Validation Errors
  - `MethodArgumentNotValidException` — thrown when `@Valid` fails
  - `ConstraintViolationException` — thrown when `@Validated` fails on params
  - Custom error response format (handled in exception handling phase)

---

### 📦 Module 2.4: DTOs & Object Mapping

#### § 2.4.1 — Why DTOs (Data Transfer Objects)
  - Separation of API contract from domain/entity model
  - Control exactly what data is exposed
  - Different DTOs for create, update, response
  - Prevent over-posting/under-posting vulnerabilities

#### § 2.4.2 — DTO Strategies
  - Records as DTOs: `record CreateUserRequest(String name, String email) {}`
  - Request DTO vs Response DTO vs Entity — clear separation
  - Nested DTOs for complex responses

#### § 2.4.3 — Object Mapping
  - **Manual mapping**: explicit conversion methods (simplest, most maintainable)
  - **MapStruct**: compile-time code generation (fastest, recommended for complex mapping)
  - **ModelMapper**: runtime reflection-based (slower, more magical)
  - MapStruct: `@Mapper(componentModel = "spring")` — integrates as a Spring bean
  - Why many teams prefer manual mapping: clarity, debuggability, no magic

---

### 📦 Module 2.5: Jackson (JSON Processing)

#### § 2.5.1 — Jackson Fundamentals
  - Auto-configured by Spring Boot
  - Serialization: Java object → JSON (using getters)
  - Deserialization: JSON → Java object (using setters or constructor)
  - Records work out of the box with Jackson

#### § 2.5.2 — Jackson Annotations
  - `@JsonProperty("name")` — custom field name in JSON
  - `@JsonIgnore` — exclude field from serialization
  - `@JsonIgnoreProperties(ignoreUnknown = true)` — ignore unknown JSON fields
  - `@JsonInclude(Include.NON_NULL)` — exclude null fields
  - `@JsonFormat(pattern = "yyyy-MM-dd")` — date format
  - `@JsonCreator` + `@JsonProperty` — custom deserialization constructor
  - `@JsonSerialize`, `@JsonDeserialize` — custom serializers/deserializers

#### § 2.5.3 — Global Jackson Configuration
  - `application.yml`: `spring.jackson.default-property-inclusion: non_null`
  - `spring.jackson.date-format`, `spring.jackson.time-zone`
  - Custom `ObjectMapper` bean for advanced configuration
  - `Jackson2ObjectMapperBuilder` — Spring Boot's customization point
  - Modules: `JavaTimeModule` for Java 8+ date/time (auto-registered)

---

### 📦 Module 2.6: File Upload & Download

#### § 2.6.1 — File Upload
  - `@RequestParam("file") MultipartFile file` — single file
  - `@RequestParam("files") List<MultipartFile> files` — multiple files
  - `multipart.max-file-size`, `multipart.max-request-size` — size limits
  - Storing files: local filesystem, cloud storage (S3)

#### § 2.6.2 — File Download
  - `Resource` return type with `Content-Disposition` header
  - `InputStreamResource`, `ByteArrayResource`
  - Streaming large files without loading into memory

---

### 📦 Module 2.7: RestClient & HTTP Clients

#### § 2.7.1 — Calling External APIs
  - `RestClient` (Spring Boot 3.2+) — modern, fluent, synchronous HTTP client (recommended)
  - `RestTemplate` — legacy synchronous client (maintenance mode)
  - `WebClient` — reactive/async client (from WebFlux, can be used in MVC)
  - `@HttpExchange` interfaces (Spring 6+) — declarative HTTP clients (like Feign)

#### § 2.7.2 — RestClient Usage
  - Creating: `RestClient.builder().baseUrl("...").build()`
  - GET, POST, PUT, DELETE operations
  - Request/response body conversion
  - Error handling: `onStatus()`, `StatusHandler`
  - Timeouts, interceptors, default headers

> ### 🛠️ Phase 2 Project: **"BookStore API — A Complete CRUD REST API"**
> Build a bookstore management REST API:
> - **Entities**: Book, Author, Category, Publisher (as records/DTOs, no database yet)
> - **Endpoints**:
>   - CRUD for all entities
>   - Search books by title, author, category
>   - Filter books by price range, publication year
>   - Pagination and sorting via query parameters
> - **Validation**: all create/update requests validated with Bean Validation
> - **Custom validator**: ISBN format validator (`@ValidISBN`)
> - **DTOs**: separate `CreateBookRequest`, `UpdateBookRequest`, `BookResponse` records
> - **Object mapping**: MapStruct or manual mapper
> - **Jackson**: custom date format, exclude nulls, rename fields
> - **File operations**: upload book cover image, download cover
> - **External API**: fetch book details from Open Library API using `RestClient`
> - **Error responses**: structured error format for validation failures
> - Test all endpoints with Postman/Bruno collection

---

## ⚡ PHASE 3 — DATA ACCESS WITH SPRING DATA JPA
> *"Spring Data JPA eliminates 80% of boilerplate database code. The other 20% is where the expertise lives."*

---

### 📦 Module 3.1: JPA & Hibernate Fundamentals

#### § 3.1.1 — What is JPA
  - JPA (Jakarta Persistence API) — specification for ORM in Java
  - Hibernate — the most popular JPA implementation (Spring Boot default)
  - Spring Data JPA — abstraction layer on top of JPA (repositories, query methods)
  - Stack: Spring Data JPA → JPA API → Hibernate → JDBC → Database

#### § 3.1.2 — Entity Mapping
  - `@Entity` — marks a class as a JPA entity (database table)
  - `@Table(name = "users")` — custom table name
  - `@Id` — primary key
  - `@GeneratedValue(strategy = GenerationType.IDENTITY)` — auto-increment
  - `@Column(name = "email", nullable = false, unique = true, length = 255)` — column config
  - `@Enumerated(EnumType.STRING)` — store enums as strings (NEVER use ORDINAL)
  - `@CreationTimestamp`, `@UpdateTimestamp` — auto-managed timestamps
  - `@Transient` — field not persisted to database

#### § 3.1.3 — Entity Relationships
  - `@OneToOne` — one-to-one (e.g., User ↔ Profile)
  - `@OneToMany` / `@ManyToOne` — one-to-many (e.g., User → Orders)
  - `@ManyToMany` — many-to-many (e.g., Students ↔ Courses)
  - `@JoinColumn(name = "user_id")` — foreign key column
  - `@JoinTable` — junction table for many-to-many
  - Cascade types: `CascadeType.ALL`, `PERSIST`, `MERGE`, `REMOVE` — propagate operations
  - Orphan removal: `orphanRemoval = true` — delete orphaned child entities
  - Bidirectional vs unidirectional relationships
  - `mappedBy` — the non-owning side of a bidirectional relationship

#### § 3.1.4 — Fetch Types & the N+1 Problem
  - `FetchType.LAZY` — load related entities on demand (DEFAULT for collections)
  - `FetchType.EAGER` — load related entities immediately (DEFAULT for single entities)
  - **N+1 problem**: loading a list of entities triggers N additional queries for related data
  - Solution: `JOIN FETCH` in JPQL, `@EntityGraph`, `@BatchSize`
  - Golden rule: always use `LAZY` fetching, explicitly fetch what you need

---

### 📦 Module 3.2: Spring Data Repositories

#### § 3.2.1 — Repository Interfaces
  - `JpaRepository<T, ID>` — full CRUD + JPA-specific (flush, batch)
  - `CrudRepository<T, ID>` — basic CRUD
  - `PagingAndSortingRepository<T, ID>` — pagination and sorting
  - `ListCrudRepository<T, ID>` — returns `List` instead of `Iterable`
  - Just define the interface — Spring Data generates the implementation at runtime

#### § 3.2.2 — Derived Query Methods (Method Name Queries)
  - `findByEmail(String email)` → `SELECT * FROM users WHERE email = ?`
  - `findByNameContainingIgnoreCase(String name)` → `LIKE %name%` (case-insensitive)
  - `findByAgeBetween(int min, int max)` → `WHERE age BETWEEN ? AND ?`
  - `findByStatusOrderByCreatedAtDesc(Status status)` → `WHERE status = ? ORDER BY created_at DESC`
  - `countByStatus(Status status)`, `existsByEmail(String email)`, `deleteByStatus(Status status)`
  - Keywords: `And`, `Or`, `Is`, `Not`, `Between`, `LessThan`, `GreaterThan`, `Like`, `In`, `After`, `Before`, `Null`, `NotNull`, `OrderBy`, `Top`, `First`

#### § 3.2.3 — `@Query` — Custom Queries
  - JPQL: `@Query("SELECT u FROM User u WHERE u.email = :email")`
  - Native SQL: `@Query(value = "SELECT * FROM users WHERE email = ?1", nativeQuery = true)`
  - Named parameters: `:paramName` with `@Param("paramName")`
  - Modifying queries: `@Modifying @Query("UPDATE User u SET u.status = :status WHERE u.id = :id")`
  - Projections: return specific fields, not entire entities

#### § 3.2.4 — Pagination & Sorting
  - `Pageable` parameter: `Page<User> findByStatus(Status status, Pageable pageable)`
  - `PageRequest.of(page, size, Sort.by("name").ascending())`
  - `Page<T>`: content, total elements, total pages, page number
  - `Slice<T>`: content + has next (more efficient for infinite scrolling)
  - Controller integration: `@PageableDefault(size = 20, sort = "name")`

#### § 3.2.5 — Specifications (Dynamic Queries)
  - `JpaSpecificationExecutor<T>` — add to repository interface
  - `Specification<T>` — composable query predicates
  - Building dynamic queries: `spec1.and(spec2).or(spec3)`
  - Use case: complex search/filter pages with optional criteria
  - Type-safe criteria building with JPA Metamodel

---

### 📦 Module 3.3: Transaction Management

#### § 3.3.1 — `@Transactional` Fundamentals
  - `@Transactional` — marks a method (or class) as transactional
  - Default: REQUIRED propagation, rollback on unchecked exceptions only
  - Place on service layer methods, NOT on repositories or controllers
  - Read-only optimization: `@Transactional(readOnly = true)` — hints to Hibernate and JDBC

#### § 3.3.2 — Transaction Propagation
  - `REQUIRED` (default) — join existing or create new
  - `REQUIRES_NEW` — always create new (suspend existing)
  - `SUPPORTS` — join if exists, non-transactional otherwise
  - `MANDATORY` — must be called within existing transaction
  - `NOT_SUPPORTED` — suspend existing, run non-transactional
  - `NEVER` — throw exception if transaction exists

#### § 3.3.3 — Rollback Rules
  - Default: rollback on unchecked exceptions (`RuntimeException`), commit on checked
  - `rollbackFor = Exception.class` — rollback on ALL exceptions
  - `noRollbackFor = SomeException.class` — don't rollback for specific exception
  - **Critical**: `@Transactional` works through proxies — self-invocation bypasses it!

#### § 3.3.4 — Transaction Best Practices
  - Keep transactions short and focused
  - Don't perform external HTTP calls inside transactions
  - Use `readOnly = true` for read-only operations
  - Watch out for `LazyInitializationException` outside of transaction scope
  - Open Session in View: `spring.jpa.open-in-view=false` (disable it — it's an anti-pattern)

---

### 📦 Module 3.4: Database Setup & Migrations

#### § 3.4.1 — Database Configuration
  - H2 (in-memory): development and testing
  - PostgreSQL / MySQL: production
  - `spring.datasource.url`, `spring.datasource.username`, `spring.datasource.password`
  - Connection pooling: HikariCP (default, fastest)
  - HikariCP tuning: `maximum-pool-size`, `minimum-idle`, `connection-timeout`

#### § 3.4.2 — Schema Management
  - `spring.jpa.hibernate.ddl-auto`: `none`, `validate`, `update`, `create`, `create-drop`
  - Development: `update` (convenient) or `validate` + migrations (safer)
  - Production: **always `validate`** + Flyway/Liquibase migrations
  - NEVER use `update` or `create` in production

#### § 3.4.3 — Flyway (Database Migrations)
  - `spring-boot-starter-flyway` — add dependency, it auto-runs
  - Migration files: `V1__Create_users_table.sql`, `V2__Add_email_column.sql`
  - Location: `src/main/resources/db/migration/`
  - Naming convention: `V{version}__{description}.sql`
  - Flyway tracks applied migrations in `flyway_schema_history` table
  - Repeatable migrations: `R__Create_views.sql`
  - Best practice: always use Flyway/Liquibase, never rely on `ddl-auto`

---

### 📦 Module 3.5: Auditing

#### § 3.5.1 — JPA Auditing
  - `@EnableJpaAuditing` — enable auditing support
  - `@CreatedDate`, `@LastModifiedDate` — auto-managed timestamps
  - `@CreatedBy`, `@LastModifiedBy` — auto-managed user info
  - `AuditorAware<String>` — provides current user (integrate with Spring Security)
  - `@MappedSuperclass` — base entity with common audit fields
  - `@EntityListeners(AuditingEntityListener.class)` — activate on entity

> ### 🛠️ Phase 3 Project: **"BookStore API v2 — Database-Backed"**
> Evolve the BookStore API to use a real database:
> - **Database**: PostgreSQL via Docker (`docker-compose.yml`)
> - **Entities**: `Book`, `Author`, `Category`, `Publisher`, `Review` with full JPA relationships
>   - Author ↔ Book: ManyToMany
>   - Category → Book: OneToMany
>   - Book → Review: OneToMany
> - **Repositories**: Spring Data JPA with derived queries and `@Query`
> - **Advanced queries**:
>   - Search books by title, author name, category (Specification-based dynamic filtering)
>   - Pagination and sorting on all list endpoints
> - **Transactions**: `@Transactional` on service layer, `readOnly` for reads
> - **Migrations**: Flyway for all schema changes (minimum 5 migration files)
> - **Auditing**: `createdAt`, `updatedAt`, `createdBy` on all entities
> - **N+1 prevention**: `@EntityGraph` or `JOIN FETCH` for eager loading
> - **DTOs**: Entity → DTO mapping, never expose entities directly
> - **Test**: H2 in-memory database for integration tests, PostgreSQL for development
> - Disable `open-in-view`

---

## ⚡ PHASE 4 — EXCEPTION HANDLING & API DESIGN
> *"How your API handles errors is more important than how it handles success."*

---

### 📦 Module 4.1: Global Exception Handling

#### § 4.1.1 — `@RestControllerAdvice`
  - Centralized exception handling for all controllers
  - `@ExceptionHandler(ExceptionType.class)` — handle specific exceptions
  - Return structured error response with appropriate status code
  - Order matters: most specific exception handler wins

#### § 4.1.2 — Standard Error Response Structure
  - Consistent error format across the entire API
  - RFC 7807 Problem Details: `type`, `title`, `status`, `detail`, `instance`
  - `ProblemDetail` class (Spring 6+) — built-in RFC 7807 support
  - Custom fields: `timestamp`, `errors` (validation), `path`, `traceId`

#### § 4.1.3 — Handling Common Exceptions
  - `MethodArgumentNotValidException` → 400 with field-level errors
  - `ConstraintViolationException` → 400 with parameter errors
  - `HttpMessageNotReadableException` → 400 (malformed JSON)
  - `NoHandlerFoundException` → 404
  - `HttpRequestMethodNotSupportedException` → 405
  - `DataIntegrityViolationException` → 409 (unique constraint, FK violation)
  - Custom business exceptions → appropriate status codes
  - `Exception` (catch-all) → 500 with generic message (never expose stack traces!)

#### § 4.1.4 — Custom Business Exceptions
  - `ResourceNotFoundException` → 404
  - `BusinessRuleViolationException` → 422
  - `ConflictException` → 409
  - `ForbiddenException` → 403
  - Base exception class with error code, message, HTTP status
  - Exception hierarchy for your domain

---

### 📦 Module 4.2: API Design Best Practices

#### § 4.2.1 — Resource Design
  - Nouns, not verbs: `/users`, not `/getUsers`
  - Plural resource names: `/users`, not `/user`
  - Nested resources: `/users/{userId}/orders`
  - Resource identifiers: prefer UUIDs over auto-increment IDs in URLs
  - Maximum nesting depth: 2 levels (`/users/{id}/orders`, not deeper)

#### § 4.2.2 — Status Code Usage
  - `200 OK` — successful GET, PUT, PATCH
  - `201 Created` — successful POST (include `Location` header)
  - `204 No Content` — successful DELETE
  - `400 Bad Request` — validation errors, malformed request
  - `401 Unauthorized` — not authenticated
  - `403 Forbidden` — authenticated but not authorized
  - `404 Not Found` — resource doesn't exist
  - `409 Conflict` — duplicate, constraint violation
  - `422 Unprocessable Entity` — valid syntax but business rule violation
  - `429 Too Many Requests` — rate limited
  - `500 Internal Server Error` — unexpected server error

#### § 4.2.3 — Pagination Response Format
  - Page metadata: `page`, `size`, `totalElements`, `totalPages`
  - Links: `self`, `first`, `last`, `next`, `prev`
  - Cursor-based pagination for large datasets (more performant)

#### § 4.2.4 — API Versioning
  - URL path (recommended): `/api/v1/users`
  - Header: `Accept: application/vnd.api.v1+json`
  - Strategy: maintain old version, deprecate, sunset

#### § 4.2.5 — HATEOAS (Overview)
  - Hypermedia As The Engine Of Application State
  - `spring-boot-starter-hateoas`
  - `EntityModel<T>`, `CollectionModel<T>`, `Link`
  - `WebMvcLinkBuilder` — generate links dynamically
  - Richardson Maturity Model: Level 0 → 3
  - Practical reality: few APIs implement full HATEOAS

---

### 📦 Module 4.3: API Documentation

#### § 4.3.1 — SpringDoc OpenAPI (Swagger)
  - `springdoc-openapi-starter-webmvc-ui` dependency
  - Auto-generated documentation at `/swagger-ui.html`
  - OpenAPI spec at `/v3/api-docs`
  - `@Operation(summary = "Get user by ID", description = "...")`
  - `@ApiResponse(responseCode = "200", description = "...")`
  - `@Schema(description = "User email", example = "user@example.com")`
  - `@Parameter`, `@RequestBody` annotations for detailed docs
  - Grouping endpoints: `@Tag(name = "Users")`
  - Global configuration: `OpenApiCustomizer` bean
  - Security scheme documentation: JWT, API keys

---

### 📦 Module 4.4: Filters, Interceptors & Request Processing

#### § 4.4.1 — Servlet Filters
  - `OncePerRequestFilter` — base class for custom filters
  - Use case: logging, CORS, request/response modification, authentication
  - `FilterRegistrationBean` — register and order filters
  - Filter execution order: `@Order` annotation

#### § 4.4.2 — Spring Interceptors
  - `HandlerInterceptor` — `preHandle`, `postHandle`, `afterCompletion`
  - Registered via `WebMvcConfigurer.addInterceptors()`
  - Use case: logging, timing, locale, tenant identification
  - Interceptors vs Filters: interceptors have access to handler info

#### § 4.4.3 — CORS Configuration
  - `@CrossOrigin` — controller/method level
  - `WebMvcConfigurer.addCorsMappings()` — global CORS
  - `CorsFilter` — filter-based CORS (for Spring Security integration)
  - Configuration: allowed origins, methods, headers, credentials, max age

> ### 🛠️ Phase 4 Project: **"BookStore API v3 — Production-Grade Error Handling & Docs"**
> Evolve the BookStore API:
> - **Global exception handler**: `@RestControllerAdvice` using `ProblemDetail` (RFC 7807)
> - **Custom exceptions**: `BookNotFoundException`, `DuplicateISBNException`, `InsufficientStockException`
> - **Validation error response**: field-level errors with field name, rejected value, message
> - **API documentation**: SpringDoc OpenAPI with Swagger UI
>   - Every endpoint documented with `@Operation`, `@ApiResponse`
>   - Every DTO field documented with `@Schema`
>   - Authentication scheme documented
> - **Request logging filter**: log method, path, status, duration for every request
> - **Request ID**: generate UUID per request, include in all log lines and error responses
> - **CORS**: configured for frontend integration
> - **API versioning**: `/api/v1/` prefix
> - **Pagination**: standardized page response format with metadata
> - All error scenarios tested with integration tests

---

## ⚡ PHASE 5 — SPRING SECURITY
> *"Security is not a feature. It's a requirement. And Spring Security is its most complex module."*

---

### 📦 Module 5.1: Spring Security Fundamentals

#### § 5.1.1 — Security Architecture
  - `SecurityFilterChain` — the core configuration (replaces deprecated `WebSecurityConfigurerAdapter`)
  - Filter chain: ordered list of security filters
  - `DelegatingFilterProxy` → `FilterChainProxy` → Security Filters
  - Key filters: `UsernamePasswordAuthenticationFilter`, `BasicAuthenticationFilter`, `BearerTokenAuthenticationFilter`, `AuthorizationFilter`

#### § 5.1.2 — Authentication vs Authorization
  - **Authentication**: WHO are you? (identity verification)
  - **Authorization**: WHAT can you do? (permission checking)
  - `Authentication` object: holds principal, credentials, authorities
  - `SecurityContext` → `SecurityContextHolder` — thread-local storage of auth info

#### § 5.1.3 — Security Configuration
  - `@Configuration` class with `@Bean SecurityFilterChain`
  - `http.csrf()`, `http.cors()`, `http.sessionManagement()`
  - `http.authorizeHttpRequests()` — define access rules
  - `requestMatchers("/public/**").permitAll()`
  - `requestMatchers("/admin/**").hasRole("ADMIN")`
  - `anyRequest().authenticated()` — everything else requires auth

---

### 📦 Module 5.2: Authentication Methods

#### § 5.2.1 — UserDetailsService
  - `UserDetailsService` interface: load user by username
  - `UserDetails` — represents the authenticated user (username, password, authorities)
  - Custom implementation: load from database
  - `PasswordEncoder` — `BCryptPasswordEncoder` (always hash passwords!)
  - `DaoAuthenticationProvider` — authenticates using `UserDetailsService` + `PasswordEncoder`

#### § 5.2.2 — JWT Authentication
  - Stateless authentication: no server-side session
  - JWT structure: Header.Payload.Signature (Base64 encoded)
  - Token generation: user login → validate credentials → generate JWT
  - Token validation: every request → extract JWT → validate signature & expiry → set authentication
  - Refresh tokens: short-lived access token + long-lived refresh token
  - Custom JWT filter extending `OncePerRequestFilter`
  - Libraries: `io.jsonwebtoken:jjwt` or `com.auth0:java-jwt` or `nimbus-jose-jwt`
  - Token storage on client: `Authorization: Bearer <token>` header
  - Never store JWTs in localStorage (XSS risk) — use httpOnly cookies

#### § 5.2.3 — OAuth2 / OpenID Connect
  - `spring-boot-starter-oauth2-client` — OAuth2 login (social login)
  - `spring-boot-starter-oauth2-resource-server` — protect API with OAuth2 tokens
  - OAuth2 login with Google, GitHub, Okta, Keycloak
  - Resource server: validate JWT tokens from external identity provider
  - `JwtDecoder` configuration for token validation
  - OIDC (OpenID Connect): extends OAuth2 with identity layer

---

### 📦 Module 5.3: Authorization

#### § 5.3.1 — URL-Based Authorization
  - `requestMatchers("/api/admin/**").hasRole("ADMIN")`
  - `requestMatchers(HttpMethod.DELETE, "/api/**").hasAuthority("DELETE_PRIVILEGE")`
  - Order matters: first match wins
  - `permitAll()`, `authenticated()`, `hasRole()`, `hasAuthority()`, `hasAnyRole()`

#### § 5.3.2 — Method-Level Security
  - `@EnableMethodSecurity` — enable method-level authorization
  - `@PreAuthorize("hasRole('ADMIN')")` — SpEL expression before method execution
  - `@PostAuthorize("returnObject.owner == authentication.name")` — after method
  - `@PreAuthorize("#id == authentication.principal.id or hasRole('ADMIN')")` — complex rules
  - `@Secured("ROLE_ADMIN")` — simpler, less flexible
  - Custom security expressions

#### § 5.3.3 — Role vs Authority
  - **Role**: high-level (ADMIN, USER, MODERATOR) — prefixed with `ROLE_`
  - **Authority/Permission**: fine-grained (READ_USER, WRITE_USER, DELETE_USER)
  - Role hierarchy: `RoleHierarchy` bean — ADMIN > MODERATOR > USER
  - Best practice: use authorities for fine-grained control

---

### 📦 Module 5.4: Security Best Practices

#### § 5.4.1 — CSRF Protection
  - CSRF enabled by default (stateful apps with sessions)
  - Disable for stateless REST APIs with JWT: `.csrf(csrf -> csrf.disable())`
  - SameSite cookies for CSRF protection

#### § 5.4.2 — Security Headers
  - `Content-Security-Policy`, `X-Content-Type-Options`, `X-Frame-Options`
  - Spring Security adds security headers by default
  - HTTPS enforcement: `requiresChannel().anyRequest().requiresSecure()`

#### § 5.4.3 — Password Security
  - BCrypt for password hashing (adaptive, salted)
  - Never store plaintext passwords
  - Password strength validation
  - Account lockout after failed attempts
  - Rate limiting on login endpoints

#### § 5.4.4 — Common Vulnerabilities
  - SQL injection: parameterized queries (JPA handles this)
  - XSS: output encoding (Thymeleaf auto-escapes)
  - CORS misconfiguration
  - Mass assignment / over-posting (use DTOs!)
  - Sensitive data exposure (never log passwords, tokens)
  - Insecure direct object references (IDOR): check authorization per resource

> ### 🛠️ Phase 5 Project: **"BookStore API v4 — Secured"**
> Add comprehensive security:
> - **User management**: registration, login, profile
> - **Password**: BCrypt hashing, validation (min length, complexity)
> - **JWT authentication**: access token (15 min) + refresh token (7 days)
> - **Custom JWT filter**: validate token, set `SecurityContext`
> - **Roles**: USER, ADMIN
> - **URL authorization**: public (search, view books), authenticated (reviews, orders), admin (CRUD books, manage users)
> - **Method-level security**: `@PreAuthorize` — users can only edit their own reviews
> - **CSRF disabled** (stateless API)
> - **CORS configured** for frontend
> - **Security headers** configured
> - **Account lockout**: lock after 5 failed login attempts
> - **Tests**: security integration tests — test authorized, unauthorized, forbidden scenarios
> - **OpenAPI**: security scheme documented in Swagger

---

## ⚡ PHASE 6 — TESTING SPRING BOOT APPLICATIONS
> *"Spring Boot has the most comprehensive testing support of any Java framework."*

---

### 📦 Module 6.1: Testing Fundamentals

#### § 6.1.1 — Testing Pyramid in Spring Boot
  - **Unit tests**: no Spring context, mock dependencies (fastest)
  - **Slice tests**: partial Spring context, test one layer (`@WebMvcTest`, `@DataJpaTest`)
  - **Integration tests**: full Spring context (`@SpringBootTest`)
  - Ratio: many unit tests, moderate slice tests, few integration tests

#### § 6.1.2 — Testing Dependencies
  - `spring-boot-starter-test` — includes JUnit 5, Mockito, AssertJ, Hamcrest, JSONPath
  - JUnit 5 (`@Test`, `@BeforeEach`, `@DisplayName`, `@Nested`, `@ParameterizedTest`)
  - Mockito (`@Mock`, `@InjectMocks`, `when().thenReturn()`, `verify()`)
  - AssertJ (`assertThat(actual).isEqualTo(expected)` — fluent assertions)

---

### 📦 Module 6.2: Unit Testing

#### § 6.2.1 — Testing Service Layer
  - No Spring context needed — plain JUnit + Mockito
  - `@ExtendWith(MockitoExtension.class)` — initialize mocks
  - `@Mock` — mock repository/external dependencies
  - `@InjectMocks` — inject mocks into service under test
  - Test business logic in isolation
  - Verify interactions: `verify(repo, times(1)).save(any())`

#### § 6.2.2 — Testing Utilities
  - `ArgumentCaptor<T>` — capture arguments passed to mocks
  - `@Spy` — partial mocking (real methods + overrides)
  - `doThrow()`, `doAnswer()` — mock void methods
  - BDD Mockito: `given().willReturn()`, `then().should()`

---

### 📦 Module 6.3: Slice Tests (Test Annotations)

#### § 6.3.1 — `@WebMvcTest` — Testing Controllers
  - Loads only web layer: controllers, filters, advice, Jackson
  - Does NOT load: services, repositories, full application context
  - `MockMvc` — perform HTTP requests without a real server
  - `mockMvc.perform(get("/api/users/{id}", 1))` — simulate GET
  - `.andExpect(status().isOk())`, `.andExpect(jsonPath("$.name").value("Alice"))`
  - `@MockBean` — mock service dependencies (injected into Spring context)
  - Testing: validation, serialization, status codes, error handling

#### § 6.3.2 — `@DataJpaTest` — Testing Repositories
  - Loads only JPA layer: entities, repositories, Flyway, embedded database
  - Auto-configures H2 in-memory database (by default)
  - `TestEntityManager` — insert test data
  - `@Sql` — execute SQL scripts before tests
  - Tests: custom queries, specifications, pagination, constraints
  - Transaction: each test auto-rolled back

#### § 6.3.3 — `@JsonTest` — Testing JSON Serialization
  - `JacksonTester<T>` — test serialization and deserialization
  - Test custom Jackson configuration, date formats, null handling

#### § 6.3.4 — Other Slice Annotations
  - `@RestClientTest` — testing `RestClient` / `RestTemplate` calls
  - `@JdbcTest` — testing JDBC-based repositories
  - `@JooqTest` — testing jOOQ queries

---

### 📦 Module 6.4: Integration Testing

#### § 6.4.1 — `@SpringBootTest` — Full Integration
  - Loads the ENTIRE application context
  - `@SpringBootTest(webEnvironment = WebEnvironment.RANDOM_PORT)` — real HTTP server
  - `TestRestTemplate` — HTTP client for integration tests
  - `WebTestClient` — reactive/WebFlux-compatible test client
  - `@ActiveProfiles("test")` — use test-specific configuration

#### § 6.4.2 — Testcontainers
  - `spring-boot-testcontainers` — first-class support (Spring Boot 3.1+)
  - Run real databases in Docker for integration tests
  - `@Container` + `@Testcontainers` — JUnit 5 integration
  - `@ServiceConnection` (Spring Boot 3.1+) — auto-configure datasource from container
  - `PostgreSQLContainer`, `MySQLContainer`, `KafkaContainer`, `RedisContainer`
  - `@DynamicPropertySource` — inject container properties (older approach)

#### § 6.4.3 — Test Configuration
  - `@TestConfiguration` — additional beans for tests only
  - `@TestPropertySource` — override properties for tests
  - `application-test.yml` — test-specific config
  - `@Import(TestConfig.class)` — import test configuration

---

### 📦 Module 6.5: Testing Spring Security

#### § 6.5.1 — Security Test Support
  - `@WithMockUser(roles = "ADMIN")` — run test as authenticated user
  - `@WithAnonymousUser` — run test as anonymous
  - `@WithUserDetails("username")` — load real user from `UserDetailsService`
  - `SecurityMockMvcRequestPostProcessors.jwt()` — mock JWT token
  - Testing: access control, authentication flows, CSRF

---

### 📦 Module 6.6: Testing Best Practices

#### § 6.6.1 — Test Organization
  - Mirror the source directory structure in test directory
  - Naming: `UserServiceTest`, `UserControllerWebMvcTest`, `UserRepositoryDataJpaTest`
  - Test data builders: reusable methods/classes for creating test entities
  - `@Nested` — group related tests within a test class

#### § 6.6.2 — What to Test
  - Service layer: ALL business logic (unit tests)
  - Controller layer: request mapping, validation, serialization, error handling (WebMvcTest)
  - Repository layer: custom queries, specifications (DataJpaTest)
  - Integration: critical user journeys end-to-end (SpringBootTest)
  - Security: authorized and unauthorized access patterns

> ### 🛠️ Phase 6 Project: **"BookStore API v5 — Fully Tested"**
> Add comprehensive testing to the BookStore API:
> - **Unit tests** (Mockito):
>   - All service methods with mocked repositories
>   - Test business logic: validation, calculations, edge cases
>   - `ArgumentCaptor` for verifying saved entities
> - **`@WebMvcTest`** (Controller tests):
>   - All endpoints: success, validation error, not found, forbidden
>   - Test JSON serialization/deserialization
>   - Test with `@WithMockUser` for security
> - **`@DataJpaTest`** (Repository tests):
>   - Custom query methods, specifications
>   - Pagination and sorting
>   - Constraint violations
> - **`@SpringBootTest`** (Integration tests):
>   - Full CRUD flow with Testcontainers (PostgreSQL)
>   - Authentication flow: register → login → access protected endpoint
>   - Error scenarios end-to-end
> - **Coverage**: 80%+ line coverage (JaCoCo report)
> - **Test data**: builder pattern for creating test entities
> - **CI**: GitHub Actions running all tests on every push

---

## ⚡ PHASE 7 — CACHING, ASYNC & SCHEDULING
> *"Not everything needs to happen synchronously. Not everything needs to hit the database."*

---

### 📦 Module 7.1: Caching

#### § 7.1.1 — Spring Cache Abstraction
  - `@EnableCaching` — enable caching support
  - `@Cacheable("cacheName")` — cache method result
  - `@CacheEvict("cacheName")` — remove from cache
  - `@CachePut("cacheName")` — update cache
  - `@Caching` — combine multiple cache operations
  - Cache key: method parameters by default, custom `key` SpEL expression
  - Conditional caching: `condition`, `unless`

#### § 7.1.2 — Cache Providers
  - `ConcurrentMapCacheManager` — default (simple, in-memory, not for production)
  - **Caffeine** — high-performance local cache (recommended for single-node)
  - **Redis** — distributed cache (recommended for multi-node)
  - `spring-boot-starter-cache` + `spring-boot-starter-data-redis`
  - Cache configuration: TTL, max size, eviction policy

#### § 7.1.3 — Redis Integration
  - `spring-boot-starter-data-redis`
  - `RedisTemplate<K, V>` — low-level Redis operations
  - `StringRedisTemplate` — string-specific operations
  - Redis as cache: `RedisCacheManager`, `RedisCacheConfiguration`
  - TTL configuration per cache
  - Redis Pub/Sub for cache invalidation across instances
  - Redis data structures: String, Hash, List, Set, Sorted Set
  - Lettuce vs Jedis: Lettuce is the default (reactive, thread-safe)

---

### 📦 Module 7.2: Asynchronous Processing

#### § 7.2.1 — `@Async` — Asynchronous Methods
  - `@EnableAsync` — enable async support
  - `@Async` — execute method in a separate thread
  - Return types: `void`, `Future<T>`, `CompletableFuture<T>`
  - Custom thread pool: `@Async("customExecutor")` + `Executor` bean
  - Default: `SimpleAsyncTaskExecutor` (creates new thread per task — bad for production!)
  - Always define a custom `ThreadPoolTaskExecutor` bean

#### § 7.2.2 — `CompletableFuture` Integration
  - `@Async` methods returning `CompletableFuture`
  - `CompletableFuture.supplyAsync()` in service methods
  - Composing: `thenApply`, `thenCompose`, `thenCombine`
  - Error handling: `exceptionally`, `handle`

#### § 7.2.3 — Virtual Threads (Spring Boot 3.2+)
  - `spring.threads.virtual.enabled=true` — enable virtual threads
  - All request handling automatically uses virtual threads
  - Massive scalability for I/O-bound workloads
  - No code changes needed — transparent integration
  - Limitations: don't use with CPU-bound or `synchronized` blocks

---

### 📦 Module 7.3: Scheduling

#### § 7.3.1 — `@Scheduled` — Task Scheduling
  - `@EnableScheduling` — enable scheduling support
  - `@Scheduled(fixedRate = 5000)` — every 5 seconds
  - `@Scheduled(fixedDelay = 5000)` — 5 seconds after last completion
  - `@Scheduled(cron = "0 0 * * * *")` — every hour (cron expression)
  - `@Scheduled(initialDelay = 10000)` — delay before first execution
  - `zone` attribute for timezone-aware cron
  - Externalize cron: `@Scheduled(cron = "${app.cleanup.cron}")`

#### § 7.3.2 — Distributed Scheduling
  - Single-node `@Scheduled` is fine for simple cases
  - Multi-node: ShedLock for distributed lock on scheduled tasks
  - ShedLock: ensures only one instance runs the task (database or Redis lock)
  - Alternative: Quartz Scheduler for complex scheduling needs

---

### 📦 Module 7.4: Events

#### § 7.4.1 — Spring Application Events
  - `ApplicationEvent` — custom event class (or just POJO in Spring 4.2+)
  - `ApplicationEventPublisher.publishEvent(event)` — publish
  - `@EventListener` — handle events (synchronous by default)
  - `@Async @EventListener` — handle events asynchronously
  - `@TransactionalEventListener(phase = AFTER_COMMIT)` — execute after transaction commits
  - Use case: decoupling services, audit logging, notifications, cache invalidation
  - Custom events: `UserRegisteredEvent`, `OrderPlacedEvent`, `PaymentCompletedEvent`

> ### 🛠️ Phase 7 Project: **"BookStore API v6 — Performance & Background Jobs"**
> Add caching, async, and scheduling:
> - **Caching**: Caffeine cache for book lookups, category lists
>   - `@Cacheable` on frequently accessed queries
>   - `@CacheEvict` on create/update/delete
>   - Cache TTL: 10 minutes for books, 1 hour for categories
> - **Redis**: Redis cache for session data and rate limiting
> - **Async**: email sending (mock), report generation as async tasks
>   - Custom `ThreadPoolTaskExecutor` with proper queue and pool sizes
>   - Return `CompletableFuture<Report>` for report generation
> - **Scheduling**:
>   - Daily cache warmup at midnight
>   - Hourly expired session cleanup
>   - Weekly sales report generation
>   - ShedLock for distributed locking
> - **Events**:
>   - `BookCreatedEvent`, `OrderPlacedEvent` → async listeners
>   - `@TransactionalEventListener` for sending notifications after order commits
> - **Virtual threads** enabled for request handling
> - Test all async/scheduled behavior

---

## ⚡ PHASE 8 — MESSAGING & REAL-TIME
> *"In distributed systems, synchronous HTTP calls are the exception. Messaging is the rule."*

---

### 📦 Module 8.1: Apache Kafka

#### § 8.1.1 — Kafka Fundamentals
  - Topics: named channels for messages
  - Partitions: parallel processing within a topic
  - Producers: send messages to topics
  - Consumers: read messages from topics
  - Consumer groups: scale consumption, each partition consumed by one consumer per group
  - Offset: position in the partition log

#### § 8.1.2 — Spring Kafka Integration
  - `spring-boot-starter-kafka` — auto-configuration
  - `KafkaTemplate<K, V>` — produce messages
  - `@KafkaListener(topics = "order-events")` — consume messages
  - JSON serialization: `JsonSerializer` / `JsonDeserializer`
  - Error handling: `DefaultErrorHandler`, `DeadLetterPublishingRecoverer`
  - Retry: configure retry attempts and backoff
  - Manual acknowledgment: `AckMode.MANUAL`
  - Transactional messaging: exactly-once semantics

#### § 8.1.3 — Kafka Design Patterns
  - Event-driven architecture: publish domain events
  - Event sourcing: events as the source of truth
  - Saga pattern: distributed transactions via events
  - Outbox pattern: reliable event publishing with database transactions

---

### 📦 Module 8.2: RabbitMQ

#### § 8.2.1 — RabbitMQ Fundamentals
  - Exchanges: route messages (direct, topic, fanout, headers)
  - Queues: store messages
  - Bindings: rules connecting exchanges to queues
  - Message acknowledgment: manual vs auto

#### § 8.2.2 — Spring AMQP Integration
  - `spring-boot-starter-amqp` — auto-configuration
  - `RabbitTemplate` — send messages
  - `@RabbitListener(queues = "order-queue")` — consume messages
  - Exchange and queue declaration via `@Bean`
  - JSON message conversion: `Jackson2JsonMessageConverter`
  - Dead letter exchange: handle failed messages
  - Retry with exponential backoff

---

### 📦 Module 8.3: WebSocket & SSE

#### § 8.3.1 — WebSocket with STOMP
  - `spring-boot-starter-websocket`
  - STOMP over WebSocket: messaging protocol
  - `@EnableWebSocketMessageBroker` — enable WebSocket messaging
  - `@MessageMapping` — handle incoming messages
  - `SimpMessagingTemplate` — send messages to subscribers
  - Use case: real-time notifications, chat, live dashboards

#### § 8.3.2 — Server-Sent Events (SSE)
  - `SseEmitter` — push events from server to client
  - Simpler than WebSocket for one-way server → client communication
  - Use case: live feeds, progress updates, notifications

> ### 🛠️ Phase 8 Project: **"BookStore API v7 — Event-Driven"**
> Add messaging and real-time features:
> - **Kafka integration**:
>   - Publish `OrderPlacedEvent` when order is created
>   - `InventoryService` consumes events and updates stock
>   - `NotificationService` consumes events and sends notifications
>   - Dead letter topic for failed messages
>   - Retry with exponential backoff
> - **Outbox pattern**: store events in database, publish to Kafka in a reliable way
> - **WebSocket**: real-time order status updates
>   - Client subscribes to `/topic/orders/{orderId}/status`
>   - Status changes broadcast to subscribers
> - **SSE**: live activity feed of recent orders
> - **Docker Compose**: add Kafka (with Zookeeper/KRaft) and Redis to the stack
> - **Integration tests**: embedded Kafka for testing producers and consumers

---

## ⚡ PHASE 9 — MONITORING, LOGGING & OBSERVABILITY
> *"You can't fix what you can't see. Observability is not optional in production."*

---

### 📦 Module 9.1: Spring Boot Actuator

#### § 9.1.1 — Actuator Fundamentals
  - `spring-boot-starter-actuator` — production-ready features
  - Health endpoint: `/actuator/health` — application health status
  - Info endpoint: `/actuator/info` — application info
  - Metrics endpoint: `/actuator/metrics` — application metrics
  - Environment: `/actuator/env` — configuration properties
  - Beans: `/actuator/beans` — all Spring beans
  - Mappings: `/actuator/mappings` — all request mappings

#### § 9.1.2 — Health Indicators
  - Auto-configured: database, disk space, Redis, Kafka, mail
  - Custom health indicators: implement `HealthIndicator`
  - Health groups: `/actuator/health/readiness`, `/actuator/health/liveness`
  - Kubernetes probes: liveness → is the app running? Readiness → can it accept traffic?
  - `management.endpoint.health.show-details=always` — show full health info

#### § 9.1.3 — Custom Actuator Endpoints
  - `@Endpoint(id = "custom")` — custom actuator endpoint
  - `@ReadOperation`, `@WriteOperation`, `@DeleteOperation`
  - Security: expose only necessary endpoints, protect with Spring Security

---

### 📦 Module 9.2: Structured Logging

#### § 9.2.1 — Logging in Spring Boot
  - SLF4J + Logback (default) — the logging standard
  - Log levels: TRACE → DEBUG → INFO → WARN → ERROR
  - `LoggerFactory.getLogger(ClassName.class)` or Lombok's `@Slf4j`
  - Parameterized logging: `log.info("User {} logged in from {}", username, ip)`
  - Never concatenate strings in log calls: `log.info("User " + name)` — BAD
  - Log configuration: `application.yml` or `logback-spring.xml`
  - Profile-specific logging: `<springProfile name="prod">...</springProfile>`

#### § 9.2.2 — Structured Logging (JSON)
  - Structured logging: log as JSON for machine parsing
  - `logstash-logback-encoder` — JSON log output
  - MDC (Mapped Diagnostic Context): add request-scoped context to all log lines
  - `MDC.put("requestId", uuid)` in filter → all logs include `requestId`
  - Correlation IDs for request tracing across services

---

### 📦 Module 9.3: Metrics & Monitoring

#### § 9.3.1 — Micrometer (Metrics Facade)
  - Micrometer: metrics facade (like SLF4J for metrics)
  - Auto-configured metrics: JVM, HTTP, database, cache, Kafka
  - Metric types: Counter, Gauge, Timer, Distribution Summary
  - Custom metrics: `meterRegistry.counter("orders.placed").increment()`
  - `@Timed` — measure method execution time
  - Tags/labels for dimensional metrics

#### § 9.3.2 — Prometheus Integration
  - `micrometer-registry-prometheus` — expose metrics in Prometheus format
  - `/actuator/prometheus` — Prometheus scrape endpoint
  - Prometheus: time-series database, scrapes metrics endpoints
  - PromQL: query language for Prometheus
  - Grafana: visualization dashboards for Prometheus metrics

#### § 9.3.3 — Key Metrics to Monitor
  - JVM: heap usage, GC pauses, thread count
  - HTTP: request count, latency (p50, p95, p99), error rate
  - Database: connection pool, query duration, active connections
  - Cache: hit rate, miss rate, evictions
  - Business: orders placed, users registered, revenue

---

### 📦 Module 9.4: Distributed Tracing

#### § 9.4.1 — OpenTelemetry & Micrometer Tracing
  - Spring Boot 3.x: Micrometer Tracing (formerly Spring Cloud Sleuth)
  - `micrometer-tracing-bridge-otel` — OpenTelemetry bridge
  - Automatic trace/span creation for: HTTP requests, database queries, Kafka messages
  - `traceId` and `spanId` automatically added to MDC (appears in logs)
  - Trace propagation: `W3C TraceContext` or `B3` headers between services

#### § 9.4.2 — Trace Exporters
  - Zipkin: `io.zipkin.reporter2:zipkin-sender-urlconnection`
  - Jaeger: via OpenTelemetry Collector
  - OTLP (OpenTelemetry Protocol): `opentelemetry-exporter-otlp`
  - Visualizing traces: see the full request path across microservices

---

### 📦 Module 9.5: ELK / Loki Stack

#### § 9.5.1 — Log Aggregation
  - **ELK**: Elasticsearch + Logstash + Kibana — the classic stack
  - **PLG**: Promtail + Loki + Grafana — lighter, cloud-native alternative
  - Centralized logging: all services log to one place
  - Search, filter, correlate logs by `traceId`

> ### 🛠️ Phase 9 Project: **"BookStore API v8 — Fully Observable"**
> Add complete observability:
> - **Actuator**: health (custom indicators for external APIs), info, metrics, Prometheus endpoint
> - **Health groups**: liveness + readiness probes configured for Kubernetes
> - **Structured logging**: JSON format with `logstash-logback-encoder`
> - **MDC filter**: request ID, user ID, trace ID in all log lines
> - **Custom metrics**: Micrometer counters and timers for business events (books sold, reviews posted, search queries)
> - **Prometheus + Grafana**: Docker Compose with Prometheus scraping, Grafana dashboard with:
>   - HTTP request rate, latency percentiles, error rate
>   - JVM metrics, database pool, cache hit rate
>   - Business metrics dashboard
> - **Distributed tracing**: Micrometer Tracing → Zipkin/Jaeger
>   - Trace ID propagation across HTTP calls and Kafka messages
>   - Trace visualization in Zipkin UI
> - **Alerting**: Grafana alerts for: error rate > 5%, p99 latency > 500ms, database pool exhaustion

---

## ⚡ PHASE 10 — MICROSERVICES WITH SPRING CLOUD
> *"Microservices are not about technology. They're about organizational boundaries. But when you need them, Spring Cloud is unmatched."*

---

### 📦 Module 10.1: Microservices Fundamentals

#### § 10.1.1 — When to Use Microservices
  - Monolith vs microservices tradeoffs
  - Start with a modular monolith, extract services when needed
  - Team autonomy, independent deployment, technology diversity
  - Complexity cost: distributed systems are HARD
  - Domain-Driven Design: bounded contexts define service boundaries

#### § 10.1.2 — Communication Patterns
  - Synchronous: REST, gRPC (request-response)
  - Asynchronous: Kafka, RabbitMQ (event-driven)
  - When to use each: sync for queries, async for commands/events
  - Saga pattern for distributed transactions

---

### 📦 Module 10.2: API Gateway

#### § 10.2.1 — Spring Cloud Gateway
  - `spring-cloud-starter-gateway` — reactive API gateway
  - Route configuration: predicates + filters
  - Predicates: path, method, header, query parameter, host
  - Filters: add/remove headers, rewrite path, rate limiting, circuit breaker
  - Load balancing integration with service discovery
  - Rate limiting: `RequestRateLimiter` filter with Redis backend
  - Global filters: logging, authentication, CORS
  - YAML-based or Java-based route configuration

---

### 📦 Module 10.3: Service Discovery

#### § 10.3.1 — Service Registry
  - Why: dynamic service locations, scaling, failover
  - **Eureka**: Netflix OSS, Spring Cloud native (client-server model)
  - **Consul**: HashiCorp, multi-datacenter, key-value store
  - **Kubernetes service discovery**: built-in, no extra component needed
  - `spring-cloud-starter-netflix-eureka-client` — register with Eureka
  - `@EnableEurekaServer` — run a Eureka server
  - Client-side load balancing: Spring Cloud LoadBalancer

---

### 📦 Module 10.4: Resilience

#### § 10.4.1 — Circuit Breaker (Resilience4j)
  - `spring-cloud-starter-circuitbreaker-resilience4j`
  - `@CircuitBreaker(name = "service", fallbackMethod = "fallback")`
  - States: CLOSED (normal) → OPEN (failing) → HALF_OPEN (testing)
  - Configuration: failure rate threshold, wait duration, ring buffer size

#### § 10.4.2 — Other Resilience Patterns
  - `@Retry` — retry with configurable attempts and backoff
  - `@RateLimiter` — limit request rate
  - `@Bulkhead` — isolate failures (semaphore or thread pool)
  - `@TimeLimiter` — timeout for async operations
  - Combining patterns: `@CircuitBreaker` + `@Retry` + `@RateLimiter`

---

### 📦 Module 10.5: Configuration Management

#### § 10.5.1 — Centralized Configuration
  - **Spring Cloud Config Server**: Git-backed configuration
  - Environment-specific: `application-dev.yml`, `application-prod.yml`
  - Config refresh: `@RefreshScope` + `/actuator/refresh`
  - **Consul KV**: configuration in Consul's key-value store
  - **Kubernetes ConfigMaps/Secrets**: cloud-native configuration
  - **Spring Vault**: secrets management (database credentials, API keys)

---

### 📦 Module 10.6: Distributed Data Patterns

#### § 10.6.1 — Database per Service
  - Each microservice owns its database
  - No shared database — strict boundary
  - Data duplication is acceptable
  - Eventual consistency between services

#### § 10.6.2 — Saga Pattern
  - Orchestration: central coordinator manages the saga
  - Choreography: services react to events and emit next events
  - Compensating transactions: undo previous steps on failure
  - Implementation with Kafka events

#### § 10.6.3 — CQRS (Command Query Responsibility Segregation)
  - Separate write model from read model
  - Write: domain-rich, normalized
  - Read: denormalized, optimized for queries
  - Sync read model via events

> ### 🛠️ Phase 10 Project: **"ShopSpring — A Microservices E-Commerce Platform"**
> Build a distributed e-commerce system:
> - **Services**:
>   - `api-gateway` — Spring Cloud Gateway (routing, rate limiting, CORS)
>   - `user-service` — registration, authentication, JWT
>   - `product-service` — product catalog, search, categories
>   - `order-service` — order creation, status management
>   - `payment-service` — payment processing (mock)
>   - `notification-service` — email/push notifications (mock)
>   - `config-server` — Spring Cloud Config (Git-backed)
>   - `discovery-server` — Eureka service registry
> - **Communication**:
>   - Sync: REST between gateway and services
>   - Async: Kafka for order → payment → notification event flow
> - **Resilience**: Resilience4j circuit breaker on all inter-service calls
> - **Data**: each service has its own PostgreSQL database
> - **Observability**: centralized logging, Prometheus metrics, distributed tracing (Zipkin)
> - **Infrastructure**: Docker Compose with ALL services + Kafka + PostgreSQL + Redis + Prometheus + Grafana + Zipkin
> - **Testing**: integration tests per service, contract tests between services

---

## ⚡ PHASE 11 — REACTIVE PROGRAMMING (SPRING WEBFLUX)
> *"Not every application needs reactive. But when you need it, nothing else will do."*

---

### 📦 Module 11.1: Reactive Fundamentals

#### § 11.1.1 — Why Reactive
  - Traditional (blocking): one thread per request — limited by thread pool size
  - Reactive (non-blocking): few threads handle many requests — event-driven
  - Use case: high-concurrency I/O-bound (API gateways, streaming, proxies, real-time)
  - NOT useful for: CPU-bound work, simple CRUD APIs
  - Reactor: Spring's reactive library (implements Reactive Streams spec)

#### § 11.1.2 — Project Reactor Core Types
  - `Mono<T>` — 0 or 1 element (like `CompletableFuture`)
  - `Flux<T>` — 0 to N elements (like `Stream` but async)
  - Creating: `Mono.just()`, `Mono.empty()`, `Mono.error()`, `Flux.fromIterable()`
  - Operators: `map`, `flatMap`, `filter`, `zip`, `merge`, `concat`, `switchIfEmpty`
  - Error handling: `onErrorResume`, `onErrorReturn`, `onErrorMap`, `retry`
  - Subscribing: `subscribe()` — triggers the pipeline (lazy until subscribed)
  - Backpressure: consumer controls the rate of data flow

---

### 📦 Module 11.2: Spring WebFlux

#### § 11.2.1 — WebFlux Controllers
  - Same annotations as Spring MVC: `@RestController`, `@GetMapping`, etc.
  - Return types: `Mono<T>`, `Flux<T>`, `Mono<ResponseEntity<T>>`
  - Request body: `@RequestBody Mono<CreateUserRequest>`
  - Streaming: `Flux<ServerSentEvent>` for SSE, `text/event-stream`

#### § 11.2.2 — Functional Endpoints
  - Alternative to annotation-based: `RouterFunction` + `HandlerFunction`
  - `RouterFunctions.route(GET("/api/users"), handler::getUsers)`
  - More functional, less annotation magic

#### § 11.2.3 — WebClient
  - Non-blocking HTTP client (replaces `RestTemplate` in reactive apps)
  - `WebClient.builder().baseUrl("...").build()`
  - `.get().uri("/users/{id}", id).retrieve().bodyToMono(User.class)`
  - Error handling: `.onStatus(HttpStatusCode::is4xxClientError, ...)`

---

### 📦 Module 11.3: Reactive Data Access

#### § 11.3.1 — R2DBC (Reactive Relational Database Connectivity)
  - Non-blocking database access (replaces JDBC for reactive apps)
  - `spring-boot-starter-data-r2dbc`
  - `ReactiveCrudRepository<T, ID>` — reactive repository
  - `DatabaseClient` — low-level reactive SQL
  - Supported: PostgreSQL (r2dbc-postgresql), MySQL, H2, MSSQL

#### § 11.3.2 — Reactive MongoDB
  - `ReactiveMongoRepository<T, ID>`
  - `ReactiveMongoTemplate`
  - Change streams: real-time data change notifications

#### § 11.3.3 — Reactive Redis
  - `ReactiveRedisTemplate`
  - `ReactiveStringRedisTemplate`

---

### 📦 Module 11.4: When to Use Reactive

#### § 11.4.1 — Decision Framework
  - Use WebFlux: API gateway, proxy, streaming, high-concurrency I/O
  - Use MVC: standard CRUD APIs, team familiarity, simpler mental model
  - Don't mix: choose one per application (MVC or WebFlux)
  - Virtual threads (Spring Boot 3.2+) often eliminate the need for WebFlux
  - Reactive all the way: once reactive, entire call chain must be non-blocking

> ### 🛠️ Phase 11 Project: **"ReactiveStream — A Real-Time Data Platform"**
> Build a reactive real-time data streaming platform:
> - **WebFlux API**: non-blocking REST endpoints for CRUD
> - **R2DBC**: reactive PostgreSQL access
> - **WebClient**: non-blocking calls to external APIs
> - **SSE stream**: `Flux<ServerSentEvent>` for real-time price updates
> - **WebSocket**: bidirectional real-time communication for chat
> - **Reactive Kafka**: consume events reactively using `reactor-kafka`
> - **Reactive Redis**: caching with `ReactiveRedisTemplate`
> - **Backpressure**: demonstrate backpressure handling with slow consumers
> - **Comparison**: benchmark same API in MVC (blocking) vs WebFlux (reactive) vs MVC + virtual threads
> - Document when each approach wins

---

## ⚡ PHASE 12 — DEPLOYMENT, PERFORMANCE & PRODUCTION READINESS
> *"Building it is 50%. Running it reliably is the other 50%."*

---

### 📦 Module 12.1: Containerization

#### § 12.1.1 — Docker for Spring Boot
  - Multi-stage Dockerfile: build with Gradle/Maven → run with JRE
  - `eclipse-temurin:21-jre-alpine` — lightweight runtime base image
  - Spring Boot layered JARs: `layers.idx` for efficient Docker caching
  - `spring-boot:build-image` — Buildpacks (no Dockerfile needed!)
  - Jib (Google): containerize without Docker daemon
  - JVM flags in Docker: `-XX:MaxRAMPercentage=75.0`, `-XX:+UseContainerSupport`
  - `.dockerignore` — exclude unnecessary files

#### § 12.1.2 — Docker Compose for Development
  - Application + PostgreSQL + Redis + Kafka + Prometheus + Grafana
  - Spring Boot 3.1+ Docker Compose support: `spring-boot-docker-compose`
  - Auto-start containers on application startup in dev mode

---

### 📦 Module 12.2: Kubernetes Deployment

#### § 12.2.1 — Kubernetes Manifests
  - Deployment, Service, Ingress, ConfigMap, Secret
  - Resource limits: CPU and memory requests/limits
  - Liveness probe: `/actuator/health/liveness` — restart if unhealthy
  - Readiness probe: `/actuator/health/readiness` — stop traffic if not ready
  - Startup probe: for slow-starting applications
  - Graceful shutdown: `server.shutdown=graceful`, `spring.lifecycle.timeout-per-shutdown-phase=30s`
  - Environment-specific configuration via ConfigMaps and Secrets

#### § 12.2.2 — Helm Charts
  - Templatized Kubernetes manifests
  - `values.yaml` for environment-specific configuration
  - Reusable charts for multiple microservices

---

### 📦 Module 12.3: GraalVM Native Image

#### § 12.3.1 — Ahead-of-Time Compilation
  - Compile Spring Boot to native binary: instant startup (~50ms), low memory
  - `spring-boot-starter-parent` includes native build support
  - `./gradlew nativeCompile` or `./mvnw -Pnative native:compile`
  - Native image with Buildpacks: `./gradlew bootBuildImage`
  - Limitations: reflection, dynamic proxies, serialization require hints
  - `@RegisterReflectionForBinding` — register classes for reflection
  - AOT processing: `@ImportRuntimeHints` for custom runtime hints
  - Trade-off: faster startup + lower memory, slower build, some library incompatibilities
  - Use case: serverless (AWS Lambda), CLI tools, resource-constrained environments

---

### 📦 Module 12.4: Performance Tuning

#### § 12.4.1 — JVM Tuning
  - Heap sizing: `-Xms` and `-Xmx` (set equal for predictability)
  - GC selection: G1 (default), ZGC (low latency), Shenandoah
  - `XX:MaxRAMPercentage=75.0` — percentage-based sizing for containers
  - JFR (Java Flight Recorder): production-safe profiling
  - Thread dump analysis: `jstack`, VisualVM

#### § 12.4.2 — Application-Level Optimization
  - Database: N+1 detection, query optimization, connection pool tuning
  - Caching: appropriate TTL, cache hit rate monitoring
  - Serialization: Jackson performance tuning, avoiding unnecessary conversions
  - Connection management: HTTP client connection pooling, keep-alive
  - Lazy initialization: `spring.main.lazy-initialization=true` (faster dev startup)
  - Startup optimization: class data sharing (CDS), `-XX:+TieredCompilation`

#### § 12.4.3 — Load Testing
  - **Gatling** — Scala/Java-based load testing (recommended for Java shops)
  - **k6** — JavaScript-based, modern
  - **JMeter** — traditional, GUI-based
  - Test scenarios: baseline, stress, spike, soak, breakpoint
  - Identify bottlenecks: thread pool, database connections, GC pauses, external calls

---

### 📦 Module 12.5: CI/CD Pipeline

#### § 12.5.1 — GitHub Actions for Spring Boot
  - Lint: Checkstyle, SpotBugs
  - Build: `./gradlew build`
  - Test: unit, integration (with Testcontainers), coverage (JaCoCo)
  - Docker: build and push image
  - Deploy: to Kubernetes, AWS ECS, or cloud platform
  - Environment-specific deployments: dev → staging → production

#### § 12.5.2 — Release Strategy
  - Semantic versioning
  - Database migration compatibility: backward-compatible migrations
  - Blue-green deployment: zero-downtime releases
  - Canary deployment: gradual rollout
  - Feature flags: enable features per environment/user

---

### 📦 Module 12.6: Production Checklist

#### § 12.6.1 — Security
  - All secrets in vault/secrets manager (not in code or properties)
  - HTTPS enforced
  - Security headers configured
  - Dependency vulnerability scanning: OWASP Dependency-Check, Snyk
  - Container image scanning: Trivy

#### § 12.6.2 — Reliability
  - Health checks configured and monitored
  - Graceful shutdown enabled
  - Circuit breakers on all external calls
  - Retry with backoff on transient failures
  - Rate limiting on public endpoints
  - Database connection pool monitoring and alerting

#### § 12.6.3 — Observability
  - Structured logging (JSON) with correlation IDs
  - Metrics exported to Prometheus, dashboards in Grafana
  - Distributed tracing enabled with proper sampling
  - Alerting rules for: error rate, latency, resource usage
  - Log aggregation with searchable logs

> ### 🛠️ Phase 12 Capstone Project: **"ShopSpring Production — Deployed & Monitored"**
> Take the Phase 10 microservices project and make it production-grade:
> - **Dockerize** all services with multi-stage builds and layered JARs
> - **Docker Compose** for full local environment (all services + infrastructure)
> - **Kubernetes manifests** for each service:
>   - Deployments with resource limits
>   - Services and Ingress
>   - ConfigMaps and Secrets
>   - Liveness, readiness, and startup probes
>   - Horizontal Pod Autoscaler
> - **GraalVM native image** for at least one service (gateway or notification)
> - **CI/CD**: GitHub Actions pipeline:
>   - Lint → Build → Test → Docker Build → Push → Deploy
>   - Separate pipelines per service (independent deployment)
> - **Load test** with Gatling: find the breaking point, optimize
> - **Production checklist**: every item checked and documented
> - **Runbook**: document common failure scenarios and resolution steps
> - **Architecture Decision Records (ADRs)**: document every major technical decision

---

## 📊 PHASE MAP (Visual Summary)

```
Phase 0   ██░░░░░░░░░░░░░░░░  Prerequisites & Orientation
Phase 1   ████░░░░░░░░░░░░░░  Spring Core: IoC, DI, Beans, AOP
Phase 2   ██████░░░░░░░░░░░░  REST APIs: Controllers, Validation, Jackson
Phase 3   ████████░░░░░░░░░░  Data Access: JPA, Repositories, Transactions
Phase 4   █████████░░░░░░░░░  Exception Handling & API Design
Phase 5   ██████████░░░░░░░░  Spring Security: Auth, JWT, OAuth2
Phase 6   ███████████░░░░░░░  Testing: Unit, Slice, Integration
Phase 7   ████████████░░░░░░  Caching, Async, Scheduling, Events
Phase 8   █████████████░░░░░  Messaging: Kafka, RabbitMQ, WebSocket
Phase 9   ██████████████░░░░  Monitoring: Actuator, Metrics, Tracing
Phase 10  ███████████████░░░  Microservices: Spring Cloud
Phase 11  ████████████████░░  Reactive: WebFlux, R2DBC
Phase 12  █████████████████░  Deployment: Docker, K8s, GraalVM, CI/CD
```

---

## 🎯 DIFFICULTY & SKILL PROGRESSION

```
       BEGINNER              INTERMEDIATE              ADVANCED                 EXPERT
    ┌────────────┐        ┌────────────────┐       ┌──────────────┐       ┌──────────────┐
    │  Phase 0   │───────▶│    Phase 3     │──────▶│   Phase 7    │──────▶│   Phase 10   │
    │  Phase 1   │        │    Phase 4     │       │   Phase 8    │       │   Phase 11   │
    │  Phase 2   │        │    Phase 5     │       │   Phase 9    │       │   Phase 12   │
    │            │        │    Phase 6     │       │              │       │              │
    └────────────┘        └────────────────┘       └──────────────┘       └──────────────┘
    "I can build           "I build secure,         "I build event-        "I architect
     REST APIs with         tested, database-        driven, monitored,     and deploy
     Spring Boot"           backed APIs"             resilient systems"     microservices"
```

---

## 🎯 CERTIFICATION ALIGNMENT

| Phase | Certification / Credibility |
|-------|----------------------------|
| 0 – 6 | **VMware Spring Certified Professional** |
| 3 – 6 | **Oracle Certified Professional: Java SE** (complements Spring) |
| 10 – 12 | **Kubernetes CKAD** (Certified Kubernetes Application Developer) |
| 10 – 12 | **AWS Solutions Architect / Developer** (deploying Spring on AWS) |
| ALL | **Senior Spring Boot Engineer** portfolio |

---

## 📚 RECOMMENDED RESOURCES

| Resource | Type | Phase |
|----------|------|-------|
| **Spring.io Guides** (spring.io/guides) | 🌐 Official (START HERE) | 0–4 |
| **Spring Boot Reference Docs** (docs.spring.io) | 🌐 Official Reference | ALL |
| *Spring in Action* — Craig Walls (6th Ed.) | 📖 Book (Comprehensive) | 0–8 |
| *Spring Boot in Practice* — Somnath Musib | 📖 Book (Practical) | 1–9 |
| *Spring Security in Action* — Laurentiu Spilca (2nd Ed.) | 📖 Book (Security Deep Dive) | 5 |
| *Cloud Native Spring in Action* — Thomas Vitale | 📖 Book (Cloud-Native) | 10–12 |
| *Spring Microservices in Action* — Carnell & Sánchez | 📖 Book (Microservices) | 10 |
| *Reactive Spring* — Josh Long | 📖 Book (WebFlux) | 11 |
| **Baeldung.com** | 🌐 Tutorials (The go-to Spring resource) | ALL |
| **Marco Behler** (YouTube + Blog) | 🎥 Video (Deep Spring internals) | 1–6 |
| **Dan Vega** (YouTube) | 🎥 Video (Modern Spring Boot) | 0–8 |
| **Java Brains** (YouTube) | 🎥 Video (Spring basics) | 0–5 |
| **Amigoscode** (YouTube) | 🎥 Video (Full-stack Spring) | 0–8 |
| **Spring Tips** — Josh Long (YouTube) | 🎥 Video (Latest features) | ALL |
| **Spring I/O Conference** (YouTube) | 🎥 Conference Talks | 5–12 |
| **SpringDeveloper** (YouTube) | 🎥 Official Channel | ALL |
| **start.spring.io** | 🧪 Project Generator | ALL |
| **Testcontainers Docs** | 📄 Testing with Docker | 6 |
| **Resilience4j Docs** | 📄 Resilience patterns | 10 |
| **Micrometer Docs** | 📄 Metrics | 9 |

---

## 🗺️ WHERE SPRING BOOT TAKES YOU (Career Paths)

```
                                  ┌───────────────────────────┐
                                  │   Backend Engineer        │
                           ┌─────▶│   (REST APIs, CRUD,       │
                           │      │    Enterprise Systems)     │
                           │      └───────────────────────────┘
                           │      ┌───────────────────────────┐
                           │      │   Microservices Architect  │
                   ┌───────┤─────▶│   (Spring Cloud, K8s,     │
                   │       │      │    Event-Driven Systems)   │
                   │       │      └───────────────────────────┘
                   │       │      ┌───────────────────────────┐
   ┌────────────┐  │       │      │   Platform / DevOps       │
   │  Master    │  │       ├─────▶│   Engineering             │
   │  Spring    ├──┤       │      │   (CI/CD, K8s, SRE)       │
   │  Boot      │  │       │      └───────────────────────────┘
   │            │  │       │      ┌───────────────────────────┐
   └────────────┘  │       │      │   Financial / Banking     │
                   │       ├─────▶│   Systems                 │
                   │       │      │   (High-reliability,       │
                   │       │      │    compliance)              │
                   │       │      └───────────────────────────┘
                   │       │      ┌───────────────────────────┐
                   │       │      │   Technical Lead /        │
                   └───────┴─────▶│   Staff Engineer          │
                                  │   (Architecture, Mentoring,│
                                  │    Technical Strategy)     │
                                  └───────────────────────────┘
```

---

## ⚠️ THE EVOLVING BOOKSTORE PROJECT

Notice how the project **evolves across every phase** — this is intentional:

```
Phase 2:  BookStore v1 — REST API with in-memory data
Phase 3:  BookStore v2 — Database-backed with JPA
Phase 4:  BookStore v3 — Production error handling & docs
Phase 5:  BookStore v4 — Secured with JWT
Phase 6:  BookStore v5 — Fully tested
Phase 7:  BookStore v6 — Cached, async, scheduled
Phase 8:  BookStore v7 — Event-driven with Kafka
Phase 9:  BookStore v8 — Fully observable
Phase 10: ShopSpring  — Microservices architecture
Phase 12: ShopSpring  — Production-deployed
```

> **One project, twelve iterations.** By the end, you have a production-grade, microservices-based, fully tested, monitored, and deployed application — built incrementally, understanding every layer.

---

> ### 💡 Final Advice
> **"Spring Boot makes easy things trivial and hard things possible. The danger is not knowing which is which."**
>
> Five non-negotiable rules for your Spring Boot journey:
>
> 1. **Understand Spring Core before Spring Boot.** Auto-configuration is magic until you understand IoC, DI, beans, and proxies. Phase 1 is the most important phase — if DI doesn't click, nothing else will.
>
> 2. **Constructor injection ONLY.** No field injection. No setter injection (except optional deps). If your class has 7 constructor parameters, your class has too many responsibilities — fix the design, don't switch to field injection.
>
> 3. **Never expose JPA entities in API responses.** Always map to DTOs. This prevents: lazy loading exceptions, circular references, security leaks, tight coupling between API and database schema.
>
> 4. **Test at every layer.** Unit tests for services (Mockito), `@WebMvcTest` for controllers, `@DataJpaTest` for repositories, `@SpringBootTest` with Testcontainers for integration. No excuses.
>
> 5. **Read the official documentation.** Spring's docs at docs.spring.io are among the best in all of software engineering. Every annotation, every property, every feature — documented with examples. Baeldung is your second source, not your first.
>
> The difference between a *Spring Boot developer* and a *Spring Boot engineer* is:
> - **Understanding the proxy mechanism** (why `@Transactional` on self-invocation doesn't work)
> - **Proper error handling** (structured, consistent, informative)
> - **Testing discipline** (not just "it works in Postman")
> - **Knowing when NOT to use a feature** (caching that's never invalidated, async that's never awaited, reactive for a CRUD API)

---

*This roadmap takes you from "What's `@Autowired`?" to "I can architect, build, test, secure, monitor, and deploy production-grade distributed systems with Spring Boot — and I understand every annotation, every proxy, and every auto-configuration that makes it all work."* 🍃🚀