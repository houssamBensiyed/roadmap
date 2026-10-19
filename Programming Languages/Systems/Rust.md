# 🦀 THE ULTIMATE RUST ROADMAP
### From Zero to Systems Programming Mastery

> **Structure:** Phase → Modules → Sections
> **Estimated Duration:** ~9-14 Months (Dedicated Study)
> **Prerequisite:** None — starts from absolute zero
> *Rust is the hardest mainstream language to learn. It's also the most rewarding. The compiler is your strictest teacher — and your best friend.*

---

## ⚡ PHASE 0 — ENVIRONMENT SETUP & THE RUST PHILOSOPHY
> *"Rust doesn't trust you. And that's exactly why your code is correct."*

---

### 📦 Module 0.1: Understanding Rust's Identity

#### § 0.1.1 — What is Rust & Why It Exists
  - Created by Graydon Hoare at Mozilla (2010), 1.0 released in 2015
  - Now governed by the Rust Foundation (Mozilla, Google, Microsoft, Amazon, Huawei)
  - Born from frustration with C/C++ memory bugs (use-after-free, buffer overflows, data races)
  - The promise: **memory safety WITHOUT garbage collection**, concurrency WITHOUT data races, abstraction WITHOUT overhead
  - "Most loved programming language" on Stack Overflow for 8 consecutive years

#### § 0.1.2 — Where Rust Dominates
  - Systems programming: OS kernels (Linux kernel modules), drivers, firmware
  - Web infrastructure: Cloudflare, Fastly, Deno, Vercel (Turbopack)
  - CLI tools: `ripgrep`, `fd`, `bat`, `exa`, `delta`, `zoxide`, `starship`
  - Databases & storage: TiKV, SurrealDB, Qdrant, Meilisearch
  - Web browsers: Firefox (Servo), Chrome (some components)
  - Blockchain: Solana, Polkadot, Near Protocol
  - Game engines: Bevy
  - DevTools: `ruff` (Python linter), `Biome` (JS linter), `SWC` (JS compiler), `uv` (Python package manager)
  - Cloud/infra: Firecracker (AWS Lambda VMs), Bottlerocket (AWS container OS)

#### § 0.1.3 — Rust's Core Philosophy
  - **Zero-cost abstractions** — high-level constructs compile to the same code you'd write by hand
  - **Ownership and borrowing** — memory safety enforced at compile time (no GC, no runtime cost)
  - **Fearless concurrency** — data races are compile-time errors
  - **If it compiles, it works** — the compiler catches an extraordinary number of bugs
  - **Explicit over implicit** — no hidden allocations, no hidden copies, no hidden null
  - **No undefined behavior** — safe Rust cannot trigger UB (unlike C/C++)
  - **Community-driven** — RFC process, open governance, welcoming community

#### § 0.1.4 — Rust vs Other Languages
  - Rust vs C: memory safety, no UB in safe code, similar performance, steeper learning curve
  - Rust vs C++: ownership instead of RAII + raw pointers, no inheritance, no exceptions, no header files
  - Rust vs Go: no GC, more complex, more powerful type system, lower-level control, harder to learn
  - Rust vs Java/C#: no runtime, no GC, algebraic data types, pattern matching, no null
  - Rust vs Haskell: imperative style with functional features, ownership instead of purity, practical systems focus
  - Rust vs Zig: more mature ecosystem, safer by default, more complex, larger standard library

#### § 0.1.5 — Rust Edition System
  - **Rust 2015** — initial stable edition
  - **Rust 2018** — module system overhaul, `async`/`await` foundations, NLL (Non-Lexical Lifetimes)
  - **Rust 2021** — disjoint capture in closures, `IntoIterator` for arrays, new prelude
  - **Rust 2024** — `gen` blocks (experimental), lifetime capture rules, `unsafe_op_in_unsafe_fn`
  - Editions are opt-in per crate, all editions interoperate seamlessly
  - Release cadence: every 6 weeks (stable, beta, nightly channels)
  - Backward compatibility guarantee: code from any edition continues to compile

---

### 📦 Module 0.2: Setting Up the Development Environment

#### § 0.2.1 — Installing Rust with `rustup`
  - `rustup` — the official Rust toolchain manager
  - `curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh`
  - Components installed: `rustc` (compiler), `cargo` (build system + package manager), `rustfmt` (formatter), `clippy` (linter)
  - Verifying: `rustc --version`, `cargo --version`
  - Updating: `rustup update`
  - Toolchain management: `rustup default stable`, `rustup toolchain install nightly`
  - Adding targets for cross-compilation: `rustup target add wasm32-unknown-unknown`

#### § 0.2.2 — Editors & IDE Setup
  - **VS Code + rust-analyzer** — the most popular setup (excellent IntelliSense, inline type hints)
  - **RustRover** (JetBrains) — full IDE experience (free for non-commercial)
  - **Neovim + rust-analyzer** — lightweight, fast
  - **Zed** — modern editor written in Rust, native Rust support
  - **rust-analyzer** — the language server powering all editors (must-have)
  - Essential VS Code extensions: rust-analyzer, Even Better TOML, Error Lens, CodeLLDB (debugging)

#### § 0.2.3 — Cargo — The Build System & Package Manager
  - `cargo new project_name` — create a new project (binary)
  - `cargo new --lib library_name` — create a library project
  - `cargo build` — compile (debug mode)
  - `cargo build --release` — compile with optimizations
  - `cargo run` — compile and run
  - `cargo test` — run all tests
  - `cargo check` — type-check without compiling (faster feedback)
  - `cargo clippy` — run the linter
  - `cargo fmt` — format code
  - `cargo doc --open` — generate and view documentation
  - `cargo add crate_name` — add a dependency
  - `cargo update` — update dependencies

#### § 0.2.4 — Project Structure
  - `Cargo.toml` — project manifest (dependencies, metadata, features)
  - `Cargo.lock` — exact dependency versions (committed for binaries, not for libraries)
  - `src/main.rs` — binary entry point
  - `src/lib.rs` — library root
  - `src/bin/` — additional binaries
  - `tests/` — integration tests
  - `benches/` — benchmarks
  - `examples/` — example programs
  - `build.rs` — build script (optional)

#### § 0.2.5 — Essential Tooling
  - `cargo clippy` — the Rust linter (hundreds of lint rules, suggestions, and corrections)
  - `cargo fmt` / `rustfmt` — non-negotiable code formatting
  - `cargo doc` — documentation generation from doc comments
  - `cargo test` — built-in test runner
  - `cargo bench` — built-in benchmark runner
  - `rust-analyzer` — IDE intelligence
  - `miri` — experimental interpreter for detecting undefined behavior
  - `cargo-expand` — show expanded macros

---

### 📦 Module 0.3: Rust Culture & Community

#### § 0.3.1 — Learning Resources Ecosystem
  - "The Book" — *The Rust Programming Language* (the official book, free online)
  - "Rustlings" — small exercises to learn Rust syntax and concepts
  - Rust Playground — browser-based Rust compiler (play.rust-lang.org)
  - Rust by Example — learn through annotated examples
  - The Rustonomicon — the dark arts of unsafe Rust
  - Crates.io — the package registry (like npm, PyPI, Maven Central)
  - Docs.rs — auto-generated documentation for every crate

#### § 0.3.2 — The Rust Community Values
  - "Empathy, craft, and community" — Rust's unofficial motto
  - Welcoming to beginners (unusual for a systems language)
  - RFC process: every major feature is publicly discussed and reviewed
  - The Rust compiler error messages are famously helpful and educational
  - "Fighting the borrow checker" is normal for beginners — embrace it

> ### 🛠️ Phase 0 Project: **"Rust Environment Explorer"**
> Create a Rust program that prints:
> - Rust version, edition, target architecture
> - Cargo version, home directory
> - Number of available CPU cores, OS information
> - All environment variables
> - Build it in debug and release mode, compare binary sizes
> - Run `cargo clippy`, fix all warnings, run `cargo fmt`
> - Generate documentation with `cargo doc --open`
> - Add a dependency (e.g., `sysinfo` crate), observe `Cargo.lock` changes

---

## ⚡ PHASE 1 — RUST LANGUAGE FUNDAMENTALS
> *"Rust syntax looks familiar. Rust semantics will break your brain — in a good way."*

---

### 📦 Module 1.1: Variables, Mutability & Data Types

#### § 1.1.1 — Variables & Mutability
  - `let x = 5;` — immutable by default (this is a feature, not a limitation)
  - `let mut x = 5;` — explicitly mutable
  - Shadowing: `let x = x + 1;` — rebinding to a new value (can change type!)
  - Shadowing vs mutation: shadowing creates a NEW variable, mutation changes the existing one
  - `const MAX: u32 = 100;` — compile-time constant (must have explicit type)
  - `static` — global variable with a fixed memory address (rarely used)
  - `static mut` — mutable global (unsafe, avoid)

#### § 1.1.2 — Scalar Types
  - **Integers**: `i8`, `i16`, `i32`, `i64`, `i128`, `isize` (signed); `u8`, `u16`, `u32`, `u64`, `u128`, `usize` (unsigned)
  - `i32` is the default integer type
  - `isize` / `usize` — pointer-sized (used for indexing)
  - Integer overflow: panics in debug mode, wraps in release mode
  - Checked, wrapping, saturating, overflowing arithmetic methods
  - **Floating point**: `f32`, `f64` (default is `f64`)
  - **Boolean**: `bool` — `true`, `false`
  - **Character**: `char` — 4 bytes, Unicode scalar value (not just ASCII)
  - Numeric literals: `1_000_000`, `0xff`, `0o77`, `0b1010`, `b'A'` (byte)
  - Type suffixes: `42u8`, `3.14f32`

#### § 1.1.3 — Compound Types
  - **Tuples**: `let tup: (i32, f64, char) = (500, 6.4, 'z');`
  - Tuple access: `tup.0`, `tup.1`, `tup.2`
  - Tuple destructuring: `let (x, y, z) = tup;`
  - Unit type: `()` — empty tuple, similar to `void`
  - **Arrays**: `let arr: [i32; 5] = [1, 2, 3, 4, 5];`
  - Fixed-size, stack-allocated, same type
  - Array initialization: `[0; 10]` — 10 zeros
  - Array access: bounds-checked at runtime (panics on out-of-bounds)
  - Arrays vs vectors: arrays are fixed-size, vectors are dynamic

#### § 1.1.4 — Type Inference & Annotations
  - Rust has powerful type inference — annotate when the compiler can't deduce
  - Turbofish syntax: `"42".parse::<i32>()` — specify generic type inline
  - `_` placeholder: `let x: Vec<_> = vec![1, 2, 3];` — let compiler infer part of type

---

### 📦 Module 1.2: Functions

#### § 1.2.1 — Function Fundamentals
  - `fn function_name(param: Type) -> ReturnType { ... }`
  - Parameters MUST have explicit type annotations (no inference on function signatures)
  - Return type annotation: `-> Type` (omit for `()` return)
  - Last expression without semicolon is the return value (expression-based language)
  - `return` keyword for early returns (idiomatic: use expression-based returns when possible)

#### § 1.2.2 — Expressions vs Statements
  - Almost everything in Rust is an expression (has a value)
  - Statements: `let` bindings, `fn` definitions (no value)
  - Block expressions: `{ ... }` — last expression is the block's value
  - `if` is an expression: `let x = if condition { 1 } else { 2 };`
  - `match` is an expression: `let x = match value { ... };`
  - Semicolon turns an expression into a statement (discards the value)

#### § 1.2.3 — Closures (Introduction)
  - `|params| expression` — closure syntax
  - `|x| x + 1` — single expression
  - `|x: i32| -> i32 { x + 1 }` — with type annotations
  - Closures capture environment (by reference, by mutable reference, or by value)
  - Deep dive on closures in Phase 4

---

### 📦 Module 1.3: Control Flow

#### § 1.3.1 — Conditional Expressions
  - `if condition { ... } else if condition { ... } else { ... }`
  - Condition must be `bool` (no truthy/falsy — `if 1` is a compile error!)
  - `if` as expression: `let x = if cond { a } else { b };` — both branches must return same type
  - `let ... else` (Rust 1.65+): `let Some(x) = val else { return; };` — refutable patterns with divergence

#### § 1.3.2 — Loops
  - `loop { ... }` — infinite loop (with `break value` to return a value!)
  - `while condition { ... }` — conditional loop
  - `while let Some(x) = iter.next() { ... }` — loop with pattern matching
  - `for item in iterator { ... }` — iterator-based loop (most common)
  - `for i in 0..10` — range (exclusive end)
  - `for i in 0..=10` — range (inclusive end)
  - `for (i, val) in iter.enumerate()` — index + value
  - `break` — exit loop, `continue` — skip iteration
  - Labeled loops: `'outer: loop { ... break 'outer; }` — break/continue specific loop
  - `break value` — loops can return values!

#### § 1.3.3 — Pattern Matching with `match`
  - `match value { pattern => expression, ... }` — exhaustive pattern matching
  - Must handle ALL possible values (exhaustive)
  - Catch-all: `_` wildcard pattern
  - Multiple patterns: `1 | 2 | 3 => ...`
  - Range patterns: `1..=5 => ...`
  - Destructuring: match on struct/enum fields
  - Guards: `x if x > 5 => ...`
  - Binding: `x @ 1..=5 => ...` — bind matched value to a name
  - `match` is an expression — all arms must return the same type

#### § 1.3.4 — `if let` and `while let`
  - `if let Some(x) = optional_value { ... }` — match a single pattern
  - Syntactic sugar for `match` with one interesting arm
  - `while let Some(x) = stack.pop() { ... }` — loop while pattern matches
  - `if let ... else` chains (Rust 2024+)

---

### 📦 Module 1.4: Ownership — The Foundation of Rust

#### § 1.4.1 — Stack vs Heap
  - Stack: fixed-size data, fast (LIFO), automatically cleaned up
  - Heap: dynamic-size data, slower (allocation + pointer lookup)
  - Rust gives you control over where data lives — and FORCES you to manage it correctly

#### § 1.4.2 — Ownership Rules (Memorize These)
  - **Rule 1**: Each value in Rust has exactly ONE owner
  - **Rule 2**: When the owner goes out of scope, the value is dropped (freed)
  - **Rule 3**: There can only be ONE owner at a time
  - No garbage collector — ownership IS the memory management strategy
  - `Drop` trait: custom cleanup when value goes out of scope (like destructors)

#### § 1.4.3 — Move Semantics
  - Assignment of heap data MOVES ownership: `let s2 = s1;` — `s1` is invalid after this
  - This is NOT a copy — the original variable can no longer be used
  - Prevents double-free bugs at compile time
  - Stack data (types implementing `Copy` trait) are copied, not moved
  - `Copy` types: all scalar types, tuples of `Copy` types, `&T` references
  - `Clone` trait: explicit deep copy: `let s2 = s1.clone();`

#### § 1.4.4 — Ownership & Functions
  - Passing a value to a function MOVES ownership (for heap data)
  - Returning a value transfers ownership to the caller
  - Pattern: take ownership, do work, return ownership back — tedious!
  - Solution: references and borrowing (next module)

---

### 📦 Module 1.5: References & Borrowing

#### § 1.5.1 — Immutable References (`&T`)
  - `&value` — create a reference (borrow)
  - Does NOT take ownership — the original owner retains it
  - Multiple immutable references allowed simultaneously
  - Cannot modify data through an immutable reference

#### § 1.5.2 — Mutable References (`&mut T`)
  - `&mut value` — create a mutable reference
  - Can modify the borrowed data
  - **Only ONE mutable reference at a time** (prevents data races at compile time!)
  - Cannot have mutable AND immutable references at the same time
  - The borrow checker enforces these rules at compile time

#### § 1.5.3 — The Borrow Checker
  - Rust's compile-time analysis that enforces borrowing rules
  - Non-Lexical Lifetimes (NLL): references are tracked by actual usage, not just scope
  - Common borrow checker errors and how to resolve them
  - "Fighting the borrow checker" — normal for beginners, becomes intuitive with practice
  - The borrow checker is not optional — it cannot be disabled in safe Rust

#### § 1.5.4 — Dangling References
  - Rust prevents dangling references at compile time
  - Cannot return a reference to a local variable (would be pointing to freed memory)
  - Lifetime annotations (deep dive in Phase 3) tell the compiler how long references are valid

#### § 1.5.5 — Slices
  - `&[T]` — view into a contiguous sequence (array, vector)
  - `&str` — string slice (view into a `String` or string literal)
  - `&s[start..end]` — create a slice
  - Slices are references — they don't own the data
  - Slices prevent using a reference after the data has been modified
  - Fat pointers: slices are (pointer, length) pairs

> ### 🛠️ Phase 1 Project: **"Ownership Playground — A Student Grade Manager"**
> Build a CLI grade management system that exercises ownership:
> - Store student names and grades in vectors
> - Functions that TAKE ownership, functions that BORROW immutably, functions that BORROW mutably
> - Demonstrate: move semantics, clone, immutable borrow, mutable borrow
> - Slice operations: get a subset of students, string slicing for name manipulation
> - Pattern matching with `match` for menu navigation and grade categorization
> - `loop` with `break value` for input validation loops
> - Add comments explaining every ownership transfer and borrow
> - Run `cargo clippy` and fix all warnings, format with `cargo fmt`

---

## ⚡ PHASE 2 — THE TYPE SYSTEM & DATA MODELING
> *"Rust's type system doesn't just describe data. It encodes invariants."*

---

### 📦 Module 2.1: Structs

#### § 2.1.1 — Struct Fundamentals
  - Named fields: `struct User { name: String, age: u32 }`
  - Instantiation: `User { name: String::from("Alice"), age: 30 }`
  - Field access: `user.name`
  - Mutable structs: `let mut user = User { ... };`
  - Field init shorthand: `User { name, age }` (when variable name matches field name)
  - Struct update syntax: `User { age: 31, ..user }` — move remaining fields from another instance

#### § 2.1.2 — Tuple Structs & Unit Structs
  - Tuple structs: `struct Point(f64, f64, f64);` — named tuples
  - Access: `point.0`, `point.1`
  - Newtype pattern: `struct Meters(f64);` — type-safe wrapper (prevents mixing Meters and Seconds)
  - Unit structs: `struct Marker;` — zero-size, used as markers or for trait implementations

#### § 2.1.3 — Methods & Associated Functions
  - `impl StructName { ... }` — implementation block
  - Methods: `fn area(&self) -> f64` — takes `&self`, `&mut self`, or `self`
  - `&self` — borrows immutably (most common)
  - `&mut self` — borrows mutably
  - `self` — takes ownership (consumed)
  - Associated functions (no `self`): `fn new(name: String) -> Self` — constructors
  - `Self` keyword — alias for the implementing type
  - Multiple `impl` blocks allowed (useful for organizing or conditional compilation)

#### § 2.1.4 — Struct Ownership
  - Structs own their data (when using `String`, `Vec`, etc.)
  - Structs with references require lifetime annotations (covered in Phase 3)
  - Derived traits: `#[derive(Debug, Clone, PartialEq)]` — auto-implement common traits

---

### 📦 Module 2.2: Enums — Algebraic Data Types

#### § 2.2.1 — Enum Fundamentals
  - `enum Direction { North, South, East, West }` — simple variants
  - Variants can hold data: `enum Shape { Circle(f64), Rectangle(f64, f64) }`
  - Variants with named fields: `enum Event { Click { x: i32, y: i32 }, KeyPress(char) }`
  - Each variant is a different type within the enum
  - Enums are Rust's sum types (algebraic data types)

#### § 2.2.2 — Pattern Matching with Enums
  - `match` on enums — destructure and extract inner data
  - Must handle all variants (exhaustive)
  - `if let` for matching a single variant
  - Nested enums and nested pattern matching
  - Guards in match arms

#### § 2.2.3 — `Option<T>` — Null Safety
  - Rust has NO null — `Option<T>` replaces it
  - `enum Option<T> { Some(T), None }`
  - Forces you to handle the "absent" case at compile time
  - Methods: `unwrap()` (panics if None!), `expect("msg")`, `unwrap_or(default)`, `unwrap_or_else(|| ...)`
  - Combinators: `map()`, `and_then()` / `flat_map()`, `or()`, `or_else()`, `filter()`
  - `?` operator (in functions returning `Option`): short-circuit on `None`
  - `is_some()`, `is_none()`

#### § 2.2.4 — `Result<T, E>` — Error Handling
  - `enum Result<T, E> { Ok(T), Err(E) }`
  - The primary error handling mechanism in Rust
  - `?` operator: propagate errors automatically (early return on `Err`)
  - Methods: `unwrap()`, `expect()`, `unwrap_or()`, `map()`, `map_err()`, `and_then()`
  - Converting: `Option` → `Result` with `ok_or()`, `Result` → `Option` with `ok()`
  - Deep dive on error handling in Phase 3

---

### 📦 Module 2.3: Collections

#### § 2.3.1 — `Vec<T>` — Dynamic Array
  - `Vec::new()`, `vec![1, 2, 3]` macro
  - Methods: `push()`, `pop()`, `len()`, `is_empty()`, `get()`, `remove()`, `insert()`
  - Indexing: `v[0]` (panics on out-of-bounds), `v.get(0)` (returns `Option`)
  - Iteration: `for item in &vec`, `for item in &mut vec`, `for item in vec` (consumes)
  - Slicing: `&v[1..3]`
  - `Vec` owns its data, `&[T]` is a borrowed slice

#### § 2.3.2 — `String` and `&str`
  - `String` — owned, heap-allocated, growable UTF-8 string
  - `&str` — borrowed string slice (view into a `String` or string literal)
  - String literals are `&'static str` (live for the entire program)
  - `String::from("hello")`, `"hello".to_string()`, `format!("Hello, {name}")`
  - Methods: `push_str()`, `push()`, `len()`, `is_empty()`, `contains()`, `replace()`, `trim()`, `split()`
  - Concatenation: `format!()` (preferred), `+` operator (takes ownership of first string!)
  - Indexing: `String` CANNOT be indexed by position (UTF-8 multi-byte characters!)
  - Iterating: `s.chars()` (Unicode code points), `s.bytes()` (raw bytes)
  - String slicing: `&s[0..4]` — byte indices, will panic if not on character boundary

#### § 2.3.3 — `HashMap<K, V>`
  - `use std::collections::HashMap;`
  - `HashMap::new()`, `HashMap::from([("key", "value")])`
  - Methods: `insert()`, `get()` (returns `Option`), `remove()`, `contains_key()`, `entry()`
  - `entry()` API: `map.entry(key).or_insert(default)` — get or insert
  - Iteration: `for (key, value) in &map`
  - Keys must implement `Eq + Hash`
  - Ownership: `HashMap` takes ownership of keys and values (for owned types)

#### § 2.3.4 — Other Collections
  - `HashSet<T>` — unique values, set operations
  - `BTreeMap<K, V>` — sorted map (keys implement `Ord`)
  - `BTreeSet<T>` — sorted set
  - `VecDeque<T>` — double-ended queue
  - `LinkedList<T>` — doubly linked list (rarely used — `Vec` is almost always better)
  - `BinaryHeap<T>` — max-heap (priority queue)

---

### 📦 Module 2.4: Type System Features

#### § 2.4.1 — Type Aliases
  - `type Kilometers = i32;` — alias (NOT a new type, no type safety)
  - `type Result<T> = std::result::Result<T, MyError>;` — simplify complex types
  - Use case: shortening long type signatures

#### § 2.4.2 — The Never Type (`!`)
  - `!` — type that never has a value
  - Functions that never return: `fn exit() -> !`
  - `panic!()` returns `!`, `loop {}` returns `!`
  - Can be coerced to any type (bottom type)
  - Use case: `match` arms that diverge (panic, return, break, continue)

#### § 2.4.3 — Newtype Pattern
  - `struct Email(String);` — wrapper type for type safety
  - Prevents mixing `Email` with `Username` even though both are `String`
  - Implement `Deref` to access inner type's methods (or implement methods explicitly)
  - Use case: domain-driven design, units of measurement, validated types

---

### 📦 Module 2.5: Modules & Crates

#### § 2.5.1 — Module System
  - `mod module_name { ... }` — inline module
  - `mod module_name;` — load from `module_name.rs` or `module_name/mod.rs`
  - `pub` keyword: make items public
  - `pub(crate)` — public within the crate only
  - `pub(super)` — public to parent module
  - `pub(in path)` — public to a specific module path
  - `use` keyword: bring items into scope
  - `use crate::module::Item;` — absolute path
  - `use self::submodule::Item;` — relative path
  - `use super::Item;` — parent module
  - Re-exports: `pub use inner::Item;` — expose inner items through outer module

#### § 2.5.2 — Crate Organization
  - Binary crate: has `main.rs`
  - Library crate: has `lib.rs`
  - A package can have both (one library + multiple binaries)
  - Workspace: multiple packages sharing dependencies (`Cargo.toml` workspace section)
  - Feature flags: conditional compilation with `#[cfg(feature = "...")]`
  - `pub` API design: expose minimal public surface

> ### 🛠️ Phase 2 Project: **"ContactBook — A Type-Safe Contact Manager"**
> Build a contact management CLI application:
> - Struct: `Contact` with name, email, phone, category (enum)
> - Enum: `Category` with `Personal`, `Work(String)` (company name), `Family(Relation)` variants
> - Newtype: `Email(String)`, `PhoneNumber(String)` with validation constructors returning `Result`
> - `Option<T>` for optional fields (phone, notes)
> - `HashMap<ContactId, Contact>` for storage
> - `Vec<Contact>` for search results
> - `Result<T, ContactError>` for all fallible operations with custom error enum
> - Module organization: `models`, `storage`, `search`, `display`
> - Pattern matching for menu options and contact operations
> - `entry()` API for upsert operations
> - `#[derive(Debug, Clone, PartialEq)]` on all types
> - Serialize/deserialize to JSON file using `serde` and `serde_json` crate

---

## ⚡ PHASE 3 — TRAITS, LIFETIMES & ERROR HANDLING
> *"Traits are Rust's superpower. Lifetimes are Rust's price of admission."*

---

### 📦 Module 3.1: Traits — Shared Behavior

#### § 3.1.1 — Trait Fundamentals
  - `trait Summary { fn summarize(&self) -> String; }` — trait definition
  - `impl Summary for Article { fn summarize(&self) -> String { ... } }` — implementation
  - Default method implementations: methods with a body in the trait definition
  - Default implementations can call other trait methods (even abstract ones)
  - Orphan rule: can only implement a trait if you own the trait OR the type (not neither)

#### § 3.1.2 — Trait Bounds
  - `fn notify(item: &impl Summary)` — shorthand
  - `fn notify<T: Summary>(item: &T)` — generic bound
  - Multiple bounds: `T: Summary + Display`
  - `where` clause: `fn func<T, U>(t: &T, u: &U) -> String where T: Summary + Clone, U: Display`
  - Returning types that implement traits: `fn create() -> impl Summary` (opaque return type)

#### § 3.1.3 — Trait Objects — Dynamic Dispatch
  - `Box<dyn Summary>` — heap-allocated trait object
  - `&dyn Summary` — borrowed trait object
  - Dynamic dispatch: method resolved at runtime via vtable (small performance cost)
  - Object safety: not all traits can be made into trait objects (no `Self` return, no generics)
  - `dyn Trait` vs `impl Trait` — dynamic vs static dispatch, flexibility vs performance

#### § 3.1.4 — Common Standard Library Traits
  - `Debug` — `{:?}` formatting (always derive)
  - `Display` — `{}` user-facing formatting (implement manually)
  - `Clone` — explicit deep copy (`clone()`)
  - `Copy` — implicit bitwise copy (marker trait, implies `Clone`)
  - `PartialEq`, `Eq` — equality comparison
  - `PartialOrd`, `Ord` — ordering comparison
  - `Hash` — hashing (for `HashMap` keys)
  - `Default` — default value (`Default::default()`)
  - `From<T>`, `Into<T>` — type conversion (implement `From`, get `Into` for free)
  - `TryFrom<T>`, `TryInto<T>` — fallible type conversion
  - `Deref`, `DerefMut` — smart pointer dereferencing
  - `Drop` — custom cleanup (destructor)
  - `Iterator` — iteration protocol
  - `Send`, `Sync` — thread safety markers (covered in concurrency)

#### § 3.1.5 — Advanced Trait Features
  - Associated types: `type Item;` in trait definition (vs generic parameter)
  - Supertraits: `trait MyTrait: Display + Debug { ... }` — require other traits
  - Blanket implementations: `impl<T: Display> ToString for T { ... }` — implement for all types satisfying a bound
  - Marker traits: `Send`, `Sync`, `Copy`, `Sized` — no methods, just properties
  - Negative trait bounds (nightly): `!Send` — NOT thread-safe

---

### 📦 Module 3.2: Generics

#### § 3.2.1 — Generic Functions & Structs
  - `fn largest<T: PartialOrd>(list: &[T]) -> &T`
  - `struct Point<T> { x: T, y: T }`
  - `struct Point<T, U> { x: T, y: U }` — multiple type parameters
  - `impl<T> Point<T> { ... }` — methods on generic types
  - `impl Point<f64> { ... }` — methods only for specific type
  - Zero-cost: generics are monomorphized (compiled to specific types, no runtime overhead)

#### § 3.2.2 — Generic Enums
  - `Option<T>`, `Result<T, E>` — the most important generic enums
  - Custom generic enums for domain modeling

#### § 3.2.3 — Const Generics
  - `struct Array<T, const N: usize> { data: [T; N] }`
  - Generic over values, not just types
  - Use case: fixed-size arrays, matrix dimensions, buffer sizes
  - `const` expressions in generic positions

---

### 📦 Module 3.3: Lifetimes

#### § 3.3.1 — Why Lifetimes Exist
  - Prevent dangling references at compile time
  - Every reference has a lifetime — the scope for which it's valid
  - Most lifetimes are inferred (elided) — you only annotate when the compiler can't figure it out
  - Lifetimes don't change how long data lives — they describe relationships between references

#### § 3.3.2 — Lifetime Annotations
  - `'a` — lifetime parameter (apostrophe + name)
  - `fn longest<'a>(x: &'a str, y: &'a str) -> &'a str` — returned reference lives as long as the shortest input
  - Struct lifetimes: `struct Excerpt<'a> { text: &'a str }` — struct cannot outlive the referenced data
  - Lifetime annotations constrain relationships, not durations

#### § 3.3.3 — Lifetime Elision Rules
  - Rule 1: each reference parameter gets its own lifetime parameter
  - Rule 2: if there's exactly one input lifetime, it's assigned to all output lifetimes
  - Rule 3: if `&self` or `&mut self` is a parameter, its lifetime is assigned to all output lifetimes
  - If these rules don't determine output lifetimes, you must annotate explicitly

#### § 3.3.4 — `'static` Lifetime
  - `'static` — reference valid for the entire program duration
  - String literals are `&'static str`
  - Owned types like `String` satisfy `'static` bounds (they don't reference anything)
  - `T: 'static` means T contains no non-static references (NOT that T lives forever)
  - Common in thread APIs: `spawn` requires `'static` because the thread might outlive the caller

#### § 3.3.5 — Lifetime in Practice
  - Most code doesn't need explicit lifetimes (elision covers ~90% of cases)
  - When you need them: returning references, storing references in structs, complex functions
  - Multiple lifetime parameters: `fn func<'a, 'b>(x: &'a str, y: &'b str) -> &'a str`
  - Higher-Ranked Trait Bounds (HRTBs): `for<'a> Fn(&'a T) -> &'a U` (advanced, closures)

---

### 📦 Module 3.4: Error Handling — The Rust Way

#### § 3.4.1 — Unrecoverable Errors (`panic!`)
  - `panic!("crash message")` — abort the thread
  - `unwrap()`, `expect()` — panic on `None`/`Err`
  - Array index out of bounds — implicit panic
  - When to panic: bugs, impossible states, unrecoverable conditions
  - `RUST_BACKTRACE=1` — get a backtrace on panic
  - `panic = "abort"` in Cargo.toml — abort process instead of unwinding

#### § 3.4.2 — Recoverable Errors (`Result<T, E>`)
  - `Result::Ok(value)` — success
  - `Result::Err(error)` — failure
  - Pattern matching on `Result`
  - Combinators: `map()`, `map_err()`, `and_then()`, `or_else()`, `unwrap_or()`, `unwrap_or_default()`

#### § 3.4.3 — The `?` Operator
  - Propagate errors automatically: `let val = func()?;`
  - If `Err`, return early with the error (converted via `From` trait)
  - Works in functions returning `Result` or `Option`
  - `From` trait enables automatic error conversion between error types
  - `?` in `main`: `fn main() -> Result<(), Box<dyn Error>>`

#### § 3.4.4 — Custom Error Types
  - Define an error enum: `enum AppError { NotFound, ParseError(String), IoError(std::io::Error) }`
  - Implement `Display` and `Error` traits
  - Implement `From<SourceError>` for automatic conversion with `?`
  - Error crates: `thiserror` (derive macros for library errors), `anyhow` (application-level flexible errors)

#### § 3.4.5 — `thiserror` vs `anyhow`
  - `thiserror` — for libraries: derive `Error`, `Display`, `From` automatically
  - `anyhow` — for applications: `anyhow::Result<T>`, `anyhow::Context`, `.context("what went wrong")`
  - Rule of thumb: `thiserror` in libraries, `anyhow` in binaries
  - `anyhow::bail!("message")` — quick error return
  - `anyhow::ensure!(condition, "message")` — assertion that returns error

> ### 🛠️ Phase 3 Project: **"MiniGrep — A Text Search Tool"**
> Build a simplified version of `grep`:
> - Takes a search pattern and file path as arguments
> - Reads the file, searches for matching lines, prints results with line numbers
> - **Traits**: `Display` for custom output formatting, custom `Searchable` trait for different search strategies (case-sensitive, regex, fuzzy)
> - **Generics**: generic search function over any `Searchable` implementation
> - **Lifetimes**: return slices referencing the original file content, struct holding references to file data
> - **Error handling**: `Result`-based with `thiserror` for a custom `SearchError` enum (`FileNotFound`, `InvalidPattern`, `IoError`)
> - **`?` operator**: throughout for clean error propagation
> - `anyhow` in `main()` for top-level error handling
> - Environment variable support: `CASE_INSENSITIVE=1` for case-insensitive search
> - Module organization: `config`, `search`, `output`
> - Unit tests for search logic, integration tests for CLI behavior

---

## ⚡ PHASE 4 — CLOSURES, ITERATORS & FUNCTIONAL PATTERNS
> *"Rust is not a functional language. But its functional features are incredibly powerful."*

---

### 📦 Module 4.1: Closures — Deep Dive

#### § 4.1.1 — Closure Traits
  - `Fn` — borrows captured variables immutably (can be called multiple times)
  - `FnMut` — borrows captured variables mutably (can be called multiple times)
  - `FnOnce` — takes ownership of captured variables (can only be called once)
  - Hierarchy: `Fn` : `FnMut` : `FnOnce` (every `Fn` is also `FnMut` and `FnOnce`)
  - Compiler infers which trait a closure implements based on how it uses captured variables

#### § 4.1.2 — Closure Capture Modes
  - Immutable borrow: closure reads captured variable
  - Mutable borrow: closure modifies captured variable
  - Move: closure takes ownership (`move || { ... }`)
  - `move` keyword: force ownership transfer (essential for threading)
  - Compiler chooses the least restrictive capture mode automatically

#### § 4.1.3 — Closures as Parameters & Return Values
  - `fn apply(f: impl Fn(i32) -> i32, x: i32) -> i32` — impl Trait (monomorphized)
  - `fn apply(f: &dyn Fn(i32) -> i32, x: i32) -> i32` — trait object (dynamic dispatch)
  - `fn apply<F: Fn(i32) -> i32>(f: F, x: i32) -> i32` — generic bound
  - Returning closures: `fn make_adder(n: i32) -> impl Fn(i32) -> i32`
  - Returning closures on heap: `fn make_adder(n: i32) -> Box<dyn Fn(i32) -> i32>`

---

### 📦 Module 4.2: Iterators

#### § 4.2.1 — The Iterator Trait
  - `trait Iterator { type Item; fn next(&mut self) -> Option<Self::Item>; }`
  - Lazy evaluation: iterator adaptors don't do work until consumed
  - Creating iterators: `.iter()` (borrow), `.iter_mut()` (mutable borrow), `.into_iter()` (ownership)
  - `for` loop: calls `into_iter()` automatically

#### § 4.2.2 — Iterator Adaptors (Lazy)
  - `map(|x| x * 2)` — transform each element
  - `filter(|x| x > &5)` — keep elements matching predicate
  - `filter_map(|x| x.parse().ok())` — filter and transform in one step
  - `flat_map(|x| x.iter())` — map + flatten
  - `enumerate()` — add index
  - `zip(other)` — pair with another iterator
  - `chain(other)` — concatenate iterators
  - `take(n)`, `skip(n)` — limit/skip elements
  - `take_while(pred)`, `skip_while(pred)` — predicate-based limits
  - `peekable()` — peek at next without consuming
  - `inspect(|x| println!("{x}"))` — debug without modifying
  - `rev()` — reverse (requires `DoubleEndedIterator`)
  - `cloned()`, `copied()` — convert `&T` iterator to `T` iterator
  - `chunks()`, `windows()` — sliding windows (on slices)

#### § 4.2.3 — Iterator Consumers (Eager)
  - `collect()` — gather into a collection (turbofish: `collect::<Vec<_>>()`)
  - `sum()`, `product()` — numeric aggregation
  - `count()`, `min()`, `max()` — statistics
  - `any(pred)`, `all(pred)` — boolean checks
  - `find(pred)` — first matching element (returns `Option`)
  - `position(pred)` — index of first match
  - `fold(init, |acc, x| ...)` — general-purpose accumulation
  - `reduce(|acc, x| ...)` — fold without initial value
  - `for_each(|x| ...)` — consume with side effects
  - `partition(pred)` — split into two collections
  - `unzip()` — split pairs into two collections

#### § 4.2.4 — Custom Iterators
  - Implement `Iterator` trait on your own types
  - Define `type Item` and `fn next(&mut self) -> Option<Self::Item>`
  - Use case: custom data structure traversal, lazy sequences, state machines

---

### 📦 Module 4.3: Functional Patterns

#### § 4.3.1 — Iterator Chains
  - Building complex data transformations as readable pipelines
  - Performance: iterator chains are zero-cost (compiled to a single loop — no intermediate allocations)
  - Splitting long chains for readability

#### § 4.3.2 — Combinators on `Option` and `Result`
  - `Option`: `map`, `and_then`, `or`, `or_else`, `filter`, `zip`, `flatten`
  - `Result`: `map`, `map_err`, `and_then`, `or`, `or_else`, `unwrap_or_else`
  - Chaining: `opt.map(|x| x + 1).filter(|x| x > &5).unwrap_or(0)`
  - `Option` and `Result` are monads (without the scary name)

#### § 4.3.3 — Composing Complex Operations
  - Building processing pipelines from small, testable functions
  - Passing closures to customize behavior
  - Using `Result` in iterator chains with `collect::<Result<Vec<_>, _>>()`
  - `try_fold`, `try_for_each` — fallible iteration

> ### 🛠️ Phase 4 Project: **"DataCrunch — A CSV Data Processing Pipeline"**
> Build a CSV data processor using iterators and closures:
> - Read CSV files line by line using iterators (lazy, memory-efficient)
> - Parse rows into typed structs using iterator chains and `Result`
> - Filter rows by predicate closures (configurable at runtime)
> - Transform data using `map` chains
> - Aggregate: sum, average, min, max, count by category using `fold`
> - Group by column using `Iterator` + `HashMap`
> - Sort results using closure comparators
> - Custom iterator: implement a `WindowedIterator` that yields sliding windows of N rows
> - Output formatted tables using `format!` and iterator chains
> - All errors handled with `Result` — no `unwrap` in production code
> - Benchmark: compare iterator chain performance vs manual loop (they should be identical)

---

## ⚡ PHASE 5 — SMART POINTERS & MEMORY MANAGEMENT
> *"Smart pointers are Rust's way of giving you heap control with safety guarantees."*

---

### 📦 Module 5.1: Smart Pointers

#### § 5.1.1 — `Box<T>` — Heap Allocation
  - Puts data on the heap with single ownership
  - `Box::new(value)` — allocate on heap
  - Use cases: recursive types (linked lists, trees), large data avoiding stack overflow, trait objects
  - `Deref` coercion: `Box<T>` auto-dereferences to `T`
  - Zero overhead beyond the heap allocation itself

#### § 5.1.2 — `Rc<T>` — Reference Counting (Single-Threaded)
  - Multiple owners of the same data
  - `Rc::new(value)`, `Rc::clone(&rc)` — increment reference count
  - `Rc::strong_count(&rc)` — check reference count
  - Data is dropped when count reaches zero
  - Immutable only — cannot get mutable access to `Rc` contents (without interior mutability)
  - NOT thread-safe — single-threaded only

#### § 5.1.3 — `Arc<T>` — Atomic Reference Counting (Thread-Safe)
  - Thread-safe version of `Rc<T>` (uses atomic operations)
  - `Arc::new(value)`, `Arc::clone(&arc)`
  - Small overhead from atomic operations
  - Required for sharing data between threads
  - Still immutable — combine with `Mutex` or `RwLock` for mutable shared state

#### § 5.1.4 — `Cow<'a, B>` — Clone on Write
  - `enum Cow<'a, B: ToOwned> { Borrowed(&'a B), Owned(B::Owned) }`
  - Holds either a borrowed reference or an owned value
  - Clones only when mutation is needed
  - Use case: functions that sometimes need to modify a string and sometimes don't

---

### 📦 Module 5.2: Interior Mutability

#### § 5.2.1 — `Cell<T>` and `RefCell<T>`
  - `Cell<T>` — get/set values for `Copy` types (no references, just copy in/out)
  - `RefCell<T>` — borrow checking at RUNTIME instead of compile time
  - `borrow()` — immutable borrow (returns `Ref<T>`)
  - `borrow_mut()` — mutable borrow (returns `RefMut<T>`)
  - Panics at runtime if borrowing rules are violated (instead of compile error)
  - Use case: when you need mutability inside an immutable structure
  - Common pattern: `Rc<RefCell<T>>` — shared mutable data (single-threaded)

#### § 5.2.2 — `Mutex<T>` and `RwLock<T>`
  - `Mutex<T>` — mutual exclusion lock, one accessor at a time
  - `mutex.lock()` — acquire lock, returns `MutexGuard` (RAII — auto-releases on drop)
  - `RwLock<T>` — multiple readers OR one writer
  - Both are interior mutability for concurrent contexts
  - Common pattern: `Arc<Mutex<T>>` — shared mutable data across threads

---

### 📦 Module 5.3: The `Deref` and `Drop` Traits

#### § 5.3.1 — `Deref` Trait
  - `Deref` — automatic dereferencing
  - Deref coercion: `&String` → `&str`, `&Box<T>` → `&T`, `&Vec<T>` → `&[T]`
  - Enables ergonomic API design (accept `&str` instead of `&String`)
  - `DerefMut` — mutable dereferencing

#### § 5.3.2 — `Drop` Trait
  - `fn drop(&mut self)` — custom cleanup logic
  - Called automatically when value goes out of scope
  - Cannot call `drop()` method directly — use `std::mem::drop(value)` for early drops
  - Drop order: variables dropped in reverse declaration order, struct fields in declaration order
  - Use case: releasing file handles, network connections, locks, GPU memory

---

### 📦 Module 5.4: Advanced Memory Patterns

#### § 5.4.1 — Recursive Data Structures
  - Linked list: `enum List { Cons(i32, Box<List>), Nil }`
  - Trees: `Box` for children, `Rc` for shared nodes
  - Graph with cycles: `Rc<RefCell<T>>` or arena allocation

#### § 5.4.2 — `Weak<T>` — Breaking Reference Cycles
  - `Rc::downgrade(&rc)` → `Weak<T>` — non-owning reference
  - `weak.upgrade()` → `Option<Rc<T>>` — check if value still exists
  - Prevents memory leaks from reference cycles
  - Parent-child trees: parent owns children (`Rc`), children reference parent (`Weak`)

#### § 5.4.3 — `Pin<T>` (Introduction)
  - Guarantees a value will not move in memory
  - Required for self-referential types and `async`/`await` futures
  - `Pin<Box<T>>`, `Pin<&mut T>`
  - `Unpin` marker trait — most types are `Unpin` (can be moved out of `Pin`)
  - Deep dive in async phase

> ### 🛠️ Phase 5 Project: **"ArenAlloc — A Custom Memory Arena and Data Structures"**
> Build memory-managed data structures:
> - Singly linked list using `Box<T>`
> - Doubly linked list using `Rc<RefCell<T>>` with `Weak<T>` for back-pointers
> - N-ary tree using `Rc<RefCell<TreeNode>>` with parent `Weak` references
> - Custom arena allocator: pre-allocate a `Vec<T>`, return indices instead of pointers
>   - Arena handles lifetimes — all nodes freed at once when arena is dropped
> - `Drop` implementation: log when each structure is freed (demonstrate drop order)
> - `Deref` implementation on a custom smart pointer wrapper
> - Benchmark: compare `Box`-based tree vs arena-based tree allocation performance
> - Detect and prevent reference cycles (demonstrate `Weak` vs `Rc` memory behavior)

---

## ⚡ PHASE 6 — CONCURRENCY & PARALLELISM
> *"Fearless concurrency — Rust's most revolutionary promise."*

---

### 📦 Module 6.1: Thread Fundamentals

#### § 6.1.1 — Spawning Threads
  - `std::thread::spawn(|| { ... })` — create a new thread
  - `handle.join()` — wait for thread to finish (returns `Result`)
  - `move` closures: transfer ownership to thread
  - Thread panics: contained to the spawned thread, `join()` returns `Err`
  - `thread::sleep(Duration)` — pause thread

#### § 6.1.2 — `Send` and `Sync` Traits
  - `Send` — type can be transferred to another thread
  - `Sync` — type can be referenced from multiple threads simultaneously
  - Auto-implemented by the compiler based on the type's contents
  - `Rc<T>` is NOT `Send`/`Sync` — use `Arc<T>` instead
  - `Cell<T>`, `RefCell<T>` are NOT `Sync` — use `Mutex<T>` instead
  - Raw pointers are NOT `Send`/`Sync` — manual `unsafe impl` if needed
  - These traits prevent data races at COMPILE TIME — not runtime

#### § 6.1.3 — Shared State with `Arc<Mutex<T>>`
  - `Arc` — shared ownership across threads
  - `Mutex` — mutual exclusion for safe mutation
  - `Arc::new(Mutex::new(data))` — the standard shared mutable state pattern
  - `mutex.lock().unwrap()` — acquire lock, handle potential poisoning
  - Lock poisoning: if a thread panics while holding a lock, the mutex becomes "poisoned"
  - `RwLock<T>` — multiple readers OR one writer (better for read-heavy workloads)

---

### 📦 Module 6.2: Message Passing

#### § 6.2.1 — Channels (`std::sync::mpsc`)
  - `mpsc::channel()` — multiple producer, single consumer
  - `tx.send(value)` — send (takes ownership)
  - `rx.recv()` — blocking receive
  - `rx.try_recv()` — non-blocking receive
  - `tx.clone()` — create additional producers
  - Iterating: `for msg in rx { ... }` — until all senders are dropped

#### § 6.2.2 — `crossbeam` Channels
  - `crossbeam::channel::unbounded()` — unbounded multi-producer multi-consumer
  - `crossbeam::channel::bounded(n)` — bounded (backpressure)
  - `select!` macro — wait on multiple channels
  - Generally preferred over `std::sync::mpsc` for production use

---

### 📦 Module 6.3: Concurrency Crate Ecosystem

#### § 6.3.1 — `rayon` — Data Parallelism
  - `par_iter()` — parallel iterator (drop-in replacement for `iter()`)
  - `par_sort()`, `par_chunks()` — parallel operations on slices
  - Work-stealing thread pool — automatic load balancing
  - Zero config: just change `iter()` to `par_iter()` and it works
  - Use case: CPU-bound data processing, batch transformations

#### § 6.3.2 — `crossbeam` — Concurrency Utilities
  - Scoped threads: `crossbeam::scope(|s| { s.spawn(|| { ... }); })` — borrow local variables in threads
  - Channels (covered above)
  - Atomic data structures: `crossbeam::queue`, `crossbeam::deque`
  - Epoch-based memory reclamation

#### § 6.3.3 — Atomic Types (`std::sync::atomic`)
  - `AtomicBool`, `AtomicI32`, `AtomicU64`, `AtomicUsize`, `AtomicPtr`
  - `load()`, `store()`, `fetch_add()`, `compare_exchange()`
  - Memory orderings: `Relaxed`, `Acquire`, `Release`, `AcqRel`, `SeqCst`
  - Use case: lock-free counters, flags, simple shared state
  - When to use atomics vs mutexes: simple values → atomics, complex state → mutexes

---

### 📦 Module 6.4: Concurrency Patterns

#### § 6.4.1 — Thread Pool Pattern
  - Fixed number of threads processing tasks from a channel
  - `rayon::ThreadPool` for automatic management
  - Manual implementation for learning

#### § 6.4.2 — Producer-Consumer
  - Bounded channel for backpressure
  - Multiple producers, single/multiple consumers
  - Graceful shutdown via channel closing

#### § 6.4.3 — Map-Reduce
  - `rayon`'s `par_iter().map(...).reduce(...)` — parallel map-reduce
  - Splitting work, processing in parallel, combining results

#### § 6.4.4 — Common Concurrency Bugs in Rust
  - Deadlocks: Rust prevents data races but NOT deadlocks
  - Lock ordering: consistent ordering to prevent deadlocks
  - Poisoned mutexes: handling panics in locked sections
  - Starvation: `RwLock` reader-writer starvation

> ### 🛠️ Phase 6 Project: **"ParaSearch — A Parallel File Search Engine"**
> Build a concurrent file search tool:
> - Recursively walk directories using threads (producer: directory walker, consumers: file processors)
> - Search file contents for a pattern using `rayon::par_iter()` across files
> - `Arc<Mutex<Results>>` for collecting results from multiple threads
> - `crossbeam` channels for work distribution (bounded, with backpressure)
> - `crossbeam::scope` for borrowing stack data in threads
> - Atomic counter for files processed, lines scanned
> - Thread pool with configurable size
> - Progress reporting from a separate thread
> - Graceful cancellation on Ctrl+C (signal handling)
> - Benchmark: single-threaded vs multi-threaded vs `rayon` parallel iterator

---

## ⚡ PHASE 7 — ASYNC/AWAIT & ASYNCHRONOUS PROGRAMMING
> *"Async Rust is hard. But it enables millions of concurrent operations on a single machine."*

---

### 📦 Module 7.1: Async Fundamentals

#### § 7.1.1 — Why Async
  - Threads are expensive: each thread ~8KB stack, OS scheduling overhead
  - Async: lightweight tasks, cooperative scheduling, single or few OS threads
  - I/O-bound workloads: network servers, HTTP clients, database queries
  - When NOT to use async: CPU-bound work (use `rayon`), simple scripts, learning Rust

#### § 7.1.2 — `async`/`await` Syntax
  - `async fn do_work() -> Result<Data, Error> { ... }` — async function
  - `value.await` — suspend until the future resolves
  - Async functions return a `Future` — they don't execute until polled
  - `Future` trait: `fn poll(self: Pin<&mut Self>, cx: &mut Context<'_>) -> Poll<Self::Output>`
  - `Poll::Ready(value)` — future is complete
  - `Poll::Pending` — future is not ready, will be woken later

#### § 7.1.3 — Async Runtimes
  - Rust's standard library does NOT include an async runtime
  - **Tokio** — the dominant async runtime (used by most production Rust)
  - **async-std** — alternative runtime (simpler API, less popular)
  - **smol** — minimal async runtime
  - Runtime responsibilities: task scheduling, I/O polling, timer management
  - `#[tokio::main]` — macro to set up the runtime for `main`

---

### 📦 Module 7.2: Tokio Runtime

#### § 7.2.1 — Tokio Fundamentals
  - `tokio::spawn(async { ... })` — spawn a task (like a lightweight thread)
  - `tokio::task::JoinHandle` — handle to a spawned task
  - `handle.await` — wait for task completion
  - Multi-threaded runtime: `#[tokio::main]` (default, work-stealing)
  - Single-threaded runtime: `#[tokio::main(flavor = "current_thread")]`
  - `tokio::time::sleep(duration).await` — async sleep

#### § 7.2.2 — Tokio Concurrency Primitives
  - `tokio::sync::Mutex` — async-aware mutex (don't use `std::sync::Mutex` in async!)
  - `tokio::sync::RwLock` — async read-write lock
  - `tokio::sync::Semaphore` — limit concurrency
  - `tokio::sync::Notify` — notify waiting tasks
  - `tokio::sync::mpsc` — async multi-producer, single consumer channel
  - `tokio::sync::broadcast` — multi-producer, multi-consumer
  - `tokio::sync::oneshot` — single-use channel
  - `tokio::sync::watch` — single-producer, multi-consumer (latest value)

#### § 7.2.3 — Tokio I/O
  - `tokio::fs` — async file operations
  - `tokio::net::TcpListener`, `tokio::net::TcpStream` — async networking
  - `tokio::io::AsyncReadExt`, `tokio::io::AsyncWriteExt` — async read/write traits
  - `tokio::io::BufReader`, `tokio::io::BufWriter` — buffered async I/O

---

### 📦 Module 7.3: Advanced Async Patterns

#### § 7.3.1 — Concurrent Execution
  - `tokio::join!` — run multiple futures concurrently, wait for all
  - `tokio::select!` — run multiple futures, complete when first finishes (cancel others)
  - `tokio::spawn` — run task in the background (fire-and-forget)
  - `FuturesUnordered` — collection of futures, process as they complete
  - `futures::future::join_all` — join a dynamic number of futures
  - `futures::stream` — async iteration (stream of values over time)

#### § 7.3.2 — Async Streams
  - `Stream` trait — async version of `Iterator`
  - `tokio_stream::StreamExt` — adaptor methods (`map`, `filter`, `next`, `collect`)
  - Creating streams: `tokio_stream::wrappers::ReceiverStream` (from channel)
  - `async-stream` crate — `stream!` macro for easy stream creation

#### § 7.3.3 — Cancellation & Timeouts
  - `tokio::time::timeout(duration, future)` — cancel after duration
  - `tokio::select!` — cancel losing branches
  - `CancellationToken` (tokio-util) — cooperative cancellation
  - Drop-based cancellation: dropping a future cancels it
  - Graceful shutdown patterns with async

#### § 7.3.4 — Common Async Pitfalls
  - Holding `std::sync::Mutex` across `.await` points — use `tokio::sync::Mutex` or restructure
  - Blocking in async context — use `tokio::task::spawn_blocking` for CPU-bound work
  - `Send` bounds on futures: `tokio::spawn` requires `Send` futures
  - Large futures: deeply nested async call chains create large future state machines
  - Async trait methods: require `async-trait` crate or RPITIT (Return Position Impl Trait In Trait, stabilized in Rust 1.75)

---

### 📦 Module 7.4: `Pin` & Self-Referential Futures

#### § 7.4.1 — Why `Pin` Exists
  - Futures are state machines — they may contain self-references
  - Moving a self-referential type invalidates internal pointers
  - `Pin<P>` guarantees the pointed-to value won't move in memory
  - Most users don't need to interact with `Pin` directly
  - Library authors and low-level async code must understand `Pin`

#### § 7.4.2 — `Unpin` Trait
  - Most types are `Unpin` — they can be safely moved even when pinned
  - Self-referential types (like compiler-generated futures) are `!Unpin`
  - `Pin` only restricts types that are `!Unpin`

> ### 🛠️ Phase 7 Project: **"AsyncChat — An Async Chat Server"**
> Build a real-time chat server with Tokio:
> - TCP-based chat server with `tokio::net::TcpListener`
> - Multiple clients connected simultaneously (each in its own task)
> - Message broadcasting: `tokio::sync::broadcast` channel for pub/sub
> - Rooms/channels: `HashMap<String, broadcast::Sender<Message>>` behind `Arc<Mutex<_>>`
> - Commands: `/join room`, `/leave`, `/list`, `/msg user`, `/quit`
> - Graceful shutdown on Ctrl+C using `tokio::signal` + `CancellationToken`
> - Connection timeout: disconnect idle clients using `tokio::time::timeout`
> - Rate limiting per client using `tokio::sync::Semaphore`
> - `tokio::select!` for handling both user input and server broadcasts
> - Async file logging: write chat history to file using `tokio::fs`
> - Client binary: interactive CLI that connects to the server
> - Error handling with `anyhow` for the binary, `thiserror` for the library parts

---

## ⚡ PHASE 8 — TESTING, TOOLING & SOFTWARE ENGINEERING
> *"Cargo gives you best-in-class testing, documentation, and tooling — built in."*

---

### 📦 Module 8.1: Testing

#### § 8.1.1 — Unit Tests
  - `#[cfg(test)] mod tests { ... }` — test module (only compiled during testing)
  - `#[test] fn test_name() { ... }` — test function
  - Assertions: `assert!()`, `assert_eq!()`, `assert_ne!()`
  - Custom messages: `assert!(cond, "Expected {expected}, got {actual}")`
  - `#[should_panic]` — test that code panics
  - `#[should_panic(expected = "message")]` — panic with specific message
  - `Result`-returning tests: `#[test] fn it_works() -> Result<(), String>`
  - `#[ignore]` — skip test (run with `cargo test -- --ignored`)
  - Testing private functions: test module is inside the crate, can access private items

#### § 8.1.2 — Integration Tests
  - `tests/` directory — each file is a separate crate
  - Can only test public API
  - Shared helpers: `tests/common/mod.rs`
  - Running: `cargo test --test integration_test_name`

#### § 8.1.3 — Documentation Tests
  - Code examples in doc comments (` ``` `) are compiled and run as tests
  - `cargo test` runs doc tests automatically
  - `# ` prefix hides lines from documentation but includes them in the test
  - `should_panic`, `no_run`, `compile_fail`, `ignore` annotations
  - Documentation tests ensure examples stay up-to-date

#### § 8.1.4 — Test Organization & Patterns
  - Test fixtures: setup/teardown with helper functions
  - Test builders: fluent API for constructing test data
  - Proptest / Quickcheck: property-based testing
  - `mockall` crate for mocking traits
  - `fake` crate for generating test data
  - `test-case` crate for parameterized tests
  - `rstest` crate for fixtures and parameterized tests

#### § 8.1.5 — Benchmarking
  - `criterion` crate — statistical benchmarking (the standard)
  - `divan` crate — simpler alternative
  - Measuring: throughput, latency, comparison between implementations
  - `cargo bench` — run benchmarks

---

### 📦 Module 8.2: Documentation

#### § 8.2.1 — Doc Comments
  - `///` — item documentation (functions, structs, enums, traits)
  - `//!` — module/crate-level documentation
  - Markdown formatting: headers, code blocks, lists, links
  - Sections: `# Examples`, `# Panics`, `# Errors`, `# Safety`
  - `[`link`]` — cross-referencing other items
  - `cargo doc --open` — generate and browse documentation

#### § 8.2.2 — Documentation Best Practices
  - Every public item should be documented
  - Include at least one example in doc comments
  - Document panic conditions and error conditions
  - Document `unsafe` invariants
  - `#[doc(hidden)]` — hide items from documentation
  - `#![warn(missing_docs)]` — lint for missing documentation

---

### 📦 Module 8.3: Advanced Cargo

#### § 8.3.1 — Cargo Features
  - `[features]` in `Cargo.toml` — optional functionality
  - Default features: `default = ["feature_a"]`
  - `#[cfg(feature = "feature_name")]` — conditional compilation
  - Dependency features: `serde = { version = "1", features = ["derive"] }`
  - Additive features: features can only ADD functionality, never remove
  - Use case: optional dependencies, compile-time configuration

#### § 8.3.2 — Workspaces
  - `[workspace]` in root `Cargo.toml`
  - Shared dependencies, shared `Cargo.lock`, shared build output
  - `cargo build -p package_name` — build specific package
  - `cargo test --workspace` — test all packages
  - Workspace dependency inheritance (Rust 1.64+): define in workspace, inherit in members

#### § 8.3.3 — Profiles
  - `[profile.dev]` — debug builds (default)
  - `[profile.release]` — release builds (`--release`)
  - `[profile.test]`, `[profile.bench]`
  - Optimization level: `opt-level = 3`
  - LTO: `lto = true` — link-time optimization
  - `debug = true` in release — keep debug symbols
  - `strip = true` — strip symbols for smaller binaries
  - Custom profiles: `[profile.profiling]`

#### § 8.3.4 — Useful Cargo Plugins
  - `cargo-watch` — recompile on file changes
  - `cargo-expand` — show expanded macros
  - `cargo-deny` — audit dependencies (licenses, security, duplicates)
  - `cargo-audit` — security vulnerability scanning
  - `cargo-flamegraph` — generate flame graphs
  - `cargo-udeps` — find unused dependencies
  - `cargo-nextest` — faster test runner
  - `cargo-release` — automated releasing
  - `cargo-mutants` — mutation testing

---

### 📦 Module 8.4: Code Quality

#### § 8.4.1 — Clippy — The Linter
  - `cargo clippy` — run Clippy
  - `#[allow(clippy::lint_name)]` — suppress specific lints
  - `#[deny(clippy::lint_name)]` — make a lint an error
  - Lint groups: `clippy::pedantic`, `clippy::nursery`, `clippy::cargo`
  - Clippy as CI gate: `cargo clippy -- -D warnings`

#### § 8.4.2 — `rustfmt`
  - `cargo fmt` — format all code
  - `rustfmt.toml` — customization (limited — opinionated by design)
  - CI gate: `cargo fmt -- --check`

#### § 8.4.3 — `miri` — Undefined Behavior Detector
  - Interprets Rust code and detects UB
  - `cargo +nightly miri test` — run tests under Miri
  - Detects: out-of-bounds, use-after-free, data races, uninitialized memory
  - Essential for `unsafe` code validation

> ### 🛠️ Phase 8 Project: **"CrateForge — A Well-Engineered Reusable Library"**
> Build a publishable-quality Rust library:
> - Library: a type-safe configuration management system
>   - Parse config from: TOML, JSON, environment variables
>   - Type-safe access: generic `get::<T>(key)` with custom deserialization
>   - Layered config: defaults → file → environment → CLI overrides
>   - Validation: custom validators per field
> - Quality:
>   - Doc comments on EVERY public item with examples (verified by doc tests)
>   - `#![warn(missing_docs)]` — enforce documentation
>   - Unit tests, integration tests, doc tests
>   - `rstest` for parameterized tests
>   - `criterion` benchmarks for hot paths
>   - `clippy::pedantic` with zero warnings
>   - `cargo deny` — license and security audit
>   - `cargo udeps` — no unused dependencies
> - Features:
>   - `toml` feature (default), `json` feature (optional)
>   - `#[cfg(feature)]` for conditional compilation
> - CI: GitHub Actions pipeline — fmt check, clippy, test, doc, build, benchmark
> - Workspace: library crate + example binary crate

---

## ⚡ PHASE 9 — MACROS & METAPROGRAMMING
> *"Rust macros are not textual substitution. They're code that generates code."*

---

### 📦 Module 9.1: Declarative Macros (`macro_rules!`)

#### § 9.1.1 — Macro Fundamentals
  - `macro_rules! name { (pattern) => { expansion }; }` — define a macro
  - Invocation: `name!()`, `name![]`, `name!{}`
  - Fragment specifiers: `$x:expr`, `$x:ident`, `$x:ty`, `$x:pat`, `$x:stmt`, `$x:block`, `$x:literal`, `$x:tt`
  - Repetition: `$( $x:expr ),*` — zero or more, `$( $x:expr ),+` — one or more

#### § 9.1.2 — Common Macro Patterns
  - Variadic arguments: `vec![1, 2, 3]` — accepting variable number of arguments
  - Multiple match arms: different expansion for different patterns
  - Recursive macros: macro calling itself for recursive patterns
  - TT munching: processing token trees one at a time
  - Internal rules: `@internal` pattern for helper rules within macros

#### § 9.1.3 — Macro Best Practices
  - Use macros as last resort — prefer functions and generics first
  - Keep macros simple and well-documented
  - Test macros through their expanded output (`cargo expand`)
  - Macro hygiene: Rust macros are hygienic (local variables don't leak)

---

### 📦 Module 9.2: Procedural Macros

#### § 9.2.1 — Types of Procedural Macros
  - **Derive macros**: `#[derive(MyTrait)]` — auto-implement traits
  - **Attribute macros**: `#[my_attribute]` — transform annotated items
  - **Function-like macros**: `my_macro!(...)` — called like declarative macros
  - Proc macros must be in a separate crate (`proc-macro = true`)

#### § 9.2.2 — Building Derive Macros
  - Input: `TokenStream` (the annotated struct/enum)
  - Parse with `syn` crate — parse Rust syntax into AST
  - Generate code with `quote` crate — produce `TokenStream` from Rust-like syntax
  - Output: `TokenStream` (the implementation code)
  - `syn::parse_macro_input!` — parse input
  - `quote::quote!` — generate code
  - Attributes on fields: `#[my_attr(option)]` — customize behavior per field

#### § 9.2.3 — Building Attribute Macros
  - Transform the entire item (function, struct, impl block)
  - Can add, remove, or modify the item
  - Use case: logging, timing, route definitions, serialization customization

#### § 9.2.4 — Popular Macro Crates
  - `serde` — the most important derive macros in Rust (`Serialize`, `Deserialize`)
  - `thiserror` — derive `Error` implementation
  - `clap` — derive CLI argument parser
  - `tokio::select!`, `tokio::join!` — async macros
  - `sqlx` — compile-time SQL query checking

---

### 📦 Module 9.3: `serde` — Serialization Framework

#### § 9.3.1 — `serde` Fundamentals
  - `#[derive(Serialize, Deserialize)]` — auto-generate serialization code
  - Data format agnostic: JSON, TOML, YAML, MessagePack, Bincode, etc.
  - `serde_json`, `serde_yaml`, `toml` — format-specific crates
  - `#[serde(rename = "name")]` — field renaming
  - `#[serde(rename_all = "camelCase")]` — rename all fields
  - `#[serde(skip)]`, `#[serde(default)]`, `#[serde(flatten)]`
  - `#[serde(tag = "type")]` — tagged enum serialization
  - Custom serialization: `serialize_with`, `deserialize_with`

> ### 🛠️ Phase 9 Project: **"DeriveBuilder — A Custom Derive Macro"**
> Build a procedural derive macro:
> - `#[derive(Builder)]` — auto-generate a builder pattern for any struct
> - For each field `name: T`, generate:
>   - Builder field: `name: Option<T>`
>   - Setter method: `fn name(mut self, val: T) -> Self`
>   - Validation in `build()`: check all required fields are set, return `Result`
> - Attribute support: `#[builder(default)]` for optional fields with defaults
> - Attribute support: `#[builder(each = "item")]` for `Vec<T>` fields — add one at a time
> - The macro crate: `derive_builder_macro` (proc-macro crate)
> - The usage crate: tests and examples
> - Comprehensive error messages for missing fields using `compile_error!`
> - Test with `trybuild` crate (compilation test — verify that invalid usage produces correct errors)

---

## ⚡ PHASE 10 — WEB DEVELOPMENT & NETWORKING
> *"Rust is the fastest-growing language for web backends. The performance is unmatched."*

---

### 📦 Module 10.1: HTTP Servers

#### § 10.1.1 — Axum (The Modern Standard)
  - Built on Tokio + Tower + Hyper — the official Tokio web framework
  - Routing: `Router::new().route("/users", get(list_users).post(create_user))`
  - Extractors: `Path<T>`, `Query<T>`, `Json<T>`, `State<T>` — type-safe request parsing
  - Response types: `Json<T>`, `StatusCode`, `impl IntoResponse`
  - Middleware via Tower layers: logging, CORS, compression, auth
  - Shared state: `State<Arc<AppState>>` — inject application state
  - Error handling: `Result<Json<T>, AppError>` with `IntoResponse` for errors

#### § 10.1.2 — Actix Web (Performance-Focused)
  - Actor-based architecture
  - Extremely high performance benchmarks
  - `#[get("/")]`, `#[post("/")]` — attribute macros for routing
  - Extractors: `web::Path`, `web::Json`, `web::Query`
  - Middleware system
  - When to choose: maximum raw performance, actor model preference

#### § 10.1.3 — Other Frameworks
  - `Rocket` — ergonomic, macro-heavy (slower compile times)
  - `Warp` — filter-based, composable
  - `Poem` — simple and elegant
  - Choosing: Axum for new projects (Tokio ecosystem), Actix for raw performance

---

### 📦 Module 10.2: Database Access

#### § 10.2.1 — SQLx (Compile-Time Checked SQL)
  - Async, pure Rust database driver
  - `sqlx::query!("SELECT * FROM users WHERE id = $1", id)` — SQL checked at compile time
  - Supports: PostgreSQL, MySQL, SQLite
  - Connection pools: `PgPool`
  - Migrations: `sqlx migrate run`
  - `sqlx::FromRow` derive — map rows to structs

#### § 10.2.2 — Diesel (Type-Safe ORM)
  - Full ORM with query builder
  - Schema defined in Rust, type-checked at compile time
  - Synchronous only (use with `tokio::task::spawn_blocking`)
  - Migrations: `diesel migration run`
  - Strong type safety but steep learning curve

#### § 10.2.3 — SeaORM (Async ORM)
  - Async ORM built on SQLx
  - Active record and entity-based patterns
  - Migration and schema generation
  - Integration with Axum, Actix

---

### 📦 Module 10.3: HTTP Client & Networking

#### § 10.3.1 — `reqwest` — HTTP Client
  - `reqwest::Client` — connection pooling, cookie management
  - `client.get(url).send().await?` — async HTTP request
  - JSON: `response.json::<T>().await?` — deserialize with `serde`
  - Form, multipart, headers, authentication
  - Timeout, redirect policy, proxy configuration

#### § 10.3.2 — `tonic` — gRPC
  - Protocol Buffers code generation
  - Client and server implementation
  - Streaming: unary, server, client, bidirectional
  - Interceptors (middleware)

#### § 10.3.3 — WebSockets
  - `tokio-tungstenite` — async WebSocket
  - `axum::extract::ws::WebSocket` — WebSocket in Axum
  - Real-time bidirectional communication

---

### 📦 Module 10.4: API Design Patterns

#### § 10.4.1 — REST API Design in Rust
  - Type-safe request/response with `serde` + Axum extractors
  - Validation with `validator` crate
  - Error handling with custom `AppError` implementing `IntoResponse`
  - Authentication middleware with Tower layers
  - Pagination, filtering, sorting — typed query parameters

#### § 10.4.2 — API Documentation
  - `utoipa` — OpenAPI (Swagger) documentation generation
  - `aide` — Axum-native API documentation
  - Derive macros for auto-generating OpenAPI schemas from Rust types

> ### 🛠️ Phase 10 Project: **"RustAPI — A Production REST API"**
> Build a complete REST API:
> - **Framework**: Axum + SQLx (PostgreSQL) + Tokio
> - **Entities**: User, Project, Task, Comment — with typed relations
> - **Features**:
>   - JWT authentication with refresh tokens
>   - CRUD for all entities with proper authorization
>   - Request validation with `validator`
>   - Pagination, filtering, sorting — type-safe query parameters
>   - File upload handling
>   - Rate limiting middleware (Tower layer)
>   - Graceful shutdown
>   - Database connection pooling and migrations
> - **Architecture**:
>   - Layered: Handler → Service → Repository
>   - `thiserror` for domain errors, `anyhow` in handlers
>   - Custom `AppError` with `IntoResponse`
>   - Newtype IDs: `UserId(Uuid)`, `TaskId(Uuid)`
>   - `serde` for all serialization/deserialization
> - **Quality**:
>   - Unit tests with mock repositories
>   - Integration tests with real PostgreSQL (`testcontainers`)
>   - `clippy::pedantic`, `cargo fmt`
>   - OpenAPI docs with `utoipa`
>   - Docker + docker-compose

---

## ⚡ PHASE 11 — UNSAFE RUST, FFI & SYSTEMS PROGRAMMING
> *"Unsafe Rust is not 'bad Rust.' It's 'Rust where you take responsibility.'"*

---

### 📦 Module 11.1: Unsafe Rust

#### § 11.1.1 — What `unsafe` Means
  - Five things only possible in `unsafe` blocks:
    1. Dereference raw pointers
    2. Call unsafe functions/methods
    3. Access mutable static variables
    4. Implement unsafe traits
    5. Access fields of unions
  - `unsafe` does NOT disable the borrow checker — everything else is still checked
  - `unsafe` is a contract: the programmer guarantees invariants the compiler can't verify

#### § 11.1.2 — Raw Pointers
  - `*const T` — immutable raw pointer
  - `*mut T` — mutable raw pointer
  - Can be null, can be dangling, can alias mutably
  - Creating raw pointers is safe — dereferencing requires `unsafe`
  - Use case: FFI, performance-critical code, implementing data structures

#### § 11.1.3 — Unsafe Functions & Traits
  - `unsafe fn dangerous() { ... }` — caller must uphold invariants
  - Safe abstraction over unsafe code: the fundamental pattern
  - `unsafe impl Send for MyType {}` — asserting thread safety
  - Documenting safety invariants: `# Safety` section in doc comments

#### § 11.1.4 — Unsafe Best Practices
  - Minimize `unsafe` surface area — small, auditable blocks
  - Wrap `unsafe` in safe abstractions with checked APIs
  - Document every invariant that must be upheld
  - Validate with `miri`: `cargo +nightly miri test`
  - Review unsafe code carefully — bugs here cause real UB

---

### 📦 Module 11.2: FFI (Foreign Function Interface)

#### § 11.2.1 — Calling C from Rust
  - `extern "C" { fn c_function(arg: c_int) -> c_int; }` — declare C function
  - `libc` crate — C standard library type definitions
  - `std::ffi::CStr`, `CString` — C string interop (null-terminated)
  - `bindgen` — auto-generate Rust bindings from C headers
  - Linking: `#[link(name = "mylib")]`
  - Build scripts (`build.rs`) for compiling C code with `cc` crate

#### § 11.2.2 — Calling Rust from C
  - `#[no_mangle] pub extern "C" fn rust_function(x: i32) -> i32 { ... }`
  - `cbindgen` — auto-generate C headers from Rust code
  - Creating shared libraries (`.so`, `.dylib`, `.dll`)
  - `crate-type = ["cdylib"]` in `Cargo.toml`

#### § 11.2.3 — Calling Rust from Python
  - `PyO3` — Rust bindings for Python
  - `maturin` — build and publish Rust Python extensions
  - Type conversion between Python and Rust types
  - GIL management
  - Building Python packages with Rust performance

#### § 11.2.4 — Calling Rust from Other Languages
  - Node.js: `napi-rs` — Rust bindings for Node.js native modules
  - WebAssembly: `wasm-bindgen`, `wasm-pack` — compile Rust to WASM
  - Swift/Kotlin: UniFFI (Mozilla) — auto-generate bindings

---

### 📦 Module 11.3: Systems Programming

#### § 11.3.1 — CLI Application Development
  - `clap` — the standard CLI argument parser (derive macros + builder)
  - `clap` subcommands, flags, arguments, validation
  - `indicatif` — progress bars and spinners
  - `dialoguer` — interactive prompts
  - `console` — terminal styling and colors
  - `crossterm` — cross-platform terminal manipulation

#### § 11.3.2 — File System & OS Interaction
  - `std::fs` — file operations
  - `std::path::Path`, `PathBuf` — path manipulation
  - `std::process::Command` — running external commands
  - `std::env` — environment variables, arguments
  - `walkdir` — recursive directory traversal
  - `notify` — file system event watching
  - `tempfile` — temporary files and directories

#### § 11.3.3 — Embedded & No-Std Rust
  - `#![no_std]` — disable standard library (bare metal)
  - `core` library — always available (types, traits, primitives)
  - `alloc` library — heap allocation without full `std`
  - Embedded Rust: `cortex-m`, `embedded-hal`, `probe-rs`
  - Use case: microcontrollers, kernels, bootloaders, firmware

#### § 11.3.4 — WebAssembly
  - `wasm32-unknown-unknown` target
  - `wasm-bindgen` — JavaScript interop
  - `wasm-pack` — build and publish WASM packages
  - `web-sys`, `js-sys` — browser API bindings
  - Use case: performance-critical browser code, plugins, edge computing

> ### 🛠️ Phase 11 Project: **"RustShell — A Systems Programming Showcase"**
> Build a Unix shell clone demonstrating systems programming:
> - **Core**: command execution with `std::process::Command`
> - **Built-in commands**: `cd`, `pwd`, `echo`, `exit`, `history`, `export`, `env`
> - **Piping**: `ls | grep .rs | wc -l` — connect stdout → stdin across commands
> - **Redirection**: `>`, `>>`, `<`, `2>`
> - **Background jobs**: `command &`, `jobs`, `fg`, `bg`
> - **Signal handling**: Ctrl+C, Ctrl+Z (using `signal-hook` or `ctrlc` crate)
> - **Tab completion**: basic path/command completion
> - **History**: persistent command history to file
> - **Environment variables**: get/set/unset
> - **CLI**: built with `clap` for the shell's own flags
> - **Unsafe**: minimal use for signal handling and process control
> - **FFI demo**: call one C library function (e.g., `libc::getpid`) and wrap it safely
> - **Cross-platform**: handle differences between Linux and macOS
> - Tests for built-in commands and piping logic

---

## ⚡ PHASE 12 — DESIGN PATTERNS, ARCHITECTURE & PRODUCTION RUST
> *"Idiomatic Rust doesn't look like C++, Java, or Go. It has its own patterns."*

---

### 📦 Module 12.1: Rust-Specific Design Patterns

#### § 12.1.1 — Builder Pattern
  - Builder struct with setter methods returning `Self`
  - `build()` method returning `Result<T, BuilderError>`
  - Typestate pattern: builder states encoded in the type system (compile-time checked required fields)
  - `#[derive(Builder)]` with the `derive_builder` crate or custom proc macro

#### § 12.1.2 — Newtype Pattern
  - `struct Email(String)` — type safety for primitives
  - Validated constructors: `impl Email { fn new(s: &str) -> Result<Self, ValidationError> }`
  - `Deref` implementation for ergonomic access
  - Use case: preventing ID mixing, units of measurement, validated types

#### § 12.1.3 — Typestate Pattern
  - Encode state transitions in the type system
  - Different states are different types: `Request<Unauthenticated>`, `Request<Authenticated>`
  - Invalid transitions are compile errors
  - Zero-size types as state markers: `struct Locked; struct Unlocked;`

#### § 12.1.4 — RAII & Guard Pattern
  - Resources acquired in constructors, released in `Drop`
  - `MutexGuard` — auto-release lock on drop
  - File handles, database connections, temporary files
  - Scope-based resource management

#### § 12.1.5 — Extension Trait Pattern
  - Add methods to foreign types by defining a new trait
  - `trait IteratorExt: Iterator { fn my_method(self) -> ... }`
  - Blanket implementation: `impl<I: Iterator> IteratorExt for I { ... }`
  - Use case: extending standard library types, adding domain-specific methods

#### § 12.1.6 — Command Pattern
  - `enum Command { Create(Data), Update(Id, Data), Delete(Id) }`
  - Process with `match` — exhaustive handling
  - Undo support: store reverse commands

---

### 📦 Module 12.2: Architectural Patterns

#### § 12.2.1 — Clean Architecture in Rust
  - Domain layer: structs, enums, traits (no external dependencies)
  - Application layer: use cases, service traits
  - Infrastructure layer: database, HTTP, file system implementations
  - Traits as interfaces at boundaries
  - Dependency injection via generics and trait bounds

#### § 12.2.2 — Repository Pattern
  - `trait UserRepository { async fn find_by_id(&self, id: UserId) -> Result<User, RepoError>; }`
  - Implementations: `PostgresUserRepo`, `InMemoryUserRepo` (for testing)
  - Generic services: `struct UserService<R: UserRepository> { repo: R }`

#### § 12.2.3 — Error Architecture
  - Library errors: enum with `thiserror` derive
  - Application errors: `anyhow` for flexible error handling
  - Error conversion chain: domain → application → API response
  - Per-layer error types with `From` implementations

#### § 12.2.4 — Configuration Management
  - `config` crate — layered configuration
  - `dotenvy` — environment variable loading
  - Type-safe config structs with `serde::Deserialize`
  - Feature flags with `cfg` attributes

---

### 📦 Module 12.3: Production Hardening

#### § 12.3.1 — Observability
  - `tracing` crate — structured, context-aware logging (the standard)
  - `tracing-subscriber` — log formatting and filtering
  - `tracing::instrument` — auto-instrument functions with spans
  - `tracing-opentelemetry` — distributed tracing
  - `metrics` crate — Prometheus-compatible metrics
  - `opentelemetry-rust` — OpenTelemetry SDK

#### § 12.3.2 — Resilience Patterns
  - Retry with backoff: custom implementation or `backon` crate
  - Circuit breaker pattern
  - Timeouts: `tokio::time::timeout`
  - Graceful shutdown: `tokio::signal`, `CancellationToken`
  - Health checks: liveness and readiness endpoints

#### § 12.3.3 — Deployment
  - Docker multi-stage builds: `rust:1.XX` (build) → `debian:bookworm-slim` or `scratch` (runtime)
  - Static linking with `musl`: `x86_64-unknown-linux-musl` target — single binary, no dependencies
  - Cross-compilation: `cross` tool
  - Binary size optimization: `strip`, `opt-level`, `lto`, `codegen-units = 1`
  - CI/CD: GitHub Actions with caching (`Swatinem/rust-cache`)

#### § 12.3.4 — Security
  - `cargo audit` — check for known vulnerabilities in dependencies
  - `cargo deny` — license compliance, advisory database, duplicate detection
  - Input validation on all external boundaries
  - `secrecy` crate — wrap secrets to prevent accidental logging
  - `argon2` / `bcrypt` — password hashing
  - Constant-time comparison: `subtle` crate

---

### 📦 Module 12.4: Ecosystem Awareness

#### § 12.4.1 — Essential Crates to Know
  - **Serialization**: `serde`, `serde_json`, `toml`, `serde_yaml`, `bincode`
  - **Async**: `tokio`, `async-trait`, `futures`
  - **Web**: `axum`, `reqwest`, `hyper`, `tower`
  - **Database**: `sqlx`, `diesel`, `sea-orm`
  - **CLI**: `clap`, `indicatif`, `dialoguer`, `console`
  - **Error**: `thiserror`, `anyhow`, `miette` (pretty errors)
  - **Logging**: `tracing`, `tracing-subscriber`, `env_logger`
  - **Testing**: `mockall`, `rstest`, `criterion`, `proptest`, `fake`
  - **Crypto**: `ring`, `rustls`, `argon2`
  - **Date/Time**: `chrono`, `time`
  - **Regex**: `regex`
  - **Random**: `rand`
  - **UUID**: `uuid`

> ### 🛠️ Phase 12 Capstone Project: **"Forgekeeper — A Production-Grade Key-Value Store"**
> Build a Redis-inspired in-memory key-value store:
>
> - **Networking**: async TCP server with Axum or raw `tokio::net`
> - **Protocol**: implement a subset of RESP (Redis Serialization Protocol)
> - **Commands**: `SET`, `GET`, `DEL`, `EXISTS`, `EXPIRE`, `TTL`, `KEYS`, `INCR`, `LPUSH`, `LPOP`, `LRANGE`, `PING`, `INFO`
>
> - **Data Structures**:
>   - Strings: `String`
>   - Lists: `VecDeque<String>`
>   - Hashes: `HashMap<String, String>`
>   - Value type: `enum Value { String(String), List(VecDeque<String>), Hash(HashMap<String, String>) }`
>
> - **Features**:
>   - Key expiration: background task sweeps expired keys using `tokio::time`
>   - Persistence: RDB-style snapshotting to binary