# 🟣 THE ULTIMATE ASP.NET ROADMAP
## From Zero to Senior ASP.NET Architect

---

```
╔══════════════════════════════════════════════════════════════════════════════════════╗
║                          ASP.NET MASTERY LADDER                                      ║
║                                                                                      ║
║   🏆 PHASE 8 ─ Microservices & Distributed Systems     [Architect]                   ║
║       ▲                                                                              ║
║   🚀 PHASE 7 ─ Performance, Scalability & DevOps       [Senior Developer]            ║
║       ▲                                                                              ║
║   🧪 PHASE 6 ─ Testing & Quality Assurance             [Senior Developer]            ║
║       ▲                                                                              ║
║   🛡️ PHASE 5 ─ Security & Identity                     [Mid-Senior Developer]        ║
║       ▲                                                                              ║
║   🗄️ PHASE 4 ─ Data Access & Database Patterns         [Mid-Level Developer]         ║
║       ▲                                                                              ║
║   🌐 PHASE 3 ─ API Development & Web Frameworks        [Mid-Level Developer]         ║
║       ▲                                                                              ║
║   ⚙️ PHASE 2 ─ ASP.NET Core Fundamentals               [Junior+ Developer]           ║
║       ▲                                                                              ║
║   🧱 PHASE 1 ─ C# & .NET Foundations                   [Starting Point]              ║
║                                                                                      ║
╚══════════════════════════════════════════════════════════════════════════════════════╝
```

---
---
---

# 🧱 PHASE 1: C# & .NET FOUNDATIONS
### 📅 Duration: Months 1–3
### 🎯 Goal: Master the C# language and .NET runtime before touching ASP.NET
### 👤 Level: Starting Point → Junior Developer

---

## Module 1.1: C# Language Fundamentals

### Section 1.1.1 — Syntax & Basic Constructs
```
├── Variables & Data Types:
│   ├── Value Types: int, double, decimal, bool, char, struct, enum
│   ├── Reference Types: string, object, class, interface, delegate
│   ├── Nullable Types: int?, Nullable<T>, null-coalescing (??, ??=)
│   ├── Null Safety: Nullable reference types (NRT), #nullable enable
│   └── var & Target-typed new: Type inference, new() expression
├── Operators:
│   ├── Arithmetic, Comparison, Logical, Bitwise
│   ├── Null-Conditional: ?. and ?[] operators
│   ├── Pattern Matching Operators: is, switch expressions, and/or/not
│   └── Range & Index: ^1 (from end), 0..5 (range), [..] (slice)
├── Control Flow:
│   ├── if/else, switch (classic + expression-based)
│   ├── Loops: for, foreach, while, do-while
│   ├── Pattern Matching in switch: Type patterns, Property patterns, Positional
│   └── Guard Clauses: Early returns for clean code
├── Strings:
│   ├── String Interpolation: $"Hello {name}"
│   ├── Raw String Literals: """multi-line""" (C# 11)
│   ├── StringBuilder: Efficient string concatenation
│   ├── Span<char>: High-performance string operations
│   └── String Comparison: Ordinal vs CurrentCulture vs InvariantCulture
└── Arrays & Collections:
    ├── Arrays: Single, Multi-dimensional, Jagged
    ├── List<T>, Dictionary<TKey,TValue>, HashSet<T>, Queue<T>, Stack<T>
    ├── IEnumerable<T> vs ICollection<T> vs IList<T>
    ├── ReadOnlyCollection<T>, ImmutableList<T>
    └── Collection Expressions: [1, 2, 3] (C# 12)
```

### Section 1.1.2 — Object-Oriented Programming in C#
```
├── Classes & Objects:
│   ├── Constructors: Default, Parameterized, Static, Primary constructors (C# 12)
│   ├── Properties: Auto-properties, Get/Set/Init, Computed properties
│   ├── Fields: private backing fields, readonly, const
│   ├── Methods: Instance, Static, Extension methods
│   └── Access Modifiers: public, private, protected, internal, protected internal, file
├── Inheritance:
│   ├── Base classes, Derived classes, sealed, abstract
│   ├── virtual / override / new (hiding)
│   ├── Constructor Chaining: base() calls
│   └── When to use: IS-A relationship only
├── Interfaces:
│   ├── Interface definition & implementation
│   ├── Default Interface Methods (C# 8+)
│   ├── Explicit interface implementation
│   ├── Multiple interface inheritance
│   └── When to use: Contracts, Testability, DI
├── Abstract Classes vs Interfaces:
│   ├── Abstract: Shared state + behavior, Single inheritance
│   └── Interface: Pure contract, Multiple inheritance, No state (mostly)
├── Encapsulation:
│   ├── Private fields + Public properties
│   ├── Immutability patterns: readonly, init-only setters
│   └── Tell Don't Ask principle
├── Polymorphism:
│   ├── Runtime (virtual/override): Method dispatch
│   ├── Compile-time (overloading): Same name, Different parameters
│   └── Covariance & Contravariance: in/out generic modifiers
├── Special Types:
│   ├── Records: record class, record struct — Immutable data types
│   │   └── With expressions: person with { Name = "New" }
│   ├── Structs: Value types, Stack allocated, When to use vs class
│   ├── Enums: Underlying types, [Flags], Parsing, String conversion
│   └── Sealed Classes: Prevent inheritance, Performance benefit
└── Object Lifecycle:
    ├── Garbage Collection: Generations (0, 1, 2), LOH, Finalization
    ├── IDisposable: Deterministic cleanup, using statement, using declaration
    ├── Dispose Pattern: Implementing IDisposable correctly
    └── Weak References: WeakReference<T> for caches
```

### Section 1.1.3 — Generics
```
├── Generic Classes: class Repository<T>
├── Generic Methods: T Find<T>(int id)
├── Generic Interfaces: IRepository<T>, IComparer<T>
├── Constraints:
│   ├── where T : class (reference type)
│   ├── where T : struct (value type)
│   ├── where T : new() (parameterless constructor)
│   ├── where T : ISomeInterface (interface constraint)
│   ├── where T : BaseClass (base class constraint)
│   └── where T : notnull (C# 8+)
├── Covariance (out) & Contravariance (in):
│   ├── IEnumerable<out T> — covariant (read-only)
│   └── IComparer<in T> — contravariant (write-only)
├── Generic Collections: List<T>, Dictionary<TK,TV>, HashSet<T>
└── When to use: Type safety without code duplication
```

### Section 1.1.4 — Delegates, Events & Lambdas
```
├── Delegates:
│   ├── Definition: Type-safe function pointers
│   ├── Built-in: Action<T>, Func<T,TResult>, Predicate<T>
│   ├── Multicast Delegates: += and -= operators
│   └── Delegate Invocation: Null-conditional invoke ?.Invoke()
├── Events:
│   ├── Event keyword: Publisher/Subscriber pattern
│   ├── EventHandler<TEventArgs>: Standard pattern
│   ├── Custom Events: Declaring, Raising, Subscribing
│   └── Weak Events: Preventing memory leaks (WeakEventManager)
├── Lambda Expressions:
│   ├── Expression Lambdas: x => x * 2
│   ├── Statement Lambdas: x => { return x * 2; }
│   ├── Closures: Capturing outer variables
│   ├── Natural Type: var parse = (string s) => int.Parse(s);
│   └── Lambda Attributes: [Attribute] (x) => ... (C# 10+)
├── Expression Trees:
│   ├── Expression<Func<T,bool>>: Code as data
│   ├── Use in ORMs: EF Core translates to SQL
│   └── Building & Compiling expressions dynamically
└── Local Functions:
    ├── Nested functions within methods
    ├── static local functions: No closure capture
    └── Use case: Helper logic, Recursive algorithms
```

### Section 1.1.5 — LINQ (Language Integrated Query)
```
├── Query Syntax: from x in collection where x > 5 select x
├── Method Syntax (Fluent): collection.Where(x => x > 5).Select(x => x)
├── Core Operators:
│   ├── Filtering: Where, OfType
│   ├── Projection: Select, SelectMany
│   ├── Ordering: OrderBy, OrderByDescending, ThenBy
│   ├── Grouping: GroupBy, GroupJoin
│   ├── Joining: Join, GroupJoin
│   ├── Aggregation: Count, Sum, Average, Min, Max, Aggregate
│   ├── Element: First, FirstOrDefault, Single, SingleOrDefault, ElementAt
│   ├── Quantifiers: Any, All, Contains
│   ├── Set: Distinct, Union, Intersect, Except
│   ├── Partitioning: Take, Skip, TakeLast, SkipLast, Chunk (C# 10)
│   └── Generation: Range, Repeat, Empty
├── Deferred Execution: LINQ queries are lazy — executed on enumeration
├── Immediate Execution: ToList(), ToArray(), ToDictionary(), Count()
├── IQueryable<T> vs IEnumerable<T>:
│   ├── IEnumerable: In-memory (LINQ to Objects)
│   └── IQueryable: Translatable (LINQ to SQL/EF Core) — expressions, not delegates
├── LINQ Performance:
│   ├── Avoid multiple enumeration
│   ├── Use Any() instead of Count() > 0
│   ├── Prefer FirstOrDefault() over Where().First()
│   └── Know when LINQ adds overhead vs raw loops
└── Advanced:
    ├── Custom Extension Methods for LINQ
    ├── AsParallel() — PLINQ (Parallel LINQ)
    └── Async LINQ: ToListAsync(), System.Linq.Async
```

---

## Module 1.2: Advanced C# Features

### Section 1.2.1 — Asynchronous Programming
```
├── async/await:
│   ├── Task & Task<T>: Representation of async operations
│   ├── ValueTask & ValueTask<T>: Avoiding allocations for sync completions
│   ├── async methods: State machine generation by compiler
│   ├── await: Suspend and resume without blocking threads
│   ├── ConfigureAwait(false): When to use (library code vs app code)
│   └── Async void: NEVER use (except event handlers) — unobserved exceptions
├── Async Patterns:
│   ├── Task.WhenAll: Parallel async operations
│   ├── Task.WhenAny: First-to-complete wins
│   ├── Task.Run: Offload CPU-bound work to thread pool
│   ├── Cancellation: CancellationToken, CancellationTokenSource
│   ├── Progress Reporting: IProgress<T>, Progress<T>
│   └── Async Streams: IAsyncEnumerable<T>, await foreach
├── SynchronizationContext:
│   ├── What it is: Manages thread affinity (UI thread, ASP.NET context)
│   ├── ASP.NET Core: No SynchronizationContext (by design)
│   └── Deadlocks: .Result / .Wait() on Task → deadlock in UI/legacy ASP.NET
├── Channels:
│   ├── Channel<T>: Thread-safe producer-consumer
│   ├── Bounded vs Unbounded channels
│   └── Use case: Background processing, Pipeline stages
├── Parallel Programming:
│   ├── Parallel.ForEach, Parallel.For
│   ├── Task Parallel Library (TPL)
│   ├── Thread Pool: ThreadPool.QueueUserWorkItem
│   └── When to use parallel vs async: CPU-bound vs I/O-bound
├── Synchronization:
│   ├── lock statement: Monitor.Enter/Exit
│   ├── SemaphoreSlim: Async-compatible semaphore
│   ├── ReaderWriterLockSlim: Multiple readers, Single writer
│   ├── ConcurrentDictionary<TK,TV>: Thread-safe dictionary
│   ├── ConcurrentQueue<T>, ConcurrentBag<T>
│   └── Interlocked: Atomic operations (Increment, CompareExchange)
└── Common Pitfalls:
    ├── Async over sync: Don't wrap sync code in Task.Run
    ├── Sync over async: Don't use .Result or .GetAwaiter().GetResult()
    ├── Fire-and-forget: Lost exceptions → use with care
    └── Thread starvation: Too many blocking calls in thread pool
```

### Section 1.2.2 — Error Handling & Exceptions
```
├── Exception Hierarchy:
│   ├── System.Exception (base)
│   ├── System.SystemException: CLR exceptions
│   ├── System.ApplicationException: Don't use (legacy)
│   └── Custom Exceptions: Inherit from Exception, Provide constructors
├── try/catch/finally/when:
│   ├── Catch specific exceptions (most specific first)
│   ├── Exception filters: catch (Exception ex) when (ex.Message.Contains("..."))
│   ├── finally: Always executes (cleanup)
│   └── throw vs throw ex: Preserve stack trace (always use throw;)
├── Custom Exceptions:
│   ├── DomainException, NotFoundException, ValidationException
│   ├── Constructors: Default, Message, Message+Inner
│   ├── Serialization: [Serializable] (for remoting/legacy)
│   └── Additional properties: ErrorCode, Details
├── Result Pattern (as alternative):
│   ├── Result<T>: Success(T value) | Failure(Error error)
│   ├── Libraries: FluentResults, ErrorOr, OneOf
│   ├── Railway-Oriented Programming: Chain operations
│   └── When to use: Expected failures (validation), Not exceptional situations
├── Global Error Handling (ASP.NET Core):
│   ├── Exception Middleware: UseExceptionHandler
│   ├── Problem Details: RFC 7807 standard error responses
│   ├── IExceptionHandler (NET 8+): Built-in exception handler
│   └── Logging: Always log exceptions with structured logging
└── Best Practices:
    ├── Don't catch Exception unless you're at the top level
    ├── Don't use exceptions for flow control
    ├── Include context in exception messages
    ├── Use inner exceptions for wrapping
    └── Fail fast on unrecoverable errors
```

### Section 1.2.3 — Modern C# Features (C# 10–12)
```
├── C# 10:
│   ├── Global Usings: global using System.Linq;
│   ├── File-scoped Namespaces: namespace MyApp;
│   ├── Record Structs: readonly record struct Point(int X, int Y);
│   ├── Interpolated String Handler: Custom string interpolation
│   └── Extended Property Patterns: { Prop.SubProp: value }
├── C# 11:
│   ├── Raw String Literals: """json""", No escaping needed
│   ├── Generic Math: INumber<T>, Static abstract interface members
│   ├── Required Members: required keyword on properties
│   ├── List Patterns: [1, 2, .., 10] pattern matching
│   ├── UTF-8 String Literals: "hello"u8 → ReadOnlySpan<byte>
│   └── File-scoped Types: file class Helper { }
├── C# 12:
│   ├── Primary Constructors (for classes): class Service(IRepo repo)
│   ├── Collection Expressions: [1, 2, 3], [..list1, ..list2]
│   ├── Default Lambda Parameters: (int x = 5) => x * 2
│   ├── Alias Any Type: using Point = (int X, int Y);
│   └── Inline Arrays: [InlineArray(10)] struct Buffer
├── C# 13 (Preview/Latest):
│   ├── params collections: params ReadOnlySpan<T>
│   ├── New lock type: System.Threading.Lock
│   ├── ref struct interfaces: Allow ref structs in generics
│   └── Partial properties: partial string Name { get; set; }
└── Pattern Matching Evolution:
    ├── C# 7: Type patterns, Const patterns
    ├── C# 8: Property patterns, Tuple patterns, Positional patterns
    ├── C# 9: Relational (> 5), Logical (and, or, not)
    ├── C# 10: Extended property patterns
    ├── C# 11: List patterns, Slice patterns
    └── Exhaustive switch: Compiler warns about missing cases
```

### Section 1.2.4 — Memory Management & Performance
```
├── Value Types vs Reference Types:
│   ├── Stack vs Heap allocation
│   ├── Boxing & Unboxing: Performance implications
│   ├── Passing by value vs by reference (ref, in, out)
│   └── ref returns and ref locals
├── Span<T> & Memory<T>:
│   ├── Span<T>: Stack-only, Zero-allocation slicing
│   ├── ReadOnlySpan<T>: Read-only view
│   ├── Memory<T>: Heap-safe version of Span<T>
│   ├── Use case: Parsing, String manipulation, Buffer operations
│   └── stackalloc: Allocate on stack (with Span<T>)
├── ArrayPool<T> & MemoryPool<T>: Rent/Return buffers, Avoid allocations
├── String Optimization:
│   ├── String.Create: Build strings without intermediate allocations
│   ├── String interning: string.Intern, Reduce duplicates
│   └── StringComparison: Always specify comparison type
├── Garbage Collection:
│   ├── Generations: Gen0 (short-lived), Gen1 (medium), Gen2 (long-lived)
│   ├── LOH (Large Object Heap): > 85KB, Less frequently collected
│   ├── GC Modes: Workstation vs Server, Concurrent vs Background
│   ├── GC.Collect(): Don't call (almost never needed)
│   └── GC Configuration: <GarbageCollectionAdaptationMode> in .csproj
├── Benchmarking:
│   ├── BenchmarkDotNet: The standard for .NET benchmarking
│   ├── Methodology: Warmup, Iterations, Statistical analysis
│   └── Diagnostics: MemoryDiagnoser, GC allocation tracking
└── Profiling:
    ├── dotnet-counters: Real-time performance monitoring
    ├── dotnet-trace: Collect traces for analysis
    ├── dotnet-dump: Memory dump analysis
    └── Visual Studio Profiler: CPU, Memory, Allocation profiling
```

---

## Module 1.3: .NET Ecosystem & Tooling

### Section 1.3.1 — .NET Runtime & SDK
```
├── .NET Versions:
│   ├── .NET 6 (LTS), .NET 7, .NET 8 (LTS), .NET 9, .NET 10 (LTS - upcoming)
│   ├── LTS vs STS: Long-Term Support (3 years) vs Standard Term (18 months)
│   └── Always target latest LTS for production
├── .NET CLI:
│   ├── dotnet new: Project templates (webapi, mvc, blazor, classlib, sln)
│   ├── dotnet build / dotnet run / dotnet publish
│   ├── dotnet test: Run tests
│   ├── dotnet add package: NuGet package management
│   ├── dotnet ef: Entity Framework Core CLI tools
│   ├── dotnet tool: Global and local .NET tools
│   └── dotnet watch: Hot reload during development
├── Project System:
│   ├── .csproj: SDK-style project file (XML)
│   ├── Target Framework: <TargetFramework>net8.0</TargetFramework>
│   ├── Multi-targeting: <TargetFrameworks>net8.0;net9.0</TargetFrameworks>
│   ├── Package References: NuGet dependencies
│   ├── Project References: Inter-project dependencies
│   ├── Directory.Build.props / .targets: Centralized build config
│   └── global.json: Pin SDK version for team consistency
├── NuGet:
│   ├── Package Manager: nuget.org, Private feeds (Azure Artifacts, GitHub Packages)
│   ├── Package Versioning: SemVer (Major.Minor.Patch)
│   ├── Central Package Management: Directory.Packages.props
│   ├── Creating Packages: dotnet pack, .nuspec
│   └── Security: Package signing, Vulnerability scanning
├── Solution Architecture:
│   ├── Solution (.sln) structure for multi-project apps
│   ├── Project per layer: API, Domain, Application, Infrastructure
│   └── Shared projects: Common utilities, Contracts
└── .NET Aspire (.NET 8+):
    ├── Cloud-native development orchestration
    ├── Service defaults: Telemetry, Health checks, Resilience
    ├── App host: Orchestrate multi-service local development
    └── Components: Pre-configured integrations (Redis, PostgreSQL, Kafka, etc.)
```

### Section 1.3.2 — Configuration & Dependency Injection
```
├── Configuration:
│   ├── Configuration Sources (priority order):
│   │   ├── appsettings.json (base)
│   │   ├── appsettings.{Environment}.json (environment-specific)
│   │   ├── User Secrets (development only, secret.json)
│   │   ├── Environment Variables
│   │   ├── Command-line Arguments
│   │   └── Azure Key Vault / AWS Secrets Manager
│   ├── Options Pattern:
│   │   ├── IOptions<T>: Singleton, Read once at startup
│   │   ├── IOptionsSnapshot<T>: Scoped, Refreshed per request
│   │   ├── IOptionsMonitor<T>: Singleton, Reacts to changes
│   │   └── Validation: ValidateDataAnnotations(), ValidateOnStart()
│   ├── Strongly-Typed Configuration:
│   │   ├── services.Configure<MyOptions>(config.GetSection("My"))
│   │   └── services.AddOptions<MyOptions>().Bind(config).ValidateOnStart()
│   └── User Secrets: dotnet user-secrets set "Key" "Value"
├── Dependency Injection (Built-in):
│   ├── Service Lifetimes:
│   │   ├── Transient: New instance every time (AddTransient)
│   │   ├── Scoped: One instance per request/scope (AddScoped)
│   │   └── Singleton: One instance for app lifetime (AddSingleton)
│   ├── Registration:
│   │   ├── services.AddTransient<IService, ServiceImpl>()
│   │   ├── services.AddScoped<IRepository, EfRepository>()
│   │   ├── services.AddSingleton<ICacheService, RedisCacheService>()
│   │   ├── services.AddKeyedTransient<INotifier, EmailNotifier>("email")
│   │   └── Factory Registration: services.AddTransient<IService>(sp => new Service(sp.GetRequiredService<IDep>()))
│   ├── Resolution:
│   │   ├── Constructor Injection (preferred)
│   │   ├── [FromServices] in controller actions
│   │   ├── [FromKeyedServices("key")] for keyed services
│   │   └── IServiceProvider: Service locator (avoid if possible)
│   ├── Common Mistakes:
│   │   ├── Captive Dependency: Singleton holding Scoped service → memory leak
│   │   ├── Over-injection: Too many dependencies → Split class
│   │   └── Service Locator Anti-Pattern: Don't resolve from IServiceProvider manually
│   └── Advanced DI:
│       ├── Open Generics: services.AddTransient(typeof(IRepo<>), typeof(EfRepo<>))
│       ├── Decorator Pattern: Scrutor library, Manual decoration
│       ├── Keyed Services (.NET 8+): Named service resolution
│       └── Scrutor: Assembly scanning, Decoration, Interception
└── Logging:
    ├── ILogger<T>: Built-in logging abstraction
    ├── Log Levels: Trace, Debug, Information, Warning, Error, Critical
    ├── Structured Logging: logger.LogInformation("Order {OrderId} placed", orderId)
    ├── Providers: Console, Debug, EventSource, Third-party (Serilog, NLog)
    ├── Serilog:
    │   ├── Sinks: Console, File, Seq, Elasticsearch, ApplicationInsights
    │   ├── Enrichers: Machine name, Thread ID, Custom properties
    │   ├── Destructuring: @operator for object serialization
    │   └── Configuration: Via appsettings.json or code
    ├── Log Scopes: using (_logger.BeginScope("Processing {OrderId}", id))
    └── High-Performance Logging: LoggerMessage.Define (source generated in .NET 6+)
```

---

## Module 1.4: SOLID Principles in C#

### Section 1.4.1 — SOLID with C# Examples
```
├── SRP: One class, One reason to change
│   ├── Bad: OrderService that validates, saves, sends email, generates PDF
│   ├── Good: OrderValidator, OrderRepository, OrderNotifier, InvoiceGenerator
│   └── C# Tool: Separate into focused services, Inject via DI
├── OCP: Open for extension, Closed for modification
│   ├── Bad: switch(paymentType) in PaymentProcessor
│   ├── Good: IPaymentStrategy + StripeStrategy, PayPalStrategy
│   └── C# Tool: Strategy pattern with DI, Middleware pipeline
├── LSP: Subtypes must be substitutable
│   ├── Bad: SqlRepository throws NotImplementedException for FindByEmail()
│   ├── Good: Separate IReadRepository, IWriteRepository interfaces
│   └── C# Tool: Interface segregation, Contract testing
├── ISP: No client should depend on unused methods
│   ├── Bad: IRepository<T> with 20+ methods, Most implementations throw NotImplemented
│   ├── Good: IReadRepository<T>, IWriteRepository<T>, IPagedRepository<T>
│   └── C# Tool: Small interfaces, Default interface members for optional behavior
└── DIP: Depend on abstractions, Not concretions
    ├── Bad: OrderService directly creates new SqlOrderRepository()
    ├── Good: OrderService depends on IOrderRepository (injected)
    └── C# Tool: Built-in DI container, Constructor injection
```

---

> ### 🛠️ PHASE 1 PROJECT: **Console-Based Expense Tracker**
> ```
> ┌─────────────────────────────────────────────────────────────────┐
> │               CONSOLE-BASED EXPENSE TRACKER                     │
> ├─────────────────────────────────────────────────────────────────┤
> │                                                                 │
> │ Features:                                                       │
> │  • Add, Edit, Delete, List expenses                             │
> │  • Categories: Food, Transport, Entertainment, Bills, Other     │
> │  • Monthly/Weekly/Daily summary reports                         │
> │  • Budget alerts (notify when exceeding budget)                 │
> │  • Export to CSV/JSON                                           │
> │  • Import from CSV                                              │
> │  • Search & filter by date range, category, amount              │
> │                                                                 │
> │ Technical Requirements:                                         │
> │  ✅ Apply ALL SOLID principles — document where & why            │
> │  ✅ Use generics for repository pattern                          │
> │  ✅ LINQ for all data queries (no manual loops for filtering)    │
> │  ✅ async/await for file I/O operations                          │
> │  ✅ Custom exceptions: InvalidExpenseException, BudgetExceeded   │
> │  ✅ IDisposable for file handlers                                │
> │  ✅ Records for immutable data: ExpenseRecord, CategoryBudget    │
> │  ✅ Dependency Injection: Microsoft.Extensions.DI (manual setup) │
> │  ✅ Structured logging: Serilog to console + file                │
> │  ✅ Configuration: appsettings.json for budgets, categories      │
> │  ✅ Unit tests: xUnit + FluentAssertions (80%+ coverage)         │
> │  ✅ Pattern matching for command parsing                          │
> │  ✅ Span<T> for efficient CSV parsing                            │
> └─────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# ⚙️ PHASE 2: ASP.NET CORE FUNDAMENTALS
### 📅 Duration: Months 3–5
### 🎯 Goal: Understand the ASP.NET Core pipeline, hosting, and core concepts
### 👤 Level: Junior+ Developer

---

## Module 2.1: ASP.NET Core Architecture

### Section 2.1.1 — Hosting & Application Lifecycle
```
├── Program.cs (Minimal Hosting Model):
│   ├── WebApplication.CreateBuilder(args): Build the host
│   ├── builder.Services: Register DI services
│   ├── builder.Configuration: Access configuration
│   ├── builder.Logging: Configure logging
│   ├── builder.Environment: Dev/Staging/Production
│   ├── var app = builder.Build(): Build the app
│   ├── app.Map...: Configure endpoints
│   └── app.Run(): Start the application
├── Web Server:
│   ├── Kestrel: Default, Cross-platform, High-performance
│   │   ├── Configuration: Ports, HTTPS, Limits, HTTP/2, HTTP/3
│   │   └── Behind Reverse Proxy: NGINX, Apache, IIS, YARP
│   ├── IIS (Windows): In-process vs Out-of-process hosting
│   └── HTTP.sys (Windows): Kernel-mode HTTP server
├── Environments:
│   ├── ASPNETCORE_ENVIRONMENT: Development, Staging, Production
│   ├── IWebHostEnvironment: IsDevelopment(), IsProduction()
│   ├── Environment-specific config: appsettings.Production.json
│   └── launchSettings.json: Development environment profiles
├── Host Lifetime:
│   ├── IHostApplicationLifetime: ApplicationStarted, ApplicationStopping, ApplicationStopped
│   ├── IHostedService: Background services, Startup/shutdown hooks
│   └── Graceful Shutdown: SIGTERM handling, Draining requests
└── .NET Aspire Integration:
    ├── Service Defaults: AddServiceDefaults() — telemetry, health, resilience
    ├── App Host: Orchestrate multiple services locally
    └── Dashboard: Built-in observability during development
```

### Section 2.1.2 — Middleware Pipeline
```
├── Concept: Request → Middleware 1 → Middleware 2 → ... → Endpoint → Response (reverse)
├── Built-in Middleware (ORDER MATTERS):
│   ├── UseExceptionHandler() / UseDeveloperExceptionPage()
│   ├── UseHsts()
│   ├── UseHttpsRedirection()
│   ├── UseStaticFiles()
│   ├── UseRouting()
│   ├── UseCors()
│   ├── UseAuthentication()
│   ├── UseAuthorization()
│   ├── UseRateLimiter()
│   ├── UseResponseCaching()
│   ├── UseResponseCompression()
│   └── MapControllers() / MapRazorPages() / Map endpoints
├── Custom Middleware:
│   ├── Inline: app.Use(async (context, next) => { await next(); })
│   ├── Class-based: IMiddleware interface or Convention-based
│   ├── Dependency Injection in middleware
│   └── Terminal Middleware: app.Run() — doesn't call next()
├── Middleware Order: Critical!
│   ├── Exception handling → FIRST (catches everything)
│   ├── HTTPS redirect → Early
│   ├── Static files → Before routing (short-circuit for static content)
│   ├── Routing → Before auth
│   ├── Authentication → Before Authorization
│   ├── Authorization → After Authentication
│   └── Endpoint → LAST
├── Branching: app.Map(), app.MapWhen(), app.UseWhen()
├── Request/Response Manipulation:
│   ├── HttpContext: Request, Response, User, Items, Features
│   ├── Reading Request Body: EnableBuffering(), ReadAsJsonAsync()
│   └── Writing Response: WriteAsJsonAsync(), StatusCode, Headers
└── Common Custom Middleware:
    ├── Request/Response logging
    ├── Correlation ID injection
    ├── Tenant resolution (multi-tenancy)
    ├── Request timing / Performance headers
    └── Custom error formatting
```

### Section 2.1.3 — Routing
```
├── Endpoint Routing:
│   ├── Convention-based: MapControllerRoute("{controller}/{action}/{id?}")
│   ├── Attribute Routing: [Route("api/[controller]")], [HttpGet("{id}")]
│   └── Minimal API: app.MapGet("/api/items/{id}", handler)
├── Route Constraints:
│   ├── Type: {id:int}, {name:alpha}, {price:decimal}
│   ├── Range: {age:range(18,120)}, {id:min(1)}
│   ├── Length: {name:length(2,50)}, {code:maxlength(10)}
│   ├── Regex: {ssn:regex(^\\d{{3}}-\\d{{2}}-\\d{{4}}$)}
│   └── Custom: Implement IRouteConstraint
├── Route Parameters:
│   ├── Required: {id}
│   ├── Optional: {id?}
│   ├── Default: {page=1}
│   └── Catch-all: {**path}
├── Route Groups (.NET 7+):
│   ├── var group = app.MapGroup("/api/v1/products");
│   ├── group.MapGet("/", GetAll);
│   ├── group.MapGet("/{id}", GetById);
│   └── Nested groups for versioning
└── URL Generation:
    ├── LinkGenerator: Generate URLs from route names
    ├── IUrlHelper: In controllers
    └── Route Names: [HttpGet("{id}", Name = "GetProduct")]
```

### Section 2.1.4 — Model Binding & Validation
```
├── Model Binding Sources:
│   ├── [FromBody]: Request body (JSON, XML)
│   ├── [FromRoute]: Route parameters
│   ├── [FromQuery]: Query string parameters
│   ├── [FromHeader]: Request headers
│   ├── [FromForm]: Form data (multipart/form-data)
│   ├── [FromServices]: DI container
│   └── [AsParameters]: Bind multiple sources to a record/class (Minimal APIs)
├── Custom Model Binders:
│   ├── Implement IModelBinder
│   ├── Apply with [ModelBinder(typeof(...))]
│   └── Use case: Custom date formats, Complex query parameters
├── Validation:
│   ├── Data Annotations:
│   │   ├── [Required], [StringLength], [Range], [EmailAddress]
│   │   ├── [RegularExpression], [Compare], [Phone], [Url]
│   │   ├── [MaxLength], [MinLength], [CreditCard]
│   │   └── Custom: Implement ValidationAttribute
│   ├── ModelState:
│   │   ├── ModelState.IsValid: Check in controller
│   │   ├── [ApiController]: Automatic 400 response on invalid model
│   │   └── Custom error messages: [Required(ErrorMessage = "...")]
│   ├── FluentValidation (recommended for complex rules):
│   │   ├── RuleFor(x => x.Name).NotEmpty().MaximumLength(100)
│   │   ├── RuleFor(x => x.Email).EmailAddress()
│   │   ├── Complex rules: Must(), When(), Custom()
│   │   ├── Async validation: MustAsync()
│   │   └── Integration: AddFluentValidation() or manual in pipeline
│   └── Validation in Minimal APIs:
│       ├── Manual: Validate in handler
│       ├── Endpoint Filters: Validation as filter
│       └── Libraries: MiniValidation, FluentValidation
└── Content Negotiation:
    ├── Accept header: application/json, application/xml
    ├── Output Formatters: JSON (default), XML (opt-in), Custom
    ├── Input Formatters: JSON (System.Text.Json), Newtonsoft.Json
    └── System.Text.Json vs Newtonsoft.Json:
        ├── STJ: Built-in, Faster, Less features
        ├── Newtonsoft: More features, Slower, Legacy
        └── Recommendation: STJ for new projects
```

---

## Module 2.2: ASP.NET Core Web Frameworks

### Section 2.2.1 — Minimal APIs
```
├── Basic Setup:
│   ├── app.MapGet("/items", () => Results.Ok(items));
│   ├── app.MapPost("/items", (Item item) => Results.Created(...));
│   ├── app.MapPut("/items/{id}", (int id, Item item) => ...);
│   └── app.MapDelete("/items/{id}", (int id) => ...);
├── Route Groups:
│   ├── Group related endpoints
│   ├── Apply shared filters/metadata
│   └── Nested groups for versioning
├── Results:
│   ├── TypedResults (strongly typed): TypedResults.Ok(item)
│   ├── Results (dynamic): Results.Ok(item)
│   ├── Common: Ok, Created, NoContent, NotFound, BadRequest, Problem
│   └── Custom: Results.Extensions
├── Endpoint Filters:
│   ├── Before/After logic (similar to action filters)
│   ├── Validation filters
│   ├── Logging filters
│   └── app.MapGet(...).AddEndpointFilter<ValidationFilter>()
├── OpenAPI / Swagger:
│   ├── WithName(), WithTags(), WithDescription()
│   ├── Produces<T>(200), ProducesValidationProblem()
│   ├── WithOpenApi(): Customize OpenAPI metadata
│   └── .NET 9+: Built-in OpenAPI document generation
├── Organizing Minimal APIs:
│   ├── Extension Methods: app.MapProductEndpoints()
│   ├── Carter Library: Module-based organization
│   └── Static classes per feature
├── When to use:
│   ├── Simple APIs, Microservices
│   ├── Performance-critical endpoints
│   ├── Quick prototyping
│   └── Azure Functions-style simplicity
└── When NOT to use:
    ├── Large applications with many controllers (MVC better)
    ├── Complex content negotiation
    └── Teams familiar with MVC conventions
```

### Section 2.2.2 — MVC (Model-View-Controller)
```
├── Controllers:
│   ├── [ApiController]: API conventions (auto 400, binding source inference)
│   ├── ControllerBase: API controllers (no view support)
│   ├── Controller: Full MVC with view support
│   ├── Action Methods: Public methods returning IActionResult or specific types
│   ├── Action Results: Ok(), NotFound(), BadRequest(), Created(), File()
│   └── Async Actions: Task<IActionResult>, Task<ActionResult<T>>
├── Filters (Pipeline):
│   ├── Authorization Filters: [Authorize], Custom IAuthorizationFilter
│   ├── Resource Filters: Short-circuit before model binding
│   ├── Action Filters: Before/after action execution
│   │   └── IActionFilter, IAsyncActionFilter, ActionFilterAttribute
│   ├── Exception Filters: Handle exceptions from actions
│   │   └── IExceptionFilter, ExceptionFilterAttribute
│   ├── Result Filters: Before/after result execution
│   └── Filter Order: Authorization → Resource → Action → Exception → Result
│       └── Filter Scope: Global → Controller → Action
├── Views (Razor):
│   ├── Razor Syntax: @expression, @{ code block }, @if, @for, @foreach
│   ├── Layouts: _Layout.cshtml, @RenderBody(), @RenderSection()
│   ├── Partial Views: <partial name="_MyPartial" model="..."/>
│   ├── View Components: Server-side reusable UI components
│   ├── Tag Helpers: <a asp-controller="Home" asp-action="Index">
│   │   ├── Built-in: Form, Input, Label, Validation, Select, Link, Script
│   │   └── Custom Tag Helpers: Inherit from TagHelper
│   ├── View Models: DTO between controller and view
│   ├── ViewData / ViewBag / TempData: Pass data to views (prefer ViewModels)
│   └── Sections: @section Scripts { ... }
├── Areas: Organize large MVC apps into functional areas
├── Razor Pages:
│   ├── Page-based model: .cshtml + .cshtml.cs (PageModel)
│   ├── Handlers: OnGet(), OnPost(), OnPostDeleteAsync()
│   ├── Routing: File-based (/Pages/Products/Index.cshtml → /Products)
│   ├── When to use: Page-focused apps, CRUD admin panels
│   └── Benefits: Simpler than MVC for page-based scenarios
└── API Controllers Best Practices:
    ├── Return ActionResult<T> for swagger documentation
    ├── Use [ProducesResponseType] for OpenAPI
    ├── Keep controllers thin: Delegate to services
    ├── Versioning: Asp.Versioning.Mvc package
    └── Consistent error responses: ProblemDetails
```

### Section 2.2.3 — Blazor
```
├── Hosting Models:
│   ├── Blazor Server:
│   │   ├── Logic runs on server, UI updates via SignalR
│   │   ├── Pros: Full .NET, Thin client, Fast initial load
│   │   ├── Cons: Latency, Scalability (SignalR connections), No offline
│   │   └── Use case: Internal apps, Low-latency requirements
│   ├── Blazor WebAssembly (WASM):
│   │   ├── .NET runs in browser via WebAssembly
│   │   ├── Pros: Offline capable, CDN hostable, No server needed
│   │   ├── Cons: Large download, Slower startup, Browser sandbox
│   │   └── Use case: PWAs, Client-heavy apps, Offline scenarios
│   ├── Blazor United / Auto (.NET 8+):
│   │   ├── Server-side rendering (SSR) + Interactive modes
│   │   ├── Per-component interactivity: @rendermode InteractiveServer/WASM/Auto
│   │   ├── Streaming Rendering: [StreamRendering]
│   │   └── Best of both worlds: Fast initial load + Rich interactivity
│   └── Blazor Hybrid (.NET MAUI):
│       ├── Blazor components inside native desktop/mobile apps
│       └── Use case: Cross-platform desktop apps with web UI
├── Component Model:
│   ├── .razor files: HTML + C# combined
│   ├── Parameters: [Parameter] public string Title { get; set; }
│   ├── Cascading Parameters: [CascadingParameter] for context propagation
│   ├── Event Callbacks: EventCallback<T>, @onclick, @onsubmit
│   ├── Component Lifecycle:
│   │   ├── OnInitialized / OnInitializedAsync
│   │   ├── OnParametersSet / OnParametersSetAsync
│   │   ├── OnAfterRender / OnAfterRenderAsync
│   │   ├── ShouldRender: Control re-rendering
│   │   └── Dispose: IDisposable / IAsyncDisposable
│   ├── State Management: Cascading values, DI services, Fluxor (Redux-like)
│   └── JS Interop: IJSRuntime.InvokeAsync<T>("jsFunction", args)
├── Forms & Validation:
│   ├── EditForm: Model binding, Validation
│   ├── InputText, InputNumber, InputDate, InputSelect
│   ├── DataAnnotationsValidator: Built-in validation
│   └── FluentValidation integration
└── Advanced:
    ├── Virtualization: <Virtualize> for large lists
    ├── Error Boundaries: <ErrorBoundary> graceful error handling
    ├── Lazy Loading: Assembly lazy loading for WASM
    ├── Authentication: AuthenticationStateProvider, [Authorize]
    └── Component Libraries: MudBlazor, Radzen, Syncfusion
```

---

## Module 2.3: Core Cross-Cutting Features

### Section 2.3.1 — Error Handling
```
├── Developer Exception Page: UseDeveloperExceptionPage() — Development only
├── Exception Handler Middleware:
│   ├── UseExceptionHandler("/error") — redirect to error page
│   ├── UseExceptionHandler(app => { }) — custom inline handler
│   └── app.UseStatusCodePagesWithReExecute("/error/{0}")
├── Problem Details (RFC 7807):
│   ├── builder.Services.AddProblemDetails()
│   ├── Standard properties: type, title, status, detail, instance
│   ├── Extensions: Custom properties for additional context
│   └── Consistent error format across APIs
├── IExceptionHandler (.NET 8+):
│   ├── Built-in interface for exception handling
│   ├── Chain multiple handlers
│   └── Return true to indicate handled, false to pass to next handler
├── Global Exception Filter:
│   ├── Implement IExceptionFilter
│   ├── Register globally: services.AddControllers(o => o.Filters.Add<...>())
│   └── Different from middleware: Only covers MVC pipeline
└── Best Practice:
    ├── Middleware for global error handling (API)
    ├── Exception filters for controller-specific handling
    ├── Problem Details for consistent error format
    ├── Log errors with correlation IDs
    └── NEVER expose stack traces in production
```

### Section 2.3.2 — Health Checks
```
├── Built-in:
│   ├── services.AddHealthChecks()
│   ├── app.MapHealthChecks("/health")
│   ├── Custom Health Checks: Implement IHealthCheck
│   └── Health Check UI: HealthChecksUI package
├── Database Health Checks:
│   ├── AddDbContextCheck<AppDbContext>()
│   ├── AddNpgSql() — PostgreSQL
│   ├── AddSqlServer() — SQL Server
│   └── AddRedis() — Redis
├── Custom Health Checks:
│   ├── External API availability
│   ├── Message broker connectivity
│   ├── Disk space
│   └── Custom business logic checks
├── Health Check Responses:
│   ├── Healthy, Degraded, Unhealthy
│   ├── Custom response writer: ResponseWriter = UIResponseWriter.WriteHealthCheckUIResponse
│   └── Tags: Filter health checks by tag
├── Kubernetes Integration:
│   ├── Liveness: /health/live — Is the process alive?
│   ├── Readiness: /health/ready — Can it handle requests?
│   └── Startup: /health/startup — Has it finished initializing?
└── Best Practice:
    ├── Separate liveness and readiness probes
    ├── Don't check external dependencies in liveness
    ├── Set appropriate timeouts
    └── Include health checks in load balancer configuration
```

### Section 2.3.3 — Static Files & File Uploads
```
├── Static Files:
│   ├── UseStaticFiles(): Serve from wwwroot/
│   ├── Custom paths: UseStaticFiles(new StaticFileOptions { FileProvider = ... })
│   ├── Directory Browsing: UseDirectoryBrowser() (disabled by default)
│   └── Default Files: UseDefaultFiles() (index.html)
├── File Uploads:
│   ├── IFormFile: Single file upload
│   ├── IFormFileCollection: Multiple files
│   ├── Streaming: For large files, Avoid buffering entire file in memory
│   ├── Size Limits: Configure Kestrel MaxRequestBodySize
│   ├── Validation: File type, Size, Content-Type checking
│   ├── Security: Never trust filename, Scan for malware, Store outside webroot
│   └── Storage: Local disk, Azure Blob, AWS S3, MinIO
├── File Downloads:
│   ├── File(): Return file as download
│   ├── PhysicalFile(): From file system path
│   ├── Content-Disposition: inline vs attachment
│   └── Streaming large files: FileStreamResult
└── Anti-patterns:
    ├── Storing files in database (usually bad for large files)
    ├── Trusting user-provided file names
    └── Not limiting upload size
```

---

## Module 2.4: Background Services & Scheduling

### Section 2.4.1 — Hosted Services
```
├── IHostedService:
│   ├── StartAsync(): Called when app starts
│   ├── StopAsync(): Called when app shuts down
│   └── Use case: Background initialization, cleanup
├── BackgroundService:
│   ├── Override ExecuteAsync(CancellationToken): Long-running loop
│   ├── Scoped Services: Create scope with IServiceScopeFactory
│   ├── Error Handling: Don't let exceptions crash the host
│   └── Graceful Shutdown: Respect CancellationToken
├── Periodic Tasks:
│   ├── PeriodicTimer (.NET 6+): Timer that respects async
│   ├── Pattern: while (!token.IsCancellationRequested) { await timer.WaitForNextTickAsync(); }
│   └── Don't use: System.Timers.Timer in ASP.NET Core (threading issues)
├── Queue-Based Background Processing:
│   ├── Channel<T> based work queue
│   ├── Producer: Enqueue work from request handler
│   ├── Consumer: BackgroundService dequeues and processes
│   └── Pattern: QueuedHostedService with Channel<Func<CancellationToken, Task>>
├── Libraries:
│   ├── Hangfire: Persistent job queue, Dashboard, Cron jobs, Retry
│   ├── Quartz.NET: Enterprise scheduler, Cron triggers, Job persistence
│   └── Wolverine: Messaging + Command bus + Saga support
└── Best Practices:
    ├── Always use IServiceScopeFactory for scoped services
    ├── Handle exceptions — don't crash the background service
    ├── Log extensively — background services are hard to debug
    ├── Monitor health of background services
    └── Use a persistent queue for important work (not in-memory)
```

---

> ### 🛠️ PHASE 2 PROJECT: **Blog Platform API + Razor Pages Admin**
> ```
> ┌─────────────────────────────────────────────────────────────────┐
> │           BLOG PLATFORM — API + ADMIN PANEL                     │
> ├─────────────────────────────────────────────────────────────────┤
> │                                                                 │
> │ Part A — RESTful API (Minimal APIs + Controllers):              │
> │  • Blog posts CRUD with Minimal APIs                            │
> │  • Comments CRUD with MVC Controllers                           │
> │  • Tags/Categories management                                   │
> │  • Search with pagination, sorting, filtering                   │
> │  • Image upload endpoint (store in local disk + serve)          │
> │  • RSS feed endpoint                                            │
> │  • Rate limiting: 100 requests/minute per IP                    │
> │                                                                 │
> │ Part B — Admin Panel (Razor Pages):                             │
> │  • Dashboard: Post count, Comment count, Recent activity        │
> │  • CRUD pages for posts (rich text editor)                      │
> │  • Comment moderation panel                                     │
> │  • Tag/Category management                                      │
> │  • Simple login page (cookie auth for admin)                    │
> │                                                                 │
> │ Part C — Background Services:                                   │
> │  • Scheduled task: Generate daily sitemap.xml                   │
> │  • Queue-based: Image thumbnail generation on upload            │
> │  • Periodic: Clean up orphaned images every hour                │
> │                                                                 │
> │ Technical Requirements:                                         │
> │  ✅ Middleware: Request logging, Correlation ID, Error handling   │
> │  ✅ Health checks: Database, Disk space                          │
> │  ✅ OpenAPI/Swagger documentation                                │
> │  ✅ Problem Details for all error responses                      │
> │  ✅ FluentValidation for all inputs                              │
> │  ✅ Serilog: Structured logging to console + file                │
> │  ✅ Options pattern for configuration                            │
> │  ✅ Response caching for GET endpoints                           │
> │  ✅ Custom middleware: Request timing header                     │
> └─────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 🌐 PHASE 3: API DEVELOPMENT & COMMUNICATION
### 📅 Duration: Months 5–7
### 🎯 Goal: Build production-grade APIs with multiple communication protocols
### 👤 Level: Mid-Level Developer

---

## Module 3.1: RESTful API Design & Best Practices

### Section 3.1.1 — REST API Design
```
├── Resource Naming:
│   ├── Nouns, not verbs: /api/products (not /api/getProducts)
│   ├── Plural: /api/products, /api/orders
│   ├── Nested: /api/orders/{orderId}/items
│   ├── Kebab-case: /api/order-items
│   └── Avoid deep nesting: Max 2 levels
├── HTTP Methods:
│   ├── GET: Read (idempotent, cacheable)
│   ├── POST: Create (not idempotent)
│   ├── PUT: Full update/replace (idempotent)
│   ├── PATCH: Partial update (JSON Patch / JSON Merge Patch)
│   ├── DELETE: Remove (idempotent)
│   ├── HEAD: Same as GET without body
│   └── OPTIONS: CORS preflight, Discovery
├── Status Codes:
│   ├── 200 OK: Successful GET/PUT/PATCH
│   ├── 201 Created: Successful POST (+ Location header)
│   ├── 204 No Content: Successful DELETE
│   ├── 400 Bad Request: Validation errors
│   ├── 401 Unauthorized: Not authenticated
│   ├── 403 Forbidden: Authenticated but not authorized
│   ├── 404 Not Found: Resource doesn't exist
│   ├── 409 Conflict: Concurrency conflict
│   ├── 422 Unprocessable Entity: Semantic validation error
│   ├── 429 Too Many Requests: Rate limited
│   └── 500 Internal Server Error: Unhandled exception
├── Pagination:
│   ├── Offset-based: ?page=2&pageSize=20 (simple, skip issues at scale)
│   ├── Cursor-based: ?cursor=abc123&limit=20 (better for large datasets)
│   ├── Response: { data: [...], pagination: { page, pageSize, totalCount, totalPages } }
│   └── Keyset pagination: WHERE id > @lastId ORDER BY id LIMIT 20 (most performant)
├── Filtering & Sorting:
│   ├── Filtering: ?status=active&category=electronics&minPrice=10
│   ├── Sorting: ?sortBy=price&sortOrder=desc
│   ├── Complex: ?filter=price gt 10 and status eq 'active' (OData style)
│   └── Libraries: Sieve, OData, Gridify
├── HATEOAS (Level 3 REST):
│   ├── Include links in responses: { "self": "/api/products/1", "update": "..." }
│   └── Rarely implemented in practice, But useful for discoverability
├── API Versioning:
│   ├── URL Path: /api/v1/products (most common, clear)
│   ├── Query String: /api/products?api-version=1.0
│   ├── Header: api-version: 1.0
│   ├── Media Type: Accept: application/json;v=1.0
│   ├── Library: Asp.Versioning.Mvc / Asp.Versioning.Http
│   └── Deprecation: Sunset header, Deprecation notices
└── API Documentation:
    ├── OpenAPI/Swagger: Swashbuckle or NSwag
    ├── .NET 9+: Built-in OpenAPI support (Microsoft.AspNetCore.OpenApi)
    ├── XML Comments: /// <summary> for descriptions
    ├── Examples: SwaggerRequestExample, SwaggerResponseExample
    └── Redoc: Alternative to Swagger UI
```

### Section 3.1.2 — API Patterns in ASP.NET Core
```
├── Request/Response Pipeline:
│   ├── Controller → MediatR (or direct) → Service → Repository
│   ├── DTOs: Never expose domain entities directly
│   ├── Mapping: AutoMapper, Mapster, or manual mapping
│   │   ├── AutoMapper: Profile-based, Convention-based
│   │   ├── Mapster: Faster, Code generation support
│   │   └── Manual: Most control, No hidden magic (recommended for critical paths)
│   └── Result Pattern: Return Result<T> from services, Map to ActionResult in controller
├── CQRS with MediatR:
│   ├── Commands: IRequest<TResponse> — change state
│   ├── Queries: IRequest<TResponse> — read state
│   ├── Handlers: IRequestHandler<TRequest, TResponse>
│   ├── Notifications: INotification — domain events
│   ├── Pipeline Behaviors: IPipelineBehavior<TRequest, TResponse>
│   │   ├── Validation Behavior: Validate request before handler
│   │   ├── Logging Behavior: Log request/response
│   │   ├── Performance Behavior: Track slow requests
│   │   └── Transaction Behavior: Wrap handler in transaction
│   └── Benefits: Separation of read/write, Clean handlers, Cross-cutting via behaviors
├── Vertical Slice Architecture:
│   ├── Organize by feature, not by layer
│   ├── Each feature: Request → Handler → Response (all in one folder)
│   ├── Benefits: High cohesion, Minimal coupling between features
│   └── Libraries: MediatR, Carter, FastEndpoints
├── FastEndpoints:
│   ├── Alternative to Minimal APIs + MediatR
│   ├── REPR Pattern: Request → Endpoint → Response
│   ├── Built-in: Validation, Mapping, Pre/Post processors
│   ├── Performance: Faster than MVC controllers
│   └── When to use: Performance-critical APIs, Clean structure
└── Output Caching (.NET 7+):
    ├── builder.Services.AddOutputCache()
    ├── [OutputCache(Duration = 60)]
    ├── Cache Policies: By query string, By header, By route
    ├── Cache Invalidation: Tag-based eviction
    └── Redis-backed: Microsoft.Extensions.Caching.StackExchangeRedis
```

---

## Module 3.2: GraphQL in ASP.NET Core

### Section 3.2.1 — GraphQL with Hot Chocolate
```
├── Setup:
│   ├── builder.Services.AddGraphQLServer()
│   ├── .AddQueryType<Query>() / .AddMutationType<Mutation>()
│   ├── app.MapGraphQL("/graphql")
│   └── Banana Cake Pop: Built-in IDE
├── Schema Design:
│   ├── Query Types: [UseProjection], [UseFiltering], [UseSorting]
│   ├── Mutations: Input types, Payload types
│   ├── Subscriptions: Real-time via WebSocket
│   ├── Type Extensions: Split type definitions across files
│   └── Relay: Global object identification, Connections (cursor pagination)
├── Data Loading:
│   ├── DataLoader: Batch and cache data fetching (N+1 prevention)
│   ├── Batch DataLoader: Load by IDs
│   ├── Group DataLoader: Load related data in groups
│   └── Integration: EF Core projections, IQueryable
├── Security:
│   ├── [Authorize] per field/type
│   ├── Query Depth Limiting: Prevent deeply nested queries
│   ├── Query Complexity Analysis: Cost per field
│   └── Introspection: Disable in production
├── Performance:
│   ├── Projections: Only query needed columns from DB
│   ├── Persisted Queries: Precompile and cache queries
│   └── Response Caching: @cacheControl directive
└── When to use:
    ├── Complex frontend data requirements
    ├── Multiple client types (web, mobile, IoT)
    └── When over-fetching/under-fetching is a real problem
```

---

## Module 3.3: gRPC in ASP.NET Core

### Section 3.3.1 — gRPC Services
```
├── Protocol Buffers (.proto files):
│   ├── Service definition: service Greeter { rpc SayHello (...) returns (...); }
│   ├── Message definition: message HelloRequest { string name = 1; }
│   ├── Scalar types: string, int32, int64, bool, bytes, double
│   ├── Enums, Oneof, Maps, Repeated (arrays)
│   └── Code generation: dotnet-grpc, Grpc.Tools NuGet
├── Communication Patterns:
│   ├── Unary: Single request → Single response (like REST)
│   ├── Server Streaming: Single request → Stream of responses
│   ├── Client Streaming: Stream of requests → Single response
│   └── Bidirectional Streaming: Stream ↔ Stream (real-time)
├── Implementation:
│   ├── Server: Inherit from generated base class
│   ├── Client: Use generated client class (GrpcChannel.ForAddress)
│   ├── Interceptors: Client-side and Server-side (like middleware)
│   ├── Deadlines: Set timeout per call
│   ├── Cancellation: CancellationToken support
│   └── Error Handling: Status codes (OK, NotFound, Internal, etc.)
├── ASP.NET Core Integration:
│   ├── builder.Services.AddGrpc()
│   ├── app.MapGrpcService<GreeterService>()
│   ├── Health checks: Grpc.HealthCheck
│   ├── Reflection: Grpc.AspNetCore.Server.Reflection (for tooling)
│   └── JSON Transcoding: gRPC-JSON transcoding (expose gRPC as REST)
├── gRPC-Web:
│   ├── Enable gRPC from browser clients
│   ├── app.UseGrpcWeb(), .EnableGrpcWeb()
│   └── Blazor WASM → gRPC-Web → Backend
├── Performance:
│   ├── Binary serialization (7-10x faster than JSON)
│   ├── HTTP/2 multiplexing
│   ├── Connection pooling: Reuse gRPC channels
│   └── Keep-alive: Configure HTTP/2 keepalive pings
└── When to use:
    ├── Internal service-to-service communication
    ├── Low-latency requirements
    ├── Streaming data (real-time updates, file transfer)
    └── Polyglot environments (strong contracts across languages)
```

---

## Module 3.4: Real-Time Communication (SignalR)

### Section 3.4.1 — SignalR
```
├── Concepts:
│   ├── Hub: Server-side endpoint for client communication
│   ├── Connections: Each client has a unique connection ID
│   ├── Groups: Organize connections into groups
│   ├── Strongly-Typed Hubs: Hub<IClientInterface> — type-safe client calls
│   └── Transport Negotiation: WebSocket → SSE → Long Polling (auto fallback)
├── Server Setup:
│   ├── builder.Services.AddSignalR()
│   ├── app.MapHub<ChatHub>("/chatHub")
│   ├── Hub Methods: public async Task SendMessage(string message)
│   ├── Sending to clients:
│   │   ├── Clients.All.ReceiveMessage(msg): Broadcast
│   │   ├── Clients.Caller.ReceiveMessage(msg): Only sender
│   │   ├── Clients.Others.ReceiveMessage(msg): Everyone except sender
│   │   ├── Clients.Group("room").ReceiveMessage(msg): Group members
│   │   └── Clients.User("userId").ReceiveMessage(msg): Specific user
│   └── Outside Hub: IHubContext<ChatHub> injected into services
├── Client Libraries:
│   ├── JavaScript: @microsoft/signalr
│   ├── .NET: Microsoft.AspNetCore.SignalR.Client
│   └── Others: Java, Python (community)
├── Scaling:
│   ├── Redis Backplane: AddStackExchangeRedis() — sync across servers
│   ├── Azure SignalR Service: Managed, Serverless mode
│   ├── Sticky Sessions: Required without backplane
│   └── MessagePack Protocol: Binary, Faster than JSON
├── Authentication:
│   ├── Bearer token via query string (WebSocket doesn't support headers)
│   ├── Cookie-based: Automatic
│   ├── [Authorize] on Hub or Hub methods
│   └── Context.User: Access authenticated user in Hub
├── Advanced:
│   ├── Streaming: IAsyncEnumerable from Hub to client
│   ├── Client Streaming: Client sends stream to Hub
│   ├── Automatic Reconnection: .withAutomaticReconnect()
│   ├── Hub Filters: IHubFilter — before/after Hub method execution
│   └── Connection Lifetime Events: OnConnectedAsync, OnDisconnectedAsync
└── Use Cases:
    ├── Chat applications
    ├── Live dashboards and notifications
    ├── Collaborative editing
    ├── Real-time gaming
    ├── Live progress indicators
    └── Auction/bidding systems
```

---

## Module 3.5: Reverse Proxy & API Gateway

### Section 3.5.1 — YARP (Yet Another Reverse Proxy)
```
├── What: Microsoft's reverse proxy library built on ASP.NET Core
├── Configuration:
│   ├── Routes: Path matching, Headers, Query strings
│   ├── Clusters: Backend service groups
│   ├── Load Balancing: RoundRobin, LeastRequests, Random, PowerOfTwoChoices
│   ├── Health Checks: Active and Passive
│   └── Configuration from: appsettings.json, Code, External source (dynamic)
├── Transforms:
│   ├── Request: Add/Remove headers, Path prefix, Query string
│   ├── Response: Add/Remove headers
│   └── Custom: Implement ITransformProvider
├── Features:
│   ├── Session Affinity: Sticky sessions via cookie
│   ├── Rate Limiting: Integration with .NET rate limiter
│   ├── Authentication/Authorization: Standard ASP.NET Core
│   ├── Caching: Response caching
│   └── WebSocket Proxying: Transparent WebSocket forwarding
├── Use Cases:
│   ├── API Gateway for microservices
│   ├── BFF (Backend for Frontend)
│   ├── Load balancer
│   └── Legacy system migration (Strangler Fig)
└── vs Other Proxies:
    ├── YARP: .NET native, Programmable, Middleware integration
    ├── NGINX: Battle-tested, Config-based, C-based
    ├── Envoy: Service mesh, xDS API, CNCF
    └── Kong: Plugin ecosystem, API management
```

---

> ### 🛠️ PHASE 3 PROJECT: **Real-Time Chat Application with API**
> ```
> ┌─────────────────────────────────────────────────────────────────┐
> │          REAL-TIME CHAT APPLICATION                              │
> ├─────────────────────────────────────────────────────────────────┤
> │                                                                 │
> │ REST API:                                                       │
> │  • User registration/login (JWT-based)                          │
> │  • Chat room CRUD (create, join, leave, list members)           │
> │  • Message history with cursor-based pagination                 │
> │  • File/image sharing (upload to local storage)                 │
> │  • User profile management                                      │
> │  • API versioning: v1 with URL path strategy                    │
> │  • Full OpenAPI documentation                                   │
> │                                                                 │
> │ GraphQL:                                                        │
> │  • Query: rooms, messages, users (with DataLoaders)             │
> │  • Mutation: sendMessage, createRoom                            │
> │  • Subscription: onMessageReceived (real-time via WebSocket)    │
> │                                                                 │
> │ gRPC:                                                           │
> │  • Internal service: Message storage/retrieval                  │
> │  • Server streaming: Live message feed                          │
> │                                                                 │
> │ SignalR:                                                        │
> │  • Real-time messaging hub                                      │
> │  • Typing indicators                                            │
> │  • Online/offline presence                                      │
> │  • Group-based rooms                                            │
> │  • Redis backplane for multi-instance scaling                   │
> │  • MessagePack protocol for performance                         │
> │                                                                 │
> │ Architecture:                                                   │
> │  ✅ CQRS with MediatR (Commands + Queries separated)             │
> │  ✅ Pipeline behaviors: Validation, Logging, Performance          │
> │  ✅ Vertical slice organization (folder per feature)              │
> │  ✅ AutoMapper for DTO mapping                                    │
> │  ✅ YARP: Reverse proxy routing REST/GraphQL/SignalR              │
> │  ✅ Output caching for message history                            │
> │  ✅ Rate limiting per user                                        │
> └─────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 🗄️ PHASE 4: DATA ACCESS & DATABASE PATTERNS
### 📅 Duration: Months 7–9
### 🎯 Goal: Master Entity Framework Core and advanced data patterns
### 👤 Level: Mid-Level Developer

---

## Module 4.1: Entity Framework Core (Deep Dive)

### Section 4.1.1 — EF Core Fundamentals
```
├── DbContext:
│   ├── Lifetime: Scoped (one per request in ASP.NET Core)
│   ├── DbSet<T>: Entry point for querying/saving entities
│   ├── OnModelCreating: Fluent API configuration
│   ├── SaveChanges / SaveChangesAsync: Persist tracked changes
│   └── DbContext Pooling: AddDbContextPool<T>() — reuse instances
├── Configuration Approaches:
│   ├── Data Annotations: [Table], [Key], [Required], [MaxLength], [Column]
│   ├── Fluent API (preferred): modelBuilder.Entity<Product>().HasKey(p => p.Id)
│   ├── IEntityTypeConfiguration<T>: Separate config per entity (clean)
│   └── Conventions: Default behaviors (Id → Primary Key, etc.)
├── Relationships:
│   ├── One-to-Many: HasMany().WithOne() + ForeignKey
│   ├── One-to-One: HasOne().WithOne() + ForeignKey
│   ├── Many-to-Many: HasMany().WithMany() (implicit join table EF 5+)
│   ├── Self-referencing: Employee → Manager relationship
│   ├── Navigation Properties: Reference navigation, Collection navigation
│   ├── Cascade Delete: DeleteBehavior.Cascade/Restrict/SetNull/NoAction
│   └── Shadow Properties: Properties only in EF model, Not in entity class
├── Migrations:
│   ├── dotnet ef migrations add <Name>
│   ├── dotnet ef database update
│   ├── dotnet ef migrations remove
│   ├── dotnet ef migrations script: Generate SQL script
│   ├── Migration Bundles: dotnet ef migrations bundle (self-contained executable)
│   ├── Idempotent Scripts: --idempotent flag
│   ├── Data Seeding: HasData() in OnModelCreating
│   └── Best Practices:
│       ├── Small, focused migrations
│       ├── Never edit applied migrations
│       ├── Review generated SQL before applying to production
│       └── Use migration bundles for CI/CD
├── Value Conversions:
│   ├── HasConversion<TProvider>(): Store value objects as primitives
│   ├── Built-in: Enum → string, DateTime → DateTimeOffset
│   ├── Custom: Money → decimal, Email → string
│   └── Value Comparers: For complex types in change tracking
└── Owned Types:
    ├── Value Objects as owned types: OwnsOne(p => p.Address)
    ├── Table splitting: Same table, Different types
    └── OwnsMany: Collection of owned types (JSON column in EF 7+)
```

### Section 4.1.2 — Querying
```
├── LINQ to Entities:
│   ├── Translates LINQ to SQL queries
│   ├── IQueryable<T>: Deferred, Composable, Server-evaluated
│   ├── vs IEnumerable<T>: Client-evaluated (avoid for large datasets)
│   └── Always inspect generated SQL: .ToQueryString()
├── Loading Strategies:
│   ├── Eager Loading: .Include(p => p.Orders).ThenInclude(o => o.Items)
│   ├── Explicit Loading: context.Entry(product).Collection(p => p.Orders).Load()
│   ├── Lazy Loading: Proxies (avoid — N+1 trap)
│   ├── Split Queries: .AsSplitQuery() — avoid cartesian explosion
│   └── Filtered Include: .Include(p => p.Orders.Where(o => o.IsActive))
├── Projections:
│   ├── Select: .Select(p => new ProductDto { Name = p.Name, Price = p.Price })
│   ├── AutoMapper ProjectTo: queryable.ProjectTo<ProductDto>(mapper.ConfigurationProvider)
│   └── Anonymous Types: .Select(p => new { p.Name, OrderCount = p.Orders.Count })
├── Tracking:
│   ├── .AsNoTracking(): Read-only queries (faster)
│   ├── .AsNoTrackingWithIdentityResolution(): No tracking but dedup
│   ├── Default: Tracking enabled (needed for SaveChanges)
│   └── Global: context.ChangeTracker.QueryTrackingBehavior = NoTracking
├── Raw SQL:
│   ├── FromSqlRaw: DbSet<T>.FromSqlRaw("SELECT * FROM Products WHERE ...")
│   ├── FromSqlInterpolated: Safe parameterized queries
│   ├── ExecuteSql: Non-query operations (UPDATE, DELETE)
│   └── SqlQuery<T> (EF 8+): Arbitrary SQL returning any type
├── Global Query Filters:
│   ├── modelBuilder.Entity<Product>().HasQueryFilter(p => !p.IsDeleted)
│   ├── Soft Delete: Automatic filtering of deleted records
│   ├── Multi-tenancy: Automatic tenant filtering
│   └── Ignoring: .IgnoreQueryFilters() when needed
├── Compiled Queries:
│   ├── EF.CompileQuery: Pre-compile for repeated queries
│   ├── EF.CompileAsyncQuery: Async version
│   └── Performance: Avoid LINQ translation overhead on hot paths
├── Bulk Operations (EF 7+):
│   ├── ExecuteUpdate: Bulk UPDATE without loading entities
│   ├── ExecuteDelete: Bulk DELETE without loading entities
│   └── Example: .Where(p => p.Price < 5).ExecuteDeleteAsync()
└── Common Performance Issues:
    ├── N+1 Queries: Use Include() or projections
    ├── Cartesian Explosion: Use SplitQuery
    ├── Loading entire entities: Use Select() projections
    ├── Missing indexes: Analyze query plans
    ├── Too many round trips: Batch operations
    └── Client evaluation: Watch for LINQ translated to C# (logs warn)
```

### Section 4.1.3 — Advanced EF Core
```
├── Interceptors:
│   ├── SaveChangesInterceptor: Before/after save (audit logging, soft delete)
│   ├── DbCommandInterceptor: Before/after SQL execution (logging, query hints)
│   ├── DbConnectionInterceptor: Connection lifecycle
│   └── Use case: Audit trails, Multi-tenancy, Performance logging
├── Concurrency Control:
│   ├── Optimistic: [ConcurrencyCheck] or IsRowVersion()
│   ├── PostgreSQL: xmin system column as concurrency token
│   ├── SQL Server: rowversion / timestamp
│   ├── DbUpdateConcurrencyException: Handle conflicts
│   └── Conflict Resolution: Client wins, Database wins, Merge
├── JSON Columns (EF 7+):
│   ├── .ToJson(): Map complex types to JSON column
│   ├── Querying: LINQ translates to JSON path queries
│   ├── Use case: Flexible metadata, Denormalized data, Value objects
│   └── Database support: PostgreSQL (jsonb), SQL Server (nvarchar with JSON)
├── Table Splitting & Entity Splitting:
│   ├── Table Splitting: Multiple entities → One table
│   ├── Entity Splitting: One entity → Multiple tables
│   └── Use case: Large tables, Lazy-load specific columns
├── Temporal Tables (EF 6+):
│   ├── Automatic history tracking
│   ├── .IsTemporalAll(), .IsTemporalAsOf(date)
│   ├── .IsTemporalBetween(start, end)
│   └── Database support: SQL Server, PostgreSQL (TimescaleDB)
├── Value Objects with EF Core:
│   ├── Owned types: OwnsOne() for single value objects
│   ├── Complex types (EF 8+): Better value object support
│   ├── Value converters: Primitive storage of complex types
│   └── Private setters: Enforce immutability
├── Database Providers:
│   ├── Npgsql.EntityFrameworkCore.PostgreSQL (PostgreSQL)
│   ├── Microsoft.EntityFrameworkCore.SqlServer (SQL Server)
│   ├── Microsoft.EntityFrameworkCore.Sqlite (SQLite)
│   ├── Pomelo.EntityFrameworkCore.MySql (MySQL/MariaDB)
│   └── MongoDB EF Core Provider (EF 8+)
└── Multiple DbContexts:
    ├── Separate contexts per bounded context
    ├── Shared database, Different schemas
    └── Cross-context transactions: TransactionScope (use carefully)
```

---

## Module 4.2: Dapper & Alternative Data Access

### Section 4.2.1 — Dapper (Micro-ORM)
```
├── Core API:
│   ├── Query<T>: SELECT queries → mapped objects
│   ├── QueryFirst<T> / QuerySingle<T>: Single result
│   ├── Execute: INSERT/UPDATE/DELETE (returns affected rows)
│   ├── QueryMultiple: Multiple result sets in one query
│   └── Parameters: Anonymous objects, DynamicParameters
├── Advanced:
│   ├── Multi-Mapping: JOIN queries → multiple objects
│   ├── Stored Procedures: CommandType.StoredProcedure
│   ├── Buffered vs Unbuffered: buffered: false for streaming
│   ├── Custom Type Handlers: SqlMapper.AddTypeHandler
│   ├── Bulk Insert: Dapper.Contrib or manual batching
│   └── Transaction: connection.BeginTransaction()
├── Dapper + Repository Pattern:
│   ├── Clean interface: IProductRepository
│   ├── Dapper implementation: Full SQL control
│   └── Testing: Testcontainers with real database
├── When to use Dapper:
│   ├── Performance-critical queries
│   ├── Complex SQL that's hard to express in LINQ
│   ├── Read-side of CQRS
│   ├── Reporting queries
│   └── When you want full SQL control
└── EF Core + Dapper Together:
    ├── EF Core for write operations (change tracking, migrations)
    ├── Dapper for read operations (performance, complex queries)
    └── Share the same connection: context.Database.GetDbConnection()
```

---

## Module 4.3: Caching in ASP.NET Core

### Section 4.3.1 — Caching Strategies
```
├── In-Memory Cache:
│   ├── IMemoryCache: services.AddMemoryCache()
│   ├── Set/Get/Remove: _cache.Set("key", value, options)
│   ├── Expiration: Absolute, Sliding, Callback on eviction
│   ├── Size limits: Set maximum cache size
│   ├── Cache-Aside Pattern: Check cache → Miss → Load from DB → Store in cache
│   └── When to use: Single-instance apps, Small datasets, Session data
├── Distributed Cache:
│   ├── IDistributedCache: Abstraction for distributed caching
│   ├── Redis: AddStackExchangeRedisCache()
│   │   ├── Cluster mode: Multiple shards
│   │   ├── Sentinel: High availability
│   │   ├── Pub/Sub: For cache invalidation events
│   │   └── Data types: Leverage Redis data structures
│   ├── SQL Server: AddDistributedSqlServerCache()
│   ├── NCache: AddNCacheDistributedCache()
│   └── When to use: Multi-instance apps, Large datasets, Shared state
├── Output Caching (.NET 7+):
│   ├── services.AddOutputCache(o => { o.AddPolicy("CacheFor60s", p => p.Expire(TimeSpan.FromSeconds(60))); })
│   ├── [OutputCache(PolicyName = "CacheFor60s")]
│   ├── Vary by: Query string, Header, Route value
│   ├── Tag-based eviction: Invalidate by tag
│   └── Custom policies: Implement IOutputCachePolicy
├── Response Caching:
│   ├── [ResponseCache]: Set Cache-Control headers
│   ├── UseResponseCaching(): Middleware (limited, prefer Output Caching)
│   └── VaryByHeader, VaryByQueryKeys
├── Hybrid Cache (.NET 9+):
│   ├── HybridCache: L1 (in-memory) + L2 (distributed) automatic
│   ├── Stampede protection: Built-in (only one cache miss query)
│   ├── Tag-based invalidation
│   └── Serialization: System.Text.Json or MessagePack
├── Cache Patterns:
│   ├── Cache-Aside: Most common, Manual cache management
│   ├── Cache-Through: Cache manages DB reads transparently
│   ├── Write-Behind: Write to cache, Async write to DB
│   └── Refresh-Ahead: Pre-populate before expiry
└── Cache Invalidation:
    ├── TTL (Time-To-Live): Simplest, Eventually consistent
    ├── Event-Based: Publish invalidation event on data change
    ├── Version-Based: Include version in cache key
    └── Change Token: IChangeToken for configuration/file changes
```

---

## Module 4.4: Repository & Unit of Work Patterns

### Section 4.4.1 — Patterns Implementation
```
├── Generic Repository (Controversial):
│   ├── IRepository<T>: CRUD interface
│   ├── Pros: Consistent API, Testable
│   ├── Cons: Leaks persistence concerns, Lowest common denominator
│   └── Recommendation: Prefer specific repositories per aggregate
├── Specific Repositories:
│   ├── IOrderRepository: Domain-specific methods
│   │   ├── GetByIdWithItems(OrderId id)
│   │   ├── GetActiveOrdersForCustomer(CustomerId customerId)
│   │   └── GetOrdersForShipping(DateRange range)
│   ├── Implementation: Uses EF Core or Dapper internally
│   └── Benefits: Domain language, Optimized queries, Testable
├── Unit of Work:
│   ├── DbContext IS a Unit of Work: SaveChanges = commit
│   ├── Explicit UoW: IUnitOfWork with SaveChangesAsync()
│   ├── Transaction per request: Middleware-based
│   └── Cross-aggregate transactions: Domain events + Outbox
├── Specification Pattern:
│   ├── Encapsulate query logic in reusable objects
│   ├── Libraries: Ardalis.Specification
│   ├── Example: ActiveProductsSpec, ProductsByPriceRangeSpec
│   └── Composable: CombineWith(), And(), Or()
└── Domain Events with EF Core:
    ├── Collect events in aggregate: _domainEvents.Add(new OrderPlaced(this))
    ├── Dispatch before/after SaveChanges: Override SaveChangesAsync
    ├── MediatR integration: INotification for domain events
    └── Outbox Pattern: Store events in DB → Background service dispatches
```

---

> ### 🛠️ PHASE 4 PROJECT: **E-Commerce Product Catalog + Order System**
> ```
> ┌─────────────────────────────────────────────────────────────────┐
> │       E-COMMERCE PRODUCT CATALOG + ORDER SYSTEM                 │
> ├─────────────────────────────────────────────────────────────────┤
> │                                                                 │
> │ Domain Model (DDD Tactical):                                    │
> │  • Product Aggregate: Product, Variant, Image (Value Object)   │
> │  • Order Aggregate: Order, OrderItem, Money (Value Object)     │
> │  • Customer Aggregate: Customer, Address (Value Object)        │
> │  • Catalog Bounded Context + Order Bounded Context             │
> │                                                                 │
> │ EF Core Features:                                               │
> │  ✅ Fluent API configuration (IEntityTypeConfiguration)          │
> │  ✅ Value Objects as Owned Types + Value Conversions             │
> │  ✅ JSON columns for product metadata (EF 7+)                   │
> │  ✅ Global Query Filters: Soft delete + Multi-tenancy            │
> │  ✅ Optimistic concurrency with row version                      │
> │  ✅ Interceptors: Audit logging (CreatedAt, UpdatedBy)           │
> │  ✅ Compiled queries for hot paths                               │
> │  ✅ Bulk operations: ExecuteUpdate/ExecuteDelete                  │
> │  ✅ Split queries for complex includes                           │
> │  ✅ Migrations with seed data                                    │
> │                                                                 │
> │ Data Access Patterns:                                           │
> │  ✅ EF Core for writes (Order creation, Product management)      │
> │  ✅ Dapper for reads (Product search, Order reports)              │
> │  ✅ Specification pattern: Ardalis.Specification                  │
> │  ✅ Domain Events: OrderPlaced → Update inventory (MediatR)      │
> │  ✅ Outbox pattern: Reliable event publishing                    │
> │                                                                 │
> │ Caching:                                                        │
> │  ✅ Redis distributed cache for product catalog                  │
> │  ✅ In-memory cache for categories (rarely changes)              │
> │  ✅ Output caching for product listing endpoints                 │
> │  ✅ Cache invalidation on product update (event-based)           │
> │                                                                 │
> │ Database:                                                       │
> │  ✅ PostgreSQL with proper indexes                               │
> │  ✅ Full-text search using GIN indexes                           │
> │  ✅ Database per bounded context (separate schemas)              │
> └─────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 🛡️ PHASE 5: SECURITY & IDENTITY
### 📅 Duration: Months 9–11
### 🎯 Goal: Implement production-grade authentication, authorization, and security
### 👤 Level: Mid-Senior Developer

---

## Module 5.1: Authentication

### Section 5.1.1 — ASP.NET Core Identity
```
├── Setup:
│   ├── services.AddIdentity<ApplicationUser, IdentityRole>()
│   ├── .AddEntityFrameworkStores<AppDbContext>()
│   ├── .AddDefaultTokenProviders()
│   └── Custom User: Extend IdentityUser with additional properties
├── Features:
│   ├── User Registration: UserManager.CreateAsync()
│   ├── Login: SignInManager.PasswordSignInAsync()
│   ├── Password Hashing: PBKDF2 (default), Can customize
│   ├── Email Confirmation: GenerateEmailConfirmationTokenAsync()
│   ├── Password Reset: GeneratePasswordResetTokenAsync()
│   ├── Two-Factor Authentication: TOTP authenticator apps
│   ├── Account Lockout: After N failed attempts
│   ├── External Login: Google, Microsoft, Facebook, GitHub
│   └── Security Stamp: Invalidate sessions on security changes
├── Configuration:
│   ├── Password Policy: Length, Complexity, History
│   ├── Lockout Policy: Duration, Max failed attempts
│   ├── User Policy: Require unique email, Allowed characters
│   └── Token Policy: Token lifespan
├── Customization:
│   ├── Custom UserStore: Implement IUserStore<T>
│   ├── Custom Password Hasher: IPasswordHasher<T>
│   ├── Custom User Validator: IUserValidator<T>
│   └── Custom Token Provider: IUserTwoFactorTokenProvider<T>
└── Identity API Endpoints (.NET 8+):
    ├── app.MapIdentityApi<ApplicationUser>()
    ├── Built-in: /register, /login, /refresh, /confirmEmail, etc.
    └── Customizable: Override specific endpoints
```

### Section 5.1.2 — JWT Authentication
```
├── Setup:
│   ├── services.AddAuthentication(JwtBearerDefaults.AuthenticationScheme)
│   │   .AddJwtBearer(options => { ... })
│   ├── Token Validation Parameters:
│   │   ├── ValidateIssuer, ValidIssuer
│   │   ├── ValidateAudience, ValidAudience
│   │   ├── ValidateLifetime
│   │   ├── ValidateIssuerSigningKey, IssuerSigningKey
│   │   └── ClockSkew: TimeSpan.Zero (default is 5 minutes!)
│   └── Key Management: Symmetric (HMAC) vs Asymmetric (RSA/EC)
├── Token Generation:
│   ├── Claims: UserId, Email, Roles, Custom claims
│   ├── SecurityTokenDescriptor: Issuer, Audience, Expiry, SigningCredentials
│   ├── JwtSecurityTokenHandler.CreateToken()
│   └── Short-lived Access Tokens (15-30 min) + Long-lived Refresh Tokens
├── Refresh Tokens:
│   ├── Generate: Random secure token, Store in database
│   ├── Rotation: Issue new refresh token on each refresh
│   ├── Revocation: Delete/invalidate on logout
│   ├── Expiry: 7-30 days (configurable)
│   └── Family Detection: Detect reuse → Revoke entire family
├── Token Revocation:
│   ├── Problem: JWTs are stateless — can't invalidate
│   ├── Short Expiry: Minimize window of validity
│   ├── Token Blacklist: Redis set of revoked JTI (token ID)
│   ├── Security Stamp: Include in claims, Validate against DB
│   └── Reference Tokens: Opaque tokens, Introspection endpoint (IdentityServer)
└── Best Practices:
    ├── Store in HttpOnly cookies (web apps) or Memory (SPAs, avoid localStorage)
    ├── Always use HTTPS
    ├── Include minimal claims (keep token small)
    ├── Use asymmetric keys for multi-service validation
    └── Implement token refresh before expiry (client-side)
```

### Section 5.1.3 — OAuth 2.0 & OpenID Connect
```
├── OAuth 2.0 Flows:
│   ├── Authorization Code + PKCE: Web apps, Mobile, SPAs (recommended)
│   ├── Client Credentials: Service-to-service (machine-to-machine)
│   ├── Device Authorization: Smart TV, IoT devices
│   └── Deprecated: Implicit, Resource Owner Password
├── OpenID Connect (OIDC):
│   ├── Identity layer on top of OAuth 2.0
│   ├── ID Token: JWT containing user identity
│   ├── UserInfo endpoint: Additional user claims
│   └── Discovery: .well-known/openid-configuration
├── Identity Providers:
│   ├── Duende IdentityServer: .NET-native, Self-hosted (commercial license)
│   ├── OpenIddict: Free, Open-source, Built on ASP.NET Core
│   ├── Auth0: Cloud-hosted, Easy integration
│   ├── Azure AD / Entra ID: Microsoft enterprise
│   ├── Keycloak: Open-source, Self-hosted (Java-based)
│   └── AWS Cognito: AWS-native
├── ASP.NET Core Integration:
│   ├── .AddOpenIdConnect(): OIDC client configuration
│   ├── .AddOAuth(): Generic OAuth 2.0
│   ├── External providers: AddGoogle(), AddMicrosoftAccount(), AddGitHub()
│   └── Claims Transformation: IClaimsTransformation — enrich claims post-auth
├── Token Management:
│   ├── Duende.AccessTokenManagement: Automatic token refresh
│   ├── HttpContext.GetTokenAsync(): Access stored tokens
│   └── Token caching: Cache access tokens for client credentials
└── Securing API-to-API:
    ├── Client Credentials flow: Service A → Identity Provider → Token → Service B
    ├── Token propagation: Forward user's token downstream
    └── mTLS: Mutual TLS for zero-trust service mesh
```

### Section 5.1.4 — Cookie Authentication
```
├── Setup:
│   ├── services.AddAuthentication(CookieAuthenticationDefaults.AuthenticationScheme)
│   │   .AddCookie(options => { ... })
│   ├── Options: LoginPath, AccessDeniedPath, ExpireTimeSpan, SlidingExpiration
│   └── Data Protection: Cookie encryption with Data Protection API
├── Sign In / Sign Out:
│   ├── HttpContext.SignInAsync(principal, authProperties)
│   ├── HttpContext.SignOutAsync()
│   └── Claims Principal: Build from user data
├── Cookie Security:
│   ├── Secure: Only sent over HTTPS
│   ├── HttpOnly: Not accessible via JavaScript
│   ├── SameSite: Strict, Lax, None (CSRF protection)
│   └── Domain & Path: Scope cookie appropriately
├── Data Protection API:
│   ├── Key management: Where keys are stored
│   ├── Key rotation: Automatic
│   ├── Key storage: File system, Azure Blob, Redis, Database
│   └── Multi-instance: Shared key ring for load-balanced scenarios
└── When to use:
    ├── Server-rendered apps (MVC, Razor Pages)
    ├── Blazor Server
    └── Simple authentication without OAuth complexity
```

---

## Module 5.2: Authorization

### Section 5.2.1 — ASP.NET Core Authorization
```
├── Simple Authorization:
│   ├── [Authorize]: Require authenticated user
│   ├── [AllowAnonymous]: Override Authorize
│   └── Global: app.MapControllers().RequireAuthorization()
├── Role-Based:
│   ├── [Authorize(Roles = "Admin,Manager")]
│   ├── Role claims in JWT or Identity
│   ├── services.AddAuthorization(o => o.AddPolicy("Admin", p => p.RequireRole("Admin")))
│   └── Limitations: Coarse-grained, Doesn't scale well
├── Claims-Based:
│   ├── [Authorize(Policy = "CanEditProducts")]
│   ├── RequireClaim("permission", "products:write")
│   ├── Custom claims from Identity Provider
│   └── Advantage: More flexible than roles
├── Policy-Based (Recommended):
│   ├── Define Policies: services.AddAuthorization(o => {
│   │   o.AddPolicy("MinAge18", p => p.RequireClaim("age").AddRequirements(new MinAgeReq(18)));
│   │   o.AddPolicy("CanDeleteOrder", p => p.Requirements.Add(new CanDeleteOrderReq()));
│   ├── Custom Requirements: IAuthorizationRequirement
│   ├── Custom Handlers: AuthorizationHandler<TRequirement>
│   ├── Resource-Based: IAuthorizationService.AuthorizeAsync(user, resource, requirement)
│   └── Multiple Handlers: Any handler succeeding = authorized (OR logic)
├── Resource-Based Authorization:
│   ├── Authorize against the specific resource being accessed
│   ├── Example: "Can this user edit THIS order?"
│   ├── IAuthorizationService: Inject and call in controller
│   └── Operation-based: OperationAuthorizationRequirement (Read, Create, Update, Delete)
└── Advanced:
    ├── Imperative Authorization: IAuthorizationService in code
    ├── Authorization Middleware Builder (.NET 8+): Custom middleware
    ├── Dynamic Policies: IAuthorizationPolicyProvider
    └── Permission-Based: Combine with role → permission mapping
```

---

## Module 5.3: Application Security

### Section 5.3.1 — OWASP Mitigations in ASP.NET Core
```
├── SQL Injection:
│   ├── EF Core: Parameterized by default ✅
│   ├── Dapper: Use parameterized queries
│   ├── Raw SQL: FromSqlInterpolated (safe) vs FromSqlRaw (dangerous with string concat)
│   └── Never: String concatenation in SQL queries
├── XSS (Cross-Site Scripting):
│   ├── Razor: Auto-encodes output by default ✅
│   ├── @Html.Raw(): DANGEROUS — only for trusted content
│   ├── Content Security Policy (CSP): Add via middleware/headers
│   └── Input Sanitization: HtmlSanitizer library
├── CSRF (Cross-Site Request Forgery):
│   ├── Anti-forgery tokens: [ValidateAntiForgeryToken]
│   ├── Automatic for Razor Pages / MVC forms
│   ├── APIs: Use SameSite cookies + CORS (not anti-forgery tokens)
│   └── SameSite cookie attribute: Lax (default), Strict, None
├── Security Headers:
│   ├── X-Content-Type-Options: nosniff
│   ├── X-Frame-Options: DENY or SAMEORIGIN
│   ├── Strict-Transport-Security: HSTS
│   ├── Content-Security-Policy: Script sources, Style sources
│   ├── Referrer-Policy: no-referrer or strict-origin
│   ├── Permissions-Policy: Disable camera, microphone, geolocation
│   └── Libraries: NWebsec, NetEscapades.AspNetCore.SecurityHeaders
├── CORS:
│   ├── services.AddCors(o => o.AddPolicy("MyPolicy", p => p.WithOrigins("https://..."))
│   ├── AllowCredentials: Required for cookies/auth headers
│   ├── Preflight: OPTIONS request for complex requests
│   └── Never: AllowAnyOrigin + AllowCredentials (security vulnerability)
├── Rate Limiting (.NET 7+):
│   ├── services.AddRateLimiter(o => { ... })
│   ├── Algorithms: Fixed Window, Sliding Window, Token Bucket, Concurrency
│   ├── Per-endpoint: [EnableRateLimiting("policy")]
│   ├── Per-user: Partition by user ID or IP
│   └── Custom: Implement IRateLimiterPolicy
├── Data Protection:
│   ├── Encrypt sensitive data at rest
│   ├── IDataProtector: Purpose-bound encryption
│   ├── Use case: Cookie encryption, Token protection
│   └── Key management: Auto-rotation, Shared key ring
└── HTTPS:
    ├── UseHttpsRedirection(): Redirect HTTP → HTTPS
    ├── UseHsts(): HTTP Strict Transport Security
    ├── Kestrel HTTPS: Certificate configuration
    └── Let's Encrypt: Free TLS certificates, LettuceEncrypt library
```

---

> ### 🛠️ PHASE 5 PROJECT: **Multi-Tenant SaaS Application with Full Auth**
> ```
> ┌─────────────────────────────────────────────────────────────────┐
> │        MULTI-TENANT SAAS WITH FULL SECURITY                     │
> ├─────────────────────────────────────────────────────────────────┤
> │                                                                 │
> │ Authentication:                                                 │
> │  ✅ ASP.NET Core Identity with custom ApplicationUser            │
> │  ✅ JWT tokens: Access (15 min) + Refresh (7 days) + Rotation    │
> │  ✅ External login: Google + Microsoft via OIDC                   │
> │  ✅ Email confirmation + Password reset flow                     │
> │  ✅ Two-factor authentication (TOTP)                             │
> │  ✅ Account lockout after 5 failed attempts                      │
> │  ✅ Identity API endpoints (.NET 8)                               │
> │                                                                 │
> │ Authorization:                                                  │
> │  ✅ Multi-tenant: Tenant resolution from JWT claim + subdomain   │
> │  ✅ Role-based: Admin, Manager, User (per tenant)                │
> │  ✅ Permission-based: Fine-grained (products:write, orders:read) │
> │  ✅ Resource-based: "Can this user edit THIS resource?"           │
> │  ✅ Custom policy handlers for complex business rules             │
> │                                                                 │
> │ Security:                                                       │
> │  ✅ All security headers configured                               │
> │  ✅ CORS: Strict origin policy per tenant                         │
> │  ✅ Rate limiting: Per-user token bucket                          │
> │  ✅ Input validation: FluentValidation on all endpoints           │
> │  ✅ CSRF protection for Razor Pages admin                        │
> │  ✅ Data Protection API for sensitive data encryption             │
> │  ✅ HTTPS enforced with HSTS                                      │
> │  ✅ Audit logging: All auth events logged with correlation IDs    │
> │  ✅ Security scan: Pass OWASP ZAP baseline scan                  │
> └─────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 🧪 PHASE 6: TESTING & QUALITY ASSURANCE
### 📅 Duration: Months 11–13
### 🎯 Goal: Test ASP.NET Core applications at every level
### 👤 Level: Senior Developer

---

## Module 6.1: Unit Testing

### Section 6.1.1 — Testing Frameworks & Tools
```
├── Test Frameworks:
│   ├── xUnit: Most popular for .NET, [Fact], [Theory], Parallel by default
│   ├── NUnit: [Test], [TestCase], [SetUp]/[TearDown]
│   └── MSTest: [TestMethod], Microsoft's framework
├── Assertion Libraries:
│   ├── FluentAssertions: result.Should().Be(42), readable assertions
│   ├── Shouldly: result.ShouldBe(42)
│   └── Built-in: Assert.Equal(), Assert.True() (less readable)
├── Mocking Libraries:
│   ├── Moq: Mock<IService>(), Setup(), Verify()
│   │   ├── Setup: mock.Setup(s => s.GetById(1)).ReturnsAsync(product)
│   │   ├── Verify: mock.Verify(s => s.Save(It.IsAny<Product>()), Times.Once)
│   │   └── Callback: mock.Setup(...).Callback<Product>(p => captured = p)
│   ├── NSubstitute: Substitute.For<IService>(), Cleaner syntax
│   └── FakeItEasy: A.Fake<IService>(), A.CallTo()
├── Test Data:
│   ├── Bogus: Fake data generation (new Faker<Product>().RuleFor(...))
│   ├── AutoFixture: Automatic test data creation
│   ├── Builder Pattern: TestProductBuilder.Create().WithName("Test").Build()
│   └── Object Mothers: Static factory methods for test data
├── Code Coverage:
│   ├── Coverlet: Cross-platform .NET coverage
│   ├── dotnet test --collect:"XPlat Code Coverage"
│   ├── ReportGenerator: HTML coverage reports
│   └── Target: 80%+ for business logic (not 100% for everything)
└── Naming Convention:
    ├── MethodName_StateUnderTest_ExpectedBehavior
    ├── Should_ReturnProduct_When_IdExists
    └── Given_ValidOrder_When_PlacingOrder_Then_OrderIsCreated
```

### Section 6.1.2 — What & How to Unit Test
```
├── Domain Model:
│   ├── Entities: Business rules, State transitions, Invariants
│   ├── Value Objects: Equality, Validation, Behavior
│   ├── Aggregates: Invariant enforcement, Domain event publishing
│   └── Domain Services: Business logic with multiple aggregates
├── Application Services (MediatR Handlers):
│   ├── Mock dependencies: Repository, External services
│   ├── Verify: Correct calls to dependencies
│   ├── Verify: Correct mapping of request → response
│   └── Verify: Domain events published
├── Validators:
│   ├── FluentValidation: TestValidate(request).ShouldHaveValidationErrorFor(...)
│   └── Test all rules: Valid, Invalid, Edge cases
├── Mapping:
│   ├── AutoMapper: AssertConfigurationIsValid()
│   ├── Test mappings: Source → Destination property mapping
│   └── Null handling: What happens with null source values
├── NOT Worth Unit Testing:
│   ├── Controllers (thin — test via integration tests)
│   ├── Simple CRUD with no logic
│   ├── EF Core configurations (test via integration tests)
│   └── Third-party library wrappers (test via integration tests)
└── Patterns:
    ├── Arrange-Act-Assert (AAA): Clear test structure
    ├── One assertion per test (mostly): Focused, Clear failure
    ├── Don't test implementation details: Test behavior
    └── Keep tests independent: No shared state between tests
```

---

## Module 6.2: Integration Testing

### Section 6.2.1 — WebApplicationFactory
```
├── WebApplicationFactory<TProgram>:
│   ├── Creates in-memory test server
│   ├── Full ASP.NET Core pipeline: Middleware, DI, Routing, Filters
│   ├── Customize: Override ConfigureWebHost for test-specific config
│   ├── HTTP Client: factory.CreateClient() — make real HTTP requests
│   └── Service override: Replace real services with test doubles
├── Custom Factory:
│   ├── Replace database: EF Core InMemory or Testcontainers
│   ├── Replace external services: Mock HTTP clients
│   ├── Replace auth: Test authentication handler
│   ├── Replace background services: Disable or mock
│   └── Configure logging: Capture logs in tests
├── Test Authentication:
│   ├── Custom AuthenticationHandler<TOptions>: Always return authenticated
│   ├── Set claims: Role, UserId, TenantId
│   └── Per-test: Different users/roles for different test scenarios
├── Database:
│   ├── Testcontainers (recommended): Real PostgreSQL/SQL Server in Docker
│   │   ├── PostgreSqlContainer: new PostgreSqlBuilder().Build()
│   │   ├── Lifecycle: Start container → Run migrations → Run tests → Dispose
│   │   ├── Benefits: Real SQL, Real database behavior, Indexes, Constraints
│   │   └── Performance: Container reuse between test classes
│   ├── EF Core InMemory: Fast but doesn't enforce constraints (avoid!)
│   ├── SQLite InMemory: Better than InMemory, Still not production-accurate
│   └── Respawn: Reset database state between tests (truncate tables)
├── Testing Patterns:
│   ├── Arrange: Seed test data → Act: HTTP request → Assert: Response + DB state
│   ├── Collection Fixtures: Shared factory across test classes
│   ├── Per-test DB reset: Respawn or Transaction rollback
│   └── Parallel: Each test class gets its own scope
└── What to Integration Test:
    ├── Full API request/response cycles
    ├── Authentication/Authorization flows
    ├── Validation (400 responses)
    ├── Database queries and mutations
    ├── Middleware behavior
    └── Health check endpoints
```

### Section 6.2.2 — HTTP Client Testing
```
├── MockHttp (RichardSzalay.MockHttp):
│   ├── Mock external API calls
│   ├── Verify requests sent to external services
│   └── Simulate: Timeouts, Errors, Slow responses
├── WireMock.Net:
│   ├── Standalone HTTP mock server
│   ├── Record/playback mode
│   ├── Request matching: URL, Headers, Body
│   ├── Response templating
│   └── Fault simulation: Delays, Connection reset
├── IHttpClientFactory Testing:
│   ├── Register named/typed clients in test factory
│   ├── Replace HttpMessageHandler with mock
│   └── Verify outbound requests
└── Contract Testing:
    ├── PactNet: Consumer-driven contract testing
    ├── Consumer tests: Define expected interactions
    ├── Provider tests: Verify API meets contract
    └── Pact Broker: Share contracts between teams
```

---

## Module 6.3: Architecture & End-to-End Testing

### Section 6.3.1 — Architecture Testing
```
├── ArchUnitNET:
│   ├── Enforce dependency rules: Domain MUST NOT reference Infrastructure
│   ├── Naming conventions: Controllers must end with "Controller"
│   ├── Layer rules: Only Application layer can reference Domain
│   └── Example:
│       Types().That().ResideInNamespace("Domain")
│           .ShouldNot().DependOnAny("Infrastructure")
├── NetArchTest:
│   ├── Similar to ArchUnit
│   ├── Types.InAssembly(assembly).That().ResideInNamespace("Domain")
│   │   .ShouldNot().HaveDependencyOn("Infrastructure")
│   └── Run in CI: Fail build on architecture violations
└── Fitness Functions:
    ├── Automated architecture validation in CI
    ├── Dependency graph analysis
    ├── Cyclomatic complexity limits
    └── API compatibility checks
```

### Section 6.3.2 — E2E & Performance Testing
```
├── Playwright (.NET):
│   ├── Browser automation: Chromium, Firefox, WebKit
│   ├── C# API: await page.GotoAsync("..."), await page.ClickAsync("...")
│   ├── Auto-waiting: Built-in, No explicit waits needed
│   ├── Assertions: await Expect(page.Locator(".title")).ToHaveTextAsync("...")
│   └── Use case: Blazor apps, Razor Pages, Full UI testing
├── Selenium:
│   ├── Legacy but widely used
│   ├── WebDriver protocol
│   └── Cross-browser testing
├── Performance Testing:
│   ├── k6: JavaScript-based, CLI runner, .NET integrable
│   ├── NBomber: .NET-native load testing framework
│   │   ├── Scenarios: Define request patterns
│   │   ├── Load Simulation: Inject rate, Ramp up/down
│   │   └── Reporting: HTML reports, Console output
│   ├── BenchmarkDotNet: Micro-benchmarks for code paths
│   └── Metrics: P50, P95, P99, Throughput, Error rate
└── Snapshot Testing:
    ├── Verify: Snapshot testing for .NET (serialized outputs)
    ├── Use case: API response snapshots, HTML output
    └── Review: Verify.DiffTool for snapshot diffs
```

---

> ### 🛠️ PHASE 6 PROJECT: **Fully Tested Task Management API**
> ```
> ┌─────────────────────────────────────────────────────────────────┐
> │        FULLY TESTED TASK MANAGEMENT API                         │
> ├─────────────────────────────────────────────────────────────────┤
> │                                                                 │
> │ Test Suite:                                                     │
> │                                                                 │
> │ Unit Tests (200+):                                              │
> │  ✅ Domain entities: Task state machine, Business rules          │
> │  ✅ Value objects: Priority, DueDate, TaskId                     │
> │  ✅ MediatR handlers: All commands and queries                   │
> │  ✅ FluentValidation validators: All request validators          │
> │  ✅ Mapping profiles: AutoMapper configuration                   │
> │  ✅ Domain events: Event publishing and handling                 │
> │  ✅ Bogus: Test data generation                                  │
> │  ✅ Moq: Mock all dependencies                                   │
> │                                                                 │
> │ Integration Tests (50+):                                        │
> │  ✅ WebApplicationFactory: Custom test factory                   │
> │  ✅ Testcontainers: PostgreSQL in Docker                         │
> │  ✅ Respawn: Database reset between tests                        │
> │  ✅ Test auth handler: Simulate different users/roles            │
> │  ✅ Full CRUD API tests                                          │
> │  ✅ Auth flow tests: Login, JWT refresh, Forbidden               │
> │  ✅ Validation tests: 400 responses                              │
> │  ✅ WireMock: External notification service mocking               │
> │  ✅ Health check tests                                           │
> │                                                                 │
> │ Architecture Tests:                                             │
> │  ✅ NetArchTest: Layer dependency rules enforced                  │
> │  ✅ Domain has NO infrastructure dependencies                    │
> │  ✅ Controllers are thin (no business logic)                     │
> │                                                                 │
> │ Performance Tests:                                              │
> │  ✅ NBomber: 1000 RPS sustained for 5 minutes                    │
> │  ✅ BenchmarkDotNet: Critical path micro-benchmarks              │
> │                                                                 │
> │ Coverage: 85%+ overall, 95%+ for domain layer                  │
> │ CI: All tests run on every PR (GitHub Actions)                  │
> └─────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 🚀 PHASE 7: PERFORMANCE, SCALABILITY & DEVOPS
### 📅 Duration: Months 13–16
### 🎯 Goal: Optimize, deploy, and operate ASP.NET Core in production
### 👤 Level: Senior Developer

---

## Module 7.1: Performance Optimization

### Section 7.1.1 — ASP.NET Core Performance
```
├── Kestrel Tuning:
│   ├── Connection Limits: MaxConcurrentConnections
│   ├── Request Limits: MaxRequestBodySize, MaxRequestHeaderCount
│   ├── Keep-Alive: KeepAliveTimeout, RequestHeadersTimeout
│   ├── HTTP/2: Enabled by default, MaxStreamsPerConnection
│   ├── HTTP/3: QUIC support (.NET 7+)
│   └── Thread Pool: ThreadPool.SetMinThreads for high-concurrency
├── Response Optimization:
│   ├── Response Compression: UseResponseCompression() — Brotli, Gzip
│   ├── Minification: HTML, CSS, JS minification
│   ├── Static File Caching: Cache-Control headers, Fingerprinting
│   ├── ETags: Conditional responses (304 Not Modified)
│   └── Content Negotiation: Return only what client needs
├── Memory Optimization:
│   ├── Object Pooling: ObjectPool<T> for expensive objects
│   ├── ArrayPool<T>.Shared: Rent/Return buffers
│   ├── StringBuilder pooling: StringBuilderPool
│   ├── MemoryCache eviction: Set size limits
│   ├── Avoid LOH allocations: Keep objects < 85KB
│   ├── Span<T> / Memory<T>: Zero-allocation operations
│   └── IAsyncEnumerable: Stream large results (don't buffer)
├── Async Best Practices:
│   ├── Async all the way: Don't mix sync and async
│   ├── Avoid .Result / .Wait(): Thread pool starvation
│   ├── ValueTask: Use for frequently sync-completing operations
│   ├── CancellationToken: Pass through entire call chain
│   └── ConfigureAwait(false): Library code only
├── Minimal API Performance:
│   ├── Faster than MVC controllers (less overhead)
│   ├── Source-generated: RequestDelegateGenerator (.NET 8+)
│   └── AOT-friendly: Ahead-of-time compilation support
├── Native AOT (.NET 8+):
│   ├── Ahead-of-time compilation: No JIT overhead
│   ├── Faster startup: Critical for serverless / containers
│   ├── Smaller footprint: Trimmed self-contained
│   ├── Limitations: No reflection-heavy code, Some libraries incompatible
│   └── Publishing: dotnet publish -c Release -r linux-x64 --self-contained /p:PublishAot=true
├── Diagnostics:
│   ├── dotnet-counters: Real-time performance counters
│   ├── dotnet-trace: Collect performance traces
│   ├── dotnet-dump: Memory dump analysis
│   ├── dotnet-gcdump: GC heap analysis
│   ├── EventPipe: Low-overhead tracing
│   └── Visual Studio: CPU profiler, Memory profiler, .NET Object Allocation Tracker
└── Database Performance:
    ├── Connection Pooling: Npgsql pool size configuration
    ├── DbContext Pooling: AddDbContextPool (avoid DbContext creation overhead)
    ├── Compiled Queries: EF.CompileQuery for hot paths
    ├── AsNoTracking: Read-only queries
    ├── Projections: Select only needed columns
    ├── Bulk operations: ExecuteUpdate/ExecuteDelete, EFCore.BulkExtensions
    └── Query analysis: MiniProfiler, EF Core logging
```

---

## Module 7.2: Observability in ASP.NET Core

### Section 7.2.1 — OpenTelemetry
```
├── Setup (.NET 8+):
│   ├── builder.Services.AddOpenTelemetry()
│   │   .WithTracing(b => b
│   │       .AddAspNetCoreInstrumentation()
│   │       .AddHttpClientInstrumentation()
│   │       .AddEntityFrameworkCoreInstrumentation()
│   │       .AddOtlpExporter())
│   │   .WithMetrics(b => b
│   │       .AddAspNetCoreInstrumentation()
│   │       .AddRuntimeInstrumentation()
│   │       .AddProcessInstrumentation()
│   │       .AddOtlpExporter())
│   └── .WithLogging(b => b.AddOtlpExporter())
├── Tracing:
│   ├── Automatic: HTTP requests, EF Core queries, HttpClient calls
│   ├── Custom: ActivitySource + Activity for custom spans
│   ├── Exporters: OTLP (Jaeger, Tempo, Honeycomb), Zipkin, Console
│   └── Context Propagation: W3C TraceContext (automatic)
├── Metrics:
│   ├── Built-in: Request duration, Active connections, Request rate
│   ├── Custom: Meter + Counter/Histogram/Gauge for business metrics
│   ├── Exporters: OTLP (Prometheus, Grafana), Console
│   └── .NET Metrics: GC, Thread pool, Memory, CPU (AddRuntimeInstrumentation)
├── Logging:
│   ├── Serilog: Structured logging with OTLP export
│   ├── Log Context: TraceId, SpanId automatically included
│   ├── Correlation: Trace logs across services via TraceId
│   └── Exporters: OTLP → Loki, Elasticsearch, Seq
├── .NET Aspire Dashboard:
│   ├── Built-in observability during development
│   ├── Traces, Logs, Metrics in one view
│   └── Structured log viewing with filtering
├── Application Insights (Azure):
│   ├── services.AddApplicationInsightsTelemetry()
│   ├── Auto-collection: Requests, Dependencies, Exceptions, Traces
│   ├── Custom: TelemetryClient for custom events/metrics
│   ├── Smart Detection: Anomaly detection, Performance alerts
│   └── Live Metrics: Real-time performance view
└── Health Check Dashboard:
    ├── HealthChecksUI: Web dashboard for health check status
    ├── Webhooks: Notify on health status changes
    └── History: Track health over time
```

---

## Module 7.3: Deployment & DevOps

### Section 7.3.1 — Containerization
```
├── Dockerfile for ASP.NET Core:
│   ├── Multi-stage build:
│   │   ├── Stage 1 (build): mcr.microsoft.com/dotnet/sdk:8.0
│   │   ├── Stage 2 (publish): dotnet publish -c Release -o /app
│   │   └── Stage 3 (runtime): mcr.microsoft.com/dotnet/aspnet:8.0
│   ├── Chiseled Images (.NET 8+): Ultra-minimal, Non-root, Distroless
│   │   └── mcr.microsoft.com/dotnet/aspnet:8.0-jammy-chiseled
│   ├── Alpine Images: Smaller footprint
│   ├── Layer Caching: Copy .csproj first → restore → copy source → build
│   └── .dockerignore: Exclude bin/, obj/, .git/
├── Docker Compose:
│   ├── Multi-container local development
│   ├── App + PostgreSQL + Redis + Kafka + Seq
│   ├── Volumes: Database persistence, Shared files
│   └── Networks: Service discovery by container name
├── Kubernetes Deployment:
│   ├── Deployment: Replicas, Rolling update strategy
│   ├── Service: ClusterIP for internal, LoadBalancer for external
│   ├── Ingress: NGINX Ingress with TLS termination
│   ├── ConfigMap: appsettings.json, Non-sensitive config
│   ├── Secret: Connection strings, API keys
│   ├── HPA: Auto-scale based on CPU/Memory/Custom metrics
│   ├── Health Probes: Liveness (/health/live), Readiness (/health/ready)
│   ├── Resource Limits: CPU/Memory requests and limits
│   └── Helm Chart: Templated Kubernetes manifests
├── .NET Aspire for Deployment:
│   ├── azd (Azure Developer CLI) integration
│   ├── Generate Bicep/Terraform from Aspire model
│   └── Deploy to: Azure Container Apps, Kubernetes
└── CI/CD Pipeline:
    ├── Build: dotnet build → dotnet test → dotnet publish
    ├── Docker: docker build → docker push to registry
    ├── Deploy: ArgoCD / Flux / Azure DevOps / GitHub Actions
    ├── Database: dotnet ef migrations bundle → Run in pipeline
    └── Smoke Tests: Post-deployment health check verification
```

### Section 7.3.2 — Cloud Deployment Options
```
├── Azure:
│   ├── Azure App Service: PaaS, Easy deployment, Scaling
│   ├── Azure Container Apps: Serverless containers, KEDA scaling
│   ├── Azure Kubernetes Service (AKS): Full K8s control
│   ├── Azure Functions: Serverless .NET functions
│   └── Azure Static Web Apps: Blazor WASM hosting
├── AWS:
│   ├── AWS App Runner: Simplest container deployment
│   ├── ECS Fargate: Serverless containers
│   ├── EKS: Managed Kubernetes
│   ├── Lambda (.NET): Serverless functions
│   └── Elastic Beanstalk: PaaS-like deployment
├── Other:
│   ├── DigitalOcean App Platform
│   ├── Railway / Render: Simple container hosting
│   ├── Self-hosted: Linux + Kestrel behind NGINX
│   └── IIS (Windows): Traditional Windows hosting
└── Configuration per Environment:
    ├── appsettings.{Environment}.json
    ├── Environment variables (12-factor)
    ├── Azure Key Vault / AWS Secrets Manager
    ├── Kubernetes ConfigMaps + Secrets
    └── .NET Aspire: Component configuration
```

---

## Module 7.4: Resilience in ASP.NET Core

### Section 7.4.1 — HTTP Resilience
```
├── Microsoft.Extensions.Http.Resilience (.NET 8+):
│   ├── Standard Resilience Handler:
│   │   services.AddHttpClient<IMyApi>()
│   │       .AddStandardResilienceHandler();
│   │   └── Includes
# 🟣 ASP.NET ROADMAP (Continued)
## Picking up from Phase 7, Module 7.4...

---

### Section 7.4.1 — HTTP Resilience (Continued)
```
├── Microsoft.Extensions.Http.Resilience (.NET 8+):
│   ├── Standard Resilience Handler:
│   │   services.AddHttpClient<IMyApi>()
│   │       .AddStandardResilienceHandler();
│   │   └── Includes: Retry, Circuit Breaker, Timeout, Rate Limiter, Bulkhead
│   ├── Custom Resilience Pipeline:
│   │   services.AddHttpClient<IMyApi>()
│   │       .AddResilienceHandler("custom", builder => {
│   │           builder.AddRetry(new HttpRetryStrategyOptions {
│   │               MaxRetryAttempts = 3,
│   │               BackoffType = DelayBackoffType.Exponential,
│   │               UseJitter = true
│   │           });
│   │           builder.AddCircuitBreaker(new HttpCircuitBreakerStrategyOptions {
│   │               FailureRatio = 0.5,
│   │               SamplingDuration = TimeSpan.FromSeconds(10),
│   │               MinimumThroughput = 10,
│   │               BreakDuration = TimeSpan.FromSeconds(30)
│   │           });
│   │           builder.AddTimeout(TimeSpan.FromSeconds(5));
│   │       });
│   └── Hedging: Send duplicate request to backup after delay
├── Polly v8 (Underlying Library):
│   ├── ResiliencePipeline: New API in Polly v8
│   ├── Strategies:
│   │   ├── Retry: Exponential backoff + Jitter
│   │   ├── Circuit Breaker: Closed → Open → Half-Open
│   │   ├── Timeout: Optimistic (CancellationToken) vs Pessimistic
│   │   ├── Bulkhead: Limit concurrent executions
│   │   ├── Rate Limiter: Token bucket, Sliding window
│   │   ├── Fallback: Default value on failure
│   │   └── Hedging: Parallel requests for latency reduction
│   ├── Composition: Chain strategies into a pipeline
│   ├── Telemetry: Built-in Polly.Extensions.Telemetry → OpenTelemetry
│   └── DI Integration: services.AddResiliencePipeline("my-pipeline", builder => { ... })
├── IHttpClientFactory:
│   ├── Named Clients: services.AddHttpClient("github", c => c.BaseAddress = ...)
│   ├── Typed Clients: services.AddHttpClient<IGitHubClient, GitHubClient>()
│   ├── Handler Lifetime: Default 2 minutes (DNS refresh)
│   ├── Delegating Handlers: Custom message handlers (auth, logging)
│   │   ├── Add auth token: DelegatingHandler → AddHttpMessageHandler<AuthHandler>()
│   │   ├── Logging: Request/Response logging handler
│   │   └── Correlation ID: Propagate correlation ID downstream
│   ├── Benefits: Connection pooling, DNS rotation, Resilience integration
│   └── Anti-pattern: new HttpClient() — socket exhaustion, DNS caching issues
├── Refit (Type-safe REST):
│   ├── Define API as interface: [Get("/users/{id}")] Task<User> GetUser(int id)
│   ├── Auto-generated implementation
│   ├── DI Integration: services.AddRefitClient<IGitHubApi>()
│   ├── Resilience: Chain with .AddStandardResilienceHandler()
│   └── Serialization: System.Text.Json or Newtonsoft
└── gRPC Resilience:
    ├── GrpcChannel options: MaxRetryAttempts, ServiceConfig
    ├── Built-in retry: Via service config in .proto
    ├── Hedging: Parallel calls for latency
    └── Deadlines: Always set deadlines on gRPC calls
```

### Section 7.4.2 — Application Resilience Patterns
```
├── Health Checks (Production-Grade):
│   ├── Liveness: /health/live → "Is the process alive?" (minimal checks)
│   ├── Readiness: /health/ready → "Can it handle traffic?" (check dependencies)
│   ├── Startup: /health/startup → "Has it finished initializing?"
│   ├── Custom Checks:
│   │   ├── Database connectivity + query execution
│   │   ├── Redis connectivity
│   │   ├── Message broker connectivity
│   │   ├── Downstream service availability
│   │   ├── Disk space
│   │   └── Memory usage threshold
│   ├── Tags: services.AddHealthChecks().AddCheck<DbCheck>("db", tags: ["ready"])
│   ├── app.MapHealthChecks("/health/live", new() { Predicate = _ => false })
│   └── app.MapHealthChecks("/health/ready", new() { Predicate = r => r.Tags.Contains("ready") })
├── Graceful Shutdown:
│   ├── IHostApplicationLifetime.ApplicationStopping: Drain in-flight requests
│   ├── Kubernetes: preStop hook + terminationGracePeriodSeconds
│   ├── SignalR: Connection draining
│   ├── Background Services: Respect CancellationToken in ExecuteAsync
│   └── Message Consumers: Stop consuming, Process remaining, Acknowledge
├── Idempotency:
│   ├── IdempotencyKey header: Client-generated unique ID
│   ├── Implementation:
│   │   ├── Middleware: Check Redis/DB for existing key
│   │   ├── If exists: Return cached response
│   │   ├── If not: Process request → Store response with key
│   │   └── TTL: Auto-expire after 24 hours
│   ├── Libraries: IdempotentAPI NuGet package
│   └── Database: INSERT ON CONFLICT DO NOTHING
├── Outbox Pattern:
│   ├── Problem: Dual-write (DB + Message broker) → Inconsistency
│   ├── Solution: Write events to outbox table → Background service publishes
│   ├── Implementation:
│   │   ├── Domain event → OutboxMessage in same DB transaction
│   │   ├── BackgroundService polls outbox → Publish to Kafka/RabbitMQ
│   │   ├── Mark as published → Delete after retention period
│   │   └── Retry: Unpublished messages retried with backoff
│   ├── Libraries: MassTransit (built-in outbox), Wolverine, CAP
│   └── CDC Alternative: Debezium reads outbox table → Kafka
└── Circuit Breaking for Database:
    ├── Short-circuit on connection failures
    ├── Prevent overwhelming recovering database
    └── Polly circuit breaker around DB operations
```

---

## Module 7.5: Message-Based Communication

### Section 7.5.1 — MassTransit
```
├── Overview: Abstraction over message brokers (RabbitMQ, Kafka, Azure SB, SQS)
├── Setup:
│   ├── services.AddMassTransit(x => {
│   │       x.AddConsumer<OrderCreatedConsumer>();
│   │       x.UsingRabbitMq((context, cfg) => {
│   │           cfg.Host("rabbitmq://localhost");
│   │           cfg.ConfigureEndpoints(context);
│   │       });
│   │   });
│   └── Transport-agnostic: Switch broker with config change
├── Message Types:
│   ├── Commands: ISendEndpoint.Send<ICreateOrder>(message)
│   │   └── Point-to-point: One sender → One consumer
│   ├── Events: IPublishEndpoint.Publish<IOrderCreated>(event)
│   │   └── Publish-Subscribe: One publisher → Many subscribers
│   └── Requests: IRequestClient<TRequest>.GetResponse<TResponse>()
│       └── Request-Reply: Synchronous-like over async transport
├── Consumers:
│   ├── IConsumer<T>: Handle messages
│   ├── Consumer Definition: Configure retries, concurrency, circuit breaker
│   ├── Message Retry: Immediate, Interval, Exponential
│   ├── Redelivery: Move to error queue after max retries
│   └── Fault Handling: IConsumer<Fault<T>> for error handling
├── Sagas:
│   ├── MassTransit Sagas: State machine for long-running processes
│   ├── Automatonymous: Define states and transitions
│   ├── Persistence: EF Core, Redis, MongoDB, Dapper
│   ├── Example: Order Saga: Created → Paid → Shipped → Completed
│   └── Compensation: Handle failures and rollback
├── Advanced:
│   ├── Outbox: cfg.UseEntityFrameworkOutbox() — guaranteed delivery
│   ├── Mediator: In-process message dispatch (no broker needed)
│   ├── Middleware: Filters, Observers, Activities
│   ├── Scheduling: Delayed messages, Recurring messages (Quartz)
│   └── Multi-tenant: Tenant-aware message routing
└── Testing:
    ├── InMemory Transport: services.AddMassTransitTestHarness()
    ├── Test Harness: Verify published/consumed messages
    └── Saga Testing: Assert state transitions
```

### Section 7.5.2 — Alternative Messaging
```
├── Wolverine:
│   ├── Messaging + Command Bus + Saga (by Jeremy Miller)
│   ├── Lighter than MassTransit
│   ├── Built-in: Outbox, Saga, Scheduled jobs
│   ├── Transport: RabbitMQ, Kafka, Azure Service Bus, Amazon SQS
│   └── Integration: EF Core, Marten (Event Sourcing)
├── CAP (DotNetCore.CAP):
│   ├── Outbox pattern library
│   ├── Database + Message broker integration
│   ├── Supports: RabbitMQ, Kafka, Azure SB, Amazon SQS
│   └── Dashboard: Built-in monitoring UI
├── RabbitMQ Direct:
│   ├── RabbitMQ.Client NuGet package
│   ├── Full control over exchanges, queues, bindings
│   ├── When: Simple pub/sub without framework overhead
│   └── Caution: Manual retry, Error handling, Connection management
├── Kafka Direct:
│   ├── Confluent.Kafka NuGet package
│   ├── Producer: ProducerBuilder<string, string>
│   ├── Consumer: ConsumerBuilder<string, string>
│   ├── Schema Registry: Avro/Protobuf serialization
│   └── When: High-throughput, Ordered events, Log-based processing
└── Azure Service Bus / Amazon SQS:
    ├── Azure.Messaging.ServiceBus: Queues, Topics, Subscriptions
    ├── Amazon.SQS: Standard and FIFO queues
    └── When: Cloud-native, Managed, Serverless integration
```

---

> ### 🛠️ PHASE 7 PROJECT: **Production-Ready Microservice**
> ```
> ┌─────────────────────────────────────────────────────────────────────┐
> │           PRODUCTION-READY NOTIFICATION MICROSERVICE               │
> ├─────────────────────────────────────────────────────────────────────┤
> │                                                                     │
> │  ┌──────────┐    ┌──────────┐    ┌──────────────────┐             │
> │  │ Other    │───→│ RabbitMQ │───→│  Notification    │             │
> │  │ Services │    │          │    │  Service         │             │
> │  └──────────┘    └──────────┘    │  (ASP.NET Core)  │             │
> │                                   └────┬──┬──┬──────┘             │
> │                                        │  │  │                     │
> │                              ┌─────────┘  │  └─────────┐          │
> │                              ▼            ▼            ▼          │
> │                         ┌────────┐  ┌─────────┐  ┌─────────┐     │
> │                         │ Email  │  │  SMS    │  │  Push   │     │
> │                         │(SMTP)  │  │(Twilio) │  │(FCM)   │     │
> │                         └────────┘  └─────────┘  └─────────┘     │
> │                                                                     │
> │ Performance:                                                       │
> │  ✅ Native AOT publishing: < 50ms startup time                     │
> │  ✅ Response compression: Brotli + Gzip                             │
> │  ✅ Object pooling for template rendering                           │
> │  ✅ Compiled EF Core queries for template lookups                   │
> │  ✅ DbContext pooling: AddDbContextPool                             │
> │  ✅ NBomber: 2000 messages/sec sustained throughput                 │
> │  ✅ Memory profiling: No GC Gen2 collections under normal load     │
> │                                                                     │
> │ Resilience:                                                        │
> │  ✅ MassTransit consumers with retry + circuit breaker              │
> │  ✅ HTTP resilience: Polly v8 on Twilio/FCM clients                 │
> │  ✅ Outbox pattern: MassTransit EF Core outbox                      │
> │  ✅ Idempotency: Deduplicate duplicate messages                     │
> │  ✅ Health checks: RabbitMQ, PostgreSQL, SMTP, Twilio               │
> │  ✅ Graceful shutdown: Drain consumers before stopping              │
> │                                                                     │
> │ Observability:                                                     │
> │  ✅ OpenTelemetry: Traces (Jaeger), Metrics (Prometheus), Logs     │
> │  ✅ Serilog: Structured JSON logging → Seq/Loki                    │
> │  ✅ Grafana dashboards: Message rate, Error rate, Latency P99      │
> │  ✅ Alerting: SLO burn rate (99.9% delivery success)               │
> │  ✅ .NET Aspire: Local development dashboard                        │
> │                                                                     │
> │ Deployment:                                                        │
> │  ✅ Docker: Multi-stage build, Chiseled image (< 50MB)              │
> │  ✅ Docker Compose: Full local stack                                 │
> │  ✅ Kubernetes: Deployment + HPA + Health probes                    │
> │  ✅ Helm chart: Parameterized deployment                            │
> │  ✅ CI/CD: GitHub Actions → Docker build → Push to registry         │
> │  ✅ GitOps: ArgoCD deployment to K8s                                 │
> │  ✅ Database migrations: EF Core migration bundle in CI             │
> └─────────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 🏆 PHASE 8: MICROSERVICES & DISTRIBUTED SYSTEMS
### 📅 Duration: Months 16–20+
### 🎯 Goal: Architect and build distributed systems with ASP.NET Core
### 👤 Level: Architect

---

## Module 8.1: Microservices with ASP.NET Core

### Section 8.1.1 — Service Architecture
```
├── Project Structure (Per Service):
│   ├── MyService.API: Controllers/Minimal APIs, Middleware, Filters
│   ├── MyService.Application: MediatR handlers, DTOs, Validators, Interfaces
│   ├── MyService.Domain: Entities, Value Objects, Aggregates, Domain Events
│   ├── MyService.Infrastructure: EF Core, External services, Messaging
│   └── MyService.Tests: Unit + Integration tests
├── Clean Architecture Template:
│   ├── ardalis/CleanArchitecture: Popular template
│   ├── jasontaylordev/CleanArchitecture: Another popular option
│   ├── amantinband/clean-architecture: Minimal template
│   └── Custom: Build your own based on team needs
├── Shared Libraries (NuGet):
│   ├── BuildingBlocks.Domain: Base Entity, Value Object, Aggregate Root
│   ├── BuildingBlocks.Application: Result<T>, PagedResult<T>
│   ├── BuildingBlocks.Infrastructure: Outbox, Interceptors
│   ├── BuildingBlocks.Messaging: MassTransit base contracts
│   └── Caution: Don't create shared domain models (breaks bounded contexts)
├── API Gateway:
│   ├── YARP: .NET-native reverse proxy
│   ├── Ocelot: Older .NET API gateway
│   ├── Configuration: Routes, Clusters, Load balancing, Auth
│   └── BFF (Backend for Frontend): Aggregate multiple service calls
├── Service Communication:
│   ├── Synchronous:
│   │   ├── gRPC: Internal service-to-service (preferred for .NET-to-.NET)
│   │   ├── REST + Refit: Type-safe HTTP clients
│   │   └── HTTP + Resilience: AddStandardResilienceHandler()
│   ├── Asynchronous:
│   │   ├── MassTransit: Events + Commands via RabbitMQ/Kafka
│   │   ├── Domain Events: In-process (MediatR) + Cross-service (MassTransit)
│   │   └── Outbox: Guaranteed delivery with EF Core outbox
│   └── Decision: Async by default, Sync only when response needed immediately
└── Service Discovery:
    ├── Kubernetes DNS: service-name.namespace.svc.cluster.local
    ├── Consul: Service registration + Health checking
    ├── .NET Aspire: Built-in service discovery for local development
    └── Configuration-based: appsettings.json with service URLs
```

### Section 8.1.2 — Distributed Data Patterns
```
├── Database per Service:
│   ├── Each service owns its database schema
│   ├── NO direct cross-service database access
│   ├── Data duplication: Acceptable (eventual consistency)
│   └── Synchronization: Events propagate changes
├── Saga Pattern with MassTransit:
│   ├── Choreography:
│   │   ├── Service publishes event → Next service reacts
│   │   ├── Each service publishes completion/failure event
│   │   ├── Compensating actions on failure
│   │   └── Example: OrderCreated → PaymentProcessed → InventoryReserved → OrderConfirmed
│   ├── Orchestration:
│   │   ├── Saga State Machine: MassTransit Automatonymous
│   │   ├── States: Submitted, PaymentPending, Shipped, Completed, Faulted
│   │   ├── Events trigger transitions
│   │   ├── Compensating events: RefundPayment, ReleaseInventory
│   │   └── Persistence: EF Core, Redis, MongoDB
│   └── Implementation:
│       public class OrderStateMachine : MassTransitStateMachine<OrderState>
│       {
│           public OrderStateMachine()
│           {
│               InstanceState(x => x.CurrentState);
│               Event(() => OrderSubmitted, x => x.CorrelateById(m => m.Message.OrderId));
│               Initially(
│                   When(OrderSubmitted)
│                       .Then(context => context.Saga.OrderDate = DateTime.UtcNow)
│                       .PublishAsync(context => context.Init<IProcessPayment>(...))
│                       .TransitionTo(PaymentPending));
│           }
│       }
├── CQRS Implementation:
│   ├── Write Side:
│   │   ├── Command → Validate → Execute → Persist → Publish Event
│   │   ├── EF Core: Full entity tracking, Transactions
│   │   ├── Strong consistency within aggregate
│   │   └── Domain events → Outbox → Message broker
│   ├── Read Side:
│   │   ├── Consume events → Update denormalized read model
│   │   ├── Dapper: Fast, Optimized queries
│   │   ├── Separate database (optional): Different schema optimized for reads
│   │   └── Eventually consistent with write side
│   └── Synchronization:
│       ├── Event-based: OrderCreatedEvent → Update OrderReadModel
│       ├── MassTransit Consumer: Consume events, Update read DB
│       └── Projection: Background service that builds read models
├── Event Sourcing with Marten:
│   ├── Marten: .NET library for Event Sourcing on PostgreSQL
│   ├── Event Store: Append events to PostgreSQL (JSONB)
│   ├── Aggregate: Load by replaying events
│   ├── Projections:
│   │   ├── Inline: Updated in same transaction as event
│   │   ├── Async: Background daemon processes events
│   │   └── Live: Rebuild on-the-fly (development/debugging)
│   ├── Snapshots: Periodic state capture for performance
│   ├── Integration: Wolverine for messaging + Marten for event sourcing
│   └── Alternative: EventStoreDB with KurrentDB client
├── Distributed Caching:
│   ├── Redis: Shared cache across services
│   ├── Cache-Aside: Service-level caching with Redis
│   ├── Invalidation: Publish cache invalidation events via message broker
│   └── HybridCache (.NET 9): L1 in-memory + L2 Redis
└── CDC (Change Data Capture):
    ├── Debezium: PostgreSQL WAL → Kafka
    ├── Use case: Sync data between service databases
    ├── Outbox table → Debezium → Kafka → Consumer service
    └── .NET Consumer: Confluent.Kafka consumer processes CDC events
```

---

## Module 8.2: .NET Aspire (Cloud-Native Orchestration)

### Section 8.2.1 — .NET Aspire Deep Dive
```
├── App Host (Orchestration):
│   ├── Define application topology in code:
│   │   var builder = DistributedApplication.CreateBuilder(args);
│   │   var postgres = builder.AddPostgres("pg").AddDatabase("orders-db");
│   │   var redis = builder.AddRedis("cache");
│   │   var rabbitMq = builder.AddRabbitMQ("messaging");
│   │   var orderApi = builder.AddProject<Projects.OrderApi>("order-api")
│   │       .WithReference(postgres)
│   │       .WithReference(redis)
│   │       .WithReference(rabbitMq);
│   │   var webFrontend = builder.AddProject<Projects.WebFrontend>("web")
│   │       .WithExternalHttpEndpoints()
│   │       .WithReference(orderApi);
│   │   builder.Build().Run();
│   ├── Auto-provisioning: Containers started automatically
│   ├── Connection strings: Injected into services automatically
│   └── Dashboard: Traces, Logs, Metrics for all services
├── Service Defaults:
│   ├── builder.AddServiceDefaults() adds:
│   │   ├── OpenTelemetry (Tracing + Metrics + Logging)
│   │   ├── Health checks (default endpoints)
│   │   ├── Service discovery
│   │   ├── HTTP resilience (standard resilience handler)
│   │   └── Logging configuration
│   └── Consistent baseline across all services
├── Components (Integrations):
│   ├── Database: PostgreSQL, SQL Server, MySQL, MongoDB, Oracle
│   ├── Caching: Redis, Garnet
│   ├── Messaging: RabbitMQ, Kafka, Azure Service Bus, Amazon SQS
│   ├── Storage: Azure Blob, Azure Queue, Amazon S3
│   ├── Search: Elasticsearch, OpenSearch
│   ├── AI: OpenAI, Ollama
│   └── Observability: Seq, Grafana, Prometheus
├── Service Discovery:
│   ├── Automatic: Services reference each other by name
│   ├── HTTP client: builder.Services.AddHttpClient<IOrderApi>()
│   │   uses service discovery to resolve "order-api" → actual URL
│   └── gRPC: Same service discovery for gRPC channels
├── Deployment:
│   ├── Azure Container Apps: Native deployment target
│   ├── Kubernetes: Generate manifests from Aspire model
│   ├── azd (Azure Developer CLI): One-command deployment
│   └── Aspir8: Community tool for K8s manifest generation
└── When to use:
    ├── New .NET microservices projects
    ├── Local development orchestration (replaces Docker Compose)
    ├── Consistent observability setup
    └── NOT a replacement for Kubernetes in production
```

---

## Module 8.3: Advanced Distributed Patterns

### Section 8.3.1 — Event-Driven Architecture
```
├── Domain Events (In-Process):
│   ├── MediatR INotification: Publish within same process
│   ├── Dispatch timing:
│   │   ├── Before SaveChanges: Side effects in same transaction
│   │   ├── After SaveChanges: Side effects in separate transaction
│   │   └── Outbox: Guaranteed delivery across process boundaries
│   └── Example:
│       // In aggregate
│       public void PlaceOrder()
│       {
│           Status = OrderStatus.Placed;
│           AddDomainEvent(new OrderPlacedDomainEvent(Id, TotalAmount));
│       }
│       // In SaveChangesInterceptor
│       foreach (var entity in entries.SelectMany(e => e.Entity.DomainEvents))
│           await mediator.Publish(entity);
├── Integration Events (Cross-Service):
│   ├── MassTransit: Publish to RabbitMQ/Kafka
│   ├── Event Contracts: Shared NuGet package with event interfaces
│   │   └── public interface IOrderPlaced { Guid OrderId { get; } decimal Total { get; } }
│   ├── Versioning: Add new fields (backward compatible), Never remove
│   ├── Outbox: Domain event → Integration event → Outbox → Broker
│   └── Idempotent Consumers: Handle duplicate messages gracefully
├── Event Schemas:
│   ├── CloudEvents: Standard event envelope format
│   │   ├── Properties: source, type, id, time, data
│   │   └── NuGet: CloudNative.CloudEvents
│   ├── Schema Registry: Confluent Schema Registry for Kafka
│   └── Contracts Package: Shared NuGet for event interfaces
├── Event Choreography vs Orchestration:
│   ├── Choreography: Events flow freely, Services react independently
│   │   ├── Pros: Loose coupling, No single point of failure
│   │   ├── Cons: Hard to understand flow, Difficult debugging
│   │   └── Use when: Simple flows, Few services involved
│   ├── Orchestration: Central coordinator manages flow
│   │   ├── Pros: Clear flow, Easy to understand, Centralized error handling
│   │   ├── Cons: Coordinator can become bottleneck
│   │   └── Use when: Complex flows, Many services, Need visibility
│   └── Hybrid: Orchestrate within bounded context, Choreograph between contexts
└── Eventual Consistency:
    ├── Embrace it: Most business processes are naturally eventual
    ├── UI Patterns: Optimistic updates, Polling, WebSocket notifications
    ├── Compensation: Undo actions on failure (Saga)
    └── Monitoring: Track event lag, Alert on processing delays
```

### Section 8.3.2 — Distributed Transactions & Consistency
```
├── Two-Phase Commit (2PC):
│   ├── TransactionScope in .NET: Promotes to distributed transaction
│   ├── MSDTC: Microsoft Distributed Transaction Coordinator (Windows)
│   ├── Problems: Blocking, Coordinator failure, Performance
│   └── Recommendation: AVOID in microservices (use Saga instead)
├── Saga Pattern (Detailed):
│   ├── Implementation Options:
│   │   ├── MassTransit StateMachine: Full saga support
│   │   ├── Wolverine: Built-in saga support
│   │   ├── Temporal: Durable execution / Workflow engine
│   │   │   └── Temporal.Client for .NET
│   │   └── Custom: State machine with database persistence
│   ├── Example — Order Processing Saga:
│   │   ├── Step 1: Create Order → OrderCreated
│   │   ├── Step 2: Reserve Inventory → InventoryReserved / InventoryFailed
│   │   ├── Step 3: Process Payment → PaymentProcessed / PaymentFailed
│   │   ├── Step 4: Ship Order → OrderShipped
│   │   ├── Compensation: PaymentFailed → Release Inventory → Cancel Order
│   │   └── Timeout: If no response in 30s → Compensate
│   └── Testing:
│       ├── MassTransit Test Harness: Simulate saga flows
│       ├── State assertions: Verify saga reached expected state
│       └── Compensation tests: Verify rollback on failure
├── Idempotent Operations:
│   ├── Idempotency Key: Client-generated UUID per operation
│   ├── Storage: Redis (fast) or Database (durable)
│   ├── Pattern:
│   │   ├── Receive request with IdempotencyKey header
│   │   ├── Check if key exists → Return cached response
│   │   ├── If not → Process → Store key + response → Return
│   │   └── TTL: 24-48 hours
│   └── Database Level: UPSERT (INSERT ON CONFLICT), Unique constraints
└── Distributed Locking:
    ├── Redis: RedLock algorithm (StackExchange.Redis.Extensions)
    ├── PostgreSQL: Advisory locks (pg_advisory_lock)
    ├── When: Prevent duplicate processing, Resource coordination
    ├── Lease-based: Lock with expiry (prevent deadlocks)
    └── Caution: Minimize lock scope, Prefer idempotency over locking
```

### Section 8.3.3 — API Gateway & BFF Pattern
```
├── YARP Gateway:
│   ├── Central entry point for all microservices
│   ├── Configuration:
│   │   "Routes": [{
│   │       "RouteId": "orders-route",
│   │       "ClusterId": "orders-cluster",
│   │       "Match": { "Path": "/api/orders/{**catch-all}" }
│   │   }]
│   │   "Clusters": [{
│   │       "ClusterId": "orders-cluster",
│   │       "Destinations": {
│   │           "orders-1": { "Address": "http://order-service:8080/" }
│   │       }
│   │   }]
│   ├── Rate Limiting: Per-route, Per-user, Global
│   ├── Authentication: Validate JWT at gateway level
│   ├── Circuit Breaker: YARP health checks + remove unhealthy destinations
│   └── Request Transformation: Add headers, Rewrite paths
├── BFF (Backend for Frontend):
│   ├── ASP.NET Core API that aggregates multiple microservice calls
│   ├── One BFF per client type: Web BFF, Mobile BFF
│   ├── GraphQL Gateway: Hot Chocolate gateway stitching multiple schemas
│   ├── Responsibilities:
│   │   ├── Aggregate data from multiple services
│   │   ├── Transform data for specific client needs
│   │   ├── Handle authentication (cookie → JWT translation)
│   │   └── Cache aggregated responses
│   └── Anti-pattern: BFF becoming a monolith (keep it thin)
└── Service Mesh Integration:
    ├── Istio/Linkerd: Sidecar proxy handles networking concerns
    ├── mTLS: Automatic mutual TLS between services
    ├── Traffic Management: Canary, A/B testing, Circuit breaking
    └── .NET Impact: Service mesh handles resilience externally
```

---

## Module 8.4: Multi-Service Observability

### Section 8.4.1 — Distributed Tracing Across Services
```
├── Trace Propagation:
│   ├── W3C TraceContext: Automatic in ASP.NET Core + HttpClient
│   ├── MassTransit: Automatic trace propagation in messages
│   ├── gRPC: Automatic metadata propagation
│   ├── Custom: Add traceId to message headers manually
│   └── Correlation ID: Additional business-level correlation
├── Full Observability Stack:
│   ├── Tracing: OpenTelemetry → OTLP → Jaeger/Tempo
│   ├── Metrics: OpenTelemetry → OTLP → Prometheus → Grafana
│   ├── Logging: Serilog → OTLP → Loki → Grafana
│   └── Single Pane: Grafana dashboards with trace-to-log correlation
├── Per-Service Dashboards:
│   ├── RED Metrics: Request Rate, Error Rate, Duration (P50/P95/P99)
│   ├── Resource Usage: CPU, Memory, GC, Thread pool
│   ├── Business Metrics: Orders/sec, Revenue, Active users
│   └── Infrastructure: Database connections, Cache hit rate, Queue depth
├── Alerting:
│   ├── SLO-based: Error budget burn rate alerts
│   ├── Anomaly Detection: Sudden spike in errors, Latency degradation
│   ├── Business Alerts: Order processing stopped, Payment failures spike
│   └── Runbooks: Every alert links to remediation steps
├── Centralized Logging:
│   ├── Structured JSON logs with:
│   │   ├── TraceId, SpanId (automatic with OpenTelemetry)
│   │   ├── ServiceName, Environment
│   │   ├── UserId, TenantId (from middleware)
│   │   ├── CorrelationId (business-level)
│   │   └── Custom properties (OrderId, ProductId, etc.)
│   ├── Tools: Seq (development), Loki (production), Elasticsearch
│   └── Querying: Search across services by TraceId or CorrelationId
└── .NET Aspire Dashboard:
    ├── Local development: All traces, logs, metrics in one view
    ├── Service dependency visualization
    └── Error investigation: Click trace → See all spans → Find error
```

---

## Module 8.5: Monorepo vs Polyrepo & Solution Organization

### Section 8.5.1 — Repository Strategies
```
├── Monorepo:
│   ├── All services in one repository
│   ├── Tools: Nx, Turborepo, Bazel, dotnet solution structure
│   ├── Pros: Atomic changes, Shared code, Consistent tooling
│   ├── Cons: Large repo, Build times, Permission management
│   └── .NET: Single .sln with multiple service projects
│       ├── src/
│       │   ├── Services/
│       │   │   ├── OrderService/
│       │   │   │   ├── Order.API/
│       │   │   │   ├── Order.Application/
│       │   │   │   ├── Order.Domain/
│       │   │   │   └── Order.Infrastructure/
│       │   │   ├── ProductService/
│       │   │   │   └── ...
│       │   │   └── PaymentService/
│       │   │       └── ...
│       │   ├── BuildingBlocks/
│       │   │   ├── BuildingBlocks.Domain/
│       │   │   ├── BuildingBlocks.Messaging/
│       │   │   └── BuildingBlocks.Infrastructure/
│       │   └── ApiGateway/
│       ├── tests/
│       └── deploy/
├── Polyrepo:
│   ├── One repository per service
│   ├── Pros: Independent teams, Focused repos, Clear ownership
│   ├── Cons: Cross-service changes hard, Dependency management
│   └── Shared Code: NuGet packages in private feed
└── Hybrid:
    ├── Monorepo per bounded context
    ├── Shared libraries as NuGet packages
    └── Recommended for most teams
```

---

> ### 🛠️ PHASE 8 PROJECT: **Full E-Commerce Microservices Platform**
> ```
> ┌─────────────────────────────────────────────────────────────────────────┐
> │           FULL E-COMMERCE MICROSERVICES PLATFORM                       │
> ├─────────────────────────────────────────────────────────────────────────┤
> │                                                                         │
> │                        ┌──────────────────┐                             │
> │    Clients ──────────→ │   YARP Gateway   │                             │
> │    (Web, Mobile)       │  (Auth, Rate     │                             │
> │                        │   Limiting)      │                             │
> │                        └────────┬─────────┘                             │
> │                    ┌────────────┼────────────┬───────────┐              │
> │                    ▼            ▼            ▼           ▼              │
> │              ┌──────────┐┌──────────┐┌──────────┐┌───────────┐        │
> │              │ Product  ││  Order   ││ Payment  ││ Notification│       │
> │              │ Service  ││ Service  ││ Service  ││  Service   │        │
> │              │(Minimal  ││(Clean   ││(Clean    ││(Background ││        │
> │              │ API+EF)  ││Arch+ES) ││Arch)     ││ Workers)   │        │
> │              └────┬─────┘└────┬─────┘└────┬─────┘└─────┬─────┘        │
> │                   │           │           │             │              │
> │              ┌────┴───┐ ┌────┴───┐ ┌────┴───┐    ┌────┴───┐          │
> │              │Postgres│ │Postgres│ │Postgres│    │  SMTP  │          │
> │              │+Redis  │ │(Marten)│ │        │    │ +Twilio│          │
> │              └────────┘ └────────┘ └────────┘    └────────┘          │
> │                                                                        │
> │              ┌─────────────────────────────────┐                       │
> │              │          RabbitMQ               │                       │
> │              │  (MassTransit Message Broker)   │                       │
> │              └─────────────────────────────────┘                       │
> │                                                                        │
> │              ┌─────────────────────────────────┐                       │
> │              │     .NET Aspire App Host        │                       │
> │              │  (Local Dev Orchestration)       │                       │
> │              └─────────────────────────────────┘                       │
> │                                                                        │
> │ Services:                                                              │
> │                                                                        │
> │ 📦 Product Service:                                                    │
> │  ✅ Minimal APIs + EF Core (PostgreSQL)                                │
> │  ✅ Redis caching for catalog                                          │
> │  ✅ Full-text search with PostgreSQL GIN indexes                       │
> │  ✅ CRUD with image upload to S3/MinIO                                 │
> │  ✅ Publishes: ProductCreated, ProductUpdated, PriceChanged            │
> │                                                                        │
> │ 🛒 Order Service:                                                      │
> │  ✅ Clean Architecture + CQRS + MediatR                                │
> │  ✅ Event Sourcing with Marten (PostgreSQL)                            │
> │  ✅ Order Saga: Orchestration with MassTransit StateMachine            │
> │  ✅ Saga states: Submitted→PaymentPending→Paid→Shipped→Completed      │
> │  ✅ Compensation: Payment failure → Release inventory → Cancel order   │
> │  ✅ Read model: Dapper queries on denormalized projection tables       │
> │  ✅ Publishes: OrderPlaced, OrderCompleted, OrderCancelled             │
> │                                                                        │
> │ 💳 Payment Service:                                                    │
> │  ✅ Clean Architecture + EF Core                                       │
> │  ✅ Stripe integration via Adapter pattern                             │
> │  ✅ Idempotency keys on all payment operations                         │
> │  ✅ Resilience: Circuit breaker + Retry on Stripe API                  │
> │  ✅ Webhook handling: Stripe webhooks → Internal events                │
> │  ✅ Outbox pattern: MassTransit EF Core outbox                         │
> │  ✅ Publishes: PaymentProcessed, PaymentFailed, RefundIssued           │
> │                                                                        │
> │ 🔔 Notification Service:                                              │
> │  ✅ BackgroundService consumers: Email, SMS, Push                      │
> │  ✅ Template engine: Razor templates for emails                        │
> │  ✅ Resilience: Retry with exponential backoff on SMTP/Twilio          │
> │  ✅ Consumes: OrderPlaced → Send confirmation email                    │
> │  ✅ Consumes: OrderShipped → Send tracking notification                │
> │                                                                        │
> │ Cross-Cutting:                                                         │
> │  ✅ .NET Aspire: Orchestrate all services + dependencies locally       │
> │  ✅ YARP API Gateway: Auth, Rate limiting, Routing                     │
> │  ✅ OpenTelemetry: Distributed traces across all services              │
> │  ✅ Serilog: Structured logging → Seq (dev) / Loki (prod)             │
> │  ✅ Grafana: Dashboards per service + Business metrics                 │
> │  ✅ Health checks: Per-service + Aggregated at gateway                  │
> │  ✅ Integration tests: WebApplicationFactory + Testcontainers           │
> │  ✅ Architecture tests: NetArchTest for layer dependencies             │
> │  ✅ Contract tests: PactNet between services                           │
> │  ✅ Docker Compose: Full local stack                                    │
> │  ✅ Kubernetes: Helm charts for each service                           │
> │  ✅ CI/CD: GitHub Actions → Build → Test → Docker → Deploy             │
> │  ✅ ADRs: 15+ decisions documented                                     │
> │  ✅ C4 Diagrams: Full system architecture                              │
> └─────────────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 📚 COMPLETE ASP.NET READING LIST & RESOURCES

```
┌──────────┬───────────────────────────────────────────────────────────────────┐
│  PHASE   │  BOOKS & RESOURCES                                               │
├──────────┼───────────────────────────────────────────────────────────────────┤
│          │  📖 C# in Depth (4th Ed) — Jon Skeet                             │
│  PHASE 1 │  📖 Concurrency in C# Cookbook — Stephen Cleary                   │
│          │  📖 Pro .NET Memory Management — Konrad Kokosa                    │
│          │  🌐 learn.microsoft.com/dotnet (official docs)                   │
├──────────┼───────────────────────────────────────────────────────────────────┤
│          │  📖 ASP.NET Core in Action (3rd Ed) — Andrew Lock                 │
│  PHASE 2 │  📖 Minimal APIs in ASP.NET Core — Andrea Tosato et al.          │
│          │  🌐 andrewlock.net (excellent blog)                               │
│          │  🎥 Nick Chapsas YouTube channel                                  │
├──────────┼───────────────────────────────────────────────────────────────────┤
│          │  📖 gRPC for .NET Developers — Microsoft docs                     │
│  PHASE 3 │  📖 ASP.NET Core 8 and Angular — Valerio De Sanctis              │
│          │  🌐 Hot Chocolate docs (chillicream.com)                          │
│          │  🌐 learn.microsoft.com/aspnet/signalr                           │
├──────────┼───────────────────────────────────────────────────────────────────┤
│          │  📖 Entity Framework Core in Action (2nd Ed) — Jon P Smith        │
│  PHASE 4 │  📖 Dapper documentation (dapperlib.github.io)                    │
│          │  🌐 EF Core docs (learn.microsoft.com/ef)                        │
│          │  🎥 Milan Jovanović YouTube channel                               │
├──────────┼───────────────────────────────────────────────────────────────────┤
│          │  📖 ASP.NET Core Security — Christian Wenz                        │
│  PHASE 5 │  📖 OAuth 2 in Action — Justin Richer                            │
│          │  🌐 Duende IdentityServer docs                                    │
│          │  🌐 OWASP ASP.NET Core Security Cheat Sheet                       │
├──────────┼───────────────────────────────────────────────────────────────────┤
│          │  📖 Unit Testing Principles — Vladimir Khorikov                   │
│  PHASE 6 │  📖 Growing Object-Oriented Software — Freeman & Pryce           │
│          │  🌐 Testcontainers for .NET docs                                  │
│          │  🌐 FluentAssertions docs                                         │
├──────────┼───────────────────────────────────────────────────────────────────┤
│          │  📖 .NET Microservices — Microsoft Architecture Guide (free)      │
│  PHASE 7 │  📖 Pro .NET Benchmarking — Andrey Akinshin                      │
│    & 8   │  📖 Building Event-Driven Microservices — Adam Bellemare          │
│          │  📖 Microservices Patterns — Chris Richardson                     │
│          │  🌐 MassTransit docs (masstransit.io)                            │
│          │  🌐 .NET Aspire docs (learn.microsoft.com/dotnet/aspire)         │
│          │  🌐 Wolverine docs (wolverine.netlify.app)                       │
│          │  🎥 dotnet-architecture GitHub repos (eShop reference app)       │
│          │  🎥 CodeOpinion YouTube (Derek Comartin) — Messaging patterns    │
└──────────┴───────────────────────────────────────────────────────────────────┘
```

---

# 🧭 COMPLETE ASP.NET VISUAL MAP

```
╔═══════════════════════════════════════════════════════════════════════════════════════╗
║                                                                                       ║
║  PHASE 8 ━━ MICROSERVICES & DISTRIBUTED ━━━━━━━━━━━━━━━━━ [Architect]                ║
║  ┃                                                                                    ║
║  ┣━ 8.1 Service Architecture    (Clean Arch per service, Communication, Discovery)   ║
║  ┣━ 8.2 .NET Aspire             (App Host, Components, Service Discovery, Deploy)    ║
║  ┣━ 8.3 Distributed Patterns    (Saga, CQRS, Event Sourcing, Outbox, CDC)           ║
║  ┣━ 8.4 Multi-Service Observe   (Distributed Tracing, Centralized Logging, Alerts)  ║
║  ┗━ 8.5 Repo Organization       (Monorepo vs Polyrepo, Solution structure)           ║
║      ▲                                                                                ║
║  PHASE 7 ━━ PERFORMANCE, SCALABILITY & DEVOPS ━━━━━━━━━━ [Senior Developer]          ║
║  ┃                                                                                    ║
║  ┣━ 7.1 Performance             (Kestrel, Memory, AOT, Profiling, DB perf)           ║
║  ┣━ 7.2 Observability           (OpenTelemetry, Serilog, Aspire Dashboard)           ║
║  ┣━ 7.3 Deployment & DevOps     (Docker, K8s, Helm, CI/CD, Cloud)                   ║
║  ┣━ 7.4 Resilience              (Polly v8, HTTP Resilience, Health, Idempotency)     ║
║  ┗━ 7.5 Messaging               (MassTransit, Wolverine, RabbitMQ, Kafka)           ║
║      ▲                                                                                ║
║  PHASE 6 ━━ TESTING & QUALITY ━━━━━━━━━━━━━━━━━━━━━━━━━━ [Senior Developer]          ║
║  ┃                                                                                    ║
║  ┣━ 6.1 Unit Testing            (xUnit, FluentAssertions, Moq, Bogus, Coverage)     ║
║  ┣━ 6.2 Integration Testing     (WebApplicationFactory, Testcontainers, Respawn)     ║
║  ┗━ 6.3 Architecture & E2E      (ArchUnit, Playwright, NBomber, Contract Tests)      ║
║      ▲                                                                                ║
║  PHASE 5 ━━ SECURITY & IDENTITY ━━━━━━━━━━━━━━━━━━━━━━━━ [Mid-Senior Developer]      ║
║  ┃                                                                                    ║
║  ┣━ 5.1 Authentication          (Identity, JWT, OAuth2/OIDC, Cookies, Refresh)       ║
║  ┣━ 5.2 Authorization           (Roles, Claims, Policies, Resource-based)            ║
║  ┗━ 5.3 Application Security    (OWASP, CORS, CSRF, Rate Limiting, Headers)          ║
║      ▲                                                                                ║
║  PHASE 4 ━━ DATA ACCESS & DATABASE ━━━━━━━━━━━━━━━━━━━━━ [Mid-Level Developer]       ║
║  ┃                                                                                    ║
║  ┣━ 4.1 EF Core Deep Dive       (Config, Queries, Migrations, Interceptors, JSON)   ║
║  ┣━ 4.2 Dapper                  (Raw SQL, Multi-mapping, EF+Dapper together)        ║
║  ┣━ 4.3 Caching                 (Memory, Redis, Output, HybridCache, Patterns)      ║
║  ┗━ 4.4 Repository & UoW        (Specific repos, Specification, Domain Events)       ║
║      ▲                                                                                ║
║  PHASE 3 ━━ API DEVELOPMENT & COMMUNICATION ━━━━━━━━━━━━ [Mid-Level Developer]       ║
║  ┃                                                                                    ║
║  ┣━ 3.1 REST API Design         (Design, Versioning, Pagination, MediatR, CQRS)     ║
║  ┣━ 3.2 GraphQL                 (Hot Chocolate, DataLoaders, Subscriptions)          ║
║  ┣━ 3.3 gRPC                    (Protobuf, Streaming, Interceptors, gRPC-Web)       ║
║  ┣━ 3.4 SignalR                 (Hubs, Groups, Scaling, Redis Backplane)             ║
║  ┗━ 3.5 Reverse Proxy           (YARP, BFF Pattern, API Gateway)                    ║
║      ▲                                                                                ║
║  PHASE 2 ━━ ASP.NET CORE FUNDAMENTALS ━━━━━━━━━━━━━━━━━━ [Junior+ Developer]         ║
║  ┃                                                                                    ║
║  ┣━ 2.1 Architecture            (Hosting, Middleware Pipeline, Routing, Binding)     ║
║  ┣━ 2.2 Web Frameworks          (Minimal APIs, MVC, Razor Pages, Blazor)            ║
║  ┣━ 2.3 Cross-Cutting           (Error Handling, Health Checks, Static Files)        ║
║  ┗━ 2.4 Background Services     (IHostedService, Channels, Hangfire, Quartz)         ║
║      ▲                                                                                ║
║  PHASE 1 ━━ C# & .NET FOUNDATIONS ━━━━━━━━━━━━━━━━━━━━━━ [Starting Point]            ║
║  ┃                                                                                    ║
║  ┣━ 1.1 C# Fundamentals         (Syntax, OOP, Generics, Delegates, LINQ)            ║
║  ┣━ 1.2 Advanced C#             (async/await, Error Handling, C# 10-13, Memory)     ║
║  ┣━ 1.3 .NET Ecosystem          (Runtime, CLI, NuGet, Config, DI, Logging, Aspire)  ║
║  ┗━ 1.4 SOLID Principles        (SRP, OCP, LSP, ISP, DIP with C# examples)         ║
║                                                                                       ║
╚═══════════════════════════════════════════════════════════════════════════════════════╝

TOTAL: 8 Phases │ 30 Modules │ 90+ Sections │ 8 Milestone Projects │ 20+ Books
TIMELINE: ~20 months (accelerate based on prior experience)
```

---

# 🔧 ESSENTIAL NUGET PACKAGES (By Category)

```
┌─────────────────────────┬────────────────────────────────────────────────────┐
│  CATEGORY               │  PACKAGES                                         │
├─────────────────────────┼────────────────────────────────────────────────────┤
│  Web Framework          │  ASP.NET Core (built-in), Carter, FastEndpoints   │
├─────────────────────────┼────────────────────────────────────────────────────┤
│  Data Access            │  EF Core, Npgsql, Dapper, Marten                 │
├─────────────────────────┼────────────────────────────────────────────────────┤
│  CQRS / Mediator        │  MediatR, Wolverine                              │
├─────────────────────────┼────────────────────────────────────────────────────┤
│  Validation             │  FluentValidation, MiniValidation                 │
├─────────────────────────┼────────────────────────────────────────────────────┤
│  Mapping                │  AutoMapper, Mapster, Mapperly (source gen)       │
├─────────────────────────┼────────────────────────────────────────────────────┤
│  Messaging              │  MassTransit, Wolverine, CAP, Confluent.Kafka    │
├─────────────────────────┼────────────────────────────────────────────────────┤
│  GraphQL                │  HotChocolate                                     │
├─────────────────────────┼────────────────────────────────────────────────────┤
│  gRPC                   │  Grpc.AspNetCore, Google.Protobuf                │
├─────────────────────────┼────────────────────────────────────────────────────┤
│  Real-Time              │  SignalR (built-in)                               │
├─────────────────────────┼────────────────────────────────────────────────────┤
│  Resilience             │  Polly, Microsoft.Extensions.Http.Resilience     │
├─────────────────────────┼────────────────────────────────────────────────────┤
│  Caching                │  StackExchange.Redis, HybridCache (built-in)     │
├─────────────────────────┼────────────────────────────────────────────────────┤
│  Auth                   │  ASP.NET Identity, Duende IdentityServer,        │
│                         │  OpenIddict                                       │
├─────────────────────────┼────────────────────────────────────────────────────┤
│  Logging                │  Serilog, Serilog.Sinks.*, Seq                   │
├─────────────────────────┼────────────────────────────────────────────────────┤
│  Observability          │  OpenTelemetry.*, Application Insights           │
├─────────────────────────┼────────────────────────────────────────────────────┤
│  API Documentation      │  Swashbuckle, NSwag, Scalar                      │
├─────────────────────────┼────────────────────────────────────────────────────┤
│  Reverse Proxy          │  YARP                                             │
├─────────────────────────┼────────────────────────────────────────────────────┤
│  HTTP Clients           │  Refit, Flurl                                     │
├─────────────────────────┼────────────────────────────────────────────────────┤
│  Scheduling             │  Hangfire, Quartz.NET                             │
├─────────────────────────┼────────────────────────────────────────────────────┤
│  Cloud-Native           │  .NET Aspire Components                           │
├─────────────────────────┼────────────────────────────────────────────────────┤
│  Testing                │  xUnit, FluentAssertions, Moq / NSubstitute,     │
│                         │  Testcontainers, Respawn, Bogus, WireMock.Net,   │
│                         │  NetArchTest, NBomber, BenchmarkDotNet,          │
│                         │  Verify, Playwright                               │
├─────────────────────────┼────────────────────────────────────────────────────┤
│  DI Extensions          │  Scrutor (assembly scanning + decoration)        │
├─────────────────────────┼────────────────────────────────────────────────────┤
│  Security Headers       │  NetEscapades.AspNetCore.SecurityHeaders          │
├─────────────────────────┼────────────────────────────────────────────────────┤
│  Architecture           │  Ardalis.Specification, Ardalis.Result,          │
│                         │  ErrorOr, FluentResults, OneOf                    │
└─────────────────────────┴────────────────────────────────────────────────────┘
```

---

# ⚡ ASP.NET GOLDEN RULES

```
┌─────┬─────────────────────────────────────────────────────────────────────────┐
│  #  │  RULE                                                                  │
├─────┼─────────────────────────────────────────────────────────────────────────┤
│  1  │  Master C# BEFORE ASP.NET. The framework changes, the language         │
│     │  fundamentals don't.                                                    │
├─────┼─────────────────────────────────────────────────────────────────────────┤
│  2  │  async/await ALL THE WAY. Never mix sync and async. Never use          │
│     │  .Result or .Wait(). This is the #1 source of production bugs.         │
├─────┼─────────────────────────────────────────────────────────────────────────┤
│  3  │  Use IHttpClientFactory. Never new HttpClient(). Socket                │
│     │  exhaustion and DNS caching will bite you in production.               │
├─────┼─────────────────────────────────────────────────────────────────────────┤
│  4  │  DbContext is SCOPED. Never inject DbContext into Singletons.          │
│     │  Understand service lifetimes (Transient/Scoped/Singleton).            │
├─────┼─────────────────────────────────────────────────────────────────────────┤
│  5  │  Never expose domain entities via API. Always use DTOs.                │
│     │  Your database schema ≠ your API contract.                             │
├─────┼─────────────────────────────────────────────────────────────────────────┤
│  6  │  Use .AsNoTracking() for read-only queries. It's a free                │
│     │  performance boost. Inspect generated SQL with .ToQueryString().       │
├─────┼─────────────────────────────────────────────────────────────────────────┤
│  7  │  Middleware order MATTERS. Exception handling first, then static       │
│     │  files, then routing, then auth, then endpoints.                       │
├─────┼─────────────────────────────────────────────────────────────────────────┤
│  8  │  Validate everything. Use FluentValidation. Never trust input.        │
│     │  Return Problem Details (RFC 7807) for all errors.                    │
├─────┼─────────────────────────────────────────────────────────────────────────┤
│  9  │  Start with a Modular Monolith. Don't start with microservices.       │
│     │  Extract services when you have clear bounded contexts and team        │
│     │  scaling needs.                                                        │
├─────┼─────────────────────────────────────────────────────────────────────────┤
│ 10  │  Use .NET Aspire for new projects. It gives you observability,        │
│     │  resilience, service discovery, and local orchestration for FREE.      │
├─────┼─────────────────────────────────────────────────────────────────────────┤
│ 11  │  Structured logging from Day 1. Serilog + Seq (dev) + OTLP (prod).   │
│     │  Log WITH context: {OrderId}, {UserId}, not string concatenation.     │
├─────┼─────────────────────────────────────────────────────────────────────────┤
│ 12  │  Stay on latest LTS. Currently .NET 8. Upgrade promptly.              │
│     │  Follow .NET release cycle (LTS every 2 years).                       │
└─────┴─────────────────────────────────────────────────────────────────────────┘
```

---

# 🎯 KEY YOUTUBE CHANNELS & BLOGS TO FOLLOW

```
┌─────────────────────────────────┬─────────────────────────────────────────────┐
│  RESOURCE                       │  FOCUS                                      │
├─────────────────────────────────┼─────────────────────────────────────────────┤
│  🎥 Nick Chapsas                │  Modern C# & ASP.NET Core deep dives       │
│  🎥 Milan Jovanović             │  Clean Architecture, DDD, ASP.NET patterns │
│  🎥 CodeOpinion (Derek Comartin)│  Architecture, Messaging, CQRS             │
│  🎥 Raw Coding (Anton)          │  Auth, Identity, Advanced ASP.NET Core     │
│  🎥 dotnet (Official)           │  .NET Conf, What's new, Tutorials          │
│  🎥 Tim Corey (IAmTimCorey)     │  Beginner-friendly C# & ASP.NET            │
│  🌐 Andrew Lock (.NET Escapades)│  Deep-dive ASP.NET Core blog posts         │
│  🌐 Steve Smith (Ardalis)       │  Clean Architecture, Specifications        │
│  🌐 Khalid Abuhakmeh            │  .NET Tips, Tricks, and Tutorials          │
│  🌐 Jimmy Bogard                │  MediatR creator, AutoMapper, DDD          │
│  🌐 Jeremy Miller               │  Wolverine, Marten, Lamar creator          │
│  🌐 Chris Pattinson (MassTransit)│ MassTransit docs & patterns              │
│  🌐 Microsoft Learn             │  Official docs (gold standard)             │
│  🌐 .NET Blog (devblogs.microsoft)│ Official announcements & deep dives     │
└─────────────────────────────────┴─────────────────────────────────────────────┘
```

---

> *"ASP.NET Core is the most complete enterprise web framework in the .NET ecosystem. Master it piece by piece, build projects at every phase, and always optimize for clarity over cleverness."*