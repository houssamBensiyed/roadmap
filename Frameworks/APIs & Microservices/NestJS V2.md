# 🐈 THE ULTIMATE NESTJS ROADMAP
### From Zero to Production-Grade NestJS Mastery

> **Structure:** Phase → Modules → Sections
> **Estimated Duration:** ~6-9 Months (Dedicated Study)
> **Prerequisites:** JavaScript (ES6+), basic TypeScript, basic HTTP/REST, basic Node.js
> *NestJS is the Angular of the backend — opinionated, structured, and enterprise-ready. It brings order to the chaos of Node.js server-side development.*

---

## ⚡ PHASE 0 — PREREQUISITES & NESTJS ORIENTATION
> *"NestJS doesn't just use TypeScript. It embraces decorators, metadata, and dependency injection to create a framework that feels like building with LEGO — structured, predictable, and scalable."*

---

### 📦 Module 0.1: Understanding NestJS

#### § 0.1.1 — What is NestJS & Why It Exists
  - Created by Kamil Myśliwiec (2017), maintained by the NestJS team
  - A progressive Node.js framework for building efficient, reliable, and scalable server-side applications
  - Built with and fully supports TypeScript (also supports JavaScript)
  - Heavily inspired by Angular: decorators, modules, dependency injection, providers
  - Under the hood: runs on Express.js (default) or Fastify (alternative)
  - Provides a true application architecture: modules, controllers, services, guards, interceptors, pipes, filters

#### § 0.1.2 — The Problems NestJS Solves
  - **Express.js**: no opinions, no structure, no DI, no standards — great for small projects, chaos for large ones
  - **Architecture**: NestJS enforces modular, testable, maintainable architecture
  - **TypeScript-first**: full decorator support, dependency injection, metadata reflection
  - **Enterprise patterns**: built-in support for microservices, WebSockets, GraphQL, CQRS, event sourcing
  - **Testing**: designed for testability from day one (DI makes mocking trivial)
  - **Ecosystem**: first-party modules for database, auth, queues, caching, scheduling, and more

#### § 0.1.3 — Where NestJS Dominates
  - Enterprise backend applications
  - REST and GraphQL APIs
  - Microservices architectures
  - Real-time applications (WebSocket/Socket.io)
  - Serverless functions
  - CLI applications
  - Who uses it: Adidas, Roche, Capgemini, Autodesk, Decathlon, many enterprise teams

#### § 0.1.4 — NestJS vs Alternatives
  - NestJS vs Express: NestJS adds structure, DI, decorators, modules — Express is barebone
  - NestJS vs Fastify (standalone): NestJS can USE Fastify as its HTTP engine
  - NestJS vs Koa/Hapi: NestJS is a full framework, Koa/Hapi are middleware frameworks
  - NestJS vs Spring Boot: similar architecture and patterns, Node.js vs Java ecosystems
  - NestJS vs ASP.NET Core: similar DI and pattern approach, TypeScript vs C#
  - NestJS vs FastAPI: similar decorator approach, TypeScript/Node.js vs Python ecosystems
  - NestJS vs Next.js: NestJS is backend-only, Next.js is full-stack React

#### § 0.1.5 — NestJS Architecture Overview
  - **Modules** — organize the application into cohesive blocks of functionality
  - **Controllers** — handle incoming HTTP requests and return responses
  - **Providers / Services** — business logic, injected via DI
  - **Middleware** — runs before route handlers (Express/Fastify middleware)
  - **Guards** — authorization logic (should this request proceed?)
  - **Interceptors** — transform result/exception, add extra logic (AOP-style)
  - **Pipes** — validation and transformation of input data
  - **Filters** — exception handling (catch and format errors)
  - **Request lifecycle**: Middleware → Guards → Interceptors (before) → Pipes → Controller → Interceptors (after) → Filters (on error)

---

### 📦 Module 0.2: TypeScript Prerequisites

#### § 0.2.1 — Essential TypeScript for NestJS
  - Types: `string`, `number`, `boolean`, `any`, `unknown`, `void`, `never`
  - Interfaces: `interface User { name: string; age: number; }`
  - Types vs interfaces: prefer interfaces for object shapes, types for unions/utility
  - Generics: `Array<T>`, `Promise<T>`, custom generics
  - Enums: `enum Role { Admin, User, Moderator }`
  - Union and intersection types: `string | number`, `A & B`
  - Utility types: `Partial<T>`, `Required<T>`, `Pick<T, K>`, `Omit<T, K>`, `Record<K, V>`
  - Type narrowing and type guards

#### § 0.2.2 — Critical TypeScript for NestJS
  - **Decorators**: `@Controller()`, `@Injectable()`, `@Module()` — metadata annotations on classes/methods
  - **Decorator factories**: decorators that accept parameters
  - **Metadata reflection**: `reflect-metadata` — how NestJS reads decorator info at runtime
  - **Abstract classes**: base classes for shared behavior
  - **Access modifiers**: `public`, `private`, `protected`, `readonly`
  - **Constructor parameter properties**: `constructor(private readonly service: UserService)` — declares AND assigns
  - **Index signatures**: `{ [key: string]: any }`

#### § 0.2.3 — Node.js Prerequisites
  - `npm` / `yarn` / `pnpm` — package management
  - `package.json` — project configuration, scripts, dependencies
  - Event loop: single-threaded, non-blocking I/O model
  - `async/await` and Promises in Node.js context
  - CommonJS (`require`) vs ES Modules (`import`) — NestJS uses ES-style imports compiled by TypeScript
  - Environment variables: `process.env`
  - Basic Express.js understanding (helpful but not required)

---

### 📦 Module 0.3: Setting Up the Development Environment

#### § 0.3.1 — Installing Prerequisites
  - Node.js 18+ (LTS recommended): `node --version`
  - npm / pnpm: `pnpm` recommended for speed and disk efficiency
  - NestJS CLI: `npm i -g @nestjs/cli`
  - Verify: `nest --version`

#### § 0.3.2 — IDE Selection
  - **VS Code** — the standard for Node.js/TypeScript (extensions: ESLint, Prettier, NestJS snippets)
  - **WebStorm** (JetBrains) — powerful, best TypeScript experience, NestJS-aware
  - Essential VS Code extensions: ESLint, Prettier, NestJS Files, Prisma, REST Client

#### § 0.3.3 — Creating a NestJS Project
  - `nest new project-name` — scaffold a new project
  - Prompts: package manager selection (npm/yarn/pnpm)
  - Project structure walkthrough: `src/`, `test/`, `nest-cli.json`, `tsconfig.json`
  - `npm run start:dev` — start with hot-reload (file watching)
  - Default files: `app.module.ts`, `app.controller.ts`, `app.service.ts`, `main.ts`

#### § 0.3.4 — NestJS CLI Commands
  - `nest generate module users` / `nest g mo users` — generate a module
  - `nest generate controller users` / `nest g co users` — generate a controller
  - `nest generate service users` / `nest g s users` — generate a service
  - `nest generate resource users` — generate full CRUD resource (module, controller, service, DTOs)
  - `nest g guard auth` — generate a guard
  - `nest g interceptor logging` — generate an interceptor
  - `nest g pipe validation` — generate a pipe
  - `nest g filter http-exception` — generate an exception filter
  - `nest build` — compile TypeScript to JavaScript

#### § 0.3.5 — Essential Configuration
  - `nest-cli.json` — CLI configuration, project structure
  - `tsconfig.json` — TypeScript compiler options (strict mode, decorators)
  - `tsconfig.build.json` — build-specific TypeScript config
  - `.eslintrc.js` — linting rules
  - `.prettierrc` — code formatting

> ### 🛠️ Phase 0 Project: **"Hello NestJS"**
> Create your first NestJS application:
> - Scaffold with `nest new hello-nest`
> - Explore every file: `main.ts`, `app.module.ts`, `app.controller.ts`, `app.service.ts`
> - Add a new endpoint that returns system info (Node version, platform, uptime)
> - Generate a new module, controller, and service using the CLI
> - Understand the relationship: Module registers Controller, Controller injects Service
> - Test with Swagger (install `@nestjs/swagger`), curl, and Postman
> - Run in dev mode, make a change, observe hot-reload
> - Explore the compiled JavaScript output in `dist/`

---

## ⚡ PHASE 1 — NESTJS CORE CONCEPTS
> *"Modules, Controllers, Providers — the holy trinity of NestJS. Everything else builds on these three."*

---

### 📦 Module 1.1: Modules

#### § 1.1.1 — Module Fundamentals
  - `@Module()` decorator — defines a module
  - Every NestJS app has at least one module: `AppModule` (the root)
  - Properties: `imports`, `controllers`, `providers`, `exports`
  - `imports` — other modules this module depends on
  - `controllers` — controllers that belong to this module
  - `providers` — services/providers to instantiate and share within this module
  - `exports` — providers to make available to other modules that import this one

#### § 1.1.2 — Module Organization
  - Feature modules: one module per domain feature (UsersModule, OrdersModule, AuthModule)
  - Shared modules: common utilities exported for reuse (DatabaseModule, LoggingModule)
  - Core module: singleton services used app-wide (ConfigModule, LoggerModule)
  - `@Global()` — makes a module globally available (use sparingly)

#### § 1.1.3 — Dynamic Modules
  - Modules that accept configuration parameters
  - `forRoot()` — configure once at the app level (singleton)
  - `forRootAsync()` — async configuration (load from config service)
  - `forFeature()` — configure per feature module
  - Use case: database module with connection string, cache module with TTL

---

### 📦 Module 1.2: Controllers

#### § 1.2.1 — Controller Fundamentals
  - `@Controller('users')` — defines a controller with route prefix `/users`
  - Route decorators: `@Get()`, `@Post()`, `@Put()`, `@Patch()`, `@Delete()`
  - Route parameters: `@Get(':id')` → `@Param('id') id: string`
  - Return values: objects auto-serialized to JSON, Observables, Promises

#### § 1.2.2 — Request Data Extraction
  - `@Param('id')` — route parameter: `/users/:id`
  - `@Query('page')` — query parameter: `?page=1`
  - `@Body()` — entire request body
  - `@Body('name')` — specific field from body
  - `@Headers('authorization')` — request header
  - `@Ip()` — client IP address
  - `@Req()` — raw Express/Fastify request (avoid — platform-dependent)
  - `@Res()` — raw response (avoid — bypasses NestJS response handling)

#### § 1.2.3 — Response Handling
  - Return value is auto-serialized to JSON (200 for GET, 201 for POST)
  - `@HttpCode(204)` — custom status code
  - `@Header('Cache-Control', 'no-cache')` — set response header
  - `@Redirect('https://example.com', 301)` — redirect
  - Return `HttpException` subclasses or throw them for error responses

#### § 1.2.4 — Route Wildcards & Versioning
  - Wildcard: `@Get('ab*cd')` — matches `abcd`, `abXcd`, `abXXcd`, etc.
  - Sub-routing: `@Controller('users')` → `@Get('profile')` → `/users/profile`
  - API versioning: URI (`/v1/users`), Header, Media Type, Custom
  - `@Version('1')` — mark controller or method for specific version

---

### 📦 Module 1.3: Providers & Dependency Injection

#### § 1.3.1 — Provider Fundamentals
  - Any class decorated with `@Injectable()` can be a provider
  - Providers are the NestJS term for services, repositories, factories, helpers
  - Registered in the `providers` array of a module
  - Injected via constructor: `constructor(private readonly usersService: UsersService)`
  - NestJS creates and manages the lifecycle

#### § 1.3.2 — Injection Scopes
  - **DEFAULT (Singleton)**: one instance shared across the entire app (most common)
  - **REQUEST**: new instance per incoming request
  - **TRANSIENT**: new instance per injection (each consumer gets a new one)
  - `@Injectable({ scope: Scope.REQUEST })` — set scope
  - Scope bubbling: if a provider is REQUEST-scoped, everything that depends on it becomes REQUEST-scoped
  - Singleton is the default and preferred — avoids performance overhead of per-request instantiation

#### § 1.3.3 — Custom Providers
  - **Value providers**: `{ provide: 'CONFIG', useValue: configObject }`
  - **Class providers**: `{ provide: IUserService, useClass: UserServiceImpl }`
  - **Factory providers**: `{ provide: 'DATABASE', useFactory: (config) => createConnection(config), inject: [ConfigService] }`
  - **Existing providers**: `{ provide: 'AliasService', useExisting: RealService }`
  - Injection tokens: strings or Symbols for non-class providers → `@Inject('CONFIG')`

#### § 1.3.4 — Circular Dependencies
  - Module A imports Module B, Module B imports Module A — circular!
  - `forwardRef(() => ModuleA)` — resolve circular module dependencies
  - `@Inject(forwardRef(() => ServiceA))` — resolve circular service dependencies
  - Best practice: refactor to eliminate circularity (extract shared module)

---

### 📦 Module 1.4: Configuration

#### § 1.4.1 — ConfigModule
  - `@nestjs/config` — built-in configuration module
  - `ConfigModule.forRoot({ isGlobal: true })` — load `.env` files
  - `ConfigService.get<string>('DATABASE_URL')` — read values
  - `.env` files: `.env`, `.env.development`, `.env.production`, `.env.test`
  - Validation: Joi or class-validator schema for environment variables
  - `envFilePath` — custom `.env` file location
  - `expandVariables: true` — support variable references in `.env`

#### § 1.4.2 — Custom Configuration Files
  - `load: [() => ({ database: { host: process.env.DB_HOST } })]` — custom config factories
  - Namespaced configuration: `registerAs('database', () => ({ host, port }))`
  - `ConfigService.get('database.host')` — access namespaced values
  - Type-safe configuration with interfaces

#### § 1.4.3 — Configuration Validation
  - Joi schema: validate all environment variables at startup
  - Fail fast: app won't start with invalid configuration
  - Default values: provide sensible defaults
  - Required vs optional: enforce critical config presence

---

### 📦 Module 1.5: Exception Handling

#### § 1.5.1 — Built-in Exceptions
  - `HttpException` — base exception class
  - `BadRequestException` (400), `UnauthorizedException` (401), `ForbiddenException` (403)
  - `NotFoundException` (404), `ConflictException` (409), `UnprocessableEntityException` (422)
  - `InternalServerErrorException` (500), `NotImplementedException` (501)
  - All accept: `message` (string or object) and optional `description`

#### § 1.5.2 — Custom Exceptions
  - Extend `HttpException` for domain-specific exceptions
  - Custom exception classes: `UserNotFoundException`, `DuplicateEmailException`
  - Include: error code, message, additional details

#### § 1.5.3 — Exception Filters
  - `@Catch()` decorator — catch specific exception types
  - `ExceptionFilter` interface — implement `catch(exception, host)` method
  - `ArgumentsHost` — access request/response objects
  - Global filter: `app.useGlobalFilters(new AllExceptionsFilter())`
  - Controller/method level: `@UseFilters(HttpExceptionFilter)`
  - Module-level: `APP_FILTER` provider token
  - Consistent error response format across the entire API

> ### 🛠️ Phase 1 Project: **"BookshelfAPI — Core Architecture"**
> Build a bookshelf management API demonstrating core concepts:
> - **Modules**: `BooksModule`, `AuthorsModule`, `CategoriesModule`, `SharedModule`
> - **Controllers**: CRUD endpoints for books, authors, categories
> - **Services**: `BooksService`, `AuthorsService` with in-memory storage
> - **Dependency injection**: services injected into controllers, services injecting other services
> - **Custom providers**: configuration value provider, logger factory provider
> - **Configuration**: `ConfigModule` with `.env` validation via Joi
> - **Exception handling**: custom `BookNotFoundException`, global exception filter with consistent error format
> - **Route parameters**: `GET /books/:id`, `GET /books?genre=fiction&page=1`
> - **Response codes**: 200, 201, 204, 400, 404, 409 used appropriately
> - **Swagger**: `@nestjs/swagger` with decorated DTOs and endpoint descriptions
> - **CLI generated**: all resources generated with `nest g resource`

---

## ⚡ PHASE 2 — VALIDATION, PIPES & SERIALIZATION
> *"Never trust client input. NestJS pipes make validation declarative, automatic, and type-safe."*

---

### 📦 Module 2.1: Pipes

#### § 2.1.1 — Pipe Fundamentals
  - Transform input data or validate it before it reaches the handler
  - Execute AFTER middleware and guards, BEFORE the controller method
  - Built-in pipes: `ValidationPipe`, `ParseIntPipe`, `ParseBoolPipe`, `ParseArrayPipe`, `ParseUUIDPipe`, `ParseEnumPipe`, `DefaultValuePipe`, `ParseFilePipe`
  - `ParseIntPipe`: `@Param('id', ParseIntPipe) id: number` — auto-converts string to int, throws 400 if invalid

#### § 2.1.2 — ValidationPipe (The Most Important Pipe)
  - `class-validator` + `class-transformer` — DTO-based validation
  - `app.useGlobalPipes(new ValidationPipe())` — enable globally
  - Options:
    - `whitelist: true` — strip unknown properties (security!)
    - `forbidNonWhitelisted: true` — throw error on unknown properties
    - `transform: true` — auto-transform payloads to DTO class instances
    - `transformOptions: { enableImplicitConversion: true }` — auto-convert types
    - `errorHttpStatusCode: HttpStatus.UNPROCESSABLE_ENTITY` — custom error status

#### § 2.1.3 — Custom Pipes
  - Implement `PipeTransform<T, R>` interface
  - `transform(value: T, metadata: ArgumentMetadata): R`
  - Use case: custom parsing, normalization, business-rule validation
  - Can be sync or async (return `Promise<R>`)

---

### 📦 Module 2.2: DTOs & Validation

#### § 2.2.1 — DTO Pattern in NestJS
  - DTO (Data Transfer Object) — defines the shape of request/response data
  - Classes (NOT interfaces) — required for runtime validation with `class-validator`
  - `CreateBookDto`, `UpdateBookDto`, `BookResponseDto`
  - One DTO per operation (create, update, response, query)

#### § 2.2.2 — class-validator Decorators
  - **String**: `@IsString()`, `@IsNotEmpty()`, `@MinLength()`, `@MaxLength()`, `@IsEmail()`, `@IsUrl()`, `@Matches(regex)`
  - **Number**: `@IsNumber()`, `@IsInt()`, `@Min()`, `@Max()`, `@IsPositive()`
  - **Boolean**: `@IsBoolean()`
  - **Date**: `@IsDate()`, `@IsDateString()`, `@IsISO8601()`
  - **Array**: `@IsArray()`, `@ArrayMinSize()`, `@ArrayMaxSize()`, `@ArrayUnique()`
  - **Enum**: `@IsEnum(Status)`
  - **Nested**: `@ValidateNested()` + `@Type(() => NestedDto)` — validate nested objects
  - **Optional**: `@IsOptional()` — field is not required
  - **Conditional**: `@ValidateIf(o => o.type === 'premium')` — conditional validation
  - **Custom**: `@Validate(CustomConstraint)` — custom validation logic
  - `message` parameter: custom error messages per decorator

#### § 2.2.3 — `PartialType` & `PickType` (Mapped Types)
  - `@nestjs/mapped-types` — utilities for creating derived DTOs
  - `PartialType(CreateBookDto)` — all fields become optional (for PATCH/PUT)
  - `PickType(CreateBookDto, ['title', 'author'])` — pick specific fields
  - `OmitType(CreateBookDto, ['password'])` — exclude fields
  - `IntersectionType(CreateBookDto, AdditionalData)` — combine DTOs
  - Avoid duplicating DTO definitions — derive from base DTOs

#### § 2.2.4 — Custom Validation
  - Custom decorator: `@IsStrongPassword()` — create reusable validators
  - `ValidatorConstraint` + `ValidatorConstraintInterface` — custom validation logic
  - `registerDecorator()` — register custom decorator
  - Cross-field validation: validate one field based on another's value

---

### 📦 Module 2.3: Serialization & Transformation

#### § 2.3.1 — class-transformer
  - `@Exclude()` — exclude field from response (e.g., password)
  - `@Expose()` — explicitly include field
  - `@Transform()` — transform field value during serialization
  - `@Type(() => Date)` — specify type for proper transformation
  - `plainToInstance()`, `instanceToPlain()` — manual transformation

#### § 2.3.2 — Serialization Interceptor
  - `ClassSerializerInterceptor` — auto-apply serialization rules
  - `app.useGlobalInterceptors(new ClassSerializerInterceptor(reflector))` — global
  - `@SerializeOptions({ excludeExtraneousValues: true })` — per controller/method
  - Controls what gets sent back to the client — security critical

#### § 2.3.3 — Response Wrapping
  - Consistent response format: `{ data, meta, timestamp }`
  - Custom interceptor for response wrapping
  - Pagination response: `{ data: items, meta: { total, page, limit, totalPages } }`
  - Error response format: `{ statusCode, message, error, timestamp, path }`

---

### 📦 Module 2.4: Swagger / OpenAPI Integration

#### § 2.4.1 — Setting Up Swagger
  - `@nestjs/swagger` — first-party OpenAPI integration
  - `SwaggerModule.setup('api', app, document)` — mount Swagger UI
  - `DocumentBuilder` — configure API title, description, version, auth schemes
  - Auto-generates documentation from controllers, DTOs, and decorators

#### § 2.4.2 — Decorating DTOs for Swagger
  - `@ApiProperty({ description, example, required, enum, type })` — document DTO fields
  - `@ApiPropertyOptional()` — optional field documentation
  - `@ApiHideProperty()` — hide field from docs
  - `@ApiTags('Users')` — group endpoints
  - `@ApiOperation({ summary, description })` — endpoint documentation
  - `@ApiResponse({ status, description, type })` — response documentation
  - `@ApiParam()`, `@ApiQuery()`, `@ApiHeader()` — parameter documentation
  - `@ApiBearerAuth()` — mark endpoint as requiring JWT

#### § 2.4.3 — Swagger Plugin (Auto-Documentation)
  - `nest-cli.json` — enable Swagger plugin
  - Auto-infers `@ApiProperty` from TypeScript types and class-validator decorators
  - Reduces manual decoration significantly
  - Prefix DTOs with DTO naming convention for auto-detection

> ### 🛠️ Phase 2 Project: **"BookshelfAPI v2 — Validated & Documented"**
> Add comprehensive validation and documentation:
> - **DTOs**: `CreateBookDto`, `UpdateBookDto` (PartialType), `BookResponseDto`, `BookQueryDto`
> - **Validation**: every field validated with `class-validator`
>   - Custom validators: `@IsISBN()` for ISBN format, `@IsPublicationYear()` for valid year
>   - Nested validation: author info within book creation
>   - Query validation: `BookQueryDto` for pagination, filter, sort parameters
> - **ValidationPipe**: global with `whitelist`, `forbidNonWhitelisted`, `transform`
> - **ParseIntPipe**: on all ID route parameters
> - **ParseEnumPipe**: on status/genre query parameters
> - **Serialization**: `@Exclude()` on sensitive fields, `ClassSerializerInterceptor`
> - **Response wrapping**: custom interceptor for consistent `{ data, meta }` format
> - **Swagger**: full API documentation
>   - Every endpoint documented with `@ApiOperation`, `@ApiResponse`
>   - Every DTO field documented with `@ApiProperty` and examples
>   - Request/response examples
>   - Authentication scheme documented
>   - Swagger plugin enabled for auto-documentation
> - Test validation: verify 400/422 responses with invalid data

---

## ⚡ PHASE 3 — DATABASE INTEGRATION
> *"NestJS is database-agnostic. But its TypeORM and Prisma integrations are first-class citizens."*

---

### 📦 Module 3.1: TypeORM Integration

#### § 3.1.1 — TypeORM Setup
  - `@nestjs/typeorm` — official TypeORM integration
  - `TypeOrmModule.forRoot({ type: 'postgres', ... })` — configure connection
  - `TypeOrmModule.forRootAsync({ useFactory, inject })` — async config from ConfigService
  - `TypeOrmModule.forFeature([User, Book])` — register entities per module
  - `@Entity()`, `@Column()`, `@PrimaryGeneratedColumn()` — entity decorators

#### § 3.1.2 — Entity Definition
  - `@Entity('users')` — table name
  - `@PrimaryGeneratedColumn('uuid')` — UUID primary key
  - `@Column({ type: 'varchar', length: 255, nullable: false, unique: true })` — column config
  - `@CreateDateColumn()`, `@UpdateDateColumn()`, `@DeleteDateColumn()` — auto-managed timestamps
  - `@Column({ type: 'enum', enum: Status, default: Status.Active })` — enum columns
  - `@Index()` — database index

#### § 3.1.3 — Relationships
  - `@OneToMany(() => Book, book => book.author)` — one-to-many
  - `@ManyToOne(() => Author, author => author.books)` — many-to-one
  - `@ManyToMany(() => Tag, tag => tag.books)` + `@JoinTable()` — many-to-many
  - `@OneToOne(() => Profile)` + `@JoinColumn()` — one-to-one
  - Eager vs lazy loading: `{ eager: true }` or query-time `relations`
  - Cascade: `{ cascade: true }` — propagate operations to related entities

#### § 3.1.4 — Repository Pattern with TypeORM
  - `@InjectRepository(User) private userRepo: Repository<User>` — inject repository
  - `repo.find()`, `repo.findOne()`, `repo.findOneBy()`, `repo.save()`, `repo.remove()`
  - `repo.create(dto)` — create entity instance (doesn't save!)
  - QueryBuilder: `repo.createQueryBuilder('user').where(...).leftJoinAndSelect(...)`
  - Custom repositories: extend `Repository<T>` with domain-specific methods
  - `repo.findAndCount()` — for pagination (returns `[items, total]`)

#### § 3.1.5 — Transactions
  - `QueryRunner` — manual transaction management
  - `DataSource.transaction(manager => { ... })` — callback-based transaction
  - Transaction decorators with custom interceptors
  - `@TransactionManager()` — inject transaction entity manager

---

### 📦 Module 3.2: Prisma Integration

#### § 3.2.1 — Prisma Setup
  - `prisma init` — create schema and `.env`
  - `schema.prisma` — define models, relations, enums
  - `prisma migrate dev` — create and apply migrations
  - `prisma generate` — generate type-safe Prisma Client
  - `PrismaService extends PrismaClient` — wrap as NestJS injectable service
  - Register `PrismaService` as a provider (often global)

#### § 3.2.2 — Prisma CRUD Operations
  - `prisma.user.findMany()`, `findUnique()`, `findFirst()`
  - `prisma.user.create({ data })`, `createMany()`
  - `prisma.user.update({ where, data })`, `updateMany()`
  - `prisma.user.delete({ where })`, `deleteMany()`
  - `prisma.user.upsert({ where, create, update })` — create or update
  - Relations: `include: { books: true }` — eager load
  - Select: `select: { id: true, name: true }` — field selection
  - Pagination: `skip`, `take`, `cursor` (cursor-based pagination)

#### § 3.2.3 — Prisma Advanced
  - Transactions: `prisma.$transaction([...])` or interactive transactions
  - Raw queries: `prisma.$queryRaw`, `prisma.$executeRaw`
  - Middleware: `prisma.$use()` — intercept queries (soft delete, audit logging)
  - Connection management: `$connect()`, `$disconnect()` in lifespan hooks

---

### 📦 Module 3.3: Drizzle ORM Integration

#### § 3.3.1 — Drizzle as an Alternative
  - SQL-like, type-safe, lightweight ORM
  - Schema defined in TypeScript
  - Better for developers who prefer SQL
  - Edge-compatible, no code generation step
  - Growing rapidly in the NestJS ecosystem

---

### 📦 Module 3.4: Database Migrations

#### § 3.4.1 — TypeORM Migrations
  - `typeorm migration:generate` — auto-generate from entity changes
  - `typeorm migration:run` — apply migrations
  - `typeorm migration:revert` — rollback last migration
  - `synchronize: true` — auto-sync in development ONLY (NEVER production)

#### § 3.4.2 — Prisma Migrations
  - `prisma migrate dev` — development migrations
  - `prisma migrate deploy` — production migrations
  - `prisma migrate reset` — reset database (development only)
  - Migration files: SQL-based, version controlled

---

### 📦 Module 3.5: Service Layer Pattern

#### § 3.5.1 — Service Architecture
  - Controller → Service → Repository/Prisma — layered architecture
  - Controller: HTTP concerns only (request/response, status codes)
  - Service: business logic, validation, orchestration
  - Repository/ORM: data access only
  - DTOs for input, entities for persistence, response DTOs for output

> ### 🛠️ Phase 3 Project: **"BookshelfAPI v3 — Database-Backed"**
> Add persistent storage:
> - **Database**: PostgreSQL via Docker
> - **ORM**: TypeORM OR Prisma (implement one, understand the other)
> - **Entities/Models**: `Book`, `Author`, `Category`, `Tag`, `Review` with relationships
>   - Author → Book: One-to-Many
>   - Book ↔ Tag: Many-to-Many
>   - Book → Review: One-to-Many
>   - Book → Category: Many-to-One
> - **Migrations**: minimum 5 migration files
> - **Service layer**: clean separation (Controller → Service → Repository/Prisma)
> - **Querying**: pagination, filtering, sorting, search, eager loading
> - **Transactions**: multi-step operations in transactions
> - **Soft delete**: `@DeleteDateColumn` or Prisma middleware
> - **Seeding**: seed script for categories, sample books, test authors
> - Auto-managed `createdAt`, `updatedAt` timestamps

---

## ⚡ PHASE 4 — AUTHENTICATION & AUTHORIZATION
> *"NestJS Guards + Passport.js + JWT = enterprise-grade security with minimal boilerplate."*

---

### 📦 Module 4.1: Passport.js Integration

#### § 4.1.1 — Passport.js Setup
  - `@nestjs/passport` — NestJS Passport integration
  - `@nestjs/jwt` — JWT utilities
  - Strategies: `passport-local` (username/password), `passport-jwt` (JWT validation)
  - `PassportModule.register({ defaultStrategy: 'jwt' })` — configure

#### § 4.1.2 — Local Strategy (Login)
  - `passport-local` — validates username/password
  - `LocalStrategy extends PassportStrategy(Strategy)` — implement `validate()` method
  - `@UseGuards(AuthGuard('local'))` — apply on login endpoint
  - `validate(username, password)` — called by Passport, return user or throw

#### § 4.1.3 — JWT Strategy (Token Validation)
  - `passport-jwt` — validates JWT on protected endpoints
  - `JwtStrategy extends PassportStrategy(Strategy)` — implement `validate()` method
  - Extract token from: `Authorization: Bearer <token>` header
  - `validate(payload)` — decode payload, return user object (attached to `request.user`)
  - `@UseGuards(AuthGuard('jwt'))` — protect endpoints

---

### 📦 Module 4.2: JWT Authentication Flow

#### § 4.2.1 — Token Management
  - `JwtService.signAsync(payload, options)` — generate token
  - Access token: short-lived (15-30 minutes)
  - Refresh token: long-lived (7-30 days), stored in database
  - Token payload: `sub` (user ID), `email`, `roles`, `iat`, `exp`
  - Token refresh endpoint: validate refresh token → issue new access token

#### § 4.2.2 — Auth Service
  - `register()` — validate, hash password, create user, return tokens
  - `login()` — verify credentials, generate tokens
  - `refreshTokens()` — validate refresh token, generate new pair
  - `logout()` — invalidate refresh token
  - Password hashing: `bcrypt` — `hashSync`, `compareSync`

#### § 4.2.3 — Custom Decorators for Auth
  - `@CurrentUser()` — custom parameter decorator to extract current user
  - `@Public()` — mark endpoint as publicly accessible (skip auth guard)
  - Custom `SetMetadata` for role/permission metadata
  - `createParamDecorator()` — create parameter decorator for `request.user`

---

### 📦 Module 4.3: Guards (Authorization)

#### § 4.3.1 — Guard Fundamentals
  - `CanActivate` interface — implement `canActivate(context)` method
  - Return `true` to allow, `false` or throw to deny
  - Executes AFTER middleware, BEFORE interceptors and pipes
  - `@UseGuards(AuthGuard)` — apply per controller/method
  - Global: `app.useGlobalGuards(new JwtAuthGuard())`

#### § 4.3.2 — Role-Based Access Control
  - `@Roles('admin', 'editor')` — custom decorator setting metadata
  - `RolesGuard` — reads roles metadata, checks against user's roles
  - `Reflector` — reads metadata set by decorators
  - Combine: `@UseGuards(JwtAuthGuard, RolesGuard)` — auth then role check

#### § 4.3.3 — Policy-Based Authorization
  - CASL integration: `@nestjs/casl` or `casl` directly
  - Ability-based: define what each role CAN do
  - Resource-based: check if user can perform action on specific resource
  - `PoliciesGuard` — evaluate policies using abilities

#### § 4.3.4 — OAuth2 / Social Login
  - `passport-google-oauth20`, `passport-github2`, `passport-facebook`
  - OAuth2 flow: redirect → callback → token exchange → create/link user
  - `@nestjs/passport` strategies for each provider

---

### 📦 Module 4.4: Security Best Practices

#### § 4.4.1 — Hardening
  - `helmet` — set security headers
  - `csurf` — CSRF protection (for session-based auth)
  - Rate limiting: `@nestjs/throttler` — built-in rate limiting
  - `ThrottlerModule.forRoot({ ttl: 60000, limit: 10 })` — 10 requests per minute
  - `@SkipThrottle()` — skip for specific endpoints
  - CORS: `app.enableCors({ origin: ['https://example.com'] })`

> ### 🛠️ Phase 4 Project: **"BookshelfAPI v4 — Secured"**
> Add authentication and authorization:
> - **Auth module**: registration, login, token refresh, logout
> - **Passport strategies**: Local (login) + JWT (protected endpoints)
> - **JWT tokens**: access (15 min) + refresh (7 days)
> - **Password hashing**: bcrypt
> - **Custom decorators**: `@CurrentUser()`, `@Public()`, `@Roles()`
> - **Guards**: `JwtAuthGuard` (global), `RolesGuard`
> - **Roles**: Admin (manage everything), User (own resources only)
> - **Resource ownership**: users can only edit/delete their own books and reviews
> - **Rate limiting**: `@nestjs/throttler` on login endpoint
> - **Security**: helmet, CORS configured
> - **Swagger**: JWT Bearer auth scheme, lock icon functional
> - Test: auth flows, protected access, forbidden scenarios

---

## ⚡ PHASE 5 — INTERCEPTORS, GUARDS & THE REQUEST LIFECYCLE
> *"Interceptors are NestJS's AOP. They can transform, cache, log, and time — all without touching business logic."*

---

### 📦 Module 5.1: Interceptors

#### § 5.1.1 — Interceptor Fundamentals
  - `NestInterceptor` interface — implement `intercept(context, next)` method
  - `next.handle()` returns an `Observable` — wrap with RxJS operators
  - Execute BEFORE and AFTER the handler (like AOP around advice)
  - Use case: response transformation, caching, logging, timing, error mapping

#### § 5.1.2 — Common Interceptor Patterns
  - **Logging interceptor**: log request/response with duration
  - **Transform interceptor**: wrap response in `{ data, statusCode, timestamp }` format
  - **Timeout interceptor**: cancel request if handler takes too long
  - **Cache interceptor**: return cached response, skip handler if cache hit
  - **Error mapping interceptor**: catch and transform exceptions

#### § 5.1.3 — Applying Interceptors
  - Global: `app.useGlobalInterceptors(new LoggingInterceptor())`
  - Controller-level: `@UseInterceptors(LoggingInterceptor)`
  - Method-level: `@UseInterceptors(CacheInterceptor)`
  - Module-level: `APP_INTERCEPTOR` provider token

---

### 📦 Module 5.2: Middleware

#### § 5.2.1 — Middleware in NestJS
  - `NestMiddleware` interface — implement `use(req, res, next)` method
  - Executes BEFORE guards, interceptors, pipes (earliest in the pipeline)
  - Access raw request/response objects (Express/Fastify)
  - Apply via `MiddlewareConsumer` in module's `configure()` method
  - Route-specific: `.forRoutes('users')`, `.forRoutes({ path: 'users', method: RequestMethod.GET })`
  - Exclude: `.exclude({ path: 'users', method: RequestMethod.POST })`
  - Functional middleware: simple functions (for Express-compatible middleware)

#### § 5.2.2 — Common Middleware Patterns
  - Request logging: log every request
  - Correlation ID: generate and attach UUID to every request
  - Request timing: track processing duration
  - Body parsing: custom body parsing logic
  - Third-party: `morgan`, `helmet`, `compression` — Express middleware works directly

---

### 📦 Module 5.3: The Full Request Lifecycle

#### § 5.3.1 — Request Processing Order
  - **Middleware** → runs first, Express/Fastify level
  - **Guards** → authorization, should request proceed?
  - **Interceptors (before)** → pre-processing, transform request
  - **Pipes** → validate and transform input parameters
  - **Controller method** → handle the request
  - **Interceptors (after)** → post-processing, transform response
  - **Exception filters** → catch and format errors (at any stage)

#### § 5.3.2 — Execution Context
  - `ExecutionContext` — provides context about the current request
  - `context.switchToHttp()` — get HTTP-specific objects (request, response)
  - `context.switchToWs()` — WebSocket context
  - `context.switchToRpc()` — microservice context
  - `context.getHandler()` — current handler method
  - `context.getClass()` — current controller class
  - `Reflector` — read metadata from decorators

#### § 5.3.3 — Custom Decorators
  - `createParamDecorator()` — custom parameter decorators
  - `SetMetadata()` — attach metadata to handlers/classes
  - `applyDecorators()` — compose multiple decorators into one
  - Custom decorator: `@Auth(Role.Admin)` combining `@UseGuards(JwtGuard, RolesGuard)` and `@Roles(Role.Admin)` and `@ApiBearerAuth()`

> ### 🛠️ Phase 5 Project: **"BookshelfAPI v5 — Cross-Cutting Concerns"**
> Add interceptors, middleware, and advanced lifecycle management:
> - **Interceptors**:
>   - Logging: log method, path, user, duration, status for every request
>   - Transform: wrap all responses in `{ data, meta: { timestamp, requestId } }`
>   - Timeout: cancel requests taking longer than 10 seconds
>   - Serialization: apply `ClassSerializerInterceptor` globally
> - **Middleware**:
>   - Correlation ID: generate UUID, attach to request, include in all logs and response headers
>   - Request logging: detailed request/response logging
> - **Custom decorators**:
>   - `@Auth(Role.Admin)` — composite decorator (guard + roles + swagger)
>   - `@CurrentUser()` — extract user from request
>   - `@Paginate()` — extract pagination parameters
>   - `@ApiPaginatedResponse(BookDto)` — Swagger decorator for paginated responses
> - **Global setup**: guards, interceptors, pipes, filters all configured globally
> - Document the request lifecycle with a diagram

---

## ⚡ PHASE 6 — TESTING
> *"NestJS was built for testability. DI makes mocking trivial. Testing utilities make integration tests elegant."*

---

### 📦 Module 6.1: Testing Fundamentals

#### § 6.1.1 — Testing Stack
  - **Jest** — test framework (default in NestJS)
  - `@nestjs/testing` — NestJS testing utilities
  - `Test.createTestingModule()` — create a testing module with custom providers
  - Test files: `*.spec.ts` (unit), `*.e2e-spec.ts` (end-to-end)
  - Run: `npm run test` (unit), `npm run test:e2e` (e2e), `npm run test:cov` (coverage)

---

### 📦 Module 6.2: Unit Testing

#### § 6.2.1 — Testing Services
  - `Test.createTestingModule({ providers: [UserService, { provide: UserRepository, useValue: mockRepo }] })`
  - Mock dependencies: `jest.fn()`, `jest.spyOn()`
  - `mockRepo.findOne = jest.fn().mockResolvedValue(user)` — configure mock
  - Test business logic in isolation
  - Test error cases: service throws appropriate exceptions

#### § 6.2.2 — Testing Controllers
  - Mock services injected into controllers
  - Test: correct methods called, correct responses returned
  - Verify: status codes, response shapes
  - Less valuable than service tests — controllers should be thin

---

### 📦 Module 6.3: Integration Testing (E2E)

#### § 6.3.1 — E2E Test Setup
  - `Test.createTestingModule({ imports: [AppModule] })` — full app module
  - `app.init()` — initialize the NestJS application
  - `supertest` — HTTP request library for testing
  - `request(app.getHttpServer()).get('/users').expect(200)` — make requests

#### § 6.3.2 — Database Testing
  - Test database: separate PostgreSQL instance or Docker container
  - Testcontainers: `@testcontainers/postgresql` — spin up real PostgreSQL
  - Database cleanup: truncate tables between tests or use transactions
  - `beforeEach` / `afterEach` — setup and teardown

#### § 6.3.3 — Testing Authentication
  - Create test user and generate JWT token in `beforeAll`
  - Pass token: `.set('Authorization', 'Bearer ${token}')` on requests
  - Test protected endpoints with and without tokens
  - Test role-based access: admin vs regular user

#### § 6.3.4 — Override Providers in Tests
  - `.overrideProvider(ConfigService).useValue(mockConfigService)` — replace services
  - `.overrideGuard(JwtAuthGuard).useValue({ canActivate: () => true })` — bypass auth
  - `.overrideInterceptor(LoggingInterceptor).useValue({})` — remove interceptors
  - Essential for isolating test concerns

---

### 📦 Module 6.4: Testing Patterns

#### § 6.4.1 — Test Data Factories
  - Factory functions for creating test entities
  - `faker` or `@faker-js/faker` for realistic test data
  - Consistent, reusable test data across test files
  - Builder pattern: `UserFactory.create({ role: Role.Admin })`

#### § 6.4.2 — Contract Testing
  - Pact or custom contract tests between services
  - Consumer-driven: frontend defines expected API contract
  - Provider verification: backend verifies it meets the contract

> ### 🛠️ Phase 6 Project: **"BookshelfAPI v6 — Fully Tested"**
> Add comprehensive testing:
> - **Unit tests** (Jest):
>   - All service methods with mocked repositories
>   - Guard logic (RolesGuard, JwtAuthGuard)
>   - Pipe validation (custom pipes)
>   - Interceptor behavior
> - **E2E tests** (supertest):
>   - Full CRUD flows for books, authors, reviews
>   - Auth flow: register → login → access protected → refresh → logout
>   - Authorization: admin vs user, resource ownership
>   - Validation: verify error responses for invalid data
>   - Pagination, filtering, sorting
> - **Database**: Testcontainers for real PostgreSQL in tests
> - **Auth**: generate real JWT tokens for authenticated tests
> - **Factories**: `BookFactory`, `UserFactory`, `AuthorFactory`
> - **Coverage**: 80%+ with Jest coverage report
> - **CI**: GitHub Actions running all tests

---

## ⚡ PHASE 7 — CACHING, QUEUES, SCHEDULING & REAL-TIME
> *"NestJS has first-party support for caching, queues, scheduling, and WebSockets — all with the same modular, injectable architecture."*

---

### 📦 Module 7.1: Caching

#### § 7.1.1 — Cache Module
  - `@nestjs/cache-manager` — built-in caching
  - `CacheModule.register({ ttl: 60, max: 100 })` — in-memory cache
  - `CacheModule.register({ store: redisStore, host, port })` — Redis cache
  - `@UseInterceptors(CacheInterceptor)` — auto-cache GET responses
  - `@CacheKey('custom-key')`, `@CacheTTL(300)` — customize per endpoint
  - `CACHE_MANAGER` injection token — inject cache manager for manual operations
  - `cache.get(key)`, `cache.set(key, value, ttl)`, `cache.del(key)` — manual cache operations

#### § 7.1.2 — Redis Integration
  - `cache-manager-redis-yet` — Redis store for cache-manager
  - Direct Redis: `ioredis` — for pub/sub, data structures, advanced features
  - Redis for sessions, rate limiting, real-time features
  - Connection pooling and cluster support

---

### 📦 Module 7.2: Queue Processing (Bull / BullMQ)

#### § 7.2.1 — Queue Fundamentals
  - `@nestjs/bullmq` — BullMQ integration (recommended) or `@nestjs/bull` (legacy)
  - Redis-backed job queue
  - `BullModule.forRoot({ connection: { host, port } })` — configure connection
  - `BullModule.registerQueue({ name: 'email' })` — register a queue

#### § 7.2.2 — Producers & Consumers
  - Producer: `@InjectQueue('email') private emailQueue: Queue` — inject queue
  - `emailQueue.add('send-welcome', { userId, email })` — add job
  - Consumer: `@Processor('email')` — process jobs from queue
  - `@Process('send-welcome')` — handle specific job type
  - `@OnQueueActive()`, `@OnQueueCompleted()`, `@OnQueueFailed()` — lifecycle events

#### § 7.2.3 — Advanced Queue Features
  - Delayed jobs: `emailQueue.add('reminder', data, { delay: 3600000 })` — delay 1 hour
  - Repeatable jobs: `{ repeat: { cron: '0 0 * * *' } }` — daily at midnight
  - Job priority: `{ priority: 1 }` — higher priority processed first
  - Retries: `{ attempts: 3, backoff: { type: 'exponential', delay: 1000 } }`
  - Concurrency: `@Processor('email', { concurrency: 5 })` — parallel processing
  - Bull Board: dashboard UI for monitoring queues

---

### 📦 Module 7.3: Task Scheduling

#### § 7.3.1 — Schedule Module
  - `@nestjs/schedule` — built-in scheduling
  - `ScheduleModule.forRoot()` — enable scheduling
  - `@Cron('0 0 * * *')` — cron-based scheduling (daily at midnight)
  - `@Interval(60000)` — run every 60 seconds
  - `@Timeout(5000)` — run once after 5 seconds
  - Cron patterns: second, minute, hour, day, month, weekday
  - `CronExpression.EVERY_DAY_AT_MIDNIGHT` — predefined expressions
  - Dynamic cron jobs: `SchedulerRegistry` — add/remove jobs at runtime

---

### 📦 Module 7.4: WebSockets & Real-Time

#### § 7.4.1 — WebSocket Gateway
  - `@nestjs/websockets` + `@nestjs/platform-socket.io` — Socket.IO integration
  - `@WebSocketGateway()` — define a WebSocket gateway
  - `@SubscribeMessage('message')` — listen for events
  - `@WebSocketServer() server: Server` — access Socket.IO server
  - `server.emit('event', data)` — broadcast to all
  - `client.join('room')` — join a room
  - `server.to('room').emit('event', data)` — broadcast to room

#### § 7.4.2 — WebSocket Authentication
  - `handleConnection(client)` — validate on connection
  - Extract JWT from handshake query or headers
  - Reject unauthenticated connections
  - Attach user to socket for subsequent messages

#### § 7.4.3 — WebSocket Guards, Pipes, Interceptors
  - All NestJS features work with WebSocket gateways
  - `WsException` — WebSocket-specific exception
  - Guards: `@UseGuards(WsAuthGuard)` — protect WebSocket events
  - Same decorator-based approach as HTTP controllers

---

### 📦 Module 7.5: Server-Sent Events (SSE)

#### § 7.5.1 — SSE in NestJS
  - `@Sse('events')` — SSE endpoint
  - Return `Observable<MessageEvent>` — stream events to client
  - Use case: live feeds, notifications, progress updates
  - Simpler than WebSocket for server → client one-way communication

---

### 📦 Module 7.6: Events (EventEmitter)

#### § 7.6.1 — Event-Driven Architecture
  - `@nestjs/event-emitter` — in-process event system
  - `EventEmitterModule.forRoot()` — enable events
  - `EventEmitter2.emit('user.created', payload)` — emit event
  - `@OnEvent('user.created')` — listen for event
  - Async event handlers: `@OnEvent('order.placed', { async: true })`
  - Wildcards: `@OnEvent('user.*')` — catch all user events
  - Decouple services: service emits event, other services react independently

> ### 🛠️ Phase 7 Project: **"BookshelfAPI v7 — Background & Real-Time"**
> Add caching, queues, scheduling, and real-time:
> - **Caching**: Redis cache for book listings, category lists
>   - `CacheInterceptor` on GET endpoints
>   - Manual cache invalidation on create/update/delete
>   - Custom cache keys for filtered/paginated results
> - **Queues** (BullMQ):
>   - Email queue: welcome email on registration, review notification
>   - Image processing queue: resize book cover images
>   - Bull Board dashboard for monitoring
>   - Retry with exponential backoff on failures
> - **Scheduling**:
>   - Daily: clean up expired sessions
>   - Weekly: generate popularity report
>   - Hourly: refresh external API data cache
> - **WebSocket**: real-time notifications
>   - New book notifications to subscribed users
>   - Live review feed for a book
>   - Authenticated WebSocket connections
> - **Events**: `book.created`, `review.posted`, `user.registered`
>   - Decouple: event triggers email, cache invalidation, analytics
> - **Docker Compose**: add Redis

---

## ⚡ PHASE 8 — MONITORING, LOGGING & OBSERVABILITY
> *"If it's not monitored, it's not in production."*

---

### 📦 Module 8.1: Structured Logging

#### § 8.1.1 — NestJS Logger
  - `Logger` — built-in logger (console-based, basic)
  - `logger.log()`, `logger.error()`, `logger.warn()`, `logger.debug()`, `logger.verbose()`
  - `new Logger('UserService')` — named logger per class
  - Custom logger: implement `LoggerService` interface

#### § 8.1.2 — Production Logging (Pino / Winston)
  - **Pino** — fastest Node.js logger (recommended)
  - `nestjs-pino` — Pino integration for NestJS
  - JSON structured logging for machine parsing
  - Automatic request context: request ID, method, path, status, duration
  - `PinoLogger` as NestJS logger replacement
  - Winston: alternative, more configurable, slower

#### § 8.1.3 — Log Correlation
  - Request ID in every log line
  - Correlation ID propagation across services
  - User context: user ID, role in log lines
  - `cls-hooked` or `AsyncLocalStorage` for request-scoped context

---

### 📦 Module 8.2: Health Checks

#### § 8.2.1 — Terminus Health Checks
  - `@nestjs/terminus` — health check framework
  - `HealthCheckService` — orchestrate multiple health checks
  - Built-in indicators: `TypeOrmHealthIndicator`, `HttpHealthIndicator`, `MemoryHealthIndicator`, `DiskHealthIndicator`
  - Custom indicators: `HealthIndicator` — check external services
  - Endpoint: `GET /health` returning detailed health status
  - Kubernetes probes: liveness and readiness checks

---

### 📦 Module 8.3: Metrics & Tracing

#### § 8.3.1 — Prometheus Metrics
  - `@willsoto/nestjs-prometheus` — Prometheus integration
  - Auto-collected: HTTP request duration, count, response size
  - Custom metrics: business counters, gauges, histograms
  - `/metrics` endpoint for Prometheus scraping
  - Grafana dashboards for visualization

#### § 8.3.2 — OpenTelemetry
  - `@opentelemetry/sdk-node` — auto-instrumentation
  - Traces: HTTP requests, database queries, external calls
  - Custom spans for business operations
  - Exporters: Jaeger, Zipkin, OTLP
  - `nestjs-otel` — NestJS-specific OpenTelemetry integration
  - Trace ID in all log lines for correlation

---

### 📦 Module 8.4: Error Tracking

#### § 8.4.1 — Sentry Integration
  - `@sentry/nestjs` — Sentry for NestJS
  - Auto-capture: unhandled exceptions, performance transactions
  - Source maps for readable stack traces
  - Release tracking: associate errors with deployments
  - User context: attach user info to error reports

> ### 🛠️ Phase 8 Project: **"BookshelfAPI v8 — Fully Observable"**
> Add complete observability:
> - **Pino logging**: structured JSON, request context, correlation IDs
> - **Health checks** (`@nestjs/terminus`): database, Redis, external API, memory, disk
> - **Prometheus metrics**: request rate, latency, error rate, custom business metrics
> - **Grafana dashboard**: HTTP metrics, database metrics, queue metrics
> - **OpenTelemetry**: distributed tracing with Jaeger
> - **Sentry**: error tracking and performance monitoring
> - **Docker Compose**: add Prometheus, Grafana, Jaeger

---

## ⚡ PHASE 9 — DESIGN PATTERNS & ARCHITECTURE
> *"NestJS is uniquely positioned to implement enterprise patterns. Its DI system makes Clean Architecture and CQRS natural."*

---

### 📦 Module 9.1: Clean Architecture

#### § 9.1.1 — Layered Architecture in NestJS
  - **Domain layer**: entities, value objects, domain interfaces (no NestJS imports)
  - **Application layer**: use cases, DTOs, application interfaces, validators
  - **Infrastructure layer**: database (TypeORM/Prisma), email, external APIs
  - **Presentation layer**: controllers, gateways, interceptors
  - Dependency rule: inner layers don't know about outer layers

#### § 9.1.2 — Module Organization
  - Feature modules: one module per bounded context
  - Shared module: common utilities, base classes
  - Infrastructure module: database, cache, messaging
  - Each feature module is self-contained: controller, service, repository, DTOs, entities

---

### 📦 Module 9.2: CQRS & Event Sourcing

#### § 9.2.1 — CQRS with `@nestjs/cqrs`
  - `CqrsModule` — built-in CQRS support
  - **Commands**: `CreateBookCommand` + `CreateBookHandler` — state changes
  - **Queries**: `GetBookQuery` + `GetBookHandler` — data retrieval
  - `CommandBus.execute(command)` — dispatch commands
  - `QueryBus.execute(query)` — dispatch queries

#### § 9.2.2 — Events
  - **Domain events**: `BookCreatedEvent` — emitted after state change
  - `EventBus.publish(event)` — publish events
  - `@EventsHandler(BookCreatedEvent)` — handle events
  - Sagas: `@Saga()` — orchestrate multi-step processes from events
  - Event sourcing: store events as the source of truth (advanced)

#### § 9.2.3 — CQRS Pipeline
  - Command → CommandHandler → Repository (write) → EventBus → EventHandler (side effects)
  - Query → QueryHandler → Repository (read) → Response
  - Separate read/write models for complex domains
  - Benefits: independent scaling, optimized models, clear intent

---

### 📦 Module 9.3: Common Patterns

#### § 9.3.1 — Repository Pattern
  - Abstract data access behind interfaces
  - NestJS custom providers: `{ provide: 'IUserRepository', useClass: TypeOrmUserRepository }`
  - Swap implementations: TypeORM → Prisma → InMemory (for tests)
  - Generic repository: base CRUD operations

#### § 9.3.2 — Strategy Pattern
  - Multiple implementations of the same interface
  - Factory: select strategy based on context
  - NestJS: inject all implementations, select at runtime
  - Use case: payment processors, notification channels, storage backends

#### § 9.3.3 — Observer Pattern (Events)
  - `@nestjs/event-emitter` — decouple services through events
  - Publisher doesn't know about subscribers
  - Add new behavior without modifying existing code
  - Use case: audit logging, cache invalidation, notifications

#### § 9.3.4 — Factory Pattern
  - Factory services: create instances based on configuration/context
  - NestJS factory providers: `useFactory` for complex instantiation
  - Use case: database connections, API clients, strategy selection

---

### 📦 Module 9.4: Anti-Patterns

#### § 9.4.1 — NestJS Anti-Patterns to Avoid
  - Fat controllers: business logic in controllers instead of services
  - Circular dependencies: A depends on B, B depends on A
  - `@Inject(REQUEST)` overuse: makes services request-scoped (performance impact)
  - Barrel file re-exports causing circular dependency issues
  - `@Global()` overuse: making everything globally available
  - Not using DTOs: passing raw request bodies to services
  - Mixing concerns: database queries in controllers, HTTP logic in services

> ### 🛠️ Phase 9 Project: **"BookshelfAPI v9 — CQRS Architecture"**
> Restructure with CQRS and Clean Architecture:
> - **CQRS** (`@nestjs/cqrs`):
>   - Commands: `CreateBookCommand`, `UpdateBookCommand`, `DeleteBookCommand`
>   - Queries: `GetBookQuery`, `ListBooksQuery`, `SearchBooksQuery`
>   - Handlers: one per command/query
>   - Events: `BookCreatedEvent`, `BookUpdatedEvent`, `ReviewPostedEvent`
>   - Sagas: `BookSaga` — when book is reviewed 10 times, auto-feature it
> - **Clean Architecture**:
>   - Domain: `Book` entity with behavior, `ISBN` value object
>   - Application: commands, queries, handlers, DTOs
>   - Infrastructure: TypeORM/Prisma repositories, email service
>   - Presentation: controllers, WebSocket gateways
> - **Repository pattern**: interface in domain, implementation in infrastructure
> - **Events**: `BookCreatedEvent` triggers: email notification, cache invalidation, analytics update
> - **Architecture tests**: verify layer dependencies don't violate rules
> - **Documentation**: architecture diagram, ADR for CQRS decision

---

## ⚡ PHASE 10 — MICROSERVICES
> *"NestJS has first-party microservices support. Transport layers are swappable. Your business logic stays the same."*

---

### 📦 Module 10.1: NestJS Microservices Fundamentals

#### § 10.1.1 — Microservices Module
  - `@nestjs/microservices` — built-in microservices support
  - Transport layers: TCP, Redis, NATS, MQTT, RabbitMQ, Kafka, gRPC
  - Same decorators, DI, and patterns — just different transport
  - Hybrid application: HTTP + microservice in the same app
  - `app.connectMicroservice({ transport: Transport.TCP })` — add microservice transport

#### § 10.1.2 — Message Patterns
  - **Request-Response**: `@MessagePattern('get_user')` — synchronous RPC
  - **Event-Based**: `@EventPattern('user_created')` — fire-and-forget
  - Client: `ClientProxy.send('get_user', payload)` — request-response
  - Client: `ClientProxy.emit('user_created', payload)` — event emission
  - `ClientsModule.register([{ name: 'USER_SERVICE', transport: Transport.TCP }])`

---

### 📦 Module 10.2: Transport Layers

#### § 10.2.1 — TCP Transport
  - Default transport, simple request-response
  - Good for: internal services on the same network

#### § 10.2.2 — Redis Transport
  - Pub/Sub-based communication
  - `Transport.REDIS` — configure host, port
  - Good for: lightweight messaging, event distribution

#### § 10.2.3 — RabbitMQ (AMQP) Transport
  - `@golevelup/nestjs-rabbitmq` — advanced RabbitMQ integration
  - Exchanges, queues, routing keys
  - Dead letter queues, retry logic
  - Good for: reliable messaging, complex routing

#### § 10.2.4 — Kafka Transport
  - `Transport.KAFKA` — Kafka integration
  - Consumer groups, partitions, offsets
  - Good for: high-throughput event streaming, log aggregation

#### § 10.2.5 — gRPC Transport
  - `@nestjs/microservices` + `@grpc/grpc-js`
  - `.proto` files for service and message definitions
  - Code generation: auto-generate TypeScript interfaces
  - Unary, server streaming, client streaming, bidirectional
  - Good for: high-performance inter-service communication

---

### 📦 Module 10.3: API Gateway

#### § 10.3.1 — Gateway Pattern
  - Dedicated NestJS service as API gateway
  - Routes requests to appropriate microservices
  - Aggregates responses from multiple services
  - Authentication at the gateway level
  - Rate limiting, CORS, request transformation

---

### 📦 Module 10.4: Distributed Patterns

#### § 10.4.1 — Saga Pattern
  - Coordinate distributed transactions across services
  - `@nestjs/cqrs` sagas: react to events, trigger commands
  - Orchestration: central coordinator manages steps
  - Choreography: services react to events independently
  - Compensating actions on failure

#### § 10.4.2 — Service Discovery
  - Consul, etcd — service registration and discovery
  - Kubernetes DNS — built-in service discovery
  - `@nestjs/terminus` — health checks for service readiness

#### § 10.4.3 — Resilience
  - Circuit breaker: prevent cascading failures
  - Retry with exponential backoff
  - Timeout: don't wait forever
  - `nestjs-resilience` or Polly-like patterns

> ### 🛠️ Phase 10 Project: **"ShelfPlatform — Microservices Architecture"**
> Build a distributed bookshelf platform:
> - **Services**:
>   - `api-gateway` — NestJS HTTP gateway, authentication, rate limiting
>   - `books-service` — book CRUD, search (TCP or gRPC)
>   - `users-service` — registration, auth, profiles (TCP or gRPC)
>   - `reviews-service` — reviews, ratings (event-driven)
>   - `notifications-service` — email, push (event consumer)
> - **Communication**:
>   - Sync: TCP or gRPC between gateway and services
>   - Async: RabbitMQ or Kafka for events (BookCreated → Reviews, Notifications)
> - **Each service**: own PostgreSQL database, own module structure
> - **Resilience**: circuit breaker, retry, timeout on inter-service calls
> - **Observability**: Pino logging, Prometheus metrics, OpenTelemetry tracing across services
> - **Docker Compose**: all services + RabbitMQ/Kafka + PostgreSQL + Redis + monitoring

---

## ⚡ PHASE 11 — DEPLOYMENT & PRODUCTION
> *"NestJS compiles to standard Node.js. It runs anywhere Node runs."*

---

### 📦 Module 11.1: Docker

#### § 11.1.1 — Production Dockerfile
  - Multi-stage build: install deps → build → production
  - `node:20-alpine` — minimal base image
  - Non-root user for security
  - `npm ci --only=production` — production dependencies only
  - Copy only `dist/` and `node_modules` to final stage
  - `CMD ["node", "dist/main"]` — run compiled JavaScript

#### § 11.1.2 — Docker Compose
  - NestJS + PostgreSQL + Redis + RabbitMQ + monitoring
  - Development: volume mounts, hot-reload
  - Production: optimized images, environment variables

---

### 📦 Module 11.2: Deployment Platforms

#### § 11.2.1 — Deployment Options
  - **Docker + VPS**: DigitalOcean, Hetzner, Linode — full control
  - **AWS**: ECS/Fargate (containers), Lambda (serverless), Elastic Beanstalk
  - **Google Cloud**: Cloud Run (serverless containers), GKE (Kubernetes)
  - **Azure**: Container Apps, AKS
  - **Railway / Render / Fly.io** — managed platforms, simple deployment
  - **Vercel**: serverless functions (limited NestJS support)

#### § 11.2.2 — Kubernetes
  - Deployment, Service, Ingress manifests
  - Health probes: `/health` endpoint mapping
  - ConfigMap and Secrets
  - Horizontal Pod Autoscaler
  - Resource limits

---

### 📦 Module 11.3: Performance

#### § 11.3.1 — Fastify Adapter
  - Replace Express with Fastify for 2-3x performance
  - `NestFactory.create<NestFastifyApplication>(AppModule, new FastifyAdapter())`
  - Most NestJS features work identically
  - Some Express-specific middleware may need adaptation
  - Recommended for performance-critical applications

#### § 11.3.2 — Node.js Performance
  - Clustering: `cluster` module or PM2 for multi-process
  - PM2: process manager with load balancing, monitoring, auto-restart
  - Memory management: monitor heap, avoid leaks
  - Connection pooling: database, Redis, HTTP clients
  - Compression: `compression` middleware or reverse proxy

---

### 📦 Module 11.4: CI/CD

#### § 11.4.1 — GitHub Actions
  - Lint: `npm run lint`
  - Test: `npm run test`, `npm run test:e2e`
  - Build: `npm run build`
  - Docker: build and push image
  - Deploy: update deployment
  - Cache: `node_modules` caching for faster builds

---

### 📦 Module 11.5: Security Hardening

#### § 11.5.1 — Production Checklist
  - `helmet` — security headers
  - CORS configured for specific origins
  - Rate limiting enabled (`@nestjs/throttler`)
  - HTTPS enforced (via reverse proxy)
  - Environment variables for all secrets
  - `npm audit` — dependency vulnerability scanning
  - Non-root Docker user
  - Request size limits
  - Debug/development features disabled

> ### 🛠️ Phase 11 Capstone Project: **"ShelfPlatform — Production Deployed"**
> Deploy the microservices platform:
> - **Docker**: multi-stage Dockerfiles for all services
> - **Docker Compose**: full development environment
> - **Deployment**: choose and execute one:
>   - Option A: Railway/Render (simplest)
>   - Option B: Docker + VPS with Nginx reverse proxy
>   - Option C: Kubernetes (local k3s or cloud AKS/EKS/GKE)
> - **CI/CD**: GitHub Actions — lint → test → build → deploy (per service)
> - **Fastify**: swap Express for Fastify on performance-critical services
> - **PM2**: process management with clustering
> - **Database**: managed PostgreSQL
> - **Monitoring**: full observability stack deployed
> - **Security**: production checklist verified
> - **Load test**: Artillery or k6 benchmark
> - **Documentation**: architecture diagram, deployment guide, runbook

---

## 📊 PHASE MAP (Visual Summary)

```
Phase 0   ██░░░░░░░░░░░░░░░░  Prerequisites & Orientation
Phase 1   ████░░░░░░░░░░░░░░  Core (Modules, Controllers, Providers, DI)
Phase 2   ██████░░░░░░░░░░░░  Validation, Pipes & Serialization
Phase 3   ████████░░░░░░░░░░  Database (TypeORM / Prisma, Migrations)
Phase 4   █████████░░░░░░░░░  Authentication & Authorization (JWT, Guards)
Phase 5   ██████████░░░░░░░░  Interceptors, Middleware & Request Lifecycle
Phase 6   ███████████░░░░░░░  Testing (Unit, E2E, Integration)
Phase 7   ████████████░░░░░░  Caching, Queues, Scheduling & Real-Time
Phase 8   █████████████░░░░░  Monitoring & Observability
Phase 9   ██████████████░░░░  Design Patterns & CQRS Architecture
Phase 10  ███████████████░░░  Microservices (TCP, gRPC, RabbitMQ, Kafka)
Phase 11  ████████████████░░  Deployment & Production
```

---

## 🎯 DIFFICULTY & SKILL PROGRESSION

```
       BEGINNER              INTERMEDIATE              ADVANCED                 EXPERT
    ┌────────────┐        ┌────────────────┐       ┌──────────────┐       ┌──────────────┐
    │  Phase 0   │───────▶│    Phase 3     │──────▶│   Phase 7    │──────▶│   Phase 10   │
    │  Phase 1   │        │    Phase 4     │       │   Phase 8    │       │   Phase 11   │
    │  Phase 2   │        │    Phase 5     │       │   Phase 9    │       │              │
    │            │        │    Phase 6     │       │              │       │              │
    └────────────┘        └────────────────┘       └──────────────┘       └──────────────┘
    "I can build           "I build secure,         "I build well-         "I architect
     structured APIs        tested, database-        architected,           distributed
     with NestJS"           backed APIs"             observable systems"    systems"
```

---

## ⚠️ THE EVOLVING BOOKSHELF PROJECT

```
Phase 1:   BookshelfAPI v1  — Core architecture (modules, DI, in-memory)
Phase 2:   BookshelfAPI v2  — Validated & documented
Phase 3:   BookshelfAPI v3  — Database-backed
Phase 4:   BookshelfAPI v4  — Secured with JWT
Phase 5:   BookshelfAPI v5  — Cross-cutting concerns (interceptors, middleware)
Phase 6:   BookshelfAPI v6  — Fully tested
Phase 7:   BookshelfAPI v7  — Background jobs & real-time
Phase 8:   BookshelfAPI v8  — Fully observable
Phase 9:   BookshelfAPI v9  — CQRS architecture
Phase 10:  ShelfPlatform    — Microservices
Phase 11:  ShelfPlatform    — Production deployed
```

---

## 📚 RECOMMENDED RESOURCES

| Resource | Type | Phase |
|----------|------|-------|
| **NestJS Official Docs** (docs.nestjs.com) | 🌐 Official (START HERE) | ALL |
| **NestJS Official Courses** (courses.nestjs.com) | 🌐 Official (Paid) | ALL |
| *NestJS in Action* — upcoming titles | 📖 Book | ALL |
| **Marius Espejo** (YouTube) | 🎥 Video (NestJS tutorials) | 0–6 |
| **Anson the Developer** (YouTube) | 🎥 Video (Full NestJS projects) | 0–7 |
| **Michael Guay** (YouTube) | 🎥 Video (NestJS deep dives) | 3–9 |
| **Wanago.io** (Blog) | 🌐 NestJS Tutorial Series | ALL |
| **Trilon.io** (Blog) | 🌐 NestJS Consulting, Best Practices | 5–11 |
| **NestJS Discord** | 🌐 Community | ALL |
| **TypeORM Docs** | 📄 ORM | 3 |
| **Prisma Docs** | 📄 ORM | 3 |
| **Passport.js Docs** | 📄 Authentication | 4 |
| **BullMQ Docs** | 📄 Queue Processing | 7 |
| **class-validator Docs** | 📄 Validation | 2 |
| **class-transformer Docs** | 📄 Serialization | 2 |
| **Jest Docs** | 📄 Testing | 6 |
| **Awesome NestJS** (GitHub) | 🌐 Resource List | ALL |
| **NestJS Devtools** | 🧪 Debugging Tool | ALL |

---

## 🗺️ WHERE NESTJS TAKES YOU (Career Paths)

```
                                  ┌───────────────────────────┐
                                  │   Backend / API           │
                           ┌─────▶│   Engineering             │
                           │      │   (REST, GraphQL, gRPC)   │
                           │      └───────────────────────────┘
                           │      ┌───────────────────────────┐
                           │      │   Microservices           │
                   ┌───────┤─────▶│   Architect               │
                   │       │      │   (Distributed, Event-     │
                   │       │      │    Driven Systems)         │
                   │       │      └───────────────────────────┘
                   │       │      ┌───────────────────────────┐
   ┌────────────┐  │       │      │   Full-Stack TypeScript   │
   │            │  │       ├─────▶│   Developer               │
   │  Master    ├──┤       │      │   (NestJS + Next.js /     │
   │  NestJS    │  │       │      │    Angular / React)        │
   │            │  │       │      └───────────────────────────┘
   └────────────┘  │       │      ┌───────────────────────────┐
                   │       │      │   Enterprise / Consulting │
                   │       ├─────▶│   (Large-Scale Systems,   │
                   │       │      │    Architecture Design)    │
                   │       │      └───────────────────────────┘
                   │       │      ┌───────────────────────────┐
                   │       │      │   Real-Time / IoT         │
                   └───────┴─────▶│   Applications            │
                                  │   (WebSocket, MQTT, SSE)   │
                                  └───────────────────────────┘
```

---

> ### 💡 Final Advice
> **"NestJS brings structure to Node.js. But structure without understanding is just ceremony. Learn WHY each piece exists."**
>
> Five non-negotiable rules for your NestJS journey:
>
> 1. **Understand the request lifecycle deeply.** Middleware → Guards → Interceptors (before) → Pipes → Handler → Interceptors (after) → Filters. Every NestJS bug you'll encounter traces back to misunderstanding this order. Draw it. Memorize it. Live it.
>
> 2. **Master Dependency Injection.** NestJS's DI is its beating heart. Constructor injection, provider scopes, custom providers, module imports/exports — if you don't understand DI, you can't build testable, maintainable NestJS applications. Coming from Express? This is the biggest paradigm shift.
>
> 3. **Use DTOs everywhere. Never pass raw request bodies.** `class-validator` + `ValidationPipe` with `whitelist: true` and `forbidNonWhitelisted: true` is your security boundary. Every request body, every query parameter, every route parameter should be typed and validated through a DTO.
>
> 4. **Test from Phase 3 onward.** NestJS's `Test.createTestingModule()` makes mocking trivial. `supertest` makes API testing elegant. There's no excuse. Mock your dependencies, test your services, integration-test your endpoints.
>
> 5. **Read the official docs cover to cover.** NestJS has some of the best framework documentation in the Node.js ecosystem. Every feature is documented with examples. The "Custom decorators," "Execution context," and "Circular dependency" pages alone will save you days of debugging.
>
> The difference between a *NestJS developer* and a *NestJS engineer* is:
> - **Understanding the module system**: properly organized, no circular deps, clean exports
> - **Leveraging the full pipeline**: guards for auth, interceptors for transforms, pipes for validation — not everything in the controller
> - **Thinking in patterns**: CQRS for complex domains, events for decoupling, repositories for data access
> - **Production mindset**: structured logging, health checks, metrics, graceful shutdown — not afterthoughts

---

*This roadmap takes you from "What's a decorator?" to "I can architect, build, test, monitor, and deploy production-grade distributed microservices with CQRS, event-driven messaging, real-time WebSocket, and full observability — all in beautifully structured, type-safe NestJS."* 🐈🚀