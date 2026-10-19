# ☕ THE ULTIMATE JAVA ROADMAP
### From Zero to Enterprise-Grade Java Mastery

> **Structure:** Phase → Modules → Sections
> **Estimated Duration:** ~8-12 Months (Dedicated Study)
> **Prerequisite:** None — starts from absolute zero

---

## ⚡ PHASE 0 — ENVIRONMENT SETUP & JAVA ORIENTATION
> *"Java is not just a language. It's a platform, an ecosystem, and a philosophy."*

---

### 📦 Module 0.1: Understanding Java's Identity

#### § 0.1.1 — What is Java & Why It Matters
  - History: James Gosling, Sun Microsystems (1995) → Oracle (2010)
  - Java's philosophy: "Write Once, Run Anywhere" (WORA)
  - Where Java dominates: enterprise backends, Android, big data (Hadoop/Spark), banking, government, microservices

#### § 0.1.2 — How Java Works: The JVM Architecture
  - Source code (`.java`) → Compiler (`javac`) → Bytecode (`.class`)
  - JVM (Java Virtual Machine): loads and executes bytecode
  - JVM components: ClassLoader, Bytecode Verifier, Interpreter, JIT Compiler
  - JRE (Java Runtime Environment) vs JDK (Java Development Kit)
  - Platform independence through abstraction

#### § 0.1.3 — Java Editions
  - **Java SE** (Standard Edition) — core language + libraries
  - **Java EE / Jakarta EE** (Enterprise Edition) — web, enterprise
  - **Java ME** (Micro Edition) — embedded (mostly legacy)
  - **Android SDK** — Android development (uses Java/Kotlin)

#### § 0.1.4 — Java Version History & LTS Strategy
  - **Java 8** (LTS) — lambdas, streams, Optional (the revolution)
  - **Java 11** (LTS) — modules matured, `var`, HTTP client
  - **Java 17** (LTS) — sealed classes, records, pattern matching preview
  - **Java 21** (LTS) — virtual threads, pattern matching, sequenced collections
  - **Java 25** (LTS — 2025) — latest stable
  - Release cadence: every 6 months, LTS every 2 years
  - Always target the latest LTS for production

---

### 📦 Module 0.2: Setting Up the Development Environment

#### § 0.2.1 — Installing the JDK
  - **Oracle JDK** vs **OpenJDK** vs **Amazon Corretto** vs **Eclipse Temurin (Adoptium)**
  - Installing on Linux: `sudo apt install openjdk-21-jdk`
  - Installing on macOS: `brew install openjdk@21`
  - Installing on Windows: Adoptium installer
  - Setting `JAVA_HOME` and `PATH` environment variables
  - Verifying: `java --version`, `javac --version`

#### § 0.2.2 — Choosing an IDE
  - **IntelliJ IDEA** (Community/Ultimate) — the industry standard (strongly recommended)
  - **Eclipse** — legacy but powerful
  - **VS Code** + Extension Pack for Java
  - **NetBeans** — simpler, good for beginners
  - Why IntelliJ wins: refactoring, debugging, Spring integration, code analysis

#### § 0.2.3 — Your First Java Program
  - Creating `HelloWorld.java`
  - Compiling: `javac HelloWorld.java`
  - Running: `java HelloWorld`
  - Understanding the `public static void main(String[] args)` entry point
  - Java 21+ simplified: `void main()` (preview — instance main methods)

#### § 0.2.4 — Essential Tooling Introduction
  - **Maven** vs **Gradle** — build tools (overview, deep dive later)
  - **Git** — version control basics
  - **JShell** — Java REPL for quick experimentation (`jshell`)

---

### 📦 Module 0.3: JVM Internals Overview (High Level)

#### § 0.3.1 — Memory Areas
  - **Stack** — method frames, local variables (per thread)
  - **Heap** — object storage (shared across threads)
  - **Method Area / Metaspace** — class metadata
  - **Program Counter Register** — per thread

#### § 0.3.2 — Garbage Collection (Introduction)
  - What is GC? (automatic memory management)
  - Why Java developers don't call `free()`
  - GC roots, reachability analysis
  - `System.gc()` — a suggestion, not a command
  - Deep dive deferred to Phase 10

> ### 🛠️ Phase 0 Project: **"JVM Inspector"**
> Write a Java program that prints:
> - Java version, JVM name, vendor (`System.getProperty()`)
> - Available processors (`Runtime.getRuntime().availableProcessors()`)
> - Max/total/free heap memory (`Runtime.getRuntime().maxMemory()`, etc.)
> - All system properties and environment variables
> - OS name, architecture, user home directory
> - Run it from the CLI, from JShell, AND from IntelliJ. Screenshot all three.

---

## ⚡ PHASE 1 — JAVA LANGUAGE FUNDAMENTALS
> *"Java is strict, verbose, and explicit — and that's a feature, not a bug."*

---

### 📦 Module 1.1: Basic Syntax & Program Structure

#### § 1.1.1 — Program Structure & Conventions
  - One public class per file, filename must match class name
  - `package` declarations and directory structure
  - `import` statements, wildcard imports (`import java.util.*`)
  - Static imports: `import static java.lang.Math.PI`
  - Java naming conventions: `PascalCase` (classes), `camelCase` (methods/variables), `UPPER_SNAKE` (constants)

#### § 1.1.2 — Comments & Documentation
  - Single-line: `//`
  - Multi-line: `/* */`
  - **Javadoc**: `/** */` — `@param`, `@return`, `@throws`, `@see`, `@since`
  - Generating Javadoc: `javadoc -d docs *.java`

#### § 1.1.3 — Statements, Blocks & Semicolons
  - Every statement ends with `;`
  - Code blocks `{}` define scope
  - Blank `main` method as skeleton

---

### 📦 Module 1.2: Primitive Data Types

#### § 1.2.1 — The 8 Primitive Types
  - `byte` (8-bit, -128 to 127)
  - `short` (16-bit)
  - `int` (32-bit) — default integer type
  - `long` (64-bit) — suffix `L`: `100L`
  - `float` (32-bit IEEE 754) — suffix `f`: `3.14f`
  - `double` (64-bit IEEE 754) — default floating type
  - `char` (16-bit Unicode, UTF-16)
  - `boolean` (`true` / `false`) — NOT an integer in Java!

#### § 1.2.2 — Literals & Type Suffixes
  - Integer literals: decimal, hex (`0x`), octal (`0`), binary (`0b`)
  - Underscore separators: `1_000_000`
  - Floating-point: `3.14`, `3.14f`, `3.14d`, `1.5e10`
  - Character: `'A'`, `'\n'`, `'\u0041'`
  - String: `"Hello"`, text blocks (Java 13+): `""" multi-line """`
  - `null` — absence of reference

#### § 1.2.3 — Type Casting & Promotion
  - **Widening** (implicit): `int` → `long` → `float` → `double`
  - **Narrowing** (explicit): `int x = (int) 3.14;`
  - Integer promotion in expressions
  - Loss of precision: `int` → `float` (32-bit float can't hold all 32-bit ints)

---

### 📦 Module 1.3: Variables & Constants

#### § 1.3.1 — Variable Declaration & Initialization
  - Declaration: `int age;`
  - Initialization: `int age = 25;`
  - Local variables MUST be initialized before use
  - Instance variables have default values (`0`, `false`, `null`)

#### § 1.3.2 — `var` — Local Variable Type Inference (Java 10+)
  - `var list = new ArrayList<String>();`
  - Only for local variables with initializers
  - Cannot use for: fields, method parameters, return types
  - Best practices: use when the type is obvious from the RHS

#### § 1.3.3 — Constants
  - `final` keyword: `final int MAX = 100;`
  - `static final` — class-level constant
  - Naming convention: `UPPER_SNAKE_CASE`

---

### 📦 Module 1.4: Operators (Complete)

#### § 1.4.1 — Arithmetic Operators
  - `+`, `-`, `*`, `/`, `%`
  - Integer division: `7 / 2 == 3` (truncates!)
  - `++`, `--` (prefix vs. postfix)

#### § 1.4.2 — Comparison & Logical Operators
  - `==`, `!=`, `<`, `>`, `<=`, `>=`
  - `==` on objects: compares REFERENCES, not content! (use `.equals()`)
  - `&&`, `||`, `!` — short-circuit
  - `&`, `|` — non-short-circuit (evaluate both sides)

#### § 1.4.3 — Bitwise Operators
  - `&`, `|`, `^`, `~`
  - `<<`, `>>` (signed), `>>>` (unsigned right shift — Java-specific!)

#### § 1.4.4 — Assignment & Ternary
  - `=`, `+=`, `-=`, `*=`, `/=`, `%=`, `<<=`, `>>=`, `>>>=`, `&=`, `|=`, `^=`
  - Ternary: `int max = (a > b) ? a : b;`

#### § 1.4.5 — `instanceof` Operator
  - `if (obj instanceof String)` — type checking
  - Pattern matching instanceof (Java 16+): `if (obj instanceof String s)`

---

### 📦 Module 1.5: Control Flow

#### § 1.5.1 — Conditional Statements
  - `if`, `else if`, `else`
  - `switch` — traditional (with `break` and fall-through)
  - **Switch expressions** (Java 14+): `var result = switch(x) { case 1 -> "one"; ... };`
  - Arrow syntax: `case 1 -> value;` (no fall-through)
  - `yield` keyword in switch blocks

#### § 1.5.2 — Loops
  - `for` loop (classic C-style)
  - **Enhanced for-each**: `for (String s : list)`
  - `while`, `do-while`
  - `break`, `continue`
  - Labeled break/continue: `outer: for (...) { break outer; }`

#### § 1.5.3 — Scope Rules
  - Block scope for local variables
  - No re-declaration in nested blocks (unlike C/C++)
  - Variable shadowing rules

---

### 📦 Module 1.6: Arrays

#### § 1.6.1 — Array Declaration & Initialization
  - `int[] arr = new int[5];` (preferred syntax)
  - `int[] arr = {1, 2, 3, 4, 5};`
  - `int arr[] = ...;` (C-style, discouraged)
  - Arrays are objects in Java (live on the heap)
  - `arr.length` (property, not method)

#### § 1.6.2 — Multi-Dimensional Arrays
  - `int[][] matrix = new int[3][4];`
  - Jagged arrays: `int[][] jagged = new int[3][];`
  - Iterating 2D arrays

#### § 1.6.3 — `java.util.Arrays` Utility Class
  - `Arrays.sort()`, `Arrays.binarySearch()`
  - `Arrays.fill()`, `Arrays.copyOf()`, `Arrays.copyOfRange()`
  - `Arrays.equals()`, `Arrays.deepEquals()`
  - `Arrays.toString()`, `Arrays.deepToString()`
  - `Arrays.stream()` — bridge to streams (Java 8+)

> ### 🛠️ Phase 1 Project: **"GradeBook CLI Application"**
> Build a student grade management CLI tool:
> 1. Store student names and grades in parallel arrays (or a 2D array)
> 2. **Calculate**: average, highest, lowest, median, standard deviation
> 3. **Sort** students by grade (using `Arrays.sort` with a copy)
> 4. **Search** for a student by name (linear and binary search)
> 5. **Grade distribution**: A (90+), B (80+), C (70+), D (60+), F (<60) — histogram using `*` chars
> 6. Use **switch expressions** for menu navigation
> 7. Use **text blocks** for the welcome banner
> 8. Handle invalid input gracefully

---

## ⚡ PHASE 2 — OBJECT-ORIENTED PROGRAMMING (OOP) — CORE
> *"Java IS OOP. Everything lives inside a class."*

---

### 📦 Module 2.1: Classes & Objects

#### § 2.1.1 — Defining a Class
  - Fields (instance variables), methods, constructors
  - `new` keyword — object instantiation on the heap
  - Object references vs. objects (references are on the stack, objects on the heap)
  - `null` references and `NullPointerException`

#### § 2.1.2 — Constructors
  - Default constructor (compiler-generated if none defined)
  - Parameterized constructors
  - Constructor overloading
  - Constructor chaining: `this(args)` — calling another constructor
  - No return type for constructors
  - Copy constructors (manual — Java has no built-in)

#### § 2.1.3 — The `this` Keyword
  - Referring to current instance: `this.name = name;`
  - Passing `this` as an argument
  - Returning `this` for method chaining (fluent API)

#### § 2.1.4 — Access Modifiers
  - `public` — accessible everywhere
  - `private` — accessible only within the class
  - `protected` — accessible within package + subclasses
  - **default** (no modifier) — package-private (accessible within the package)
  - Access modifier summary table (class, package, subclass, world)

#### § 2.1.5 — Getters, Setters & Encapsulation
  - Private fields + public getters/setters
  - Validation in setters
  - Why direct field access is an anti-pattern
  - JavaBeans convention: `getName()`, `setName()`, `isActive()`

---

### 📦 Module 2.2: Methods — Deep Dive

#### § 2.2.1 — Method Signatures & Overloading
  - Method signature: name + parameter types
  - Overloading: same name, different parameters
  - Overloading resolution: most specific match
  - Varargs: `void print(String... args)` — variable-length arguments

#### § 2.2.2 — Pass-by-Value Semantics
  - Java is ALWAYS pass-by-value
  - Primitives: copy of the value
  - Objects: copy of the REFERENCE (not the object!)
  - Proving it: reassigning a parameter inside a method doesn't affect the caller
  - But: modifying the object via the reference DOES affect the original

#### § 2.2.3 — `static` Methods & Fields
  - Belong to the class, not to instances
  - `ClassName.method()` — called without an object
  - `static` fields: shared across all instances
  - `static` blocks: `static { ... }` — class initialization
  - Cannot access instance members from `static` context
  - Use cases: utility methods (`Math.sqrt()`), counters, factories

#### § 2.2.4 — `final` Keyword (Methods & Variables)
  - `final` variable: cannot be reassigned (but object contents can change!)
  - `final` method: cannot be overridden
  - `final` class: cannot be extended
  - `final` parameters: cannot be reassigned inside the method
  - Effective finality (lambdas require it)

---

### 📦 Module 2.3: Core Java Classes

#### § 2.3.1 — The `Object` Class (Root of All)
  - Every class extends `Object` implicitly
  - Key methods:
    - `toString()` — string representation (override it!)
    - `equals(Object obj)` — content equality (override it!)
    - `hashCode()` — hash value (override it with `equals`!)
    - `getClass()` — runtime class info
    - `clone()` — shallow copy (use carefully)
    - `finalize()` — deprecated, never use

#### § 2.3.2 — The `equals()` and `hashCode()` Contract
  - If `a.equals(b)` then `a.hashCode() == b.hashCode()`
  - The converse is NOT necessarily true
  - Implementing `equals()`: reflexive, symmetric, transitive, consistent
  - Using `Objects.equals()` and `Objects.hash()` helpers
  - IDE auto-generation of `equals`/`hashCode`

#### § 2.3.3 — The `String` Class (Immutable)
  - Strings are immutable — every modification creates a new object
  - String pool (interning): `"hello" == "hello"` is `true` (same pool reference)
  - `new String("hello")` — bypasses the pool
  - Essential methods: `length()`, `charAt()`, `substring()`, `indexOf()`, `contains()`, `replace()`, `split()`, `trim()`, `strip()`, `toLowerCase()`, `toUpperCase()`, `startsWith()`, `endsWith()`, `isEmpty()`, `isBlank()`
  - `String.format()`, `formatted()` (Java 15+)
  - `StringBuilder` — mutable, not thread-safe (use for building strings in loops)
  - `StringBuffer` — mutable, thread-safe (legacy, prefer `StringBuilder`)
  - String comparison: ALWAYS use `.equals()`, NEVER use `==`

#### § 2.3.4 — Wrapper Classes & Autoboxing
  - `Integer`, `Double`, `Boolean`, `Character`, `Long`, `Float`, `Short`, `Byte`
  - Autoboxing: `Integer x = 5;` (primitive → wrapper automatic)
  - Unboxing: `int y = x;` (wrapper → primitive automatic)
  - Integer cache: `-128` to `127` (why `==` works for small Integers)
  - `parseInt()`, `valueOf()`, `MAX_VALUE`, `MIN_VALUE`
  - `NullPointerException` from unboxing `null`

---

### 📦 Module 2.4: Memory Model for Objects

#### § 2.4.1 — Stack vs. Heap
  - Stack: primitives, local variables, references
  - Heap: objects, arrays, strings
  - Each thread has its own stack, heap is shared

#### § 2.4.2 — Object Lifecycle
  - Creation (`new`) → Usage → Eligibility for GC → Garbage Collection
  - Making objects eligible: nullifying references, going out of scope
  - No manual `free()` or `delete`

#### § 2.4.3 — Reference Types
  - Strong references (default)
  - `WeakReference<T>` — doesn't prevent GC
  - `SoftReference<T>` — GC'd only under memory pressure (caching)
  - `PhantomReference<T>` — for cleanup actions (advanced)

> ### 🛠️ Phase 2 Project: **"BankAccount System"**
> Build an object-oriented banking system:
> - `class BankAccount` — fields: `accountNumber`, `ownerName`, `balance`, `accountType` (enum: SAVINGS, CHECKING)
> - **Methods**: `deposit()`, `withdraw()` (with validation), `transfer(BankAccount target, double amount)`
> - Override `toString()`, `equals()`, `hashCode()`
> - `class Bank` — manages a collection of `BankAccount[]`
>   - `createAccount()`, `findAccount()`, `getTotalAssets()`, `getAccountsByType()`
> - `class TransactionLog` — static utility class that logs every transaction with timestamps
> - Use `StringBuilder` for formatted reports
> - Proper encapsulation: all fields `private`, validated setters
> - CLI menu with `Scanner` for interactive use

---

## ⚡ PHASE 3 — OOP ADVANCED: INHERITANCE, POLYMORPHISM & ABSTRACTION
> *"The four pillars: Encapsulation, Inheritance, Polymorphism, Abstraction."*

---

### 📦 Module 3.1: Inheritance

#### § 3.1.1 — Extending Classes
  - `class Dog extends Animal { ... }`
  - `super` keyword: accessing parent constructor, methods, fields
  - `super()` must be first statement in constructor
  - Constructor chaining through the hierarchy
  - Java is **single inheritance** only (one parent class)

#### § 3.1.2 — Method Overriding
  - Same signature as parent method
  - `@Override` annotation (always use it!)
  - Access modifier must be same or less restrictive
  - Return type: same or covariant (subtype)
  - `super.method()` — calling the parent's version
  - Cannot override `final`, `static`, or `private` methods

#### § 3.1.3 — The `final` Modifier on Classes & Methods
  - `final class` — cannot be subclassed (e.g., `String`, `Integer`)
  - `final method` — cannot be overridden
  - Use case: preventing modification of critical behavior

#### § 3.1.4 — The `Object` Hierarchy
  - Every class implicitly extends `Object`
  - Upcasting: `Animal a = new Dog();` (always safe)
  - Downcasting: `Dog d = (Dog) a;` (requires runtime check)
  - `ClassCastException` — failed downcast
  - `instanceof` check before downcasting

---

### 📦 Module 3.2: Polymorphism

#### § 3.2.1 — Compile-Time Polymorphism (Method Overloading)
  - Multiple methods with same name, different parameters
  - Resolved at compile time by the compiler

#### § 3.2.2 — Runtime Polymorphism (Method Overriding + Dynamic Dispatch)
  - Virtual method table (vtable) concept
  - The reference type determines WHAT can be called
  - The object type determines WHICH implementation runs
  - Example: `Animal a = new Dog(); a.speak();` → calls `Dog.speak()`

#### § 3.2.3 — Polymorphism in Practice
  - Polymorphic arrays: `Animal[] animals = {new Dog(), new Cat()};`
  - Polymorphic method parameters: `void feed(Animal a)`
  - Polymorphic return types
  - The power of programming to interfaces

---

### 📦 Module 3.3: Abstract Classes & Interfaces

#### § 3.3.1 — Abstract Classes
  - `abstract class Shape { abstract double area(); }`
  - Can have both abstract and concrete methods
  - Can have constructors, fields, static methods
  - Cannot be instantiated directly
  - Subclasses MUST implement all abstract methods (or be abstract themselves)

#### § 3.3.2 — Interfaces
  - `interface Drawable { void draw(); }`
  - All methods are implicitly `public abstract` (pre-Java 8)
  - All fields are implicitly `public static final`
  - A class can implement MULTIPLE interfaces: `class Foo implements A, B`
  - **Default methods** (Java 8+): `default void log() { ... }` — methods with a body
  - **Static methods** (Java 8+): `static void helper() { ... }`
  - **Private methods** (Java 9+): `private void internal() { ... }`

#### § 3.3.3 — Abstract Class vs. Interface (When to Use Which)
  - Interface: defines a contract (capability), no state
  - Abstract class: partial implementation, shared state
  - Java 8+ blurred the line with default methods
  - Prefer interfaces for type definitions, abstract classes for shared implementation

#### § 3.3.4 — Functional Interfaces (Java 8+)
  - An interface with exactly ONE abstract method
  - `@FunctionalInterface` annotation
  - Can be implemented with lambdas
  - Key functional interfaces in `java.util.function`:
    - `Predicate<T>` — `boolean test(T t)`
    - `Function<T, R>` — `R apply(T t)`
    - `Consumer<T>` — `void accept(T t)`
    - `Supplier<T>` — `T get()`
    - `BiFunction<T, U, R>`, `BiPredicate<T, U>`, `BiConsumer<T, U>`
    - `UnaryOperator<T>`, `BinaryOperator<T>`

---

### 📦 Module 3.4: Sealed Classes (Java 17+)

#### § 3.4.1 — Restricting Inheritance
  - `sealed class Shape permits Circle, Rectangle, Triangle { ... }`
  - Subclasses must be `final`, `sealed`, or `non-sealed`
  - Use case: exhaustive type hierarchies
  - Enabling exhaustive `switch` + pattern matching

---

### 📦 Module 3.5: Records (Java 16+)

#### § 3.5.1 — Immutable Data Carriers
  - `record Point(int x, int y) { }` — auto-generates: constructor, getters, `equals`, `hashCode`, `toString`
  - Compact constructors for validation
  - Records are `final`, cannot extend other classes
  - Can implement interfaces
  - Use case: DTOs, value objects, tuples

---

### 📦 Module 3.6: Enums — Advanced

#### § 3.6.1 — Enums as Full Classes
  - `enum Direction { NORTH, SOUTH, EAST, WEST }`
  - Enums can have fields, constructors, methods
  - `enum Planet { EARTH(5.97e24, 6.37e6); ... }`
  - Implementing interfaces in enums
  - Abstract methods in enums (each constant provides implementation)
  - `values()`, `valueOf()`, `ordinal()`, `name()`
  - `EnumSet`, `EnumMap` — efficient enum collections

---

### 📦 Module 3.7: Nested & Inner Classes

#### § 3.7.1 — Types of Nested Classes
  - **Static nested class**: `static class Inner` — no reference to outer instance
  - **Inner class** (non-static): has implicit reference to outer instance
  - **Local class**: defined inside a method
  - **Anonymous class**: `new Runnable() { ... }` — inline implementation
  - When to use each, memory leak implications of inner classes

> ### 🛠️ Phase 3 Project: **"Shape Hierarchy & Drawing Engine"**
> Build a polymorphic shape drawing system:
> - `sealed interface Shape permits Circle, Rectangle, Triangle, Polygon`
> - Each shape: `record Circle(double radius) implements Shape`
> - `interface Drawable { void draw(Canvas canvas); }`
> - `interface Resizable { Shape resize(double factor); }`
> - `abstract class AbstractShape implements Shape, Drawable, Resizable` (shared logic)
> - `class Canvas` — 2D character grid, shapes draw themselves onto it
> - `enum Color { RED, GREEN, BLUE, ... }` — with RGB values as fields
> - **Pattern matching switch** (Java 21+):
>   ```java
>   switch (shape) {
>       case Circle c -> System.out.println("Circle r=" + c.radius());
>       case Rectangle r -> ...
>   }
>   ```
> - Factory method: `ShapeFactory.create("circle", params)`
> - Print the canvas as ASCII art to the console

---

## ⚡ PHASE 4 — GENERICS & COLLECTIONS FRAMEWORK
> *"The Collections Framework is the most used part of Java — master it completely."*

---

### 📦 Module 4.1: Generics

#### § 4.1.1 — Why Generics? (Type Safety Without Casting)
  - Pre-generics: `List list = new ArrayList(); list.add("hello"); String s = (String) list.get(0);`
  - With generics: `List<String> list = new ArrayList<>(); String s = list.get(0);`
  - Type erasure: generics are a compile-time mechanism (erased at runtime)

#### § 4.1.2 — Generic Classes & Interfaces
  - `class Box<T> { private T value; ... }`
  - `interface Comparable<T> { int compareTo(T o); }`
  - Multiple type parameters: `class Pair<K, V>`
  - Diamond operator: `Box<String> box = new Box<>();`

#### § 4.1.3 — Generic Methods
  - `static <T> T getFirst(List<T> list) { ... }`
  - Type inference for generic methods
  - Bounded type parameters: `<T extends Comparable<T>>`

#### § 4.1.4 — Bounded Type Parameters
  - Upper bound: `<T extends Number>` — T must be Number or subclass
  - Multiple bounds: `<T extends Comparable<T> & Serializable>`
  - `extends` is used for both classes and interfaces in bounds

#### § 4.1.5 — Wildcards
  - Unbounded: `List<?>` — list of unknown type
  - Upper bounded: `List<? extends Number>` — producer (read-only)
  - Lower bounded: `List<? super Integer>` — consumer (write-only)
  - **PECS principle**: Producer Extends, Consumer Super
  - `List<?>` vs `List<Object>` — critical difference

#### § 4.1.6 — Type Erasure & Limitations
  - Cannot create `new T()` or `new T[]`
  - Cannot use `instanceof` with generic types
  - Cannot create generic arrays: `new List<String>[10]` — illegal
  - Raw types and `@SuppressWarnings("unchecked")`
  - Bridge methods (compiler-generated)

---

### 📦 Module 4.2: Collections Framework Overview

#### § 4.2.1 — The Collections Hierarchy
  ```
  Iterable
    └── Collection
          ├── List (ordered, indexed, duplicates allowed)
          ├── Set (no duplicates)
          │    └── SortedSet → NavigableSet
          └── Queue
               └── Deque
  Map (separate hierarchy — NOT a Collection)
    └── SortedMap → NavigableMap
  ```

#### § 4.2.2 — Choosing the Right Collection
  - Need order + index? → `ArrayList`
  - Need fast lookup? → `HashSet` / `HashMap`
  - Need sorted order? → `TreeSet` / `TreeMap`
  - Need insertion order? → `LinkedHashSet` / `LinkedHashMap`
  - Need FIFO? → `ArrayDeque` (as queue)
  - Need LIFO? → `ArrayDeque` (as stack)
  - Need thread-safety? → `ConcurrentHashMap`, `CopyOnWriteArrayList`

---

### 📦 Module 4.3: List Implementations

#### § 4.3.1 — `ArrayList<E>`
  - Dynamic array — THE default `List`
  - O(1) random access, O(n) insert/remove at arbitrary position
  - `add()`, `get()`, `set()`, `remove()`, `size()`, `contains()`, `indexOf()`
  - `subList()` — view (not a copy!)
  - Initial capacity and growth strategy

#### § 4.3.2 — `LinkedList<E>`
  - Doubly linked list — also implements `Deque`
  - O(1) insert/remove at ends, O(n) random access
  - Almost never the right choice (cache-unfriendly)

#### § 4.3.3 — `List.of()` & `List.copyOf()` (Java 9+)
  - Immutable lists: `List.of("a", "b", "c")`
  - `List.copyOf(existingList)` — immutable copy
  - Cannot add, remove, or set elements (throws `UnsupportedOperationException`)
  - No `null` elements allowed

---

### 📦 Module 4.4: Set Implementations

#### § 4.4.1 — `HashSet<E>`
  - Hash table backed — O(1) add/remove/contains
  - No ordering guarantees
  - Requires proper `hashCode()` + `equals()`

#### § 4.4.2 — `LinkedHashSet<E>`
  - Hash table + linked list — maintains insertion order
  - Slightly slower than `HashSet`

#### § 4.4.3 — `TreeSet<E>`
  - Red-black tree — sorted order
  - O(log n) add/remove/contains
  - Elements must implement `Comparable` or provide a `Comparator`
  - `first()`, `last()`, `headSet()`, `tailSet()`, `subSet()`

#### § 4.4.4 — `EnumSet<E>`
  - Extremely efficient set for enum types (bit vector internally)
  - `EnumSet.of(Color.RED, Color.BLUE)`, `EnumSet.allOf(Color.class)`

---

### 📦 Module 4.5: Map Implementations

#### § 4.5.1 — `HashMap<K, V>`
  - Hash table — O(1) average get/put
  - `put()`, `get()`, `getOrDefault()`, `containsKey()`, `containsValue()`
  - `keySet()`, `values()`, `entrySet()`
  - `putIfAbsent()`, `compute()`, `computeIfAbsent()`, `merge()` (Java 8+)
  - Internal: buckets, linked lists → red-black trees (Java 8+ when bucket > 8)

#### § 4.5.2 — `LinkedHashMap<K, V>`
  - Maintains insertion order (or access order for LRU cache)
  - `removeEldestEntry()` — LRU cache implementation

#### § 4.5.3 — `TreeMap<K, V>`
  - Red-black tree — sorted by keys
  - `NavigableMap` operations: `firstKey()`, `lastKey()`, `floorKey()`, `ceilingKey()`

#### § 4.5.4 — `Map.of()` & `Map.entry()` (Java 9+)
  - Immutable maps: `Map.of("key1", "val1", "key2", "val2")`
  - `Map.ofEntries(Map.entry("key", "val"), ...)`

---

### 📦 Module 4.6: Queue & Deque Implementations

#### § 4.6.1 — `ArrayDeque<E>`
  - Resizable array — fastest general-purpose queue AND stack
  - As Queue: `offer()`, `poll()`, `peek()`
  - As Stack: `push()`, `pop()`, `peek()`
  - Prefer over `Stack` class (legacy) and `LinkedList`

#### § 4.6.2 — `PriorityQueue<E>`
  - Binary heap — elements ordered by natural order or `Comparator`
  - `offer()`, `poll()` (dequeues smallest), `peek()`
  - NOT sorted iteration — only `poll()` gives order
  - Use case: Dijkstra, task scheduling, top-K problems

---

### 📦 Module 4.7: Utility Classes & Operations

#### § 4.7.1 — `Collections` Utility Class
  - `Collections.sort()`, `Collections.reverse()`
  - `Collections.unmodifiableList()`, `Collections.synchronizedList()`
  - `Collections.singletonList()`, `Collections.emptyList()`
  - `Collections.frequency()`, `Collections.disjoint()`

#### § 4.7.2 — `Comparable<T>` vs `Comparator<T>`
  - `Comparable`: natural ordering — `class Person implements Comparable<Person>`
  - `Comparator`: custom ordering — `Comparator.comparing(Person::getAge).thenComparing(Person::getName)`
  - `Comparator.naturalOrder()`, `Comparator.reverseOrder()`
  - `Comparator.nullsFirst()`, `Comparator.nullsLast()`

#### § 4.7.3 — Iterating Collections
  - Enhanced for-each: `for (var item : list)`
  - `Iterator<E>`: `hasNext()`, `next()`, `remove()`
  - `ListIterator<E>`: bidirectional, `add()`, `set()`
  - `forEach(Consumer<T>)` (Java 8+)
  - `ConcurrentModificationException` — modifying during iteration

---

### 📦 Module 4.8: Sequenced Collections (Java 21+)

#### § 4.8.1 — New Interfaces
  - `SequencedCollection<E>`: `getFirst()`, `getLast()`, `addFirst()`, `addLast()`, `reversed()`
  - `SequencedSet<E>`, `SequencedMap<K, V>`
  - Unifies access patterns across `List`, `LinkedHashSet`, `TreeSet`, `LinkedHashMap`, `TreeMap`

> ### 🛠️ Phase 4 Project: **"InMemoryDB — A Generic In-Memory Database"**
> Build a type-safe in-memory database engine:
> - `class Table<T>` — generic table that stores records of type `T`
> - **CRUD**: `insert(T)`, `findById(int)`, `update(int, T)`, `delete(int)`
> - **Querying**:
>   - `findAll(Predicate<T>)` — filter by condition
>   - `sortBy(Comparator<T>)` — sort results
>   - `groupBy(Function<T, K>)` — returns `Map<K, List<T>>`
>   - `aggregate(Function<T, Number>)` — sum, avg, min, max
> - **Indexing**: secondary index using `HashMap<FieldValue, List<T>>` for fast lookups
> - **Persistence**: serialize to JSON file, load on startup
> - Use records for data models: `record Employee(int id, String name, String dept, double salary)`
> - Use generics with bounds: `<T extends Identifiable>` (interface with `getId()`)
> - Demonstrate PECS with wildcard-bounded query methods

---

## ⚡ PHASE 5 — EXCEPTION HANDLING & DEFENSIVE PROGRAMMING
> *"In Java, exceptions are not optional. They're part of the API contract."*

---

### 📦 Module 5.1: Exception Hierarchy

#### § 5.1.1 — The Throwable Tree
  ```
  Throwable
  ├── Error (DO NOT CATCH — JVM-level)
  │   ├── OutOfMemoryError
  │   ├── StackOverflowError
  │   └── VirtualMachineError
  └── Exception
      ├── Checked Exceptions (MUST handle)
      │   ├── IOException
      │   ├── SQLException
      │   ├── FileNotFoundException
      │   └── ClassNotFoundException
      └── RuntimeException (Unchecked — optional handling)
          ├── NullPointerException
          ├── IndexOutOfBoundsException
          ├── IllegalArgumentException
          ├── IllegalStateException
          ├── ClassCastException
          ├── ArithmeticException
          └── UnsupportedOperationException
  ```

#### § 5.1.2 — Checked vs. Unchecked Exceptions
  - **Checked**: compiler forces handling (`try-catch` or `throws`)
  - **Unchecked** (`RuntimeException` subclasses): compiler doesn't force handling
  - Design debate: when to use which
  - Modern preference: unchecked for programming errors, checked for recoverable conditions

---

### 📦 Module 5.2: Handling Exceptions

#### § 5.2.1 — `try-catch-finally`
  - `try { ... } catch (ExceptionType e) { ... } finally { ... }`
  - Multi-catch (Java 7+): `catch (IOException | SQLException e)`
  - `finally` always executes (even after `return`!)
  - Don't use `finally` for resource cleanup — use try-with-resources

#### § 5.2.2 — `try-with-resources` (Java 7+)
  - `try (var reader = new BufferedReader(...)) { ... }`
  - Auto-closes resources implementing `AutoCloseable`
  - Multiple resources: `try (var in = ...; var out = ...) { ... }`
  - Suppressed exceptions: `getSuppressed()`
  - Effectively final resources (Java 9+): can use pre-declared variables

#### § 5.2.3 — Throwing Exceptions
  - `throw new IllegalArgumentException("age must be positive");`
  - `throws` in method signature: `void read() throws IOException`
  - Re-throwing: `catch (Exception e) { throw e; }`
  - Chained exceptions: `throw new ServiceException("failed", cause);`

---

### 📦 Module 5.3: Custom Exceptions

#### § 5.3.1 — Creating Custom Exception Classes
  - Extending `Exception` (checked) or `RuntimeException` (unchecked)
  - Constructors: message, cause, both
  - Adding custom fields (error codes, context)
  - Best practice: make exceptions meaningful and specific

---

### 📦 Module 5.4: Defensive Programming & Best Practices

#### § 5.4.1 — Preconditions & Validation
  - `Objects.requireNonNull(param, "param must not be null")`
  - Guava's `Preconditions.checkArgument()`, `Preconditions.checkState()`
  - `assert` keyword: `assert age > 0 : "age must be positive";` (enable with `-ea`)

#### § 5.4.2 — Helpful NullPointerExceptions (Java 17+)
  - JVM tells you WHICH variable was null: `Cannot invoke "String.length()" because "name" is null`

#### § 5.4.3 — Optional as Null Alternative
  - `Optional<T>` — wrapper for values that might be absent
  - `Optional.of()`, `Optional.ofNullable()`, `Optional.empty()`
  - `isPresent()`, `isEmpty()`, `get()` (avoid!), `orElse()`, `orElseGet()`, `orElseThrow()`
  - `map()`, `flatMap()`, `filter()` — monadic operations
  - When to use: return types only (NOT fields, NOT parameters)

> ### 🛠️ Phase 5 Project: **"RobustFileProcessor"**
> Build a file processing pipeline with comprehensive error handling:
> - Read a CSV file, validate every row, transform data, write results to output
> - **Custom exceptions**: `FileFormatException`, `ValidationException`, `TransformationException`
> - Each exception carries: line number, column, raw value, error message
> - **Error accumulation**: don't stop at first error — collect ALL errors and report them
> - **Try-with-resources** for all file I/O
> - **Optional** for nullable fields
> - **Error report**: at the end, print a summary: X rows processed, Y succeeded, Z failed, with details
> - **Retry logic**: if file is locked, retry 3 times with exponential backoff

---

## ⚡ PHASE 6 — FUNCTIONAL PROGRAMMING (JAVA 8+)
> *"Java 8 didn't just add lambdas. It changed the way Java developers think."*

---

### 📦 Module 6.1: Lambda Expressions

#### § 6.1.1 — Lambda Syntax
  - Full syntax: `(parameters) -> { body }`
  - Single expression: `(a, b) -> a + b` (return is implicit)
  - Single parameter: `x -> x * 2` (parentheses optional)
  - No parameters: `() -> System.out.println("hello")`
  - Type inference: compiler deduces parameter types

#### § 6.1.2 — Lambdas as Functional Interface Implementations
  - Lambda = inline implementation of a functional interface
  - `Predicate<String> isLong = s -> s.length() > 10;`
  - `Function<String, Integer> toLength = String::length;`
  - Variable capture: lambdas can capture effectively final local variables
  - `this` in lambdas: refers to the enclosing class (unlike anonymous classes)

---

### 📦 Module 6.2: Method References

#### § 6.2.1 — Four Types of Method References
  - **Static method**: `Integer::parseInt` → `s -> Integer.parseInt(s)`
  - **Instance method of object**: `System.out::println` → `x -> System.out.println(x)`
  - **Instance method of type**: `String::toUpperCase` → `s -> s.toUpperCase()`
  - **Constructor**: `ArrayList::new` → `() -> new ArrayList<>()`

#### § 6.2.2 — When Method References Are Clearer
  - Prefer method references when the lambda just delegates to a single method
  - `list.forEach(System.out::println)` over `list.forEach(x -> System.out.println(x))`

---

### 📦 Module 6.3: The Stream API

#### § 6.3.1 — What Are Streams?
  - A sequence of elements supporting sequential and parallel aggregate operations
  - **NOT** a data structure — doesn't store data
  - Lazy evaluation — operations are not executed until a terminal operation
  - One-time use — cannot be reused after a terminal operation
  - Pipeline: **Source** → **Intermediate Operations** → **Terminal Operation**

#### § 6.3.2 — Creating Streams
  - `collection.stream()`, `collection.parallelStream()`
  - `Stream.of("a", "b", "c")`
  - `Stream.iterate(0, n -> n + 1)`, `Stream.generate(Math::random)`
  - `Arrays.stream(array)`
  - `IntStream.range(0, 10)`, `IntStream.rangeClosed(1, 10)`
  - `Files.lines(path)` — stream of lines from a file
  - `BufferedReader.lines()`
  - `Stream.empty()`

#### § 6.3.3 — Intermediate Operations (Lazy)
  - `filter(Predicate)` — keep elements matching condition
  - `map(Function)` — transform each element
  - `flatMap(Function)` — one-to-many transformation, flatten nested streams
  - `distinct()` — remove duplicates (uses `equals`)
  - `sorted()`, `sorted(Comparator)` — sort elements
  - `peek(Consumer)` — debug/inspect (don't mutate!)
  - `limit(n)`, `skip(n)` — truncate/skip elements
  - `takeWhile(Predicate)`, `dropWhile(Predicate)` (Java 9+)
  - `mapToInt()`, `mapToDouble()`, `mapToLong()` — primitive streams

#### § 6.3.4 — Terminal Operations
  - `forEach(Consumer)`, `forEachOrdered(Consumer)`
  - `collect(Collector)` — the most powerful terminal operation
  - `toList()` (Java 16+ — immutable!)
  - `reduce(identity, BinaryOperator)` — fold/accumulate
  - `count()`, `min(Comparator)`, `max(Comparator)`
  - `anyMatch()`, `allMatch()`, `noneMatch()`
  - `findFirst()`, `findAny()` — return `Optional`
  - `toArray()`

#### § 6.3.5 — Collectors (`java.util.stream.Collectors`)
  - `toList()`, `toSet()`, `toUnmodifiableList()`, `toUnmodifiableSet()`
  - `toMap()`, `toUnmodifiableMap()` — with key/value extractors
  - `joining(delimiter)` — concatenate strings
  - `groupingBy(Function)` — `Map<K, List<V>>`
  - `partitioningBy(Predicate)` — `Map<Boolean, List<V>>`
  - `counting()`, `summingInt()`, `averagingDouble()`
  - `summarizingInt()` — `IntSummaryStatistics`
  - `mapping()`, `filtering()`, `flatMapping()` — downstream collectors
  - `collectingAndThen()` — post-processing
  - `reducing()` — collector-based reduction
  - `teeing()` (Java 12+) — two collectors, merged result

#### § 6.3.6 — Primitive Streams
  - `IntStream`, `LongStream`, `DoubleStream`
  - `sum()`, `average()`, `max()`, `min()`, `summaryStatistics()`
  - `boxed()` — convert to `Stream<Integer>`
  - `mapToObj()` — convert back to object stream

#### § 6.3.7 — Parallel Streams
  - `stream.parallel()` or `collection.parallelStream()`
  - Uses `ForkJoinPool.commonPool()`
  - When to parallelize: large datasets, independent operations, CPU-bound
  - When NOT to: small datasets, I/O-bound, order-dependent, shared mutable state
  - `forEachOrdered()` to maintain order in parallel

---

### 📦 Module 6.4: Functional Composition & Advanced Patterns

#### § 6.4.1 — Composing Functions
  - `Function.compose()`: `f.compose(g)` = `f(g(x))`
  - `Function.andThen()`: `f.andThen(g)` = `g(f(x))`
  - `Predicate.and()`, `Predicate.or()`, `Predicate.negate()`

#### § 6.4.2 — Currying & Partial Application
  - `Function<Integer, Function<Integer, Integer>> add = a -> b -> a + b;`
  - Simulating currying in Java

#### § 6.4.3 — Immutability & Functional Design
  - Immutable objects + pure functions = fewer bugs
  - Records as immutable data
  - `List.copyOf()`, `Map.copyOf()` — defensive copies

> ### 🛠️ Phase 6 Project: **"DataForge — A Stream-Powered Analytics Engine"**
> Build a data analytics tool that processes a large dataset (e.g., 100K+ rows of e-commerce orders):
> - **Read** CSV into `List<Order>` (record: `orderId`, `customer`, `product`, `category`, `quantity`, `price`, `date`)
> - **Queries** (all implemented as stream pipelines):
>   1. Total revenue by category → `Map<String, Double>`
>   2. Top 10 customers by spending
>   3. Monthly revenue trend → `Map<YearMonth, Double>`
>   4. Products with above-average revenue
>   5. Customer segmentation: `partitioningBy(spent > 1000)`
>   6. Most popular product per category → `groupingBy` + `maxBy`
> - **Compare** sequential vs parallel stream performance (benchmark both)
> - **Functional composition**: build query pipelines from composable `Function` and `Predicate` objects
> - **Export** results as formatted tables using `Collectors.joining()`
> - Use `Optional` throughout — no `null` in any query result

---

## ⚡ PHASE 7 — CONCURRENCY & MULTITHREADING
> *"Java has the most comprehensive concurrency library of any mainstream language."*

---

### 📦 Module 7.1: Thread Fundamentals

#### § 7.1.1 — Creating Threads
  - Extending `Thread` class (not recommended)
  - Implementing `Runnable` interface (preferred)
  - Lambda syntax: `new Thread(() -> { ... }).start();`
  - `Callable<V>` — `Runnable` with a return value
  - Thread lifecycle: NEW → RUNNABLE → RUNNING → BLOCKED/WAITING → TERMINATED

#### § 7.1.2 — Thread Management
  - `start()` vs `run()` — start() creates a new thread, run() executes in current thread!
  - `sleep()`, `yield()`, `join()`
  - `interrupt()`, `isInterrupted()`, `InterruptedException`
  - Thread priority (`setPriority()`) — mostly a hint
  - Daemon threads: `setDaemon(true)` — die when all non-daemon threads exit
  - `Thread.currentThread()`, `getName()`, `setName()`

---

### 📦 Module 7.2: Synchronization

#### § 7.2.1 — The Problem: Race Conditions & Data Races
  - Multiple threads modifying shared mutable state
  - Non-atomic operations: `count++` is read → modify → write
  - Visibility problem: threads may see stale data (CPU caching)

#### § 7.2.2 — `synchronized` Keyword
  - Synchronized methods: `synchronized void increment() { ... }`
  - Synchronized blocks: `synchronized (lockObject) { ... }`
  - Intrinsic locks (monitors) — every Java object has one
  - Reentrant: same thread can acquire the same lock multiple times
  - `wait()`, `notify()`, `notifyAll()` — inter-thread communication

#### § 7.2.3 — `volatile` Keyword
  - Ensures visibility: reads/writes go directly to main memory
  - Does NOT ensure atomicity
  - Use case: flags, single-writer-multiple-reader

---

### 📦 Module 7.3: `java.util.concurrent` — The Concurrency Toolkit

#### § 7.3.1 — Locks (`java.util.concurrent.locks`)
  - `ReentrantLock` — more flexible than `synchronized`
  - `tryLock()`, `lockInterruptibly()`, `newCondition()`
  - `ReadWriteLock` / `ReentrantReadWriteLock` — multiple readers, single writer
  - `StampedLock` (Java 8+) — optimistic locking (highest performance)

#### § 7.3.2 — Atomic Classes (`java.util.concurrent.atomic`)
  - `AtomicInteger`, `AtomicLong`, `AtomicBoolean`, `AtomicReference<V>`
  - `incrementAndGet()`, `compareAndSet()`, `getAndUpdate()`
  - Lock-free, CAS-based (Compare-And-Swap)
  - `LongAdder`, `LongAccumulator` (Java 8+) — higher throughput under contention

#### § 7.3.3 — Concurrent Collections
  - `ConcurrentHashMap<K, V>` — segment-locked, high-concurrency map
  - `CopyOnWriteArrayList<E>` — read-optimized, copies on write
  - `CopyOnWriteArraySet<E>`
  - `ConcurrentLinkedQueue<E>`, `ConcurrentLinkedDeque<E>`
  - `BlockingQueue<E>` — producer-consumer:
    - `ArrayBlockingQueue` (bounded)
    - `LinkedBlockingQueue` (optionally bounded)
    - `PriorityBlockingQueue` (unbounded, priority)
    - `SynchronousQueue` (direct handoff)
    - `DelayQueue` (delayed elements)
  - `TransferQueue<E>` (Java 7+)

#### § 7.3.4 — Synchronizers
  - `CountDownLatch` — wait for N events
  - `CyclicBarrier` — wait for N threads to reach a point
  - `Semaphore` — control concurrent access count
  - `Phaser` (Java 7+) — flexible barrier
  - `Exchanger<V>` — two threads exchange data

---

### 📦 Module 7.4: Executor Framework

#### § 7.4.1 — Executors & Thread Pools
  - `ExecutorService` interface
  - `Executors.newFixedThreadPool(n)` — fixed-size pool
  - `Executors.newCachedThreadPool()` — dynamic, reuses threads
  - `Executors.newSingleThreadExecutor()` — single thread, ordered
  - `Executors.newScheduledThreadPool(n)` — scheduled/periodic tasks
  - `submit(Runnable)`, `submit(Callable<V>)` → `Future<V>`
  - `invokeAll()`, `invokeAny()`
  - `shutdown()`, `shutdownNow()`, `awaitTermination()`

#### § 7.4.2 — `Future<V>` & `CompletableFuture<V>`
  - `Future.get()` — blocking, `get(timeout, unit)` — bounded blocking
  - `Future.isDone()`, `Future.cancel()`
  - **`CompletableFuture<V>`** (Java 8+) — the async powerhouse:
    - `supplyAsync()`, `runAsync()`
    - `thenApply()`, `thenAccept()`, `thenRun()` — chaining
    - `thenCompose()` — flatMap for futures
    - `thenCombine()` — combine two futures
    - `exceptionally()`, `handle()` — error handling
    - `allOf()`, `anyOf()` — combining multiple futures
    - Custom executors: `supplyAsync(supplier, executor)`

---

### 📦 Module 7.5: Virtual Threads (Java 21+ — Project Loom)

#### § 7.5.1 — The Revolution: Lightweight Threads
  - Platform threads (OS-level) vs Virtual threads (JVM-managed)
  - `Thread.ofVirtual().start(() -> { ... });`
  - `Executors.newVirtualThreadPerTaskExecutor()`
  - Millions of virtual threads are feasible
  - Blocking I/O on virtual threads is efficient (no thread waste)
  - Structured concurrency (preview): `StructuredTaskScope`

#### § 7.5.2 — When to Use Virtual Threads
  - I/O-bound workloads: HTTP servers, database clients, file processing
  - NOT for: CPU-bound computation (use platform thread pools)
  - Migration: drop-in replacement for platform threads in most cases

---

### 📦 Module 7.6: Common Concurrency Patterns & Pitfalls

#### § 7.6.1 — Patterns
  - Producer-Consumer (BlockingQueue)
  - Reader-Writer (ReadWriteLock)
  - Thread-safe Singleton (enum, holder pattern, double-checked locking)
  - Fork-Join framework: `ForkJoinPool`, `RecursiveTask<V>`, `RecursiveAction`

#### § 7.6.2 — Pitfalls
  - Deadlock: circular lock dependencies
  - Livelock: threads keep responding to each other without progress
  - Starvation: thread never gets the lock
  - Thread leaks: never-terminated threads
  - Memory consistency errors

> ### 🛠️ Phase 7 Project: **"WebCrawler — A Concurrent Web Scraper"**
> Build a multi-threaded web crawler:
> - **Architecture**: Producer-consumer with `BlockingQueue<URL>`
> - **Thread pool**: configurable using `ExecutorService`
> - **Version A**: Platform threads with `CompletableFuture` chains
> - **Version B**: Virtual threads (Java 21+) with `newVirtualThreadPerTaskExecutor()`
> - **Features**:
>   - Crawl from a seed URL, discover linked pages (up to depth N)
>   - `ConcurrentHashMap<URL, PageData>` for visited tracking (no duplicates)
>   - Rate limiting: `Semaphore` to limit concurrent requests per domain
>   - Timeout handling: cancel slow requests
>   - Graceful shutdown with `CountDownLatch`
> - **Output**: site map, word frequency analysis, broken link report
> - **Benchmark**: compare platform threads vs virtual threads (throughput, memory)

---

## ⚡ PHASE 8 — I/O, NIO & SERIALIZATION
> *"Java has three I/O APIs. Know when to use each."*

---

### 📦 Module 8.1: Classic I/O (`java.io`)

#### § 8.1.1 — Byte Streams
  - `InputStream` / `OutputStream` (abstract base classes)
  - `FileInputStream` / `FileOutputStream` — raw byte file I/O
  - `BufferedInputStream` / `BufferedOutputStream` — buffered for performance
  - `DataInputStream` / `DataOutputStream` — read/write primitives
  - `ByteArrayInputStream` / `ByteArrayOutputStream`

#### § 8.1.2 — Character Streams
  - `Reader` / `Writer` (abstract base classes)
  - `FileReader` / `FileWriter` — character file I/O
  - `BufferedReader` / `BufferedWriter` — line-at-a-time I/O
  - `InputStreamReader` / `OutputStreamWriter` — byte-to-char bridge (charset)
  - `PrintWriter` — formatted output

#### § 8.1.3 — Object Serialization
  - `Serializable` interface — marker interface
  - `ObjectOutputStream.writeObject()`, `ObjectInputStream.readObject()`
  - `serialVersionUID` — version control for serialized objects
  - `transient` keyword — exclude fields from serialization
  - Security risks of Java serialization (deserialization attacks)
  - Modern alternatives: JSON, Protocol Buffers

---

### 📦 Module 8.2: NIO & NIO.2 (`java.nio`)

#### § 8.2.1 — Channels & Buffers
  - `FileChannel`, `SocketChannel`, `ServerSocketChannel`, `DatagramChannel`
  - `ByteBuffer` — the core NIO buffer
  - `ByteBuffer.allocate()`, `allocateDirect()` (off-heap, faster I/O)
  - Buffer operations: `put()`, `get()`, `flip()`, `clear()`, `compact()`, `rewind()`
  - Position, limit, capacity

#### § 8.2.2 — File I/O with NIO.2 (`java.nio.file`)
  - `Path` — the modern replacement for `File`
  - `Paths.get()`, `Path.of()` (Java 11+)
  - `Files.readString()`, `Files.writeString()` (Java 11+)
  - `Files.readAllLines()`, `Files.readAllBytes()`
  - `Files.lines()` — lazy stream of lines
  - `Files.walk()`, `Files.find()` — recursive directory traversal
  - `Files.copy()`, `Files.move()`, `Files.delete()`
  - `Files.createDirectory()`, `Files.createTempFile()`
  - File attributes: `Files.size()`, `Files.getLastModifiedTime()`
  - `WatchService` — filesystem event monitoring

#### § 8.2.3 — Non-Blocking I/O & Selectors
  - `Selector` — monitor multiple channels
  - `SelectionKey` — interest ops (READ, WRITE, ACCEPT, CONNECT)
  - Non-blocking server with `ServerSocketChannel` + `Selector`
  - Use case: high-concurrency network servers

---

### 📦 Module 8.3: Modern Serialization & Data Formats

#### § 8.3.1 — JSON Processing
  - **Jackson**: `ObjectMapper`, `@JsonProperty`, `@JsonIgnore`
  - **Gson**: `new Gson().toJson(obj)`, `fromJson(json, Type.class)`
  - Jackson annotations: `@JsonCreator`, `@JsonFormat`, `@JsonSerialize`
  - Streaming API for large JSON: `JsonParser`, `JsonGenerator`

#### § 8.3.2 — Other Formats
  - XML: JAXB, DOM, SAX, StAX
  - YAML: SnakeYAML, Jackson YAML module
  - Protocol Buffers (protobuf) — binary, schema-driven
  - Apache Avro — schema evolution support

---

### 📦 Module 8.4: HTTP Client (Java 11+)

#### § 8.4.1 — `java.net.http.HttpClient`
  - `HttpClient.newHttpClient()`
  - `HttpRequest.newBuilder().uri(URI.create("...")).GET().build()`
  - `HttpResponse.BodyHandlers.ofString()`
  - Synchronous: `client.send(request, handler)`
  - Asynchronous: `client.sendAsync(request, handler)` → `CompletableFuture`
  - Custom headers, POST body, timeouts, redirects
  - HTTP/2 support built-in

> ### 🛠️ Phase 8 Project: **"FileVault — An Encrypted File Storage System"**
> Build a file management application:
> - **Watch** a directory for new files using `WatchService`
> - **Encrypt** files using `javax.crypto` (AES-256-GCM) and store them in a vault directory
> - **Decrypt** and retrieve files by name
> - **Metadata** stored in a JSON index file (using Jackson) with: filename, size, date, checksum (SHA-256)
> - **NIO**: use `FileChannel` + `ByteBuffer` for efficient large file I/O
> - **HTTP API**: expose a simple REST API using `com.sun.net.httpserver.HttpServer` (built-in) to upload/download/list files
> - **Virtual threads** for handling concurrent HTTP requests
> - All I/O with proper `try-with-resources`, all errors handled with custom exceptions

---

## ⚡ PHASE 9 — BUILD TOOLS, TESTING & SOFTWARE ENGINEERING
> *"Professional Java is 50% code and 50% tooling."*

---

### 📦 Module 9.1: Build Tools

#### § 9.1.1 — Maven
  - `pom.xml` — Project Object Model
  - GAV coordinates: `groupId`, `artifactId`, `version`
  - Dependency management: `<dependencies>` section
  - Maven lifecycle: `validate` → `compile` → `test` → `package` → `install` → `deploy`
  - `mvn clean install`, `mvn test`, `mvn package`
  - Plugins: `maven-compiler-plugin`, `maven-surefire-plugin`, `maven-shade-plugin`
  - Maven Central repository

#### § 9.1.2 — Gradle
  - `build.gradle` (Groovy) / `build.gradle.kts` (Kotlin DSL — preferred)
  - `dependencies { implementation("group:artifact:version") }`
  - Tasks: `gradle build`, `gradle test`, `gradle run`
  - `implementation` vs `api` vs `compileOnly` vs `runtimeOnly` vs `testImplementation`
  - Gradle wrapper: `./gradlew build` — reproducible builds
  - Multi-project builds
  - Why Gradle is overtaking Maven (incremental builds, flexibility, Kotlin DSL)

---

### 📦 Module 9.2: Testing

#### § 9.2.1 — JUnit 5 (Jupiter)
  - `@Test`, `@BeforeEach`, `@AfterEach`, `@BeforeAll`, `@AfterAll`
  - Assertions: `assertEquals()`, `assertNotNull()`, `assertTrue()`, `assertThrows()`
  - `assertAll()` — grouped assertions
  - `@DisplayName("Human-readable test name")`
  - `@Disabled` — skip tests
  - `@ParameterizedTest` with `@ValueSource`, `@CsvSource`, `@MethodSource`
  - `@Nested` — nested test classes for organization
  - `@RepeatedTest`, `@Timeout`

#### § 9.2.2 — AssertJ (Fluent Assertions)
  - `assertThat(name).isNotNull().startsWith("J").hasSize(4);`
  - Collection assertions: `assertThat(list).containsExactly(1, 2, 3)`
  - Exception assertions: `assertThatThrownBy(() -> ...).isInstanceOf(IllegalArgumentException.class)`
  - Much more readable than JUnit assertions

#### § 9.2.3 — Mockito (Mocking Framework)
  - `@Mock`, `@InjectMocks`, `@ExtendWith(MockitoExtension.class)`
  - `when(mock.method()).thenReturn(value)`
  - `verify(mock, times(1)).method()`
  - `ArgumentCaptor` — capturing arguments
  - `@Spy` — partial mocking
  - `doThrow()`, `doAnswer()`, `doNothing()`

#### § 9.2.4 — Integration & Other Testing
  - Testcontainers: real databases in Docker for integration tests
  - WireMock: HTTP mock server
  - ArchUnit: architectural tests (`noClasses().that().resideIn("..service..").should().dependOn("..controller..")`)
  - JaCoCo: code coverage (`./gradlew jacocoTestReport`)
  - Mutation testing: PITest

---

### 📦 Module 9.3: Code Quality & Best Practices

#### § 9.3.1 — Static Analysis
  - **SpotBugs**: finds common bug patterns
  - **Checkstyle**: coding style enforcement
  - **SonarQube / SonarLint**: comprehensive code quality analysis
  - **Error Prone**: catches common Java mistakes at compile time

#### § 9.3.2 — Logging
  - **SLF4J** — logging facade (the standard)
  - **Logback** — SLF4J's native implementation
  - **Log4j2** — high-performance alternative
  - Log levels: TRACE → DEBUG → INFO → WARN → ERROR
  - Parameterized logging: `log.info("User {} logged in at {}", user, time);`
  - MDC (Mapped Diagnostic Context) for request tracing
  - Never log sensitive data (passwords, tokens)

#### § 9.3.3 — Documentation & Style
  - Javadoc for all public APIs
  - Google Java Style Guide
  - `google-java-format` — automatic formatting
  - Lombok: `@Getter`, `@Setter`, `@Builder`, `@ToString`, `@EqualsAndHashCode`, `@Slf4j`
  - Lombok debate: magic vs. boilerplate (know both sides)

---

### 📦 Module 9.4: Packaging & Distribution

#### § 9.4.1 — JAR Files
  - `jar cf app.jar *.class` — creating a JAR
  - Executable JAR: `MANIFEST.MF` with `Main-Class`
  - Fat/Uber JAR: `maven-shade-plugin` / Gradle `shadowJar`
  - `java -jar app.jar` — running

#### § 9.4.2 — Java Modules (JPMS — Java 9+)
  - `module-info.java`: `module com.myapp { requires java.sql; exports com.myapp.api; }`
  - `requires`, `exports`, `opens`, `provides...with`, `uses`
  - Strong encapsulation: internal packages are truly hidden
  - Module path vs classpath
  - Practical reality: most projects still use classpath

> ### 🛠️ Phase 9 Project: **"LibTask — A Well-Engineered Task Library"**
> Build a polished, publishable library:
> - **Library**: `TaskScheduler` — schedule tasks with cron-like expressions
>   - `scheduler.schedule("0 */5 * * *", () -> sendReport());`
>   - Support: one-time, repeating, delayed tasks
>   - Thread pool backed with proper shutdown
> - **Build**: Gradle with Kotlin DSL (`build.gradle.kts`)
> - **Testing**:
>   - 90%+ code coverage (JaCoCo)
>   - JUnit 5 with parameterized tests
>   - AssertJ for assertions
>   - Mockito for mocking time/clock (`java.time.Clock`)
> - **Quality**: SpotBugs, Checkstyle, SonarLint — zero issues
> - **Logging**: SLF4J + Logback
> - **Documentation**: Full Javadoc, README with usage examples
> - **Publishing**: generate a JAR, publish to local Maven repository

---

## ⚡ PHASE 10 — JVM INTERNALS & PERFORMANCE
> *"Understanding the JVM is what separates a Java developer from a Java engineer."*

---

### 📦 Module 10.1: JVM Architecture — Deep Dive

#### § 10.1.1 — Class Loading
  - Class loading phases: Loading → Linking (Verify, Prepare, Resolve) → Initialization
  - ClassLoader hierarchy: Bootstrap → Platform → Application
  - Custom ClassLoaders
  - Class loading delegation model (parent-first)

#### § 10.1.2 — JVM Memory Areas (Detailed)
  - **Heap**: Young Generation (Eden + Survivor S0/S1) → Old Generation
  - **Metaspace**: class metadata (replaced PermGen in Java 8)
  - **Thread Stacks**: frames, local variables, operand stack
  - **PC Register**: per thread
  - **Native Method Stack**: for JNI calls
  - **Direct Memory**: off-heap (`ByteBuffer.allocateDirect`)

#### § 10.1.3 — JIT Compilation
  - Interpreter vs JIT (Just-In-Time) compiler
  - C1 (client compiler) vs C2 (server compiler) — tiered compilation
  - Hotspot detection — frequently executed methods get compiled
  - Inlining, escape analysis, loop unrolling, dead code elimination
  - `GraalVM` — polyglot VM with advanced JIT
  - Ahead-of-Time (AOT) compilation: `GraalVM Native Image` — compile to native binary

---

### 📦 Module 10.2: Garbage Collection — Deep Dive

#### § 10.2.1 — GC Fundamentals
  - GC roots: static fields, stack variables, JNI references
  - Mark-and-Sweep, Mark-and-Compact
  - Generational hypothesis: most objects die young
  - Minor GC (young gen) vs Major GC (old gen) vs Full GC

#### § 10.2.2 — GC Algorithms
  - **Serial GC**: `-XX:+UseSerialGC` — single-thread, small apps
  - **Parallel GC**: `-XX:+UseParallelGC` — multi-thread, throughput-focused
  - **G1 GC**: `-XX:+UseG1GC` — default since Java 9, region-based, low pause
  - **ZGC**: `-XX:+UseZGC` — sub-millisecond pauses, scalable (Java 15+)
  - **Shenandoah GC**: low-pause, concurrent (RedHat)
  - Choosing the right GC for your workload

#### § 10.2.3 — GC Tuning
  - Key JVM flags: `-Xms`, `-Xmx`, `-Xss`, `-XX:MaxMetaspaceSize`
  - GC logging: `-Xlog:gc*` (Java 9+ unified logging)
  - Analyzing GC logs: GCViewer, GCEasy
  - Reducing GC pressure: object pooling, primitive collections, avoiding autoboxing

---

### 📦 Module 10.3: Performance Analysis & Tuning

#### § 10.3.1 — Profiling Tools
  - **JVisualVM** / **VisualVM** — monitor, profile, heap dump
  - **JFR (Java Flight Recorder)** — low-overhead production profiling
  - **JMC (Java Mission Control)** — analyze JFR recordings
  - **async-profiler** — sampling profiler (CPU, allocation, lock)
  - **YourKit**, **JProfiler** — commercial profilers

#### § 10.3.2 — Benchmarking
  - **JMH (Java Microbenchmark Harness)** — the only correct way to benchmark Java
  - `@Benchmark`, `@Warmup`, `@Measurement`, `@Fork`
  - Avoiding benchmarking pitfalls: dead code elimination, constant folding
  - `@State`, `@Setup`, `@TearDown`

#### § 10.3.3 — Memory Analysis
  - Heap dumps: `jmap -dump:format=b,file=heap.hprof <pid>`
  - Analyzing with **Eclipse MAT** (Memory Analyzer Tool)
  - Detecting memory leaks: retained size, dominator tree, GC roots path
  - Common leak patterns: static collections, listeners, inner classes

#### § 10.3.4 — Performance Patterns
  - String concatenation in loops: use `StringBuilder`
  - Avoid `Optional` in hot paths
  - Primitive collections: Eclipse Collections, HPPC
  - Object pooling (judiciously)
  - `final` classes/methods for JIT optimization
  - Value types / Project Valhalla (upcoming)

---

### 📦 Module 10.4: JVM Command-Line Tools

#### § 10.4.1 — Diagnostic Tools
  - `jps` — list Java processes
  - `jstack <pid>` — thread dump (deadlock detection!)
  - `jmap <pid>` — memory map, heap dump
  - `jstat -gc <pid>` — GC statistics
  - `jcmd <pid> <command>` — all-in-one diagnostic
  - `jinfo <pid>` — JVM configuration info
  - `javap -c MyClass` — disassemble bytecode
  - `jfr` — flight recorder commands

> ### 🛠️ Phase 10 Project: **"PerfLab — JVM Performance Investigation"**
> Perform a comprehensive performance investigation:
> 1. **Write 5 deliberately problematic programs**:
>    - Memory leak (static `List` that grows forever)
>    - Excessive GC (creating millions of tiny objects)
>    - Deadlock (two threads, two locks, wrong order)
>    - Thread starvation (unfair locking)
>    - CPU hotspot (inefficient algorithm)
> 2. **Diagnose each** using the right tool:
>    - Memory leak → heap dump + Eclipse MAT
>    - GC pressure → GC logs + GCViewer
>    - Deadlock → `jstack` thread dump
>    - CPU hotspot → async-profiler flame graph
> 3. **Fix each problem** and verify with JMH benchmarks (before/after)
> 4. **GC comparison**: run the same workload with G1, ZGC, and Parallel GC — compare pause times and throughput
> 5. **Document** findings in a report with flame graphs, GC charts, and heap dump screenshots

---

## ⚡ PHASE 11 — SPRING FRAMEWORK & ENTERPRISE JAVA
> *"Spring is Java's killer framework. If you're a Java backend developer, you WILL use Spring."*

---

### 📦 Module 11.1: Spring Core — Dependency Injection & IoC

#### § 11.1.1 — Inversion of Control (IoC) Concept
  - The problem: tight coupling, `new` everywhere
  - IoC: the framework creates and manages objects (beans)
  - Dependency Injection: constructor, setter, field injection
  - **Constructor injection is the recommended approach** (immutable, testable)

#### § 11.1.2 — Spring Boot Basics
  - `@SpringBootApplication` — main entry point
  - Auto-configuration — convention over configuration
  - `application.properties` / `application.yml`
  - `spring-boot-starter-*` dependencies
  - Spring Initializr: start.spring.io

#### § 11.1.3 — Beans & Component Scanning
  - `@Component`, `@Service`, `@Repository`, `@Controller` — stereotype annotations
  - `@Bean` — manual bean definition in `@Configuration` classes
  - `@Autowired` — injection (prefer constructor injection)
  - Bean scopes: `singleton` (default), `prototype`, `request`, `session`
  - `@Qualifier` — disambiguating multiple beans of same type
  - Bean lifecycle: `@PostConstruct`, `@PreDestroy`

#### § 11.1.4 — Profiles & Configuration
  - `@Profile("dev")`, `@Profile("prod")`
  - `@Value("${app.name}")` — inject properties
  - `@ConfigurationProperties(prefix = "app")` — type-safe config
  - Environment-specific configs: `application-dev.yml`, `application-prod.yml`

---

### 📦 Module 11.2: Spring Web (REST APIs)

#### § 11.2.1 — Building REST Controllers
  - `@RestController` — combines `@Controller` + `@ResponseBody`
  - `@GetMapping`, `@PostMapping`, `@PutMapping`, `@DeleteMapping`, `@PatchMapping`
  - `@PathVariable`, `@RequestParam`, `@RequestBody`
  - `@RequestHeader`, `@CookieValue`
  - `ResponseEntity<T>` — full control over status code, headers, body

#### § 11.2.2 — Request Validation
  - `@Valid` + Bean Validation annotations: `@NotNull`, `@NotBlank`, `@Size`, `@Min`, `@Max`, `@Email`, `@Pattern`
  - Custom validators: implement `ConstraintValidator`
  - `MethodArgumentNotValidException` handling

#### § 11.2.3 — Exception Handling
  - `@ExceptionHandler` — controller-level
  - `@ControllerAdvice` / `@RestControllerAdvice` — global exception handler
  - `ProblemDetail` (Java/Spring 6+) — RFC 7807 error responses

#### § 11.2.4 — REST Best Practices
  - Resource naming: nouns, not verbs (`/api/users`, not `/api/getUsers`)
  - HTTP status codes: 200, 201, 204, 400, 401, 403, 404, 409, 500
  - Pagination: `Pageable`, `Page<T>`
  - HATEOAS (overview): `spring-boot-starter-hateoas`
  - API versioning: URL path (`/v1/users`), header, query param

---

### 📦 Module 11.3: Spring Data (Database Access)

#### § 11.3.1 — Spring Data JPA
  - `@Entity`, `@Table`, `@Id`, `@GeneratedValue`
  - `@Column`, `@Enumerated`, `@Temporal`
  - Relationships: `@OneToMany`, `@ManyToOne`, `@ManyToMany`, `@OneToOne`
  - `FetchType.LAZY` vs `FetchType.EAGER`
  - `JpaRepository<T, ID>` — CRUD operations out of the box
  - Derived query methods: `findByNameContainingIgnoreCase(String name)`
  - `@Query` — JPQL and native SQL
  - `@Transactional` — transaction management

#### § 11.3.2 — Database Setup
  - H2 (in-memory for dev/test)
  - PostgreSQL, MySQL (production)
  - Flyway / Liquibase — database migration
  - Connection pooling: HikariCP (default in Spring Boot)

---

### 📦 Module 11.4: Spring Security

#### § 11.4.1 — Authentication & Authorization
  - `SecurityFilterChain` configuration
  - In-memory authentication (dev)
  - `UserDetailsService` — custom user loading
  - Password encoding: `BCryptPasswordEncoder`
  - Method-level security: `@PreAuthorize("hasRole('ADMIN')")`

#### § 11.4.2 — JWT Authentication
  - Stateless authentication with JSON Web Tokens
  - JWT structure: header.payload.signature
  - Token generation, validation, refresh
  - Spring Security filter chain integration

---

### 📦 Module 11.5: Spring Ecosystem

#### § 11.5.1 — Key Spring Projects (Overview)
  - **Spring WebFlux** — reactive, non-blocking web framework
  - **Spring Cloud** — microservices: config server, service discovery (Eureka), circuit breaker (Resilience4j), API gateway
  - **Spring Batch** — batch processing
  - **Spring Integration** — enterprise integration patterns
  - **Spring Actuator** — health checks, metrics, monitoring (`/actuator/health`)

#### § 11.5.2 — API Documentation
  - **SpringDoc OpenAPI** (Swagger UI): auto-generated API docs
  - `@Operation`, `@ApiResponse`, `@Schema` annotations

> ### 🛠️ Phase 11 Project: **"TaskFlow — A Full REST API Backend"**
> Build a complete task management REST API:
> - **Stack**: Spring Boot 3 + Spring Data JPA + PostgreSQL + Spring Security
> - **Entities**: `User`, `Project`, `Task`, `Comment`, `Label` (with relationships)
> - **Features**:
>   - User registration & JWT authentication
>   - CRUD for projects, tasks, comments
>   - Task assignment, status transitions (TODO → IN_PROGRESS → DONE)
>   - Filtering: tasks by status, assignee, due date (Spring Data Specifications)
>   - Pagination & sorting
>   - File attachments (upload/download)
> - **Quality**:
>   - Input validation with Bean Validation
>   - Global exception handling with `@RestControllerAdvice` + `ProblemDetail`
>   - Unit tests (Mockito) + Integration tests (Testcontainers + PostgreSQL)
>   - 80%+ code coverage
>   - Flyway database migrations
>   - SpringDoc Swagger UI
>   - Spring Actuator for health/metrics
> - **Build**: Gradle with multi-module (`:api`, `:domain`, `:infrastructure`)
> - **Deployment**: Dockerize with a `Dockerfile` + `docker-compose.yml`

---

## ⚡ PHASE 12 — MICROSERVICES, CLOUD & PRODUCTION JAVA
> *"From monolith to distributed systems — where Java truly shines at scale."*

---

### 📦 Module 12.1: Microservices Architecture

#### § 12.1.1 — Monolith vs. Microservices
  - When monolith is better (most startups!)
  - When microservices make sense (scale, team autonomy, independent deployment)
  - Domain-Driven Design (DDD): bounded contexts
  - Decomposition strategies

#### § 12.1.2 — Inter-Service Communication
  - **Synchronous**: REST, gRPC
  - **Asynchronous**: message queues (RabbitMQ, Apache Kafka)
  - gRPC in Java: Protocol Buffers, `grpc-java`
  - Apache Kafka: producers, consumers, topics, partitions, consumer groups
  - Event-driven architecture & event sourcing (overview)

#### § 12.1.3 — Service Patterns
  - API Gateway (Spring Cloud Gateway)
  - Service Discovery (Eureka, Consul)
  - Circuit Breaker (Resilience4j)
  - Saga pattern for distributed transactions
  - CQRS (Command Query Responsibility Segregation)

---

### 📦 Module 12.2: Containerization & Orchestration

#### § 12.2.1 — Docker for Java
  - Multi-stage `Dockerfile` for Java apps
  - Jib (Google): containerize without Docker daemon
  - Layered JARs for efficient Docker caching
  - Docker Compose for local multi-service development

#### § 12.2.2 — Kubernetes Basics for Java Developers
  - Pods, Deployments, Services, Ingress
  - ConfigMaps & Secrets for configuration
  - Liveness & readiness probes (Spring Actuator integration)
  - Helm charts for packaging
  - GraalVM Native Image for faster startup in containers

---

### 📦 Module 12.3: Observability

#### § 12.3.1 — The Three Pillars
  - **Logging**: structured logging (JSON), ELK Stack (Elasticsearch, Logstash, Kibana)
  - **Metrics**: Micrometer + Prometheus + Grafana
  - **Tracing**: OpenTelemetry + Jaeger/Zipkin — distributed tracing across services
  - Spring Boot Actuator metrics endpoint
  - Correlation IDs / Trace IDs across services

---

### 📦 Module 12.4: Production Hardening

#### § 12.4.1 — Resilience
  - Circuit breaker: Resilience4j `@CircuitBreaker`
  - Retry: `@Retry` with exponential backoff
  - Rate limiting: `@RateLimiter`
  - Bulkhead: isolate failures
  - Timeout: never wait forever

#### § 12.4.2 — Caching
  - Spring Cache abstraction: `@Cacheable`, `@CacheEvict`
  - Redis as distributed cache (Spring Data Redis / Lettuce)
  - Local cache: Caffeine

#### § 12.4.3 — Security in Production
  - OWASP Top 10 awareness
  - SQL injection prevention (parameterized queries — JPA handles this)
  - XSS, CSRF protection
  - Secrets management: HashiCorp Vault, AWS Secrets Manager
  - Dependency vulnerability scanning: OWASP Dependency-Check, Snyk

---

### 📦 Module 12.5: Reactive Programming (Optional Deep Dive)

#### § 12.5.1 — Project Reactor & Spring WebFlux
  - `Mono<T>` — 0 or 1 element
  - `Flux<T>` — 0 to N elements
  - Reactive operators: `map`, `flatMap`, `filter`, `zip`, `merge`
  - Backpressure handling
  - Reactive data access: R2DBC (non-blocking SQL)
  - When to go reactive: high I/O concurrency, streaming data
  - When NOT to: simple CRUD, CPU-bound work

> ### 🛠️ Phase 12 Capstone Project: **"ShopStream — A Microservices E-Commerce Platform"**
> Build a distributed e-commerce system:
> - **Services**:
>   - `user-service` — registration, authentication (JWT), profile
>   - `product-service` — CRUD products, categories, search
>   - `order-service` — place orders, order status, history
>   - `payment-service` — payment processing (mock)
>   - `notification-service` — email/SMS notifications (mock)
>   - `api-gateway` — Spring Cloud Gateway, routing, rate limiting
> - **Communication**:
>   - Sync: REST (between gateway ↔ services)
>   - Async: Apache Kafka (order events → payment → notification)
> - **Data**: each service has its own PostgreSQL database (database-per-service)
> - **Infrastructure**:
>   - Docker Compose for local dev (all services + Kafka + PostgreSQL + Redis)
>   - Redis for caching (product catalog)
>   - Resilience4j for circuit breaker on inter-service calls
> - **Observability**:
>   - Structured logging (JSON) → ELK Stack
>   - Micrometer + Prometheus + Grafana dashboards
>   - OpenTelemetry distributed tracing → Jaeger
> - **Quality**:
>   - Unit + integration tests per service
>   - Contract testing with Spring Cloud Contract or Pact
>   - API documentation: SpringDoc OpenAPI per service
> - **Deployment**:
>   - Multi-stage Dockerfiles (Jib or manual)
>   - Kubernetes manifests or Helm charts
>   - GitHub Actions CI/CD pipeline

---

## 📊 PHASE MAP (Visual Summary)

```
Phase 0   ██░░░░░░░░░░░░░░  Environment & JVM Orientation
Phase 1   ███░░░░░░░░░░░░░  Language Fundamentals
Phase 2   ████░░░░░░░░░░░░  OOP Core (Classes, Objects, Strings)
Phase 3   ██████░░░░░░░░░░  OOP Advanced (Inheritance, Interfaces, Records)
Phase 4   ████████░░░░░░░░  Generics & Collections Framework
Phase 5   █████████░░░░░░░  Exception Handling & Defensive Programming
Phase 6   ██████████░░░░░░  Functional Programming (Lambdas, Streams)
Phase 7   ███████████░░░░░  Concurrency & Multithreading
Phase 8   ████████████░░░░  I/O, NIO & Serialization
Phase 9   █████████████░░░  Build Tools, Testing & Engineering
Phase 10  ██████████████░░  JVM Internals & Performance
Phase 11  ███████████████░  Spring Framework & Enterprise Java
Phase 12  ████████████████  Microservices, Cloud & Production
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
    "I can write           "I use generics,        "I build tested,       "I architect
     Java programs          streams, and            concurrent, and        production
     with OOP"              collections"            performant apps"       systems"
```

---

## 🎯 CERTIFICATION ALIGNMENT

| Phase | Certification |
|-------|--------------|
| 0 – 6 | **Oracle Certified Associate (OCA) — Java SE** |
| 0 – 9 | **Oracle Certified Professional (OCP) — Java SE 17/21** |
| 11 | **VMware Spring Certified Professional** |
| 10 – 12 | **AWS Certified Developer / Solutions Architect** (Java on AWS) |

---

## 📚 RECOMMENDED RESOURCES

| Resource | Type | Phase |
|----------|------|-------|
| *Head First Java* — Kathy Sierra & Bert Bates (3rd Ed.) | 📖 Book (Beginner) | 0–3 |
| *Effective Java* — Joshua Bloch (3rd Ed.) | 📖 Book (MUST READ) | 4–10 |
| *Java: The Complete Reference* — Herbert Schildt | 📖 Book (Reference) | ALL |
| *Modern Java in Action* — Urma, Fusco, Mycroft | 📖 Book (Functional) | 6–7 |
| *Java Concurrency in Practice* — Brian Goetz | 📖 Book (Concurrency Bible) | 7 |
| *Java Performance* — Scott Oaks (2nd Ed.) | 📖 Book | 10 |
| *Spring in Action* — Craig Walls (6th Ed.) | 📖 Book | 11 |
| *Building Microservices* — Sam Newman | 📖 Book | 12 |
| *Release It!* — Michael Nygard | 📖 Book (Production) | 12 |
| **MOOC.fi Java Programming** (Helsinki) | 🌐 Free Course | 0–6 |
| **Baeldung.com** | 🌐 Tutorials | ALL |
| **Java Brains** (YouTube) | 🎥 Video | 0–11 |
| **Amigoscode** (YouTube) | 🎥 Video | 0–11 |
| **Marco Codes** (YouTube) | 🎥 Video (Modern Java) | 4–10 |
| **JetBrains Academy** (Hyperskill) | 🧪 Interactive | 0–8 |
| **Exercism — Java Track** | 🧪 Practice | 1–6 |
| **LeetCode** (Java) | 🧪 DSA Practice | 4 |
| **start.spring.io** | 🧪 Spring Initializr | 11 |
| **cppreference equivalent: docs.oracle.com/javase** | 📄 Official Docs | ALL |

---

## 🗺️ WHERE JAVA TAKES YOU (Career Paths)

```
                                  ┌───────────────────────────┐
                                  │   Backend Engineering     │
                           ┌─────▶│   (REST APIs, Spring,     │
                           │      │    Microservices)          │
                           │      └───────────────────────────┘
                           │      ┌───────────────────────────┐
                           │      │   Android Development     │
                   ┌───────┤─────▶│   (Kotlin/Java, Jetpack)  │
                   │       │      └───────────────────────────┘
                   │       │      ┌───────────────────────────┐
   ┌────────────┐  │       │      │   Big Data Engineering    │
   │            │  │       ├─────▶│   (Hadoop, Spark, Flink,  │
   │  Master    ├──┤       │      │    Kafka, Cassandra)      │
   │  Java      │  │       │      └───────────────────────────┘
   │            │  │       │      ┌───────────────────────────┐
   └────────────┘  │       │      │   Cloud / DevOps          │
                   │       ├─────▶│   (AWS/GCP/Azure, K8s,    │
                   │       │      │    Terraform)              │
                   │       │      └───────────────────────────┘
                   │       │      ┌───────────────────────────┐
                   │       │      │   Financial / Enterprise  │
                   │       ├─────▶│   (Banking, Insurance,    │
                   │       │      │    Trading Systems)        │
                   │       │      └───────────────────────────┘
                   │       │      ┌───────────────────────────┐
                   │       │      │   Platform / Tooling      │
                   └───────┴─────▶│   (Elasticsearch, Kafka,  │
                                  │    Gradle, IntelliJ)       │
                                  └───────────────────────────┘
```

---

> ### 💡 Final Advice
> **"Java is not the most exciting language. It's the most employable one. Its ecosystem, tooling, and backward compatibility are unmatched."**
>
> Five non-negotiable rules for your Java journey:
>
> 1. **Read *Effective Java* by Joshua Bloch** — cover to cover, twice. It's the most important Java book ever written.
> 2. **Use the latest LTS** (Java 21+) — don't learn on Java 8 syntax. Use records, sealed classes, pattern matching, virtual threads.
> 3. **Master the Stream API** — it's how modern Java code is written. If you can't write a stream pipeline fluently, you're not production-ready.
> 4. **Learn Spring Boot deeply** — 80%+ of Java backend jobs use Spring. It's not optional.
> 5. **Write tests from Phase 2 onward** — JUnit + Mockito are not "advanced" topics. They're day-one skills.
>
> The difference between a *Java programmer* and a *Java engineer* is:
> - **Understanding the JVM**, **writing clean, tested code**, **knowing the right collection for the job**, and **building systems that don't fall over at 3 AM**.

---

*This roadmap takes you from "What's `public static void main`?" to "I can architect, build, test, deploy, and monitor a distributed microservices platform running on Kubernetes — all in Java."* ☕🚀

## 📍 WHERE TO PLACE IT

It should be inserted as **the NEW Phase 10**, right after Testing/Engineering (Phase 9) and **before Spring** (current Phase 11). Here's why:

```
Phase 9  — Build Tools, Testing & Engineering
                          ⬇
         ┌────────────────────────────────────────┐
         │  ✅ NEW PHASE 10: DESIGN PATTERNS &    │ ◄── INSERT HERE
         │     SOLID PRINCIPLES                    │
         └────────────────────────────────────────┘
                          ⬇
Phase 11 — JVM Internals & Performance   (becomes Phase 11)
Phase 12 — Spring Framework              (becomes Phase 12)
Phase 13 — Microservices & Cloud         (becomes Phase 13)
```

**Reasoning:**
1. By Phase 9, you've mastered OOP, Generics, Collections, Functional Programming, Concurrency, I/O, and Testing
2. Design Patterns **require** all of those foundations
3. Spring Framework **requires** design pattern knowledge (it IS a pattern factory)
4. You cannot properly architect microservices without SOLID and patterns

---

## ⚡ PHASE 10 — DESIGN PATTERNS & SOLID PRINCIPLES
> *"You can write Java without patterns. You cannot write GOOD Java without them."*

---

### 📦 Module 10.1: SOLID Principles

#### § 10.1.1 — Single Responsibility Principle (SRP)
  - One class should have one, and only one, reason to change
  - Identifying responsibilities: persistence, validation, formatting, business logic
  - Signs of violation: classes with too many methods, mixed concerns
  - Refactoring large classes into focused, cohesive ones
  - Real-world example: separating a `UserService` from `UserValidator` from `UserRepository`

#### § 10.1.2 — Open/Closed Principle (OCP)
  - Classes should be open for extension, closed for modification
  - Achieving OCP through: inheritance, interfaces, composition, strategy pattern
  - Adding new behavior without modifying existing code
  - How the Java Collections Framework follows OCP
  - Violation example: a growing chain of `if/else` or `switch` for each new type

#### § 10.1.3 — Liskov Substitution Principle (LSP)
  - Subtypes must be substitutable for their base types without breaking behavior
  - The classic violation: `Square extends Rectangle` problem
  - Behavioral contracts: preconditions, postconditions, invariants
  - Covariant return types and exception rules in Java
  - How `sealed` classes (Java 17+) help enforce LSP

#### § 10.1.4 — Interface Segregation Principle (ISP)
  - Clients should not be forced to depend on methods they do not use
  - Fat interfaces vs. focused interfaces
  - Splitting large interfaces into smaller, role-based ones
  - How Java's own design follows ISP: `Iterable`, `Comparable`, `Serializable`, `AutoCloseable`
  - Functional interfaces as the ultimate ISP: one method, one responsibility

#### § 10.1.5 — Dependency Inversion Principle (DIP)
  - High-level modules should not depend on low-level modules — both should depend on abstractions
  - Abstractions should not depend on details — details should depend on abstractions
  - Coding to interfaces, not implementations
  - Dependency Injection as the primary DIP mechanism in Java
  - Constructor injection: the preferred approach
  - How Spring's IoC container is a direct implementation of DIP

---

### 📦 Module 10.2: SOLID In Practice

#### § 10.2.1 — Identifying SOLID Violations
  - Code smells that indicate SRP violation: God classes, feature envy
  - Code smells that indicate OCP violation: shotgun surgery, switch-on-type
  - Code smells that indicate LSP violation: type-checking before calling methods
  - Code smells that indicate ISP violation: empty method implementations, `UnsupportedOperationException`
  - Code smells that indicate DIP violation: `new` in business logic, concrete class dependencies

#### § 10.2.2 — Refactoring Toward SOLID
  - Extract Class refactoring (SRP)
  - Extract Interface refactoring (ISP, DIP)
  - Replace Conditional with Polymorphism (OCP)
  - Pull Up / Push Down refactoring (LSP)
  - Introduce Parameter Object (SRP)
  - Using IntelliJ's refactoring tools

#### § 10.2.3 — SOLID and Testability
  - Why SOLID code is inherently easier to test
  - DIP enables mocking and test doubles
  - SRP leads to focused, simple unit tests
  - ISP allows testing through narrow interfaces

---

### 📦 Module 10.3: Creational Design Patterns

#### § 10.3.1 — Singleton Pattern
  - Intent: ensure only one instance of a class exists
  - Enum-based Singleton — the recommended Java approach
  - Holder pattern (Bill Pugh Singleton) — lazy, thread-safe
  - Why double-checked locking is error-prone in Java
  - Singleton anti-pattern: global state, hidden dependencies, testability nightmare
  - When Singleton is acceptable: loggers, configuration, connection pools
  - Modern alternative: dependency injection with singleton scope (Spring beans)

#### § 10.3.2 — Factory Method Pattern
  - Intent: define an interface for creating objects, let subclasses decide which class to instantiate
  - Creator class with abstract factory method
  - Concrete creators override the factory method
  - Java examples: `Calendar.getInstance()`, `NumberFormat.getInstance()`, `Collections.unmodifiableList()`
  - Static factory methods vs constructors (Effective Java Item 1)
  - Advantages: naming, caching, returning subtypes, reducing verbosity

#### § 10.3.3 — Abstract Factory Pattern
  - Intent: create families of related objects without specifying concrete classes
  - Factory of factories
  - Use case: cross-platform UI toolkit, database abstraction (different dialects)
  - Abstract factory vs factory method: scope difference

#### § 10.3.4 — Builder Pattern
  - Intent: construct complex objects step by step
  - The Java Builder pattern (Effective Java Item 2)
  - Fluent interface with method chaining
  - Inner static `Builder` class
  - Immutable objects via builder
  - Java examples: `StringBuilder`, `Stream.Builder`, `HttpRequest.newBuilder()`, `ProcessBuilder`
  - When to use: objects with many optional parameters, immutable objects with validation
  - Builder vs telescoping constructors vs JavaBeans pattern

#### § 10.3.5 — Prototype Pattern
  - Intent: create new objects by copying existing ones
  - `Cloneable` interface and `clone()` method in Java
  - Shallow copy vs deep copy
  - Problems with `Cloneable` (Effective Java Item 13)
  - Modern alternatives: copy constructors, copy factory methods
  - Use case: expensive object creation, object registries

---

### 📦 Module 10.4: Structural Design Patterns

#### § 10.4.1 — Adapter Pattern
  - Intent: make incompatible interfaces work together
  - Class adapter (inheritance) vs object adapter (composition)
  - Java examples: `Arrays.asList()`, `InputStreamReader` (byte stream → character stream), `Collections.enumeration()`
  - Use case: integrating legacy code, wrapping third-party libraries

#### § 10.4.2 — Decorator Pattern
  - Intent: add responsibilities to objects dynamically without modifying their class
  - Wrapping objects: decorator implements the same interface as the wrapped object
  - Java examples: `BufferedReader(new FileReader(...))`, `Collections.synchronizedList()`, `Collections.unmodifiableList()`
  - The entire Java I/O library is built on the Decorator pattern
  - Decorator vs inheritance: composition wins

#### § 10.4.3 — Facade Pattern
  - Intent: provide a simplified interface to a complex subsystem
  - Hiding complexity behind a clean API
  - Java examples: `javax.faces.context.FacesContext`, SLF4J (facade for logging)
  - Use case: simplifying library APIs, legacy system integration

#### § 10.4.4 — Proxy Pattern
  - Intent: provide a surrogate or placeholder for another object to control access
  - Types: protection proxy, virtual proxy (lazy loading), remote proxy, caching proxy
  - Java's built-in dynamic proxies: `java.lang.reflect.Proxy`, `InvocationHandler`
  - How Spring uses proxies: AOP, `@Transactional`, `@Cacheable`, `@Async`
  - CGLIB proxies vs JDK dynamic proxies in Spring

#### § 10.4.5 — Composite Pattern
  - Intent: compose objects into tree structures to represent part-whole hierarchies
  - Uniform treatment of individual objects and compositions
  - Java examples: `java.awt.Component` / `Container`, UI hierarchies
  - Use case: file systems, organization charts, menu systems, expression trees

#### § 10.4.6 — Bridge Pattern
  - Intent: decouple abstraction from implementation so they can vary independently
  - Separating "what" from "how"
  - Use case: platform-independent abstractions, driver architectures
  - JDBC as a real-world bridge: `DriverManager` abstraction → database-specific drivers

#### § 10.4.7 — Flyweight Pattern
  - Intent: share common state among many objects to reduce memory usage
  - Intrinsic state (shared) vs extrinsic state (unique)
  - Java examples: `Integer.valueOf()` cache (-128 to 127), `String` pool, `Boolean.TRUE` / `Boolean.FALSE`
  - `EnumSet` and `EnumMap` internals
  - Use case: rendering millions of game objects, character formatting

---

### 📦 Module 10.5: Behavioral Design Patterns

#### § 10.5.1 — Strategy Pattern
  - Intent: define a family of algorithms, encapsulate each one, and make them interchangeable
  - Strategy interface + concrete strategy implementations
  - Context class holds a reference to the strategy
  - Java examples: `Comparator` is a strategy for sorting, `LayoutManager` in Swing
  - Modern Java: lambdas as lightweight strategies (functional interfaces ARE strategies)
  - Strategy vs `if/else` chain: open/closed principle in action

#### § 10.5.2 — Observer Pattern
  - Intent: define a one-to-many dependency so that when one object changes, all dependents are notified
  - Subject (publisher) + Observer (subscriber)
  - Java's deprecated `java.util.Observable` / `Observer` — why it was removed
  - Modern alternatives: custom event system, `PropertyChangeListener`, reactive streams
  - How Spring's event system works: `ApplicationEvent`, `@EventListener`
  - Use case: UI event handling, message broadcasting, event-driven architecture

#### § 10.5.3 — Command Pattern
  - Intent: encapsulate a request as an object, allowing parameterization, queuing, and undo
  - Command interface with `execute()` method
  - Invoker, Receiver, ConcreteCommand
  - Java examples: `Runnable` is a command, `Callable` is a command with a result
  - Use case: undo/redo systems, transaction systems, macro recording, task queues
  - Command + Memento for undo

#### § 10.5.4 — Template Method Pattern
  - Intent: define the skeleton of an algorithm in a base class, let subclasses fill in specific steps
  - Abstract class with `final` template method + abstract hook methods
  - Hollywood Principle: "Don't call us, we'll call you"
  - Java examples: `AbstractList`, `HttpServlet` (`doGet`, `doPost`), `InputStream.read()`
  - How Spring uses template method: `JdbcTemplate`, `RestTemplate`, `JmsTemplate`
  - Template Method vs Strategy: inheritance vs composition

#### § 10.5.5 — Iterator Pattern
  - Intent: provide a way to access elements sequentially without exposing the collection's structure
  - `Iterable<T>` and `Iterator<T>` interfaces in Java
  - `hasNext()`, `next()`, `remove()`
  - Enhanced for-each loop relies on `Iterable`
  - Custom iterator implementation for custom data structures
  - `Spliterator` for parallel iteration (Java 8+)
  - Fail-fast vs fail-safe iterators: `ConcurrentModificationException`

#### § 10.5.6 — State Pattern
  - Intent: allow an object to change its behavior when its internal state changes
  - State interface + concrete state classes
  - Context delegates behavior to the current state object
  - State transitions: who decides? (context or state object)
  - State vs Strategy: state transitions happen internally, strategy is set externally
  - Use case: TCP connection states, order processing, game character states, UI workflows
  - Modern Java: enum-based state machines, `sealed` interfaces for states

#### § 10.5.7 — Chain of Responsibility Pattern
  - Intent: pass a request along a chain of handlers until one handles it
  - Each handler decides to process or forward
  - Java examples: Servlet Filters, Spring Security filter chain, `java.util.logging` handler chain
  - Use case: request processing pipelines, validation chains, approval workflows

#### § 10.5.8 — Visitor Pattern
  - Intent: add operations to object structures without modifying the objects
  - Double dispatch mechanism
  - Visitor interface with `visit()` method per element type
  - Element interface with `accept(Visitor)` method
  - Modern Java alternative: `sealed` classes + pattern matching `switch` (Java 21+) — replaces classic visitor
  - Use case: AST traversal, report generation on object hierarchies

#### § 10.5.9 — Mediator Pattern
  - Intent: reduce chaotic dependencies between objects by having them communicate through a mediator
  - Colleagues communicate via the mediator, not directly
  - Java examples: `java.util.Timer`, `ExecutorService` as a task mediator
  - Use case: chat rooms, air traffic control, UI component coordination

#### § 10.5.10 — Memento Pattern
  - Intent: capture and restore an object's internal state without violating encapsulation
  - Originator (creates memento), Memento (stores state), Caretaker (manages mementos)
  - Use case: undo/redo, game save states, transaction rollback
  - Java's `Serializable` as a crude memento mechanism

---

### 📦 Module 10.6: Architectural Patterns

#### § 10.6.1 — MVC (Model-View-Controller)
  - Model: data and business logic
  - View: presentation
  - Controller: handles input, updates model
  - How Spring MVC implements this pattern
  - MVC vs MVP vs MVVM

#### § 10.6.2 — Repository Pattern
  - Abstracting data access behind a collection-like interface
  - Separating domain logic from persistence logic
  - How Spring Data JPA's `JpaRepository` implements this pattern
  - Repository vs DAO (Data Access Object)

#### § 10.6.3 — Service Layer Pattern
  - Business logic encapsulated in service classes
  - Controller → Service → Repository layering
  - Transaction boundaries at the service layer
  - Why business logic does NOT belong in controllers or repositories

#### § 10.6.4 — DTO (Data Transfer Object) Pattern
  - Objects for transferring data between layers or over the network
  - DTO vs Entity vs Domain Object
  - Java records as DTOs (Java 16+)
  - MapStruct for entity-to-DTO mapping

#### § 10.6.5 — Dependency Injection (DI) Pattern
  - Constructor injection vs setter injection vs field injection
  - DI containers: Spring IoC, Google Guice, Dagger
  - Manual DI (without a framework) — understanding the pure pattern
  - DI as the practical application of DIP (SOLID)

---

### 📦 Module 10.7: Java-Specific Pattern Idioms

#### § 10.7.1 — Static Factory Method
  - Effective Java Item 1: prefer static factory methods over constructors
  - Naming conventions: `of()`, `from()`, `valueOf()`, `getInstance()`, `create()`, `newInstance()`
  - Advantages: naming, caching, returning subtypes, reduced verbosity

#### § 10.7.2 — Enum Singleton
  - Effective Java Item 3: the safest singleton implementation in Java
  - Serialization-safe, reflection-safe, thread-safe — all for free

#### § 10.7.3 — Immutable Objects Pattern
  - Effective Java Item 17: minimize mutability
  - All fields `private final`, no setters, defensive copies
  - Java records as immutable data carriers
  - `List.of()`, `Map.of()`, `Set.of()` — immutable collections
  - Benefits: thread-safety, simplicity, cacheability

#### § 10.7.4 — Null Object Pattern
  - Provide a "do nothing" default implementation instead of returning `null`
  - Combined with `Optional` for a modern approach
  - Eliminating `NullPointerException` by design
  - `Collections.emptyList()`, `Stream.empty()` as null objects

#### § 10.7.5 — Object Pool Pattern
  - Reuse expensive objects instead of creating new ones
  - Java examples: thread pools (`ExecutorService`), connection pools (HikariCP), string pool
  - When pooling helps vs when it hurts (modern JVMs allocate fast)

#### § 10.7.6 — Marker Interface Pattern
  - Empty interfaces that tag a class with metadata
  - Java examples: `Serializable`, `Cloneable`, `RandomAccess`
  - Modern alternative: annotations (`@Entity`, `@Component`, `@FunctionalInterface`)

---

### 📦 Module 10.8: Anti-Patterns to Recognize & Avoid

#### § 10.8.1 — Creational Anti-Patterns
  - God Object / God Class — one class does everything
  - Telescoping Constructor — too many constructor parameters
  - Static Cling — excessive static methods creating hidden coupling

#### § 10.8.2 — Structural Anti-Patterns
  - Circular Dependencies — A depends on B, B depends on A
  - Yo-Yo Problem — deep inheritance chains that bounce up and down
  - Golden Hammer — using the same pattern/tool for everything

#### § 10.8.3 — Behavioral Anti-Patterns
  - Anemic Domain Model — classes with only getters/setters, no behavior
  - Service Locator — globally accessible registry instead of DI
  - Premature Optimization — designing for performance before correctness

#### § 10.8.4 — How to Detect Anti-Patterns
  - Code metrics: cyclomatic complexity, coupling, cohesion
  - IntelliJ inspections and SonarQube rules
  - Code reviews with pattern awareness
  - Refactoring strategies for each anti-pattern

> ### 🛠️ Phase 10 Project: **"DesignHub — A Pattern Showcase Application"**
> Build a **task management / workflow engine** that intentionally demonstrates every major pattern:
>
> **Creational Patterns:**
> - Factory Method for creating different task types (Bug, Feature, Epic)
> - Builder for constructing complex task configurations with many optional fields
> - Singleton for the application configuration manager (enum-based)
> - Prototype for task templates that users can clone and customize
>
> **Structural Patterns:**
> - Decorator for adding behaviors to tasks dynamically (logging, notification, audit)
> - Adapter for integrating a mock third-party calendar API
> - Composite for task hierarchies (Epic contains Stories, Stories contain Sub-tasks)
> - Proxy for lazy-loading task attachments and access control
> - Facade for a simplified API that hides the complex subsystem
>
> **Behavioral Patterns:**
> - Strategy for different task prioritization algorithms (FIFO, priority-based, deadline-based)
> - Observer for task status change notifications (email, dashboard, log)
> - State for task lifecycle management (Open → InProgress → Review → Done → Closed)
> - Command for undo/redo of task operations (change status, reassign, edit)
> - Template Method for different report generators (PDF, CSV, Console) sharing a skeleton
> - Iterator for custom filtered traversal of task collections
> - Chain of Responsibility for task validation pipeline (format → permissions → business rules)
>
> **Architecture:**
> - Full SOLID compliance across all modules
> - Clean layering: Controller → Service → Repository (interfaces everywhere)
> - DTOs with records for data transfer
> - Dependency Injection done manually (no Spring yet — understand the pure pattern)
>
> **Quality:**
> - Every pattern must have a corresponding unit test
> - A written explanation in a README documenting each pattern: problem, solution, where it's used, and tradeoffs
> - UML class diagrams for each pattern using draw.io or PlantUML

---

## 📍 UPDATED PHASE MAP

```
Phase 0   ██░░░░░░░░░░░░░░░░  Environment & JVM Orientation
Phase 1   ███░░░░░░░░░░░░░░░  Language Fundamentals
Phase 2   ████░░░░░░░░░░░░░░  OOP Core
Phase 3   ██████░░░░░░░░░░░░  OOP Advanced
Phase 4   ████████░░░░░░░░░░  Generics & Collections
Phase 5   █████████░░░░░░░░░  Exception Handling
Phase 6   ██████████░░░░░░░░  Functional Programming
Phase 7   ███████████░░░░░░░  Concurrency & Multithreading
Phase 8   ████████████░░░░░░  I/O, NIO & Serialization
Phase 9   █████████████░░░░░  Build Tools, Testing & Engineering
Phase 10  ██████████████░░░░  ✅ DESIGN PATTERNS & SOLID  ◄── NEW
Phase 11  ███████████████░░░  JVM Internals & Performance
Phase 12  ████████████████░░  Spring Framework & Enterprise Java
Phase 13  █████████████████░  Microservices, Cloud & Production
```

> **Notice how Phase 10 (Patterns) feeds directly into Phase 12 (Spring).** When you see Spring's `@Component`, `@Autowired`, `JdbcTemplate`, `@EventListener`, `@Transactional` proxy — you'll immediately recognize: *"That's Factory... that's DI... that's Template Method... that's Observer... that's Proxy."* Without Phase 10, Spring feels like magic. With Phase 10, Spring feels **inevitable**.