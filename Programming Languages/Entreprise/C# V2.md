# 💜 THE ULTIMATE C# ROADMAP
### From Zero to Production-Grade C# Mastery

> **Structure:** Phase → Modules → Sections
> **Estimated Duration:** ~8-12 Months (Dedicated Study)
> **Prerequisite:** None — starts from absolute zero
> *C# is one of the most well-designed, continuously evolving languages in existence. It borrows the best ideas from every language and makes them work together beautifully.*

---

## ⚡ PHASE 0 — ENVIRONMENT SETUP & C# ORIENTATION
> *"C# is not just a language. It's a language + runtime + ecosystem + philosophy."*

---

### 📦 Module 0.1: Understanding C#'s Identity

#### § 0.1.1 — What is C# & Why It Matters
  - Created by Anders Hejlsberg at Microsoft (2000)
  - Designed as a modern, type-safe, object-oriented, component-based language
  - Originally "Java killer" for Windows — now fully cross-platform
  - Where C# dominates: enterprise backends, game development (Unity), desktop apps (WPF/WinUI), cloud services (Azure), mobile (MAUI), web APIs, IoT, AI/ML (.NET ML)

#### § 0.1.2 — The .NET Ecosystem
  - **.NET** (formerly .NET Core) — the modern, cross-platform, open-source runtime
  - **.NET Framework** — Windows-only legacy (4.x — maintenance mode, don't start new projects here)
  - **CLR (Common Language Runtime)** — executes managed code (garbage collection, JIT compilation, type safety)
  - **BCL (Base Class Library)** — massive standard library
  - **Roslyn** — the C# compiler (open-source, written in C#)
  - **NuGet** — package manager
  - **MSBuild** — build system
  - C# source → Roslyn compiler → **IL (Intermediate Language)** → JIT → Native machine code

#### § 0.1.3 — C# vs Other Languages
  - C# vs Java: similar syntax, C# is more modern (properties, LINQ, async/await, value types, pattern matching, records)
  - C# vs C++: managed memory, safer, slower for systems programming, faster development
  - C# vs TypeScript: both by Anders Hejlsberg, C# is compiled & strongly typed
  - C# vs Go: more features, more complexity, richer type system, less opinionated
  - C# vs Python: statically typed, compiled, much faster runtime, more verbose

#### § 0.1.4 — C# Version History (Key Milestones)
  - **C# 1.0** (2002) — managed code, classes, interfaces, delegates
  - **C# 2.0** (2005) — generics, nullable types, iterators, anonymous methods
  - **C# 3.0** (2007) — LINQ, lambda expressions, extension methods, `var`, anonymous types
  - **C# 4.0** (2010) — `dynamic`, named/optional parameters, covariance/contravariance
  - **C# 5.0** (2012) — `async`/`await` (revolutionary)
  - **C# 6.0** (2015) — string interpolation, null-conditional `?.`, expression-bodied members
  - **C# 7.x** (2017) — tuples, pattern matching, `out var`, local functions, `ref` returns
  - **C# 8.0** (2019) — nullable reference types, async streams, default interface members, switch expressions
  - **C# 9.0** (2020) — records, `init`-only setters, top-level statements, pattern matching improvements
  - **C# 10** (2021) — global usings, file-scoped namespaces, `record struct`
  - **C# 11** (2022) — raw string literals, required members, generic math, list patterns
  - **C# 12** (2023) — primary constructors, collection expressions, alias any type
  - **C# 13** (2024) — `params` collections, `Lock` type, `ref` and `unsafe` in async/iterators
  - **C# 14** (2025) — field keyword, extension members, null-conditional assignment
  - Always use the latest stable version

---

### 📦 Module 0.2: Setting Up the Development Environment

#### § 0.2.1 — Installing the .NET SDK
  - Official installer from dotnet.microsoft.com
  - Linux: `sudo apt install dotnet-sdk-9.0` (or latest)
  - macOS: `brew install dotnet-sdk`
  - Windows: official installer or Visual Studio includes it
  - Verifying: `dotnet --version`, `dotnet --list-sdks`

#### § 0.2.2 — Editors & IDEs
  - **Visual Studio** (Windows/Mac) — the ultimate C# IDE (Community edition is free)
  - **JetBrains Rider** — cross-platform, powerful (best on Linux)
  - **VS Code + C# Dev Kit** — lightweight, cross-platform
  - Why Visual Studio / Rider: refactoring, IntelliSense, debugging, NuGet integration, profiling, test runners
  - Hot Reload: see changes instantly without restarting

#### § 0.2.3 — The .NET CLI
  - `dotnet new console -n MyApp` — create new console project
  - `dotnet new webapi -n MyApi` — create new web API project
  - `dotnet run` — build and run
  - `dotnet build` — compile
  - `dotnet test` — run tests
  - `dotnet publish` — publish for deployment
  - `dotnet add package PackageName` — add NuGet dependency
  - `dotnet new list` — see all available templates
  - `dotnet tool install` — install global/local tools

#### § 0.2.4 — Project Structure
  - `.csproj` — project file (MSBuild XML format)
  - `<TargetFramework>net9.0</TargetFramework>` — target runtime
  - `<Nullable>enable</Nullable>` — enable nullable reference type checking
  - `<ImplicitUsings>enable</ImplicitUsings>` — auto-import common namespaces
  - Solution file (`.sln`) — groups multiple projects
  - `dotnet new sln`, `dotnet sln add ProjectName`
  - `bin/` — compiled output, `obj/` — intermediate files
  - `global.json` — pin SDK version for the project

---

### 📦 Module 0.3: Your First C# Program

#### § 0.3.1 — Top-Level Statements (C# 9+)
  - Minimal program: just write code, no `Main` method needed
  - `Console.WriteLine("Hello, World!");` — that's the entire program
  - Implicit `Main` method generated by the compiler
  - Top-level statements are for the entry point only (one file per project)

#### § 0.3.2 — Traditional Program Structure
  - `namespace`, `class`, `static void Main(string[] args)`
  - Understanding the traditional structure is essential for libraries and larger projects
  - File-scoped namespaces (C# 10): `namespace MyApp;` (no braces, applies to entire file)

#### § 0.3.3 — .NET Conventions
  - `PascalCase` for: classes, methods, properties, events, namespaces, public fields
  - `camelCase` for: parameters, local variables
  - `_camelCase` for: private fields (underscore prefix)
  - `IPascalCase` for interfaces (prefix with `I`)
  - `TPascalCase` for type parameters (prefix with `T`)
  - No Hungarian notation, no `m_` prefixes

> ### 🛠️ Phase 0 Project: **"Environment Inspector"**
> Write a C# program that prints:
> - .NET runtime version, OS description, architecture, process info
> - CLR version, number of processors, machine name
> - All environment variables
> - Available memory, current directory, user name
> - List all installed .NET SDKs and runtimes (via `dotnet --list-sdks` subprocess)
> - Create it using the CLI (`dotnet new console`), run it, publish it as a self-contained executable for your platform, and run the published binary directly

---

## ⚡ PHASE 1 — C# LANGUAGE FUNDAMENTALS
> *"C# is statically typed but feels dynamic. Strongly typed but feels lightweight."*

---

### 📦 Module 1.1: Data Types & Variables

#### § 1.1.1 — Value Types vs Reference Types (Critical Distinction)
  - **Value types**: stored on stack (or inline), copied on assignment
    - Numeric: `byte`, `short`, `int`, `long`, `float`, `double`, `decimal`
    - `char`, `bool`
    - `struct`, `enum`
    - Nullable value types: `int?`, `bool?`
  - **Reference types**: stored on heap, variable holds a reference
    - `string`, `object`, `dynamic`
    - `class`, `interface`, `delegate`, `array`
    - `record` (reference type), `record struct` (value type)
  - Default values: value types get `0`/`false`, reference types get `null`
  - `sizeof()` for value types
  - Boxing/unboxing: value type ↔ object (avoid in performance-critical code)

#### § 1.1.2 — Numeric Types
  - Integer: `byte` (8-bit), `short` (16), `int` (32), `long` (64)
  - Unsigned: `sbyte`, `ushort`, `uint`, `ulong`
  - Floating: `float` (32-bit, suffix `f`), `double` (64-bit, default)
  - `decimal` (128-bit, suffix `m`) — exact decimal arithmetic (financial)
  - `nint`, `nuint` — native-sized integers (pointer-sized)
  - Numeric literals: `1_000_000`, `0xFF`, `0b1010`
  - `checked` / `unchecked` — overflow behavior control

#### § 1.1.3 — Strings
  - `string` — immutable, UTF-16 encoded, reference type (but behaves like value type)
  - String interpolation: `$"Hello, {name}! {2 + 2}"`
  - Verbatim strings: `@"C:\Users\no\escape"` (no escape sequences)
  - Raw string literals (C# 11): `"""raw "content" here"""`
  - Interpolated + verbatim: `$@"Path: {path}\file"`
  - Common methods: `Length`, `Substring`, `Contains`, `IndexOf`, `Replace`, `Split`, `Trim`, `ToUpper`, `ToLower`, `StartsWith`, `EndsWith`, `Join`
  - `string.IsNullOrEmpty()`, `string.IsNullOrWhiteSpace()`
  - `StringBuilder` — mutable, efficient concatenation
  - String comparison: `StringComparison.Ordinal` vs `OrdinalIgnoreCase` vs `CurrentCulture`
  - `==` on strings compares VALUE (unlike Java)
  - `char` — single UTF-16 character, value type

#### § 1.1.4 — Boolean & Special Types
  - `bool` — `true` / `false` (no implicit conversion from int!)
  - `object` — base type of everything (boxing for value types)
  - `dynamic` — bypass static typing (resolved at runtime, uses DLR)
  - `var` — compiler-inferred type (static — type is fixed at compile time)

#### § 1.1.5 — Constants & Read-Only
  - `const` — compile-time constant (inlined at usage, must be known at compile time)
  - `readonly` — runtime constant (set in declaration or constructor)
  - `static readonly` — class-level runtime constant
  - `const` vs `readonly`: const is faster but more limited

---

### 📦 Module 1.2: Operators

#### § 1.2.1 — Arithmetic & Assignment
  - `+`, `-`, `*`, `/`, `%`
  - `+=`, `-=`, `*=`, `/=`, `%=`
  - `++`, `--` (prefix and postfix)
  - Integer division truncates: `7 / 2 == 3`
  - No power operator — use `Math.Pow()`

#### § 1.2.2 — Comparison & Logical
  - `==`, `!=`, `<`, `>`, `<=`, `>=`
  - `&&` (short-circuit AND), `||` (short-circuit OR), `!` (NOT)
  - `&`, `|` — non-short-circuit logical

#### § 1.2.3 — Null-Related Operators (C# Power Feature)
  - `?.` — null-conditional (safe navigation): `person?.Address?.City`
  - `?[]` — null-conditional indexer: `array?[0]`
  - `??` — null-coalescing: `name ?? "Unknown"` (return left if not null, else right)
  - `??=` — null-coalescing assignment: `name ??= "Default"` (assign only if null)
  - `!` — null-forgiving operator: `value!` (trust me, it's not null)

#### § 1.2.4 — Bitwise & Other
  - `&`, `|`, `^`, `~`, `<<`, `>>`, `>>>` (unsigned right shift)
  - `is` — type checking: `if (obj is string s)` (with pattern)
  - `as` — safe cast: `var s = obj as string;` (returns null if cast fails)
  - `typeof()` — get `Type` object at compile time
  - `nameof()` — get name as string: `nameof(variable)` → `"variable"`
  - `sizeof()` — size of value type
  - Ternary: `condition ? valueIfTrue : valueIfFalse`

---

### 📦 Module 1.3: Control Flow

#### § 1.3.1 — Conditional Statements
  - `if`, `else if`, `else`
  - `switch` statement — traditional with `break`
  - **Switch expressions** (C# 8+): `var result = x switch { 1 => "one", 2 => "two", _ => "other" };`
  - Pattern matching in switch (deep dive in Phase 4)

#### § 1.3.2 — Loops
  - `for (int i = 0; i < n; i++)`
  - `foreach (var item in collection)` — iterate over any `IEnumerable`
  - `while (condition)`
  - `do { ... } while (condition)`
  - `break`, `continue`
  - No labeled break/continue (unlike Java)

#### § 1.3.3 — Exception Basics (Detailed in Phase 5)
  - `try`, `catch`, `finally`, `throw`
  - `using` statement — deterministic resource disposal (RAII-like)
  - `using` declaration (C# 8+): `using var file = File.OpenRead(path);` (no braces needed)

---

### 📦 Module 1.4: Arrays & Spans

#### § 1.4.1 — Arrays
  - Single-dimensional: `int[] arr = new int[5];`, `int[] arr = {1, 2, 3};`
  - Multi-dimensional: `int[,] matrix = new int[3, 4];` (rectangular)
  - Jagged: `int[][] jagged = new int[3][];` (array of arrays)
  - `Array.Sort()`, `Array.Reverse()`, `Array.IndexOf()`, `Array.Find()`, `Array.Copy()`
  - `Array.Length`, `Array.Rank`
  - Collection expressions (C# 12): `int[] arr = [1, 2, 3];`

#### § 1.4.2 — `Span<T>` & `Memory<T>` (High-Performance)
  - `Span<T>` — stack-only view into contiguous memory (arrays, strings, native memory)
  - `ReadOnlySpan<T>` — read-only view
  - Slicing without allocation: `span.Slice(start, length)`, `span[1..3]`
  - `Memory<T>` — heap-safe version of Span (can be stored in fields)
  - Use case: high-performance parsing, avoiding allocations
  - `string.AsSpan()` — zero-allocation string processing

#### § 1.4.3 — Ranges & Indices (C# 8+)
  - Index from end: `^1` (last element), `^2` (second to last)
  - Range: `1..4` (elements 1 to 3), `..3` (first 3), `2..` (from index 2)
  - Works on arrays, strings, `Span<T>`

> ### 🛠️ Phase 1 Project: **"Calculator & Converter Suite"**
> Build a CLI calculator application:
> - Standard calculator: `+`, `-`, `*`, `/`, `%`, `^` (power) with proper operator precedence
> - Unit converter: temperature, distance, weight, data sizes, currency (static rates)
> - String analyzer: input a string, output length, word count, character frequency, reversed, palindrome check
> - Use switch expressions for menu navigation
> - Use null-coalescing for default values
> - Use string interpolation and raw string literals for formatted output
> - Use `Span<char>` for at least one string processing operation
> - Use `checked` blocks for overflow detection
> - Handle all invalid inputs gracefully with try/catch

---

## ⚡ PHASE 2 — METHODS, STRUCTURES & ENUMS
> *"C# gives you structs, records, classes, enums, tuples — the right tool for every data shape."*

---

### 📦 Module 2.1: Methods — Deep Dive

#### § 2.1.1 — Method Fundamentals
  - Method signature: access modifier, return type, name, parameters
  - `void` methods — no return value
  - Expression-bodied methods (C# 6+): `int Double(int x) => x * 2;`
  - `static` methods — belong to the class, no instance needed

#### § 2.1.2 — Parameter Passing
  - **By value** (default): copy of the value/reference
  - **`ref`**: pass by reference — caller and callee share the same variable
  - **`out`**: like `ref` but variable must be assigned inside the method
  - `out var` (C# 7): `if (int.TryParse(s, out var result))`
  - **`in`**: pass by reference, read-only (no modification allowed)
  - **`params`**: variable-length parameter: `void Print(params string[] items)`
  - `params` with collection expressions (C# 13): `params ReadOnlySpan<int>`
  - Optional parameters: `void Greet(string name = "World")`
  - Named arguments: `Greet(name: "Alice")`

#### § 2.1.3 — `ref` Returns & `ref` Locals (C# 7+)
  - Returning a reference to a variable: `ref int Find(int[] arr, int target)`
  - `ref` locals: `ref var item = ref Find(arr, 5);`
  - Use case: high-performance scenarios, avoiding copies of large structs

#### § 2.1.4 — Local Functions (C# 7+)
  - Functions defined inside other functions
  - Can capture local variables (closure)
  - `static` local functions (C# 8+): cannot capture, better performance
  - Use case: helper logic that doesn't belong at class level, validators, recursive helpers

#### § 2.1.5 — Method Overloading
  - Same name, different parameter lists
  - Overload resolution: most specific match wins
  - Overloading vs optional parameters — tradeoffs

---

### 📦 Module 2.2: Tuples

#### § 2.2.1 — Value Tuples (C# 7+)
  - `(int X, string Name) result = (42, "Alice");`
  - Accessing: `result.X`, `result.Name`
  - Unnamed: `(int, string) pair = (1, "hello");` → `pair.Item1`, `pair.Item2`
  - Multiple return values: `(int Min, int Max) FindRange(int[] arr)`
  - Deconstruction: `var (min, max) = FindRange(arr);`
  - Discards: `var (_, max) = FindRange(arr);` — ignore unwanted values
  - Tuples are value types — no heap allocation

#### § 2.2.2 — Deconstruction
  - Tuple deconstruction: `var (x, y) = point;`
  - Custom deconstruction: `public void Deconstruct(out int x, out int y)`
  - Any type can be deconstructable by adding `Deconstruct` methods

---

### 📦 Module 2.3: Enums

#### § 2.3.1 — Enum Fundamentals
  - `enum Direction { North, South, East, West }`
  - Underlying type: `int` by default, customizable: `enum Status : byte`
  - Explicit values: `enum HttpStatus { OK = 200, NotFound = 404 }`
  - `[Flags]` attribute for bitwise enums: `[Flags] enum Permissions { Read = 1, Write = 2, Execute = 4 }`
  - Parsing: `Enum.Parse<Direction>("North")`, `Enum.TryParse`
  - `Enum.GetValues<Direction>()`, `Enum.GetNames<Direction>()`
  - `ToString()` — get string name
  - Bitwise operations with `[Flags]`: `var perms = Permissions.Read | Permissions.Write;`
  - `perms.HasFlag(Permissions.Read)` — check flag

---

### 📦 Module 2.4: Structs

#### § 2.4.1 — Struct Fundamentals
  - `struct Point { public int X; public int Y; }` — value type
  - Structs live on the stack (when local) — no heap allocation, no GC pressure
  - Default parameterless constructor initializes all fields to default
  - Parameterized constructors must initialize ALL fields (pre-C# 11)
  - Structs are copied on assignment (value semantics)
  - `readonly struct` (C# 7.2) — all fields are readonly, enables compiler optimizations
  - `ref struct` (C# 7.2) — stack-only, cannot be boxed, cannot be in classes/arrays (`Span<T>` is a `ref struct`)

#### § 2.4.2 — Record Structs (C# 10+)
  - `record struct Point(int X, int Y);` — value-type record
  - Combines value semantics with record features (auto `Equals`, `ToString`, `GetHashCode`)
  - `readonly record struct` — immutable value-type record
  - Use case: small, data-centric value types

#### § 2.4.3 — When to Use Struct vs Class
  - Struct: small (< ~16 bytes), immutable, short-lived, frequently allocated, value semantics
  - Class: larger, mutable, long-lived, identity matters, reference semantics
  - Struct gotchas: boxing when cast to interface, unexpected mutation with mutable structs
  - Always prefer `readonly struct` unless mutation is required

---

### 📦 Module 2.5: Namespaces & Usings

#### § 2.5.1 — Namespaces
  - `namespace MyCompany.MyProject.SubModule;` — file-scoped (C# 10+)
  - Organizing code logically
  - Matching namespaces to directory structure (convention)
  - Nested namespaces

#### § 2.5.2 — Using Directives
  - `using System.Collections.Generic;` — import namespace
  - `using static System.Math;` — import static members: `Sqrt(x)` instead of `Math.Sqrt(x)`
  - `using Alias = Full.Namespace.TypeName;` — type alias
  - `using FilePath = string;` — alias any type (C# 12)
  - `global using` (C# 10) — apply using to entire project
  - Implicit usings: common namespaces auto-imported when enabled

> ### 🛠️ Phase 2 Project: **"GeometryLib — A Value Types Library"**
> Build a geometry library emphasizing value types:
> - `readonly record struct Point2D(double X, double Y)` — with distance, midpoint methods
> - `readonly record struct Vector2D(double X, double Y)` — with add, scale, dot product, magnitude, normalize
> - `readonly record struct Color(byte R, byte G, byte B, byte A)` — with blend, lerp, hex conversion
> - `enum ShapeType { Circle, Rectangle, Triangle, Polygon }`
> - `[Flags] enum Quadrant { None = 0, I = 1, II = 2, III = 4, IV = 8, All = 15 }` — determine which quadrants a shape spans
> - Operator overloading on structs: `+`, `-`, `*`, `==`, implicit/explicit conversions
> - Deconstruction: `var (x, y) = point;`
> - Methods with `ref`, `in`, `out` parameters for performance
> - Use `Span<Point2D>` for batch operations
> - Return tuples for multi-value results: `(double Area, double Perimeter) Measure()`

---

## ⚡ PHASE 3 — OBJECT-ORIENTED PROGRAMMING
> *"C# has the most refined OOP system of any mainstream language."*

---

### 📦 Module 3.1: Classes — Deep Dive

#### § 3.1.1 — Class Definition & Members
  - Fields, properties, methods, constructors, destructors/finalizers
  - Access modifiers: `public`, `private`, `protected`, `internal`, `protected internal`, `private protected`
  - `internal` — accessible within the same assembly (project) — C#'s unique and powerful modifier
  - `file` (C# 11) — type visible only within the same file

#### § 3.1.2 — Properties
  - Auto-implemented: `public string Name { get; set; }`
  - Read-only auto: `public string Id { get; }` (set only in constructor)
  - `init`-only (C# 9+): `public string Name { get; init; }` (set in initializer, then immutable)
  - Computed property: `public double Area => Width * Height;` (expression-bodied)
  - Backing field: manual get/set with private field
  - `required` keyword (C# 11): `public required string Name { get; init; }` — must be set in object initializer
  - `field` keyword (C# 14): access auto-property backing field in getter/setter

#### § 3.1.3 — Constructors
  - Default constructor (compiler-generated if none defined)
  - Parameterized constructors
  - Constructor chaining: `this(args)` — call another constructor
  - Static constructors: `static ClassName() { ... }` — runs once per type
  - **Primary constructors** (C# 12): `class Person(string name, int age)` — parameters available throughout the class
  - Object initializer syntax: `new Person { Name = "Alice", Age = 30 }`

#### § 3.1.4 — Destructors & `IDisposable`
  - `~ClassName() { ... }` — finalizer (avoid! non-deterministic, performance cost)
  - `IDisposable` pattern: `Dispose()` for deterministic cleanup
  - `using` statement / declaration — auto-calls `Dispose()`
  - `IAsyncDisposable` — async cleanup: `await using var conn = ...;`
  - Implement `Dispose` pattern correctly: protected virtual `Dispose(bool disposing)`

#### § 3.1.5 — Static Members & Classes
  - `static` fields, properties, methods — shared across all instances
  - `static class` — cannot be instantiated, only static members (utility classes)
  - Extension methods must be in `static class` (covered in Module 3.5)

---

### 📦 Module 3.2: Inheritance & Polymorphism

#### § 3.2.1 — Inheritance
  - `class Dog : Animal { ... }` — single inheritance only
  - `base` keyword: access parent constructor, methods
  - `base(args)` — call parent constructor
  - Constructor call order: parent first, then child
  - All classes inherit from `object` implicitly

#### § 3.2.2 — Virtual Methods & Overriding
  - `virtual` keyword: method CAN be overridden
  - `override` keyword: method IS overriding a virtual method
  - `sealed override` — prevent further overriding
  - `new` keyword (method hiding): hides parent method (different from override — avoid)
  - `abstract` methods: no body, MUST be overridden in derived class
  - `abstract class` — cannot be instantiated, can have abstract and concrete methods

#### § 3.2.3 — Sealed Classes & Methods
  - `sealed class` — cannot be inherited (like `final` in Java)
  - `sealed override` — method cannot be overridden further
  - Sealed classes enable devirtualization (performance optimization by JIT)

#### § 3.2.4 — Polymorphism in Practice
  - Runtime polymorphism: `Animal a = new Dog(); a.Speak();` → calls `Dog.Speak()`
  - `is` operator with pattern: `if (animal is Dog d) { d.Fetch(); }`
  - `as` operator: `var dog = animal as Dog;` (null if cast fails)
  - Casting: `(Dog)animal` — throws `InvalidCastException` if wrong type

---

### 📦 Module 3.3: Interfaces

#### § 3.3.1 — Interface Fundamentals
  - `interface IShape { double Area(); }` — contract definition
  - A class can implement MULTIPLE interfaces: `class Circle : IShape, IDrawable`
  - Implicit implementation: `public double Area() { ... }`
  - Explicit implementation: `double IShape.Area() { ... }` — only accessible through interface reference
  - All interface members are implicitly `public` (before C# 8)

#### § 3.3.2 — Default Interface Methods (C# 8+)
  - Interfaces can have method bodies: `default` implementation
  - Implementing class can override or use default
  - Static methods in interfaces
  - Interface properties, events, indexers
  - Use case: evolving interfaces without breaking implementations

#### § 3.3.3 — Static Abstract Members in Interfaces (C# 11+)
  - `static abstract` methods in interfaces
  - Enables generic math: `T Add<T>(T a, T b) where T : IAdditionOperators<T, T, T>`
  - Factory pattern via interfaces: `static abstract T Create(string data);`
  - Foundation for .NET's generic math support

#### § 3.3.4 — Key .NET Interfaces
  - `IEnumerable<T>`, `IEnumerator<T>` — iteration
  - `IDisposable`, `IAsyncDisposable` — resource cleanup
  - `IComparable<T>` — natural ordering
  - `IEquatable<T>` — value equality
  - `ICloneable` — cloning (discouraged — ambiguous shallow/deep)
  - `IFormattable` — custom string formatting
  - `INotifyPropertyChanged` — data binding (WPF/MAUI)

---

### 📦 Module 3.4: Records (C# 9+)

#### § 3.4.1 — Record Classes
  - `record Person(string Name, int Age);` — positional record
  - Auto-generated: constructor, `Equals`, `GetHashCode`, `ToString`, `Deconstruct`, `with` expression
  - Value-based equality (unlike regular classes which use reference equality)
  - `with` expression for non-destructive mutation: `var older = person with { Age = 31 };`
  - Immutable by default (positional properties are `init`-only)
  - Records are reference types (live on heap)
  - Inheritance: records can inherit from other records

#### § 3.4.2 — Record Structs (C# 10+)
  - `record struct Point(int X, int Y);` — value-type record
  - `readonly record struct` — fully immutable value-type record
  - Same features as record class but value semantics

#### § 3.4.3 — Records vs Classes vs Structs — Decision Matrix
  - Record class: immutable data, value equality, reference semantics (DTOs, domain events)
  - Record struct: immutable data, value equality, value semantics (small data objects)
  - Class: mutable state, identity matters, behavior-rich objects
  - Struct: small, performance-critical value types

---

### 📦 Module 3.5: Extension Methods

#### § 3.5.1 — Defining & Using Extension Methods
  - `static class StringExtensions { public static bool IsEmail(this string s) { ... } }`
  - Calling: `"test@email.com".IsEmail()` — looks like an instance method
  - `this` keyword on the first parameter marks it as an extension
  - Can extend any type: classes, interfaces, structs, enums, even sealed types
  - LINQ is entirely built on extension methods
  - Cannot access private members of the extended type

#### § 3.5.2 — Extension Members (C# 14 Preview)
  - Extension properties, static methods, indexers (beyond just methods)
  - `implicit extension ClassName for TargetType { ... }`
  - Evolving feature — expanding the extension concept

---

### 📦 Module 3.6: Operator Overloading

#### § 3.6.1 — Overloadable Operators
  - Arithmetic: `+`, `-`, `*`, `/`, `%`
  - Comparison: `==`, `!=`, `<`, `>`, `<=`, `>=` (must be in pairs)
  - Unary: `+`, `-`, `!`, `~`, `++`, `--`, `true`, `false`
  - Implicit conversion: `public static implicit operator Celsius(double d)`
  - Explicit conversion: `public static explicit operator Fahrenheit(Celsius c)`
  - Operator overloading is `static`: `public static Point operator +(Point a, Point b)`

> ### 🛠️ Phase 3 Project: **"ShapeEngine — A Polymorphic Shape System"**
> Build a comprehensive shape system demonstrating all OOP features:
> - `interface IShape` — `Area`, `Perimeter`, custom `IFormattable` implementation
> - `interface IDrawable` — `Draw(ICanvas canvas)` with default interface method for ASCII drawing
> - `abstract class Shape` — base with common logic, position, color
> - Concrete classes: `Circle`, `Rectangle`, `Triangle`, `Polygon` (all sealed)
> - `record ShapeMetrics(double Area, double Perimeter, string Type)` — immutable result type
> - `record struct BoundingBox(Point2D Min, Point2D Max)` — value type bounding box
> - Operator overloading: `Shape + Shape` (combine into group), `Shape * double` (scale)
> - Extension methods: `IEnumerable<IShape>.TotalArea()`, `IShape.IsLargerThan(IShape other)`
> - `IDisposable` for canvas resources
> - Proper `IEquatable<T>` implementation on shapes
> - Use `required` and `init` properties where appropriate
> - Primary constructors on appropriate classes

---

## ⚡ PHASE 4 — GENERICS & PATTERN MATCHING
> *"Generics and pattern matching together make C# one of the most expressive typed languages."*

---

### 📦 Module 4.1: Generics

#### § 4.1.1 — Generic Classes & Methods
  - `class Stack<T> { ... }` — generic class
  - `T Max<T>(T a, T b) where T : IComparable<T>` — generic method
  - Type inference: compiler deduces `T` from arguments
  - Multiple type parameters: `class Dictionary<TKey, TValue>`

#### § 4.1.2 — Generic Constraints
  - `where T : struct` — value type
  - `where T : class` — reference type
  - `where T : class?` — nullable reference type
  - `where T : notnull` — non-nullable
  - `where T : new()` — has parameterless constructor
  - `where T : BaseClass` — inherits from specific class
  - `where T : IInterface` — implements specific interface
  - `where T : unmanaged` — unmanaged type (no references)
  - `where T : allows ref struct` (C# 13) — allow ref structs as type arguments
  - Multiple constraints: `where T : class, IComparable<T>, new()`

#### § 4.1.3 — Variance (Covariance & Contravariance)
  - **Covariance** (`out T`): `IEnumerable<Dog>` assignable to `IEnumerable<Animal>` (output only)
  - **Contravariance** (`in T`): `Action<Animal>` assignable to `Action<Dog>` (input only)
  - `IEnumerable<out T>` — covariant (read-only)
  - `IComparer<in T>` — contravariant (write/consume)
  - Only interfaces and delegates support variance

#### § 4.1.4 — Generic Math (C# 11+)
  - `INumber<T>`, `IAdditionOperators<T, T, T>`, `IMultiplyOperators<T, T, T>`
  - `static abstract` members in interfaces enable generic arithmetic
  - `T Sum<T>(IEnumerable<T> values) where T : INumber<T>`
  - Replaces the need for separate `int`, `double`, `decimal` method versions

---

### 📦 Module 4.2: Pattern Matching (C#'s Superpower)

#### § 4.2.1 — Type Patterns
  - `if (obj is string s)` — type check + cast + assign in one
  - `if (obj is not null)` — null check
  - `switch (obj) { case int i: ... case string s: ... }`

#### § 4.2.2 — Property Patterns (C# 8+)
  - `if (person is { Age: > 18, Name: "Alice" })` — match properties
  - Nested: `if (order is { Customer: { Country: "US" } })`
  - Extended property patterns (C# 10): `if (order is { Customer.Country: "US" })`

#### § 4.2.3 — Positional Patterns
  - Deconstruct + match: `if (point is (0, 0))` (matches origin)
  - `if (point is (var x, var y) when x == y)` — capture + guard

#### § 4.2.4 — Relational & Logical Patterns (C# 9+)
  - `case > 0 and < 100:` — relational patterns
  - `case not null:`, `case int or string:` — logical patterns
  - `case >= 'a' and <= 'z':` — character range
  - Combinators: `and`, `or`, `not`

#### § 4.2.5 — List Patterns (C# 11+)
  - `if (arr is [1, 2, 3])` — exact match
  - `if (arr is [1, .., 3])` — first and last
  - `if (arr is [var first, .. var rest])` — capture first and rest
  - `if (arr is [_, _, _])` — match length

#### § 4.2.6 — Switch Expressions (C# 8+)
  - `var description = shape switch { Circle c => $"Circle r={c.Radius}", Rectangle r => $"Rect {r.Width}x{r.Height}", _ => "Unknown" };`
  - Exhaustiveness checking: compiler warns if not all cases covered
  - Pattern combinators in switch arms
  - Guard clauses: `Circle c when c.Radius > 10 => "Large circle"`

---

### 📦 Module 4.3: Nullable Reference Types (C# 8+)

#### § 4.3.1 — Understanding Nullable References
  - Enabled: `<Nullable>enable</Nullable>` in `.csproj` (default in new projects)
  - `string` — non-nullable (compiler warns on possible null assignment)
  - `string?` — explicitly nullable
  - Compiler flow analysis: tracks null state through code
  - Annotations: `[NotNull]`, `[MaybeNull]`, `[NotNullWhen(true)]`, `[MemberNotNull]`

#### § 4.3.2 — Working with Nullable Types
  - Null guard: `ArgumentNullException.ThrowIfNull(param)`
  - Null-conditional: `obj?.Method()`
  - Null-coalescing: `value ?? default`
  - Null-forgiving: `value!` (suppress warning — use cautiously)
  - Pattern matching: `if (value is not null)` (preferred over `!= null`)

> ### 🛠️ Phase 4 Project: **"GenericCollections — A Type-Safe Collections Library"**
> Build a generic collections library with pattern matching:
> - `class Result<T, TError>` — Ok/Error discriminated union with pattern matching
> - `class Option<T>` — Some/None with Map, FlatMap, Filter, Match
> - `class TypedList<T>` — generic list with LINQ-like methods (Where, Select, Aggregate) using constraints
> - `class PriorityQueue<TPriority, TItem> where TPriority : IComparable<TPriority>` — generic priority queue
> - Generic math utility: `T Average<T>(IEnumerable<T> values) where T : INumber<T>`
> - Pattern matching showcase: `ProcessShape(IShape shape)` using type, property, relational, and list patterns
> - `Result<T>.Match(onOk, onError)` using switch expressions
> - Use nullable reference types throughout — zero nullable warnings
> - Variance demonstration: covariant `IReadOnlyList<out T>` usage

---

## ⚡ PHASE 5 — EXCEPTION HANDLING, EVENTS & DELEGATES
> *"Delegates are the foundation. Events are the pattern. Exceptions are the safety net."*

---

### 📦 Module 5.1: Exception Handling

#### § 5.1.1 — Exception Hierarchy
  - `System.Exception` — base class
    - `SystemException` — runtime errors
      - `NullReferenceException`, `IndexOutOfRangeException`, `InvalidCastException`
      - `ArgumentException` → `ArgumentNullException`, `ArgumentOutOfRangeException`
      - `InvalidOperationException`
      - `NotSupportedException`, `NotImplementedException`
      - `StackOverflowException` (uncatchable)
      - `OutOfMemoryException`
    - `ApplicationException` — deprecated, don't use
    - `IOException` → `FileNotFoundException`, `DirectoryNotFoundException`
    - `AggregateException` — wraps multiple exceptions (from Task)

#### § 5.1.2 — `try/catch/finally/when`
  - `catch (SpecificException ex) { ... }` — specific exceptions first
  - `catch (Exception ex) when (ex.Message.Contains("timeout"))` — exception filter (C# 6+)
  - `finally { ... }` — always executes
  - `throw;` — re-throw preserving stack trace
  - `throw ex;` — re-throw losing original stack trace (NEVER do this)
  - `throw new CustomException("msg", innerException)` — wrap with context

#### § 5.1.3 — Custom Exceptions
  - Inherit from `Exception`
  - Provide: default constructor, message constructor, message + inner exception constructor
  - Serialization constructor (for legacy scenarios)
  - Add custom properties: error codes, context data

#### § 5.1.4 — Exception Best Practices
  - Catch specific exceptions, not `Exception`
  - Use exception filters (`when`) instead of catch-then-rethrow
  - Never swallow exceptions silently
  - Use `ArgumentNullException.ThrowIfNull()` for argument validation
  - Don't use exceptions for flow control
  - `ExceptionDispatchInfo.Capture(ex).Throw()` — re-throw preserving stack trace in async code

---

### 📦 Module 5.2: Delegates

#### § 5.2.1 — Delegate Fundamentals
  - A delegate is a type-safe function pointer
  - Declaration: `delegate int MathOperation(int a, int b);`
  - Instantiation: `MathOperation add = (a, b) => a + b;`
  - Invocation: `int result = add(3, 4);`
  - Multicast delegates: `del1 + del2` — invoke multiple methods
  - `Invoke()`, `?.Invoke()` — null-safe invocation

#### § 5.2.2 — Built-in Delegate Types
  - `Action` — void return: `Action`, `Action<T>`, `Action<T1, T2>` (up to 16 params)
  - `Func` — with return: `Func<TResult>`, `Func<T, TResult>`, `Func<T1, T2, TResult>`
  - `Predicate<T>` — returns `bool`: `Predicate<string> isLong = s => s.Length > 10;`
  - Almost never need custom delegate types — use `Func`/`Action`

#### § 5.2.3 — Lambda Expressions
  - Expression lambda: `(int x) => x * 2`
  - Statement lambda: `(int x) => { var result = x * 2; return result; }`
  - Type inference: `x => x * 2`
  - Natural type for lambdas (C# 10): `var f = (int x) => x * 2;` (infers `Func<int, int>`)
  - Attributes on lambdas (C# 10): `var f = [Obsolete] (int x) => x * 2;`
  - Default parameter values in lambdas (C# 12): `var f = (int x = 5) => x * 2;`
  - Closures: capturing outer variables (captured by reference!)

---

### 📦 Module 5.3: Events

#### § 5.3.1 — Event Fundamentals
  - `event EventHandler<TEventArgs> OnDataReceived;`
  - Publisher-subscriber pattern built into the language
  - `event` keyword restricts access: subscribers can only `+=` and `-=` (not invoke directly)
  - `EventHandler<TEventArgs>` — standard delegate type for events
  - Custom `EventArgs` subclass for event data
  - Raising events: `OnDataReceived?.Invoke(this, new DataEventArgs(data));`
  - Subscribing: `publisher.OnDataReceived += HandleData;`
  - Unsubscribing: `publisher.OnDataReceived -= HandleData;` (prevents memory leaks!)

#### § 5.3.2 — Event Patterns
  - Standard .NET event pattern: `sender` + `EventArgs`
  - Weak event pattern: prevent memory leaks from event subscriptions
  - Event aggregator / message bus pattern
  - Events vs delegates: events enforce subscriber-only access

---

### 📦 Module 5.4: `IDisposable` & Resource Management

#### § 5.4.1 — The Dispose Pattern
  - `IDisposable` — interface with single `Dispose()` method
  - `using` statement: `using (var resource = new Resource()) { ... }`
  - `using` declaration (C# 8+): `using var resource = new Resource();`
  - `IAsyncDisposable` + `await using` for async cleanup
  - Implementing the full dispose pattern: `Dispose(bool disposing)`, `GC.SuppressFinalize`
  - When to implement `IDisposable`: file handles, database connections, network sockets, unmanaged resources
  - `SafeHandle` — preferred over raw finalizers

> ### 🛠️ Phase 5 Project: **"EventDriven Logger & Monitor"**
> Build an event-driven logging and monitoring system:
> - `class EventBus` — publish/subscribe with generic event types using delegates
> - Custom events: `LogEvent`, `MetricEvent`, `AlertEvent` with custom `EventArgs`
> - Event handlers: `ConsoleLogger`, `FileLogger`, `JsonLogger` (all `IDisposable`)
> - `FileLogger` uses proper `IDisposable` pattern with `using` declarations
> - Exception handling: wrap event handler calls in try/catch, log handler failures
> - Exception filters: `catch (IOException ex) when (ex.HResult == -2147024864)`
> - Custom exceptions: `LogWriteException`, `EventBusException` with inner exception chaining
> - Multicast delegates: one event triggers multiple handlers
> - Unsubscription on dispose: prevent memory leaks
> - Use `Func<T>` and `Action<T>` for configurable formatters and filters

---

## ⚡ PHASE 6 — COLLECTIONS & LINQ
> *"LINQ is C#'s crown jewel. No other language has anything quite like it."*

---

### 📦 Module 6.1: Collections Framework

#### § 6.1.1 — Generic Collections (`System.Collections.Generic`)
  - `List<T>` — dynamic array (the default collection)
  - `Dictionary<TKey, TValue>` — hash map
  - `HashSet<T>` — unique elements, O(1) lookup
  - `SortedSet<T>`, `SortedDictionary<TKey, TValue>` — red-black tree
  - `SortedList<TKey, TValue>` — sorted by key, array-backed
  - `Queue<T>`, `Stack<T>` — FIFO, LIFO
  - `PriorityQueue<TElement, TPriority>` (.NET 6+)
  - `LinkedList<T>` — doubly linked list (rarely needed)

#### § 6.1.2 — Immutable Collections (`System.Collections.Immutable`)
  - `ImmutableList<T>`, `ImmutableDictionary<TKey, TValue>`, `ImmutableHashSet<T>`
  - `ImmutableArray<T>` — high-performance immutable array
  - Builder pattern: `ImmutableList.CreateBuilder<T>()`
  - Thread-safe by nature (no synchronization needed)
  - Structural sharing for efficiency

#### § 6.1.3 — Frozen Collections (.NET 8+)
  - `FrozenDictionary<TKey, TValue>`, `FrozenSet<T>`
  - Optimized for read-heavy, never-modified scenarios
  - Created once from existing collection: `myDict.ToFrozenDictionary()`
  - Faster lookup than standard collections

#### § 6.1.4 — Concurrent Collections
  - `ConcurrentDictionary<TKey, TValue>` — thread-safe dictionary
  - `ConcurrentQueue<T>`, `ConcurrentStack<T>`, `ConcurrentBag<T>`
  - `BlockingCollection<T>` — producer-consumer
  - `Channel<T>` (.NET Core 3+) — modern async producer-consumer

#### § 6.1.5 — Collection Interfaces Hierarchy
  - `IEnumerable<T>` → `ICollection<T>` → `IList<T>`
  - `IReadOnlyList<T>`, `IReadOnlyCollection<T>`, `IReadOnlyDictionary<TKey, TValue>`
  - Accept the most general interface, return the most specific type
  - Prefer `IReadOnlyList<T>` over `IList<T>` for parameters when mutation isn't needed

#### § 6.1.6 — Collection Expressions (C# 12)
  - `List<int> list = [1, 2, 3];`
  - `int[] arr = [1, 2, 3];`
  - Spread: `int[] combined = [..first, ..second, 42];`
  - Works with any collection type that has a suitable `Create` method

---

### 📦 Module 6.2: LINQ — Language Integrated Query

#### § 6.2.1 — LINQ Fundamentals
  - Query any collection implementing `IEnumerable<T>`
  - **Method syntax** (preferred): `list.Where(x => x > 5).Select(x => x * 2)`
  - **Query syntax**: `from x in list where x > 5 select x * 2`
  - Deferred execution: query not executed until iterated (lazy!)
  - Immediate execution: `ToList()`, `ToArray()`, `Count()`, `First()` force execution

#### § 6.2.2 — Filtering & Projection
  - `Where(predicate)` — filter elements
  - `Select(transform)` — project/transform each element
  - `SelectMany(transform)` — flatten nested collections (like flatMap)
  - `OfType<T>()` — filter by type
  - `Cast<T>()` — cast all elements
  - `Distinct()`, `DistinctBy()` (.NET 6+)

#### § 6.2.3 — Ordering
  - `OrderBy(keySelector)`, `OrderByDescending(keySelector)`
  - `ThenBy()`, `ThenByDescending()` — secondary sort
  - `Reverse()`
  - `Order()`, `OrderDescending()` (.NET 7+) — sort by self

#### § 6.2.4 — Aggregation
  - `Count()`, `LongCount()`
  - `Sum()`, `Average()`, `Min()`, `Max()`
  - `MinBy()`, `MaxBy()` (.NET 6+) — element with min/max key
  - `Aggregate(seed, func)` — fold/reduce
  - `Any(predicate)`, `All(predicate)` — existence checks

#### § 6.2.5 — Element Access
  - `First()`, `FirstOrDefault()` — first element (or default if empty)
  - `Last()`, `LastOrDefault()`
  - `Single()`, `SingleOrDefault()` — exactly one element (throws if multiple)
  - `ElementAt()`, `ElementAtOrDefault()`
  - Default values: `FirstOrDefault(defaultValue)` (.NET 6+)

#### § 6.2.6 — Set Operations
  - `Union()`, `Intersect()`, `Except()`, `ExceptBy()` (.NET 6+)
  - `UnionBy()`, `IntersectBy()` (.NET 6+) — set operations with key selector
  - `Concat()` — concatenate two sequences
  - `Append()`, `Prepend()` — add elements

#### § 6.2.7 — Grouping & Joining
  - `GroupBy(keySelector)` — group elements by key → `IGrouping<TKey, TElement>`
  - `ToLookup(keySelector)` — eager grouping into `ILookup<TKey, TElement>`
  - `Join()` — inner join (like SQL)
  - `GroupJoin()` — left outer join
  - `Zip(other)` — pair elements from two sequences
  - `Chunk(size)` (.NET 6+) — split into chunks

#### § 6.2.8 — Conversion & Materialization
  - `ToList()`, `ToArray()`, `ToDictionary()`, `ToHashSet()`
  - `ToFrozenDictionary()`, `ToFrozenSet()` (.NET 8+)
  - `ToImmutableList()`, `ToImmutableDictionary()`
  - `AsEnumerable()` — force local evaluation (LINQ to Objects)

#### § 6.2.9 — LINQ Performance Considerations
  - Deferred execution can cause multiple enumerations — materialize when needed
  - `Any()` vs `Count() > 0` — `Any()` is faster (short-circuits)
  - `FirstOrDefault()` vs `Where().First()` — equivalent, but clarity matters
  - Avoid LINQ in hot paths — manual loops can be faster
  - `Span<T>` and LINQ don't mix — use manual iteration for span

---

### 📦 Module 6.3: Iterators & `yield`

#### § 6.3.1 — Iterator Methods
  - `yield return value;` — produce next value lazily
  - `yield break;` — end iteration
  - Method returns `IEnumerable<T>` or `IAsyncEnumerable<T>`
  - State machine generated by compiler
  - Lazy evaluation: values produced on demand
  - Use case: reading large files, infinite sequences, custom collection traversal

#### § 6.3.2 — Async Iterators (C# 8+)
  - `async IAsyncEnumerable<T>` — async lazy sequences
  - `await foreach (var item in asyncSequence)` — async iteration
  - `[EnumeratorCancellation]` — propagate cancellation tokens
  - Use case: streaming data from database, API pagination

> ### 🛠️ Phase 6 Project: **"DataForge — A LINQ-Powered Analytics Engine"**
> Build a data analytics tool demonstrating LINQ mastery:
> - Load data from CSV into `List<SalesRecord>` (record type)
> - Queries (all LINQ method syntax):
>   1. Total revenue by category → `GroupBy` + `Sum`
>   2. Top 10 products by revenue → `OrderByDescending` + `Take`
>   3. Monthly revenue trend → `GroupBy` month + `Sum`
>   4. Customer lifetime value → `GroupBy` customer + `Aggregate`
>   5. Products above average price → `Where` + `Average`
>   6. Revenue per region per quarter → nested `GroupBy`
>   7. Year-over-year growth → `Zip` with previous year data
>   8. Outlier detection → statistical calculation with `Aggregate`
> - Custom LINQ-like extension methods: `Median()`, `StandardDeviation()`, `MovingAverage(int window)`
> - Iterator methods: `ReadCsvLazy(path)` using `yield return` for memory efficiency
> - Async iterator: `ReadCsvFromUrlAsync(url)` using `IAsyncEnumerable`
> - Process a 1M+ row dataset — prove constant memory usage with lazy evaluation
> - Collection expressions for test data setup

---

## ⚡ PHASE 7 — ASYNCHRONOUS PROGRAMMING
> *"C# pioneered async/await. Every other language's implementation is inspired by C#'s."*

---

### 📦 Module 7.1: Task-Based Asynchronous Pattern (TAP)

#### § 7.1.1 — `async` and `await` Fundamentals
  - `async Task<T>` — asynchronous method that returns a value
  - `async Task` — asynchronous method with no return value
  - `async ValueTask<T>` — lightweight task for hot-path (avoids allocation when result is cached)
  - `await` — suspend execution until task completes, resume on captured context
  - `await` is NOT blocking — it frees the thread
  - State machine: compiler transforms async method into a state machine

#### § 7.1.2 — The `Task` and `Task<T>` Types
  - `Task.Run(() => CpuBoundWork())` — offload CPU-bound work to thread pool
  - `Task.FromResult(value)` — wrap a value in a completed task
  - `Task.CompletedTask` — already completed task
  - `Task.Delay(milliseconds)` — async delay (don't use `Thread.Sleep`!)
  - `Task.WhenAll(tasks)` — wait for all tasks to complete
  - `Task.WhenAny(tasks)` — wait for first task to complete
  - `Task.WhenEach(tasks)` (.NET 9+) — process results as they complete
  - `task.Result` — blocking access (AVOID — can cause deadlocks!)
  - `task.GetAwaiter().GetResult()` — blocking (marginally better, still avoid)

#### § 7.1.3 — `ValueTask<T>` — High-Performance Async
  - Avoids `Task<T>` heap allocation when result is synchronously available
  - Rules: can only be awaited ONCE, cannot store or reuse
  - Use when: caching, fast-path optimization
  - Prefer `Task<T>` by default, upgrade to `ValueTask<T>` when profiling shows benefit

---

### 📦 Module 7.2: Async Patterns & Best Practices

#### § 7.2.1 — Async All the Way
  - Never mix sync and async: don't call `.Result` or `.Wait()` on async code
  - Async methods should call other async methods: `async` all the way up the call stack
  - `ConfigureAwait(false)` — don't capture synchronization context (library code should use this)
  - UI applications: `await` resumes on UI thread by default (captured context)

#### § 7.2.2 — Cancellation with `CancellationToken`
  - `CancellationTokenSource` — creates and controls the token
  - `CancellationToken` — passed to async methods
  - Checking: `token.ThrowIfCancellationRequested()`
  - Linking: `CancellationTokenSource.CreateLinkedTokenSource(token1, token2)`
  - Timeout: `new CancellationTokenSource(TimeSpan.FromSeconds(30))`
  - Every async method accepting I/O should accept `CancellationToken`

#### § 7.2.3 — Error Handling in Async Code
  - Exceptions in `async` methods are wrapped in `Task` (not thrown immediately)
  - `await` unwraps the exception — normal `try/catch` works
  - `AggregateException` from `Task.WhenAll` — contains multiple exceptions
  - `Task.Exception` — access exception without awaiting
  - Fire-and-forget: `_ = Task.Run(async () => { ... })` — handle errors inside!

#### § 7.2.4 — Common Async Pitfalls
  - Deadlock: calling `.Result` on a task that needs the current context
  - Thread pool starvation: blocking thread pool threads with sync calls
  - Async void: only for event handlers (exceptions can't be caught)
  - Over-parallelization: `Task.WhenAll` with thousands of HTTP calls → use `SemaphoreSlim`

---

### 📦 Module 7.3: Advanced Async Patterns

#### § 7.3.1 — `IAsyncEnumerable<T>` — Async Streams
  - `async IAsyncEnumerable<T>` — produce items asynchronously
  - `await foreach (var item in stream)` — consume asynchronously
  - Use case: database streaming, API pagination, real-time data
  - Cancellation: `[EnumeratorCancellation] CancellationToken token`

#### § 7.3.2 — Channels (`System.Threading.Channels`)
  - Modern async producer-consumer pattern
  - `Channel.CreateBounded<T>(capacity)` — bounded channel
  - `Channel.CreateUnbounded<T>()` — unbounded channel
  - Writer: `channel.Writer.WriteAsync(item)`
  - Reader: `await foreach (var item in channel.Reader.ReadAllAsync())`
  - Multiple producers, multiple consumers
  - Backpressure: bounded channels block writers when full

#### § 7.3.3 — `Parallel` & `Parallel.ForEachAsync`
  - `Parallel.For`, `Parallel.ForEach` — CPU-bound parallel loops
  - `Parallel.ForEachAsync` (.NET 6+) — async parallel processing with degree-of-parallelism
  - `ParallelOptions` — control max parallelism, cancellation

#### § 7.3.4 — `SemaphoreSlim` — Throttling Async Operations
  - Limit concurrent async operations
  - `await semaphore.WaitAsync()`
  - Use with `try/finally` to ensure release
  - Use case: limiting concurrent HTTP requests, database connections

---

### 📦 Module 7.4: Threading & Synchronization

#### § 7.4.1 — Thread Fundamentals
  - `Thread` class — low-level (rarely used directly now)
  - `ThreadPool` — managed pool of worker threads
  - `Task.Run` — preferred way to offload CPU-bound work
  - `lock` statement — mutual exclusion: `lock (lockObj) { ... }`
  - `Monitor` — underlying mechanism for `lock`
  - `SemaphoreSlim`, `Mutex`, `ReaderWriterLockSlim`

#### § 7.4.2 — Thread Safety
  - `Interlocked` — atomic operations: `Increment`, `Decrement`, `CompareExchange`
  - `volatile` keyword — ensure visibility across threads
  - `Lazy<T>` — thread-safe lazy initialization
  - `ThreadLocal<T>` — per-thread storage
  - Immutable types: inherently thread-safe

#### § 7.4.3 — `Lock` Type (.NET 9 / C# 13)
  - New dedicated `Lock` class — more efficient than `object` locking
  - `using (myLock.EnterScope()) { ... }` — scoped locking
  - Better than `lock (object)` — purpose-built, faster

> ### 🛠️ Phase 7 Project: **"AsyncPipeline — A Concurrent Data Processing System"**
> Build a concurrent data processing pipeline:
> - **Architecture**: Source → Transform → Enrich → Validate → Output (each stage is async)
> - **Channels**: connect pipeline stages with `Channel<T>`
> - **Producers**: file reader, HTTP API poller, random data generator (all `IAsyncEnumerable`)
> - **Workers**: configurable parallelism per stage using `SemaphoreSlim`
> - **Features**:
>   - Cancellation: `CancellationToken` propagation through entire pipeline
>   - Timeout: configurable per-stage timeout
>   - Error handling: failed items routed to error channel, processing continues
>   - Backpressure: bounded channels prevent memory overflow
>   - Progress reporting: items processed, throughput, errors per stage
> - **Async HTTP**: fetch data from multiple APIs concurrently with rate limiting
> - **`Parallel.ForEachAsync`**: CPU-bound transform stage
> - **Benchmark**: compare sequential vs pipeline vs fully parallel processing
> - `ValueTask` for hot-path optimization in cache layer

---

## ⚡ PHASE 8 — FILE I/O, SERIALIZATION & NETWORKING
> *".NET's I/O and networking stack is one of the fastest in any managed runtime."*

---

### 📦 Module 8.1: File I/O

#### § 8.1.1 — `System.IO` Fundamentals
  - `File` static class: `ReadAllText`, `ReadAllLines`, `ReadAllBytes`, `WriteAllText`, `WriteAllLines`
  - `File.ReadLinesAsync()` — async line-by-line reading
  - `StreamReader` / `StreamWriter` — text file I/O
  - `FileStream` — binary file I/O
  - `BinaryReader` / `BinaryWriter` — typed binary I/O
  - `BufferedStream` — buffered wrapper for any stream
  - Always use `using` / `await using` for streams

#### § 8.1.2 — `Path` & `Directory`
  - `Path.Combine()`, `Path.GetExtension()`, `Path.GetFileName()`, `Path.GetDirectoryName()`
  - `Path.GetTempPath()`, `Path.GetRandomFileName()`
  - `Directory.CreateDirectory()`, `Directory.GetFiles()`, `Directory.EnumerateFiles()` (lazy)
  - `Directory.EnumerateDirectories()`, `Directory.Exists()`
  - `FileInfo`, `DirectoryInfo` — instance-based file/dir info

#### § 8.1.3 — Async File I/O
  - `File.ReadAllTextAsync()`, `File.WriteAllTextAsync()`
  - `StreamReader.ReadLineAsync()`, `StreamWriter.WriteLineAsync()`
  - `FileStream` with `useAsync: true` flag

---

### 📦 Module 8.2: Serialization

#### § 8.2.1 — `System.Text.Json` (Standard)
  - `JsonSerializer.Serialize(obj)` — object → JSON string
  - `JsonSerializer.Deserialize<T>(json)` — JSON string → object
  - `JsonSerializerOptions`: camelCase, indented, ignore nulls
  - Attributes: `[JsonPropertyName]`, `[JsonIgnore]`, `[JsonInclude]`, `[JsonConstructor]`
  - Source generators (AOT-friendly): `[JsonSerializable(typeof(MyType))]`
  - Custom converters: `JsonConverter<T>`
  - Streaming: `JsonSerializer.SerializeAsync`, `DeserializeAsync`
  - JSON DOM: `JsonDocument`, `JsonElement` — read-only access
  - `JsonNode` — mutable JSON DOM (writable)

#### § 8.2.2 — Other Serialization Formats
  - `Newtonsoft.Json` (Json.NET) — legacy king (still widely used)
  - XML: `XmlSerializer`, `XDocument` (LINQ to XML), `XElement`
  - `MessagePack-CSharp` — fast binary serialization
  - `protobuf-net` — Protocol Buffers for .NET
  - YAML: `YamlDotNet`

---

### 📦 Module 8.3: HTTP Client

#### § 8.3.1 — `HttpClient`
  - `HttpClient` — the standard HTTP client
  - NEVER create `HttpClient` per request — use `IHttpClientFactory` or singleton
  - `GetAsync()`, `PostAsync()`, `PutAsync()`, `DeleteAsync()`
  - `GetStringAsync()`, `GetStreamAsync()`, `GetByteArrayAsync()`
  - `HttpRequestMessage` — full control over request
  - `HttpResponseMessage` — response with status, headers, body
  - `response.EnsureSuccessStatusCode()` — throw on non-2xx
  - Timeout: `client.Timeout = TimeSpan.FromSeconds(30)`
  - `IHttpClientFactory` — proper lifecycle management in DI

#### § 8.3.2 — HTTP Resilience
  - `Microsoft.Extensions.Http.Resilience` — retry, circuit breaker, timeout
  - Polly integration for resilience policies
  - `AddStandardResilienceHandler()` — one line for retry + circuit breaker + timeout

---

### 📦 Module 8.4: Networking

#### § 8.4.1 — TCP/UDP
  - `TcpClient`, `TcpListener` — TCP client/server
  - `UdpClient` — UDP communication
  - `NetworkStream` — stream over TCP connection
  - `Socket` — low-level socket API

#### § 8.4.2 — WebSockets
  - `ClientWebSocket` — built-in WebSocket client
  - SignalR — real-time communication framework (abstraction over WebSocket, SSE, long polling)

> ### 🛠️ Phase 8 Project: **"SecureVault — Encrypted File Storage"**
> Build an encrypted file storage system:
> - Watch a directory for new files using `FileSystemWatcher`
> - Encrypt files with AES-256-GCM using `System.Security.Cryptography`
> - Store metadata as JSON using `System.Text.Json` with source generators
> - REST API: expose file operations via `HttpClient` (upload, download, list, delete)
> - Async file I/O: all operations are async (`ReadAllBytesAsync`, `WriteAllBytesAsync`)
> - Hash verification: SHA-256 checksum for integrity
> - Streaming: support large files without loading entirely into memory
> - `IAsyncEnumerable` for listing files lazily
> - `Span<byte>` for zero-allocation encryption buffer management
> - `IDisposable` / `IAsyncDisposable` for all resource types

---

## ⚡ PHASE 9 — TESTING, TOOLING & CODE QUALITY
> *".NET's testing and tooling ecosystem is enterprise-grade."*

---

### 📦 Module 9.1: Unit Testing

#### § 9.1.1 — Testing Frameworks
  - **xUnit** — the modern standard (used by .NET team itself)
  - **NUnit** — mature, feature-rich
  - **MSTest** — Microsoft's built-in framework
  - xUnit conventions: `[Fact]` for single tests, `[Theory]` for parameterized
  - Test project: `dotnet new xunit -n MyProject.Tests`
  - Running: `dotnet test`

#### § 9.1.2 — xUnit Fundamentals
  - `[Fact]` — single test method
  - `[Theory]` + `[InlineData]` — parameterized tests
  - `[Theory]` + `[MemberData]` — data from method/property
  - `[Theory]` + `[ClassData]` — data from separate class
  - `Assert.Equal()`, `Assert.NotNull()`, `Assert.True()`, `Assert.Throws<T>()`
  - `Assert.Collection()`, `Assert.Contains()`, `Assert.Empty()`
  - Constructor / `IDisposable` for per-test setup/teardown
  - `IClassFixture<T>` — shared fixture across tests in a class
  - `ICollectionFixture<T>` — shared fixture across test classes

#### § 9.1.3 — FluentAssertions
  - `value.Should().Be(42);`
  - `list.Should().HaveCount(3).And.Contain(x => x > 0);`
  - `action.Should().Throw<InvalidOperationException>().WithMessage("...");`
  - `record.Should().BeEquivalentTo(expected);` — deep comparison
  - Much more readable than raw `Assert` calls

---

### 📦 Module 9.2: Mocking

#### § 9.2.1 — Moq (Most Popular)
  - `var mock = new Mock<IRepository>();`
  - `mock.Setup(r => r.GetById(1)).ReturnsAsync(entity);`
  - `mock.Verify(r => r.Save(It.IsAny<Entity>()), Times.Once);`
  - `mock.Object` — get the mocked instance
  - `It.Is<T>(predicate)` — argument matching
  - `CallBase` — call real implementation
  - Callbacks: `mock.Setup(...).Callback<T>(arg => { ... })`

#### § 9.2.2 — NSubstitute (Alternative)
  - `var sub = Substitute.For<IRepository>();`
  - `sub.GetById(1).Returns(entity);`
  - `sub.Received(1).Save(Arg.Any<Entity>());`
  - More natural syntax than Moq

#### § 9.2.3 — Testing Best Practices
  - AAA pattern: Arrange, Act, Assert
  - One assertion per test (or closely related assertions)
  - Test naming: `MethodName_Scenario_ExpectedResult`
  - Test doubles: mocks (verify behavior), stubs (return values), fakes (simplified implementations)
  - Interface-based design enables testability

---

### 📦 Module 9.3: Integration & Advanced Testing

#### § 9.3.1 — Integration Testing
  - `WebApplicationFactory<T>` — in-memory test server for ASP.NET Core
  - `Testcontainers.NET` — real databases in Docker
  - `Respawn` — database reset between tests
  - `WireMock.NET` — mock HTTP services

#### § 9.3.2 — Code Coverage
  - `dotnet test --collect:"XPlat Code Coverage"` — generate coverage
  - `coverlet` — cross-platform coverage tool
  - `ReportGenerator` — generate HTML coverage reports
  - Coverage in CI: Codecov, Coveralls

#### § 9.3.3 — Architecture Testing
  - `NetArchTest` — enforce architectural rules in tests
  - `ArchUnitNET` — port of Java's ArchUnit
  - Rule examples: "controllers should not depend on repositories directly"

#### § 9.3.4 — Benchmarking
  - `BenchmarkDotNet` — the gold standard for .NET benchmarks
  - `[Benchmark]` attribute
  - Memory diagnostics: allocation tracking
  - Multiple runtime comparison
  - Statistical analysis of results

---

### 📦 Module 9.4: Code Quality Tools

#### § 9.4.1 — Static Analysis
  - Roslyn analyzers: built-in compiler warnings/errors
  - `.editorconfig` — code style configuration
  - `dotnet format` — auto-format code
  - `StyleCop.Analyzers` — code style rules
  - `SonarAnalyzer.CSharp` — bug detection
  - `Roslynator` — extended analyzers and refactorings
  - `<TreatWarningsAsErrors>true</TreatWarningsAsErrors>` — zero-tolerance for warnings

#### § 9.4.2 — NuGet Package Management
  - `dotnet add package PackageName`
  - `Directory.Build.props` — shared configuration across projects
  - Central package management: `Directory.Packages.props`
  - `dotnet list package --outdated` — find outdated packages
  - `dotnet list package --vulnerable` — find vulnerable packages

> ### 🛠️ Phase 9 Project: **"TestSuite — Comprehensive Testing Showcase"**
> Take any previous project and add enterprise-grade testing:
> - xUnit test project with FluentAssertions
> - `[Theory]` + `[MemberData]` for parameterized tests
> - Moq for mocking all interfaces/dependencies
> - Integration tests with `WebApplicationFactory` and `Testcontainers`
> - Architecture tests with `NetArchTest`: enforce layer dependencies
> - BenchmarkDotNet benchmarks for performance-critical methods
> - 90%+ code coverage with `coverlet`
> - `.editorconfig` with strict rules
> - `Directory.Build.props` for shared settings
> - CI pipeline (GitHub Actions): build, test, coverage report, NuGet vulnerability check

---

## ⚡ PHASE 10 — DESIGN PATTERNS & SOLID PRINCIPLES
> *"C# was designed with design patterns in mind. Many patterns are built into the language itself."*

---

### 📦 Module 10.1: SOLID Principles in C#

#### § 10.1.1 — Single Responsibility Principle
  - One class, one reason to change
  - Separating concerns: validation, persistence, formatting, business logic
  - Small, focused classes and methods
  - C# tools: partial classes for organizing generated code, extension methods for adding behavior without modifying classes

#### § 10.1.2 — Open/Closed Principle
  - Open for extension, closed for modification
  - Achieved via: inheritance, interfaces, extension methods, generics, delegates
  - Pattern matching on sealed hierarchies (closed set, open behavior)

#### § 10.1.3 — Liskov Substitution Principle
  - Subtypes must be substitutable for base types
  - Covariant/contravariant interfaces support LSP
  - `sealed` classes prevent unwanted inheritance

#### § 10.1.4 — Interface Segregation Principle
  - Small, focused interfaces
  - C# interfaces with default methods allow growth without breaking
  - `IReadOnlyList<T>` vs `IList<T>` — expose minimum capability

#### § 10.1.5 — Dependency Inversion Principle
  - Depend on abstractions (interfaces), not concretions (classes)
  - Constructor injection is the standard approach in C# / .NET
  - Built-in DI container: `Microsoft.Extensions.DependencyInjection`
  - Service lifetimes: `Singleton`, `Scoped`, `Transient`

---

### 📦 Module 10.2: Creational Patterns

#### § 10.2.1 — Singleton Pattern
  - `Lazy<T>` — thread-safe lazy initialization
  - DI container singleton: `services.AddSingleton<IService, Service>()` — the C# way
  - Static readonly field initialization (thread-safe by CLR guarantee)
  - Anti-pattern warning: prefer DI over manual singletons

#### § 10.2.2 — Factory Method & Abstract Factory
  - Factory method: virtual method in base class, overridden in subclasses
  - Static factory methods: `TimeSpan.FromSeconds(30)`, `Task.FromResult(value)`
  - Abstract factory: interface that creates families of related objects
  - DI factory: `IServiceProvider`, `Func<T>` injection, `ActivatorUtilities`

#### § 10.2.3 — Builder Pattern
  - Fluent interface: `new QueryBuilder().Select("Name").From("Users").Where("Age > 18").Build()`
  - `StringBuilder` — built-in builder
  - `IHostBuilder`, `WebApplicationBuilder` — framework builders
  - Records with `with` expression reduce need for builders
  - Required properties (C# 11) as builder alternative

#### § 10.2.4 — Prototype Pattern
  - `ICloneable` — built-in (but ambiguous shallow/deep)
  - Records: `with` expression creates a modified copy
  - `MemberwiseClone()` — shallow copy
  - Custom deep clone methods

---

### 📦 Module 10.3: Structural Patterns

#### § 10.3.1 — Adapter Pattern
  - Wrapping incompatible interfaces
  - Extension methods as lightweight adapters
  - `Stream` adapters: `StreamReader(Stream)`, `CryptoStream(Stream, ...)`

#### § 10.3.2 — Decorator Pattern
  - Wrapping objects to add behavior
  - Stream decorators: `BufferedStream(FileStream)`, `GZipStream(Stream)`
  - DI decorators: `Scrutor` library for decorator registration
  - Middleware pipeline (ASP.NET Core) — decorator chain

#### § 10.3.3 — Facade Pattern
  - Simplified interface to complex subsystems
  - `HttpClient` as a facade over HTTP protocol complexity
  - Service layer pattern as a facade over business logic

#### § 10.3.4 — Proxy Pattern
  - `Lazy<T>` — lazy loading proxy
  - `DispatchProxy` — runtime proxy generation
  - Entity Framework lazy loading proxies
  - Castle.DynamicProxy — AOP proxying

#### § 10.3.5 — Composite Pattern
  - Tree structures with uniform interface
  - UI component hierarchies
  - Expression trees in LINQ

---

### 📦 Module 10.4: Behavioral Patterns

#### § 10.4.1 — Strategy Pattern
  - Interface with multiple implementations, injected via DI
  - `Func<T>` / `Action<T>` as lightweight strategies
  - `IComparer<T>` — sorting strategy
  - DI: register multiple implementations, resolve by key (.NET 8+: keyed services)

#### § 10.4.2 — Observer Pattern
  - Built into C#: `event` keyword + `EventHandler<T>`
  - `IObservable<T>` / `IObserver<T>` — reactive observer pattern
  - Reactive Extensions (Rx.NET) — full reactive programming
  - `MediatR` — mediator/observer pattern library (CQRS)

#### § 10.4.3 — Command Pattern
  - `ICommand` interface (WPF/MAUI)
  - `MediatR` — CQRS command/query pattern
  - `Func<Task>` / `Action` as lightweight commands
  - Undo/redo with command history

#### § 10.4.4 — State Machine Pattern
  - Enum-based state machines
  - `Stateless` library — lightweight state machine
  - Pattern matching switch expressions for state transitions

#### § 10.4.5 — Template Method Pattern
  - Abstract base class with `sealed` template method + `abstract`/`virtual` hook methods
  - `Stream` is a template method pattern: `Read` is abstract, `CopyTo` uses `Read`

#### § 10.4.6 — Chain of Responsibility
  - ASP.NET Core middleware pipeline — THE C# chain of responsibility
  - `DelegatingHandler` for HTTP pipeline
  - Custom pipeline builders

#### § 10.4.7 — Iterator Pattern
  - Built into C#: `IEnumerable<T>`, `foreach`, `yield return`
  - LINQ is the ultimate iterator pattern implementation

#### § 10.4.8 — Mediator Pattern
  - `MediatR` library — the standard in .NET
  - Decouples senders from receivers
  - Enables CQRS: separate command and query models
  - Pipeline behaviors: logging, validation, caching as cross-cutting concerns

#### § 10.4.9 — Visitor Pattern
  - Traditional double-dispatch visitor
  - Modern C# alternative: pattern matching with `switch` expressions on sealed hierarchies (preferred)

---

### 📦 Module 10.5: Architectural Patterns

#### § 10.5.1 — Repository Pattern
  - Abstract data access behind an interface
  - `IRepository<T>`: `GetByIdAsync`, `GetAllAsync`, `AddAsync`, `UpdateAsync`, `DeleteAsync`
  - Generic repository vs specific repositories — debate
  - Unit of Work pattern: `IUnitOfWork` coordinating multiple repositories

#### § 10.5.2 — CQRS (Command Query Responsibility Segregation)
  - Separate read and write models
  - `IRequest<TResponse>` — command/query (MediatR)
  - `IRequestHandler<TRequest, TResponse>` — handler
  - Pipeline behaviors for cross-cutting concerns
  - When CQRS adds value vs when it's over-engineering

#### § 10.5.3 — Clean Architecture
  - Domain layer: entities, value objects, domain events
  - Application layer: use cases, interfaces, DTOs
  - Infrastructure layer: EF Core, HTTP clients, file system
  - Presentation layer: API controllers, minimal APIs
  - Dependency rule: inner layers don't know about outer layers

#### § 10.5.4 — Vertical Slice Architecture (Alternative)
  - Organize by feature, not by layer
  - Each feature contains: request, handler, validator, endpoint
  - Less abstraction, more cohesion
  - Growing popularity as alternative to Clean Architecture

---

### 📦 Module 10.6: C#-Specific Anti-Patterns

#### § 10.6.1 — Common Anti-Patterns
  - Service Locator: resolving from `IServiceProvider` directly (use constructor injection)
  - Anemic Domain Model: entities with no behavior (just data bags)
  - God Class / God Controller: one class/controller doing everything
  - Async void: fire-and-forget without error handling (only for event handlers)
  - `.Result` / `.Wait()` on tasks: deadlock risk, thread pool starvation
  - Mutable shared state without synchronization
  - Over-abstraction: interfaces for everything, even when only one implementation exists

> ### 🛠️ Phase 10 Project: **"DesignShowcase — A Pattern-Rich Task Workflow Engine"**
> Build a workflow engine demonstrating C#-specific patterns:
>
> **Creational:**
> - Factory method for creating workflow steps from configuration
> - Builder pattern for constructing complex workflow definitions fluently
> - DI container for all service resolution (`Microsoft.Extensions.DependencyInjection`)
>
> **Structural:**
> - Decorator for adding logging, timing, retry to any workflow step
> - Adapter for integrating external notification systems
> - Composite for nested workflow groups (sequential, parallel)
>
> **Behavioral:**
> - Strategy for different execution policies (sequential, parallel, conditional)
> - Observer via events for workflow state change notifications
> - State machine for workflow lifecycle (Draft → Active → Paused → Completed → Failed)
> - Chain of responsibility for step validation pipeline
> - MediatR for command/query separation (CQRS)
> - Template method for common step execution framework
>
> **Architecture:**
> - Clean Architecture layers: Domain, Application, Infrastructure, API
> - Repository + Unit of Work pattern
> - CQRS with MediatR
> - Dependency injection throughout
> - Records for DTOs and value objects
> - Sealed class hierarchies with pattern matching

---

## ⚡ PHASE 11 — ASP.NET CORE & WEB DEVELOPMENT
> *"ASP.NET Core is one of the fastest web frameworks in any language — benchmarks prove it."*

---

### 📦 Module 11.1: ASP.NET Core Fundamentals

#### § 11.1.1 — Application Setup
  - `WebApplication.CreateBuilder(args)` — the entry point
  - `builder.Services` — configure DI container
  - `app.Map*` — configure HTTP pipeline
  - Middleware pipeline: request → middleware chain → endpoint → response
  - `app.UseRouting()`, `app.UseAuthentication()`, `app.UseAuthorization()`
  - Configuration: `appsettings.json`, environment variables, user secrets
  - `IOptions<T>`, `IOptionsSnapshot<T>`, `IOptionsMonitor<T>` — typed configuration

#### § 11.1.2 — Minimal APIs
  - `app.MapGet("/items/{id}", (int id) => ...)` — inline endpoint
  - Parameter binding: route, query, header, body (automatic)
  - `TypedResults.Ok()`, `TypedResults.NotFound()`, `TypedResults.Created()`
  - Filters: endpoint-specific middleware
  - Route groups: `app.MapGroup("/api/v1")`
  - OpenAPI support: `WithOpenApi()`, `WithName()`, `WithTags()`

#### § 11.1.3 — Controller-Based APIs
  - `[ApiController]` attribute — automatic model validation, binding source inference
  - `ControllerBase` — base class for API controllers
  - `[HttpGet]`, `[HttpPost]`, `[HttpPut]`, `[HttpDelete]`
  - `[FromRoute]`, `[FromQuery]`, `[FromBody]`, `[FromHeader]`
  - `ActionResult<T>` — typed return with HTTP status
  - `IActionResult` — untyped return

#### § 11.1.4 — Minimal APIs vs Controllers — When to Use Which
  - Minimal APIs: simpler endpoints, microservices, small APIs
  - Controllers: complex APIs, attribute routing, filters, heavy convention-based routing
  - Minimal APIs are the future direction of ASP.NET Core

---

### 📦 Module 11.2: Middleware & Pipeline

#### § 11.2.1 — Middleware Fundamentals
  - `app.Use(async (context, next) => { ... await next(); ... })` — inline middleware
  - `app.UseMiddleware<T>()` — class-based middleware
  - Middleware ordering matters: authentication before authorization
  - `app.Map()` — branch pipeline by path
  - Request/response pipeline: each middleware can short-circuit

#### § 11.2.2 — Built-in Middleware
  - `UseExceptionHandler` — global exception handling
  - `UseHttpsRedirection` — force HTTPS
  - `UseCors` — Cross-Origin Resource Sharing
  - `UseRateLimiter` (.NET 7+) — built-in rate limiting
  - `UseOutputCache` (.NET 7+) — response caching
  - `UseResponseCompression` — gzip/brotli compression
  - `UseStaticFiles` — serve static content

---

### 📦 Module 11.3: Data Access with Entity Framework Core

#### § 11.3.1 — EF Core Fundamentals
  - Code-First: define C# classes, generate database schema
  - `DbContext` — unit of work and repository combined
  - `DbSet<T>` — represents a table
  - Migrations: `dotnet ef migrations add InitialCreate`, `dotnet ef database update`
  - Configuration: Fluent API in `OnModelCreating` or data annotations
  - `SaveChangesAsync()` — persist changes

#### § 11.3.2 — Querying
  - LINQ to Entities: LINQ queries translated to SQL
  - Eager loading: `Include()`, `ThenInclude()`
  - Explicit loading: `Entry().Collection().LoadAsync()`
  - Lazy loading (opt-in, with proxies)
  - Projection: `Select()` — load only needed columns
  - Tracking vs no-tracking: `AsNoTracking()` for read-only queries
  - Raw SQL: `FromSqlRaw()`, `FromSqlInterpolated()`
  - Compiled queries: `EF.CompileAsyncQuery()` — pre-compiled for performance

#### § 11.3.3 — Advanced EF Core
  - Transactions: `using var transaction = await db.Database.BeginTransactionAsync()`
  - Concurrency: `[ConcurrencyCheck]`, `[Timestamp]`
  - Value objects: `OwnsOne()`, `ComplexProperty()` (.NET 8+)
  - Global query filters: `HasQueryFilter(e => !e.IsDeleted)` (soft delete)
  - Interceptors: `SaveChangesInterceptor`, `DbCommandInterceptor`
  - Shadow properties, value converters, table splitting

#### § 11.3.4 — Alternatives to EF Core
  - **Dapper** — micro-ORM, raw SQL with mapping (fastest)
  - **RepoDB** — hybrid ORM
  - Raw `ADO.NET` — maximum control
  - When to use EF Core vs Dapper vs raw SQL

---

### 📦 Module 11.4: Authentication & Authorization

#### § 11.4.1 — ASP.NET Core Identity
  - Built-in user management: registration, login, roles, claims
  - `UserManager<T>`, `SignInManager<T>`, `RoleManager<T>`
  - Password hashing, account lockout, email confirmation

#### § 11.4.2 — JWT Authentication
  - `AddAuthentication().AddJwtBearer()` — configure JWT
  - Token generation: `JwtSecurityTokenHandler`
  - Claims-based identity: `ClaimsPrincipal`, `Claim`
  - Refresh tokens, token revocation

#### § 11.4.3 — Authorization
  - `[Authorize]` — require authentication
  - `[Authorize(Roles = "Admin")]` — role-based
  - `[Authorize(Policy = "MinAge18")]` — policy-based
  - Custom `IAuthorizationHandler` — complex authorization logic
  - Resource-based authorization: `IAuthorizationService`

---

### 📦 Module 11.5: Real-Time Communication

#### § 11.5.1 — SignalR
  - Real-time bidirectional communication
  - Hub-based architecture: `Hub<T>` with strongly-typed methods
  - Client methods, server methods, groups, users
  - Automatic protocol negotiation: WebSocket, SSE, long polling
  - Scaling: Redis backplane, Azure SignalR Service

---

### 📦 Module 11.6: API Documentation & Versioning

#### § 11.6.1 — OpenAPI & Swagger
  - `Swashbuckle` — OpenAPI document generation
  - Built-in OpenAPI support (.NET 9+)
  - `[ProducesResponseType]` — document response types
  - XML comments → API docs

#### § 11.6.2 — API Versioning
  - `Asp.Versioning.Http` — official versioning package
  - URL segment, query string, header, media type versioning
  - Deprecated version marking

> ### 🛠️ Phase 11 Project: **"TaskBoard API — A Production-Grade REST API"**
> Build a complete project management API:
> - **Stack**: ASP.NET Core Minimal APIs + EF Core + PostgreSQL + JWT auth
> - **Entities**: User, Board, Column, Card, Comment, Label, Attachment
> - **Features**:
>   - JWT authentication with refresh tokens
>   - Role-based authorization (Admin, Member, Viewer)
>   - CRUD for all entities with proper authorization
>   - Card drag-and-drop ordering (position management)
>   - Filtering, sorting, pagination (cursor-based)
>   - File upload/download for attachments
>   - Real-time updates via SignalR (card moved, comment added)
>   - Rate limiting per user
>   - Output caching for read-heavy endpoints
> - **Architecture**:
>   - Clean Architecture with MediatR (CQRS)
>   - Repository + Unit of Work pattern
>   - FluentValidation for request validation
>   - Global exception handling middleware
>   - Typed configuration with `IOptions<T>`
>   - EF Core migrations with seed data
> - **Quality**:
>   - xUnit + FluentAssertions + Moq
>   - Integration tests with `WebApplicationFactory` + Testcontainers
>   - 85%+ coverage
>   - OpenAPI documentation
>   - Docker + docker-compose

---

## ⚡ PHASE 12 — ADVANCED .NET, PERFORMANCE & PRODUCTION
> *"This is where you become a .NET engineer, not just a C# developer."*

---

### 📦 Module 12.1: Performance & Memory

#### § 12.1.1 — Memory Management Deep Dive
  - GC generations: Gen 0 (short-lived), Gen 1 (medium), Gen 2 (long-lived), LOH (Large Object Heap)
  - GC modes: Workstation vs Server, Concurrent vs Background
  - `GC.Collect()` — manual GC (almost never do this)
  - `GC.GetTotalMemory()`, `GC.GetGCMemoryInfo()`
  - Pinned Object Heap (POH) — .NET 5+
  - `struct` vs `class` for allocation pressure
  - Object pooling: `ObjectPool<T>` (Microsoft.Extensions.ObjectPool)
  - `ArrayPool<T>.Shared` — rent and return arrays without allocation

#### § 12.1.2 — High-Performance Techniques
  - `Span<T>`, `ReadOnlySpan<T>` — zero-allocation slicing
  - `stackalloc` — allocate on stack: `Span<int> buffer = stackalloc int[100];`
  - `ref struct` — stack-only types
  - `IBufferWriter<T>`, `ReadOnlySequence<T>` — high-performance I/O (System.IO.Pipelines)
  - String interning: `string.Intern()`
  - `SearchValues<T>` (.NET 8+) — SIMD-accelerated search
  - `FrozenDictionary`, `FrozenSet` — read-optimized collections
  - `CompositeFormat` (.NET 8+) — pre-parsed format strings

#### § 12.1.3 — Profiling & Diagnostics
  - **BenchmarkDotNet** — microbenchmarking
  - **dotnet-trace** — collect traces
  - **dotnet-dump** — analyze dumps
  - **dotnet-counters** — real-time performance counters
  - **dotnet-monitor** — production diagnostics
  - Visual Studio Profiler / JetBrains dotMemory / dotTrace
  - ETW events, `EventSource`, `DiagnosticSource`
  - `Activity` API — distributed tracing

---

### 📦 Module 12.2: .NET Internals

#### § 12.2.1 — CLR Deep Dive
  - JIT compilation: method-by-method, tiered compilation
  - Tiered compilation: Tier 0 (quick), Tier 1 (optimized after profiling)
  - ReadyToRun (R2R) — pre-compiled assemblies for faster startup
  - Native AOT (.NET 7+) — compile to native binary (no JIT, no runtime)
  - GC internals: mark-sweep-compact, generational, concurrent

#### § 12.2.2 — Source Generators
  - Roslyn source generators: generate code at compile time
  - `[Generator]` attribute
  - `IIncrementalGenerator` interface
  - Use cases: JSON serialization, DI registration, boilerplate elimination, validation
  - Replacing runtime reflection with compile-time code generation

#### § 12.2.3 — Reflection
  - `typeof(T)`, `obj.GetType()` — get `Type` info
  - `Type.GetProperties()`, `Type.GetMethods()` — inspect members
  - `Activator.CreateInstance<T>()` — dynamic instantiation
  - Performance cost: reflection is slow — prefer source generators
  - `MethodInfo.Invoke()`, `PropertyInfo.GetValue()` / `SetValue()`
  - Custom attributes: `[AttributeUsage]`, `typeof(T).GetCustomAttributes()`

---

### 📦 Module 12.3: Microservices & Distributed Systems

#### § 12.3.1 — Microservices in .NET
  - ASP.NET Core as microservice host
  - gRPC: `Grpc.AspNetCore` — high-performance service-to-service
  - Message queues: RabbitMQ (`MassTransit`), Azure Service Bus, Apache Kafka
  - `MassTransit` — message bus abstraction (sagas, state machines, retry)
  - `Wolverine` — modern messaging framework

#### § 12.3.2 — Service Communication
  - `IHttpClientFactory` — managed HTTP client lifecycle
  - `Refit` — type-safe HTTP client from interface definitions
  - gRPC client/server with protobuf
  - Service discovery: Consul, DNS-based
  - API Gateway: YARP (Yet Another Reverse Proxy)

#### § 12.3.3 — Resilience
  - `Microsoft.Extensions.Http.Resilience` — built-in resilience
  - Polly v8: retry, circuit breaker, timeout, bulkhead, hedging
  - `AddStandardResilienceHandler()` — one line for production-grade resilience
  - Health checks: `AddHealthChecks()`, `/health` endpoint

---

### 📦 Module 12.4: Observability

#### § 12.4.1 — Logging
  - `ILogger<T>` — built-in structured logging
  - `LoggerMessage.Define` — high-performance source-generated logging
  - `[LoggerMessage]` attribute (.NET 6+) — source generator for log methods
  - Providers: Console, Debug, EventLog, Serilog, NLog, Seq
  - Serilog: structured logging with sinks (console, file, Elasticsearch, Seq)
  - Scopes: `using (logger.BeginScope("OrderId: {OrderId}", orderId))`

#### § 12.4.2 — Metrics & Tracing
  - `System.Diagnostics.Metrics` — built-in metrics API
  - OpenTelemetry SDK for .NET
  - Metrics: Counter, Histogram, Gauge
  - Distributed tracing: `Activity` API, `ActivitySource`
  - Export to: Prometheus, Grafana, Jaeger, Zipkin, Azure Monitor
  - ASP.NET Core instrumentation: automatic HTTP metrics and traces

#### § 12.4.3 — Health Checks
  - `AddHealthChecks()`, `MapHealthChecks("/health")`
  - Custom health checks: database connectivity, external service availability
  - `AspNetCore.HealthChecks.*` — pre-built checks for SQL, Redis, RabbitMQ, etc.
  - Readiness vs liveness probes

---

### 📦 Module 12.5: Containerization & Deployment

#### § 12.5.1 — Docker for .NET
  - Built-in container support (.NET 8+): `dotnet publish --os linux --arch x64 /t:PublishContainer`
  - Multi-stage Dockerfile: SDK image (build) → runtime image (production)
  - Base images: `mcr.microsoft.com/dotnet/aspnet:9.0` (runtime), `mcr.microsoft.com/dotnet/sdk:9.0` (build)
  - Alpine images for smaller size: `aspnet:9.0-alpine`
  - `chiseled` images (Ubuntu) — distroless, smallest possible .NET container
  - Native AOT in containers: smallest, fastest startup
  - `.dockerignore` — exclude `bin/`, `obj/`, `.git`
  - Docker Compose for local multi-service development

#### § 12.5.2 — Kubernetes for .NET
  - Health endpoints: `/health` (liveness), `/ready` (readiness), `/startup` (startup)
  - Graceful shutdown: `IHostApplicationLifetime.ApplicationStopping`
  - Configuration: environment variables, ConfigMaps, Secrets
  - `KubernetesClient` — .NET client for Kubernetes API
  - Helm charts for packaging .NET services
  - `Aspire` — .NET's cloud-native orchestration framework

#### § 12.5.3 — .NET Aspire (.NET 8+)
  - Opinionated stack for building observable, production-ready cloud-native apps
  - App model: define multi-service topology in code
  - Service defaults: OpenTelemetry, health checks, resilience pre-configured
  - Dashboard: built-in local development dashboard
  - Integrations: Redis, PostgreSQL, RabbitMQ, Azure services — one line each
  - `builder.AddProject<Projects.ApiService>("api")`
  - `builder.AddPostgres("db")`, `builder.AddRedis("cache")`
  - Deployment manifests: generate Kubernetes manifests or Azure Bicep

#### § 12.5.4 — CI/CD for .NET
  - GitHub Actions workflow: build → test → publish → deploy
  - `dotnet publish -c Release` — release build
  - Self-contained deployment: `--self-contained`
  - Framework-dependent deployment: smaller, requires .NET runtime on target
  - Native AOT: `PublishAot=true` — single native binary, no runtime dependency
  - Trimming: `PublishTrimmed=true` — remove unused code (reduce binary size)

---

### 📦 Module 12.6: Security

#### § 12.6.1 — Application Security
  - Input validation: FluentValidation, DataAnnotations, manual
  - SQL injection prevention: parameterized queries (EF Core handles this)
  - XSS prevention: Razor auto-encoding, `HtmlEncoder`
  - CSRF: anti-forgery tokens
  - CORS: `UseCors()` with explicit policy
  - Content Security Policy headers
  - HTTPS enforcement: `UseHttpsRedirection()`, `UseHsts()`

#### § 12.6.2 — Secrets Management
  - User Secrets (development): `dotnet user-secrets`
  - Azure Key Vault, AWS Secrets Manager, HashiCorp Vault
  - `IConfiguration` — unified access to secrets and config
  - Never store secrets in `appsettings.json` or source control

#### § 12.6.3 — Cryptography
  - `System.Security.Cryptography` — built-in crypto library
  - Hashing: `SHA256.HashData()`, `SHA512.HashData()`
  - Password hashing: `Rfc2898DeriveBytes` (PBKDF2), or use ASP.NET Core Identity
  - AES encryption: `Aes.Create()`
  - RSA: `RSA.Create()` — asymmetric encryption/signing
  - `RandomNumberGenerator.GetBytes()` — cryptographically secure random
  - Data protection API: `IDataProtector` — encrypt/decrypt application data

#### § 12.6.4 — Vulnerability Scanning
  - `dotnet list package --vulnerable` — NuGet vulnerability check
  - OWASP dependency check
  - GitHub Dependabot / Snyk for automated scanning
  - `SecurityCodeScan` — static analysis for security bugs

---

### 📦 Module 12.7: Specialized .NET Domains

#### § 12.7.1 — Background Services & Workers
  - `BackgroundService` / `IHostedService` — long-running background work
  - `Worker Service` template: `dotnet new worker`
  - Cron-like scheduling: Hangfire, Quartz.NET
  - `PeriodicTimer` — modern timer for background loops
  - Hosted services in ASP.NET Core: background processing alongside web API

#### § 12.7.2 — Desktop & Mobile
  - **WPF** — Windows desktop (XAML, MVVM, rich UI)
  - **WinUI 3** — modern Windows desktop
  - **.NET MAUI** — cross-platform mobile + desktop (iOS, Android, Windows, macOS)
  - **Avalonia** — cross-platform desktop UI (community, truly cross-platform)
  - **Blazor** — C# in the browser (WebAssembly) or server-side

#### § 12.7.3 — Game Development
  - **Unity** — the #1 game engine uses C# as scripting language
  - **Godot** — growing C# support
  - **MonoGame** — low-level 2D/3D framework
  - **Stride** — open-source C# game engine

#### § 12.7.4 — AI & Machine Learning
  - **ML.NET** — Microsoft's ML framework for .NET
  - **Semantic Kernel** — LLM orchestration framework (Microsoft)
  - **ONNX Runtime** — run ML models in .NET
  - **TorchSharp** — PyTorch bindings for .NET
  - `Microsoft.Extensions.AI` — unified AI abstractions

#### § 12.7.5 — Native AOT & Minimal Footprint
  - Ahead-of-Time compilation: `<PublishAot>true</PublishAot>`
  - No JIT, no IL, no runtime — pure native binary
  - Sub-millisecond startup (ideal for serverless, CLI tools, containers)
  - Limitations: no runtime reflection, no dynamic code generation
  - Source generators replace reflection for AOT compatibility
  - Trimming: `<PublishTrimmed>true</PublishTrimmed>` — tree-shaking for .NET

> ### 🛠️ Phase 12 Capstone Project: **"NexusCommerce — A Distributed E-Commerce Platform"**
> Build a production-grade distributed e-commerce system:
>
> - **Services**:
>   - `Identity.Api` — user registration, JWT authentication, role management
>   - `Catalog.Api` — product CRUD, categories, search (full-text)
>   - `Cart.Api` — shopping cart management (Redis-backed)
>   - `Order.Api` — order placement, status tracking, history
>   - `Payment.Api` — payment processing (mock Stripe integration)
>   - `Notification.Worker` — background service for email/SMS notifications
>   - `Gateway` — YARP reverse proxy / API gateway
>
> - **Communication**:
>   - Sync: gRPC between internal services
>   - Async: RabbitMQ via MassTransit (order events → payment → notification)
>   - Real-time: SignalR for order status updates
>
> - **Data**:
>   - PostgreSQL per service (EF Core, database-per-service pattern)
>   - Redis for cart caching and session management
>   - Each service has its own migrations
>
> - **Architecture**:
>   - Clean Architecture per service
>   - MediatR CQRS with pipeline behaviors (logging, validation, caching)
>   - Repository + Unit of Work
>   - Domain events for cross-aggregate communication
>   - Records for DTOs and value objects
>   - FluentValidation for all requests
>
> - **Resilience**:
>   - Polly v8 via `Microsoft.Extensions.Http.Resilience`
>   - Circuit breaker on inter-service HTTP/gRPC calls
>   - Retry with exponential backoff
>   - Rate limiting on public endpoints
>   - Health checks per service
>
> - **Observability**:
>   - Structured logging with Serilog → Seq or ELK
>   - OpenTelemetry: metrics + distributed tracing → Prometheus + Jaeger
>   - Custom metrics: orders/second, cart abandonment, payment success rate
>   - Grafana dashboards
>   - .NET Aspire dashboard for local development
>
> - **Quality**:
>   - xUnit + FluentAssertions + Moq per service
>   - Integration tests with `WebApplicationFactory` + Testcontainers
>   - Architecture tests with NetArchTest
>   - 80%+ coverage per service
>   - BenchmarkDotNet for critical paths
>
> - **Deployment**:
>   - Multi-stage Dockerfiles (chiseled/alpine base)
>   - Docker Compose: all services + PostgreSQL + Redis + RabbitMQ + Seq + Prometheus + Grafana + Jaeger
>   - .NET Aspire app model for orchestration
>   - Kubernetes manifests or Helm charts
>   - GitHub Actions CI/CD: build → test → coverage → Docker push
>   - OpenAPI docs per service

---

## 📊 PHASE MAP (Visual Summary)

```
Phase 0   ██░░░░░░░░░░░░░░░░  Environment & .NET Orientation
Phase 1   ███░░░░░░░░░░░░░░░  Language Fundamentals
Phase 2   █████░░░░░░░░░░░░░  Methods, Structs, Enums & Tuples
Phase 3   ██████░░░░░░░░░░░░  OOP (Classes, Interfaces, Records)
Phase 4   ████████░░░░░░░░░░  Generics & Pattern Matching
Phase 5   █████████░░░░░░░░░  Exceptions, Delegates, Events
Phase 6   ██████████░░░░░░░░  Collections & LINQ
Phase 7   ███████████░░░░░░░  Async/Await & Concurrency
Phase 8   ████████████░░░░░░  File I/O, Serialization & Networking
Phase 9   █████████████░░░░░  Testing, Tooling & Code Quality
Phase 10  ██████████████░░░░  Design Patterns & SOLID
Phase 11  ███████████████░░░  ASP.NET Core & Web Development
Phase 12  ████████████████░░  Advanced .NET, Performance & Production
```

---

## 🎯 DIFFICULTY & SKILL PROGRESSION

```
       BEGINNER              INTERMEDIATE              ADVANCED                 EXPERT
    ┌────────────┐        ┌────────────────┐       ┌──────────────┐       ┌──────────────┐
    │  Phase 0   │───────▶│    Phase 4     │──────▶│   Phase 7    │──────▶│   Phase 10   │
    │  Phase 1   │        │    Phase 5     │       │   Phase 8    │       │   Phase 11   │
    │  Phase 2   │        │    Phase 6     │       │   Phase 9    │       │   Phase 12   │
    │  Phase 3   │        │               │       │              │       │              │
    └────────────┘        └────────────────┘       └──────────────┘       └──────────────┘
    "I can write           "I use LINQ,             "I build tested,       "I architect
     C# programs           generics, async,         production-grade       distributed
     with OOP &            and delegates"           APIs with EF Core"     systems on
     records"                                                              .NET"
```

---

## 🎯 CERTIFICATION ALIGNMENT

| Phase | Certification / Credibility |
|-------|----------------------------|
| 0 – 6 | **Microsoft Certified: Foundational (AZ-900 + C#)** |
| 7 – 9 | **Microsoft Certified: Azure Developer Associate (AZ-204)** |
| 10 – 12 | **Microsoft Certified: Azure Solutions Architect Expert (AZ-305)** |
| 11 | **.NET Backend Developer interviews (FAANG-tier)** |
| ALL | **Open-source contributions** (ASP.NET Core, EF Core, Roslyn, Orleans) |

---

## 📚 RECOMMENDED RESOURCES

| Resource | Type | Phase |
|----------|------|-------|
| *C# 12 in a Nutshell* — Joseph Albahari | 📖 Book (Reference Bible) | ALL |
| *C# in Depth* — Jon Skeet (4th Ed.) | 📖 Book (MUST READ) | 2–10 |
| *Head First C#* — Andrew Stellman | 📖 Book (Beginner) | 0–4 |
| *Concurrency in C# Cookbook* — Stephen Cleary | 📖 Book | 7 |
| *Pro ASP.NET Core* — Adam Freeman | 📖 Book | 11 |
| *Entity Framework Core in Action* — Jon P Smith | 📖 Book | 11 |
| *Writing High-Performance .NET Code* — Ben Watson | 📖 Book | 12 |
| *CLR via C#* — Jeffrey Richter | 📖 Book (Internals) | 12 |
| *Dependency Injection in .NET* — Mark Seemann (2nd Ed.) | 📖 Book | 10–11 |
| *Clean Architecture* — Robert C. Martin | 📖 Book | 10 |
| *Domain-Driven Design* — Eric Evans | 📖 Book | 10 |
| **Microsoft Learn** (learn.microsoft.com) | 🌐 Official Tutorials | ALL |
| **docs.microsoft.com/dotnet** | 🌐 Official Docs | ALL |
| **Nick Chapsas** (YouTube) | 🎥 Video (Modern .NET) | 4–12 |
| **Raw Coding** (YouTube) | 🎥 Video (ASP.NET) | 7–11 |
| **IAmTimCorey** (YouTube) | 🎥 Video (Fundamentals) | 0–8 |
| **Zoran Horvat** (YouTube) | 🎥 Video (Patterns, OOP) | 3–10 |
| **Milan Jovanovic** (YouTube/Blog) | 🎥 Video (Clean Arch, Patterns) | 10–12 |
| **.NET Conf** (YouTube) | 🎥 Conference Talks | ALL |
| **Exercism — C# Track** | 🧪 Practice | 1–6 |
| **LeetCode** (C#) | 🧪 DSA Practice | 1–6 |
| **Sharplab.io** | 🧪 Tool (see IL, AST, lowered code) | 4–12 |
| **BenchmarkDotNet** | 🧪 Tool | 12 |

---

## 🗺️ WHERE C# TAKES YOU (Career Paths)

```
                                  ┌───────────────────────────┐
                                  │   Backend / API           │
                           ┌─────▶│   Engineering             │
                           │      │   (ASP.NET Core, gRPC,    │
                           │      │    Microservices)          │
                           │      └───────────────────────────┘
                           │      ┌───────────────────────────┐
                           │      │   Game Development        │
                   ┌───────┤─────▶│   (Unity, Godot,          │
                   │       │      │    MonoGame, Stride)       │
                   │       │      └───────────────────────────┘
                   │       │      ┌───────────────────────────┐
   ┌────────────┐  │       │      │   Cloud / Azure           │
   │            │  │       ├─────▶│   Engineering             │
   │  Master    ├──┤       │      │   (Azure Functions,       │
   │  C#        │  │       │      │    Service Bus, Cosmos DB) │
   │            │  │       │      └───────────────────────────┘
   └────────────┘  │       │      ┌───────────────────────────┐
                   │       │      │   Desktop & Mobile        │
                   │       ├─────▶│   (WPF, WinUI, MAUI,      │
                   │       │      │    Avalonia, Blazor)       │
                   │       │      └───────────────────────────┘
                   │       │      ┌───────────────────────────┐
                   │       │      │   Enterprise / Finance     │
                   │       ├─────▶│   (Banking, Insurance,     │
                   │       │      │    ERP, CRM Systems)       │
                   │       │      └───────────────────────────┘
                   │       │      ┌───────────────────────────┐
                   │       │      │   AI / ML / Data          │
                   └───────┴─────▶│   (ML.NET, Semantic Kernel,│
                                  │    ONNX, Data Pipelines)   │
                                  └───────────────────────────┘
```

---

> ### 💡 Final Advice
> **"C# is the language that keeps stealing the best features from every other language and integrating them seamlessly. It's perpetually modern."**
>
> Five non-negotiable rules for your C# journey:
>
> 1. **Read *C# in Depth* by Jon Skeet** — it's the definitive book on understanding WHY C# features exist and HOW they work under the hood. Every chapter will make you a better developer.
>
> 2. **Use the latest C# version — always** — unlike Java, C# evolves rapidly (yearly releases). Records, pattern matching, primary constructors, collection expressions, nullable reference types — these aren't optional luxuries, they're how modern C# is written. Don't write C# 6 code in 2026.
>
> 3. **Master LINQ — it's non-negotiable** — LINQ is to C# what list comprehensions are to Python, but more powerful. If you can't write a fluent LINQ pipeline instinctively, you're not a proficient C# developer. Use method syntax, understand deferred execution, know your operators.
>
> 4. **Understand async/await deeply** — C# invented the modern async/await pattern. Know the difference between `Task` and `ValueTask`, understand `ConfigureAwait`, know why `.Result` causes deadlocks, and always propagate `CancellationToken`. Async bugs are the hardest to debug.
>
> 5. **Watch Nick Chapsas on YouTube** — he covers every new .NET release, design patterns, performance techniques, and real-world architecture decisions. One video per day will keep you at the cutting edge of the .NET ecosystem.
>
> The difference between a *C# programmer* and a *.NET engineer* is:
> - **Knowing value types vs reference types and when each matters**
> - **Writing LINQ fluently**, **understanding the GC and allocation**
> - **Using records, pattern matching, and nullable references idiomatically**
> - **Building systems with proper DI, testing, observability, and resilience**
> - **Knowing the ecosystem**: EF Core, ASP.NET Core, MediatR, Polly, SignalR, Aspire
>
> C# gives you **enterprise power with modern elegance**. The roadmap above gives you the **discipline to wield both**.

---

*This roadmap takes you from "What's a `var`?" to "I can architect, build, test, and deploy a distributed microservices platform with gRPC, CQRS, observability, and resilience — all in modern, idiomatic C# on .NET."* 💜🚀