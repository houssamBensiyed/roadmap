# 🍃 THE ULTIMATE SPRING BOOT ROADMAP
## Complete Edition — From Zero to Spring Boot Master

---

```
╔══════════════════════════════════════════════════════════════════════════════════════╗
║                        SPRING BOOT — MASTERY LADDER                                 ║
║                                                                                      ║
║   🏆 PHASE 8 ─ Spring Boot in Production at Scale     [Principal Engineer]           ║
║       ▲                                                                              ║
║   🤖 PHASE 7 ─ Spring AI & Emerging Ecosystem         [Advanced Specialist]          ║
║       ▲                                                                              ║
║   ☁️ PHASE 6 ─ Spring Cloud & Microservices            [Senior Engineer]              ║
║       ▲                                                                              ║
║   📡 PHASE 5 ─ Messaging, Events & Async              [Mid-Senior Engineer]          ║
║       ▲                                                                              ║
║   🛡️ PHASE 4 ─ Spring Security (Deep Dive)             [Mid-Level Engineer]           ║
║       ▲                                                                              ║
║   🗄️ PHASE 3 ─ Data Access & Persistence              [Mid-Level Engineer]           ║
║       ▲                                                                              ║
║   🌐 PHASE 2 ─ Building REST APIs & Web Layer         [Junior+ Engineer]             ║
║       ▲                                                                              ║
║   🧱 PHASE 1 ─ Java & Spring Core Foundations         [Starting Point]               ║
║                                                                                      ║
╚══════════════════════════════════════════════════════════════════════════════════════╝
```

---
---
---

# 🧱 PHASE 1: JAVA & SPRING CORE FOUNDATIONS
### 📅 Duration: Months 1–2
### 🎯 Goal: Master the Java and Spring fundamentals that EVERYTHING else builds on
### 👤 Level: Starting Point

---

## Module 1.1: Java Prerequisites (Non-Negotiable)

### Section 1.1.1 — Core Java Essentials
```
├── OOP in Java:
│   ├── Classes, Objects, Constructors, this keyword
│   ├── Inheritance: extends, super, Method overriding
│   ├── Polymorphism: Compile-time (overloading) vs Runtime (overriding)
│   ├── Abstraction: Abstract classes vs Interfaces (and when to use which)
│   ├── Encapsulation: Access modifiers (private, protected, public, package-private)
│   └── Sealed Classes (Java 17+): Restrict inheritance hierarchy
├── Interfaces:
│   ├── Default Methods (Java 8+): Backward-compatible evolution
│   ├── Static Methods in interfaces
│   ├── Functional Interfaces: @FunctionalInterface, Single Abstract Method (SAM)
│   └── Interface segregation in practice
├── Generics:
│   ├── Type Parameters: <T>, <K,V>, Bounded types (<T extends Comparable<T>>)
│   ├── Wildcards: <?>, <? extends T>, <? super T> (PECS principle)
│   ├── Type Erasure: How generics work at runtime
│   └── Generic Methods vs Generic Classes
├── Enums:
│   ├── Enum with fields, Methods, Constructors
│   ├── Enum implementing interfaces
│   └── EnumMap, EnumSet — Performance benefits
└── Records (Java 16+):
    ├── Immutable data carriers
    ├── Compact constructors, Custom accessors
    └── Records vs Lombok @Value vs regular classes
```

### Section 1.1.2 — Modern Java Features (Java 17–21+)
```
├── Functional Programming:
│   ├── Lambda Expressions: (x) -> x * 2, Method references ::
│   ├── Streams API:
│   │   ├── Intermediate: filter, map, flatMap, sorted, distinct, peek
│   │   ├── Terminal: collect, forEach, reduce, count, findFirst, anyMatch
│   │   ├── Collectors: toList, toMap, groupingBy, partitioningBy, joining
│   │   └── Parallel Streams: When to use (CPU-bound), When NOT to (I/O-bound)
│   ├── Optional<T>: Avoiding null, map, flatMap, orElse, orElseThrow
│   ├── Predicate, Function, Consumer, Supplier: Core functional interfaces
│   └── Composition: andThen, compose, Predicate.and/or/negate
├── Text Blocks: """ Multi-line strings """ (Java 13+)
├── Pattern Matching:
│   ├── instanceof pattern: if (obj instanceof String s) — no cast needed
│   ├── Switch Expressions: yield, Arrow labels, Pattern matching in switch (Java 21+)
│   └── Record Patterns: Decompose records in pattern matching
├── Var (Local Variable Type Inference): var list = new ArrayList<String>()
├── Virtual Threads (Java 21+):
│   ├── Project Loom: Lightweight threads, Massive concurrency
│   ├── Thread.ofVirtual().start(() -> ...)
│   ├── Structured Concurrency: StructuredTaskScope (preview)
│   └── Impact on Spring Boot: Servlet thread model revolution
└── Sealed Classes & Interfaces: Controlled inheritance hierarchy
```

### Section 1.1.3 — Java Collections & Concurrency
```
├── Collections Framework:
│   ├── List: ArrayList (O(1) random access), LinkedList (O(1) insert), CopyOnWriteArrayList
│   ├── Set: HashSet (O(1)), TreeSet (sorted, O(log n)), LinkedHashSet (insertion order)
│   ├── Map: HashMap, TreeMap, LinkedHashMap, ConcurrentHashMap
│   ├── Queue/Deque: ArrayDeque, PriorityQueue, BlockingQueue
│   ├── Immutable Collections: List.of(), Map.of(), Set.of(), Collections.unmodifiable*
│   └── Performance Characteristics: Know Big-O for every operation
├── Concurrency:
│   ├── Thread, Runnable, Callable: Basic thread creation
│   ├── ExecutorService: Thread pools (Fixed, Cached, Scheduled, WorkStealing)
│   ├── Future & CompletableFuture:
│   │   ├── thenApply, thenCompose, thenCombine
│   │   ├── exceptionally, handle, whenComplete
│   │   └── allOf, anyOf — Combining futures
│   ├── synchronized, volatile, Atomic classes (AtomicInteger, AtomicReference)
│   ├── ReentrantLock, ReadWriteLock, StampedLock
│   ├── CountDownLatch, CyclicBarrier, Semaphore
│   └── ConcurrentHashMap, CopyOnWriteArrayList, BlockingQueue
└── Memory Model:
    ├── Heap vs Stack: Object allocation, Primitive storage
    ├── Garbage Collection: G1GC (default), ZGC (low-latency), Shenandoah
    ├── GC Tuning Basics: Heap sizing, GC algorithm selection
    └── Memory Leaks: Common causes, Detection tools (VisualVM, JFR)
```

### Section 1.1.4 — Build Tools & Project Structure
```
├── Maven:
│   ├── POM (pom.xml): groupId, artifactId, version
│   ├── Dependency Management: <dependencies>, <dependencyManagement>, Scope (compile, test, runtime, provided)
│   ├── Lifecycle: clean, compile, test, package, install, deploy
│   ├── Plugins: compiler-plugin, surefire, failsafe, shade, spring-boot-maven-plugin
│   ├── Profiles: Environment-specific configurations
│   ├── Multi-Module Projects: Parent POM, Module inheritance
│   └── BOM (Bill of Materials): Version management (spring-boot-dependencies)
├── Gradle:
│   ├── build.gradle / build.gradle.kts (Kotlin DSL)
│   ├── Dependencies: implementation, testImplementation, runtimeOnly, compileOnly
│   ├── Tasks: Build lifecycle, Custom tasks
│   ├── Plugins: java, org.springframework.boot, io.spring.dependency-management
│   ├── Multi-Module: settings.gradle, subproject configuration
│   └── Gradle vs Maven: Speed (Gradle), Ecosystem (Maven), Kotlin DSL benefits
├── Project Structure (Standard):
│   ├── src/main/java — Application code
│   ├── src/main/resources — Config files (application.yml, static, templates)
│   ├── src/test/java — Test code
│   └── src/test/resources — Test configurations
└── Java Tooling:
    ├── JDK Versions: Use Java 21+ (LTS) for new projects
    ├── SDKMAN: Manage multiple JDK versions
    └── IDE: IntelliJ IDEA (Ultimate preferred), VS Code with Java extensions
```

---

## Module 1.2: Spring Framework Core

### Section 1.2.1 — Inversion of Control (IoC) & Dependency Injection
```
├── IoC Container:
│   ├── ApplicationContext: The Spring container
│   ├── BeanFactory: Base container (rarely used directly)
│   ├── Bean Lifecycle:
│   │   ├── Instantiation → Populate Properties → setBeanName → setBeanFactory
│   │   ├── → setApplicationContext → @PostConstruct → afterPropertiesSet
│   │   ├── → Custom init-method → READY
│   │   ├── → @PreDestroy → destroy → Custom destroy-method → DESTROYED
│   │   └── Bean Post Processors: Modify beans before/after initialization
│   └── Bean Scopes: singleton (default), prototype, request, session, application
├── Dependency Injection Types:
│   ├── Constructor Injection (PREFERRED):
│   │   ├── Immutable dependencies, Final fields
│   │   ├── Required dependencies enforced at compile time
│   │   └── No @Autowired needed (single constructor auto-wired by default)
│   ├── Setter Injection: Optional dependencies, Mutable
│   ├── Field Injection (@Autowired on field): AVOID — hard to test, hides dependencies
│   └── Method Injection: @Lookup for prototype beans in singleton scope
├── Annotations:
│   ├── @Component: Generic Spring-managed bean
│   ├── @Service: Business logic layer (semantic alias for @Component)
│   ├── @Repository: Data access layer (adds exception translation)
│   ├── @Controller / @RestController: Web layer
│   ├── @Configuration: Java-based configuration class
│   ├── @Bean: Method-level bean definition in @Configuration class
│   ├── @Primary: Default bean when multiple candidates exist
│   ├── @Qualifier: Select specific bean by name
│   └── @Lazy: Defer initialization until first use
└── Profiles:
    ├── @Profile("dev"): Activate beans conditionally
    ├── spring.profiles.active: Activate profiles via config
    ├── Profile-Specific Config: application-dev.yml, application-prod.yml
    └── @Profile("!prod"): Negative profiles
```

### Section 1.2.2 — Spring Configuration
```
├── Java Configuration (Preferred):
│   ├── @Configuration + @Bean: Type-safe, IDE support, Refactorable
│   ├── @Import: Compose configuration classes
│   ├── @PropertySource: Load external property files
│   └── @Conditional*: Conditional bean registration
├── Properties & YAML:
│   ├── application.properties vs application.yml: Preference/readability
│   ├── @Value("${property.name}"): Inject individual properties
│   ├── @ConfigurationProperties: Type-safe configuration binding
│   │   ├── @ConfigurationProperties(prefix = "app.mail")
│   │   ├── Nested objects, Lists, Maps, Validation (@Valid, @NotBlank)
│   │   └── Immutable: @ConstructorBinding (records work perfectly)
│   ├── Property Resolution Order:
│   │   ├── 1. Command line args
│   │   ├── 2. OS Environment variables
│   │   ├── 3. application-{profile}.yml
│   │   ├── 4. application.yml
│   │   └── 5. Default values
│   └── Externalized Config: Config Server, Vault, Kubernetes ConfigMaps
├── Spring Expression Language (SpEL):
│   ├── @Value("#{systemProperties['user.name']}")
│   ├── @Value("#{T(java.lang.Math).PI}")
│   ├── Conditional expressions, Collection projection
│   └── Use sparingly: Prefer @ConfigurationProperties
└── Conditional Beans:
    ├── @ConditionalOnProperty: Create bean based on property value
    ├── @ConditionalOnClass: Create bean if class exists on classpath
    ├── @ConditionalOnMissingBean: Fallback bean if no other exists
    ├── @ConditionalOnBean: Create bean if another bean exists
    └── Custom @Conditional: Implement Condition interface
```

### Section 1.2.3 — Aspect-Oriented Programming (AOP)
```
├── Concepts:
│   ├── Aspect: Cross-cutting concern module (logging, security, transactions)
│   ├── Join Point: Point in execution (method call, exception)
│   ├── Pointcut: Expression selecting join points
│   ├── Advice: Action at join point (before, after, around)
│   └── Weaving: Linking aspects with code (compile-time, load-time, runtime)
├── Spring AOP Implementation:
│   ├── @Aspect: Declare an aspect class
│   ├── @Before: Run before method execution
│   ├── @After: Run after method (regardless of outcome)
│   ├── @AfterReturning: Run after successful return
│   ├── @AfterThrowing: Run after exception
│   ├── @Around: Wrap method execution (most powerful)
│   └── ProceedingJoinPoint: Control method execution in @Around
├── Pointcut Expressions:
│   ├── execution(* com.example.service.*.*(..)) — Method execution
│   ├── @annotation(com.example.Loggable) — Methods with annotation
│   ├── within(com.example.service..*) — Within a package
│   └── Combining: && (and), || (or), ! (not)
├── Common Use Cases:
│   ├── Logging: Log method entry/exit/duration
│   ├── Performance Monitoring: Measure execution time
│   ├── Security: Check permissions before method
│   ├── Transaction Management: @Transactional (AOP-based!)
│   ├── Caching: @Cacheable (AOP-based!)
│   └── Retry: @Retryable (AOP-based!)
├── How It Works: Spring AOP uses JDK Dynamic Proxies (interfaces) or CGLIB (classes)
└── Gotchas:
    ├── Self-Invocation: Calling method within same class BYPASSES proxy
    ├── Private Methods: Not intercepted (proxy-based AOP)
    ├── Final Classes/Methods: Not intercepted by CGLIB
    └── Solution for Self-Invocation: Inject self, Use AspectJ weaving, Refactor
```

### Section 1.2.4 — Spring Events
```
├── ApplicationEvent: Base class for custom events
├── Publishing: ApplicationEventPublisher.publishEvent(event)
├── Listening:
│   ├── @EventListener: Method-level listener
│   ├── @TransactionalEventListener: Fire after transaction commits
│   │   ├── phase = AFTER_COMMIT (default)
│   │   ├── phase = AFTER_ROLLBACK
│   │   └── phase = AFTER_COMPLETION
│   └── ApplicationListener<T>: Interface-based listener
├── Async Events: @Async + @EventListener = Non-blocking event processing
├── Built-in Events:
│   ├── ContextRefreshedEvent: ApplicationContext initialized/refreshed
│   ├── ContextStartedEvent: ApplicationContext started
│   ├── ContextStoppedEvent: ApplicationContext stopped
│   └── ContextClosedEvent: ApplicationContext closed
├── Ordering: @Order(1) — Control listener execution order
└── Use Cases:
    ├── Decoupling: Service A publishes event, Service B reacts
    ├── Audit Logging: Log business events without coupling
    ├── Cache Invalidation: Clear cache when entity changes
    └── Notification: Send email/SMS after order placed
```

---

## Module 1.3: Spring Boot Fundamentals

### Section 1.3.1 — What Spring Boot Actually Does
```
├── Auto-Configuration:
│   ├── @EnableAutoConfiguration: Scans classpath, Configures beans automatically
│   ├── spring.factories / AutoConfiguration.imports: Registers auto-config classes
│   ├── Conditional Annotations: @ConditionalOnClass, @ConditionalOnProperty, etc.
│   ├── How it works: "If H2 is on classpath → auto-configure in-memory DataSource"
│   ├── Overriding: Define your own bean → Auto-config backs off
│   └── Debugging: --debug flag → ConditionEvaluationReport (CONDITIONS EVALUATION REPORT)
├── Starter Dependencies:
│   ├── spring-boot-starter-web: Tomcat + Spring MVC + Jackson
│   ├── spring-boot-starter-data-jpa: Hibernate + Spring Data JPA
│   ├── spring-boot-starter-security: Spring Security auto-config
│   ├── spring-boot-starter-test: JUnit 5 + Mockito + AssertJ + Testcontainers
│   ├── spring-boot-starter-actuator: Health, Metrics, Info endpoints
│   ├── spring-boot-starter-validation: Hibernate Validator (Bean Validation)
│   └── Custom Starters: Build your own for shared library configuration
├── Embedded Server:
│   ├── Tomcat (default): Mature, Battle-tested
│   ├── Jetty: Lightweight, WebSocket-friendly
│   ├── Undertow: High-performance, Non-blocking
│   └── Netty (WebFlux): Reactive, Non-blocking I/O
├── SpringApplication:
│   ├── @SpringBootApplication = @Configuration + @EnableAutoConfiguration + @ComponentScan
│   ├── SpringApplication.run(): Bootstrap the application
│   ├── ApplicationRunner / CommandLineRunner: Run code after startup
│   ├── Banner: Custom startup banner (banner.txt)
│   └── SpringApplicationBuilder: Fluent API for customization
└── Fat JAR (Uber JAR):
    ├── All dependencies packaged in single JAR
    ├── java -jar app.jar: Run anywhere with JRE
    ├── Spring Boot Maven/Gradle Plugin: Creates executable JAR
    ├── Layered JARs: Optimized Docker layer caching
    └── Executable WAR: For traditional servlet container deployment (rarely needed)
```

### Section 1.3.2 — Application Configuration Deep Dive
```
├── Configuration Files:
│   ├── application.yml (preferred): Human-readable, Hierarchical
│   ├── application.properties: Simple key=value
│   ├── application-{profile}.yml: Profile-specific overrides
│   └── Config File Locations (priority order):
│       ├── 1. ./config/application.yml
│       ├── 2. ./application.yml
│       ├── 3. classpath:/config/application.yml
│       └── 4. classpath:/application.yml
├── @ConfigurationProperties (Best Practice):
│   ├── Type-safe binding: Compile-time checked
│   ├── Validation: @Valid, @NotNull, @Min, @Max, @Pattern
│   ├── Nested Objects: Complex configuration hierarchies
│   ├── Records: Immutable config with Java records
│   ├── Lists & Maps: List<String>, Map<String, DatabaseConfig>
│   └── Metadata: spring-configuration-metadata.json for IDE autocompletion
├── Externalized Configuration (12-Factor):
│   ├── Environment Variables: SPRING_DATASOURCE_URL=...
│   ├── Command Line Args: --server.port=9090
│   ├── System Properties: -Dserver.port=9090
│   ├── Config Server (Spring Cloud): Centralized configuration
│   ├── Vault: Secrets management
│   └── Kubernetes: ConfigMaps + Secrets
├── Custom Configuration Processor:
│   ├── spring-boot-configuration-processor: Generate IDE metadata
│   └── @ConstructorBinding: Immutable @ConfigurationProperties
└── Relaxed Binding:
    ├── my-property = MY_PROPERTY = myProperty = my.property
    └── Environment variables: Replace . with _ and uppercase
```

### Section 1.3.3 — Logging
```
├── Default: SLF4J + Logback (included in spring-boot-starter)
├── Log Levels: TRACE < DEBUG < INFO < WARN < ERROR
├── Configuration:
│   ├── application.yml: logging.level.com.example=DEBUG
│   ├── logback-spring.xml: Full Logback configuration
│   ├── Profile-specific: <springProfile name="dev"> in logback-spring.xml
│   └── Log Groups: logging.group.web=org.springframework.web,org.apache.tomcat
├── Structured Logging (Production):
│   ├── JSON Format: Logstash encoder, structured-arguments
│   ├── MDC (Mapped Diagnostic Context): Add traceId, userId, requestId
│   ├── Correlation ID: Propagate across services
│   └── Spring Boot 3.4+: Built-in structured logging support
├── Log Rotation: logback-spring.xml → RollingFileAppender, MaxFileSize, MaxHistory
├── Alternative Implementations:
│   ├── Log4j2: Async logging, Better performance under load
│   └── JUL (java.util.logging): Legacy, Avoid
├── Best Practices:
│   ├── Use parameterized logging: log.info("User {} logged in", userId)
│   ├── NEVER log sensitive data (passwords, tokens, PII)
│   ├── Use appropriate levels: DEBUG for dev, INFO/WARN/ERROR for prod
│   ├── Include context: Who, What, When, Result
│   └── Log at boundaries: Entry/exit of services, External calls
└── Performance:
    ├── Guard debug logging: if (log.isDebugEnabled())
    ├── Async Appender: Don't block on I/O in logging
    └── Sampling: Don't log every request in high-throughput systems
```

### Section 1.3.4 — DevTools & Developer Productivity
```
├── Spring Boot DevTools:
│   ├── Automatic Restart: Reloads app on code change (uses two classloaders)
│   ├── LiveReload: Auto-refresh browser on static resource change
│   ├── Property Overrides: Disable caching in dev (Thymeleaf, Freemarker)
│   ├── Remote Debugging: Connect to remote running app
│   └── Limitations: Disabled automatically in production JARs
├── Spring Initializr:
│   ├── https://start.spring.io: Bootstrap new projects
│   ├── IDE Integration: IntelliJ, VS Code built-in project generation
│   ├── CLI: spring init --dependencies=web,jpa,security my-app
│   └── Custom Initializr: Company-specific templates
├── Lombok (Optional but Common):
│   ├── @Getter, @Setter: Generate accessors
│   ├── @Builder: Builder pattern generation
│   ├── @AllArgsConstructor, @NoArgsConstructor, @RequiredArgsConstructor
│   ├── @Slf4j: Inject logger automatically
│   ├── @Data: All of the above + @ToString + @EqualsAndHashCode
│   ├── @Value: Immutable class generation
│   └── Controversy: Prefer Java Records (Java 16+) for DTOs, Reduce Lombok usage
└── IDE Tips (IntelliJ):
    ├── Spring Boot Run Configuration: Built-in support
    ├── Spring Dashboard: View beans, Endpoints, Mappings
    ├── Actuator Integration: Monitor from IDE
    └── Database Tools: Query databases, View schema from IDE
```

---

> ### 🛠️ PHASE 1 PROJECT: **Employee Management CLI Application**
> ```
> ┌─────────────────────────────────────────────────────────────────┐
> │            EMPLOYEE MANAGEMENT CLI APPLICATION                  │
> ├─────────────────────────────────────────────────────────────────┤
> │ Features:                                                       │
> │  • CLI-based CRUD for Employees (CommandLineRunner)             │
> │  • Departments with one-to-many relationship                    │
> │  • In-memory H2 database (auto-configured)                      │
> │  • Service layer with proper DI (constructor injection)         │
> │  • Configuration via @ConfigurationProperties                   │
> │  • Custom Spring Events: EmployeeCreated, EmployeeDeleted      │
> │  • AOP: Logging aspect for all service methods                  │
> │  • Profiles: dev (H2 console), prod (PostgreSQL)               │
> │                                                                 │
> │ Requirements:                                                   │
> │  ✅ NO field injection — Constructor injection ONLY               │
> │  ✅ Use Java Records for DTOs                                    │
> │  ✅ Custom @ConfigurationProperties for app settings             │
> │  ✅ @Aspect for method-level logging (entry, exit, duration)     │
> │  ✅ ApplicationEvents for decoupled notifications                │
> │  ✅ Proper exception handling with custom exceptions             │
> │  ✅ Unit tests for services (JUnit 5 + Mockito)                 │
> │  ✅ Maven multi-module: core, cli, common                       │
> │  ✅ Structured logging with MDC context                         │
> └─────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 🌐 PHASE 2: BUILDING REST APIs & WEB LAYER
### 📅 Duration: Months 2–4
### 🎯 Goal: Build production-grade RESTful APIs
### 👤 Level: Junior+ Engineer

---

## Module 2.1: Spring MVC & REST Controllers

### Section 2.1.1 — HTTP & REST Foundations in Spring
```
├── @RestController vs @Controller:
│   ├── @RestController = @Controller + @ResponseBody on every method
│   ├── @Controller: For MVC views (Thymeleaf, Freemarker)
│   └── When to use: @RestController for APIs, @Controller for server-side rendering
├── Request Mapping:
│   ├── @RequestMapping: Base annotation (method, path, produces, consumes)
│   ├── @GetMapping: GET requests (read operations)
│   ├── @PostMapping: POST requests (create operations)
│   ├── @PutMapping: PUT requests (full update / replace)
│   ├── @PatchMapping: PATCH requests (partial update)
│   └── @DeleteMapping: DELETE requests (delete operations)
├── Request Data Binding:
│   ├── @PathVariable: /users/{id} → @PathVariable Long id
│   ├── @RequestParam: ?name=John → @RequestParam String name
│   │   ├── required, defaultValue, name attributes
│   │   └── Multiple values: @RequestParam List<String> tags
│   ├── @RequestBody: JSON/XML request body → Java object (Jackson)
│   ├── @RequestHeader: Access HTTP headers
│   ├── @CookieValue: Access cookies
│   └── @ModelAttribute: Form data binding (MVC)
├── Response Handling:
│   ├── ResponseEntity<T>: Full control over status, headers, body
│   │   ├── ResponseEntity.ok(body)
│   │   ├── ResponseEntity.created(uri).body(body)
│   │   ├── ResponseEntity.noContent().build()
│   │   └── ResponseEntity.notFound().build()
│   ├── @ResponseStatus: Set default HTTP status for method/exception
│   ├── Content Negotiation: Accept header, produces attribute
│   └── Streaming: StreamingResponseBody for large responses
├── Jackson (JSON Serialization):
│   ├── @JsonProperty: Custom JSON field names
│   ├── @JsonIgnore: Exclude fields from serialization
│   ├── @JsonInclude(NON_NULL): Exclude null fields
│   ├── @JsonFormat: Date/time formatting
│   ├── @JsonView: Multiple JSON views for same object
│   ├── Custom Serializers/Deserializers: JsonSerializer<T>, JsonDeserializer<T>
│   ├── Mixins: Add annotations without modifying source class
│   └── ObjectMapper Configuration: Global customization in @Configuration
└── URI Design Best Practices:
    ├── Nouns, not verbs: /users, NOT /getUsers
    ├── Plural: /users, NOT /user
    ├── Hierarchical: /users/{userId}/orders/{orderId}
    ├── Filtering: /users?status=active&role=admin
    ├── Sorting: /users?sort=name,asc
    └── HTTP methods convey the action, URI conveys the resource
```

### Section 2.1.2 — Request Validation
```
├── Bean Validation (JSR 380):
│   ├── @NotNull, @NotBlank, @NotEmpty: Null/empty checks
│   ├── @Size(min, max): String length, Collection size
│   ├── @Min, @Max: Numeric range
│   ├── @Pattern(regexp): Regex validation
│   ├── @Email: Email format validation
│   ├── @Past, @Future, @PastOrPresent, @FutureOrPresent: Date validation
│   └── @Positive, @PositiveOrZero, @Negative: Number sign validation
├── Activating Validation:
│   ├── @Valid on @RequestBody: Triggers validation
│   ├── @Validated: Spring-specific, Supports validation groups
│   └── @Valid on nested objects: Cascading validation
├── Validation Groups:
│   ├── Define interfaces: OnCreate, OnUpdate
│   ├── Annotate: @NotNull(groups = OnCreate.class)
│   └── Activate: @Validated(OnCreate.class) on method parameter
├── Custom Validators:
│   ├── Create annotation: @ValidAge
│   ├── Implement ConstraintValidator<ValidAge, Integer>
│   ├── Cross-field validation: Class-level constraint
│   └── Programmatic validation: Validator.validate(object)
├── Validation in @PathVariable / @RequestParam:
│   ├── Add @Validated to controller class
│   ├── Use constraints: @PathVariable @Min(1) Long id
│   └── ConstraintViolationException thrown on failure
└── Error Response:
    ├── MethodArgumentNotValidException: @RequestBody validation failures
    ├── ConstraintViolationException: Path/Query param validation failures
    └── Map to structured error response (see Exception Handling section)
```

### Section 2.1.3 — Exception Handling
```
├── @ExceptionHandler:
│   ├── Method-level in controller: Handle specific exceptions
│   ├── Return ResponseEntity with proper status + error body
│   └── Can handle multiple exceptions: @ExceptionHandler({A.class, B.class})
├── @ControllerAdvice / @RestControllerAdvice:
│   ├── Global exception handling across ALL controllers
│   ├── Centralized error response formatting
│   ├── Can target specific packages: @RestControllerAdvice(basePackages = "com.example.api")
│   └── Multiple @ControllerAdvice classes with @Order
├── Problem Details (RFC 9457 — Spring Boot 3+):
│   ├── Standard error response format:
│   │   ├── type: URI identifying the error type
│   │   ├── title: Human-readable summary
│   │   ├── status: HTTP status code
│   │   ├── detail: Human-readable explanation
│   │   └── instance: URI identifying the specific occurrence
│   ├── ProblemDetail class: Spring 6 built-in support
│   ├── ErrorResponse interface: Implement for custom exceptions
│   └── spring.mvc.problemdetails.enabled=true
├── Custom Exception Hierarchy:
│   ├── BusinessException (abstract): Base for domain exceptions
│   │   ├── ResourceNotFoundException: → 404
│   │   ├── DuplicateResourceException: → 409
│   │   ├── InvalidOperationException: → 422
│   │   └── AccessDeniedException: → 403
│   └── Map each to specific HTTP status + structured response
├── Error Response DTO:
│   ├── timestamp, status, error, message, path
│   ├── errors[] (for validation): field, message, rejectedValue
│   └── traceId: Correlation ID for debugging
└── Anti-patterns:
    ├── Returning stack traces to clients (security risk!)
    ├── Generic 500 for all errors (bad DX)
    ├── Catching Exception (too broad)
    └── Business logic in exception handlers
```

---

## Module 2.2: API Design & Documentation

### Section 2.2.1 — RESTful API Design Patterns
```
├── Pagination:
│   ├── Offset-Based: ?page=0&size=20 — Simple, Skipping rows at scale is slow
│   ├── Cursor-Based: ?cursor=abc123&size=20 — Performant, No skipping
│   ├── Keyset Pagination: WHERE id > :lastId LIMIT 20 — Best for sorted data
│   ├── Spring Data Page<T>: Built-in pagination support
│   ├── Response: content[], page (number, size, totalElements, totalPages)
│   └── HATEOAS Links: next, prev, first, last
├── Filtering & Sorting:
│   ├── Query Params: ?status=active&createdAfter=2024-01-01
│   ├── Sorting: ?sort=createdAt,desc&sort=name,asc
│   ├── Complex Filters: Consider Specification pattern or RSQL
│   └── Spring Data: Pageable, Sort parameters auto-bound
├── Partial Updates (PATCH):
│   ├── JSON Merge Patch (RFC 7386): Simple, Send only changed fields
│   ├── JSON Patch (RFC 6902): Operations array (add, remove, replace, move, copy)
│   └── Implementation: Null vs Absent handling (Jackson JsonNullable)
├── Bulk Operations:
│   ├── POST /users/batch: Create multiple resources
│   ├── Response: Individual status per item (partial success)
│   └── Idempotency: Support idempotency keys for bulk operations
├── Versioning:
│   ├── URI Path: /api/v1/users, /api/v2/users (most common)
│   ├── Request Header: X-API-Version: 2
│   ├── Accept Header: Accept: application/vnd.myapp.v2+json
│   ├── Query Param: /api/users?version=2
│   └── Recommendation: URI path for simplicity, Header for purity
├── HATEOAS (Hypermedia):
│   ├── Spring HATEOAS: EntityModel<T>, CollectionModel<T>, Link, WebMvcLinkBuilder
│   ├── HAL (Hypertext Application Language): _links, _embedded
│   └── Practical Use: Rarely fully implemented, But useful for discoverability
└── API Response Envelope Pattern:
    ├── Wrapped: { "data": {...}, "meta": {...}, "errors": [...] }
    ├── Unwrapped: Return data directly (simpler, preferred)
    └── Decision: Pick one and be consistent across entire API
```

### Section 2.2.2 — API Documentation (OpenAPI / Swagger)
```
├── SpringDoc OpenAPI (Preferred for Spring Boot 3+):
│   ├── Dependency: springdoc-openapi-starter-webmvc-ui
│   ├── Auto-generates: OpenAPI 3.0 spec from your code
│   ├── Swagger UI: /swagger-ui.html — Interactive API docs
│   ├── OpenAPI JSON: /v3/api-docs — Machine-readable spec
│   └── Configuration: SpringDocConfiguration bean
├── Annotations:
│   ├── @Tag: Group endpoints (e.g., "User Management")
│   ├── @Operation: Describe endpoint (summary, description)
│   ├── @Parameter: Describe path/query parameters
│   ├── @ApiResponse: Document response codes + schemas
│   ├── @Schema: Describe request/response model fields
│   ├── @Hidden: Exclude endpoint from docs
│   └── @SecurityRequirement: Document required auth
├── Best Practices:
│   ├── API-First: Design OpenAPI spec BEFORE coding (openapi-generator)
│   ├── Examples: Provide request/response examples in annotations
│   ├── Descriptions: Every field, Every endpoint, Every parameter
│   ├── Error Schemas: Document error response format
│   └── Versioned Docs: Separate specs per API version
└── Code Generation:
    ├── openapi-generator-maven-plugin: Generate client SDKs
    ├── Server Stubs: Generate controller interfaces from spec
    └── Languages: Java, TypeScript, Python, Go, Kotlin, etc.
```

### Section 2.2.3 — Content Negotiation & Media Types
```
├── JSON (Default): application/json — Jackson serialization
├── XML: application/xml — Add jackson-dataformat-xml dependency
├── Custom Media Types: application/vnd.myapp.user.v2+json
├── Configuration:
│   ├── produces = MediaType.APPLICATION_JSON_VALUE
│   ├── consumes = MediaType.APPLICATION_JSON_VALUE
│   └── Global: WebMvcConfigurer.configureContentNegotiation()
├── Multipart File Upload:
│   ├── @RequestParam MultipartFile file
│   ├── spring.servlet.multipart.max-file-size=10MB
│   ├── Multiple files: @RequestParam List<MultipartFile> files
│   └── With metadata: @RequestPart for mixed multipart
└── Streaming Responses:
    ├── StreamingResponseBody: Write to OutputStream directly
    ├── Resource: Return file as Resource (InputStreamResource, ClassPathResource)
    └── Content-Disposition header: inline vs attachment
```

---

## Module 2.3: HTTP Client (Calling External APIs)

### Section 2.3.1 — RestClient (Spring Boot 3.2+ — Recommended)
```
├── Creation: RestClient.builder().baseUrl("...").build()
├── Fluent API:
│   ├── .get().uri("/users/{id}", id).retrieve().body(User.class)
│   ├── .post().uri("/users").body(userDto).retrieve().body(User.class)
│   └── .delete().uri("/users/{id}", id).retrieve().toBodilessEntity()
├── Error Handling:
│   ├── .onStatus(HttpStatusCode::is4xxClientError, (req, res) -> ...)
│   ├── .onStatus(HttpStatusCode::is5xxServerError, (req, res) -> ...)
│   └── Default: Throws RestClientException on error
├── Configuration:
│   ├── Default headers: .defaultHeader(HttpHeaders.AUTHORIZATION, "Bearer ...")
│   ├── Interceptors: ClientHttpRequestInterceptor
│   ├── Timeouts: HttpComponentsClientHttpRequestFactory (connection + read timeout)
│   └── Base URL: .baseUrl("https://api.example.com/v1")
└── Testing: MockRestServiceServer for integration tests
```

### Section 2.3.2 — WebClient (Reactive — for non-blocking calls)
```
├── Non-Blocking: Built on Project Reactor, Returns Mono<T> / Flux<T>
├── Usage in non-reactive apps: .block() to get synchronous result
├── Creation: WebClient.builder().baseUrl("...").build()
├── Configuration: Timeouts, Retry, Error handling
├── When to use: High-concurrency external API calls, Streaming responses
└── Comparison: RestClient (blocking, simpler) vs WebClient (non-blocking, more complex)
```

### Section 2.3.3 — Declarative HTTP Clients
```
├── Spring 6 HTTP Interface:
│   ├── Define interface with @GetExchange, @PostExchange annotations
│   ├── Spring creates proxy implementation automatically
│   ├── Similar to Feign but Spring-native
│   └── Backed by RestClient or WebClient
├── OpenFeign (Spring Cloud):
│   ├── @FeignClient(name = "user-service", url = "...")
│   ├── Declarative interface with @GetMapping, @PostMapping
│   ├── Integrates with Eureka for service discovery
│   ├── Error handling: ErrorDecoder
│   └── Interceptors: RequestInterceptor (add auth headers)
└── Resilience: Integrate with Resilience4j for retry, Circuit breaker, Timeout
```

---

## Module 2.4: Servlet Architecture & Filters

### Section 2.4.1 — Servlet Container & Request Lifecycle
```
├── Request Flow:
│   ├── Client → Embedded Tomcat → Filter Chain → DispatcherServlet
│   ├── → HandlerMapping → HandlerAdapter → Controller Method
│   ├── → Return Value → HttpMessageConverter → Response
│   └── → Filter Chain (reverse) → Client
├── DispatcherServlet:
│   ├── Front Controller pattern
│   ├── HandlerMapping: Maps URL to controller method
│   ├── HandlerAdapter: Invokes the controller method
│   ├── ViewResolver: Resolves view name to view (MVC only)
│   └── HandlerExceptionResolver: Maps exceptions to responses
├── Filters:
│   ├── javax.servlet.Filter / jakarta.servlet.Filter (Jakarta EE 9+)
│   ├── OncePerRequestFilter: Guarantees single execution per request
│   ├── FilterRegistrationBean: Register filters with ordering
│   ├── Use cases: CORS, Logging, Authentication, Request ID generation
│   └── Ordering: @Order annotation or FilterRegistrationBean.setOrder()
├── Interceptors (Spring MVC):
│   ├── HandlerInterceptor: preHandle, postHandle, afterCompletion
│   ├── Registered via WebMvcConfigurer.addInterceptors()
│   ├── vs Filters: Interceptors have access to Handler info, Filters don't
│   └── Use cases: Logging, Timing, Tenant context, Locale resolution
└── Thread Model:
    ├── Default: One thread per request (Tomcat thread pool)
    ├── Default Pool Size: 200 threads (server.tomcat.threads.max)
    ├── Connection Queue: server.tomcat.accept-count=100
    ├── Virtual Threads (Java 21+): spring.threads.virtual.enabled=true
    └── Impact: With virtual threads, thousands of concurrent requests possible
```

---

## Module 2.5: Testing REST APIs

### Section 2.5.1 — Testing Strategies
```
├── @WebMvcTest (Controller Slice Test):
│   ├── Loads ONLY web layer: Controllers, Filters, ControllerAdvice
│   ├── Auto-configures MockMvc
│   ├── Mock dependencies with @MockBean
│   ├── Fast: Doesn't load full ApplicationContext
│   └── Use for: Testing request mapping, Validation, Serialization, Exception handling
├── MockMvc:
│   ├── mockMvc.perform(get("/api/users"))
│   │   ├── .andExpect(status().isOk())
│   │   ├── .andExpect(jsonPath("$.name").value("John"))
│   │   ├── .andExpect(content().contentType(MediaType.APPLICATION_JSON))
│   │   └── .andDo(print()) — Print request/response for debugging
│   ├── POST with body: .perform(post("/api/users")
│   │   .contentType(APPLICATION_JSON).content(json))
│   ├── With auth: .with(SecurityMockMvcRequestPostProcessors.jwt())
│   └── File upload: MockMultipartFile + multipart()
├── @SpringBootTest (Full Integration Test):
│   ├── Loads FULL ApplicationContext
│   ├── webEnvironment = RANDOM_PORT: Start real server
│   ├── TestRestTemplate / WebTestClient: Test real HTTP calls
│   ├── @Testcontainers: Real database in Docker
│   └── Use for: Full integration testing, End-to-end API tests
├── TestRestTemplate:
│   ├── Synchronous HTTP client for tests
│   ├── restTemplate.getForEntity("/api/users", UserResponse.class)
│   ├── Follows redirects, Manages cookies
│   └── Best for: @SpringBootTest with RANDOM_PORT
├── REST Assured (Alternative):
│   ├── given().contentType(JSON).body(request)
│   │   .when().post("/api/users")
│   │   .then().statusCode(201).body("id", notNullValue())
│   └── More readable, BDD-style API testing
└── Contract Testing:
    ├── Spring Cloud Contract: Define contracts in Groovy/YAML
    ├── Auto-generates: Tests for provider, Stubs for consumer
    ├── WireMock: Stub external APIs in tests
    └── Pact: Consumer-driven contract testing
```

---

> ### 🛠️ PHASE 2 PROJECT: **Blog Platform REST API**
> ```
> ┌─────────────────────────────────────────────────────────────────┐
> │                 BLOG PLATFORM REST API                          │
> ├─────────────────────────────────────────────────────────────────┤
> │ Features:                                                       │
> │  • Users: Registration, Profile management                     │
> │  • Posts: CRUD with rich text, Tags, Categories                 │
> │  • Comments: Nested comments (parent-child)                     │
> │  • Pagination: Cursor-based for posts feed                     │
> │  • Search: Filter by tag, category, author, date range          │
> │  • File Upload: Post images (multipart)                         │
> │  • External API: Fetch author's GitHub profile (RestClient)     │
> │                                                                 │
> │ Technical Requirements:                                         │
> │  ✅ RESTful URL design following best practices                  │
> │  ✅ Bean Validation on all request DTOs                          │
> │  ✅ Custom validators: @UniqueEmail, @ValidSlug                  │
> │  ✅ Global exception handling with ProblemDetail (RFC 9457)      │
> │  ✅ OpenAPI/Swagger documentation (SpringDoc)                    │
> │  ✅ DTO ↔ Entity mapping (MapStruct or manual)                  │
> │  ✅ Request/Response logging filter with correlation ID          │
> │  ✅ Content negotiation: JSON + XML support                     │
> │  ✅ RestClient: Call external GitHub API with error handling     │
> │  ✅ Tests: @WebMvcTest (every endpoint) + MockMvc assertions    │
> │  ✅ Tests: @SpringBootTest integration tests with Testcontainers│
> │  ✅ API versioning: v1 endpoints                                │
> └─────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 🗄️ PHASE 3: DATA ACCESS & PERSISTENCE
### 📅 Duration: Months 4–6
### 🎯 Goal: Master every way Spring Boot accesses data
### 👤 Level: Mid-Level Engineer

---

## Module 3.1: Spring Data JPA (Deep Dive)

### Section 3.1.1 — JPA & Hibernate Fundamentals
```
├── JPA (Jakarta Persistence API):
│   ├── Specification (not implementation): Defines ORM standard
│   ├── Hibernate: Default JPA implementation in Spring Boot
│   └── Persistence Unit: Configuration of entity manager
├── Entity Mapping:
│   ├── @Entity: Marks class as JPA entity
│   ├── @Table: Custom table name, Schema, Unique constraints
│   ├── @Id: Primary key
│   ├── @GeneratedValue: ID generation strategy
│   │   ├── IDENTITY: Auto-increment (MySQL) — bad for batch inserts
│   │   ├── SEQUENCE: Database sequence (PostgreSQL) — preferred
│   │   ├── TABLE: Sequence table (portable but slow)
│   │   └── UUID: UUID generation (Java 17+ or custom)
│   ├── @Column: Name, Nullable, Length, Unique, columnDefinition
│   ├── @Enumerated: EnumType.STRING (preferred) vs EnumType.ORDINAL (fragile)
│   ├── @Temporal: Date/Time mapping (use java.time with JPA 2.2+)
│   ├── @Lob: Large objects (CLOB, BLOB)
│   ├── @Embedded / @Embeddable: Value objects (Address, Money)
│   └── @MappedSuperclass: Shared fields (BaseEntity: id, createdAt, updatedAt)
├── Relationship Mapping:
│   ├── @OneToMany / @ManyToOne: Most common
│   │   ├── Owning Side: @ManyToOne (has FK column)
│   │   ├── Inverse Side: @OneToMany(mappedBy = "parent")
│   │   ├── Cascade: CascadeType.ALL, PERSIST, MERGE, REMOVE
│   │   └── OrphanRemoval: Remove child when detached from parent
│   ├── @ManyToMany:
│   │   ├── Join Table: @JoinTable(name, joinColumns, inverseJoinColumns)
│   │   ├── Avoid: Prefer explicit join entity for additional attributes
│   │   └── Set vs List: Use Set to avoid Hibernate bag issues
│   ├── @OneToOne:
│   │   ├── Shared Primary Key: @MapsId
│   │   └── Lazy Loading Gotcha: OneToOne is EAGER by default on non-owning side
│   └── Fetch Types:
│       ├── LAZY (default for collections): Load on access — PREFERRED
│       ├── EAGER: Load immediately — AVOID (causes N+1, loads too much)
│       └── Rule: ALWAYS use LAZY, Use JOIN FETCH or EntityGraph for eager loading
├── Inheritance Mapping:
│   ├── SINGLE_TABLE (default): All subclasses in one table (discriminator column)
│   │   ├── Pros: Simple, Fast queries, No joins
│   │   └── Cons: Nullable columns, Table bloat
│   ├── JOINED: Separate table per class, JOIN on queries
│   │   ├── Pros: Normalized, No nullable columns
│   │   └── Cons: Slow queries (multiple joins)
│   ├── TABLE_PER_CLASS: Separate table per concrete class
│   │   ├── Pros: No discriminator needed
│   │   └── Cons: Polymorphic queries are expensive (UNION ALL)
│   └── Recommendation: SINGLE_TABLE for most cases
└── Entity Best Practices:
    ├── equals/hashCode: Use business key or @Id (never use all fields)
    ├── toString: Exclude lazy collections (triggers lazy load!)
    ├── No-arg constructor: Required by JPA (can be protected)
    ├── Avoid Lombok @Data on entities: Breaks equals/hashCode
    └── Use Lombok @Getter, @Setter, @NoArgsConstructor, @AllArgsConstructor separately
```

### Section 3.1.2 — Spring Data Repositories
```
├── Repository Hierarchy:
│   ├── Repository<T, ID>: Marker interface
│   ├── CrudRepository<T, ID>: Basic CRUD operations
│   ├── ListCrudRepository<T, ID>: Returns List instead of Iterable
│   ├── PagingAndSortingRepository<T, ID>: Adds pagination + sorting
│   ├── JpaRepository<T, ID>: All of the above + JPA-specific (flush, batch)
│   └── Custom: Extend JpaRepository + add your methods
├── Query Methods (Derived Queries):
│   ├── findByName(String name): WHERE name = ?
│   ├── findByNameAndStatus(String name, Status status): AND
│   ├── findByNameOrEmail(String name, String email): OR
│   ├── findByCreatedAtBetween(LocalDateTime start, LocalDateTime end)
│   ├── findByNameContainingIgnoreCase(String name): LIKE %name%
│   ├── findByStatusIn(List<Status> statuses): IN clause
│   ├── findByParentIsNull(): IS NULL
│   ├── findByActiveTrue(): Boolean field check
│   ├── countByStatus(Status status): COUNT query
│   ├── existsByEmail(String email): EXISTS check
│   ├── deleteByStatus(Status status): DELETE query
│   ├── findFirst5ByOrderByCreatedAtDesc(): Top N + Ordering
│   └── Naming Convention: find...By, count...By, exists...By, delete...By
├── @Query (Custom JPQL/SQL):
│   ├── JPQL: @Query("SELECT u FROM User u WHERE u.email = :email")
│   ├── Native SQL: @Query(value = "SELECT * FROM users WHERE ...", nativeQuery = true)
│   ├── Named Parameters: @Param("email") String email
│   ├── Modifying: @Modifying @Query("UPDATE User u SET u.status = :status WHERE ...")
│   │   └── @Modifying(clearAutomatically = true): Clear persistence context after update
│   └── SpEL: #{#entityName} — Dynamic entity name
├── Pagination & Sorting:
│   ├── Pageable: Page<User> findByStatus(Status s, Pageable pageable)
│   ├── PageRequest.of(0, 20, Sort.by("name").ascending())
│   ├── Slice<T>: Like Page but without total count (better performance)
│   ├── Sort: Sort.by(Sort.Direction.DESC, "createdAt")
│   └── Custom Pageable: Limit max page size in configuration
├── Projections:
│   ├── Interface Projection: Interface with getter methods (SELECT only needed columns)
│   ├── Class Projection: DTO with constructor (record-based)
│   ├── Dynamic Projection: <T> T findByEmail(String email, Class<T> type)
│   └── @Value SpEL: @Value("#{target.firstName + ' ' + target.lastName}") String fullName
├── Specifications (Criteria API wrapper):
│   ├── JpaSpecificationExecutor<T>: Extend your repository
│   ├── Specification<T>: Reusable, Composable query predicates
│   ├── Spec.where(hasStatus(ACTIVE)).and(hasRole(ADMIN))
│   └── Use case: Dynamic query building, Complex search/filtering
└── Custom Repository Implementation:
    ├── Define: UserRepositoryCustom (interface)
    ├── Implement: UserRepositoryCustomImpl (class)
    ├── Extend: UserRepository extends JpaRepository<User, Long>, UserRepositoryCustom
    ├── Spring auto-detects *Impl suffix
    └── Use case: Complex queries, Criteria API, Bulk operations
```

### Section 3.1.3 — Hibernate Performance & Pitfalls
```
├── N+1 Problem:
│   ├── What: 1 query for parent + N queries for children
│   ├── Detection: Enable SQL logging (spring.jpa.show-sql=true + p6spy)
│   ├── Fix 1: JOIN FETCH — @Query("SELECT u FROM User u JOIN FETCH u.orders")
│   ├── Fix 2: @EntityGraph — @EntityGraph(attributePaths = {"orders"})
│   ├── Fix 3: @BatchSize(size = 25) — Batch lazy loading
│   ├── Fix 4: Subselect: @Fetch(FetchMode.SUBSELECT)
│   └── Best Practice: ALWAYS use LAZY loading + explicit fetching
├── Persistence Context (First-Level Cache):
│   ├── EntityManager: Tracks entity state within a transaction
│   ├── Entity States: Transient → Managed → Detached → Removed
│   ├── Dirty Checking: Automatic UPDATE on flush (no explicit save needed)
│   ├── Flush Modes: AUTO (default), COMMIT
│   ├── Clear: entityManager.clear() — Detach all entities
│   └── Gotcha: Large batch operations → OutOfMemoryError (clear periodically)
├── Second-Level Cache:
│   ├── Shared cache across sessions/transactions
│   ├── Providers: Ehcache, Hazelcast, Infinispan, Caffeine
│   ├── @Cacheable: Entity-level caching
│   ├── @Cache(usage = CacheConcurrencyStrategy.READ_WRITE)
│   ├── Query Cache: Cache query results (rarely worth it)
│   └── Invalidation: Automatic on entity update (within same app)
├── Batch Operations:
│   ├── spring.jpa.properties.hibernate.jdbc.batch_size=50
│   ├── spring.jpa.properties.hibernate.order_inserts=true
│   ├── spring.jpa.properties.hibernate.order_updates=true
│   ├── Flush + Clear periodically: Every N entities
│   ├── IDENTITY generation: Disables batching! Use SEQUENCE instead
│   └── Bulk UPDATE/DELETE: Use @Modifying @Query (bypasses persistence context)
├── Connection Pooling:
│   ├── HikariCP (default in Spring Boot): Fastest connection pool
│   ├── Key Settings:
│   │   ├── maximum-pool-size: 10 (default) — tune based on load
│   │   ├── minimum-idle: Same as max (keep pool warm)
│   │   ├── connection-timeout: 30s (how long to wait for connection)
│   │   ├── idle-timeout: 600s (close idle connections)
│   │   └── max-lifetime: 1800s (close connections before DB timeout)
│   ├── Pool Sizing: connections = (core_count * 2) + effective_spindle_count
│   └── Monitoring: HikariCP metrics → Micrometer → Prometheus
└── Common Performance Killers:
    ├── SELECT * (use projections, select only needed columns)
    ├── Open Session in View (OSIV): spring.jpa.open-in-view=false (disable!)
    ├── Cartesian Product: Multiple JOIN FETCH on collections → data explosion
    ├── Missing Indexes: Always add indexes for query WHERE/JOIN columns
    └── Excessive Cascade: CascadeType.ALL can cause unexpected deletes/updates
```

### Section 3.1.4 — Transactions
```
├── @Transactional:
│   ├── Class-Level: All public methods are transactional
│   ├── Method-Level: Specific methods only
│   ├── Properties:
│   │   ├── propagation: REQUIRED (default), REQUIRES_NEW, NESTED, SUPPORTS, etc.
│   │   ├── isolation: DEFAULT, READ_COMMITTED, REPEATABLE_READ, SERIALIZABLE
│   │   ├── readOnly: true/false — Optimization hint (no dirty checking)
│   │   ├── timeout: Max transaction duration (seconds)
│   │   ├── rollbackFor: Which exceptions trigger rollback
│   │   └── noRollbackFor: Exceptions that should NOT rollback
│   └── Default: Rollback on RuntimeException/Error, NOT on checked exceptions
├── Propagation Types:
│   ├── REQUIRED: Join existing or create new (default, most common)
│   ├── REQUIRES_NEW: Always create new (suspend existing)
│   │   └── Use case: Audit logging that MUST persist even if main tx fails
│   ├── NESTED: Nested transaction with savepoint
│   ├── SUPPORTS: Join existing, Run non-transactional if none
│   ├── NOT_SUPPORTED: Suspend existing, Run non-transactional
│   └── MANDATORY: Must run in existing transaction (throws if none)
├── Gotchas:
│   ├── Self-Invocation: this.method() bypasses proxy → NO transaction!
│   │   └── Fix: Inject self, Use TransactionTemplate, Refactor to different bean
│   ├── Private Methods: @Transactional has NO effect on private methods
│   ├── Runtime vs Checked Exceptions: Only unchecked rollback by default
│   │   └── Fix: @Transactional(rollbackFor = Exception.class)
│   └── Read-Only Optimization: Set readOnly=true for queries (skips dirty checking)
├── Programmatic Transactions:
│   ├── TransactionTemplate: Callback-based, More control
│   ├── PlatformTransactionManager: Manual begin/commit/rollback
│   └── When: Dynamic transaction decisions, Transaction within lambda
└── Testing Transactions:
    ├── @Transactional on test: Auto-rolls back after each test
    ├── @Commit: Override auto-rollback
    └── @Sql: Execute SQL scripts before/after test
```

### Section 3.1.5 — Auditing & Soft Deletes
```
├── Spring Data Auditing:
│   ├── @EnableJpaAuditing: Activate auditing
│   ├── @CreatedDate: Auto-set creation timestamp
│   ├── @LastModifiedDate: Auto-set update timestamp
│   ├── @CreatedBy: Auto-set creator (needs AuditorAware bean)
│   ├── @LastModifiedBy: Auto-set last modifier
│   ├── AuditorAware<String>: Custom implementation (get from SecurityContext)
│   └── BaseEntity: Abstract class with all audit fields
├── Soft Deletes:
│   ├── @SQLDelete(sql = "UPDATE users SET deleted = true WHERE id = ?")
│   ├── @Where(clause = "deleted = false") — Hibernate annotation (deprecated in 6.3+)
│   ├── @FilterDef + @Filter: Hibernate filters for soft delete
│   ├── Alternative: Specification-based filtering (more explicit)
│   └── Consideration: Unique constraints + Soft deletes = Partial unique indexes
├── Entity Listeners:
│   ├── @EntityListeners(AuditingEntityListener.class): Spring auditing
│   ├── @PrePersist, @PostPersist: Before/after insert
│   ├── @PreUpdate, @PostUpdate: Before/after update
│   ├── @PreRemove, @PostRemove: Before/after delete
│   └── Custom Listener: Extract listener class with @EntityListeners
└── Envers (Hibernate Audit):
    ├── @Audited: Track all changes to entity
    ├── Audit Tables: Automatic revision tables (*_AUD)
    ├── AuditReader: Query historical data
    └── Use case: Compliance, Regulatory requirements, Change history
```

---

## Module 3.2: Database Migration

### Section 3.2.1 — Flyway
```
├── Convention: V1__Create_users_table.sql, V2__Add_email_column.sql
├── Location: src/main/resources/db/migration/
├── Naming: V{version}__{description}.sql (two underscores!)
├── Repeatable: R__Create_views.sql (re-run on checksum change)
├── Undo: U1__Undo_create_users.sql (Flyway Teams only)
├── Callbacks: beforeMigrate, afterMigrate, afterEachMigrate
├── Configuration:
│   ├── spring.flyway.enabled=true (default when on classpath)
│   ├── spring.flyway.locations=classpath:db/migration
│   ├── spring.flyway.baseline-on-migrate=true (for existing databases)
│   └── spring.flyway.validate-on-migrate=true (checksum validation)
├── Profiles: V1__Create_users.sql + Vendor-specific: db/migration/postgresql/
├── Java Migrations: Implement JavaMigration interface (for complex data migrations)
└── Best Practices:
    ├── NEVER modify applied migrations (checksum will fail)
    ├── ALWAYS test migrations against production-like data
    ├── Small, incremental migrations (not one massive script)
    ├── Include both UP and DOWN logic in documentation
    └── Backward compatible: Expand-Contract pattern for column renames/drops
```

### Section 3.2.2 — Liquibase (Alternative)
```
├── Changelog: XML, YAML, JSON, or SQL format
├── Changesets: Uniquely identified (id + author + filename)
├── Rollback: Explicit rollback commands per changeset
├── Preconditions: Check before applying (tableExists, columnExists)
├── Contexts: Apply changesets conditionally (dev, test, prod)
├── Diff: Generate changelog from database diff
├── Flyway vs Liquibase:
│   ├── Flyway: SQL-first, Simpler, Convention over configuration
│   └── Liquibase: XML/YAML changelogs, More features, Rollback support
└── Recommendation: Flyway for most projects (simpler, SQL-native)
```

---

## Module 3.3: Alternative Data Access

### Section 3.3.1 — Spring Data JDBC (Simpler Alternative to JPA)
```
├── Philosophy: Simple, No lazy loading, No dirty checking, No session cache
├── Aggregates: True DDD aggregate support
│   └── Rule: Spring Data JDBC loads/saves entire aggregate at once
├── No Proxy Magic: What you see is what you get
├── Repository: CrudRepository<T, ID> (same interface as JPA)
├── @Query: SQL queries (not JPQL) — works with native SQL
├── One-to-Many: Embedded Set<Child> in aggregate root
├── When to use:
│   ├── Simple domain model
│   ├── Want DDD aggregates without Hibernate complexity
│   ├── Prefer explicit SQL control
│   └── Don't need lazy loading, caching, inheritance mapping
└── When NOT to use: Complex relationships, Need Hibernate second-level cache
```

### Section 3.3.2 — Spring Data MongoDB
```
├── @Document: Marks class as MongoDB document
├── MongoRepository<T, ID>: Repository interface
├── MongoTemplate: Lower-level operations, Aggregation pipeline
├── Query Methods: Same derived query naming as JPA
├── @DBRef: References between documents (use sparingly)
├── Embedded Documents: Preferred over references (denormalization)
├── Aggregation Pipeline: MongoTemplate.aggregate()
├── Change Streams: React to database changes in real-time
├── Transactions: Multi-document ACID transactions (MongoDB 4.0+)
└── Indexes: @Indexed, @CompoundIndex, @TextIndexed
```

### Section 3.3.3 — Spring Data Redis
```
├── RedisTemplate<K, V>: Low-level operations
├── StringRedisTemplate: String-specialized RedisTemplate
├── @RedisHash: Map object to Redis hash
├── CrudRepository<T, ID>: For @RedisHash entities
├── Operations:
│   ├── opsForValue(): String operations (SET, GET)
│   ├── opsForHash(): Hash operations (HSET, HGET)
│   ├── opsForList(): List operations (LPUSH, RPUSH, LRANGE)
│   ├── opsForSet(): Set operations (SADD, SMEMBERS)
│   └── opsForZSet(): Sorted set operations (ZADD, ZRANGE)
├── Serialization: Jackson2JsonRedisSerializer, GenericJackson2JsonRedisSerializer
├── Pub/Sub: MessageListener, RedisMessageListenerContainer
├── Lua Scripts: Execute atomic operations
├── Pipelining: Batch commands for performance
└── Lettuce vs Jedis: Lettuce (default, reactive-ready) vs Jedis (legacy, thread-safe)
```

### Section 3.3.4 — Spring Data Elasticsearch
```
├── @Document(indexName = "products"): Map to ES index
├── ElasticsearchRepository<T, ID>: Repository interface
├── ElasticsearchOperations: Lower-level queries
├── @Field: Mapping (type = FieldType.Text, analyzer = "standard")
├── NativeQuery: Build complex ES queries
├── Highlighting: Search result highlighting
├── Aggregations: Terms, Date histogram, Nested aggregations
└── Index Management: @Setting, @Mapping, Index lifecycle
```

### Section 3.3.5 — Spring Caching Abstraction
```
├── @EnableCaching: Activate caching
├── Annotations:
│   ├── @Cacheable("users"): Cache method result
│   │   ├── key: SpEL for custom key (#id, #user.email)
│   │   ├── condition: Cache only if (#result != null)
│   │   └── unless: Don't cache if (#result.age < 18)
│   ├── @CachePut("users"): Always execute + update cache
│   ├── @CacheEvict("users"): Remove from cache
│   │   ├── allEntries = true: Clear entire cache
│   │   └── beforeInvocation = true: Evict before method runs
│   └── @Caching: Combine multiple cache annotations
├── Cache Providers:
│   ├── ConcurrentMapCache: In-memory, Simple, No TTL (default)
│   ├── Caffeine: High-performance in-memory, TTL support (recommended for local)
│   ├── Redis: Distributed cache, Shared across instances
│   ├── Ehcache: Feature-rich, Offheap support
│   └── Hazelcast: Distributed, In-memory data grid
├── Caffeine Configuration:
│   ├── spring.cache.type=caffeine
│   ├── spring.cache.caffeine.spec=maximumSize=500,expireAfterWrite=10m
│   └── Custom CacheManager: Different configs per cache name
├── Redis Cache Configuration:
│   ├── spring.cache.type=redis
│   ├── spring.cache.redis.time-to-live=60m
│   ├── RedisCacheConfiguration: Custom serialization, TTL per cache
│   └── Cache Key Prefix: Avoid collisions in shared Redis
├── Multi-Level Caching: L1 (Caffeine) + L2 (Redis) pattern
└── Cache Gotchas:
    ├── Self-Invocation: Same AOP proxy issue as @Transactional
    ├── Null Caching: Cache null results? (depends on use case)
    ├── Cache Warming: Pre-load cache on startup
    └── Serialization: Cached objects MUST be serializable (for Redis)
```

---

## Module 3.4: Multi-DataSource & Advanced Patterns

### Section 3.4.1 — Multiple DataSources
```
├── Configuration: Define multiple DataSource beans
├── @Primary: Default DataSource
├── @Qualifier: Select specific DataSource
├── Separate EntityManagerFactory per DataSource
├── Separate TransactionManager per DataSource
├── @Transactional("secondaryTransactionManager"): Specify which TX manager
├── Base Package Scanning: Each DataSource scans different entity packages
└── Use case: Read-write splitting, Multi-database architecture
```

### Section 3.4.2 — Read-Write Splitting
```
├── AbstractRoutingDataSource: Route queries to different DataSources
├── @Transactional(readOnly = true): Route to read replica
├── Custom Annotation: @ReadOnly for explicit routing
├── Implementation: ThreadLocal to track current DataSource key
├── Connection Pool: Separate HikariCP pool per DataSource
└── Use case: Scale reads independently, Reduce primary DB load
```

---

> ### 🛠️ PHASE 3 PROJECT: **Multi-Tenant Inventory Management System**
> ```
> ┌─────────────────────────────────────────────────────────────────┐
> │          MULTI-TENANT INVENTORY MANAGEMENT SYSTEM               │
> ├─────────────────────────────────────────────────────────────────┤
> │ Features:                                                       │
> │  • Products with categories, SKUs, variants                     │
> │  • Warehouse management with stock levels                       │
> │  • Stock movements: In, Out, Transfer, Adjustment               │
> │  • Supplier management with purchase orders                     │
> │  • Search: Full-text product search (Elasticsearch)             │
> │  • Caching: Product catalog cached (Caffeine + Redis)           │
> │  • Audit: Complete change history (Envers)                      │
> │                                                                 │
> │ Technical Requirements:                                         │
> │  ✅ Spring Data JPA: Complex entity relationships                │
> │  ✅ Flyway: 10+ migration scripts (incremental schema evolution) │
> │  ✅ N+1 Prevention: EntityGraph + JOIN FETCH (NO lazy load bugs) │
> │  ✅ Specifications: Dynamic product search/filtering              │
> │  ✅ Projections: DTO projections for list views (no SELECT *)    │
> │  ✅ Auditing: @CreatedDate, @LastModifiedDate, @CreatedBy        │
> │  ✅ Soft Deletes: Products are archived, never hard-deleted      │
> │  ✅ @Transactional: Proper propagation, Read-only where possible │
> │  ✅ Caching: L1 Caffeine + L2 Redis, Cache eviction on updates   │
> │  ✅ Spring Data Elasticsearch: Product search index               │
> │  ✅ Spring Data Redis: Stock level caching + Pub/Sub for updates  │
> │  ✅ Batch Operations: Bulk product import (1000+ items)           │
> │  ✅ Testcontainers: PostgreSQL + Redis + Elasticsearch in tests   │
> │  ✅ HikariCP monitoring: Pool metrics exposed via Actuator        │
> │  ✅ Open Session in View: DISABLED                                │
> └─────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 🛡️ PHASE 4: SPRING SECURITY (DEEP DIVE)
### 📅 Duration: Months 6–8
### 🎯 Goal: Secure your application properly — authentication, authorization, and beyond
### 👤 Level: Mid-Level Engineer

---

## Module 4.1: Spring Security Fundamentals

### Section 4.1.1 — Security Architecture
```
├── Security Filter Chain:
│   ├── Request → DelegatingFilterProxy → FilterChainProxy → SecurityFilterChain
│   ├── Key Filters (in order):
│   │   ├── SecurityContextPersistenceFilter: Load SecurityContext
│   │   ├── CorsFilter: CORS handling
│   │   ├── CsrfFilter: CSRF protection
│   │   ├── LogoutFilter: Process logout
│   │   ├── UsernamePasswordAuthenticationFilter: Form login
│   │   ├── BearerTokenAuthenticationFilter: JWT/OAuth2 token
│   │   ├── ExceptionTranslationFilter: Handle AuthenticationException, AccessDeniedException
│   │   └── AuthorizationFilter: Check permissions (last filter)
│   └── Multiple Filter Chains: Different security for /api/** vs /admin/**
├── SecurityContext:
│   ├── SecurityContextHolder: Thread-local storage of current authentication
│   ├── SecurityContext.getAuthentication(): Get current user
│   ├── Authentication: Principal + Credentials + Authorities
│   ├── Propagation: SecurityContextHolder.MODE_INHERITABLETHREADLOCAL (for async)
│   └── @AuthenticationPrincipal: Inject current user in controller method
├── Configuration (Spring Security 6+):
│   ├── @Configuration + @EnableWebSecurity
│   ├── SecurityFilterChain @Bean (replaces WebSecurityConfigurerAdapter — deprecated)
│   ├── Lambda DSL:
│   │   http.authorizeHttpRequests(auth -> auth
│   │       .requestMatchers("/api/public/**").permitAll()
│   │       .requestMatchers("/api/admin/**").hasRole("ADMIN")
│   │       .anyRequest().authenticated()
│   │   )
│   └── Multiple SecurityFilterChain beans with @Order
└── Authentication Manager:
    ├── AuthenticationManager: Authenticates Authentication objects
    ├── ProviderManager: Delegates to AuthenticationProvider(s)
    ├── AuthenticationProvider: Strategy for authentication logic
    └── UserDetailsService: Load user from database/LDAP/etc.
```

### Section 4.1.2 — Authentication Mechanisms
```
├── Form-Based Login:
│   ├── http.formLogin(form -> form.loginPage("/login"))
│   ├── UsernamePasswordAuthenticationFilter: Processes login form
│   ├── AuthenticationSuccessHandler: Redirect after login
│   ├── AuthenticationFailureHandler: Handle login failure
│   └── RememberMe: Persistent token, Cookie-based
├── HTTP Basic:
│   ├── http.httpBasic(Customizer.withDefaults())
│   ├── Base64(username:password) in Authorization header
│   └── Use case: Internal APIs, Simple services, Dev/Testing
├── JWT (JSON Web Token):
│   ├── Stateless Authentication: No server-side session
│   ├── Spring Security OAuth2 Resource Server:
│   │   ├── spring-boot-starter-oauth2-resource-server
│   │   ├── JwtDecoder @Bean: Validate JWT signature
│   │   ├── http.oauth2ResourceServer(oauth -> oauth.jwt(...))
│   │   └── spring.security.oauth2.resourceserver.jwt.issuer-uri=...
│   ├── Custom JWT Filter (if not using OAuth2):
│   │   ├── OncePerRequestFilter: Extract token → Validate → Set SecurityContext
│   │   ├── JJWT library or Nimbus JOSE: Token creation/validation
│   │   └── Register before UsernamePasswordAuthenticationFilter
│   ├── Token Structure: Header.Payload.Signature
│   ├── Claims: sub, exp, iat, iss, roles/authorities
│   ├── Access Token: Short-lived (15-30 minutes)
│   └── Refresh Token: Long-lived, Stored in HttpOnly cookie or DB
├── OAuth2 Login (Social Login):
│   ├── spring-boot-starter-oauth2-client
│   ├── Providers: Google, GitHub, Facebook, Okta, Azure AD
│   ├── Configuration: spring.security.oauth2.client.registration.google.*
│   ├── OAuth2UserService: Custom user processing after OAuth login
│   └── Linking: Map OAuth identity to local user account
├── API Key Authentication:
│   ├── Custom Filter: Extract API key from header/query param
│   ├── Validate against database/cache
│   └── Use case: Service-to-service, Public APIs
└── UserDetailsService:
    ├── loadUserByUsername(String username): Load user from your data store
    ├── UserDetails: username, password, authorities, enabled, accountNonLocked, etc.
    ├── Custom Implementation: JPA-backed user loading
    ├── PasswordEncoder: BCryptPasswordEncoder (default recommendation)
    │   ├── bcrypt: Adaptive, Salt built-in, Recommended
    │   ├── argon2: Memory-hard, Most secure, Slower
    │   ├── scrypt: Memory-hard, CPU-hard
    │   └── PBKDF2: NIST recommended, Configurable iterations
    └── DelegatingPasswordEncoder: Support multiple encoders (migration)
```

### Section 4.1.3 — Authorization
```
├── URL-Based Authorization:
│   ├── .requestMatchers("/api/admin/**").hasRole("ADMIN")
│   ├── .requestMatchers(HttpMethod.DELETE, "/api/**").hasAuthority("WRITE")
│   ├── .requestMatchers("/api/public/**").permitAll()
│   ├── .anyRequest().authenticated()
│   └── Order matters: Most specific FIRST
├── Method-Level Security:
│   ├── @EnableMethodSecurity: Activate method security
│   ├── @PreAuthorize("hasRole('ADMIN')"): Check BEFORE method execution
│   ├── @PostAuthorize("returnObject.owner == authentication.name"): Check AFTER
│   ├── @PreFilter: Filter input collection
│   ├── @PostFilter: Filter output collection
│   ├── SpEL Expressions:
│   │   ├── hasRole('ADMIN'): Role check
│   │   ├── hasAuthority('user:write'): Authority check
│   │   ├── #id == authentication.principal.id: Parameter check
│   │   ├── @permissionService.canAccess(#id): Custom bean method
│   │   └── hasPermission(returnObject, 'READ'): PermissionEvaluator
│   └── @Secured("ROLE_ADMIN"): Simpler (no SpEL), Less flexible
├── Custom Authorization:
│   ├── AuthorizationManager<T>: Custom authorization logic
│   ├── PermissionEvaluator: hasPermission() implementation
│   │   └── Use case: Object-level permissions (ACL)
│   └── Custom AccessDecisionVoter: (deprecated in Spring Security 6)
├── RBAC Implementation:
│   ├── User → Role → Permission mapping
│   ├── Database Schema: users, roles, permissions, user_roles, role_permissions
│   ├── GrantedAuthority: Map permissions to Spring Security authorities
│   └── Hierarchical Roles: RoleHierarchy bean (ADMIN > MANAGER > USER)
└── ACL (Access Control Lists):
    ├── Spring Security ACL module: Per-object permissions
    ├── Database tables: acl_sid, acl_class, acl_object_identity, acl_entry
    ├── Permissions: READ, WRITE, CREATE, DELETE, ADMINISTRATION
    └── Use case: Document management, Fine-grained access control
```

---

## Module 4.2: Advanced Security

### Section 4.2.1 — CORS & CSRF
```
├── CORS (Cross-Origin Resource Sharing):
│   ├── Global Configuration:
│   │   http.cors(cors -> cors.configurationSource(corsConfigurationSource()))
│   ├── CorsConfiguration:
│   │   ├── setAllowedOrigins: Specific origins (NEVER use * in production)
│   │   ├── setAllowedMethods: GET, POST, PUT, DELETE
│   │   ├── setAllowedHeaders: Content-Type, Authorization
│   │   ├── setAllowCredentials: true (for cookies/auth)
│   │   └── setMaxAge: Preflight cache duration
│   ├── @CrossOrigin: Per-controller CORS configuration
│   └── Debug: Browser DevTools Network tab → Preflight OPTIONS request
├── CSRF (Cross-Site Request Forgery):
│   ├── Enabled by default for session-based auth
│   ├── Disable for stateless APIs:
│   │   http.csrf(csrf -> csrf.disable()) // OK for JWT-based APIs
│   ├── CsrfTokenRepository: Cookie or header-based token
│   ├── SPA Integration: CookieCsrfTokenRepository.withHttpOnlyFalse()
│   └── When to keep: Server-rendered forms, Session-based authentication
└── Security Headers:
    ├── http.headers(headers -> headers
    │   .contentSecurityPolicy(csp -> csp.policyDirectives("default-src 'self'"))
    │   .frameOptions(frame -> frame.deny())
    │   .httpStrictTransportSecurity(hsts -> hsts.maxAgeInSeconds(31536000))
    │   )
    ├── X-Content-Type-Options: nosniff (prevent MIME sniffing)
    ├── X-Frame-Options: DENY (prevent clickjacking)
    ├── HSTS: Force HTTPS
    └── CSP: Content Security Policy (XSS prevention)
```

### Section 4.2.2 — OAuth2 & OpenID Connect
```
├── Spring as OAuth2 Resource Server:
│   ├── Validates JWT tokens from external IdP (Keycloak, Auth0, Okta)
│   ├── Configuration:
│   │   spring.security.oauth2.resourceserver.jwt.issuer-uri=https://auth.example.com
│   ├── JwtAuthenticationConverter: Map JWT claims to Spring authorities
│   ├── Custom claim names: roles, groups, permissions → GrantedAuthority
│   ├── Multi-Tenancy: Different issuers for different tenants
│   └── Opaque Tokens: Token introspection instead of JWT
├── Spring as OAuth2 Client:
│   ├── Authorization Code Flow: Browser-based login
│   ├── Client Credentials Flow: Service-to-service authentication
│   ├── OAuth2AuthorizedClientManager: Manage token lifecycle
│   ├── OAuth2AuthorizedClientRepository: Store tokens
│   └── Intercept RestClient/WebClient: Automatically attach access token
├── Spring Authorization Server:
│   ├── Build your own OAuth2 / OIDC provider
│   ├── Supported Grants: Authorization Code (+PKCE), Client Credentials, Refresh Token
│   ├── Token Types: JWT, Opaque
│   ├── OIDC: UserInfo endpoint, ID Token
│   ├── Dynamic Client Registration
│   └── Use case: Enterprise needs, Custom auth requirements
└── Keycloak Integration (Common):
    ├── External IdP: Manage users, Roles, Groups, Clients
    ├── Realm: Tenant isolation in Keycloak
    ├── Client: Your Spring Boot app registered in Keycloak
    ├── Roles: Map Keycloak roles to Spring Security authorities
    └── Admin Console: User management, SSO configuration
```

### Section 4.2.3 — Testing Security
```
├── @WithMockUser: Simulate authenticated user
│   ├── @WithMockUser(username = "admin", roles = {"ADMIN"})
│   ├── Custom: @WithMockUser(authorities = {"user:read", "user:write"})
│   └── Anonymous: @WithAnonymousUser
├── @WithUserDetails: Load real UserDetails from UserDetailsService
├── SecurityMockMvcRequestPostProcessors:
│   ├── .with(user("admin").roles("ADMIN"))
│   ├── .with(jwt().authorities(new SimpleGrantedAuthority("SCOPE_read")))
│   ├── .with(csrf()) — Include CSRF token in test requests
│   └── .with(oauth2Login().attributes(attrs -> attrs.put("name", "John")))
├── @SpringBootTest with Security:
│   ├── TestRestTemplate with HTTP Basic: .withBasicAuth("user", "pass")
│   ├── Inject tokens in headers for JWT testing
│   └── WireMock for mocking external IdP
├── Integration Testing:
│   ├── Test full auth flow: Login → Get token → Access protected resource
│   ├── Test authorization: Verify 403 for unauthorized access
│   ├── Test token expiry: Verify 401 for expired tokens
│   └── Testcontainers + Keycloak: Full OAuth2 integration test
└── Security Scanning:
    ├── OWASP ZAP: Dynamic Application Security Testing
    ├── Dependency Check: owasp-dependency-check-maven
    └── Spring Security Advisories: Follow security bulletins
```

---

> ### 🛠️ PHASE 4 PROJECT: **Secure Document Management System**
> ```
> ┌─────────────────────────────────────────────────────────────────┐
> │            SECURE DOCUMENT MANAGEMENT SYSTEM                    │
> ├─────────────────────────────────────────────────────────────────┤
> │ Features:                                                       │
> │  • User registration with email verification                    │
> │  • Login: Form-based + OAuth2 (Google, GitHub)                  │
> │  • JWT token authentication for API access                      │
> │  • Role hierarchy: VIEWER < EDITOR < ADMIN < SUPER_ADMIN       │
> │  • Document CRUD with per-document access control               │
> │  • Document sharing: Grant read/write to specific users         │
> │  • File upload/download with presigned URLs                     │
> │  • Audit log: Who accessed/modified what, When                  │
> │                                                                 │
> │ Security Requirements:                                          │
> │  ✅ Spring Security 6 with SecurityFilterChain                   │
> │  ✅ JWT: Access (15min) + Refresh (7d) tokens                    │
> │  ✅ Password: BCrypt encoding, Strength validation               │
> │  ✅ OAuth2 Login: Google + GitHub social login                   │
> │  ✅ Method Security: @PreAuthorize on service methods            │
> │  ✅ Object-Level: PermissionEvaluator for document access        │
> │  ✅ CORS: Configured for frontend origin only                    │
> │  ✅ CSRF: Disabled (JWT-based API)                               │
> │  ✅ Security Headers: CSP, HSTS, X-Frame-Options                │
> │  ✅ Rate Limiting: Login endpoint (prevent brute force)          │
> │  ✅ Audit: Spring Security events logged (login, logout, denied) │
> │  ✅ Tests: @WithMockUser, @WithUserDetails, JWT testing           │
> │  ✅ Tests: Full auth flow integration tests                      │
> │  ✅ OWASP: Input validation, SQL injection prevention, XSS      │
> └─────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 📡 PHASE 5: MESSAGING, EVENTS & ASYNC PROCESSING
### 📅 Duration: Months 8–10
### 🎯 Goal: Build event-driven, asynchronous Spring Boot applications
### 👤 Level: Mid-Senior Engineer

---

## Module 5.1: Async Processing

### Section 5.1.1 — @Async & Task Execution
```
├── @EnableAsync: Activate async method execution
├── @Async: Execute method in separate thread
│   ├── Return void: Fire-and-forget
│   ├── Return CompletableFuture<T>: Get result asynchronously
│   └── Custom Executor: @Async("customExecutor") — specify thread pool
├── Thread Pool Configuration:
│   ├── ThreadPoolTaskExecutor @Bean:
│   │   ├── corePoolSize: Threads always alive
│   │   ├── maxPoolSize: Maximum threads under load
│   │   ├── queueCapacity: Queue size before scaling up
│   │   ├── threadNamePrefix: For logging/debugging
│   │   └── rejectedExecutionHandler: CallerRunsPolicy (backpressure)
│   └── Virtual Threads (Java 21+): SimpleAsyncTaskExecutor with virtual threads
├── Exception Handling:
│   ├── AsyncUncaughtExceptionHandler: Handle void @Async exceptions
│   ├── CompletableFuture: .exceptionally() or .handle() for async results
│   └── Logging: Async exceptions are SILENT unless handled!
├── Gotchas:
│   ├── Self-Invocation: @Async on method called from same class → NOT async
│   ├── SecurityContext Propagation: Doesn't propagate by default → DelegatingSecurityContextExecutor
│   ├── MDC Propagation: Logging context lost in async threads → TaskDecorator
│   └── Transaction: @Async methods run in NEW transaction (not parent's)
└── TaskDecorator:
    ├── Copy MDC context to async thread
    ├── Copy SecurityContext to async thread
    └── Implementation: Wrap Runnable with context copying logic
```

### Section 5.1.2 — Scheduling
```
├── @EnableScheduling: Activate scheduled tasks
├── @Scheduled:
│   ├── fixedRate = 5000: Every 5 seconds (from START of previous)
│   ├── fixedDelay = 5000: Every 5 seconds (from END of previous)
│   ├── initialDelay = 10000: Delay before first execution
│   ├── cron = "0 0 * * * *": Cron expression (every hour)
│   └── zone = "America/New_York": Timezone for cron
├── Cron Expressions: second minute hour day month weekday
│   ├── "0 0 6 * * MON-FRI": 6 AM on weekdays
│   ├── "0 */15 * * * *": Every 15 minutes
│   └── "0 0 0 1 * *": First day of every month at midnight
├── Dynamic Scheduling:
│   ├── SchedulingConfigurer: Programmatic task registration
│   ├── Trigger: Custom next execution time logic
│   └── TaskScheduler: Schedule tasks at runtime
├── Distributed Scheduling:
│   ├── Problem: Multiple instances → Task runs multiple times!
│   ├── ShedLock: Distributed lock for scheduled tasks
│   │   ├── @SchedulerLock(name = "taskName", lockAtLeastFor = "5m")
│   │   ├── Lock Providers: JDBC, MongoDB, Redis, Hazelcast
│   │   └── How: Creates lock record in DB, Other instances skip
│   ├── Quartz Scheduler: Enterprise job scheduling with clustering
│   │   ├── Job + Trigger model
│   │   ├── JDBC JobStore: Persistent, Clustered
│   │   ├── Misfire handling: What to do when a trigger is missed
│   │   └── spring-boot-starter-quartz: Auto-configuration
│   └── Temporal: Workflow-based scheduling (advanced)
└── Best Practices:
    ├── Keep scheduled tasks SHORT (or make them async)
    ├── Handle failures: Retry, Alert, Log
    ├── Idempotent: Safe to run multiple times
    └── Monitoring: Track execution time, Success/failure metrics
```

---

## Module 5.2: Apache Kafka with Spring

### Section 5.2.1 — Spring Kafka Fundamentals
```
├── Dependencies: spring-boot-starter (spring-kafka auto-configured)
├── Configuration:
│   ├── spring.kafka.bootstrap-servers=localhost:9092
│   ├── spring.kafka.consumer.group-id=my-group
│   ├── spring.kafka.consumer.auto-offset-reset=earliest
│   ├── spring.kafka.producer.key-serializer=StringSerializer
│   └── spring.kafka.producer.value-serializer=JsonSerializer
├── KafkaTemplate (Producer):
│   ├── kafkaTemplate.send("topic", key, value): Send message
│   ├── kafkaTemplate.send(ProducerRecord): Full control
│   ├── CompletableFuture<SendResult>: Async result
│   ├── sendDefault(): Use default topic
│   ├── ProducerListener: Global success/error callbacks
│   └── Transactional Producer: spring.kafka.producer.transaction-id-prefix
├── @KafkaListener (Consumer):
│   ├── @KafkaListener(topics = "orders", groupId = "order-processor")
│   ├── Method Parameters:
│   │   ├── @Payload Order order: Deserialized message
│   │   ├── @Header(KafkaHeaders.RECEIVED_KEY) String key
│   │   ├── @Header(KafkaHeaders.RECEIVED_TOPIC) String topic
│   │   ├── @Header(KafkaHeaders.RECEIVED_PARTITION) int partition
│   │   ├── @Header(KafkaHeaders.OFFSET) long offset
│   │   └── Acknowledgment ack: Manual acknowledgment
│   ├── Batch Consumption: @KafkaListener + List<ConsumerRecord<K,V>>
│   ├── Concurrency: @KafkaListener(concurrency = "3") — parallel consumers
│   └── Container Factory: ConcurrentKafkaListenerContainerFactory (customization)
├── Serialization/Deserialization:
│   ├── StringSerializer/Deserializer: Plain text
│   ├── JsonSerializer/Deserializer: Jackson-based JSON
│   ├── Avro + Schema Registry: Schema evolution, Confluent integration
│   │   └── spring.kafka.properties.schema.registry.url=http://localhost:8081
│   ├── Protobuf: Binary, Schema-defined
│   └── Custom: Implement Serializer<T> / Deserializer<T>
└── Topics & Partitions:
    ├── NewTopic @Bean: Create topics on startup
    ├── Partitions: Parallelism unit, Message ordering per partition
    ├── Key: Messages with same key → same partition → ordered
    └── AdminClient: Programmatic topic management
```

### Section 5.2.2 — Advanced Kafka Patterns
```
├── Error Handling:
│   ├── DefaultErrorHandler: Default (Spring Kafka 2.8+)
│   │   ├── Retry: BackOff (fixed, exponential)
│   │   ├── Recovery: DeadLetterPublishingRecoverer (DLT)
│   │   ├── Retryable Exceptions: Configure which exceptions are retryable
│   │   └── Non-Retryable: DeserializationException, etc. → DLT immediately
│   ├── Dead Letter Topic (DLT): {original-topic}.DLT
│   │   ├── Headers: Original topic, Partition, Offset, Exception
│   │   └── DLT Consumer: Process/monitor failed messages
│   ├── @RetryableTopic: Annotation-based retry topic
│   │   ├── Retry Topics: {topic}-retry-0, {topic}-retry-1, ..., {topic}-dlt
│   │   ├── Configurable: Attempts, Backoff, DLT strategy
│   │   └── Benefit: Non-blocking retry (messages don't block partition)
│   └── Custom ErrorHandler: Implement ConsumerRecordRecoverer
├── Exactly-Once Semantics:
│   ├── Idempotent Producer: enable.idempotence=true (default in Kafka 3.0+)
│   ├── Transactional Producer: Atomic produce across partitions
│   ├── Read-Process-Write Pattern: Consume → Process → Produce atomically
│   └── spring.kafka.producer.transaction-id-prefix=tx-
├── Consumer Offset Management:
│   ├── Auto Commit (default): spring.kafka.consumer.enable-auto-commit=true
│   ├── Manual Commit: Acknowledgment.acknowledge() (recommended for reliability)
│   ├── AckMode:
│   │   ├── RECORD: Ack after each record
│   │   ├── BATCH: Ack after batch (default manual)
│   │   ├── MANUAL: Developer calls ack
│   │   └── MANUAL_IMMEDIATE: Ack immediately (no batching)
│   └── Seek: ConsumerSeekAware — Rewind to specific offset
├── Kafka Streams with Spring:
│   ├── spring-kafka + kafka-streams dependency
│   ├── @EnableKafkaStreams: Activate Kafka Streams
│   ├── StreamsBuilder @Bean: Define stream topology
│   ├── KStream, KTable, GlobalKTable: Stream/Table duality
│   ├── Operations: filter, map, flatMap, groupBy, aggregate, join, windowed
│   ├── State Stores: Local state (RocksDB), Queryable
│   └── Use case: Real-time aggregation, Enrichment, Filtering
└── Testing Kafka:
    ├── @EmbeddedKafka: In-memory Kafka broker for tests
    ├── EmbeddedKafkaBroker: Configure topics, Partitions
    ├── Testcontainers Kafka: More realistic (real Kafka in Docker)
    ├── KafkaTemplate + @KafkaListener: Test full produce-consume cycle
    └── Assertions: ConsumerRecords, Poll with timeout, Verify message content
```

---

## Module 5.3: RabbitMQ with Spring

### Section 5.3.1 — Spring AMQP
```
├── Dependencies: spring-boot-starter-amqp
├── Configuration:
│   ├── spring.rabbitmq.host=localhost
│   ├── spring.rabbitmq.port=5672
│   ├── spring.rabbitmq.username / password
│   └── ConnectionFactory: Auto-configured
├── RabbitTemplate (Producer):
│   ├── rabbitTemplate.convertAndSend(exchange, routingKey, message)
│   ├── Message Converter: Jackson2JsonMessageConverter @Bean
│   ├── Confirm Mode: Publisher confirms (message reached broker)
│   └── Return Callback: Message couldn't be routed to queue
├── @RabbitListener (Consumer):
│   ├── @RabbitListener(queues = "order.created")
│   ├── @RabbitHandler: Method-level handler (per message type)
│   ├── @Payload, @Header: Access message parts
│   ├── Acknowledgment: AUTO (default), MANUAL, NONE
│   └── Concurrency: @RabbitListener(concurrency = "3-10")
├── Exchange Types:
│   ├── Direct: Route by exact routing key match
│   ├── Topic: Route by pattern (order.* or order.#)
│   ├── Fanout: Broadcast to all bound queues
│   ├── Headers: Route by header attributes
│   └── Dead Letter Exchange (DLX): Route failed messages
├── Topology Declaration:
│   ├── Queue @Bean: Durable, Auto-delete, Exclusive
│   ├── Exchange @Bean: DirectExchange, TopicExchange, FanoutExchange
│   ├── Binding @Bean: BindingBuilder.bind(queue).to(exchange).with(routingKey)
│   └── @QueueBinding: Declare all in @RabbitListener annotation
├── Error Handling:
│   ├── Retry: RetryInterceptor with ExponentialBackOff
│   ├── DLQ: Dead letter queue for unprocessable messages
│   ├── Republish: RepublishMessageRecoverer to DLQ with exception details
│   └── Manual Nack: channel.basicNack(deliveryTag, false, true) — Requeue
├── Advanced Patterns:
│   ├── Request-Reply: RabbitTemplate.convertSendAndReceive() — RPC pattern
│   ├── Priority Queue: x-max-priority argument
│   ├── TTL: Message TTL, Queue TTL
│   ├── Delayed Message: rabbitmq_delayed_message_exchange plugin
│   └── Quorum Queues: Replicated, Raft-based (high availability)
└── Testing: @SpringBootTest + Testcontainers RabbitMQ
```

---

## Module 5.4: Spring Cloud Stream

### Section 5.4.1 — Binder Abstraction
```
├── Concept: Abstraction over messaging middleware
├── Binders: Kafka, RabbitMQ, AWS Kinesis, Azure Event Hubs, Google Pub/Sub
├── Programming Model:
│   ├── Functional Style (preferred):
│   │   ├── Supplier<T>: Source (produces messages)
│   │   ├── Consumer<T>: Sink (consumes messages)
│   │   └── Function<T, R>: Processor (transforms messages)
│   ├── @Bean:
│   │   ├── Consumer<Message<Order>> processOrder() — Auto-bound to input channel
│   │   ├── Supplier<Order> generateOrder() — Auto-bound to output channel
│   │   └── Function<Order, Invoice> createInvoice() — Input → Output
│   └── Configuration: spring.cloud.stream.bindings.*
├── Configuration:
│   ├── Destinations: spring.cloud.stream.bindings.processOrder-in-0.destination=orders
│   ├── Consumer Groups: spring.cloud.stream.bindings.processOrder-in-0.group=order-service
│   ├── Content Type: spring.cloud.stream.bindings.*.content-type=application/json
│   ├── Partitioning: spring.cloud.stream.bindings.*.producer.partitionKeyExpression
│   └── Error Handling: DLQ, Retry, Error channel
├── Benefits:
│   ├── Swap Kafka for RabbitMQ without code changes (change binder)
│   ├── Testing: TestChannelBinder for unit tests (no real broker)
│   └── Standardized error handling across brokers
└── When to use: Multi-broker support needed, Want abstraction over messaging
    When NOT to use: Need broker-specific features, Already committed to one broker
```

---

## Module 5.5: WebSocket & Server-Sent Events

### Section 5.5.1 — WebSocket with STOMP
```
├── Dependencies: spring-boot-starter-websocket
├── Configuration:
│   ├── @EnableWebSocketMessageBroker
│   ├── configureMessageBroker: /topic, /queue prefixes
│   ├── registerStompEndpoints: /ws endpoint (SockJS fallback)
│   └── Message Broker: Simple (in-memory) or RabbitMQ/ActiveMQ (clustered)
├── @MessageMapping: Handle WebSocket messages (like @RequestMapping for WS)
├── @SendTo: Send response to topic
├── SimpMessagingTemplate: Send messages programmatically
│   ├── convertAndSend("/topic/notifications", message): Broadcast
│   └── convertAndSendToUser(userId, "/queue/private", message): User-specific
├── Security: WebSocket security configuration, AuthenticationPrincipal
├── Scaling: External broker (RabbitMQ STOMP plugin) for multi-instance
└── Testing: WebSocketStompClient for integration tests
```

### Section 5.5.2 — Server-Sent Events (SSE)
```
├── SseEmitter: Server → Client one-way streaming
├── Controller: Return SseEmitter, Send events asynchronously
├── Timeout: sseEmitter.timeout(TimeUnit.MINUTES.toMillis(30))
├── Error Handling: onCompletion, onTimeout, onError callbacks
├── Use case: Real-time notifications, Live feeds, Progress updates
└── vs WebSocket: SSE is simpler (one-way), No client → server
```

---

> ### 🛠️ PHASE 5 PROJECT: **Real-Time E-Commerce Event System**
> ```
> ┌─────────────────────────────────────────────────────────────────┐
> │           REAL-TIME E-COMMERCE EVENT SYSTEM                     │
> ├─────────────────────────────────────────────────────────────────┤
> │                                                                 │
> │  ┌───────────┐     ┌──────────┐     ┌───────────────┐         │
> │  │  Order    │────→│  Kafka   │────→│ Inventory     │         │
> │  │  Service  │     │          │────→│ Service       │         │
> │  └───────────┘     │          │────→│               │         │
> │                    │          │     └───────────────┘         │
> │  ┌───────────┐     │          │     ┌───────────────┐         │
> │  │  Price    │────→│          │────→│ Notification  │         │
> │  │  Updater  │     │          │     │ Service       │         │
> │  │(@Scheduled)│     │          │     │(Email + SSE)  │         │
> │  └───────────┘     └──────────┘     └───────────────┘         │
> │                                                                 │
> │ Features:                                                       │
> │  • Order Service: Create orders → Publish OrderCreated event   │
> │  • Inventory Service: Consume OrderCreated → Reserve stock     │
> │  • Notification Service: Send email + Real-time SSE to user    │
> │  • Price Updater: @Scheduled job with ShedLock (distributed)   │
> │  • Live Dashboard: WebSocket (STOMP) for admin order feed      │
> │  • Async: @Async for email sending, Image processing           │
> │                                                                 │
> │ Technical Requirements:                                         │
> │  ✅ Spring Kafka: Producer/Consumer with JSON serialization      │
> │  ✅ Error Handling: @RetryableTopic with DLT                     │
> │  ✅ Manual Offset: AckMode.MANUAL for critical consumers        │
> │  ✅ @Async: Custom ThreadPoolTaskExecutor with TaskDecorator     │
> │  ✅ @Scheduled + ShedLock: Distributed scheduled tasks          │
> │  ✅ WebSocket (STOMP): Live admin dashboard                     │
> │  ✅ SSE: Real-time order status updates to customers            │
> │  ✅ Idempotent Consumers: Handle duplicate messages gracefully   │
> │  ✅ @EmbeddedKafka + Testcontainers: Full integration tests    │
> │  ✅ Observability: Correlation ID propagation across Kafka       │
> │  ✅ Dead Letter Topic: Monitor and reprocess failed messages    │
> └─────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# ☁️ PHASE 6: SPRING CLOUD & MICROSERVICES
### 📅 Duration: Months 10–13
### 🎯 Goal: Build and operate distributed microservices with Spring Cloud
### 👤 Level: Senior Engineer

---

## Module 6.1: Service Discovery & Configuration

### Section 6.1.1 — Spring Cloud Config Server
```
├── Centralized Configuration: All services read config from one place
├── Backend: Git repo, File system, Vault, JDBC, AWS S3
├── @EnableConfigServer: Create config server
├── Client: spring.config.import=configserver:http://config-server:8888
├── Profiles: application-dev.yml, application-prod.yml per service
├── Encryption: Encrypt sensitive values ({cipher}...)
├── Refresh: @RefreshScope + /actuator/refresh → Hot reload config
├── Bus Refresh: Spring Cloud Bus (Kafka/RabbitMQ) → Broadcast config changes
└── Alternative: Kubernetes ConfigMaps + Secrets (no separate config server needed)
```

### Section 6.1.2 — Service Discovery
```
├── Netflix Eureka:
│   ├── @EnableEurekaServer: Discovery server
│   ├── @EnableDiscoveryClient: Register service
│   ├── Client-Side Load Balancing: Spring Cloud LoadBalancer
│   ├── Self-Preservation: Prevent mass de-registration
│   └── Instance Info: Hostname, Port, Health status, Metadata
├── Consul: Service discovery + KV store + Health checking
├── Kubernetes Service Discovery: Native, No additional component needed
│   ├── spring-cloud-starter-kubernetes-client-all
│   ├── Service name → Kubernetes Service DNS resolution
│   └── Preferred: When running on Kubernetes (no Eureka needed)
└── Client-Side Load Balancing:
    ├── Spring Cloud LoadBalancer: Replaces Netflix Ribbon
    ├── @LoadBalanced RestTemplate/WebClient: Auto-resolve service names
    ├── Algorithms: RoundRobin (default), Random, Custom
    └── Service Instance List Supplier: From Eureka, Consul, K8s, or static
```

---

## Module 6.2: Resilience & Circuit Breaking

### Section 6.2.1 — Resilience4j with Spring Boot
```
├── Dependencies: spring-cloud-starter-circuitbreaker-resilience4j
├── Circuit Breaker:
│   ├── @CircuitBreaker(name = "paymentService", fallbackMethod = "fallback")
│   ├── Configuration (application.yml):
│   │   ├── slidingWindowSize: 10
│   │   ├── failureRateThreshold: 50 (%)
│   │   ├── waitDurationInOpenState: 30s
│   │   ├── permittedNumberOfCallsInHalfOpenState: 3
│   │   └── recordExceptions: [HttpServerErrorException, ConnectException]
│   ├── States: CLOSED → OPEN → HALF_OPEN → CLOSED
│   └── Fallback: Method with same signature + Exception parameter
├── Retry:
│   ├── @Retry(name = "paymentService", fallbackMethod = "fallback")
│   ├── Configuration:
│   │   ├── maxAttempts: 3
│   │   ├── waitDuration: 500ms
│   │   ├── enableExponentialBackoff: true
│   │   ├── exponentialBackoffMultiplier: 2
│   │   └── retryExceptions: [ConnectException, TimeoutException]
│   └── Retry + Circuit Breaker: Retry INSIDE Circuit Breaker
├── Rate Limiter:
│   ├── @RateLimiter(name = "api", fallbackMethod = "rateLimitFallback")
│   ├── Configuration:
│   │   ├── limitForPeriod: 10
│   │   ├── limitRefreshPeriod: 1s
│   │   └── timeoutDuration: 0 (fail immediately when limited)
│   └── Use case: Protect APIs from abuse
├── Bulkhead:
│   ├── @Bulkhead(name = "paymentService")
│   ├── Types:
│   │   ├── Semaphore: Limit concurrent calls
│   │   └── ThreadPool: Separate thread pool per service
│   └── Configuration: maxConcurrentCalls, maxWaitDuration
├── Time Limiter:
│   ├── @TimeLimiter(name = "paymentService")
│   ├── timeoutDuration: 3s
│   └── Requires CompletableFuture return type
├── Combining Annotations:
│   ├── Order: Retry(CircuitBreaker(RateLimiter(TimeLimiter(Bulkhead(method)))))
│   └── Configurable via resilience4j.circuitbreaker.circuitBreakerAspectOrder
├── Monitoring:
│   ├── Actuator Integration: /actuator/circuitbreakers, /actuator/retries
│   ├── Micrometer Metrics: Circuit breaker state, Call rate, Failure rate
│   └── Grafana Dashboard: Resilience4j dashboard template
└── Spring Cloud Circuit Breaker: Abstraction (can swap Resilience4j for other libs)
```

---

## Module 6.3: API Gateway

### Section 6.3.1 — Spring Cloud Gateway
```
├── Reactive Gateway: Built on Spring WebFlux + Project Reactor
├── Core Concepts:
│   ├── Route: ID + URI + Predicates + Filters
│   ├── Predicate: When to route (Path, Method, Header, Cookie, Time)
│   ├── Filter: Modify request/response (before/after routing)
│   └── Configuration: YAML or Java DSL
├── YAML Configuration:
│   spring:
│     cloud:
│       gateway:
│         routes:
│           - id: user-service
│             uri: lb://user-service  # Load balanced
│             predicates:
│               - Path=/api/users/**
│               - Method=GET,POST
│             filters:
│               - StripPrefix=1
│               - AddRequestHeader=X-Request-Source, gateway
├── Built-in Predicates:
│   ├── Path, Method, Header, Cookie, Query, Host
│   ├── After/Before/Between: Time-based routing
│   ├── Weight: Traffic splitting (canary)
│   └── RemoteAddr: IP-based routing
├── Built-in Filters:
│   ├── AddRequestHeader / AddResponseHeader
│   ├── StripPrefix: Remove path prefix before forwarding
│   ├── RewritePath: Regex-based path rewriting
│   ├── RequestRateLimiter: Redis-based rate limiting
│   ├── CircuitBreaker: Integrate Resilience4j
│   ├── Retry: Configurable retry filter
│   └── ModifyResponseBody: Transform response
├── Custom Filters:
│   ├── GatewayFilter: Per-route filter
│   ├── GlobalFilter: Applied to ALL routes
│   └── Use cases: Authentication, Logging, Request/Response transformation
├── Rate Limiting:
│   ├── RequestRateLimiterGatewayFilterFactory
│   ├── RedisRateLimiter: Token bucket algorithm
│   ├── KeyResolver: Rate limit by user, IP, API key
│   └── Configuration: replenishRate, burstCapacity, requestedTokens
├── Security:
│   ├── TokenRelay: Forward OAuth2 token to downstream services
│   ├── JWT Validation: Validate at gateway, Forward claims as headers
│   └── CORS: Gateway-level CORS configuration
└── vs NGINX / Kong: Spring Cloud Gateway is code-first, Integrated with Spring ecosystem
```

---

## Module 6.4: Distributed Tracing & Observability

### Section 6.4.1 — Micrometer & Spring Boot Actuator
```
├── Spring Boot Actuator:
│   ├── Health: /actuator/health — Liveness + Readiness
│   │   ├── Custom HealthIndicator: Check external dependencies
│   │   ├── Health Groups: Liveness probe (k8s), Readiness probe (k8s)
│   │   └── Detailed: management.endpoint.health.show-details=always
│   ├── Metrics: /actuator/metrics — Micrometer metrics
│   ├── Info: /actuator/info — Build info, Git info
│   ├── Env: /actuator/env — Configuration properties
│   ├── Loggers: /actuator/loggers — Change log levels at runtime!
│   ├── HTTP Exchanges: /actuator/httpexchanges — Recent HTTP requests
│   ├── Beans: /actuator/beans — All registered beans
│   ├── Mappings: /actuator/mappings — All request mappings
│   ├── Flyway: /actuator/flyway — Migration history
│   └── Security: Secure actuator endpoints! (management.endpoints.web.exposure.include)
├── Micrometer (Metrics):
│   ├── Facade: Like SLF4J but for metrics (vendor-neutral)
│   ├── Meter Types:
│   │   ├── Counter: Monotonically increasing (total requests, errors)
│   │   ├── Gauge: Current value (queue size, active threads)
│   │   ├── Timer: Duration + count (request latency)
│   │   ├── DistributionSummary: Distribution of values (response sizes)
│   │   └── LongTaskTimer: Track in-progress long tasks
│   ├── Auto-Instrumented:
│   │   ├── JVM: Memory, GC, Threads, Classes
│   │   ├── HTTP: Server requests (method, status, uri, exception)
│   │   ├── Database: HikariCP pool metrics, JPA query timing
│   │   ├── Cache: Hit/miss ratio, Size
│   │   ├── Kafka: Consumer lag, Producer send rate
│   │   └── Tomcat: Threads, Sessions, Request processing time
│   ├── Custom Metrics:
│   │   ├── @Counted: Count method invocations
│   │   ├── @Timed: Time method execution
│   │   ├── MeterRegistry: Programmatic metric creation
│   │   └── Custom tags: Environment, Service, Instance
│   ├── Export to:
│   │   ├── Prometheus: micrometer-registry-prometheus
│   │   ├── Datadog: micrometer-registry-datadog
│   │   ├── CloudWatch: micrometer-registry-cloudwatch2
│   │   ├── InfluxDB: micrometer-registry-influx
│   │   └── OTLP: micrometer-registry-otlp (OpenTelemetry)
│   └── Prometheus Integration:
│       ├── /actuator/prometheus: Scrape endpoint
│       ├── Prometheus scrape config: Target Spring Boot app
│       └── Grafana: Import Spring Boot dashboard (ID: 4701, 11378)
└── Spring Boot 3 Observability:
    ├── Micrometer Observation API: Unified API for metrics + traces
    ├── @Observed: Instrument methods with metrics AND traces
    ├── ObservationHandler: Custom observation processing
    └── Convention: Auto-naming based on method/class
```

### Section 6.4.2 — Distributed Tracing (Micrometer Tracing)
```
├── Micrometer Tracing (replaces Spring Cloud Sleuth):
│   ├── Trace ID: Unique ID for entire request chain
│   ├── Span ID: Unique ID for each service hop
│   ├── Parent Span: Linking spans into a tree
│   ├── Auto-Propagation: HTTP headers, Kafka headers, RabbitMQ headers
│   └── MDC Integration: TraceId + SpanId in every log line
├── Bridges:
│   ├── micrometer-tracing-bridge-brave: Zipkin Brave tracer
│   └── micrometer-tracing-bridge-otel: OpenTelemetry tracer (recommended)
├── Exporters:
│   ├── Zipkin: zipkin-reporter-brave
│   ├── Jaeger: OpenTelemetry exporter
│   ├── Tempo (Grafana): OTLP exporter
│   └── AWS X-Ray: OTLP exporter with X-Ray compatible IDs
├── Configuration:
│   ├── management.tracing.sampling.probability=1.0 (100% in dev, lower in prod)
│   ├── management.zipkin.tracing.endpoint=http://zipkin:9411/api/v2/spans
│   └── logging.pattern.correlation: Include traceId in log pattern
├── Baggage: Key-value pairs propagated across services
│   ├── management.tracing.baggage.remote-fields=userId,tenantId
│   ├── management.tracing.baggage.correlation.fields=userId
│   └── Use case: Propagate tenant ID, User ID across services
└── Auto-Instrumented:
    ├── Spring MVC / WebFlux: Incoming HTTP requests
    ├── RestClient / WebClient / RestTemplate: Outgoing HTTP calls
    ├── Spring Kafka / RabbitMQ: Message production and consumption
    ├── Spring Data: Database queries
    ├── @Scheduled: Scheduled task spans
    └── @Async: Async method spans
```

---

## Module 6.5: Distributed Transactions & Sagas

### Section 6.5.1 — Saga Pattern Implementation
```
├── Orchestration-Based:
│   ├── Spring State Machine: Define saga states + transitions
│   ├── Temporal (recommended for complex workflows):
│   │   ├── Workflow: @WorkflowMethod — Define saga steps
│   │   ├── Activities: @ActivityMethod — Each saga step
│   │   ├── Compensation: Automatic rollback on failure
│   │   ├── Retry: Built-in retry with backoff per activity
│   │   └── Visibility: Track saga execution state
│   └── Axon Framework: CQRS + Event Sourcing + Saga support
├── Choreography-Based:
│   ├── Each service publishes events → Next service reacts
│   ├── Spring Kafka / RabbitMQ for event distribution
│   ├── Compensating Events: OrderCancelled triggers InventoryReleased
│   └── Tracking: Correlation ID to trace full saga
├── Outbox Pattern (Spring Implementation):
│   ├── Save event in outbox table within same DB transaction as entity
│   ├── Scheduled job / Debezium: Publish outbox events to Kafka
│   ├── Avoids Dual-Write Problem: DB + Kafka write is NOT atomic
│   └── Libraries: Spring Modulith Events, Custom implementation
└── Spring Modulith:
    ├── @ApplicationModuleListener: Module event listener
    ├── Event Publication Registry: Track unpublished events
    ├── Event Externalization: Automatically publish to Kafka/RabbitMQ
    └── Use case: Modular monolith with reliable event processing
```

---

## Module 6.6: Additional Spring Cloud Components

### Section 6.6.1 — Other Cloud Components
```
├── Spring Cloud OpenFeign:
│   ├── Declarative REST client: @FeignClient
│   ├── Load balanced: @FeignClient(name = "user-service")
│   ├── Integration: Resilience4j, OAuth2, Micrometer
│   └── Error Decoder: Custom error handling
├── Spring Cloud Kubernetes:
│   ├── Config: Load from Kubernetes ConfigMaps/Secrets
│   ├── Discovery: Kubernetes Service as service discovery
│   ├── Leader Election: HA leader selection
│   └── Reload: Watch ConfigMap changes, Auto-reload
├── Spring Cloud Stream: (Covered in Phase 5)
├── Spring Cloud Function:
│   ├── Write business logic as Java functions
│   ├── Deploy anywhere: AWS Lambda, Azure Functions, GCP Functions, Knative
│   ├── Same code, Multiple platforms
│   └── Integration with Spring Cloud Stream
└── Spring Cloud Contract:
    ├── Contract-First: Define contracts in Groovy DSL or YAML
    ├── Auto-Generate: Tests for provider + Stubs for consumer
    ├── WireMock Stubs: Use in consumer tests
    └── Pact Compatibility: Export to Pact format
```

---

> ### 🛠️ PHASE 6 PROJECT: **Ride-Sharing Microservices Platform**
> ```
> ┌────────────────────────────────────────────────────────────────────┐
> │            RIDE-SHARING MICROSERVICES PLATFORM                     │
> ├────────────────────────────────────────────────────────────────────┤
> │                                                                    │
> │              ┌──────────────────┐                                   │
> │              │  Spring Cloud    │                                   │
> │   Client ──→ │  Gateway         │                                   │
> │              │  (Rate Limit,    │                                   │
> │              │   Auth, Routes)  │                                   │
> │              └────────┬─────────┘                                   │
> │         ┌─────────────┼─────────────┬──────────────┐               │
> │   ┌─────┴─────┐ ┌─────┴─────┐ ┌────┴────┐ ┌──────┴──────┐       │
> │   │   User    │ │   Ride    │ │ Driver  │ │  Payment    │       │
> │   │  Service  │ │  Service  │ │ Service │ │  Service    │       │
> │   │          │ │          │ │         │ │(Circuit Brkr)│       │
> │   └─────┬─────┘ └─────┬─────┘ └────┬────┘ └──────┬──────┘       │
> │         └─────────────┼─────────────┼──────────────┘               │
> │                  ┌────┴────┐   ┌────┴────┐                         │
> │                  │  Kafka  │   │  Redis  │                         │
> │                  └─────────┘   └─────────┘                         │
> │                  ┌─────────┐   ┌─────────────┐                     │
> │                  │  Tempo  │   │ Prometheus  │                     │
> │                  │(Tracing)│   │ + Grafana   │                     │
> │                  └─────────┘   └─────────────┘                     │
> │                                                                    │
> │ Services:                                                          │
> │  • User Service: Registration, Authentication (JWT)                │
> │  • Ride Service: Request ride, Track status, History               │
> │  • Driver Service: Availability, Location updates, Matching        │
> │  • Payment Service: Process payments, Wallet management            │
> │  • Notification Service: Email/Push via Kafka consumers            │
> │                                                                    │
> │ Spring Cloud Requirements:                                         │
> │  ✅ Spring Cloud Gateway: Routing, Rate limiting, JWT validation    │
> │  ✅ Service Discovery: Eureka OR Kubernetes-native                  │
> │  ✅ Spring Cloud Config: Centralized configuration (Git backend)    │
> │  ✅ Resilience4j: Circuit breaker on Payment Service calls          │
> │  ✅ Resilience4j: Retry + Bulkhead on Driver Service calls          │
> │  ✅ OpenFeign: Declarative inter-service communication              │
> │  ✅ Saga: Ride booking saga (orchestration with Temporal)           │
> │  ✅ Kafka: Async events (RideRequested, DriverAssigned, etc.)       │
> │  ✅ Micrometer + Prometheus: Custom business metrics                │
> │  ✅ Micrometer Tracing → Tempo: Distributed traces across services │
> │  ✅ Spring Boot Actuator: Health, Metrics, Loggers endpoints        │
> │  ✅ Grafana Dashboards: Per-service RED metrics + Business KPIs     │
> │  ✅ Spring Cloud Contract: Consumer-driven contract tests           │
> │  ✅ Docker Compose: Full local development environment              │
> │  ✅ Kubernetes: Helm charts for all services                        │
> └────────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 🤖 PHASE 7: SPRING AI & EMERGING ECOSYSTEM
### 📅 Duration: Months 13–15
### 🎯 Goal: Master cutting-edge Spring Boot features and ecosystem
### 👤 Level: Advanced Specialist

---

## Module 7.1: Spring AI

### Section 7.1.1 — AI Integration
```
├── Spring AI Framework:
│   ├── Portable AI API: Same code for OpenAI, Anthropic, Ollama, Vertex AI, Azure OpenAI
│   ├── ChatClient: High-level chat API
│   │   ├── chatClient.prompt("Summarize this document: " + text).call().content()
│   │   ├── System Prompts: Set system-level instructions
│   │   ├── Advisors: Logging, Memory, RAG advisors
│   │   └── Streaming: .stream() for token-by-token responses
│   ├── Embedding Model: Generate vector embeddings
│   │   ├── embeddingModel.embed("search query") → float[]
│   │   └── Batch: embeddingModel.embed(List<String>)
│   ├── Image Model: Generate/edit images
│   │   └── imageModel.call(new ImagePrompt("..."))
│   └── Audio Model: Speech-to-text, Text-to-speech
├── RAG (Retrieval-Augmented Generation):
│   ├── Document Loading: PDF, Text, HTML, Markdown readers
│   ├── Text Splitting: Chunking strategies (TokenTextSplitter)
│   ├── Embedding: Convert chunks to vectors
│   ├── Vector Store: Store embeddings
│   │   ├── PGVector (PostgreSQL): pgvector extension
│   │   ├── Redis: Redis Vector Similarity Search
│   │   ├── Chroma, Pinecone, Weaviate, Qdrant, Milvus
│   │   └── SimpleVectorStore: In-memory (dev/testing)
│   ├── Retrieval: Search similar documents by query embedding
│   ├── QuestionAnswerAdvisor: Auto-RAG pipeline
│   └── Pipeline: Load → Split → Embed → Store → Query → Generate
├── Function Calling (Tool Use):
│   ├── Define Java methods as tools
│   ├── @Description: Describe function for AI model
│   ├── AI model decides when to call your functions
│   └── Use case: Database queries, API calls, Calculations
├── Structured Output:
│   ├── chatClient.prompt("...").call().entity(MyRecord.class)
│   ├── BeanOutputConverter: Map AI response to Java objects
│   ├── ListOutputConverter: Extract lists
│   └── MapOutputConverter: Extract key-value pairs
├── Memory / Conversation:
│   ├── ChatMemory: Store conversation history
│   ├── MessageChatMemoryAdvisor: Auto-add history to prompts
│   ├── Implementations: InMemory, JDBC, Redis, Cassandra
│   └── Window: Last N messages, Token-limited
└── Evaluation:
    ├── RelevancyEvaluator: Is the answer relevant to the query?
    ├── FactualityEvaluator: Is the answer factually correct given context?
    └── Custom Evaluators: Define your own quality metrics
```

---

## Module 7.2: Spring Boot Native (GraalVM)

### Section 7.2.1 — GraalVM Native Image
```
├── What: Compile Spring Boot app to native executable (AOT compilation)
├── Benefits:
│   ├── Startup: ~50ms (vs ~2-5 seconds for JVM)
│   ├── Memory: 50-80% less memory
│   ├── Peak Performance: Slightly lower (no JIT optimization)
│   └── Container Size: Smaller Docker images
├── Build:
│   ├── Maven: mvn -Pnative spring-boot:build-image (Buildpacks)
│   ├── Maven: mvn -Pnative native:compile (GraalVM installed)
│   ├── Gradle: gradle nativeCompile
│   └── Build Time: 2-10 minutes (much longer than JVM compilation)
├── AOT Processing:
│   ├── Spring AOT: Generates optimized code at build time
│   ├── Bean Definitions: Pre-computed at build time (not runtime)
│   ├── @Conditional: Evaluated at build time
│   └── RuntimeHints: Register reflection, Resources, Proxies, Serialization
├── Limitations:
│   ├── Reflection: Must be declared explicitly (RuntimeHintsRegistrar)
│   ├── Dynamic Proxies: Must be declared
│   ├── Serialization: Classes must be registered
│   ├── Classpath: Fixed at build time (no dynamic class loading)
│   └── Some Libraries: Not compatible (check compatibility list)
├── Testing:
│   ├── @SpringBootTest nativeTest: Run tests in native mode
│   └── CI: GraalVM GitHub Actions, Native test support
├── When to use:
│   ├── Serverless (AWS Lambda): Cold start reduction is game-changing
│   ├── CLI Tools: Instant startup
│   ├── Kubernetes: Faster pod startup, Lower resource requests
│   └── Edge Computing: Minimal footprint
└── When NOT to use:
    ├── Heavy computation: JIT optimization matters
    ├── Heavy use of reflection-based libraries
    └── Rapid development: Long build times slow iteration
```

---

## Module 7.3: Spring WebFlux (Reactive)

### Section 7.3.1 — Reactive Programming with Spring
```
├── Project Reactor:
│   ├── Mono<T>: 0 or 1 element (single result)
│   ├── Flux<T>: 0 to N elements (stream/collection)
│   ├── Operators: map, flatMap, filter, zip, merge, concat, switchIfEmpty
│   ├── Error Handling: onErrorReturn, onErrorResume, retry
│   ├── Backpressure: Built-in, Request-based
│   └── Schedulers: boundedElastic (blocking I/O), parallel (computation)
├── Spring WebFlux:
│   ├── Annotation Model: Same as Spring MVC (@RestController, @GetMapping)
│   ├── Return: Mono<ResponseEntity<T>>, Flux<T>
│   ├── Functional Endpoints: RouterFunction + HandlerFunction
│   ├── Server: Netty (default), Undertow, Jetty
│   └── Non-Blocking I/O: Event loop model (few threads, many connections)
├── Reactive Data Access:
│   ├── R2DBC: Reactive relational database connectivity
│   │   ├── Spring Data R2DBC: ReactiveCrudRepository
│   │   ├── Supported: PostgreSQL, MySQL, H2, SQL Server, Oracle
│   │   └── No Hibernate: No lazy loading, No dirty checking
│   ├── Spring Data MongoDB Reactive: ReactiveMongoRepository
│   └── Spring Data Redis Reactive: ReactiveRedisTemplate
├── WebClient: Reactive HTTP client (covered in Phase 2)
├── WebSocket: Reactive WebSocket (WebSocketHandler)
├── SSE: Flux<ServerSentEvent<T>> — Natural fit for streaming
├── When to use:
│   ├── High concurrency: 10K+ concurrent connections
│   ├── Streaming: Real-time data, SSE, WebSocket
│   ├── Gateway: Spring Cloud Gateway is WebFlux-based
│   └── I/O-bound: Many external API calls, Database queries
├── When NOT to use:
│   ├── JDBC: Blocking (use R2DBC or avoid reactive)
│   ├── Small team: Learning curve is steep
│   ├── CPU-bound: No benefit from reactive
│   └── Simple CRUD: Over-engineering
└── Virtual Threads Alternative:
    ├── Java 21+ Virtual Threads: Similar concurrency benefits
    ├── Imperative code: Easier to read, Debug, Test
    ├── spring.threads.virtual.enabled=true: One config change
    └── Recommendation: For NEW projects, consider Virtual Threads over WebFlux
```

---

## Module 7.4: Spring Modulith

### Section 7.4.1 — Modular Monolith with Spring
```
├── Concept: Structure monolith as independent modules
├── Module Detection: Package-based, Each top-level package = Module
├── Module Rules:
│   ├── Public API: Only classes in module root package are accessible
│   ├── Internal: Sub-packages are module-internal (hidden)
│   └── Dependencies: Module A cannot access Module B's internals
├── Verification: ApplicationModules.of(Application.class).verify()
│   └── Fails if: Module boundary violations, Cyclic dependencies
├── Events:
│   ├── @ApplicationModuleListener: Listen to events from other modules
│   ├── Event Publication Registry: Track if events were processed
│   ├── Incomplete Publications: Retry on restart (at-least-once)
│   └── Event Externalization: Publish to Kafka/RabbitMQ automatically
├── Documentation: Auto-generate module documentation
│   ├── Module dependency diagrams
│   ├── Canvas: Overview of each module (events, APIs, dependencies)
│   └── PlantUML: Auto-generated diagrams
├── Integration Testing:
│   ├── @ApplicationModuleTest: Test a single module in isolation
│   ├── Scenario: Publish events, Verify processing, Assert outcomes
│   └── Bootstrap: Only loads beans for the module under test
├── Benefits:
│   ├── Enforced boundaries without microservice overhead
│   ├── Easy migration to microservices later
│   ├── Module-level testing
│   └── Clear documentation
└── Migration to Microservices:
    ├── Each module → potential microservice
    ├── Events already in place (just externalize to Kafka)
    └── Module API → Service API
```

---

## Module 7.5: Spring Boot Testing (Advanced)

### Section 7.5.1 — Advanced Testing Patterns
```
├── Slice Tests (Targeted Context):
│   ├── @WebMvcTest: Controllers only
│   ├── @DataJpaTest: JPA repositories + Entities
│   ├── @DataMongoTest: MongoDB repositories
│   ├── @DataRedisTest: Redis repositories
│   ├── @DataElasticsearchTest: Elasticsearch
│   ├── @JdbcTest: JdbcTemplate tests
│   ├── @JsonTest: JSON serialization/deserialization
│   ├── @RestClientTest: RestClient testing with MockRestServiceServer
│   └── @WebFluxTest: WebFlux controllers
├── Testcontainers:
│   ├── @Container + @Testcontainers: JUnit 5 integration
│   ├── @ServiceConnection (Spring Boot 3.1+): Auto-configure connection properties
│   ├── Containers: PostgreSQL, MySQL, MongoDB, Redis, Kafka, Elasticsearch, RabbitMQ
│   ├── Reusable Containers: testcontainers.reuse.enable=true (dev speed)
│   └── Compose Module: Start full docker-compose.yml for tests
├── @SpringBootTest Configurations:
│   ├── webEnvironment = MOCK: MockMvc (default, fast)
│   ├── webEnvironment = RANDOM_PORT: Real HTTP server (slower, more realistic)
│   ├── webEnvironment = DEFINED_PORT: Specific port
│   ├── webEnvironment = NONE: No web server (service/repo tests)
│   ├── classes = {App.class, TestConfig.class}: Custom context
│   └── properties = {"spring.profiles.active=test"}
├── Test Fixtures & Data:
│   ├── @Sql: Run SQL scripts before/after test
│   ├── @DynamicPropertySource: Set properties from Testcontainers
│   ├── TestEntityManager: JPA test helper (persist, flush, find)
│   ├── Test Data Builders: Fluent API for creating test entities
│   └── Database Cleaning: @Transactional (auto-rollback) or manual truncation
├── Architecture Testing:
│   ├── ArchUnit: Test architecture rules
│   │   ├── No cycles between packages
│   │   ├── Domain layer doesn't depend on infrastructure
│   │   ├── Services don't access repositories directly (only through domain)
│   │   ├── Controllers only call services
│   │   └── @Entity classes don't depend on @Controller classes
│   └── Spring Modulith: Module boundary verification
├── Performance Testing:
│   ├── JMH (Java Microbenchmark Harness): Micro-benchmarking
│   ├── @SpringBootTest + custom load: Test under realistic load
│   └── Gatling with Spring Boot: Scala-based load testing
└── Test Configuration:
    ├── @TestConfiguration: Test-specific beans
    ├── @MockBean: Replace bean with Mockito mock in context
    ├── @SpyBean: Wrap real bean with Mockito spy
    ├── @Import(TestConfig.class): Import test configuration
    └── application-test.yml: Test-specific properties
```

---

> ### 🛠️ PHASE 7 PROJECT: **AI-Powered Customer Support Platform**
> ```
> ┌─────────────────────────────────────────────────────────────────┐
> │          AI-POWERED CUSTOMER SUPPORT PLATFORM                   │
> ├─────────────────────────────────────────────────────────────────┤
> │                                                                 │
> │ Features:                                                       │
> │  • Knowledge Base: CRUD for support articles (markdown)         │
> │  • AI Chat: RAG-based Q&A from knowledge base                   │
> │  • Ticket System: Create, Assign, Track support tickets         │
> │  • AI Summarization: Auto-summarize ticket conversations        │
> │  • Live Chat: WebSocket-based customer-agent chat               │
> │  • Analytics: Ticket metrics, AI accuracy tracking              │
> │                                                                 │
> │ Technical Requirements:                                         │
> │  ✅ Spring AI: ChatClient with OpenAI/Ollama                    │
> │  ✅ RAG Pipeline: Load articles → Split → Embed → PGVector      │
> │  ✅ Function Calling: AI queries ticket database when asked      │
> │  ✅ Structured Output: AI extracts ticket category + priority    │
> │  ✅ Conversation Memory: JDBC-backed chat memory                │
> │  ✅ Spring Modulith: Modules (tickets, knowledge, chat, ai)     │
> │  ✅ Module Verification: Boundary tests passing                 │
> │  ✅ Event Externalization: Module events → Kafka automatically  │
> │  ✅ WebFlux: SSE for streaming AI responses token-by-token      │
> │  ✅ GraalVM Native: Build native image, Verify startup < 200ms  │
> │  ✅ ArchUnit: Architecture rules enforced in CI                  │
> │  ✅ Testcontainers: PostgreSQL + PGVector + Redis in tests      │
> │  ✅ Slice Tests: Every layer tested independently               │
> └─────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 🏆 PHASE 8: SPRING BOOT IN PRODUCTION AT SCALE
### 📅 Duration: Months 15–18+
### 🎯 Goal: Production hardening — deploy, scale, and operate Spring Boot at enterprise scale
### 👤 Level: Principal Engineer

---

## Module 8.1: Performance Tuning

### Section 8.1.1 — JVM Tuning for Spring Boot
```
├── Heap Sizing:
│   ├── -Xms / -Xmx: Set initial and maximum heap
│   ├── Container-Aware: -XX:MaxRAMPercentage=75 (for Docker)
│   ├── Rule: Don't set Xmx > 75% of container memory
│   └── Metaspace: -XX:MaxMetaspaceSize (default unlimited, set a limit)
├── Garbage Collector Selection:
│   ├── G1GC (default Java 11+): General purpose, Good for most Spring Boot apps
│   │   └── -XX:MaxGCPauseMillis=200 — Target pause time
│   ├── ZGC: Ultra-low latency (<1ms pauses), Java 17+
│   │   └── -XX:+UseZGC — Use for latency-critical services
│   ├── Shenandoah: Low latency, Alternative to ZGC
│   └── Parallel GC: Maximum throughput (batch processing)
├── JVM Flags for Spring Boot:
│   ├── -XX:+UseStringDeduplication: Save memory with G1GC
│   ├── -XX:+UseCompressedOops: Compressed object pointers (default <32GB heap)
│   ├── -XX:+AlwaysPreTouch: Pre-touch memory pages (faster startup after warmup)
│   └── -XX:TieredStopAtLevel=1: Faster startup (less JIT optimization)
├── Profiling & Monitoring:
│   ├── JFR (Java Flight Recorder): Low-overhead production profiling
│   │   ├── -XX:+FlightRecorder -XX:StartFlightRecording=...
│   │   └── JDK Mission Control: Analyze JFR recordings
│   ├── Async Profiler: CPU/Memory/Allocation profiling, Flame graphs
│   ├── VisualVM: Heap dumps, Thread dumps, CPU profiling
│   └── Micrometer: JVM metrics → Prometheus → Grafana
├── Spring Boot Specific:
│   ├── Lazy Initialization: spring.main.lazy-initialization=true (faster startup, slower first request)
│   ├── Application Startup Tracking: ApplicationStartup + /actuator/startup
│   ├── Bean Post Processors: Audit slow bean initialization
│   ├── Class Data Sharing (CDS): -XX:ArchiveClassesAtExit (faster startup)
│   └── AOT Hints: Spring AOT processing for faster startup
└── Thread Pool Tuning:
    ├── Tomcat: server.tomcat.threads.max=200 (tune based on load)
    ├── HikariCP: maximum-pool-size (connections = cores * 2 + spindles)
    ├── @Async: Tune ThreadPoolTaskExecutor sizes
    ├── Virtual Threads: Eliminate thread pool tuning entirely!
    └── Monitoring: Track thread pool utilization via Micrometer
```

### Section 8.1.2 — Application Performance
```
├── HTTP Compression: server.compression.enabled=true, server.compression.min-response-size=1024
├── HTTP/2: server.http2.enabled=true (needs TLS in prod)
├── Keep-Alive: Reuse connections, Reduce TCP handshake overhead
├── Response Caching: ETag, Last-Modified, Cache-Control headers
├── Database:
│   ├── Connection Pool Monitoring: HikariCP metrics in Grafana
│   ├── Slow Query Log: Enable + Alert
│   ├── Index Analysis: Periodic EXPLAIN ANALYZE on critical queries
│   ├── Read Replicas: Route @Transactional(readOnly=true) to replica
│   └── Prepared Statements: spring.jpa.properties.hibernate.jdbc.batch_size=50
├── Serialization:
│   ├── Jackson: Disable SerializationFeature.WRITE_DATES_AS_TIMESTAMPS
│   ├── Jackson: ObjectMapper.setDefaultPropertyInclusion(NON_NULL)
│   ├── Protobuf/gRPC: For internal service-to-service (faster than JSON)
│   └── Avoid: Serialize huge objects (paginate, project)
└── Caching: (Phase 3 revisited)
    ├── Multi-Level: Caffeine (L1) + Redis (L2)
    ├── Warm Cache: Pre-load on startup
    ├── TTL Strategy: Per-cache TTL based on data volatility
    └── Metrics: Hit ratio tracking (should be >90% for effective cache)
```

---

## Module 8.2: Docker & Kubernetes for Spring Boot

### Section 8.2.1 — Docker Best Practices
```
├── Multi-Stage Build:
│   ├── Stage 1: Build with Maven/Gradle (full JDK)
│   ├── Stage 2: Run with JRE only (eclipse-temurin:21-jre-alpine)
│   └── Image Size: ~150MB instead of ~500MB
├── Layered JAR:
│   ├── Spring Boot layers: dependencies → spring-boot-loader →
│   │   snapshot-dependencies → application
│   ├── Docker Layers: Each layer cached independently
│   ├── Result: Only application layer changes on code change (fast rebuild)
│   └── Extract: java -Djarmode=layertools -jar app.jar extract
├── Buildpacks:
│   ├── mvn spring-boot:build-image: OCI image without Dockerfile
│   ├── Paketo Buildpacks: Auto-detect Java version, Optimize
│   └── Benefit: Security patches applied automatically
├── Security:
│   ├── Non-Root User: RUN adduser -D appuser; USER appuser
│   ├── Distroless: gcr.io/distroless/java21-debian12 (no shell, no tools)
│   ├── Vulnerability Scanning: Trivy, Snyk, Grype
│   └── Secrets: Never in image; Use env vars, Mounted secrets
├── Health Checks:
│   ├── HEALTHCHECK CMD curl -f http://localhost:8080/actuator/health || exit 1
│   └── Better: Use Kubernetes probes instead of Docker HEALTHCHECK
└── Configuration:
    ├── Environment Variables: SPRING_DATASOURCE_URL=...
    ├── Config Files: Mount application-prod.yml as volume
    └── Secrets: Mounted files or external secret manager
```

### Section 8.2.2 — Kubernetes Deployment
```
├── Deployment YAML:
│   ├── Replicas: Start with 2-3 for HA
│   ├── Resource Requests/Limits:
│   │   ├── requests: cpu=500m, memory=512Mi (scheduling guarantee)
│   │   └── limits: cpu=1000m, memory=1Gi (hard cap)
│   ├── Strategy: RollingUpdate (maxSurge=1, maxUnavailable=0)
│   └── ImagePullPolicy: Always (for latest), IfNotPresent (for tagged)
├── Probes:
│   ├── Liveness Probe: /actuator/health/liveness
│   │   ├── Restart container if unhealthy
│   │   ├── initialDelaySeconds: 30 (Spring Boot startup time)
│   │   └── periodSeconds: 10, failureThreshold: 3
│   ├── Readiness Probe: /actuator/health/readiness
│   │   ├── Remove from load balancer if not ready
│   │   ├── Checks: Database connectivity, External dependencies
│   │   └── initialDelaySeconds: 15
│   └── Startup Probe: /actuator/health/liveness
│       ├── Allow longer startup time (Spring Boot can be slow)
│       ├── failureThreshold: 30, periodSeconds: 2 (= 60s max startup)
│       └── Once passed, Liveness probe takes over
├── ConfigMap & Secret:
│   ├── ConfigMap: application-kubernetes.yml mounted as file
│   ├── Secret: Database password, API keys
│   ├── Environment Variables: From ConfigMap/Secret
│   └── spring-cloud-starter-kubernetes-client-config: Auto-load
├── Auto-Scaling (HPA):
│   ├── CPU-Based: Scale at 70% CPU utilization
│   ├── Memory-Based: Scale at 80% memory utilization
│   ├── Custom Metrics: Kafka consumer lag, Request queue depth
│   └── KEDA: Event-driven autoscaling (scale to zero)
├── Graceful Shutdown:
│   ├── server.shutdown=graceful: Stop accepting new requests
│   ├── spring.lifecycle.timeout-per-shutdown-phase=30s: Drain timeout
│   ├── preStop Hook: Sleep 5s (allow load balancer to update)
│   └── SIGTERM → Graceful shutdown → Complete in-flight requests → Exit
├── Service & Ingress:
│   ├── ClusterIP Service: Internal communication
│   ├── Ingress: External access with TLS termination
│   └── Service Mesh: Istio/Linkerd for mTLS, Traffic management
└── Helm Chart:
    ├── Parameterized: values.yaml for each environment
    ├── Templates: Deployment, Service, Ingress, ConfigMap, HPA
    ├── values-dev.yaml, values-staging.yaml, values-prod.yaml
    └── Chart repository: Private Helm repo or OCI registry
```

---

## Module 8.3: CI/CD for Spring Boot

### Section 8.3.1 — Production Pipeline
```
├── Pipeline Stages:
│   ├── 1. Build: mvn clean package -DskipTests
│   ├── 2. Unit Tests: mvn test (surefire)
│   ├── 3. Integration Tests: mvn verify (failsafe + Testcontainers)
│   ├── 4. Code Quality: SonarQube scan (quality gate)
│   ├── 5. Security Scan: Dependency check (Snyk, OWASP)
│   ├── 6. Docker Build: Multi-stage build, Push to registry
│   ├── 7. Container Scan: Trivy vulnerability scan
│   ├── 8. Deploy to Staging: ArgoCD sync
│   ├── 9. E2E / Smoke Tests: Against staging environment
│   ├── 10. Performance Test: k6 load test (gate on latency/error rate)
│   ├── 11. Approval Gate: Manual approval for production (optional)
│   └── 12. Deploy to Production: Canary → Full rollout
├── GitHub Actions Example:
│   ├── on: push (branches: main), pull_request
│   ├── Jobs: build → test → sonar → docker → deploy
│   ├── Caching: Maven dependencies, Docker layers
│   └── Secrets: SONAR_TOKEN, DOCKER_PASSWORD, KUBECONFIG
├── GitOps (ArgoCD):
│   ├── Application CRD: Points to Git repo with K8s manifests
│   ├── Sync: Auto-sync on Git push, Manual sync for prod
│   ├── Rollback: Git revert → ArgoCD auto-syncs to previous state
│   └── Multi-Environment: dev, staging, prod ApplicationSets
├── Database Migration in CI/CD:
│   ├── Flyway: Run BEFORE application deployment
│   ├── Backward Compatible: Only additive changes
│   ├── Expand-Contract: Multi-deployment migration process
│   └── Separate Pipeline Step: Migration → Verify → Deploy app
└── Release Versioning:
    ├── Semantic Versioning: MAJOR.MINOR.PATCH
    ├── Git Tag: Automated versioning from Git tags
    ├── Maven Release Plugin: or maven-ci-friendly-versions
    └── Docker Tags: ${version}, latest, commit-sha
```

---

## Module 8.4: Production Observability Stack

### Section 8.4.1 — Full Observability Setup
```
├── Metrics Stack:
│   ├── Spring Boot Actuator → Prometheus → Grafana
│   ├── Essential Dashboards:
│   │   ├── JVM: Heap, GC, Threads, Classes
│   │   ├── HTTP: Request rate, Error rate, Latency (P50/P95/P99)
│   │   ├── Database: Connection pool, Query times, Slow queries
│   │   ├── Cache: Hit/miss ratio, Evictions
│   │   ├── Kafka: Consumer lag, Processing rate
│   │   └── Business: Orders/minute, Revenue, Active users
│   └── SLO Dashboards: SLI tracking, Error budget burn-down
├── Logging Stack:
│   ├── Spring Boot (JSON) → Filebeat/Fluentd → Elasticsearch → Kibana
│   ├── OR: Spring Boot (JSON) → Promtail → Loki → Grafana
│   ├── Structured Logging: JSON with traceId, spanId, userId
│   ├── Log Aggregation: Centralized search across all services
│   └── Alert on Log Patterns: Error rate spikes, Specific error messages
├── Tracing Stack:
│   ├── Micrometer Tracing → Tempo/Jaeger/Zipkin
│   ├── Trace Visualization: Waterfall view of request across services
│   ├── Sampling: 10% in production, 100% on errors
│   └── Exemplars: Link metrics to specific traces
├── Alerting:
│   ├── Grafana Alerting: Rules on Prometheus metrics
│   ├── Alert Routing: PagerDuty (page), Slack (notify), Email (info)
│   ├── SLO-Based: Alert on error budget burn rate (not raw metrics)
│   └── Runbooks: Every alert links to a runbook
└── Unified: Grafana (Metrics + Logs + Traces in one UI)
```

---

> ### 🛠️ PHASE 8 PROJECT: **Production-Ready SaaS Application**
> ```
> ┌────────────────────────────────────────────────────────────────────┐
> │           PRODUCTION-READY SAAS APPLICATION                       │
> ├────────────────────────────────────────────────────────────────────┤
> │                                                                    │
> │ Take your Phase 6 project (Ride-Sharing) and make it              │
> │ PRODUCTION-READY:                                                  │
> │                                                                    │
> │ ⚡ PERFORMANCE:                                                    │
> │  ✅ JVM Tuning: ZGC, Container-aware memory, JFR recording        │
> │  ✅ Connection Pool: Optimized HikariCP settings per service       │
> │  ✅ Caching: Caffeine L1 + Redis L2 with hit ratio > 90%          │
> │  ✅ HTTP/2 enabled with TLS                                       │
> │  ✅ Load Test: k6 script proving 5K RPS at P99 < 100ms            │
> │  ✅ Flame Graphs: Profile and optimize hotspots                   │
> │                                                                    │
> │ 🐳 KUBERNETES:                                                    │
> │  ✅ Helm Charts: All services with values per environment          │
> │  ✅ Probes: Liveness + Readiness + Startup for every service       │
> │  ✅ Graceful Shutdown: 30s drain, preStop hook                     │
> │  ✅ HPA: Auto-scale based on CPU + custom metrics (Kafka lag)     │
> │  ✅ Resource Limits: Properly sized requests/limits                │
> │  ✅ Docker: Multi-stage builds, Non-root, Distroless, <200MB      │
> │  ✅ GraalVM Native: Build at least ONE service as native image     │
> │                                                                    │
> │ 🔄 CI/CD:                                                        │
> │  ✅ GitHub Actions: Build → Test → Sonar → Docker → Deploy        │
> │  ✅ ArgoCD: GitOps-based deployment to Kubernetes                  │
> │  ✅ Canary Deployment: 10% → 50% → 100% with metrics gating      │
> │  ✅ Flyway: Database migration step BEFORE app deployment          │
> │  ✅ Quality Gates: SonarQube, Snyk, Trivy scans pass              │
> │                                                                    │
> │ 📊 OBSERVABILITY:                                                 │
> │  ✅ Prometheus + Grafana: 5+ dashboards (JVM, HTTP, DB, Kafka,    │
> │     Business)                                                      │
> │  ✅ Loki: Centralized structured logging with traceId correlation  │
> │  ✅ Tempo: Distributed tracing with exemplar links from Grafana    │
> │  ✅ SLOs: Defined for every service, Error budget alerting         │
> │  ✅ Alerting: PagerDuty integration, Runbooks for every alert     │
> │  ✅ Custom Business Metrics: Rides/minute, Revenue, Cancellation   │
> │                                                                    │
> │ 📋 DOCUMENTATION:                                                 │
> │  ✅ Architecture Decision Records: 15+ ADRs                       │
> │  ✅ Runbooks: Startup, Shutdown, Failover, Scaling, Rollback      │
> │  ✅ API Documentation: OpenAPI for every service                   │
> │  ✅ Infrastructure Diagram: Full K8s deployment architecture       │
> └────────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 📚 COMPLETE SPRING BOOT READING LIST

```
┌──────────┬──────────────────────────────────────────────────────────────────────┐
│  PHASE   │  BOOKS & RESOURCES                                                  │
├──────────┼──────────────────────────────────────────────────────────────────────┤
│          │  📖 Effective Java (3rd ed) — Joshua Bloch                          │
│  PHASE 1 │  📖 Modern Java in Action — Urma, Fusco, Mycroft                   │
│          │  📖 Spring in Action (6th ed) — Craig Walls                         │
│          │  📖 Spring Start Here — Laurentiu Spilca                            │
├──────────┼──────────────────────────────────────────────────────────────────────┤
│  PHASE 2 │  📖 Spring Boot: Up and Running — Mark Heckler                      │
│          │  📖 RESTful Web APIs — Richardson & Ruby                            │
├──────────┼──────────────────────────────────────────────────────────────────────┤
│          │  📖 Java Persistence with Spring Data and Hibernate — Bauer et al.  │
│  PHASE 3 │  📖 High-Performance Java Persistence — Vlad Mihalcea              │
│          │  📖 Spring Data (official reference documentation)                  │
├──────────┼──────────────────────────────────────────────────────────────────────┤
│  PHASE 4 │  📖 Spring Security in Action (2nd ed) — Laurentiu Spilca          │
│          │  📖 OAuth 2 in Action — Justin Richer & Antonio Sanso              │
├──────────┼──────────────────────────────────────────────────────────────────────┤
│  PHASE 5 │  📖 Kafka: The Definitive Guide (2nd ed) — Narkhede, Shapira      │
│          │  📖 Enterprise Integration Patterns — Hohpe & Woolf                │
├──────────┼──────────────────────────────────────────────────────────────────────┤
│          │  📖 Spring Microservices in Action (2nd ed) — Carnell & Sánchez    │
│  PHASE 6 │  📖 Microservices Patterns — Chris Richardson                      │
│          │  📖 Cloud Native Spring in Action — Thomas Vitale                  │
├──────────┼──────────────────────────────────────────────────────────────────────┤
│  PHASE 7 │  📖 Reactive Spring — Josh Long                                    │
│          │  📖 Spring AI Reference Documentation (official)                   │
├──────────┼──────────────────────────────────────────────────────────────────────┤
│          │  📖 Optimizing Java — Benjamin Evans et al.                        │
│  PHASE 8 │  📖 Kubernetes in Action (2nd ed) — Marko Lukša                    │
│          │  📖 Release It! (2nd ed) — Michael Nygard                          │
└──────────┴──────────────────────────────────────────────────────────────────────┘

🌐 ESSENTIAL ONLINE RESOURCES:
  • Spring Official Docs: https://docs.spring.io/spring-boot/reference/
  • Baeldung: https://www.baeldung.com (comprehensive Spring tutorials)
  • Vlad Mihalcea Blog: https://vladmihalcea.com (JPA/Hibernate performance)
  • Spring Blog: https://spring.io/blog
  • Dan Vega YouTube: Spring Boot content
  • Spring Academy: https://spring.academy (free courses from VMware)
```

---

# 🧭 COMPLETE VISUAL PROGRESSION MAP

```
╔═══════════════════════════════════════════════════════════════════════════════════╗
║                                                                                   ║
║  PHASE 8 ━━ PRODUCTION AT SCALE ━━━━━━━━━━━━━━━━━━━━━━━ [Principal Engineer]    ║
║  ┃                                                                                ║
║  ┣━ 8.1 Performance Tuning     (JVM, GC, Profiling, Thread Pools, Caching)       ║
║  ┣━ 8.2 Docker & Kubernetes    (Multi-stage, Probes, HPA, Graceful Shutdown)     ║
║  ┣━ 8.3 CI/CD Pipeline         (GitHub Actions, ArgoCD, Canary, Quality Gates)   ║
║  ┗━ 8.4 Observability Stack    (Prometheus, Grafana, Loki, Tempo, Alerting)      ║
║      ▲                                                                            ║
║      ║                                                                            ║
║  PHASE 7 ━━ SPRING AI & EMERGING ━━━━━━━━━━━━━━━━━━━━━━ [Advanced Specialist]   ║
║  ┃                                                                                ║
║  ┣━ 7.1 Spring AI              (ChatClient, RAG, Embeddings, Function Calling)   ║
║  ┣━ 7.2 GraalVM Native         (AOT, Native Image, RuntimeHints)                ║
║  ┣━ 7.3 Spring WebFlux         (Reactor, R2DBC, Non-blocking, vs Virtual Threads)║
║  ┣━ 7.4 Spring Modulith        (Module Boundaries, Events, Verification)        ║
║  ┗━ 7.5 Advanced Testing       (Slices, Testcontainers, ArchUnit, Performance)   ║
║      ▲                                                                            ║
║      ║                                                                            ║
║  PHASE 6 ━━ SPRING CLOUD & MICROSERVICES ━━━━━━━━━━━━━━ [Senior Engineer]        ║
║  ┃                                                                                ║
║  ┣━ 6.1 Discovery & Config     (Eureka, Config Server, K8s-native)              ║
║  ┣━ 6.2 Resilience             (Resilience4j: CB, Retry, Bulkhead, Rate Limit)  ║
║  ┣━ 6.3 API Gateway            (Spring Cloud Gateway, Routes, Filters, Security) ║
║  ┣━ 6.4 Observability          (Actuator, Micrometer, Distributed Tracing)      ║
║  ┣━ 6.5 Distributed TX         (Saga, Outbox Pattern, Spring Modulith Events)   ║
║  ┗━ 6.6 Cloud Components       (OpenFeign, K8s Client, Cloud Function, Contract)║
║      ▲                                                                            ║
║      ║                                                                            ║
║  PHASE 5 ━━ MESSAGING, EVENTS & ASYNC ━━━━━━━━━━━━━━━━━ [Mid-Senior Engineer]   ║
║  ┃                                                                                ║
║  ┣━ 5.1 Async Processing       (@Async, CompletableFuture, ThreadPools)          ║
║  ┣━ 5.2 Apache Kafka           (KafkaTemplate, @KafkaListener, Streams, DLT)    ║
║  ┣━ 5.3 RabbitMQ               (RabbitTemplate, @RabbitListener, Exchanges, DLQ) ║
║  ┣━ 5.4 Spring Cloud Stream    (Binder Abstraction, Functional Model)           ║
║  ┗━ 5.5 WebSocket & SSE        (STOMP, SimpMessaging, SseEmitter)               ║
║      ▲                                                                            ║
║      ║                                                                            ║
║  PHASE 4 ━━ SPRING SECURITY (DEEP DIVE) ━━━━━━━━━━━━━━━ [Mid-Level Engineer]    ║
║  ┃                                                                                ║
║  ┣━ 4.1 Security Fundamentals  (Filter Chain, AuthN, AuthZ, JWT, OAuth2 Login)   ║
║  ┗━ 4.2 Advanced Security      (CORS, CSRF, OAuth2 Resource Server, Spring      ║
║                                  Authorization Server, Keycloak, Testing)        ║
║      ▲                                                                            ║
║      ║                                                                            ║
║  PHASE 3 ━━ DATA ACCESS & PERSISTENCE ━━━━━━━━━━━━━━━━━ [Mid-Level Engineer]    ║
║  ┃                                                                                ║
║  ┣━ 3.1 Spring Data JPA        (Entities, Repos, N+1, Transactions, Performance)║
║  ┣━ 3.2 Database Migration     (Flyway, Liquibase, Zero-downtime migrations)    ║
║  ┣━ 3.3 Alternative Data       (Spring Data JDBC, MongoDB, Redis, ES, Caching)  ║
║  ┗━ 3.4 Advanced Patterns      (Multi-DataSource, Read-Write Splitting)          ║
║      ▲                                                                            ║
║      ║                                                                            ║
║  PHASE 2 ━━ BUILDING REST APIs & WEB LAYER ━━━━━━━━━━━━ [Junior+ Engineer]      ║
║  ┃                                                                                ║
║  ┣━ 2.1 Spring MVC & REST      (Controllers, Validation, Exception Handling)     ║
║  ┣━ 2.2 API Design & Docs      (Pagination, Versioning, OpenAPI/Swagger)        ║
║  ┣━ 2.3 HTTP Client            (RestClient, WebClient, Declarative Clients)     ║
║  ┣━ 2.4 Servlet Architecture   (Filter Chain, DispatcherServlet, Interceptors)  ║
║  ┗━ 2.5 Testing REST APIs      (@WebMvcTest, MockMvc, @SpringBootTest, Contract)║
║      ▲                                                                            ║
║      ║                                                                            ║
║  PHASE 1 ━━ JAVA & SPRING CORE FOUNDATIONS ━━━━━━━━━━━━ [Starting Point]         ║
║  ┃                                                                                ║
║  ┣━ 1.1 Java Prerequisites     (OOP, FP, Modern Java 17-21+, Collections,       ║
║  ┃                               Concurrency, Build Tools)                       ║
║  ┣━ 1.2 Spring Framework Core  (IoC, DI, Configuration, AOP, Events)            ║
║  ┗━ 1.3 Spring Boot Basics     (Auto-Config, Starters, Embedded Server,         ║
║                                  Properties, Logging, DevTools)                  ║
║                                                                                   ║
╚═══════════════════════════════════════════════════════════════════════════════════╝

TOTAL: 8 Phases │ 35 Modules │ 100+ Sections │ 8 Milestone Projects │ 20+ Books
TIMELINE: ~18 months (adjust based on prior Java/Spring experience)
```

---

# ⚡ SPRING BOOT GOLDEN RULES

```
┌─────┬────────────────────────────────────────────────────────────────────────┐
│  #  │  RULE                                                                 │
├─────┼────────────────────────────────────────────────────────────────────────┤
│  1  │  Constructor injection ONLY. Never @Autowired on fields.              │
│  2  │  Always use @ConfigurationProperties over @Value.                     │
│  3  │  Disable Open Session in View (spring.jpa.open-in-view=false).        │
│  4  │  ALL fetch types = LAZY. Use JOIN FETCH or @EntityGraph explicitly.   │
│  5  │  @Transactional(readOnly=true) on all read operations.                │
│  6  │  Flyway/Liquibase for EVERY database change. No manual DDL.           │
│  7  │  Test slices (@WebMvcTest, @DataJpaTest) before @SpringBootTest.      │
│  8  │  Use Testcontainers for integration tests. Never mock the database.   │
│  9  │  Actuator endpoints are NOT optional. Health, Metrics, Info always.    │
│ 10  │  Structured JSON logging in production. Include traceId in every log. │
│ 11  │  Externalize ALL configuration. Nothing hardcoded.                    │
│ 12  │  Profile-specific configs: application-dev.yml, application-prod.yml. │
│ 13  │  Graceful shutdown enabled. Always. server.shutdown=graceful.          │
│ 14  │  Spring Security: NEVER disable CSRF without understanding why.       │
│ 15  │  Read the Spring Boot Reference Docs. They are excellent.             │
└─────┴────────────────────────────────────────────────────────────────────────┘
```