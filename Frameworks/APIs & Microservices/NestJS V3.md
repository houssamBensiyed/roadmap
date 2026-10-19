# 🐈 THE ULTIMATE NestJS ROADMAP
## From Zero to NestJS Master — Every Concept, Every Layer

---

```
╔══════════════════════════════════════════════════════════════════════════════════════╗
║                           NestJS — MASTERY LADDER                                    ║
║                                                                                      ║
║   🏆 PHASE 7 ─ Enterprise & Production Patterns       [NestJS Expert / Architect]   ║
║       ▲                                                                              ║
║   🤖 PHASE 6 ─ Real-Time, GraphQL & Advanced APIs     [Advanced Developer]           ║
║       ▲                                                                              ║
║   🔒 PHASE 5 ─ Security, Auth & Access Control        [Mid-Senior Developer]         ║
║       ▲                                                                              ║
║   🗄️ PHASE 4 ─ Data Layer & Database Mastery           [Mid-Level Developer]          ║
║       ▲                                                                              ║
║   🧩 PHASE 3 ─ Core Architecture Deep Dive            [Junior+ Developer]            ║
║       ▲                                                                              ║
║   ⚙️ PHASE 2 ─ NestJS Building Blocks                  [Beginner+]                   ║
║       ▲                                                                              ║
║   🧱 PHASE 1 ─ Prerequisites & Foundations             [Starting Point]              ║
║                                                                                      ║
╚══════════════════════════════════════════════════════════════════════════════════════╝
```

---
---
---

# 🧱 PHASE 1: PREREQUISITES & FOUNDATIONS
### 📅 Duration: Weeks 1–3
### 🎯 Goal: Master everything you need BEFORE touching NestJS
### 👤 Level: Starting Point

---

## Module 1.1: TypeScript Mastery (Non-Negotiable)

### Section 1.1.1 — TypeScript Core
```
├── Type System:
│   ├── Primitive Types: string, number, boolean, null, undefined, symbol, bigint
│   ├── Special Types: any, unknown, never, void
│   ├── Object Types: Interfaces vs Type Aliases — when to use each
│   ├── Arrays & Tuples: Typed arrays, Fixed-length tuples
│   ├── Enums: String enums, Numeric enums, Const enums
│   └── Literal Types: String literals, Numeric literals, Template literals
├── Union & Intersection Types:
│   ├── Union (|): "This OR That"
│   ├── Intersection (&): "This AND That"
│   ├── Discriminated Unions: Tagged unions with type narrowing
│   └── Type Guards: typeof, instanceof, in, Custom type guards (is keyword)
├── Functions:
│   ├── Parameter Types & Return Types
│   ├── Optional & Default Parameters
│   ├── Rest Parameters: ...args: string[]
│   ├── Function Overloads: Multiple signatures, Single implementation
│   └── Arrow Functions vs Function Declarations: `this` binding
├── Type Assertions & Narrowing:
│   ├── as keyword: Type assertion (use sparingly)
│   ├── Non-null assertion (!): Dangerous, Avoid when possible
│   ├── Type Narrowing: Control flow analysis, Type guards
│   └── Satisfies Operator: Validate type without widening
└── Strict Mode: Enable ALL strict flags — no shortcuts
```

### Section 1.1.2 — TypeScript Advanced
```
├── Generics:
│   ├── Generic Functions: function identity<T>(arg: T): T
│   ├── Generic Interfaces & Classes
│   ├── Generic Constraints: <T extends SomeType>
│   ├── Default Generics: <T = string>
│   ├── Multiple Type Parameters: <T, U, R>
│   └── Why This Matters for NestJS: Custom decorators, Repositories, Services
├── Utility Types:
│   ├── Partial<T>: All properties optional
│   ├── Required<T>: All properties required
│   ├── Readonly<T>: All properties readonly
│   ├── Pick<T, K>: Select specific properties
│   ├── Omit<T, K>: Exclude specific properties
│   ├── Record<K, V>: Object with typed keys and values
│   ├── Exclude<T, U> & Extract<T, U>: Union type manipulation
│   ├── ReturnType<T> & Parameters<T>: Function type extraction
│   └── NonNullable<T>: Remove null/undefined
├── Advanced Types:
│   ├── Mapped Types: { [K in keyof T]: ... }
│   ├── Conditional Types: T extends U ? X : Y
│   ├── Template Literal Types: `${string}Controller`
│   ├── Index Access Types: T[K], T["property"]
│   └── Infer Keyword: Type inference in conditional types
├── Decorators (CRITICAL for NestJS):
│   ├── What Are Decorators: Metadata attachment, @ syntax
│   ├── Class Decorators: @Controller(), @Injectable(), @Module()
│   ├── Method Decorators: @Get(), @Post(), @UseGuards()
│   ├── Property Decorators: @Inject(), @Column()
│   ├── Parameter Decorators: @Body(), @Param(), @Query()
│   ├── Decorator Factories: Functions that return decorators
│   ├── Decorator Composition: Stacking multiple decorators
│   ├── reflect-metadata: Metadata reflection API
│   └── experimentalDecorators vs TC39 Decorators: Current state
└── Module System:
    ├── ES Modules: import/export, Named vs Default exports
    ├── Module Resolution: Relative vs Non-relative, paths/baseUrl in tsconfig
    ├── Barrel Files: index.ts re-exports (pros and cons)
    └── Declaration Files: .d.ts, @types packages, Triple-slash directives
```

### Section 1.1.3 — tsconfig.json for NestJS
```
├── Key Compiler Options:
│   ├── "target": "ES2021" — Modern JS output
│   ├── "module": "commonjs" — Node.js module system
│   ├── "strict": true — ALL strict checks enabled
│   ├── "experimentalDecorators": true — REQUIRED for NestJS
│   ├── "emitDecoratorMetadata": true — REQUIRED for NestJS DI
│   ├── "esModuleInterop": true — CommonJS/ESM interop
│   ├── "skipLibCheck": true — Faster builds, Skip .d.ts checking
│   ├── "forceConsistentCasingInImports": true — Cross-platform safety
│   ├── "strictNullChecks": true — Null safety
│   └── "strictPropertyInitialization": true — Ensure constructor initialization
├── Path Aliases: "@modules/*", "@shared/*", "@config/*"
└── Include/Exclude: src/**/*.ts, Exclude node_modules, dist, test
```

---

## Module 1.2: Node.js Fundamentals

### Section 1.2.1 — Node.js Runtime
```
├── Event Loop:
│   ├── Phases: Timers → Pending Callbacks → Idle → Poll → Check → Close
│   ├── Microtasks: process.nextTick, Promise callbacks (run between phases)
│   ├── Macrotasks: setTimeout, setInterval, setImmediate, I/O callbacks
│   └── Why This Matters: Understanding async behavior in NestJS
├── Module System:
│   ├── CommonJS: require(), module.exports (Node.js default)
│   ├── ES Modules: import/export (Node.js native support)
│   └── NestJS Uses: CommonJS compilation from TypeScript
├── Streams:
│   ├── Readable, Writable, Duplex, Transform
│   ├── Backpressure: Handling fast producers, slow consumers
│   └── NestJS Usage: File uploads (StreamableFile), SSE
├── Buffers & Binary Data: Buffer class, Encoding, Decoding
├── Error Handling:
│   ├── Synchronous: try/catch
│   ├── Asynchronous: Promise.catch, async/await + try/catch
│   ├── Unhandled Rejections: process.on('unhandledRejection')
│   └── Uncaught Exceptions: process.on('uncaughtException')
├── File System: fs/promises, Path module, File operations
├── Child Processes: exec, spawn, fork — Worker threads
└── Environment:
    ├── process.env: Environment variables
    ├── dotenv: Loading .env files
    └── NestJS: @nestjs/config module (ConfigModule)
```

### Section 1.2.2 — npm & Package Management
```
├── package.json: dependencies, devDependencies, peerDependencies, scripts
├── Lock Files: package-lock.json (npm), yarn.lock, pnpm-lock.yaml
├── Semantic Versioning: ^1.0.0 (minor), ~1.0.0 (patch), 1.0.0 (exact)
├── npm Scripts: start, build, test, lint, format — lifecycle scripts
├── Workspaces: Monorepo support (npm, yarn, pnpm)
└── Package Managers: npm vs yarn vs pnpm — tradeoffs
    └── pnpm: Recommended for NestJS monorepos (faster, disk-efficient)
```

---

## Module 1.3: Foundational Concepts

### Section 1.3.1 — Object-Oriented Programming in TypeScript
```
├── Classes: Constructor, Properties, Methods, Access modifiers (public/private/protected)
├── Inheritance: extends, super(), Method overriding
├── Abstract Classes: Abstract methods, Partial implementations
├── Interfaces: Contracts, implements keyword, Multiple interfaces
├── Composition over Inheritance: Injecting dependencies, Delegation
├── SOLID Principles: Applied to TypeScript
│   ├── SRP: One class, One responsibility
│   ├── OCP: Extend via interfaces, Not modification
│   ├── LSP: Subtypes substitutable for base types
│   ├── ISP: Small, Focused interfaces
│   └── DIP: Depend on abstractions (NestJS DI makes this natural)
└── Design Patterns Preview:
    ├── Singleton: NestJS providers are singletons by default
    ├── Factory: Custom providers, useFactory
    ├── Strategy: Swappable service implementations
    ├── Observer: EventEmitter, NestJS event system
    └── Decorator: NestJS is BUILT on decorators
```

### Section 1.3.2 — HTTP & REST Fundamentals
```
├── HTTP Methods: GET, POST, PUT, PATCH, DELETE, OPTIONS, HEAD
├── Status Codes:
│   ├── 2xx: 200 OK, 201 Created, 204 No Content
│   ├── 3xx: 301 Moved Permanently, 304 Not Modified
│   ├── 4xx: 400 Bad Request, 401 Unauthorized, 403 Forbidden, 404 Not Found, 409 Conflict, 422 Unprocessable, 429 Too Many Requests
│   └── 5xx: 500 Internal Server Error, 502 Bad Gateway, 503 Service Unavailable
├── Headers: Content-Type, Authorization, Accept, Cache-Control, CORS headers
├── Request/Response Body: JSON, Form data, Multipart
├── REST Principles:
│   ├── Resources: /users, /users/:id, /users/:id/posts
│   ├── Stateless: No server-side session (per request)
│   ├── Uniform Interface: Consistent URL patterns, HTTP verbs
│   └── HATEOAS: Hypermedia links (rarely implemented)
├── Query Parameters: Filtering, Sorting, Pagination
│   └── Example: GET /users?page=1&limit=20&sort=name&order=asc
├── API Design:
│   ├── Naming: Nouns (not verbs), Plural (/users not /user)
│   ├── Nesting: /users/:userId/posts (max 2 levels deep)
│   ├── Versioning: /v1/users, /v2/users
│   └── Error Response Format: { statusCode, message, error, details }
└── Tools: Postman, Insomnia, HTTPie, curl
```

### Section 1.3.3 — Dependency Injection Concept
```
├── Problem: Tight coupling between classes
├── Concept: Don't create dependencies, RECEIVE them
├── Types:
│   ├── Constructor Injection: Dependencies in constructor (NestJS default)
│   ├── Setter Injection: Set via method
│   └── Interface Injection: Implement an injection interface
├── IoC Container: Framework manages object creation and wiring
│   └── NestJS: Built-in IoC container, Automatic resolution
├── Benefits:
│   ├── Testability: Swap real dependencies with mocks
│   ├── Flexibility: Change implementations without modifying consumers
│   ├── Loose Coupling: Classes don't know concrete types
│   └── Single Responsibility: Container handles wiring, Classes handle logic
└── Example Mental Model:
    ├── WITHOUT DI: class UserService { db = new Database(); }
    └── WITH DI: class UserService { constructor(private db: Database) {} }
```

---

> ### 🛠️ PHASE 1 PROJECT: **TypeScript REST API WITHOUT NestJS**
> ```
> ┌─────────────────────────────────────────────────────────────────┐
> │       PURE TypeScript + Express REST API (No NestJS!)           │
> ├─────────────────────────────────────────────────────────────────┤
> │                                                                 │
> │ Build a simple Bookmark Manager API using ONLY Express +        │
> │ TypeScript to understand WHAT NestJS abstracts away:            │
> │                                                                 │
> │ Features:                                                       │
> │  • CRUD for bookmarks (title, url, description, tags)           │
> │  • CRUD for tags                                                │
> │  • Manual class-based structure:                                │
> │    Controller → Service → Repository (in-memory array)          │
> │  • Manual dependency injection (constructor injection)          │
> │  • Custom middleware for logging                                │
> │  • Custom error handling middleware                             │
> │  • TypeScript strict mode, Interfaces for everything            │
> │  • Custom decorators: @Log() method decorator, @Validate()     │
> │                                                                 │
> │ Requirements:                                                   │
> │  ✅ Strict TypeScript with all compiler options                  │
> │  ✅ Manual DI — wire everything in a composition root            │
> │  ✅ Use generics for a base Repository<T>                        │
> │  ✅ Custom decorators using reflect-metadata                     │
> │  ✅ Error handling with custom exception classes                 │
> │  ✅ Unit tests with Jest + ts-jest                               │
> │                                                                 │
> │ Purpose: Appreciate what NestJS automates!                      │
> └─────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# ⚙️ PHASE 2: NestJS BUILDING BLOCKS
### 📅 Duration: Weeks 3–6
### 🎯 Goal: Understand every core building block of NestJS
### 👤 Level: Beginner+

---

## Module 2.1: Project Setup & CLI

### Section 2.1.1 — NestJS CLI
```
├── Installation: npm i -g @nestjs/cli
├── Create Project: nest new project-name
│   ├── Package Manager Selection: npm, yarn, pnpm
│   └── Default Structure:
│       ├── src/
│       │   ├── app.module.ts        ← Root module
│       │   ├── app.controller.ts    ← Root controller
│       │   ├── app.service.ts       ← Root service
│       │   ├── app.controller.spec.ts ← Root controller tests
│       │   └── main.ts              ← Entry point (bootstrap)
│       ├── test/
│       │   ├── app.e2e-spec.ts      ← E2E tests
│       │   └── jest-e2e.json        ← E2E Jest config
│       ├── nest-cli.json            ← NestJS CLI configuration
│       ├── tsconfig.json            ← TypeScript configuration
│       └── tsconfig.build.json      ← Build-specific TS config
├── Generate Commands:
│   ├── nest g module users          ← Generate module
│   ├── nest g controller users      ← Generate controller
│   ├── nest g service users         ← Generate service
│   ├── nest g resource users        ← Generate full CRUD resource (module + controller + service + DTOs + entity)
│   ├── nest g guard auth            ← Generate guard
│   ├── nest g interceptor logging   ← Generate interceptor
│   ├── nest g pipe validation       ← Generate pipe
│   ├── nest g filter http-exception ← Generate filter
│   ├── nest g middleware logger     ← Generate middleware
│   ├── nest g decorator roles       ← Generate decorator
│   ├── nest g gateway events        ← Generate WebSocket gateway
│   └── nest g library shared        ← Generate library (monorepo)
├── Build & Run:
│   ├── nest start                   ← Build and run
│   ├── nest start --watch           ← Watch mode (development)
│   ├── nest start --debug           ← Debug mode
│   ├── nest build                   ← Build only
│   └── nest build --webpack         ← Build with webpack (faster)
└── nest-cli.json Configuration:
    ├── collection: "@nestjs/schematics"
    ├── sourceRoot: "src"
    ├── compilerOptions: { "webpack": true, "tsConfigPath": "..." }
    └── projects: { } ← Monorepo project definitions
```

### Section 2.1.2 — Application Bootstrap (main.ts)
```
├── NestFactory.create(AppModule):
│   ├── Creates the NestJS application instance
│   ├── Initializes the IoC container
│   └── Resolves all dependencies
├── Platform Selection:
│   ├── Express (default): NestExpressApplication
│   │   └── app = await NestFactory.create<NestExpressApplication>(AppModule)
│   ├── Fastify (alternative): NestFastifyApplication
│   │   └── app = await NestFactory.create<NestFastifyApplication>(
│   │         AppModule, new FastifyAdapter())
│   └── Express vs Fastify:
│       ├── Express: Larger ecosystem, More middleware, Community standard
│       └── Fastify: ~2x faster, Schema-based validation, Built-in logging
├── Global Configuration (in main.ts):
│   ├── app.setGlobalPrefix('api/v1')         ← URL prefix
│   ├── app.enableCors({ origin: '...' })      ← CORS
│   ├── app.useGlobalPipes(new ValidationPipe()) ← Global validation
│   ├── app.useGlobalFilters(...)              ← Global exception filters
│   ├── app.useGlobalInterceptors(...)         ← Global interceptors
│   ├── app.useGlobalGuards(...)               ← Global guards
│   ├── app.enableVersioning(...)              ← API versioning
│   ├── app.enableShutdownHooks()              ← Graceful shutdown
│   └── app.use(helmet())                      ← Express middleware
├── Swagger Setup:
│   ├── const config = new DocumentBuilder()
│   │     .setTitle('API')
│   │     .setVersion('1.0')
│   │     .addBearerAuth()
│   │     .build();
│   ├── const document = SwaggerModule.createDocument(app, config);
│   └── SwaggerModule.setup('docs', app, document);
└── Listen:
    └── await app.listen(process.env.PORT ?? 3000);
```

---

## Module 2.2: Modules

### Section 2.2.1 — Module Fundamentals
```
├── What is a Module:
│   ├── Organizing unit for NestJS applications
│   ├── Every NestJS app has at least ONE module (AppModule)
│   ├── Encapsulates providers (services), controllers, imports, exports
│   └── Analogous to Angular modules (NestJS inspired by Angular)
├── @Module() Decorator Properties:
│   ├── imports: [ ]      ← Other modules this module depends on
│   ├── controllers: [ ]  ← Controllers handled by this module
│   ├── providers: [ ]    ← Services/Providers available within this module
│   └── exports: [ ]      ← Providers available to OTHER modules that import this one
├── Example:
│   └── @Module({
│         imports: [DatabaseModule, AuthModule],
│         controllers: [UsersController],
│         providers: [UsersService, UsersRepository],
│         exports: [UsersService],  // Other modules can use UsersService
│       })
│       export class UsersModule {}
├── Module Scope:
│   ├── Providers are scoped to their module by DEFAULT
│   ├── To use a provider outside its module → export it
│   ├── To use an exported provider → import the module
│   └── Key Rule: Import the MODULE, not the provider directly
└── Root Module (AppModule):
    └── Imports ALL feature modules, The application entry point
```

### Section 2.2.2 — Module Types
```
├── Feature Modules:
│   ├── Organize by business domain: UsersModule, OrdersModule, ProductsModule
│   ├── Each feature module encapsulates its controllers + services + entities
│   └── Best Practice: One module per bounded context / feature area
├── Shared Modules:
│   ├── Contain commonly used providers (utilities, helpers)
│   ├── Exported and imported by many feature modules
│   ├── Example: SharedModule exports LoggerService, MailService, etc.
│   └── @Global() decorator: Makes module available everywhere (use sparingly!)
├── Dynamic Modules:
│   ├── Modules configured at import time (parameterized)
│   ├── Pattern: forRoot() (singleton) vs forRootAsync() (async config)
│   ├── Pattern: register() vs registerAsync() (per-module instance)
│   ├── Example:
│   │   └── ConfigModule.forRoot({ isGlobal: true, envFilePath: '.env' })
│   │   └── TypeOrmModule.forRoot({ type: 'postgres', ... })
│   │   └── TypeOrmModule.forFeature([UserEntity])
│   ├── Building Custom Dynamic Modules:
│   │   ├── DynamicModule interface
│   │   ├── Static forRoot() / register() methods
│   │   ├── Async forRootAsync() / registerAsync() with useFactory
│   │   └── ConfigurableModuleBuilder (NestJS v9+): Automated dynamic module creation
│   └── When to use: Database connections, Third-party integrations, Configuration
├── Global Modules:
│   ├── @Global() decorator: Module available in ALL modules without importing
│   ├── Use Case: Configuration, Logging, Database connection
│   └── Warning: Overuse creates hidden dependencies — prefer explicit imports
└── Lazy-Loaded Modules (Advanced):
    ├── Load modules on demand (not at startup)
    ├── LazyModuleLoader service
    ├── Use case: Serverless functions, Rarely-used features
    └── const { LazyModule } = await this.lazyModuleLoader.load(() => import('./lazy.module'))
```

---

## Module 2.3: Controllers

### Section 2.3.1 — Controller Fundamentals
```
├── Purpose: Handle incoming HTTP requests, Return responses
├── @Controller() Decorator:
│   ├── @Controller('users')       → /users
│   ├── @Controller('api/users')   → /api/users
│   └── @Controller({ path: 'users', version: '1' }) → /v1/users
├── HTTP Method Decorators:
│   ├── @Get()        → GET request
│   ├── @Post()       → POST request
│   ├── @Put()        → PUT request
│   ├── @Patch()      → PATCH request
│   ├── @Delete()     → DELETE request
│   ├── @Options()    → OPTIONS request
│   ├── @Head()       → HEAD request
│   └── @All()        → ALL methods
├── Route Parameters:
│   ├── @Get(':id')
│   │   └── findOne(@Param('id') id: string)
│   ├── @Get(':userId/posts/:postId')
│   │   └── findPost(@Param('userId') userId: string, @Param('postId') postId: string)
│   └── @Param() without argument → entire params object
├── Route Wildcards:
│   ├── @Get('ab*cd')  → Matches abcd, ab_cd, abXXXcd
│   └── Regex routes: @Get(/regex/) (platform-dependent)
└── Sub-Domain Routing:
    └── @Controller({ host: ':account.example.com' })
        └── @Get() getInfo(@HostParam('account') account: string)
```

### Section 2.3.2 — Request Data Extraction
```
├── @Body():
│   ├── @Body() body: CreateUserDto          ← Entire body
│   ├── @Body('name') name: string           ← Single property
│   └── Used with: @Post(), @Put(), @Patch()
├── @Query():
│   ├── @Query() query: PaginationDto        ← All query params
│   ├── @Query('page') page: number          ← Single query param
│   └── GET /users?page=1&limit=20
├── @Param():
│   ├── @Param() params: { id: string }      ← All route params
│   ├── @Param('id') id: string              ← Single route param
│   └── GET /users/:id
├── @Headers():
│   ├── @Headers() headers: Record<string, string> ← All headers
│   └── @Headers('authorization') auth: string     ← Single header
├── @Ip(): Client IP address
├── @Session(): Express session object
├── @Req() / @Request(): Raw Express/Fastify request (avoid — platform-specific)
├── @Res() / @Response(): Raw Express/Fastify response (avoid — bypasses interceptors)
│   └── Warning: Using @Res() puts you in "library-specific mode" — NestJS loses control
│   └── Use @Res({ passthrough: true }) to keep NestJS response handling
├── @UploadedFile(): Single file upload (with @UseInterceptors(FileInterceptor))
├── @UploadedFiles(): Multiple file uploads (with FilesInterceptor)
└── @Next(): Express next function (rarely needed)
```

### Section 2.3.3 — Response Handling
```
├── Standard Response (Recommended):
│   ├── Return value → Automatically serialized to JSON
│   ├── Return string → Sent as text
│   ├── Return object/array → Serialized to JSON (200 for GET, 201 for POST)
│   └── Return Observable/Promise → Awaited and serialized
├── Status Code Override:
│   ├── @HttpCode(204)            ← Custom status code
│   ├── @HttpCode(HttpStatus.NO_CONTENT) ← Enum-based
│   └── Default: 200 for GET/PUT/PATCH/DELETE, 201 for POST
├── Response Headers:
│   ├── @Header('Cache-Control', 'max-age=3600')   ← Static header
│   └── @Header('X-Custom-Header', 'value')
├── Redirect:
│   ├── @Redirect('https://example.com', 301)
│   └── Dynamic redirect: return { url: '...', statusCode: 301 }
├── Streaming:
│   ├── StreamableFile: Return file as stream
│   └── return new StreamableFile(createReadStream(path))
└── Response Best Practice:
    ├── DO: Return plain objects/arrays, Let NestJS handle serialization
    ├── DON'T: Use @Res() directly (loses interceptors, pipes, filters)
    └── Use class-transformer for response shaping (ClassSerializerInterceptor)
```

---

## Module 2.4: Providers & Dependency Injection

### Section 2.4.1 — Provider Fundamentals
```
├── What is a Provider:
│   ├── Any class annotated with @Injectable()
│   ├── Can be injected as a dependency into other classes
│   ├── Managed by the NestJS IoC container
│   └── Lifecycle: Created once (singleton by default), Shared across module
├── @Injectable() Decorator:
│   ├── Marks a class as a provider
│   ├── Tells NestJS to manage its lifecycle and dependencies
│   └── @Injectable()
│       export class UsersService {
│         constructor(private readonly usersRepo: UsersRepository) {} // Auto-injected!
│       }
├── Provider Types:
│   ├── Services: Business logic (most common)
│   ├── Repositories: Data access
│   ├── Factories: Object creation
│   ├── Helpers/Utilities: Shared logic
│   └── ANY class can be a provider if @Injectable()
├── Injection Scope:
│   ├── DEFAULT (Singleton): One instance shared across entire app (recommended)
│   ├── REQUEST: New instance per HTTP request
│   │   └── @Injectable({ scope: Scope.REQUEST })
│   │   └── Use case: Request-specific state (current user, tenant)
│   │   └── Warning: Bubbles up — all dependents become request-scoped too
│   ├── TRANSIENT: New instance per injection (every consumer gets its own)
│   │   └── @Injectable({ scope: Scope.TRANSIENT })
│   │   └── Use case: Stateful helpers, Unique instances
│   └── Performance: DEFAULT > TRANSIENT > REQUEST (singleton is fastest)
└── Injection via Constructor:
    ├── constructor(private readonly usersService: UsersService) {}
    ├── NestJS resolves by TYPE (TypeScript type metadata)
    └── Access modifier (private/readonly) auto-creates class property
```

### Section 2.4.2 — Custom Providers
```
├── Standard Provider (shorthand):
│   └── providers: [UsersService]
│   └── Equivalent to: providers: [{ provide: UsersService, useClass: UsersService }]
├── useClass — Swap Implementations:
│   └── providers: [{
│         provide: UsersService,
│         useClass: process.env.MOCK ? MockUsersService : UsersService
│       }]
│   └── Use case: Swap between real and mock services based on environment
├── useValue — Provide a Constant:
│   └── providers: [{
│         provide: 'API_KEY',
│         useValue: 'my-secret-key'
│       }]
│   └── Inject with: constructor(@Inject('API_KEY') private apiKey: string)
│   └── Use case: Configuration values, Static objects, External library instances
├── useFactory — Dynamic Creation:
│   └── providers: [{
│         provide: 'DATABASE_CONNECTION',
│         useFactory: async (config: ConfigService) => {
│           return createConnection(config.get('DATABASE_URL'));
│         },
│         inject: [ConfigService], // Factory dependencies
│       }]
│   └── Use case: Async initialization, Conditional creation, External connections
├── useExisting — Alias:
│   └── providers: [{
│         provide: 'AliasedService',
│         useExisting: UsersService
│       }]
│   └── Use case: Backward compatibility, Interface aliasing
├── Injection Tokens:
│   ├── String tokens: @Inject('TOKEN_NAME') — simple, risk of collision
│   ├── Symbol tokens: const TOKEN = Symbol('TOKEN') — unique, no collision
│   └── InjectionToken class: Better type safety
│       └── export const CONFIG_OPTIONS = new InjectionToken<ConfigOptions>('CONFIG_OPTIONS')
├── Optional Dependencies:
│   └── constructor(@Optional() @Inject('OPTIONAL_SERVICE') private svc?: SomeService)
│   └── If not available, value is undefined (no error)
└── Circular Dependencies:
    ├── Problem: A depends on B, B depends on A → Crash
    ├── Solution: forwardRef(() => ClassB)
    │   └── @Inject(forwardRef(() => CatsService)) private catsService: CatsService
    ├── ModuleRef: Lazy resolution at runtime
    └── Best Fix: Refactor to remove the circular dependency!
```

### Section 2.4.3 — Async Providers
```
├── Async Factory:
│   └── providers: [{
│         provide: 'ASYNC_CONNECTION',
│         useFactory: async () => {
│           const connection = await createConnection({...});
│           return connection;
│         },
│       }]
│   └── NestJS waits for async resolution before starting the app
├── Async Configuration Pattern:
│   └── TypeOrmModule.forRootAsync({
│         imports: [ConfigModule],
│         useFactory: (config: ConfigService) => ({
│           type: 'postgres',
│           host: config.get('DB_HOST'),
│           // ...
│         }),
│         inject: [ConfigService],
│       })
└── Use Case: Database connections, External API clients, Any async initialization
```

---

## Module 2.5: Middleware

### Section 2.5.1 — NestJS Middleware
```
├── What is Middleware:
│   ├── Function executed BEFORE the route handler
│   ├── Has access to Request, Response, Next
│   ├── Similar to Express middleware
│   └── NestJS Request Lifecycle:
│       Middleware → Guards → Interceptors (before) → Pipes → Handler → Interceptors (after) → Filters
├── Class Middleware:
│   ├── Implements NestMiddleware interface
│   ├── @Injectable() + use(req, res, next) method
│   └── Can inject dependencies (DI-aware)
│   └── Example:
│       @Injectable()
│       export class LoggerMiddleware implements NestMiddleware {
│         use(req: Request, res: Response, next: NextFunction) {
│           console.log(`${req.method} ${req.url}`);
│           next();
│         }
│       }
├── Functional Middleware:
│   ├── Simple function: (req, res, next) => { ... next(); }
│   ├── When: No dependencies needed, Simple logic
│   └── Example:
│       export function logger(req, res, next) {
│         console.log(`Request...`);
│         next();
│       }
├── Applying Middleware (in Module):
│   ├── export class AppModule implements NestModule {
│   │     configure(consumer: MiddlewareConsumer) {
│   │       consumer
│   │         .apply(LoggerMiddleware)
│   │         .exclude({ path: 'health', method: RequestMethod.GET })
│   │         .forRoutes('*');  // or specific controller/route
│   │     }
│   │   }
│   ├── .forRoutes('users')              ← Specific path
│   ├── .forRoutes(UsersController)      ← Specific controller
│   ├── .forRoutes({ path: 'users', method: RequestMethod.GET }) ← Specific method
│   └── .forRoutes('*')                  ← All routes
├── Multiple Middleware: .apply(Cors, Helmet, Logger).forRoutes('*')
├── Global Middleware (Express):
│   └── app.use(helmet())  // In main.ts — Express middleware directly
└── Express Middleware Compatibility:
    ├── cors, helmet, morgan, compression, cookie-parser — all work!
    └── app.use(compression()); app.use(helmet()); // in main.ts
```

---

## Module 2.6: Exception Filters

### Section 2.6.1 — Built-in Exceptions
```
├── NestJS Built-in HTTP Exceptions:
│   ├── BadRequestException          → 400
│   ├── UnauthorizedException        → 401
│   ├── ForbiddenException           → 403
│   ├── NotFoundException            → 404
│   ├── MethodNotAllowedException    → 405
│   ├── NotAcceptableException       → 406
│   ├── RequestTimeoutException      → 408
│   ├── ConflictException            → 409
│   ├── GoneException                → 410
│   ├── PayloadTooLargeException     → 413
│   ├── UnsupportedMediaTypeException → 415
│   ├── UnprocessableEntityException → 422
│   ├── InternalServerErrorException → 500
│   ├── NotImplementedException      → 501
│   ├── BadGatewayException          → 502
│   ├── ServiceUnavailableException  → 503
│   └── GatewayTimeoutException      → 504
├── Usage:
│   └── throw new NotFoundException('User not found');
│   └── throw new BadRequestException({ message: 'Invalid input', details: errors });
├── Custom Exception:
│   └── export class UserNotFoundException extends NotFoundException {
│         constructor(userId: string) {
│           super(`User with ID ${userId} not found`);
│         }
│       }
└── Default Response Format:
    └── { "statusCode": 404, "message": "User not found", "error": "Not Found" }
```

### Section 2.6.2 — Custom Exception Filters
```
├── Purpose: Customize error response format, Log errors, Transform exceptions
├── @Catch() Decorator: Specify which exception types to catch
├── ExceptionFilter Interface: catch(exception, host) method
├── Example — HTTP Exception Filter:
│   └── @Catch(HttpException)
│       export class HttpExceptionFilter implements ExceptionFilter {
│         catch(exception: HttpException, host: ArgumentsHost) {
│           const ctx = host.switchToHttp();
│           const response = ctx.getResponse<Response>();
│           const request = ctx.getRequest<Request>();
│           const status = exception.getStatus();
│           response.status(status).json({
│             statusCode: status,
│             timestamp: new Date().toISOString(),
│             path: request.url,
│             message: exception.message,
│           });
│         }
│       }
├── Catch ALL Exceptions:
│   └── @Catch() — No argument catches everything (including non-HTTP errors)
│   └── Good for: Logging unhandled errors, Preventing stack traces in response
├── Applying Filters:
│   ├── Method level: @UseFilters(HttpExceptionFilter) on handler
│   ├── Controller level: @UseFilters(HttpExceptionFilter) on controller class
│   ├── Global level: app.useGlobalFilters(new HttpExceptionFilter()) in main.ts
│   └── Global with DI:
│       └── providers: [{ provide: APP_FILTER, useClass: HttpExceptionFilter }]
│       └── Advantage: Can inject dependencies (logger, etc.)
└── Multiple Filters: @UseFilters(Filter1, Filter2) — first match wins
```

---

## Module 2.7: Pipes

### Section 2.7.1 — Built-in Pipes
```
├── Purpose: Transform input data OR Validate input data
├── Pipe Execution: AFTER middleware & guards, BEFORE handler
├── Built-in Pipes:
│   ├── ValidationPipe: Validates DTOs using class-validator decorators
│   │   └── MOST IMPORTANT PIPE — use globally
│   ├── ParseIntPipe: Transform string → number (or throw 400)
│   │   └── @Param('id', ParseIntPipe) id: number
│   ├── ParseUUIDPipe: Validate UUID format
│   │   └── @Param('id', ParseUUIDPipe) id: string
│   ├── ParseBoolPipe: Transform string → boolean
│   ├── ParseFloatPipe: Transform string → float
│   ├── ParseArrayPipe: Transform string → array
│   ├── ParseEnumPipe: Validate against enum values
│   ├── DefaultValuePipe: Provide default if undefined
│   │   └── @Query('page', new DefaultValuePipe(1), ParseIntPipe) page: number
│   └── ParseFilePipe: Validate file uploads (size, type)
└── Chaining Pipes:
    └── @Query('page', new DefaultValuePipe(1), ParseIntPipe) page: number
    └── DefaultValuePipe runs first → ParseIntPipe runs on result
```

### Section 2.7.2 — ValidationPipe & DTOs
```
├── Setup (install dependencies):
│   └── npm install class-validator class-transformer
├── Global ValidationPipe (main.ts):
│   └── app.useGlobalPipes(new ValidationPipe({
│         whitelist: true,           // Strip properties not in DTO
│         forbidNonWhitelisted: true, // Throw error on extra properties
│         transform: true,           // Auto-transform to DTO class instance
│         transformOptions: {
│           enableImplicitConversion: true, // Auto-convert query string to numbers, etc.
│         },
│       }));
├── DTO (Data Transfer Object):
│   └── export class CreateUserDto {
│         @IsString()
│         @IsNotEmpty()
│         @MinLength(2)
│         @MaxLength(50)
│         name: string;
│
│         @IsEmail()
│         email: string;
│
│         @IsString()
│         @MinLength(8)
│         @Matches(/^(?=.*[A-Z])(?=.*[0-9])/)
│         password: string;
│
│         @IsOptional()
│         @IsInt()
│         @Min(0)
│         @Max(150)
│         age?: number;
│       }
├── Common Validators (class-validator):
│   ├── @IsString(), @IsNumber(), @IsBoolean(), @IsDate()
│   ├── @IsNotEmpty(), @IsOptional(), @IsDefined()
│   ├── @IsEmail(), @IsUrl(), @IsUUID()
│   ├── @MinLength(), @MaxLength(), @Length()
│   ├── @Min(), @Max(), @IsPositive(), @IsNegative()
│   ├── @IsEnum(SomeEnum), @IsIn(['value1', 'value2'])
│   ├── @IsArray(), @ArrayMinSize(), @ArrayMaxSize()
│   ├── @ValidateNested(), @Type(() => NestedDto) ← Nested validation
│   ├── @Matches(/regex/), @Contains(), @NotContains()
│   └── @IsDateString(), @IsISO8601(), @IsPhoneNumber()
├── Partial DTOs (for updates):
│   └── export class UpdateUserDto extends PartialType(CreateUserDto) {}
│   └── PartialType: Makes all properties optional (from @nestjs/mapped-types)
├── Other Mapped Types:
│   ├── PickType(CreateUserDto, ['name', 'email']): Select specific fields
│   ├── OmitType(CreateUserDto, ['password']): Exclude specific fields
│   └── IntersectionType(CreateUserDto, AdditionalInfoDto): Merge DTOs
├── Custom Validators:
│   └── @ValidatorConstraint({ async: true })
│       export class IsUniqueEmailConstraint implements ValidatorConstraintInterface {
│         constructor(private usersService: UsersService) {}
│         async validate(email: string) {
│           const user = await this.usersService.findByEmail(email);
│           return !user;
│         }
│       }
└── Groups: Validation groups for conditional validation
    └── @IsNotEmpty({ groups: ['create'] })
    └── @IsOptional({ groups: ['update'] })
```

### Section 2.7.3 — Custom Pipes
```
├── Transformation Pipe:
│   └── @Injectable()
│       export class ParseDatePipe implements PipeTransform<string, Date> {
│         transform(value: string, metadata: ArgumentMetadata): Date {
│           const date = new Date(value);
│           if (isNaN(date.getTime())) throw new BadRequestException('Invalid date');
│           return date;
│         }
│       }
├── Applying Custom Pipes:
│   ├── Parameter level: @Query('date', ParseDatePipe) date: Date
│   ├── Method level: @UsePipes(MyPipe)
│   └── Global level: app.useGlobalPipes(new MyPipe())
└── PipeTransform<T, R>: T = input type, R = output type
```

---

## Module 2.8: Guards

### Section 2.8.1 — Guard Fundamentals
```
├── Purpose: Determine if a request should be handled (Authorization)
├── Execution: AFTER middleware, BEFORE interceptors & pipes
├── Return: true (allow) or false (deny → ForbiddenException)
├── CanActivate Interface: canActivate(context: ExecutionContext): boolean | Promise<boolean>
├── ExecutionContext: Extended ArgumentsHost with additional methods
│   ├── context.getHandler()  → Current route handler method reference
│   ├── context.getClass()    → Current controller class reference
│   └── context.switchToHttp().getRequest() → HTTP request object
├── Basic Guard Example:
│   └── @Injectable()
│       export class AuthGuard implements CanActivate {
│         constructor(private authService: AuthService) {}
│         async canActivate(context: ExecutionContext): Promise<boolean> {
│           const request = context.switchToHttp().getRequest();
│           const token = request.headers.authorization?.split(' ')[1];
│           if (!token) return false;
│           request.user = await this.authService.validateToken(token);
│           return true;
│         }
│       }
├── Applying Guards:
│   ├── Method level: @UseGuards(AuthGuard)
│   ├── Controller level: @UseGuards(AuthGuard) on class
│   ├── Global level: app.useGlobalGuards(new AuthGuard())
│   └── Global with DI:
│       └── providers: [{ provide: APP_GUARD, useClass: AuthGuard }]
├── Role-Based Guard (using custom metadata):
│   ├── Custom decorator: @Roles('admin', 'moderator')
│   │   └── export const Roles = (...roles: string[]) => SetMetadata('roles', roles);
│   ├── Guard reads metadata:
│   │   └── const requiredRoles = this.reflector.getAllAndOverride<string[]>(
│   │         'roles', [context.getHandler(), context.getClass()]);
│   │   └── if (!requiredRoles) return true; // No roles = public
│   │   └── return requiredRoles.some(role => user.roles.includes(role));
│   └── Reflector: Service to read metadata set by decorators
└── Guard vs Middleware:
    ├── Middleware: Doesn't know which handler will execute next
    ├── Guard: HAS access to ExecutionContext (knows the handler + class)
    └── Use Guard for: Auth, Role checks, Permissions — anything needing route awareness
```

---

## Module 2.9: Interceptors

### Section 2.9.1 — Interceptor Fundamentals
```
├── Purpose: Transform data, Add extra logic BEFORE and/or AFTER handler execution
├── Inspired by: Aspect-Oriented Programming (AOP)
├── NestInterceptor Interface: intercept(context, next: CallHandler): Observable<any>
├── Capabilities:
│   ├── Transform the response (map/transform returned data)
│   ├── Bind extra logic before/after handler
│   ├── Override the handler entirely
│   ├── Extend/override behavior
│   ├── Cache responses
│   └── Logging / Timing / Performance tracking
├── Example — Logging Interceptor:
│   └── @Injectable()
│       export class LoggingInterceptor implements NestInterceptor {
│         intercept(context: ExecutionContext, next: CallHandler): Observable<any> {
│           const now = Date.now();
│           return next.handle().pipe(
│             tap(() => console.log(`${Date.now() - now}ms`)),
│           );
│         }
│       }
├── Example — Transform Response:
│   └── @Injectable()
│       export class TransformInterceptor<T> implements NestInterceptor<T, Response<T>> {
│         intercept(context, next): Observable<Response<T>> {
│           return next.handle().pipe(
│             map(data => ({ data, statusCode: 200, timestamp: new Date().toISOString() })),
│           );
│         }
│       }
├── Example — Timeout Interceptor:
│   └── return next.handle().pipe(
│         timeout(5000),
│         catchError(err => {
│           if (err instanceof TimeoutError) throw new RequestTimeoutException();
│           throw err;
│         }),
│       );
├── Example — Cache Interceptor:
│   └── Built-in: @UseInterceptors(CacheInterceptor) with @nestjs/cache-manager
├── Applying Interceptors:
│   ├── Method level: @UseInterceptors(LoggingInterceptor)
│   ├── Controller level: @UseInterceptors(LoggingInterceptor) on class
│   ├── Global level: app.useGlobalInterceptors(new LoggingInterceptor())
│   └── Global with DI:
│       └── providers: [{ provide: APP_INTERCEPTOR, useClass: LoggingInterceptor }]
└── RxJS in Interceptors:
    ├── map(): Transform data
    ├── tap(): Side effects (logging)
    ├── catchError(): Handle errors
    ├── timeout(): Request timeout
    ├── mergeMap() / switchMap(): Async operations
    └── retry(): Retry on failure
```

### Section 2.9.2 — Class Serialization (ClassSerializerInterceptor)
```
├── Purpose: Control what properties are included in the response
├── Setup: @UseInterceptors(ClassSerializerInterceptor) (or globally)
├── class-transformer Decorators:
│   ├── @Exclude(): Hide property from response (e.g., password)
│   ├── @Expose(): Include property in response (when using excludeAll strategy)
│   ├── @Transform(): Custom transformation
│   │   └── @Transform(({ value }) => value.toUpperCase())
│   ├── @Type(): Specify nested type
│   └── Groups: @Expose({ groups: ['admin'] }) — conditional exposure
├── Example:
│   └── export class UserEntity {
│         id: number;
│         name: string;
│         email: string;
│         @Exclude()
│         password: string;
│         @Transform(({ value }) => value.toISOString())
│         createdAt: Date;
│         constructor(partial: Partial<UserEntity>) {
│           Object.assign(this, partial);
│         }
│       }
│       // Controller: return new UserEntity(user);
└── Alternative: Custom interceptor with class-transformer plainToClass()
```

---

## Module 2.10: Custom Decorators

### Section 2.10.1 — Creating Custom Decorators
```
├── Parameter Decorator:
│   └── export const CurrentUser = createParamDecorator(
│         (data: string, ctx: ExecutionContext) => {
│           const request = ctx.switchToHttp().getRequest();
│           const user = request.user;
│           return data ? user?.[data] : user;
│         },
│       );
│   └── Usage: @CurrentUser() user: User, @CurrentUser('email') email: string
├── Metadata Decorator:
│   └── export const Roles = (...roles: Role[]) => SetMetadata('roles', roles);
│   └── Usage: @Roles(Role.ADMIN, Role.MODERATOR)
├── Composed Decorator (combine multiple):
│   └── export function Auth(...roles: Role[]) {
│         return applyDecorators(
│           SetMetadata('roles', roles),
│           UseGuards(JwtAuthGuard, RolesGuard),
│           ApiBearerAuth(),  // Swagger
│           ApiUnauthorizedResponse({ description: 'Unauthorized' }),
│         );
│       }
│   └── Usage: @Auth(Role.ADMIN)  ← One decorator does everything!
├── Common Custom Decorators:
│   ├── @CurrentUser(): Extract authenticated user from request
│   ├── @Public(): Mark route as public (skip auth guard)
│   ├── @Roles(): Attach role metadata
│   ├── @Permissions(): Attach permission metadata
│   ├── @ApiPaginated(): Combine Swagger decorators for paginated responses
│   └── @Throttle(): Custom rate limiting metadata
└── Best Practice:
    ├── Compose decorators to reduce boilerplate
    ├── Keep decorators small and focused
    └── Document custom decorators in shared module
```

---

> ### 🛠️ PHASE 2 PROJECT: **Blog API with All Building Blocks**
> ```
> ┌─────────────────────────────────────────────────────────────────┐
> │                     BLOG API — ALL BUILDING BLOCKS              │
> ├─────────────────────────────────────────────────────────────────┤
> │                                                                 │
> │ Modules: AppModule, PostsModule, UsersModule, TagsModule,       │
> │          CommentsModule, SharedModule                            │
> │                                                                 │
> │ Features:                                                       │
> │  • Users: Registration, Profile management                      │
> │  • Posts: Full CRUD with pagination, filtering, sorting         │
> │  • Comments: Nested comments on posts                           │
> │  • Tags: Many-to-many with posts                                │
> │  • In-memory data store (no real DB yet)                        │
> │                                                                 │
> │ Building Blocks Practiced:                                      │
> │  ✅ Modules: Feature modules + Shared module + Dynamic module    │
> │  ✅ Controllers: All HTTP methods, Params, Query, Body           │
> │  ✅ Providers: Services, Custom providers (useValue, useFactory) │
> │  ✅ DTOs: class-validator for ALL inputs, Mapped types           │
> │  ✅ Pipes: ValidationPipe (global), ParseIntPipe, ParseUUIDPipe │
> │  ✅ Custom Pipe: ParseDatePipe for date query params             │
> │  ✅ Guards: Simple API key guard                                 │
> │  ✅ Interceptors: Logging, Response transform, Timeout           │
> │  ✅ Exception Filters: Custom HTTP exception filter              │
> │  ✅ Middleware: Request logger, Correlation ID                   │
> │  ✅ Custom Decorators: @CurrentUser(), @Public(), @ApiPaginated()│
> │  ✅ Serialization: @Exclude() password, @Transform() dates       │
> │  ✅ Swagger: Full API documentation with all decorators          │
> │  ✅ Unit Tests: Every service, Every guard, Every pipe            │
> └─────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 🧩 PHASE 3: CORE ARCHITECTURE DEEP DIVE
### 📅 Duration: Weeks 6–9
### 🎯 Goal: Master NestJS internals, lifecycle, configuration, and testing
### 👤 Level: Junior+ Developer

---

## Module 3.1: Request Lifecycle (Complete)

### Section 3.1.1 — Full Request Pipeline
```
├── 1. Incoming Request
│
├── 2. MIDDLEWARE (in order of registration)
│   ├── Global middleware (app.use() in main.ts)
│   └── Module middleware (configure() in module)
│
├── 3. GUARDS (in order: Global → Controller → Route)
│   ├── Global guards
│   ├── Controller-level guards
│   └── Route-level guards
│   └── If ANY guard returns false → ForbiddenException (skip everything below)
│
├── 4. INTERCEPTORS — BEFORE (in order: Global → Controller → Route)
│   ├── Code before next.handle()
│   └── Can short-circuit (return Observable without calling next)
│
├── 5. PIPES (in order: Global → Controller → Route → Parameter)
│   ├── Transform/validate @Param()
│   ├── Transform/validate @Query()
│   ├── Transform/validate @Body()
│   └── If validation fails → BadRequestException (skip handler)
│
├── 6. ROUTE HANDLER (Controller method)
│   └── Your business logic executes here
│
├── 7. INTERCEPTORS — AFTER (in REVERSE order: Route → Controller → Global)
│   └── Code after next.handle() — transform response
│
├── 8. EXCEPTION FILTERS (if error thrown anywhere above)
│   └── Catches exceptions: Route → Controller → Global
│   └── First matching filter handles the exception
│
└── 9. Response sent to client

VISUAL FLOW:
Request → Middleware → Guards → Interceptors(pre) → Pipes → Handler → Interceptors(post) → Response
                                                                                    ↓ (on error)
                                                                           Exception Filters
```

---

## Module 3.2: Configuration Management

### Section 3.2.1 — @nestjs/config (ConfigModule)
```
├── Installation: npm install @nestjs/config
├── Setup:
│   └── @Module({
│         imports: [ConfigModule.forRoot({
│           isGlobal: true,            // Available everywhere
│           envFilePath: ['.env.local', '.env'],  // Multiple env files
│           cache: true,               // Cache values for performance
│           expandVariables: true,     // Support ${VAR} in .env
│           validationSchema: Joi.object({ ... }), // Validate env vars
│         })],
│       })
├── Usage:
│   ├── Injection: constructor(private config: ConfigService) {}
│   ├── Get value: this.config.get<string>('DATABASE_URL')
│   ├── Get with default: this.config.get('PORT', 3000)
│   ├── Get or throw: this.config.getOrThrow('SECRET_KEY')
│   └── Typed config: this.config.get<number>('PORT')
├── Configuration Namespaces:
│   ├── Define:
│   │   └── export default registerAs('database', () => ({
│   │         host: process.env.DB_HOST || 'localhost',
│   │         port: parseInt(process.env.DB_PORT, 10) || 5432,
│   │         name: process.env.DB_NAME,
│   │       }));
│   ├── Load: ConfigModule.forRoot({ load: [databaseConfig] })
│   ├── Inject: @Inject(databaseConfig.KEY) private dbConfig: ConfigType<typeof databaseConfig>
│   └── Access: this.dbConfig.host, this.dbConfig.port
├── Validation (with Joi):
│   └── validationSchema: Joi.object({
│         NODE_ENV: Joi.string().valid('development', 'production', 'test').default('development'),
│         PORT: Joi.number().default(3000),
│         DATABASE_URL: Joi.string().required(),
│         JWT_SECRET: Joi.string().required(),
│         JWT_EXPIRES_IN: Joi.string().default('1h'),
│       }),
│       validationOptions: { abortEarly: true },
├── Validation (with class-validator):
│   └── validate: (config: Record<string, unknown>) => {
│         const validatedConfig = plainToInstance(EnvironmentVariables, config);
│         const errors = validateSync(validatedConfig);
│         if (errors.length > 0) throw new Error(errors.toString());
│         return validatedConfig;
│       }
└── Best Practices:
    ├── ALWAYS validate environment variables at startup
    ├── Use namespaced configs for grouping (database, auth, mail, etc.)
    ├── Type-safe config with registerAs + ConfigType
    ├── Never access process.env directly in services — always via ConfigService
    └── Provide defaults for non-critical values, Throw for critical ones
```

---

## Module 3.3: Lifecycle Events

### Section 3.3.1 — Application Lifecycle Hooks
```
├── Module/Provider Lifecycle Hooks:
│   ├── OnModuleInit: Called ONCE after module's providers are initialized
│   │   └── Use case: Initialize connections, Seed data, Run migrations
│   ├── OnApplicationBootstrap: Called after ALL modules initialized, Before listening
│   │   └── Use case: Start background jobs, Verify external services
│   ├── OnModuleDestroy: Called when module is being destroyed
│   │   └── Use case: Close connections, Clean up resources
│   ├── BeforeApplicationShutdown: Called BEFORE connections closed (receives signal)
│   │   └── Use case: Finish in-flight requests, Stop accepting new work
│   └── OnApplicationShutdown: Called after connections closed
│       └── Use case: Final cleanup, Log shutdown
├── Implementation:
│   └── @Injectable()
│       export class DatabaseService implements OnModuleInit, OnModuleDestroy {
│         async onModuleInit() { await this.connect(); }
│         async onModuleDestroy() { await this.disconnect(); }
│       }
├── Graceful Shutdown:
│   ├── Enable: app.enableShutdownHooks() in main.ts
│   ├── Listens for: SIGTERM, SIGINT
│   ├── Process: Stop accepting requests → Finish in-flight → Close connections → Exit
│   └── Important for: Kubernetes (sends SIGTERM), Docker, Cloud deployments
├── Execution Order:
│   └── Startup: OnModuleInit → OnApplicationBootstrap → Listen
│   └── Shutdown: BeforeApplicationShutdown → OnModuleDestroy → OnApplicationShutdown → Exit
└── Timeout: Set shutdown timeout to prevent hanging
    └── app.enableShutdownHooks(); with terminationGracePeriod
```

---

## Module 3.4: Testing in NestJS

### Section 3.4.1 — Unit Testing
```
├── Test Runner: Jest (built-in)
├── Testing Module:
│   └── const module = await Test.createTestingModule({
│         providers: [
│           UsersService,
│           { provide: UsersRepository, useValue: mockRepository },
│           { provide: ConfigService, useValue: mockConfig },
│         ],
│       }).compile();
│       service = module.get<UsersService>(UsersService);
├── Mocking:
│   ├── Manual Mocks: { provide: SomeService, useValue: { methodA: jest.fn() } }
│   ├── jest.fn(): Create mock function
│   ├── jest.spyOn(): Spy on existing method
│   ├── @golevelup/ts-jest: createMock<T>() — Auto-mock interfaces
│   └── Mock Factories: Reusable mock objects
├── Testing Services:
│   └── describe('UsersService', () => {
│         it('should create a user', async () => {
│           const dto = { name: 'John', email: 'john@test.com' };
│           mockRepository.create.mockResolvedValue({ id: 1, ...dto });
│           const result = await service.create(dto);
│           expect(result).toEqual({ id: 1, ...dto });
│           expect(mockRepository.create).toHaveBeenCalledWith(dto);
│         });
│       });
├── Testing Controllers:
│   └── Similar to services — mock the service, Test the controller
├── Testing Guards:
│   └── Create mock ExecutionContext
│   └── const context = createMock<ExecutionContext>();
│   └── expect(guard.canActivate(context)).toBe(true);
├── Testing Pipes:
│   └── const pipe = new ParseDatePipe();
│   └── expect(pipe.transform('2024-01-01')).toEqual(new Date('2024-01-01'));
│   └── expect(() => pipe.transform('invalid')).toThrow(BadRequestException);
└── Testing Interceptors:
    └── Create mock ExecutionContext + CallHandler
    └── const callHandler = { handle: () => of(testData) };
```

### Section 3.4.2 — Integration Testing (E2E)
```
├── Setup:
│   └── const moduleFixture = await Test.createTestingModule({
│         imports: [AppModule],
│       }).compile();
│       app = moduleFixture.createNestApplication();
│       app.useGlobalPipes(new ValidationPipe({ ... }));
│       await app.init();
├── Supertest:
│   └── import * as request from 'supertest';
│       it('/users (POST)', () => {
│         return request(app.getHttpServer())
│           .post('/users')
│           .send({ name: 'John', email: 'john@test.com' })
│           .expect(201)
│           .expect(res => {
│             expect(res.body.name).toBe('John');
│           });
│       });
├── Database Testing:
│   ├── Testcontainers: Real PostgreSQL in Docker for tests
│   │   └── npm install @testcontainers/postgresql
│   ├── SQLite in-memory: Fast but different SQL dialect
│   └── Test Database: Separate database, Seeded before each test
├── Authentication in Tests:
│   └── const loginResponse = await request(app.getHttpServer())
│         .post('/auth/login')
│         .send({ email: 'admin@test.com', password: 'password' });
│       const token = loginResponse.body.access_token;
│       // Use in subsequent requests:
│       .set('Authorization', `Bearer ${token}`)
├── Test Lifecycle:
│   ├── beforeAll: Create app, Initialize database
│   ├── beforeEach: Seed test data, Reset state
│   ├── afterEach: Clean up test data
│   └── afterAll: Close app, Destroy database
└── Best Practices:
    ├── Apply SAME global configuration as main.ts (pipes, filters, etc.)
    ├── Use realistic test data
    ├── Test error cases and edge cases
    ├── Test authentication flows
    └── Don't mock what you're testing (real DB for integration tests)
```

---

## Module 3.5: Logging

### Section 3.5.1 — NestJS Logger
```
├── Built-in Logger:
│   ├── this.logger = new Logger(UsersService.name);
│   ├── Levels: log, error, warn, debug, verbose
│   ├── this.logger.log('User created', { userId: user.id });
│   └── Context: Automatically shows class name
├── Custom Logger:
│   ├── Implement LoggerService interface
│   ├── Replace default: app.useLogger(new CustomLogger())
│   └── Use cases: JSON structured logging, External logging service
├── Pino Logger (@nestjs/pino — Recommended for Production):
│   ├── npm install nestjs-pino pino-http pino-pretty
│   ├── Fast, Structured JSON logging
│   ├── Request context (correlation ID, method, URL)
│   └── LoggerModule.forRoot({
│         pinoHttp: {
│           transport: process.env.NODE_ENV !== 'production'
│             ? { target: 'pino-pretty' }
│             : undefined,
│         },
│       })
├── Winston Logger (nest-winston):
│   ├── npm install nest-winston winston
│   ├── Multiple transports: Console, File, External services
│   └── Flexible formatting
├── Correlation IDs:
│   ├── Generate per request (middleware or interceptor)
│   ├── Attach to every log message
│   ├── Pass to downstream services via headers
│   └── cls-hooked or AsyncLocalStorage for context propagation
└── Best Practices:
    ├── Use structured logging (JSON) in production
    ├── Include correlation IDs in every log
    ├── Log business events, not just errors
    ├── Never log sensitive data (passwords, tokens, PII)
    ├── Use appropriate log levels
    └── Configure log level via environment variable
```

---

## Module 3.6: Swagger / OpenAPI Documentation

### Section 3.6.1 — API Documentation
```
├── Setup:
│   ├── npm install @nestjs/swagger
│   └── Configure in main.ts (see Module 2.1.2)
├── Controller Decorators:
│   ├── @ApiTags('users')               ← Group endpoints
│   ├── @ApiOperation({ summary: '...' }) ← Describe endpoint
│   ├── @ApiResponse({ status: 200, type: UserEntity }) ← Response schema
│   ├── @ApiResponse({ status: 404, description: 'User not found' })
│   ├── @ApiBearerAuth()                ← Indicate JWT auth
│   ├── @ApiParam({ name: 'id', type: 'string' }) ← Document params
│   ├── @ApiQuery({ name: 'page', required: false }) ← Document query
│   └── @ApiConsumes('multipart/form-data') ← Content type
├── DTO Decorators:
│   ├── @ApiProperty({ example: 'John', description: 'User name' })
│   ├── @ApiPropertyOptional({ default: 1 })
│   ├── @ApiHideProperty()              ← Hide from docs
│   └── CLI Plugin: Auto-infer from TypeScript types (nest-cli.json)
│       └── "plugins": ["@nestjs/swagger"]  ← Auto-generate ApiProperty!
├── Advanced:
│   ├── @ApiExtraModels(PaginatedDto)   ← Register extra models
│   ├── @ApiBody({ type: [CreateUserDto] }) ← Array body
│   ├── Generic Responses: Use @ApiOkResponse with getSchemaPath()
│   └── Multiple Swagger Docs: Different docs for different API versions
└── Best Practices:
    ├── Use the CLI plugin to auto-generate most decorators
    ├── Always provide examples in @ApiProperty()
    ├── Document ALL error responses
    ├── Group endpoints with @ApiTags()
    └── Keep Swagger doc in sync — it IS your contract
```

---

> ### 🛠️ PHASE 3 PROJECT: **Task Manager API with Full Architecture**
> ```
> ┌─────────────────────────────────────────────────────────────────┐
> │            TASK MANAGER API — DEEP ARCHITECTURE                 │
> ├─────────────────────────────────────────────────────────────────┤
> │                                                                 │
> │ Rebuild Phase 2 Blog API with production-grade architecture:    │
> │                                                                 │
> │  ✅ Namespaced Configuration: app, database, auth, mail configs │
> │  ✅ Environment Validation: Joi schema, Crash on missing vars   │
> │  ✅ Structured Logging: nestjs-pino, Correlation IDs            │
> │  ✅ Full Request Lifecycle demonstrated with each building block │
> │  ✅ Lifecycle Hooks: OnModuleInit, Graceful shutdown             │
> │  ✅ Swagger: 100% documented API, Examples on every DTO          │
> │  ✅ Unit Tests: 90%+ coverage on services, guards, pipes         │
> │  ✅ E2E Tests: Full CRUD flows, Auth flows, Error cases          │
> │  ✅ Custom Dynamic Module: NotificationModule.forRoot(options)   │
> │  ✅ Health Check: @nestjs/terminus (DB, Memory, Disk)            │
> │  ✅ Composed Decorators: @Auth(), @ApiPaginatedResponse()        │
> │  ✅ Still in-memory storage (DB comes in Phase 4)                │
> └─────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 🗄️ PHASE 4: DATA LAYER & DATABASE MASTERY
### 📅 Duration: Weeks 9–14
### 🎯 Goal: Master every database integration pattern in NestJS
### 👤 Level: Mid-Level Developer

---

## Module 4.1: TypeORM Integration

### Section 4.1.1 — Setup & Configuration
```
├── Installation: npm install @nestjs/typeorm typeorm pg
├── Root Configuration:
│   └── TypeOrmModule.forRootAsync({
│         imports: [ConfigModule],
│         useFactory: (config: ConfigService) => ({
│           type: 'postgres',
│           host: config.get('DB_HOST'),
│           port: config.get('DB_PORT'),
│           username: config.get('DB_USER'),
│           password: config.get('DB_PASS'),
│           database: config.get('DB_NAME'),
│           entities: [__dirname + '/**/*.entity{.ts,.js}'],
│           autoLoadEntities: true,      // Auto-discover entities
│           synchronize: false,          // NEVER true in production!
│           logging: config.get('NODE_ENV') === 'development',
│           ssl: config.get('NODE_ENV') === 'production' ? { rejectUnauthorized: false } : false,
│         }),
│         inject: [ConfigService],
│       })
├── Feature Module Registration:
│   └── TypeOrmModule.forFeature([UserEntity, ProfileEntity])
│   └── This makes repositories available in the module
├── Migrations:
│   ├── npm run typeorm migration:generate -- -n MigrationName
│   ├── npm run typeorm migration:run
│   ├── npm run typeorm migration:revert
│   └── Always use migrations, NEVER synchronize in production
└── Data Source (TypeORM 0.3+):
    ├── data-source.ts: Standalone config for CLI migrations
    └── Share config between NestJS module and CLI
```

### Section 4.1.2 — Entities & Relations
```
├── Entity Definition:
│   └── @Entity('users')
│       export class UserEntity {
│         @PrimaryGeneratedColumn('uuid')
│         id: string;
│
│         @Column({ type: 'varchar', length: 255, unique: true })
│         email: string;
│
│         @Column({ type: 'varchar', length: 100 })
│         name: string;
│
│         @Column({ select: false })  // Not included in queries by default
│         password: string;
│
│         @Column({ type: 'enum', enum: UserRole, default: UserRole.USER })
│         role: UserRole;
│
│         @Column({ type: 'boolean', default: true })
│         isActive: boolean;
│
│         @CreateDateColumn()
│         createdAt: Date;
│
│         @UpdateDateColumn()
│         updatedAt: Date;
│
│         @DeleteDateColumn()  // Soft delete support
│         deletedAt: Date;
│       }
├── Relations:
│   ├── @OneToOne(() => ProfileEntity, profile => profile.user, { cascade: true })
│   │   @JoinColumn()
│   │   profile: ProfileEntity;
│   ├── @OneToMany(() => PostEntity, post => post.author)
│   │   posts: PostEntity[];
│   ├── @ManyToOne(() => UserEntity, user => user.posts, { onDelete: 'CASCADE' })
│   │   @JoinColumn({ name: 'author_id' })
│   │   author: UserEntity;
│   └── @ManyToMany(() => TagEntity, tag => tag.posts)
│       @JoinTable({ name: 'post_tags' })
│       tags: TagEntity[];
├── Relation Options:
│   ├── eager: true/false — Auto-load relations (default false)
│   ├── cascade: true/['insert', 'update'] — Cascade operations
│   ├── onDelete: 'CASCADE' | 'SET NULL' | 'RESTRICT'
│   ├── nullable: true/false
│   └── lazy: true — Load via Promise (post.tags.then(...))
├── Embeddable Entities:
│   └── @Column(() => AddressEmbed)
│       address: AddressEmbed;
├── Single Table Inheritance:
│   └── @TableInheritance({ column: { name: 'type' } })
│       @ChildEntity('admin')
│       export class AdminEntity extends UserEntity { ... }
├── Indexes:
│   ├── @Index() on column
│   ├── @Index(['email', 'name']) composite index on entity
│   └── @Unique(['email']) unique constraint
└── Subscribers & Listeners:
    ├── @BeforeInsert(), @BeforeUpdate(), @AfterLoad()
    └── Entity Subscribers: @EventSubscriber() for cross-cutting concerns
```

### Section 4.1.3 — Repository Pattern (TypeORM)
```
├── Injecting Repository:
│   └── constructor(
│         @InjectRepository(UserEntity)
│         private readonly usersRepo: Repository<UserEntity>,
│       ) {}
├── Basic Operations:
│   ├── Create: this.usersRepo.create(dto) → entity instance (NOT saved)
│   ├── Save: this.usersRepo.save(entity) → INSERT or UPDATE
│   ├── Find: this.usersRepo.find({ where: { isActive: true } })
│   ├── FindOne: this.usersRepo.findOne({ where: { id } })
│   ├── FindOneOrFail: this.usersRepo.findOneOrFail(...)  → throws if not found
│   ├── Update: this.usersRepo.update(id, { name: 'New Name' }) → UPDATE query
│   ├── Delete: this.usersRepo.delete(id) → Hard delete
│   ├── Soft Delete: this.usersRepo.softDelete(id)
│   ├── Restore: this.usersRepo.restore(id)
│   ├── Count: this.usersRepo.count({ where: { ... } })
│   └── Exists: this.usersRepo.exist({ where: { email } })
├── Find Options:
│   ├── where: { name: 'John', role: In([Role.ADMIN, Role.USER]) }
│   ├── relations: { profile: true, posts: { tags: true } }
│   ├── select: { id: true, name: true, email: true }
│   ├── order: { createdAt: 'DESC' }
│   ├── skip: 0, take: 20  (pagination)
│   └── withDeleted: true  (include soft-deleted)
├── Where Operators:
│   ├── Equal, Not, LessThan, MoreThan, LessThanOrEqual, MoreThanOrEqual
│   ├── Between(start, end), In([values]), IsNull()
│   ├── Like('%pattern%'), ILike('%pattern%') (case-insensitive)
│   ├── Raw(alias => `${alias} > NOW()`)
│   └── And(), Or() for complex conditions
├── QueryBuilder (Complex Queries):
│   └── this.usersRepo.createQueryBuilder('user')
│       .leftJoinAndSelect('user.posts', 'post')
│       .where('user.isActive = :isActive', { isActive: true })
│       .andWhere('post.createdAt > :date', { date })
│       .orderBy('user.createdAt', 'DESC')
│       .skip(offset)
│       .take(limit)
│       .getManyAndCount();
├── Transactions:
│   ├── DataSource transaction:
│   │   └── await this.dataSource.transaction(async manager => {
│   │         await manager.save(user);
│   │         await manager.save(profile);
│   │       });
│   ├── QueryRunner transaction:
│   │   └── Manual BEGIN, COMMIT, ROLLBACK
│   └── Decorator approach: @Transaction(), @TransactionManager()
└── Custom Repository:
    ├── TypeORM 0.3+: Extend Repository with custom methods
    │   └── @Injectable()
    │       export class UsersRepository extends Repository<UserEntity> {
    │         constructor(private dataSource: DataSource) {
    │           super(UserEntity, dataSource.createEntityManager());
    │         }
    │         async findByEmail(email: string): Promise<UserEntity | null> {
    │           return this.findOne({ where: { email } });
    │         }
    │       }
    └── Register as provider in module
```

---

## Module 4.2: Prisma Integration

### Section 4.2.1 — Prisma Setup
```
├── Installation:
│   └── npm install prisma @prisma/client
│   └── npx prisma init
├── Schema (schema.prisma):
│   └── generator client {
│         provider = "prisma-client-js"
│       }
│       datasource db {
│         provider = "postgresql"
│         url      = env("DATABASE_URL")
│       }
│       model User {
│         id        String   @id @default(uuid())
│         email     String   @unique
│         name      String
│         password  String
│         role      Role     @default(USER)
│         posts     Post[]
│         profile   Profile?
│         createdAt DateTime @default(now())
│         updatedAt DateTime @updatedAt
│         @@map("users")
│       }
│       enum Role { USER ADMIN MODERATOR }
├── NestJS Service:
│   └── @Injectable()
│       export class PrismaService extends PrismaClient implements OnModuleInit, OnModuleDestroy {
│         async onModuleInit() { await this.$connect(); }
│         async onModuleDestroy() { await this.$disconnect(); }
│       }
├── Migrations:
│   ├── npx prisma migrate dev --name init    ← Development
│   ├── npx prisma migrate deploy             ← Production
│   ├── npx prisma db push                    ← Quick sync (no migration file)
│   └── npx prisma generate                   ← Regenerate client
├── Usage in Service:
│   └── @Injectable()
│       export class UsersService {
│         constructor(private prisma: PrismaService) {}
│         async create(dto: CreateUserDto) {
│           return this.prisma.user.create({ data: dto });
│         }
│         async findAll(params: { skip?: number; take?: number }) {
│           return this.prisma.user.findMany({
│             skip: params.skip,
│             take: params.take,
│             include: { profile: true },
│           });
│         }
│       }
├── Prisma vs TypeORM:
│   ├── Prisma: Schema-first, Type-safe, Better DX, Newer
│   ├── TypeORM: Code-first (decorators), Mature, More flexible
│   ├── Prisma: Better for new projects
│   └── TypeORM: Better for complex queries, Existing projects
└── Advanced Prisma:
    ├── Middleware: Logging, Soft deletes, Audit trails
    ├── Interactive Transactions: prisma.$transaction(async (tx) => { ... })
    ├── Raw Queries: prisma.$queryRaw`SELECT * FROM users WHERE ...`
    └── Prisma Studio: npx prisma studio — Visual database browser
```

---

## Module 4.3: MikroORM Integration (Alternative)

### Section 4.3.1 — MikroORM Overview
```
├── Why MikroORM: Strict Unit of Work, Identity Map, Better DDD support
├── Installation: npm install @mikro-orm/core @mikro-orm/nestjs @mikro-orm/postgresql
├── Entity Definition: @Entity(), @Property(), @ManyToOne()
├── Unit of Work: Track changes, Flush once (batch operations)
├── Identity Map: Same entity loaded twice = same instance
├── NestJS Module: MikroOrmModule.forRoot(config)
├── Repository: @InjectRepository(UserEntity) — EntityRepository<UserEntity>
└── When to choose: DDD projects, Complex domain logic, Unit of Work pattern
```

---

## Module 4.4: Advanced Data Patterns

### Section 4.4.1 — Pagination
```
├── Offset-Based (Simple):
│   └── findAll(page: number, limit: number) {
│         const [items, total] = await this.repo.findAndCount({
│           skip: (page - 1) * limit,
│           take: limit,
│           order: { createdAt: 'DESC' },
│         });
│         return { items, total, page, limit, totalPages: Math.ceil(total / limit) };
│       }
│   └── Problem: Performance degrades on large offsets (OFFSET 100000)
├── Cursor-Based (Recommended for large datasets):
│   └── Use last item's ID/timestamp as cursor
│   └── WHERE id > :cursor ORDER BY id LIMIT :limit
│   └── Better performance, No page skipping
├── Pagination DTO:
│   └── export class PaginationDto {
│         @IsOptional() @IsInt() @Min(1) page?: number = 1;
│         @IsOptional() @IsInt() @Min(1) @Max(100) limit?: number = 20;
│         @IsOptional() @IsString() sortBy?: string = 'createdAt';
│         @IsOptional() @IsIn(['ASC', 'DESC']) order?: 'ASC' | 'DESC' = 'DESC';
│       }
└── Response Format:
    └── { data: T[], meta: { total, page, limit, totalPages, hasNext, hasPrev } }
```

### Section 4.4.2 — Filtering & Searching
```
├── Dynamic Filtering:
│   └── Build QueryBuilder conditions from query parameters
│   └── if (filter.name) qb.andWhere('user.name ILIKE :name', { name: `%${filter.name}%` });
│   └── if (filter.role) qb.andWhere('user.role = :role', { role: filter.role });
├── Full-Text Search: PostgreSQL tsvector/tsquery, Or use Elasticsearch
├── Filter DTO: Validate and type filter parameters
└── Generic Filtering: Abstract filter builder for reuse across entities
```

### Section 4.4.3 — Caching
```
├── @nestjs/cache-manager:
│   ├── npm install @nestjs/cache-manager cache-manager cache-manager-redis-yet
│   ├── CacheModule.register({ store: redisStore, ttl: 300 })
│   ├── @UseInterceptors(CacheInterceptor) — Auto-cache GET responses
│   ├── Manual: @Inject(CACHE_MANAGER) private cache: Cache
│   │   ├── await this.cache.get<User>('user:1')
│   │   ├── await this.cache.set('user:1', user, 3600)
│   │   └── await this.cache.del('user:1')
│   └── Cache Key: @CacheKey('custom-key'), @CacheTTL(60)
├── Redis Integration:
│   ├── npm install ioredis @nestjs-modules/ioredis (or custom provider)
│   ├── Direct Redis client for complex operations
│   └── Pub/Sub, Sorted sets, Streams, Lua scripts
└── Cache Invalidation Strategies:
    ├── TTL-based: Auto-expire after N seconds
    ├── Event-based: Invalidate on create/update/delete
    └── Cache-aside with write-through: Update cache on write
```

### Section 4.4.4 — Seeding & Fixtures
```
├── typeorm-seeding: Seed data for development and testing
├── Custom Seeders:
│   └── @Injectable()
│       export class DatabaseSeeder implements OnModuleInit {
│         async onModuleInit() {
│           if (process.env.SEED === 'true') await this.seed();
│         }
│       }
├── Factories: Generate realistic test data (faker.js / @faker-js/faker)
└── Test Fixtures: Predictable data for integration tests
```

---

> ### 🛠️ PHASE 4 PROJECT: **Multi-Feature REST API with Real Database**
> ```
> ┌─────────────────────────────────────────────────────────────────┐
> │         MULTI-FEATURE REST API WITH PostgreSQL                  │
> ├─────────────────────────────────────────────────────────────────┤
> │                                                                 │
> │ Choose TypeORM OR Prisma (implement with one, study the other)  │
> │                                                                 │
> │ Domain: Project Management Tool (mini Jira)                     │
> │                                                                 │
> │ Entities:                                                       │
> │  • User (auth, profile, avatar)                                 │
> │  • Organization (multi-tenant context)                          │
> │  • Project (belongs to organization)                            │
> │  • Task (title, description, status, priority, assignee, due)   │
> │  • Comment (on tasks, by users)                                 │
> │  • Label (many-to-many with tasks)                              │
> │  • Activity Log (audit trail)                                   │
> │                                                                 │
> │ Data Layer Requirements:                                        │
> │  ✅ PostgreSQL with proper schema design                         │
> │  ✅ Migrations (NOT synchronize)                                 │
> │  ✅ Relations: 1:1, 1:N, N:M all demonstrated                   │
> │  ✅ Soft deletes on tasks and comments                           │
> │  ✅ Pagination: Offset + Cursor-based                            │
> │  ✅ Advanced filtering: Status, Priority, Assignee, Date range  │
> │  ✅ Full-text search on task title/description                   │
> │  ✅ Redis caching: Cache-aside for frequently accessed data      │
> │  ✅ Transactions: Task creation with activity log (atomic)       │
> │  ✅ Database seeder with Faker.js                                │
> │  ✅ Custom repository with complex queries                       │
> │  ✅ E2E tests with Testcontainers (real PostgreSQL)              │
> │  ✅ Swagger documentation with all response types                │
> │  ✅ Health checks: Database + Redis connectivity                 │
> └─────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 🔒 PHASE 5: SECURITY, AUTH & ACCESS CONTROL
### 📅 Duration: Weeks 14–18
### 🎯 Goal: Implement production-grade authentication & authorization
### 👤 Level: Mid-Senior Developer

---

## Module 5.1: Passport.js Integration

### Section 5.1.1 — @nestjs/passport Setup
```
├── Installation: npm install @nestjs/passport passport @nestjs/jwt passport-jwt passport-local
├── Passport Strategies:
│   ├── Local Strategy: Username/password login
│   │   └── @Injectable()
│   │       export class LocalStrategy extends PassportStrategy(Strategy) {
│   │         constructor(private authService: AuthService) { super({ usernameField: 'email' }); }
│   │         async validate(email: string, password: string): Promise<User> {
│   │           const user = await this.authService.validateUser(email, password);
│   │           if (!user) throw new UnauthorizedException();
│   │           return user; // Attached to request.user
│   │         }
│   │       }
│   ├── JWT Strategy: Token-based authentication
│   │   └── @Injectable()
│   │       export class JwtStrategy extends PassportStrategy(Strategy) {
│   │         constructor(config: ConfigService) {
│   │           super({
│   │             jwtFromRequest: ExtractJwt.fromAuthHeaderAsBearerToken(),
│   │             ignoreExpiration: false,
│   │             secretOrKey: config.get('JWT_SECRET'),
│   │           });
│   │         }
│   │         async validate(payload: JwtPayload) {
│   │           return { id: payload.sub, email: payload.email, roles: payload.roles };
│   │         }
│   │       }
│   ├── OAuth2 Strategies: Google, GitHub, Facebook
│   │   └── passport-google-oauth20, passport-github2
│   └── API Key Strategy: Custom strategy for service-to-service auth
├── Auth Guards:
│   ├── @UseGuards(AuthGuard('local'))   → Trigger local strategy
│   ├── @UseGuards(AuthGuard('jwt'))     → Trigger JWT strategy
│   └── Custom JwtAuthGuard: Extend AuthGuard('jwt') to add custom logic
│       └── Handle token expiration, Refresh token logic, Custom error messages
├── Login Flow:
│   └── @Post('login')
│       @UseGuards(AuthGuard('local'))
│       async login(@Request() req) {
│         return this.authService.login(req.user); // Generate JWT
│       }
├── Registration Flow:
│   └── Hash password (bcrypt), Create user, Generate JWT, Return tokens
└── Token Generation:
    └── async login(user: User) {
          const payload = { sub: user.id, email: user.email, roles: user.roles };
          return {
            access_token: this.jwtService.sign(payload, { expiresIn: '15m' }),
            refresh_token: this.jwtService.sign(payload, { expiresIn: '7d' }),
          };
        }
```

### Section 5.1.2 — JWT Token Management
```
├── Access Token:
│   ├── Short-lived: 15 minutes
│   ├── Contains: userId, email, roles
│   ├── Stateless: No server-side storage needed
│   └── Sent: Authorization: Bearer <token>
├── Refresh Token:
│   ├── Long-lived: 7-30 days
│   ├── Stored: In database or Redis (for revocation)
│   ├── Hashed: bcrypt hash in database (never store plain)
│   ├── Rotation: Issue new refresh token on each refresh
│   └── Revocation: Delete from database on logout
├── Token Refresh Flow:
│   └── POST /auth/refresh
│       1. Validate refresh token
│       2. Check if token exists in database (not revoked)
│       3. Generate new access token + new refresh token
│       4. Invalidate old refresh token
│       5. Store new refresh token hash
│       6. Return both new tokens
├── Logout:
│   └── Delete refresh token from database
│   └── Optionally: Add access token to blacklist (Redis with TTL)
├── Token Blacklisting (for access tokens):
│   ├── Store blacklisted JTI (JWT ID) in Redis
│   ├── TTL = remaining access token lifetime
│   ├── Check blacklist in JWT strategy validate()
│   └── Trade-off: Adds a Redis check per request
└── Password Hashing:
    ├── bcrypt: npm install bcrypt @types/bcrypt
    ├── Rounds: 10-12 (balance security vs performance)
    ├── Hash: await bcrypt.hash(password, 10)
    └── Compare: await bcrypt.compare(password, hash)
```

---

## Module 5.2: Authorization

### Section 5.2.1 — Role-Based Access Control (RBAC)
```
├── Roles Enum:
│   └── export enum Role { USER = 'user', ADMIN = 'admin', MODERATOR = 'moderator' }
├── Roles Decorator:
│   └── export const Roles = (...roles: Role[]) => SetMetadata(ROLES_KEY, roles);
├── Roles Guard:
│   └── @Injectable()
│       export class RolesGuard implements CanActivate {
│         constructor(private reflector: Reflector) {}
│         canActivate(context: ExecutionContext): boolean {
│           const requiredRoles = this.reflector.getAllAndOverride<Role[]>(
│             ROLES_KEY, [context.getHandler(), context.getClass()]);
│           if (!requiredRoles) return true;
│           const { user } = context.switchToHttp().getRequest();
│           return requiredRoles.some(role => user.roles?.includes(role));
│         }
│       }
├── Usage:
│   └── @Get('admin/dashboard')
│       @Roles(Role.ADMIN)
│       @UseGuards(JwtAuthGuard, RolesGuard)
│       getAdminDashboard() { ... }
└── Composed Decorator:
    └── export function Auth(...roles: Role[]) {
          return applyDecorators(
            Roles(...roles),
            UseGuards(JwtAuthGuard, RolesGuard),
            ApiBearerAuth(),
          );
        }
    └── Usage: @Auth(Role.ADMIN)
```

### Section 5.2.2 — Permission-Based Access Control
```
├── Permissions: More granular than roles
│   └── export enum Permission {
│         READ_USERS = 'read:users',
│         CREATE_USERS = 'create:users',
│         UPDATE_USERS = 'update:users',
│         DELETE_USERS = 'delete:users',
│         MANAGE_PROJECTS = 'manage:projects',
│       }
├── @Permissions() decorator + PermissionsGuard
├── Role → Permissions mapping: Each role has a SET of permissions
└── CASL Integration (@casl/ability):
    ├── npm install @casl/ability
    ├── Define abilities based on user role
    ├── Check abilities in guards or services
    ├── Resource-level permissions: "Can user X edit post Y?"
    └── Example:
        const ability = defineAbility((can, cannot) => {
          can('read', 'Post');
          can('update', 'Post', { authorId: user.id }); // Own posts only
          cannot('delete', 'Post').because('Not allowed');
        });
```

### Section 5.2.3 — Resource Ownership
```
├── Problem: User can only update THEIR OWN resources
├── Policy Guard:
│   └── Check if request.user.id === resource.userId
│   └── Load resource in guard using service injection
├── Policy-Based Authorization:
│   ├── Create policies per resource: UserPolicy, PostPolicy
│   ├── Methods: canUpdate(user, post), canDelete(user, post)
│   └── Check in guard or decorator
└── Best Practice: Separate auth (who are you?) from authz (what can you do?)
```

---

## Module 5.3: Security Best Practices

### Section 5.3.1 — Application Security
```
├── Helmet: Security headers
│   └── app.use(helmet()) in main.ts
├── CORS: Cross-Origin Resource Sharing
│   └── app.enableCors({ origin: ['https://myapp.com'], credentials: true })
├── Rate Limiting: @nestjs/throttler
│   ├── npm install @nestjs/throttler
│   ├── ThrottlerModule.forRoot([{ ttl: 60000, limit: 100 }])
│   ├── @UseGuards(ThrottlerGuard) — or global
│   ├── @SkipThrottle() — Skip on specific routes
│   └── @Throttle({ default: { limit: 3, ttl: 60000 } }) — Per-route override
├── CSRF Protection: csurf middleware (for cookie-based auth)
├── Input Validation: ValidationPipe (whitelist + forbidNonWhitelisted)
├── SQL Injection: Use parameterized queries (TypeORM/Prisma handle this)
├── XSS: Sanitize HTML input (sanitize-html, DOMPurify for server)
├── Sensitive Data:
│   ├── Never log passwords, Tokens, Credit cards
│   ├── @Exclude() on entity password field
│   ├── Hash passwords with bcrypt (never store plain)
│   └── Encrypt PII at rest if required
├── File Upload Security:
│   ├── Validate file type: MIME type, File extension
│   ├── Limit file size: ParseFilePipe with MaxFileSize
│   ├── Scan for malware: ClamAV integration
│   └── Store outside web root: S3, Not public/uploads
└── Dependency Security:
    ├── npm audit: Check for vulnerabilities
    ├── Snyk / Dependabot: Automated dependency scanning
    └── Lock files: Always commit package-lock.json
```

---

## Module 5.4: OAuth2 & Social Login

### Section 5.4.1 — Google OAuth2
```
├── npm install passport-google-oauth20 @types/passport-google-oauth20
├── Strategy:
│   └── @Injectable()
│       export class GoogleStrategy extends PassportStrategy(Strategy, 'google') {
│         constructor(config: ConfigService) {
│           super({
│             clientID: config.get('GOOGLE_CLIENT_ID'),
│             clientSecret: config.get('GOOGLE_CLIENT_SECRET'),
│             callbackURL: config.get('GOOGLE_CALLBACK_URL'),
│             scope: ['email', 'profile'],
│           });
│         }
│         async validate(accessToken, refreshToken, profile, done) {
│           const user = await this.authService.findOrCreateOAuthUser(profile);
│           done(null, user);
│         }
│       }
├── Routes:
│   ├── @Get('google') @UseGuards(AuthGuard('google')) → Redirect to Google
│   └── @Get('google/callback') @UseGuards(AuthGuard('google')) → Handle callback
├── GitHub, Facebook, Apple: Same pattern, Different passport strategies
└── Account Linking: Link OAuth accounts to existing email-based accounts
```

---

> ### 🛠️ PHASE 5 PROJECT: **Secure Multi-Auth API**
> ```
> ┌─────────────────────────────────────────────────────────────────┐
> │                 SECURE MULTI-AUTH API                            │
> ├─────────────────────────────────────────────────────────────────┤
> │                                                                 │
> │ Build on top of Phase 4 Project and add:                        │
> │                                                                 │
> │  ✅ Local Auth: Email/password registration + login (bcrypt)     │
> │  ✅ JWT: Access token (15min) + Refresh token (7d) + Rotation   │
> │  ✅ Token Refresh: POST /auth/refresh with token rotation       │
> │  ✅ Logout: Refresh token revocation in Redis                    │
> │  ✅ Google OAuth2: Social login with account linking             │
> │  ✅ RBAC: Admin, Moderator, User roles                          │
> │  ✅ Permission-Based: CASL integration for resource permissions  │
> │  ✅ Resource Ownership: Users can only edit own tasks/comments   │
> │  ✅ Rate Limiting: 100 req/min general, 5 req/min for login     │
> │  ✅ Helmet: Security headers                                    │
> │  ✅ CORS: Properly configured for frontend origin               │
> │  ✅ Input Sanitization: Strip HTML from user inputs              │
> │  ✅ @Public() decorator: Skip auth on specific routes            │
> │  ✅ @Auth(Role.ADMIN) composed decorator                        │
> │  ✅ Password reset flow: Email token + Reset endpoint            │
> │  ✅ Email verification: Verification token + Confirm endpoint    │
> │  ✅ E2E tests: All auth flows tested                             │
> └─────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 🤖 PHASE 6: REAL-TIME, GraphQL & ADVANCED APIs
### 📅 Duration: Weeks 18–23
### 🎯 Goal: Master real-time communication, GraphQL, and advanced API patterns
### 👤 Level: Advanced Developer

---

## Module 6.1: WebSockets & Real-Time

### Section 6.1.1 — @nestjs/websockets
```
├── Installation: npm install @nestjs/websockets @nestjs/platform-socket.io socket.io
├── Gateway:
│   └── @WebSocketGateway({
│         cors: { origin: '*' },
│         namespace: '/chat',
│       })
│       export class ChatGateway implements OnGatewayInit, OnGatewayConnection, OnGatewayDisconnect {
│         @WebSocketServer() server: Server;
│
│         @SubscribeMessage('sendMessage')
│         handleMessage(@MessageBody() data: CreateMessageDto, @ConnectedSocket() client: Socket) {
│           this.server.to(data.room).emit('newMessage', data);
│         }
│
│         handleConnection(client: Socket) { console.log('Client connected:', client.id); }
│         handleDisconnect(client: Socket) { console.log('Client disconnected:', client.id); }
│       }
├── Decorators:
│   ├── @WebSocketGateway(): Define WebSocket gateway
│   ├── @WebSocketServer(): Inject server instance
│   ├── @SubscribeMessage('event'): Listen for events
│   ├── @MessageBody(): Extract message payload
│   └── @ConnectedSocket(): Access client socket
├── Rooms:
│   ├── client.join('room-1')
│   ├── client.leave('room-1')
│   ├── this.server.to('room-1').emit('event', data)
│   └── Use case: Chat rooms, Per-user channels, Per-project updates
├── Guards & Pipes in WebSockets:
│   ├── @UseGuards(WsJwtGuard) — Same pattern as HTTP guards
│   ├── @UsePipes(new ValidationPipe()) — Validate message body
│   └── WsException: Throw instead of HttpException for WebSocket errors
├── Adapter:
│   ├── Default: Socket.IO
│   ├── Alternative: ws library (lighter weight)
│   └── Redis Adapter: Scale WebSockets across multiple servers
│       └── npm install @socket.io/redis-adapter
│       └── Pub/Sub: Sync events across Node.js instances
└── Broadcasting:
    ├── this.server.emit('event', data)          ← All clients
    ├── this.server.to('room').emit(...)         ← Specific room
    ├── client.broadcast.emit(...)               ← All EXCEPT sender
    └── this.server.to(socketId).emit(...)       ← Specific client
```

### Section 6.1.2 — Server-Sent Events (SSE)
```
├── Implementation:
│   └── @Sse('events')
│       events(): Observable<MessageEvent> {
│         return interval(1000).pipe(
│           map(num => ({ data: { count: num } })),
│         );
│       }
├── Use Case: Notifications, Live feeds, Progress updates
├── SSE vs WebSocket:
│   ├── SSE: Server → Client only, Simpler, HTTP-based, Auto-reconnect
│   └── WebSocket: Bidirectional, More complex, Custom protocol
└── Real-world: Push notifications, Order status updates, Dashboard metrics
```

---

## Module 6.2: GraphQL

### Section 6.2.1 — Code-First Approach
```
├── Installation: npm install @nestjs/graphql @nestjs/apollo @apollo/server graphql
├── Module Setup:
│   └── GraphQLModule.forRoot<ApolloDriverConfig>({
│         driver: ApolloDriver,
│         autoSchemaFile: join(process.cwd(), 'src/schema.gql'),
│         sortSchema: true,
│         playground: true,
│         context: ({ req }) => ({ req }), // Pass request for auth
│       })
├── Object Types:
│   └── @ObjectType()
│       export class User {
│         @Field(() => ID) id: string;
│         @Field() name: string;
│         @Field() email: string;
│         @Field(() => [Post]) posts: Post[];
│         // password NOT decorated with @Field() → excluded from schema
│       }
├── Resolvers:
│   └── @Resolver(() => User)
│       export class UsersResolver {
│         constructor(private usersService: UsersService) {}
│
│         @Query(() => [User], { name: 'users' })
│         findAll() { return this.usersService.findAll(); }
│
│         @Query(() => User, { name: 'user', nullable: true })
│         findOne(@Args('id', { type: () => ID }) id: string) {
│           return this.usersService.findOne(id);
│         }
│
│         @Mutation(() => User)
│         createUser(@Args('input') input: CreateUserInput) {
│           return this.usersService.create(input);
│         }
│
│         @ResolveField(() => [Post])
│         posts(@Parent() user: User) {
│           return this.postsService.findByAuthor(user.id);
│         }
│       }
├── Input Types:
│   └── @InputType()
│       export class CreateUserInput {
│         @Field() @IsString() @IsNotEmpty() name: string;
│         @Field() @IsEmail() email: string;
│       }
├── Subscriptions (Real-time GraphQL):
│   └── @Subscription(() => Post, { resolve: value => value.newPost })
│       postAdded() { return this.pubSub.asyncIterator('postAdded'); }
│   └── Publish: this.pubSub.publish('postAdded', { newPost: post });
├── N+1 Problem:
│   ├── DataLoader: Batch and cache database requests
│   ├── npm install dataloader
│   └── Create per-request DataLoader instances
│       └── @ResolveField() async posts(@Parent() user: User, @Context() ctx) {
│             return ctx.loaders.postsLoader.load(user.id);
│           }
├── Authentication in GraphQL:
│   ├── Use guards: @UseGuards(GqlAuthGuard) — extends AuthGuard('jwt')
│   ├── GqlExecutionContext: getContext().req instead of switchToHttp()
│   └── @CurrentUser() decorator: Extract user from GraphQL context
├── Complexity & Depth Limiting:
│   ├── Prevent deeply nested queries (DoS protection)
│   ├── graphql-query-complexity: Limit query cost
│   └── graphql-depth-limit: Limit nesting depth
└── Federation:
    ├── Apollo Federation: Compose multiple GraphQL services
    ├── @nestjs/graphql supports Federation directives
    └── @Key, @External, @Requires, @Provides directives
```

### Section 6.2.2 — Schema-First Approach
```
├── Write .graphql schema files manually
├── Generate TypeScript types from schema
├── Useful for: Teams with non-TypeScript services, Schema standardization
└── Most NestJS projects prefer Code-First
```

---

## Module 6.3: Microservices in NestJS

### Section 6.3.1 — @nestjs/microservices
```
├── Installation: npm install @nestjs/microservices
├── Transport Layers:
│   ├── TCP: Default, Simple, Development
│   ├── Redis: Pub/Sub based, Easy setup
│   ├── NATS: Lightweight, High performance
│   ├── MQTT: IoT-friendly
│   ├── Kafka: Event streaming, High throughput
│   ├── gRPC: Binary protocol, Schema-defined, Type-safe
│   └── RabbitMQ: Full-featured message broker
├── Message Patterns:
│   ├── Request-Response (@MessagePattern):
│   │   └── @MessagePattern({ cmd: 'get_user' })
│   │       getUser(@Payload() data: { id: string }) { return this.service.findOne(data.id); }
│   │   └── Client: this.client.send({ cmd: 'get_user' }, { id: '1' })
│   └── Event-Based (@EventPattern):
│       └── @EventPattern('user_created')
│           handleUserCreated(@Payload() data: UserCreatedEvent) { ... }
│       └── Client: this.client.emit('user_created', userData)
├── Client Proxy:
│   └── constructor(@Inject('USERS_SERVICE') private client: ClientProxy) {}
│   └── Registration:
│       ClientsModule.register([{
│         name: 'USERS_SERVICE',
│         transport: Transport.TCP,
│         options: { host: 'localhost', port: 3001 },
│       }])
├── Hybrid Application (HTTP + Microservice):
│   └── const app = await NestFactory.create(AppModule);
│       app.connectMicroservice<MicroserviceOptions>({
│         transport: Transport.REDIS,
│         options: { host: 'localhost', port: 6379 },
│       });
│       await app.startAllMicroservices();
│       await app.listen(3000);
├── Kafka Integration:
│   ├── Producer: this.client.emit('topic', { key, value })
│   ├── Consumer: @EventPattern('topic') + @Payload() + @Ctx() KafkaContext
│   ├── Configuration: Client ID, Group ID, Brokers
│   └── Serialization: Custom serializers/deserializers
├── gRPC Integration:
│   ├── Define .proto files (Protocol Buffers)
│   ├── NestJS auto-generates types
│   ├── @GrpcMethod('ServiceName', 'MethodName')
│   └── High performance, Cross-language compatibility
└── Error Handling in Microservices:
    ├── RpcException: Microservice-specific exception
    └── ExceptionFilter: @Catch(RpcException) for microservice errors
```

---

## Module 6.4: Task Scheduling & Queues

### Section 6.4.1 — @nestjs/schedule
```
├── Installation: npm install @nestjs/schedule
├── Cron Jobs:
│   └── @Cron(CronExpression.EVERY_DAY_AT_MIDNIGHT)
│       handleCron() { this.logger.log('Running daily cleanup'); }
├── Intervals:
│   └── @Interval(30000) // Every 30 seconds
│       handleInterval() { this.logger.log('Heartbeat'); }
├── Timeouts:
│   └── @Timeout(5000) // Once after 5 seconds
│       handleTimeout() { this.logger.log('Delayed initialization'); }
├── Dynamic Scheduling:
│   ├── this.schedulerRegistry.addCronJob('name', job)
│   ├── this.schedulerRegistry.deleteCronJob('name')
│   └── this.schedulerRegistry.getCronJob('name').stop()
└── Use Cases: Cleanup jobs, Report generation, Cache warming, Health checks
```

### Section 6.4.2 — @nestjs/bull (BullMQ)
```
├── Installation: npm install @nestjs/bullmq bullmq
├── Queue Registration:
│   └── BullModule.forRoot({ connection: { host: 'localhost', port: 6379 } })
│   └── BullModule.registerQueue({ name: 'email' })
├── Producer:
│   └── constructor(@InjectQueue('email') private emailQueue: Queue) {}
│   └── await this.emailQueue.add('send-welcome', { userId: user.id, email: user.email })
├── Consumer (Processor):
│   └── @Processor('email')
│       export class EmailProcessor extends WorkerHost {
│         async process(job: Job<EmailJobData>) {
│           await this.mailService.send(job.data.email, 'Welcome!');
│         }
│       }
├── Job Options:
│   ├── delay: 5000 — Delay execution by 5 seconds
│   ├── attempts: 3 — Retry up to 3 times
│   ├── backoff: { type: 'exponential', delay: 1000 }
│   ├── removeOnComplete: true — Cleanup after success
│   ├── removeOnFail: false — Keep failed jobs for inspection
│   ├── priority: 1 — Higher priority = processed first
│   └── repeat: { cron: '0 0 * * *' } — Recurring job
├── Events:
│   ├── @OnQueueEvent(QueueEventsHost.COMPLETED)
│   ├── @OnQueueEvent(QueueEventsHost.FAILED)
│   └── @OnQueueEvent(QueueEventsHost.STALLED)
├── Bull Board: Visual dashboard for monitoring queues
│   └── npm install @bull-board/api @bull-board/express @bull-board/nestjs
└── Use Cases:
    ├── Email sending (don't block HTTP response)
    ├── Image/video processing
    ├── Report generation
    ├── Webhook delivery
    └── Data import/export
```

---

## Module 6.5: File Uploads

### Section 6.5.1 — Multer Integration
```
├── Single File:
│   └── @Post('upload')
│       @UseInterceptors(FileInterceptor('file'))
│       uploadFile(@UploadedFile() file: Express.Multer.File) { ... }
├── Multiple Files:
│   └── @UseInterceptors(FilesInterceptor('files', 10))
│       uploadFiles(@UploadedFiles() files: Express.Multer.File[]) { ... }
├── Validation (ParseFilePipe):
│   └── @UploadedFile(new ParseFilePipe({
│         validators: [
│           new MaxFileSizeValidator({ maxSize: 5 * 1024 * 1024 }), // 5MB
│           new FileTypeValidator({ fileType: /(jpg|jpeg|png|gif)$/ }),
│         ],
│       }))
│       file: Express.Multer.File
├── Storage Destinations:
│   ├── Memory (default): file.buffer — good for S3 upload
│   ├── Disk: MulterModule.register({ dest: './uploads' })
│   └── S3: Use aws-sdk to upload file.buffer to S3
├── S3 Upload Pattern:
│   └── this.s3.upload({ Bucket: 'my-bucket', Key: filename, Body: file.buffer })
│   └── Return: Presigned URL or CloudFront URL
└── Streaming Large Files:
    └── StreamableFile for downloads
    └── Multipart upload for large S3 uploads
```

---

## Module 6.6: API Versioning

### Section 6.6.1 — NestJS Versioning
```
├── Enable in main.ts:
│   └── app.enableVersioning({
│         type: VersioningType.URI,     // /v1/users, /v2/users
│         // type: VersioningType.HEADER,  // X-API-Version: 1
│         // type: VersioningType.MEDIA_TYPE, // Accept: application/json;v=1
│         defaultVersion: '1',
│       })
├── Controller-Level:
│   └── @Controller({ path: 'users', version: '2' })
├── Route-Level:
│   └── @Version('2')
│       @Get()
│       findAllV2() { ... }
├── Version-Neutral:
│   └── @Controller({ path: 'health', version: VERSION_NEUTRAL })
│       → Available on all versions
└── Best Practice: Support current + previous version (N-1)
```

---

> ### 🛠️ PHASE 6 PROJECT: **Real-Time Collaboration Platform**
> ```
> ┌─────────────────────────────────────────────────────────────────┐
> │            REAL-TIME COLLABORATION PLATFORM                     │
> ├─────────────────────────────────────────────────────────────────┤
> │                                                                 │
> │ Build on Phase 4/5 Project Management API and add:              │
> │                                                                 │
> │ 🔌 REAL-TIME:                                                   │
> │  ✅ WebSocket gateway for live task updates                      │
> │  ✅ Rooms: Per-project rooms, Users auto-join their projects     │
> │  ✅ Live notifications: Task assigned, Comment added             │
> │  ✅ Online presence: Show who's viewing a project                │
> │  ✅ SSE endpoint for activity feed                               │
> │  ✅ Redis adapter for multi-instance WebSocket scaling           │
> │                                                                 │
> │ 📊 GRAPHQL:                                                     │
> │  ✅ Code-first GraphQL API alongside REST                        │
> │  ✅ Queries: users, projects, tasks with nested relations        │
> │  ✅ Mutations: CRUD operations                                   │
> │  ✅ Subscriptions: Live task updates via GraphQL                  │
> │  ✅ DataLoader: Solve N+1 for nested queries                     │
> │  ✅ Complexity limiting: Prevent abusive queries                  │
> │                                                                 │
> │ 📬 BACKGROUND JOBS:                                             │
> │  ✅ BullMQ queues: Email notifications, Report generation        │
> │  ✅ Scheduled jobs: Daily digest email, Overdue task alerts       │
> │  ✅ Bull Board dashboard for queue monitoring                    │
> │                                                                 │
> │ 📁 FILES:                                                       │
> │  ✅ File attachments on tasks (upload to S3)                     │
> │  ✅ Avatar upload with image validation                          │
> │  ✅ Presigned URLs for secure downloads                          │
> │                                                                 │
> │ 🔄 API VERSIONING:                                              │
> │  ✅ v1 and v2 of users endpoint (URI versioning)                │
> │                                                                 │
> │ 🔗 MICROSERVICE (Bonus):                                        │
> │  ✅ Extract notification logic into separate microservice        │
> │  ✅ Communication via Redis transport                            │
> └─────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 🏆 PHASE 7: ENTERPRISE & PRODUCTION PATTERNS
### 📅 Duration: Weeks 23–30+
### 🎯 Goal: Build production-grade, enterprise-ready NestJS applications
### 👤 Level: NestJS Expert / Architect

---

## Module 7.1: Advanced Architecture Patterns

### Section 7.1.1 — CQRS & Event Sourcing in NestJS
```
├── @nestjs/cqrs:
│   ├── npm install @nestjs/cqrs
│   ├── Commands:
│   │   └── export class CreateUserCommand { constructor(public readonly dto: CreateUserDto) {} }
│   │   └── @CommandHandler(CreateUserCommand)
│   │       export class CreateUserHandler implements ICommandHandler<CreateUserCommand> {
│   │         async execute(command: CreateUserCommand) { ... }
│   │       }
│   ├── Queries:
│   │   └── export class GetUserQuery { constructor(public readonly id: string) {} }
│   │   └── @QueryHandler(GetUserQuery)
│   │       export class GetUserHandler implements IQueryHandler<GetUserQuery> {
│   │         async execute(query: GetUserQuery) { ... }
│   │       }
│   ├── Events:
│   │   └── export class UserCreatedEvent { constructor(public readonly user: User) {} }
│   │   └── @EventsHandler(UserCreatedEvent)
│   │       export class UserCreatedHandler implements IEventHandler<UserCreatedEvent> {
│   │         handle(event: UserCreatedEvent) { ... }
│   │       }
│   ├── Sagas:
│   │   └── @Injectable()
│   │       export class UsersSaga {
│   │         @Saga()
│   │         userCreated = (events$: Observable<any>) =>
│   │           events$.pipe(
│   │             ofType(UserCreatedEvent),
│   │             map(event => new SendWelcomeEmailCommand(event.user.email)),
│   │           );
│   │       }
│   └── Aggregate Roots:
│       └── export class User extends AggregateRoot {
│             createUser(...) {
│               this.apply(new UserCreatedEvent(this));
│             }
│           }
├── Event Sourcing Pattern:
│   ├── Store events instead of current state
│   ├── Event Store: Custom or EventStoreDB
│   ├── Projections: Build read models from events
│   └── NestJS Integration: Custom event store + CQRS module
└── When to use CQRS in NestJS:
    ├── Complex business domains
    ├── Different read/write optimization needs
    ├── Audit trail requirements
    └── Avoid for simple CRUD applications
```

### Section 7.1.2 — Hexagonal Architecture in NestJS
```
├── Structure:
│   └── src/
│       ├── modules/
│       │   └── users/
│       │       ├── domain/
│       │       │   ├── entities/          ← Domain entities (plain classes)
│       │       │   ├── value-objects/     ← Value objects
│       │       │   ├── ports/
│       │       │   │   ├── in/            ← Driving ports (use case interfaces)
│       │       │   │   └── out/           ← Driven ports (repository interfaces)
│       │       │   └── services/          ← Domain services
│       │       ├── application/
│       │       │   ├── use-cases/         ← Use case implementations
│       │       │   ├── dtos/              ← Input/Output DTOs
│       │       │   └── mappers/           ← Entity ↔ DTO mapping
│       │       └── infrastructure/
│       │           ├── adapters/
│       │           │   ├── in/
│       │           │   │   ├── rest/      ← REST controllers
│       │           │   │   └── graphql/   ← GraphQL resolvers
│       │           │   └── out/
│       │           │       ├── persistence/ ← TypeORM repositories
│       │           │       └── external/   ← External API clients
│       │           └── users.module.ts
├── Key Principle: Domain layer has ZERO NestJS imports
├── Dependency Rule: Infrastructure → Application → Domain (never reverse)
├── NestJS Role: Wiring framework (DI container for ports ↔ adapters)
└── Testing: Mock adapters, Test domain logic in isolation
```

### Section 7.1.3 — Modular Monolith with NestJS
```
├── Module Boundaries: Each module is a potential microservice
├── Inter-Module Communication:
│   ├── Shared interfaces (not implementations)
│   ├── Event-based: @nestjs/cqrs events across modules
│   └── Module API: Export ONLY what's needed
├── Database Isolation: Separate schemas per module
│   └── Each module has its own TypeORM/Prisma schema
│   └── No cross-module database queries!
├── Testing Module Boundaries:
│   └── ArchUnit-style tests to enforce dependency rules
│   └── Custom ESLint rules to prevent cross-boundary imports
└── Migration to Microservices: Extract module → separate service
```

---

## Module 7.2: Performance & Optimization

### Section 7.2.1 — NestJS Performance
```
├── Fastify Adapter: ~2x faster than Express
│   └── npm install @nestjs/platform-fastify
│   └── NestFactory.create<NestFastifyApplication>(AppModule, new FastifyAdapter())
├── Compression: app.use(compression()) — gzip/brotli responses
├── Lazy Loading Modules: Load on-demand, Not at startup
├── Response Caching: CacheInterceptor with Redis backend
├── Connection Pooling:
│   ├── TypeORM: extra: { max: 20 } — connection pool size
│   └── Prisma: connection_limit=20 in DATABASE_URL
├── Streaming Responses: StreamableFile for large downloads
├── Clustering: pm2 cluster mode or Node.js cluster module
│   └── Utilize all CPU cores
├── Memory Management:
│   ├── Avoid memory leaks: Unsubscribe Observables, Clear intervals
│   ├── Monitor: process.memoryUsage(), Heap snapshots
│   └── Garbage Collection: --expose-gc flag for forced GC in tests
├── Payload Size: Limit body size, Paginate large collections
└── Database Optimization:
    ├── Select only needed columns: select: { id: true, name: true }
    ├── Avoid eager loading: Load relations only when needed
    ├── Use QueryBuilder for complex queries (more control)
    └── Batch operations: Bulk insert/update instead of loops
```

---

## Module 7.3: Monitoring & Observability

### Section 7.3.1 — Production Observability
```
├── Health Checks (@nestjs/terminus):
│   ├── npm install @nestjs/terminus
│   ├── Checks: Database, Redis, Memory, Disk, HTTP dependency
│   └── @Controller('health')
│       export class HealthController {
│         @Get()
│         @HealthCheck()
│         check() {
│           return this.health.check([
│             () => this.db.pingCheck('database'),
│             () => this.memory.checkHeap('memory_heap', 200 * 1024 * 1024),
│             () => this.http.pingCheck('external-api', 'https://api.example.com'),
│           ]);
│         }
│       }
├── Prometheus Metrics:
│   ├── npm install @willsoto/nestjs-prometheus prom-client
│   ├── Auto-collect: HTTP request count, Duration, Status codes
│   ├── Custom metrics: Business metrics (orders placed, users registered)
│   └── Expose: /metrics endpoint → Scraped by Prometheus
├── OpenTelemetry:
│   ├── npm install @opentelemetry/sdk-node @opentelemetry/auto-instrumentations-node
│   ├── Auto-instrumentation: HTTP, Database, Redis, Kafka
│   ├── Custom spans: tracer.startSpan('custom-operation')
│   ├── Export to: Jaeger, Tempo, Datadog, New Relic
│   └── Correlation: Trace ID propagated through entire request chain
├── Structured Logging (Production):
│   ├── nestjs-pino: JSON logs with request context
│   ├── Fields: timestamp, level, message, correlationId, userId, method, url, duration
│   └── Ship to: ELK Stack, Loki, CloudWatch Logs, Datadog
├── Error Tracking:
│   ├── Sentry: @sentry/nestjs integration
│   │   ├── Auto-capture unhandled exceptions
│   │   ├── Breadcrumbs: Track user journey
│   │   └── Release tracking: Map errors to deployments
│   └── Custom: Global exception filter → send to error tracking service
└── APM (Application Performance Monitoring):
    ├── Datadog APM
    ├── New Relic
    └── Elastic APM
```

---

## Module 7.4: Deployment & DevOps

### Section 7.4.1 — Docker & Kubernetes
```
├── Dockerfile (Production-Ready):
│   └── # Build stage
│       FROM node:20-alpine AS build
│       WORKDIR /app
│       COPY package*.json ./
│       RUN npm ci
│       COPY . .
│       RUN npm run build
│       RUN npm prune --production
│
│       # Production stage
│       FROM node:20-alpine
│       WORKDIR /app
│       RUN addgroup -S appgroup && adduser -S appuser -G appgroup
│       COPY --from=build /app/dist ./dist
│       COPY --from=build /app/node_modules ./node_modules
│       COPY --from=build /app/package.json ./
│       USER appuser
│       EXPOSE 3000
│       HEALTHCHECK CMD wget -qO- http://localhost:3000/health || exit 1
│       CMD ["node", "dist/main.js"]
├── Docker Compose (Development):
│   └── services:
│         app:
│           build: .
│           ports: ["3000:3000"]
│           depends_on: [postgres, redis]
│           environment:
│             DATABASE_URL: postgres://user:pass@postgres:5432/db
│             REDIS_URL: redis://redis:6379
│         postgres:
│           image: postgres:16-alpine
│           volumes: [pgdata:/var/lib/postgresql/data]
│         redis:
│           image: redis:7-alpine
├── Kubernetes Deployment:
│   ├── Deployment: Replicas, Resource limits, Readiness/Liveness probes
│   ├── Service: ClusterIP for internal, LoadBalancer for external
│   ├── ConfigMap: Non-sensitive configuration
│   ├── Secret: Sensitive values (DB password, JWT secret)
│   ├── HPA: Auto-scale based on CPU/Memory/Custom metrics
│   ├── Readiness Probe: GET /health — 200 = ready
│   └── Liveness Probe: GET /health — 200 = alive
├── Graceful Shutdown:
│   ├── app.enableShutdownHooks()
│   ├── Kubernetes: terminationGracePeriodSeconds: 30
│   ├── Stop accepting new connections
│   ├── Wait for in-flight requests to complete
│   ├── Close database connections
│   └── Exit process
└── CI/CD:
    ├── GitHub Actions:
    │   └── Lint → Test → Build → Docker build → Push to ECR → Deploy to K8s
    ├── Migrations in CI: Run before deployment
    └── E2E Tests in CI: Against real database (Testcontainers)
```

---

## Module 7.5: NestJS Monorepo

### Section 7.5.1 — Monorepo Mode
```
├── Setup: nest g app service-name — or nest new --monorepo
├── Structure:
│   └── apps/
│       ├── api/          ← Main HTTP API
│       ├── worker/       ← Background job processor
│       └── notification/ ← Notification microservice
│   └── libs/
│       ├── common/       ← Shared DTOs, Interfaces, Constants
│       ├── database/     ← Shared database module
│       ├── auth/         ← Shared auth module
│       └── utils/        ← Shared utilities
├── Library Creation: nest g library common
├── Importing: import { SharedModule } from '@app/common'
├── Building: nest build api, nest build worker
├── nest-cli.json: Configure projects, Shared compiler options
├── Advantages:
│   ├── Shared code without publishing packages
│   ├── Atomic changes across services
│   ├── Unified CI/CD pipeline
│   └── Consistent dependencies
└── When to use:
    ├── Multiple NestJS services sharing code
    ├── Microservices that share DTOs/interfaces
    ├── API + Worker + Scheduler in one repo
    └── Alternative: Nx workspace (more powerful, More complex)
```

---

## Module 7.6: Advanced Testing Patterns

### Section 7.6.1 — Testing Strategy
```
├── Unit Tests:
│   ├── Every service, guard, pipe, interceptor
│   ├── Mock ALL external dependencies
│   ├── Test business logic in isolation
│   └── Fast: Milliseconds per test
├── Integration Tests:
│   ├── Real database (Testcontainers)
│   ├── Test repository + service together
│   ├── Test module wiring
│   └── Medium speed: Seconds per test
├── E2E Tests:
│   ├── Full application (app.init())
│   ├── Real database, Real Redis
│   ├── Test complete request flows
│   ├── Test authentication + authorization
│   ├── Test error handling
│   └── Slow: Seconds per test
├── Contract Tests:
│   ├── Pact: Consumer-driven contract testing
│   └── Verify API compatibility between services
├── Load Tests:
│   ├── k6: Script-based load testing
│   ├── Test against staging environment
│   └── Establish performance baselines
└── Coverage:
    ├── Unit: 80%+ coverage
    ├── Critical paths: 100% coverage (auth, payments)
    └── Don't chase 100% everywhere — focus on business logic
```

---

## Module 7.7: Event-Driven Patterns

### Section 7.7.1 — Event Emitter
```
├── @nestjs/event-emitter:
│   ├── npm install @nestjs/event-emitter
│   ├── EventEmitterModule.forRoot() in AppModule
│   ├── Emit: this.eventEmitter.emit('user.created', new UserCreatedEvent(user))
│   ├── Listen: @OnEvent('user.created') handleUserCreated(event: UserCreatedEvent) { ... }
│   ├── Async listeners: @OnEvent('user.created', { async: true })
│   ├── Wildcard: @OnEvent('user.*')
│   └── Use case: In-process event-driven architecture
├── Event-Driven Module Communication:
│   └── UsersModule emits 'user.created' → NotificationsModule listens
│   └── Loose coupling: Modules don't import each other
└── External Events:
    ├── Kafka/RabbitMQ: For cross-service events
    ├── Outbox Pattern: Write event to DB, CDC → Message broker
    └── Event Bridge: AWS EventBridge for cloud-native events
```

---

> ### 🛠️ PHASE 7 PROJECT: **Production SaaS Application**
> ```
> ┌─────────────────────────────────────────────────────────────────────────┐
> │              PRODUCTION-GRADE SAAS APPLICATION                          │
> ├─────────────────────────────────────────────────────────────────────────┤
> │                                                                         │
> │ Build a complete SaaS project management tool:                          │
> │                                                                         │
> │ 📁 MONOREPO STRUCTURE:                                                 │
> │  ├── apps/                                                              │
> │  │   ├── api/         ← Main REST + GraphQL API                        │
> │  │   ├── worker/      ← BullMQ job processor                           │
> │  │   └── gateway/     ← WebSocket gateway service                      │
> │  └── libs/                                                              │
> │      ├── common/      ← Shared DTOs, Interfaces                        │
> │      ├── database/    ← Prisma schema + PrismaService                  │
> │      └── auth/        ← Shared JWT strategy + Guards                   │
> │                                                                         │
> │ 🏗️ ARCHITECTURE:                                                       │
> │  ✅ Hexagonal Architecture in domain modules                           │
> │  ✅ CQRS for task management (commands + queries + events)              │
> │  ✅ Event-driven: @nestjs/event-emitter for module communication        │
> │  ✅ Modular monolith: Strict module boundaries, No cross-DB queries     │
> │                                                                         │
> │ 🔌 APIS:                                                               │
> │  ✅ REST API: Full CRUD, Pagination, Filtering, Versioned (v1/v2)       │
> │  ✅ GraphQL: Code-first, Subscriptions, DataLoader, Complexity limits   │
> │  ✅ WebSocket: Live task updates, Presence, Notifications               │
> │                                                                         │
> │ 🗄️ DATA:                                                               │
> │  ✅ PostgreSQL (Prisma): Primary database with migrations               │
> │  ✅ Redis: Caching, Sessions, BullMQ, WebSocket adapter                 │
> │  ✅ S3: File attachments with presigned URLs                            │
> │                                                                         │
> │ 🔒 SECURITY:                                                           │
> │  ✅ JWT + Refresh tokens with rotation                                  │
> │  ✅ Google OAuth2 with account linking                                  │
> │  ✅ RBAC + CASL permissions                                             │
> │  ✅ Rate limiting (Throttler)                                           │
> │  ✅ Helmet + CORS + Input sanitization                                  │
> │                                                                         │
> │ 📊 OBSERVABILITY:                                                      │
> │  ✅ Health checks: DB, Redis, Memory, External APIs                     │
> │  ✅ Prometheus metrics + Grafana dashboards                             │
> │  ✅ OpenTelemetry: Distributed tracing                                  │
> │  ✅ Structured logging (Pino) with correlation IDs                      │
> │  ✅ Sentry error tracking                                               │
> │                                                                         │
> │ 📬 BACKGROUND:                                                         │
> │  ✅ BullMQ: Email, Reports, Data export                                 │
> │  ✅ Scheduled jobs: Daily digest, Overdue alerts, Cleanup               │
> │  ✅ Bull Board dashboard                                                │
> │                                                                         │
> │ 🚀 DEPLOYMENT:                                                         │
> │  ✅ Multi-stage Dockerfile (< 200MB image)                              │
> │  ✅ Docker Compose for local development                                │
> │  ✅ Kubernetes manifests: Deployment, Service, HPA, Ingress             │
> │  ✅ Graceful shutdown with shutdown hooks                               │
> │  ✅ GitHub Actions: Lint → Test → Build → Deploy pipeline               │
> │  ✅ Database migrations in CI/CD                                        │
> │                                                                         │
> │ 🧪 TESTING:                                                            │
> │  ✅ Unit tests: 85%+ coverage on business logic                         │
> │  ✅ Integration tests: Testcontainers (PostgreSQL + Redis)              │
> │  ✅ E2E tests: All critical flows (auth, CRUD, WebSocket)               │
> │  ✅ Load test: k6 script proving 1K+ RPS at P99 < 100ms                │
> └─────────────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 📚 ESSENTIAL RESOURCES

```
┌──────────┬────────────────────────────────────────────────────────────────────┐
│ CATEGORY │  RESOURCE                                                         │
├──────────┼────────────────────────────────────────────────────────────────────┤
│ Official │  📖 NestJS Documentation: https://docs.nestjs.com                 │
│          │  📖 NestJS GitHub: https://github.com/nestjs/nest                 │
│          │  📖 NestJS Courses (Official): https://courses.nestjs.com         │
├──────────┼────────────────────────────────────────────────────────────────────┤
│ Books    │  📖 NestJS in Action — Manning Publications                       │
│          │  📖 Mastering NestJS — Packt (hands-on projects)                  │
├──────────┼────────────────────────────────────────────────────────────────────┤
│ Learning │  🎥 NestJS Official YouTube channel                               │
│          │  🎥 Fireship NestJS videos                                        │
│          │  💻 NestJS Fundamentals (official paid course — EXCELLENT)         │
├──────────┼────────────────────────────────────────────────────────────────────┤
│ Repos    │  📂 nestjs/nest — Framework source code (study it!)               │
│          │  📂 awesome-nestjs — Community curated resources                   │
│          │  📂 nestjs-realworld-example-app — Full example                    │
├──────────┼────────────────────────────────────────────────────────────────────┤
│ Pre-req  │  📖 TypeScript Handbook: https://www.typescriptlang.org/docs      │
│          │  📖 Node.js Design Patterns — Mario Casciaro                      │
│          │  📖 Effective TypeScript — Dan Vanderkam                          │
└──────────┴────────────────────────────────────────────────────────────────────┘
```

---

# 🧭 COMPLETE VISUAL MAP

```
╔═══════════════════════════════════════════════════════════════════════════════════╗
║                                                                                   ║
║  PHASE 7 ━━ ENTERPRISE & PRODUCTION ━━━━━━━━━━━━━━━━━━━ [Expert / Architect]     ║
║  ┃                                                                                ║
║  ┣━ 7.1 Advanced Patterns    (CQRS, Hexagonal, Modular Monolith, Event Sourcing)║
║  ┣━ 7.2 Performance          (Fastify, Caching, Clustering, DB Optimization)     ║
║  ┣━ 7.3 Observability        (Health, Prometheus, OpenTelemetry, Sentry)         ║
║  ┣━ 7.4 Deployment           (Docker, Kubernetes, CI/CD, Graceful Shutdown)      ║
║  ┣━ 7.5 Monorepo             (Multi-app, Shared libs, nx workspace)             ║
║  ┣━ 7.6 Advanced Testing     (Testcontainers, Contract, Load, Coverage)         ║
║  ┗━ 7.7 Event-Driven         (EventEmitter, Outbox, External events)            ║
║      ▲                                                                            ║
║  PHASE 6 ━━ REAL-TIME, GRAPHQL & ADVANCED ━━━━━━━━━━━━ [Advanced Developer]      ║
║  ┃                                                                                ║
║  ┣━ 6.1 WebSockets           (Gateway, Rooms, Broadcasting, Redis Adapter)       ║
║  ┣━ 6.2 GraphQL              (Code-first, Resolvers, Subscriptions, DataLoader)  ║
║  ┣━ 6.3 Microservices        (TCP, Redis, Kafka, gRPC, RabbitMQ, Hybrid)        ║
║  ┣━ 6.4 Scheduling & Queues  (Cron, BullMQ, Workers, Bull Board)               ║
║  ┣━ 6.5 File Uploads         (Multer, S3, Streaming, Validation)                ║
║  ┗━ 6.6 API Versioning       (URI, Header, Media Type versioning)               ║
║      ▲                                                                            ║
║  PHASE 5 ━━ SECURITY & AUTH ━━━━━━━━━━━━━━━━━━━━━━━━━━ [Mid-Senior Developer]    ║
║  ┃                                                                                ║
║  ┣━ 5.1 Passport.js          (Local, JWT, OAuth2, Token Management)              ║
║  ┣━ 5.2 Authorization        (RBAC, Permissions, CASL, Resource Ownership)       ║
║  ┣━ 5.3 Security Practices   (Helmet, CORS, Rate Limit, OWASP, XSS, CSRF)      ║
║  ┗━ 5.4 Social Login         (Google, GitHub, Apple OAuth2)                      ║
║      ▲                                                                            ║
║  PHASE 4 ━━ DATA LAYER & DATABASE ━━━━━━━━━━━━━━━━━━━━ [Mid-Level Developer]     ║
║  ┃                                                                                ║
║  ┣━ 4.1 TypeORM              (Entities, Relations, QueryBuilder, Migrations)     ║
║  ┣━ 4.2 Prisma               (Schema, Client, Migrations, Middleware)            ║
║  ┣━ 4.3 MikroORM             (UnitOfWork, Identity Map, DDD support)            ║
║  ┗━ 4.4 Data Patterns         (Pagination, Filtering, Caching, Seeding)          ║
║      ▲                                                                            ║
║  PHASE 3 ━━ CORE DEEP DIVE ━━━━━━━━━━━━━━━━━━━━━━━━━━━ [Junior+ Developer]      ║
║  ┃                                                                                ║
║  ┣━ 3.1 Request Lifecycle    (Full pipeline: MW → Guard → Int → Pipe → Handler)  ║
║  ┣━ 3.2 Configuration        (ConfigModule, Namespaces, Validation, Type-safe)   ║
║  ┣━ 3.3 Lifecycle Events     (OnModuleInit, Shutdown hooks, Graceful shutdown)    ║
║  ┣━ 3.4 Testing              (Unit tests, E2E tests, Mocking, Testcontainers)    ║
║  ┣━ 3.5 Logging              (Pino, Winston, Correlation IDs, Structured)        ║
║  ┗━ 3.6 Swagger              (OpenAPI, DTOs, Decorators, CLI Plugin)             ║
║      ▲                                                                            ║
║  PHASE 2 ━━ BUILDING BLOCKS ━━━━━━━━━━━━━━━━━━━━━━━━━━ [Beginner+]              ║
║  ┃                                                                                ║
║  ┣━ 2.1 CLI & Setup          (nest new, nest generate, main.ts bootstrap)        ║
║  ┣━ 2.2 Modules              (Feature, Shared, Dynamic, Global, Lazy)            ║
║  ┣━ 2.3 Controllers          (Routes, Params, Query, Body, Response handling)    ║
║  ┣━ 2.4 Providers & DI       (Injectable, Custom providers, Scopes, Tokens)      ║
║  ┣━ 2.5 Middleware            (Class, Functional, Global, Express compat)         ║
║  ┣━ 2.6 Exception Filters    (Built-in exceptions, Custom filters, @Catch())     ║
║  ┣━ 2.7 Pipes                (ValidationPipe, DTOs, class-validator, Custom)     ║
║  ┣━ 2.8 Guards               (CanActivate, ExecutionContext, Reflector, Roles)   ║
║  ┣━ 2.9 Interceptors         (Transform, Logging, Cache, Timeout, Serialization)║
║  ┗━ 2.10 Custom Decorators   (Param, Metadata, Composed, createParamDecorator)   ║
║      ▲                                                                            ║
║  PHASE 1 ━━ PREREQUISITES ━━━━━━━━━━━━━━━━━━━━━━━━━━━━ [Starting Point]         ║
║  ┃                                                                                ║
║  ┣━ 1.1 TypeScript            (Types, Generics, Utility Types, DECORATORS)       ║
║  ┣━ 1.2 Node.js               (Event Loop, Streams, Async, npm, Modules)        ║
║  ┗━ 1.3 Foundations           (OOP, HTTP/REST, Dependency Injection)             ║
║                                                                                   ║
╚═══════════════════════════════════════════════════════════════════════════════════╝

TOTAL: 7 Phases │ 34 Modules │ 80+ Sections │ 7 Milestone Projects
TIMELINE: ~30 weeks (7-8 months) — adjust based on experience
```

---

# ⚡ GOLDEN RULES FOR NESTJS MASTERY

```
┌─────┬────────────────────────────────────────────────────────────────────┐
│  #  │  RULE                                                             │
├─────┼────────────────────────────────────────────────────────────────────┤
│  1  │  Master TypeScript FIRST. NestJS is TypeScript-heavy.             │
│  2  │  Understand decorators deeply. NestJS IS decorators.              │
│  3  │  Build the Phase 1 project WITHOUT NestJS. Then appreciate it.    │
│  4  │  Read the NestJS source code. It's surprisingly readable.         │
│  5  │  Use the CLI. Don't manually create files. nest g resource.       │
│  6  │  Global ValidationPipe from day 1. NEVER skip validation.         │
│  7  │  Prefer composition: Composed decorators > Repeating decorators.  │
│  8  │  Test everything. NestJS testing utilities are excellent — use them│
│  9  │  Don't over-engineer. Start monolith, Extract microservices later.│
│ 10  │  Follow the NestJS Discord community. It's incredibly helpful.    │
└─────┴────────────────────────────────────────────────────────────────────┘
```