# 🚀 THE ULTIMATE C++ ROADMAP
### From Zero to Modern C++ Mastery

> **Structure:** Phase → Modules → Sections
> **Estimated Duration:** ~8-12 Months (Dedicated Study)
> **Prerequisite:** Basic understanding of C is helpful but not mandatory

---

## ⚡ PHASE 0 — ENVIRONMENT SETUP & C++ ORIENTATION
> *"C++ is a multiparadigm language. Understanding its philosophy comes first."*

---

### 📦 Module 0.1: Understanding the C++ Ecosystem

#### § 0.1.1 — What is C++ & Why Learn It
  - History: Bjarne Stroustrup, "C with Classes" (1979) → C++ (1983)
  - C++ philosophy: zero-cost abstractions, "you don't pay for what you don't use"
  - Where C++ dominates: game engines, OS kernels, browsers, databases, embedded, HFT, compilers, simulations

#### § 0.1.2 — C++ vs. C vs. Other Languages
  - C++ is NOT a superset of C (common misconception)
  - Key differences from C: classes, templates, RAII, exceptions, namespaces, references, overloading
  - C++ vs. Java/C#: manual memory management, no GC, value semantics
  - C++ vs. Rust: similar performance, different safety model

#### § 0.1.3 — C++ Standards Timeline
  - **C++98/03** — the classic (STL, templates, exceptions)
  - **C++11** — the modern revolution (move semantics, lambdas, `auto`, smart pointers)
  - **C++14** — quality of life (generic lambdas, `std::make_unique`)
  - **C++17** — structured bindings, `std::optional`, `std::variant`, `if constexpr`
  - **C++20** — concepts, ranges, coroutines, modules, `<=>` (spaceship)
  - **C++23** — `std::expected`, `std::print`, `std::flat_map`, deducing `this`
  - **C++26** — contracts, reflection (upcoming)

---

### 📦 Module 0.2: Setting Up the Development Environment

#### § 0.2.1 — Compilers: Installation & Selection
  - **GCC (g++)**: Linux/macOS/MinGW — `sudo apt install g++`
  - **Clang (clang++)**: Linux/macOS — superior error messages
  - **MSVC**: Windows — Visual Studio Build Tools
  - Checking version & supported standard: `g++ --version`, `g++ -std=c++20`

#### § 0.2.2 — Editors & IDEs
  - **VS Code** + C/C++ extension + clangd (lightweight)
  - **CLion** (JetBrains — best debugging experience)
  - **Visual Studio** (Windows — full-featured)
  - **Vim/Neovim** + clangd LSP (advanced)
  - **Qt Creator** (for GUI development later)

#### § 0.2.3 — Compiling & Running Your First Program
  - Writing `hello.cpp`
  - Compiling: `g++ -std=c++17 -Wall -Wextra -o hello hello.cpp`
  - Understanding compilation flags: `-std=`, `-Wall`, `-Wextra`, `-Werror`, `-g`, `-O2`, `-pedantic`
  - Compiler Explorer (godbolt.org) — seeing generated assembly

#### § 0.2.4 — Build Systems Introduction
  - Manual compilation for multi-file projects
  - Basic `Makefile` for C++
  - **CMake** introduction: `CMakeLists.txt`, `cmake`, `make`
  - Creating a minimal CMake project structure

---

### 📦 Module 0.3: Essential Tooling for C++ Development

#### § 0.3.1 — Debugging Tools
  - **GDB**: breakpoints, stepping, watching variables, backtrace
  - **LLDB**: Clang's debugger
  - Visual Studio / CLion integrated debuggers
  - Core dumps analysis

#### § 0.3.2 — Memory & Analysis Tools
  - **Valgrind (memcheck)**: leak detection
  - **AddressSanitizer (ASan)**: `-fsanitize=address`
  - **UndefinedBehaviorSanitizer (UBSan)**: `-fsanitize=undefined`
  - **ThreadSanitizer (TSan)**: `-fsanitize=thread`

#### § 0.3.3 — Documentation & Help
  - cppreference.com (the C++ bible — bookmark it)
  - C++ Core Guidelines (Stroustrup & Sutter)
  - Using `man` pages for POSIX functions
  - Reading compiler error messages (Clang's are the best)

> ### 🛠️ Phase 0 Project: **"Environment Validator"**
> Write a C++ program that prints:
> - The C++ standard being used (`__cplusplus`)
> - Compiler name & version (`__GNUC__`, `__clang__`, `_MSC_VER`)
> - Sizes of all fundamental types (`sizeof`)
> - System endianness (detect at runtime)
> - Build it with **CMake**, run it under **Valgrind**, debug it with **GDB** (set a breakpoint in `main`). Screenshot every step.

---

## ⚡ PHASE 1 — C++ LANGUAGE FUNDAMENTALS
> *"Master the basics — they never stop being relevant."*

---

### 📦 Module 1.1: Basic Syntax & Program Structure

#### § 1.1.1 — Anatomy of a C++ Program
  - `#include <iostream>`, `int main()`, `return 0;`
  - `std::cout`, `std::cin`, `std::endl` vs `'\n'`
  - The `<<` (insertion) and `>>` (extraction) operators

#### § 1.1.2 — Namespaces
  - What namespaces solve (name collisions)
  - `std::` namespace
  - `using namespace std;` — why it's bad practice (especially in headers)
  - `using std::cout;` — selective using-declaration
  - Creating custom namespaces
  - Nested namespaces (C++17: `namespace A::B::C {}`)
  - Anonymous namespaces (internal linkage)

#### § 1.1.3 — Comments & Documentation
  - `//` single-line, `/* */` multi-line
  - Doxygen-style documentation: `///`, `/** */`, `@param`, `@return`, `@brief`

---

### 📦 Module 1.2: Data Types & Variables

#### § 1.2.1 — Fundamental Types
  - Boolean: `bool` (`true`, `false`)
  - Character: `char`, `char8_t`, `char16_t`, `char32_t`, `wchar_t`
  - Integer: `short`, `int`, `long`, `long long` (signed/unsigned)
  - Floating point: `float`, `double`, `long double`
  - `void`
  - `sizeof()`, `<climits>`, `<cfloat>`
  - Fixed-width: `int32_t`, `uint64_t`, `size_t`, `ptrdiff_t` (`<cstdint>`)

#### § 1.2.2 — Variable Declaration & Initialization
  - **Copy initialization:** `int x = 5;`
  - **Direct initialization:** `int x(5);`
  - **Uniform (brace) initialization:** `int x{5};` (preferred — prevents narrowing)
  - **Default initialization** vs. **value initialization** vs. **zero initialization**
  - Uninitialized variables — undefined behavior!

#### § 1.2.3 — Type Deduction & Aliases
  - `auto` keyword (C++11) — let the compiler deduce the type
  - `decltype` — deduce the type of an expression
  - `decltype(auto)` (C++14)
  - Type aliases: `typedef` vs `using` (prefer `using` in modern C++)
  - `using IntVec = std::vector<int>;`

#### § 1.2.4 — Constants & Immutability
  - `const` — runtime constant
  - `constexpr` — compile-time constant (C++11)
  - `consteval` — must be evaluated at compile time (C++20)
  - `constinit` — compile-time initialized, runtime usable (C++20)
  - `#define` — preprocessor macros (avoid in modern C++)
  - `enum` vs `enum class` (scoped enums — prefer `enum class`)

#### § 1.2.5 — Literals
  - Integer: `42`, `0x2A`, `0b101010`, `052`, `1'000'000` (digit separators C++14)
  - Floating: `3.14`, `3.14f`, `3.14L`, `1.0e10`
  - Character: `'A'`, `'\n'`, `'\x41'`
  - String: `"hello"`, raw strings `R"(no\escape\needed)"`
  - User-defined literals: `operator""_km` (C++11)
  - `nullptr` (not `NULL`, not `0`)

---

### 📦 Module 1.3: Operators

#### § 1.3.1 — Arithmetic & Assignment Operators
  - `+`, `-`, `*`, `/`, `%`
  - `=`, `+=`, `-=`, `*=`, `/=`, `%=`
  - Increment/Decrement: `++i` (prefer) vs `i++`

#### § 1.3.2 — Comparison & Logical Operators
  - `==`, `!=`, `<`, `>`, `<=`, `>=`
  - Three-way comparison (spaceship): `<=>` (C++20)
  - `&&`, `||`, `!` — short-circuit evaluation

#### § 1.3.3 — Bitwise Operators
  - `&`, `|`, `^`, `~`, `<<`, `>>`
  - `<<=`, `>>=`, `&=`, `|=`, `^=`
  - Practical uses: flags, masks, bit manipulation

#### § 1.3.4 — Special Operators
  - Ternary: `condition ? a : b`
  - `sizeof`, `alignof`
  - `typeid` (RTTI)
  - Scope resolution: `::`
  - Member access: `.`, `->`, `.*`, `->*`
  - Comma operator
  - **Operator precedence & associativity** (know the full table)

---

### 📦 Module 1.4: Control Flow

#### § 1.4.1 — Conditional Statements
  - `if`, `else if`, `else`
  - `if` with initializer (C++17): `if (auto it = map.find(key); it != map.end())`
  - `switch` — `case`, `default`, `break`, `[[fallthrough]]` attribute
  - `switch` on `enum class`

#### § 1.4.2 — Loops
  - `for` loop (classic C-style)
  - **Range-based for** (C++11): `for (auto& x : container)`
  - `while`, `do-while`
  - `break`, `continue`
  - Avoiding infinite loops

#### § 1.4.3 — Modern Control Flow
  - `if constexpr` (C++17) — compile-time branching
  - `[[likely]]` / `[[unlikely]]` attributes (C++20)
  - `goto` — when it's acceptable (almost never)

---

### 📦 Module 1.5: Type Conversions

#### § 1.5.1 — Implicit Conversions
  - Numeric promotions & conversions
  - Narrowing conversions (prevented by brace initialization)
  - Boolean conversions
  - Pointer conversions

#### § 1.5.2 — Explicit Casts (Modern C++ Style)
  - `static_cast<T>()` — safe, compile-time checked
  - `dynamic_cast<T>()` — runtime polymorphic cast (requires RTTI)
  - `const_cast<T>()` — add/remove const
  - `reinterpret_cast<T>()` — dangerous, bit-level reinterpretation
  - Why NEVER to use C-style casts `(int)x` in C++

> ### 🛠️ Phase 1 Project: **"Type Explorer & Expression Evaluator"**
> Build a CLI program that:
> 1. Demonstrates every fundamental type with its `sizeof`, min, max values
> 2. Shows implicit conversions in action (with warnings enabled)
> 3. Implements a basic expression evaluator using `std::cin` that handles `+`, `-`, `*`, `/`, `%` with proper type promotions
> 4. Uses `enum class` for operation types, `auto` for deduction, and brace initialization everywhere
> 5. Uses C++17 `if` with initializer for input validation

---

## ⚡ PHASE 2 — FUNCTIONS & REFERENCES
> *"Functions in C++ are far more powerful than in C."*

---

### 📦 Module 2.1: Function Fundamentals

#### § 2.1.1 — Declaration, Definition & Calling
  - Function prototypes (forward declarations)
  - Definition with body
  - Return types, `void` functions
  - `[[nodiscard]]` attribute (C++17) — force callers to use return value

#### § 2.1.2 — Parameter Passing Mechanisms
  - **Pass by value** — copies the argument
  - **Pass by reference** — `int& x` (alias, no copy)
  - **Pass by const reference** — `const int& x` (read-only, no copy — the default for large objects)
  - **Pass by pointer** — `int* x` (C-style, still used)
  - When to use which: the decision flowchart

#### § 2.1.3 — Default Arguments
  - Syntax: `void foo(int x, int y = 10);`
  - Rules: defaults must be rightmost parameters
  - Defaults in declaration (header) only, not definition

#### § 2.1.4 — Function Overloading
  - Same name, different parameter lists
  - Overload resolution rules
  - Ambiguity errors
  - Overloading vs. default arguments — tradeoffs

---

### 📦 Module 2.2: References — Deep Dive

#### § 2.2.1 — Lvalue References (`&`)
  - What is an lvalue? (has an address, has a name)
  - `int& ref = x;` — must bind to an lvalue
  - References are NOT pointers (no null, no reseat, no `sizeof` of their own)
  - References as function parameters & return values
  - Dangling references — returning a reference to a local variable (UB!)

#### § 2.2.2 — Const References
  - `const int& ref` — can bind to rvalues too!
  - Lifetime extension of temporaries bound to const references
  - Why `const std::string&` is the standard way to pass strings

#### § 2.2.3 — Rvalue References (`&&`) — Introduction
  - What is an rvalue? (temporary, no persistent address)
  - `int&& rref = 42;` — binds to temporaries
  - Why rvalue references exist: enabling move semantics (deep dive in Phase 5)

---

### 📦 Module 2.3: Advanced Function Features

#### § 2.3.1 — Inline Functions
  - `inline` keyword — hint to the compiler
  - Header-only functions and ODR (One Definition Rule)
  - `inline` variables (C++17)

#### § 2.3.2 — `constexpr` Functions
  - Functions evaluated at compile time
  - `constexpr` vs `consteval` (C++20)
  - `constexpr` rules: what's allowed inside

#### § 2.3.3 — Recursion in C++
  - Classic recursion & base cases
  - Tail recursion optimization
  - `constexpr` recursion (compile-time computation)

#### § 2.3.4 — Function Pointers & `std::function`
  - C-style function pointers: `int (*fptr)(int, int)`
  - `std::function<int(int, int)>` — type-erased callable wrapper
  - Callbacks using `std::function`
  - Performance: function pointer vs `std::function` vs templates

#### § 2.3.5 — Lambda Expressions (C++11+)
  - Syntax: `[captures](params) -> return_type { body }`
  - Capture modes: `[=]` by value, `[&]` by reference, `[x]`, `[&x]`, `[this]`, `[*this]`
  - Mutable lambdas: `[x]() mutable { x++; }`
  - Generic lambdas (C++14): `[](auto x) { ... }`
  - Immediately invoked lambdas: `[](){ ... }()`
  - Lambda as comparator for `std::sort`, `std::priority_queue`
  - Lambdas vs. functors vs. function pointers
  - Template lambdas (C++20): `[]<typename T>(T x) { ... }`
  - Captureless lambdas convert to function pointers

---

### 📦 Module 2.4: Program Organization

#### § 2.4.1 — Header & Source File Separation
  - `.h` / `.hpp` for declarations
  - `.cpp` for definitions
  - Include guards: `#ifndef` / `#define` / `#endif` vs `#pragma once`
  - Forward declarations to minimize includes

#### § 2.4.2 — Compilation Model & Linkage
  - Translation units
  - Internal linkage (`static`, anonymous namespaces)
  - External linkage (`extern`)
  - One Definition Rule (ODR)
  - Why templates must be in headers (or explicit instantiation)

#### § 2.4.3 — CMake for Real Projects
  - `add_executable()`, `add_library()`
  - `target_include_directories()`, `target_link_libraries()`
  - `PUBLIC` / `PRIVATE` / `INTERFACE` linkage
  - Setting C++ standard: `set(CMAKE_CXX_STANDARD 17)`
  - Out-of-source builds: `cmake -B build && cmake --build build`

> ### 🛠️ Phase 2 Project: **"Functional Toolkit Library"**
> Create a **header-only library** (`functional_toolkit.hpp`) containing:
> - `map(container, func)` — apply a function to every element
> - `filter(container, predicate)` — return elements matching a predicate
> - `reduce(container, func, initial)` — fold/accumulate
> - `compose(f, g)` — return a new lambda that is `f(g(x))`
> - `memoize(func)` — return a cached version of a function
> - All implemented with **lambdas**, **templates**, and **`std::function`**
> - Write a `main.cpp` demo + build with **CMake**
> - Example: `auto doubled = map(vec, [](int x){ return x * 2; });`

---

## ⚡ PHASE 3 — OBJECT-ORIENTED PROGRAMMING (OOP)
> *"C++ didn't invent OOP, but it perfected the performance-conscious version of it."*

---

### 📦 Module 3.1: Classes & Objects — Fundamentals

#### § 3.1.1 — Defining Classes
  - `class` vs `struct` (default access: `private` vs `public`)
  - Member variables (data members / attributes)
  - Member functions (methods)
  - Accessing members: `.` and `->`
  - Object instantiation on stack vs. heap

#### § 3.1.2 — Access Specifiers
  - `public` — accessible everywhere
  - `private` — accessible only within the class
  - `protected` — accessible within class & derived classes
  - Encapsulation: why private data + public interface matters

#### § 3.1.3 — Constructors
  - Default constructor
  - Parameterized constructors
  - **Member initializer list** — `MyClass(int x) : m_x{x} {}` (prefer over assignment)
  - Why initializer lists are necessary for `const` members, references, base classes
  - Delegating constructors (C++11): one constructor calling another
  - `explicit` keyword — preventing implicit conversions

#### § 3.1.4 — Destructors
  - `~ClassName()` — cleanup
  - When destructors are called (scope exit, `delete`)
  - RAII principle: resource acquisition is initialization
  - Virtual destructors (why & when — covered in inheritance)

#### § 3.1.5 — The `this` Pointer
  - Implicit pointer to current object
  - `this->member` for disambiguation
  - Returning `*this` for method chaining (fluent interface)

---

### 📦 Module 3.2: The Rule of Zero/Three/Five

#### § 3.2.1 — Special Member Functions
  - Default constructor
  - Copy constructor: `MyClass(const MyClass& other)`
  - Copy assignment operator: `MyClass& operator=(const MyClass& other)`
  - Destructor: `~MyClass()`
  - Move constructor: `MyClass(MyClass&& other) noexcept` (C++11)
  - Move assignment operator: `MyClass& operator=(MyClass&& other) noexcept` (C++11)

#### § 3.2.2 — Rule of Three (Pre-C++11)
  - If you define one of {destructor, copy constructor, copy assignment}, define all three
  - Deep copy vs. shallow copy

#### § 3.2.3 — Rule of Five (C++11+)
  - Add move constructor + move assignment to the three
  - Implementing move semantics correctly with `std::move` and `std::exchange`

#### § 3.2.4 — Rule of Zero (Modern Best Practice)
  - Use smart pointers and standard containers
  - Let the compiler generate all special members
  - `= default` and `= delete` (explicitly defaulted/deleted functions)

---

### 📦 Module 3.3: Operator Overloading

#### § 3.3.1 — Overloading Arithmetic & Comparison Operators
  - `operator+`, `operator-`, `operator*`, `operator/`
  - `operator==`, `operator!=`, `operator<`, `operator>`
  - Member function vs. free (friend) function overload
  - `operator<=>` (spaceship — C++20) — auto-generates all comparisons

#### § 3.3.2 — Overloading Stream Operators
  - `operator<<` (output) — must be a free/friend function
  - `operator>>` (input)
  - Chaining: returning `std::ostream&`

#### § 3.3.3 — Overloading Subscript & Function Call
  - `operator[]` — array-like access
  - `operator()` — functor (callable object)
  - `operator->` and `operator*` — smart pointer pattern

#### § 3.3.4 — Overloading Assignment & Conversion
  - `operator=` — copy & move assignment
  - Copy-and-swap idiom for exception-safe assignment
  - Conversion operators: `operator int() const`, `explicit operator bool() const`

---

### 📦 Module 3.4: Static Members & Friends

#### § 3.4.1 — Static Data Members
  - Shared across all instances
  - `inline static` initialization (C++17)
  - Use cases: counters, shared configuration

#### § 3.4.2 — Static Member Functions
  - No `this` pointer
  - Called via `ClassName::func()`
  - Factory method pattern

#### § 3.4.3 — Friend Functions & Classes
  - `friend` keyword — granting private access
  - Friend functions for operator overloading
  - Friend classes
  - Why friends don't break encapsulation (they're part of the interface)

---

### 📦 Module 3.5: Inheritance

#### § 3.5.1 — Basic Inheritance
  - `class Derived : public Base {}`
  - `public`, `protected`, `private` inheritance
  - Constructor & destructor call order (base first, derived first to destruct)
  - `using Base::Base;` — inheriting constructors (C++11)

#### § 3.5.2 — Polymorphism & Virtual Functions
  - `virtual` keyword — enabling runtime dispatch
  - `override` specifier (C++11) — catch errors at compile time
  - `final` specifier (C++11) — prevent further overriding
  - Virtual function tables (vtable) — how polymorphism works under the hood
  - **Virtual destructors** — essential when deleting via base pointer
  - Pure virtual functions: `virtual void draw() = 0;` — abstract classes

#### § 3.5.3 — Abstract Classes & Interfaces
  - Abstract class: has at least one pure virtual function
  - Interface pattern: class with ONLY pure virtual functions
  - Cannot instantiate abstract classes
  - Designing class hierarchies

#### § 3.5.4 — Multiple Inheritance
  - Syntax: `class C : public A, public B {}`
  - The Diamond Problem
  - Virtual inheritance: `class B : virtual public A {}`
  - Why to prefer composition over multiple inheritance
  - Mixin classes

#### § 3.5.5 — Casting in Class Hierarchies
  - `static_cast` — compile-time up/downcast (unsafe downcast)
  - `dynamic_cast` — runtime-checked downcast (requires `virtual`)
  - RTTI: `typeid`, `type_info`
  - When downcasting indicates a design smell

---

### 📦 Module 3.6: Const Correctness in Classes

#### § 3.6.1 — Const Member Functions
  - `int getValue() const;` — promises not to modify the object
  - Const overloading: mutable and const versions of the same function
  - `mutable` keyword — allows modification in const functions (e.g., caching, mutexes)

#### § 3.6.2 — Const Objects
  - `const MyClass obj;` — can only call const member functions
  - Returning `const&` to prevent modification of internals

> ### 🛠️ Phase 3 Project: **"Linear Algebra Library (LinAlg)"**
> Build a **matrix & vector math library**:
> - `class Vec2`, `Vec3`, `Vec4` — with operator overloading (`+`, `-`, `*`, `==`, `[]`, `<<`)
> - `class Matrix4x4` — with `operator*` (matrix multiplication), `transpose()`, `inverse()`, `determinant()`
> - Inheritance: `Shape` (abstract) → `Circle`, `Rectangle`, `Triangle`
>   - Pure virtual: `area()`, `perimeter()`, `draw()` (prints ASCII art)
>   - `operator<<` for printing shape info
> - Rule of Five: implement a `DynamicMatrix` class with heap-allocated data
> - Use `virtual` destructors, `override`, `final`, `explicit`
> - Unit test with assertions, build with CMake

---

## ⚡ PHASE 4 — STANDARD TEMPLATE LIBRARY (STL)
> *"The STL is arguably the most well-designed generic library in any language."*

---

### 📦 Module 4.1: STL Overview & Iterators

#### § 4.1.1 — STL Architecture
  - Three pillars: **Containers**, **Algorithms**, **Iterators**
  - Function objects (functors) & comparators
  - Allocators (advanced — mentioned for completeness)

#### § 4.1.2 — Iterator Categories
  - **Input iterator** — read-only, single-pass forward
  - **Output iterator** — write-only, single-pass forward
  - **Forward iterator** — read/write, multi-pass forward
  - **Bidirectional iterator** — forward + backward
  - **Random access iterator** — bidirectional + jump (`[]`, `+n`, `-n`)
  - **Contiguous iterator** (C++20) — elements adjacent in memory
  - `begin()`, `end()`, `cbegin()`, `cend()`, `rbegin()`, `rend()`

#### § 4.1.3 — Iterator Utilities
  - `std::advance()`, `std::distance()`, `std::next()`, `std::prev()`
  - `std::back_inserter()`, `std::front_inserter()`, `std::inserter()`
  - Stream iterators: `std::istream_iterator`, `std::ostream_iterator`

---

### 📦 Module 4.2: Sequence Containers

#### § 4.2.1 — `std::vector<T>`
  - Dynamic array — THE default container
  - `push_back()`, `emplace_back()`, `pop_back()`
  - `size()`, `capacity()`, `reserve()`, `shrink_to_fit()`
  - Element access: `[]`, `at()` (bounds-checked), `front()`, `back()`, `data()`
  - Iterator invalidation rules
  - `std::vector<bool>` — the controversial specialization (avoid it)

#### § 4.2.2 — `std::array<T, N>`
  - Fixed-size array on the stack
  - `constexpr`-friendly
  - Zero overhead over raw arrays

#### § 4.2.3 — `std::deque<T>`
  - Double-ended queue
  - `push_front()`, `push_back()`
  - Non-contiguous memory — NOT cache-friendly like vector

#### § 4.2.4 — `std::list<T>` & `std::forward_list<T>`
  - Doubly linked list & singly linked list
  - `splice()`, `merge()`, `sort()` (member functions, not `std::sort`)
  - When to use: frequent insertion/deletion in the middle (rare in practice)

#### § 4.2.5 — `std::string` (as a container)
  - `std::string` IS a `std::basic_string<char>`
  - `find()`, `substr()`, `replace()`, `compare()`
  - `c_str()`, `data()` — interop with C
  - `std::string_view` (C++17) — non-owning, lightweight view (avoids copies!)
  - Small String Optimization (SSO)

---

### 📦 Module 4.3: Associative Containers

#### § 4.3.1 — `std::map<K, V>` & `std::multimap<K, V>`
  - Ordered key-value pairs (red-black tree)
  - `insert()`, `emplace()`, `[]`, `at()`, `find()`, `count()`
  - `try_emplace()` (C++17), `insert_or_assign()` (C++17)
  - Iterating in sorted order

#### § 4.3.2 — `std::set<T>` & `std::multiset<T>`
  - Ordered unique/non-unique elements
  - `insert()`, `find()`, `count()`, `erase()`
  - `contains()` (C++20)
  - Custom comparators: `std::set<T, Comparator>`

#### § 4.3.3 — `std::unordered_map<K, V>` & `std::unordered_set<T>`
  - Hash table based — O(1) average lookup
  - Requires `std::hash<K>` specialization for custom keys
  - Bucket interface: `bucket_count()`, `load_factor()`, `rehash()`
  - When to use `unordered_*` vs ordered: performance vs. ordering

---

### 📦 Module 4.4: Container Adaptors

#### § 4.4.1 — `std::stack<T>`
  - LIFO — `push()`, `pop()`, `top()`
  - Default underlying: `std::deque`

#### § 4.4.2 — `std::queue<T>`
  - FIFO — `push()`, `pop()`, `front()`, `back()`

#### § 4.4.3 — `std::priority_queue<T>`
  - Max-heap by default
  - Custom comparator for min-heap: `std::greater<T>`
  - Use case: Dijkstra, task scheduling

---

### 📦 Module 4.5: STL Algorithms

#### § 4.5.1 — Non-Modifying Algorithms
  - `std::find`, `std::find_if`, `std::count`, `std::count_if`
  - `std::all_of`, `std::any_of`, `std::none_of`
  - `std::for_each`
  - `std::search`, `std::adjacent_find`
  - `std::equal`, `std::mismatch`

#### § 4.5.2 — Modifying Algorithms
  - `std::copy`, `std::copy_if`, `std::move`
  - `std::transform` — the map operation
  - `std::fill`, `std::generate`
  - `std::replace`, `std::replace_if`
  - `std::remove` / `std::remove_if` + `erase` (erase-remove idiom)
  - `std::erase` / `std::erase_if` (C++20 — finally!)
  - `std::unique`
  - `std::reverse`, `std::rotate`, `std::shuffle`

#### § 4.5.3 — Sorting & Searching
  - `std::sort`, `std::stable_sort`, `std::partial_sort`
  - `std::nth_element`
  - `std::binary_search`, `std::lower_bound`, `std::upper_bound`, `std::equal_range`
  - `std::merge`, `std::inplace_merge`
  - `std::min_element`, `std::max_element`, `std::minmax_element`
  - `std::clamp` (C++17)

#### § 4.5.4 — Numeric Algorithms (`<numeric>`)
  - `std::accumulate`, `std::reduce` (C++17, parallelizable)
  - `std::inner_product`, `std::transform_reduce` (C++17)
  - `std::partial_sum`, `std::inclusive_scan`, `std::exclusive_scan` (C++17)
  - `std::iota` — fill with incrementing values
  - `std::gcd`, `std::lcm` (C++17)

---

### 📦 Module 4.6: Ranges (C++20)

#### § 4.6.1 — Ranges Basics
  - What are ranges? (an abstraction over iterator pairs)
  - `std::ranges::sort`, `std::ranges::find`, etc.
  - Projections: `std::ranges::sort(vec, {}, &Person::age)`

#### § 4.6.2 — Views (Lazy Evaluation)
  - `std::views::filter`, `std::views::transform`
  - `std::views::take`, `std::views::drop`
  - `std::views::reverse`, `std::views::split`
  - `std::views::iota` — infinite range
  - Pipe syntax: `vec | filter(pred) | transform(func) | take(5)`
  - Views are lazy — no allocation, evaluated on demand

> ### 🛠️ Phase 4 Project: **"Data Analysis CLI Tool"**
> Build a CLI tool that reads a CSV file (e.g., sales data) and:
> 1. Parses it into a `std::vector<Record>` using `std::string_view` and `std::getline`
> 2. **Sorts** by any column (name, date, revenue) — user's choice
> 3. **Filters** records by criteria (date range, minimum revenue) using `std::copy_if` or ranges
> 4. **Aggregates**: sum, average, min, max of numeric columns using `std::accumulate` / `std::reduce`
> 5. **Groups** data using `std::unordered_map` (e.g., revenue per region)
> 6. **Searches** for records using `std::lower_bound` on sorted data
> 7. Outputs results in a formatted table using `<iomanip>` or `std::format` (C++20)
> 8. Implement a **C++20 Ranges pipeline** version of the same queries for comparison

---

## ⚡ PHASE 5 — MEMORY MANAGEMENT & MOVE SEMANTICS
> *"Modern C++ doesn't do new/delete. It does smart pointers and RAII."*

---

### 📦 Module 5.1: Memory Model in C++

#### § 5.1.1 — Stack vs. Heap Allocation
  - Stack: automatic, fast, deterministic destruction
  - Heap: `new` / `delete`, `new[]` / `delete[]` — manual (error-prone)
  - When to use which
  - Memory layout: text, data, BSS, heap, stack

#### § 5.1.2 — RAII (Resource Acquisition Is Initialization)
  - The most important C++ idiom
  - Constructor acquires, destructor releases
  - RAII for files, locks, memory, sockets, database connections
  - Scope-bound resource management

---

### 📦 Module 5.2: Smart Pointers (`<memory>`)

#### § 5.2.1 — `std::unique_ptr<T>`
  - Exclusive ownership — only one owner
  - Zero overhead (same size as raw pointer)
  - `std::make_unique<T>(args...)` (C++14)
  - Cannot be copied, can be moved
  - Custom deleters: `std::unique_ptr<T, Deleter>`
  - `unique_ptr` for arrays: `std::unique_ptr<int[]>`
  - Replacing `new`/`delete` in 99% of cases

#### § 5.2.2 — `std::shared_ptr<T>`
  - Shared ownership — reference counting
  - `std::make_shared<T>(args...)` — single allocation (control block + object)
  - `use_count()` — reference count
  - Thread-safe reference counting (but not thread-safe access!)
  - Overhead: control block (counter + deleter + allocator)
  - Aliasing constructor

#### § 5.2.3 — `std::weak_ptr<T>`
  - Non-owning observer of `shared_ptr`
  - Breaks circular references (the circular dependency problem)
  - `lock()` → returns `shared_ptr` (or empty if expired)
  - `expired()` — check if pointed-to object still exists

#### § 5.2.4 — Smart Pointer Best Practices
  - **Default to `unique_ptr`**, upgrade to `shared_ptr` only when truly shared
  - Never use raw `new` / `delete` in modern C++
  - Factory functions returning `unique_ptr`
  - Passing smart pointers to functions: by value, by reference, or raw pointer? (follow the C++ Core Guidelines)

---

### 📦 Module 5.3: Move Semantics — Deep Dive

#### § 5.3.1 — Value Categories (lvalue, rvalue, xvalue, prvalue, glvalue)
  - lvalue: has identity, can't be moved from (implicitly)
  - prvalue: temporary, no identity
  - xvalue: eXpiring value — has identity but can be moved from
  - Understanding the value category taxonomy

#### § 5.3.2 — Move Constructor & Move Assignment
  - `MyClass(MyClass&& other) noexcept` — steal resources
  - `MyClass& operator=(MyClass&& other) noexcept` — steal + cleanup
  - Moved-from state: valid but unspecified
  - Why `noexcept` matters for move (vector reallocation!)

#### § 5.3.3 — `std::move` & `std::forward`
  - `std::move()` — unconditional cast to rvalue reference (it doesn't move anything!)
  - `std::forward<T>()` — conditional cast (perfect forwarding)
  - When to use `std::move`: transferring ownership, return optimization
  - Anti-pattern: `std::move` on `const` objects (does nothing!)

#### § 5.3.4 — Copy Elision & Return Value Optimization (RVO)
  - NRVO (Named Return Value Optimization)
  - Guaranteed copy elision (C++17): `return MyClass{};`
  - Don't `std::move` return values (prevents RVO!)

---

### 📦 Module 5.4: Resource Management Patterns

#### § 5.4.1 — RAII Wrappers
  - File handle wrapper: constructor opens, destructor closes
  - Lock guard: `std::lock_guard`, `std::unique_lock`
  - Scope guard: execute cleanup on scope exit

#### § 5.4.2 — Custom Allocators (Advanced)
  - `std::allocator<T>` — default allocator
  - Pool allocators, arena allocators
  - `std::pmr` (Polymorphic Memory Resources — C++17)
  - `std::pmr::monotonic_buffer_resource`, `std::pmr::unsynchronized_pool_resource`

> ### 🛠️ Phase 5 Project: **"SmartFS — A RAII File System Wrapper"**
> Build an RAII-based file system library:
> - `class File` — wraps `std::fstream` with RAII, moveable but not copyable
> - `class MappedFile` — wraps `mmap` (POSIX) with RAII, moveable, auto-unmaps
> - `class TempFile` — auto-deletes on destruction
> - `class DirectoryIterator` — iterates entries using `std::filesystem` internally
> - Use `std::unique_ptr` with custom deleters for C resources
> - Implement a `FilePool` using `std::shared_ptr` for shared access
> - Demonstrate **move semantics**: `File f2 = std::move(f1);` (f1 becomes empty)
> - Zero `new`/`delete` in the entire project
> - Valgrind / ASan verified

---

## ⚡ PHASE 6 — TEMPLATES & GENERIC PROGRAMMING
> *"Templates are C++'s superpower. They're also its most complex feature."*

---

### 📦 Module 6.1: Function Templates

#### § 6.1.1 — Basic Function Templates
  - `template <typename T>` syntax
  - Template argument deduction
  - Explicit template arguments: `func<int>(42)`
  - Multiple template parameters: `template <typename T, typename U>`

#### § 6.1.2 — Function Template Overloading & Specialization
  - Overloading templates with non-templates
  - Full (explicit) specialization: `template <> void func<int>(int x)`
  - Overload resolution with templates
  - Why partial specialization of function templates is NOT allowed

---

### 📦 Module 6.2: Class Templates

#### § 6.2.1 — Basic Class Templates
  - `template <typename T> class Container { ... };`
  - Member function definitions outside the class
  - Template classes in header files (why)

#### § 6.2.2 — Class Template Specialization
  - Full specialization: `template <> class Container<bool> { ... };`
  - **Partial specialization**: `template <typename T> class Container<T*> { ... };`
  - Use case: optimizing for specific types

#### § 6.2.3 — Non-Type Template Parameters
  - `template <typename T, size_t N> class Array { ... };`
  - `auto` non-type template parameters (C++17)
  - Non-type parameters: integers, pointers, references, enums
  - Use case: `std::array<int, 10>`

---

### 📦 Module 6.3: Advanced Template Techniques

#### § 6.3.1 — Variadic Templates
  - Parameter packs: `template <typename... Args>`
  - Pack expansion: `func(args...)`
  - Recursive unpacking pattern
  - Fold expressions (C++17): `(args + ...)`, `(args && ...)`
  - `sizeof...(Args)` — count parameters
  - `std::tuple` and `std::apply`

#### § 6.3.2 — SFINAE (Substitution Failure Is Not An Error)
  - `std::enable_if<condition, T>`
  - Using SFINAE to constrain templates
  - `std::is_integral`, `std::is_floating_point`, `std::is_same` (`<type_traits>`)
  - `decltype` + trailing return types for SFINAE
  - `std::void_t` (C++17 detection idiom)

#### § 6.3.3 — Concepts (C++20) — Replacing SFINAE
  - `template <typename T> concept Hashable = requires(T t) { std::hash<T>{}(t); };`
  - `requires` clause: `template <typename T> requires Integral<T>`
  - Abbreviated function templates: `void print(std::integral auto x)`
  - Standard concepts: `std::integral`, `std::floating_point`, `std::copyable`, `std::sortable`, `std::ranges::range`
  - Composing concepts: `&&`, `||`
  - Why concepts are superior to SFINAE (readability, error messages)

#### § 6.3.4 — `if constexpr` (C++17)
  - Compile-time branching in templates
  - Replacing tag dispatch and SFINAE for simple cases
  - Discarded statements — branches not taken are not compiled

#### § 6.3.5 — Template Metaprogramming (TMP)
  - Compile-time computation with templates
  - `constexpr` vs TMP (prefer `constexpr` in modern C++)
  - Type traits: `std::remove_reference`, `std::decay`, `std::conditional`
  - `std::integral_constant`, `std::true_type`, `std::false_type`
  - Building custom type traits

---

### 📦 Module 6.4: CRTP & Other Patterns

#### § 6.4.1 — Curiously Recurring Template Pattern (CRTP)
  - `class Derived : public Base<Derived>`
  - Static polymorphism (no vtable overhead)
  - Mixin pattern with CRTP

#### § 6.4.2 — Tag Dispatch
  - Using empty types as tags to select overloads
  - `std::true_type` / `std::false_type` dispatch

#### § 6.4.3 — Expression Templates (Overview)
  - Lazy evaluation of arithmetic expressions
  - Used in: Eigen, Blaze (linear algebra libraries)

> ### 🛠️ Phase 6 Project: **"TemplateDS — A Generic Data Structures Library"**
> Build a header-only, **fully generic** data structures library using templates:
> - `template <typename T> class LinkedList<T>` — with iterators (begin/end)
> - `template <typename K, typename V> class HashMap<K, V>` — with custom hash support via concepts
> - `template <typename T, typename Compare = std::less<T>> class BST<T, Compare>`
> - `template <typename T, size_t N> class StaticVector<T, N>` — stack-allocated, fixed capacity
> - Use **C++20 Concepts** to constrain:
>   - Keys must satisfy `Hashable` concept
>   - Elements must satisfy `std::equality_comparable`
> - Use **fold expressions** for a variadic `insert(T... items)`
> - Use **`if constexpr`** for type-specific optimizations
> - Comprehensive static_assert tests + runtime unit tests

---

## ⚡ PHASE 7 — ERROR HANDLING & ROBUSTNESS
> *"In C++ you can choose: exceptions, error codes, or monadic types. Know all three."*

---

### 📦 Module 7.1: Exception Handling

#### § 7.1.1 — `try`, `catch`, `throw` Basics
  - Throwing exceptions: `throw std::runtime_error("msg");`
  - Catching: by const reference (`catch (const std::exception& e)`)
  - Re-throwing: `throw;`
  - Catch-all: `catch (...)`

#### § 7.1.2 — Standard Exception Hierarchy
  - `std::exception` (base)
  - `std::runtime_error`, `std::logic_error`
  - `std::out_of_range`, `std::invalid_argument`, `std::overflow_error`
  - `std::bad_alloc`, `std::bad_cast`, `std::bad_typeid`
  - Creating custom exception classes (inherit from `std::exception`)

#### § 7.1.3 — Exception Safety Guarantees
  - **No-throw guarantee** — function never throws (`noexcept`)
  - **Strong guarantee** — operation succeeds or state is rolled back (transactional)
  - **Basic guarantee** — invariants preserved, no leaks, but state may change
  - **No guarantee** — avoid at all costs

#### § 7.1.4 — `noexcept` Specifier & Operator
  - `void func() noexcept;` — guarantees no exceptions (calls `std::terminate` if violated)
  - `noexcept(expression)` — conditional noexcept
  - `noexcept` operator: `noexcept(func())` — returns `true`/`false`
  - Why `noexcept` matters: move constructors, performance, `std::vector`

#### § 7.1.5 — Exception Pitfalls
  - Don't throw in destructors
  - Exception overhead: zero-cost when not thrown (table-based), costly when thrown
  - Exceptions vs. error codes: the debate
  - When NOT to use exceptions: embedded, real-time, game loops

---

### 📦 Module 7.2: Error Handling Without Exceptions

#### § 7.2.1 — `std::optional<T>` (C++17)
  - Represents "a value or nothing"
  - `std::nullopt`, `has_value()`, `value()`, `value_or(default)`
  - Monadic operations (C++23): `and_then()`, `transform()`, `or_else()`
  - Use case: functions that might not return a result

#### § 7.2.2 — `std::variant<T...>` (C++17)
  - Type-safe union — holds one of several types
  - `std::get<T>()`, `std::get_if<T>()`
  - `std::visit()` — visitor pattern with overloaded lambdas
  - Use case: result-or-error type, parsers, state machines

#### § 7.2.3 — `std::expected<T, E>` (C++23)
  - Value OR error (like Rust's `Result<T, E>`)
  - `has_value()`, `value()`, `error()`
  - Monadic: `and_then()`, `transform()`, `or_else()`
  - The modern C++ way to handle errors without exceptions

#### § 7.2.4 — Error Codes & `std::error_code` / `std::error_category`
  - `<system_error>` — system-level error handling
  - Custom error categories
  - `std::errc` enumeration

---

### 📦 Module 7.3: Assertions & Contracts

#### § 7.3.1 — Runtime Assertions
  - `assert()` (`<cassert>`) — debug-only checks
  - `NDEBUG` — disabling assertions in release

#### § 7.3.2 — Static Assertions
  - `static_assert(condition, "message")` — compile-time checks
  - Use with type traits: `static_assert(std::is_integral_v<T>, "T must be integral");`

#### § 7.3.3 — Contracts (C++26 — Upcoming)
  - `pre(condition)`, `post(condition)`, `assert(condition)`
  - Preconditions, postconditions, invariants

> ### 🛠️ Phase 7 Project: **"SafeJSON — A Robust JSON Parser"**
> Build a JSON parser from scratch that uses all three error-handling strategies:
> - Parse JSON strings into a `JsonValue` type using `std::variant<null_t, bool, double, std::string, JsonArray, JsonObject>`
> - **Version A:** Uses exceptions for parse errors (`JsonParseError : std::runtime_error`)
> - **Version B:** Uses `std::expected<JsonValue, ParseError>` (C++23) or a custom `Result<T, E>` type
> - **Version C:** Uses `std::optional<JsonValue>` for simple cases
> - Support: objects, arrays, strings, numbers, booleans, null
> - Comprehensive test suite with valid AND malformed JSON inputs
> - Benchmark exception vs. error-code performance on 10,000 malformed inputs

---

## ⚡ PHASE 8 — CONCURRENCY & MULTITHREADING
> *"Modern C++ has first-class concurrency primitives. No more platform-specific threading."*

---

### 📦 Module 8.1: Thread Fundamentals (`<thread>`)

#### § 8.1.1 — Creating & Managing Threads
  - `std::thread t(func, args...);`
  - `t.join()` — wait for completion
  - `t.detach()` — let it run independently
  - `t.joinable()` — check before join/detach
  - `std::jthread` (C++20) — auto-joining thread with stop token
  - `std::this_thread::get_id()`, `std::this_thread::sleep_for()`
  - Hardware concurrency: `std::thread::hardware_concurrency()`

#### § 8.1.2 — Passing Data to Threads
  - By value, by reference (`std::ref`), by move
  - Lambdas as thread functions
  - Returning results from threads (via shared data or `std::future`)

---

### 📦 Module 8.2: Synchronization Primitives

#### § 8.2.1 — Mutexes (`<mutex>`)
  - `std::mutex` — basic mutual exclusion
  - `std::recursive_mutex` — same thread can lock multiple times
  - `std::timed_mutex` — `try_lock_for()`, `try_lock_until()`
  - `std::shared_mutex` (C++17) — multiple readers, single writer

#### § 8.2.2 — Lock Guards (RAII Locks)
  - `std::lock_guard<std::mutex>` — simple scoped lock
  - `std::unique_lock<std::mutex>` — flexible (defer, try, timed)
  - `std::shared_lock<std::shared_mutex>` (C++17) — reader lock
  - `std::scoped_lock` (C++17) — locks multiple mutexes deadlock-free

#### § 8.2.3 — Condition Variables
  - `std::condition_variable` — wait/notify mechanism
  - `wait()`, `wait_for()`, `wait_until()`
  - `notify_one()`, `notify_all()`
  - Producer-consumer pattern implementation
  - Spurious wakeups & predicate-based wait

#### § 8.2.4 — Atomics (`<atomic>`)
  - `std::atomic<T>` — lock-free thread-safe operations
  - `load()`, `store()`, `exchange()`, `compare_exchange_weak/strong()`
  - `fetch_add()`, `fetch_sub()` — atomic arithmetic
  - `std::atomic_flag` — simplest atomic (spinlock)
  - Memory orderings: `memory_order_relaxed`, `acquire`, `release`, `seq_cst`
  - Lock-free vs. wait-free data structures (overview)

---

### 📦 Module 8.3: Asynchronous Programming

#### § 8.3.1 — Futures & Promises
  - `std::future<T>` — receive a result
  - `std::promise<T>` — produce a result
  - `std::async()` — launch async tasks (with `std::launch::async` / `deferred`)
  - `future.get()` — blocks until result is ready
  - `std::shared_future<T>` — multiple consumers

#### § 8.3.2 — `std::packaged_task<T>`
  - Wraps a callable for async execution
  - Getting the future from a packaged task
  - Use case: thread pools

---

### 📦 Module 8.4: Advanced Concurrency

#### § 8.4.1 — Thread Pool Implementation
  - Fixed-size thread pool
  - Task queue with `std::queue` + `std::mutex` + `std::condition_variable`
  - Submitting tasks, retrieving results via `std::future`

#### § 8.4.2 — Coroutines (C++20) — Introduction
  - `co_await` — suspend and resume
  - `co_yield` — produce a value and suspend
  - `co_return` — final return
  - Generator pattern: lazy sequence generation
  - Promise type, coroutine handle
  - Use case: async I/O, lazy iteration, state machines

#### § 8.4.3 — Parallel Algorithms (C++17)
  - Execution policies: `std::execution::seq`, `par`, `par_unseq`
  - `std::sort(std::execution::par, vec.begin(), vec.end())`
  - `std::reduce(std::execution::par, ...)`
  - `std::for_each(std::execution::par, ...)`
  - When parallelism helps vs. hurts (overhead)

#### § 8.4.4 — Common Concurrency Bugs
  - Data races
  - Deadlocks (lock ordering, `std::scoped_lock`)
  - Race conditions
  - Starvation, livelock
  - Using ThreadSanitizer: `g++ -fsanitize=thread`

> ### 🛠️ Phase 8 Project: **"TaskForge — A Thread Pool & Task Scheduler"**
> Build a production-quality **thread pool** library:
> - `class ThreadPool` — configurable worker count
> - `auto future = pool.submit(callable, args...)` — returns `std::future<ReturnType>`
> - `pool.shutdown()` — graceful shutdown (finish pending, reject new)
> - **Priority queue** variant: tasks with priorities
> - **Coroutine generator**: `Generator<int> fibonacci()` using C++20 coroutines
> - **Demo application:**
>   - Parallel merge sort using the thread pool
>   - Async HTTP-like request simulator (10,000 tasks)
>   - Performance benchmark: 1 thread vs. N threads vs. `std::execution::par`
> - Thread-safe with `std::scoped_lock`, verified with ThreadSanitizer

---

## ⚡ PHASE 9 — FILE I/O, SERIALIZATION & THE FILESYSTEM
> *"Modern C++ finally has a proper filesystem library."*

---

### 📦 Module 9.1: Stream-Based I/O (`<iostream>`, `<fstream>`, `<sstream>`)

#### § 9.1.1 — Stream Hierarchy
  - `std::istream`, `std::ostream`, `std::iostream`
  - `std::ifstream`, `std::ofstream`, `std::fstream`
  - `std::istringstream`, `std::ostringstream`, `std::stringstream`
  - Stream states: `good()`, `fail()`, `bad()`, `eof()`, `clear()`

#### § 9.1.2 — Text File I/O
  - Opening files: constructor or `.open()`
  - Reading line by line: `std::getline()`
  - Formatted reading: `stream >> var`
  - Writing: `stream << data`
  - RAII: streams auto-close on destruction

#### § 9.1.3 — Binary File I/O
  - `std::ios::binary` flag
  - `write(reinterpret_cast<const char*>(&data), sizeof(data))`
  - `read(reinterpret_cast<char*>(&data), sizeof(data))`
  - `seekg()`, `seekp()`, `tellg()`, `tellp()`

#### § 9.1.4 — String Streams
  - Parsing strings: `std::istringstream`
  - Building strings: `std::ostringstream`
  - Type conversion via string streams

#### § 9.1.5 — Formatting Output
  - `<iomanip>`: `std::setw`, `std::setprecision`, `std::setfill`, `std::fixed`, `std::hex`
  - `std::format` (C++20): `std::format("Hello, {}! Pi is {:.2f}", name, 3.14159)`
  - `std::print` (C++23): `std::print("x = {}\n", x);`

---

### 📦 Module 9.2: Filesystem Library (`<filesystem>` — C++17)

#### § 9.2.1 — Paths
  - `std::filesystem::path` — platform-independent paths
  - `path.extension()`, `path.stem()`, `path.parent_path()`
  - `path / "subdir" / "file.txt"` — path concatenation with `/`

#### § 9.2.2 — Directory Operations
  - `exists()`, `is_regular_file()`, `is_directory()`
  - `create_directory()`, `create_directories()`
  - `remove()`, `remove_all()`
  - `rename()`, `copy()`, `copy_file()`

#### § 9.2.3 — Directory Iteration
  - `std::filesystem::directory_iterator` — non-recursive
  - `std::filesystem::recursive_directory_iterator` — recursive
  - Filtering by extension, size, modification time

#### § 9.2.4 — File Information
  - `file_size()`, `last_write_time()`
  - `permissions()`, `status()`
  - `space()` — disk space info

---

### 📦 Module 9.3: Serialization Strategies

#### § 9.3.1 — Manual Binary Serialization
  - Writing struct fields individually (portable)
  - Endianness handling: `std::endian` (C++20), manual byte-swapping
  - Schema versioning

#### § 9.3.2 — Text-Based Serialization
  - JSON: using `nlohmann/json` library
  - TOML / YAML parsing libraries
  - Custom text formats

#### § 9.3.3 — Third-Party Serialization Libraries
  - Protocol Buffers (protobuf)
  - FlatBuffers — zero-copy deserialization
  - cereal — header-only C++ serialization
  - Boost.Serialization

> ### 🛠️ Phase 9 Project: **"SyncDir — A File Synchronization Tool"**
> Build a command-line file sync tool (like a mini `rsync`):
> - **Scan** source and destination directories recursively using `std::filesystem`
> - **Compare** files by size, modification time, and optionally hash (MD5/SHA-256)
> - **Sync modes**: mirror, update-only, bidirectional
> - **Logging**: all operations logged to a file with timestamps using `std::format`
> - **Config file**: read sync settings from a JSON config using `nlohmann/json`
> - **Progress reporting**: show files processed, bytes transferred
> - **Dry-run mode**: `--dry-run` shows what would happen without doing it
> - Build with CMake + `FetchContent` for nlohmann/json dependency

---

## ⚡ PHASE 10 — DESIGN PATTERNS & SOFTWARE ARCHITECTURE
> *"Knowing the language is not enough. Knowing how to design with it is everything."*

---

### 📦 Module 10.1: SOLID Principles in C++

#### § 10.1.1 — Single Responsibility Principle
  - One class = one reason to change
  - Separating concerns in C++

#### § 10.1.2 — Open/Closed Principle
  - Open for extension, closed for modification
  - Achieving it with inheritance, templates, and policy classes

#### § 10.1.3 — Liskov Substitution Principle
  - Derived classes must be substitutable for base classes
  - Correct use of `virtual` and `override`

#### § 10.1.4 — Interface Segregation Principle
  - Small, focused interfaces (abstract classes)
  - No client should depend on methods it doesn't use

#### § 10.1.5 — Dependency Inversion Principle
  - Depend on abstractions, not concretions
  - Dependency injection in C++ (constructor injection, template-based)

---

### 📦 Module 10.2: Creational Patterns

#### § 10.2.1 — Factory Method & Abstract Factory
  - `std::unique_ptr<Base> create(Type t)`
  - Factory with `std::unordered_map<string, std::function<unique_ptr<Base>()>>`
  - Self-registering factories

#### § 10.2.2 — Builder Pattern
  - Fluent interface with method chaining (`return *this;`)
  - Use case: constructing complex objects (config, queries)

#### § 10.2.3 — Singleton Pattern
  - Meyers' Singleton: `static T& instance() { static T inst; return inst; }`
  - Thread safety (guaranteed since C++11)
  - Why singletons are often an anti-pattern
  - Alternatives: dependency injection

#### § 10.2.4 — Prototype Pattern
  - `virtual std::unique_ptr<Base> clone() const = 0;`
  - Deep copy via polymorphism

---

### 📦 Module 10.3: Structural Patterns

#### § 10.3.1 — Adapter Pattern
  - Class adapter (inheritance) vs. object adapter (composition)
  - Wrapping C APIs in C++ RAII classes

#### § 10.3.2 — Decorator Pattern
  - Wrapping objects to add behavior dynamically
  - Implementation with inheritance and composition

#### § 10.3.3 — Composite Pattern
  - Tree structures: `Component` → `Leaf`, `Composite`
  - Use case: UI hierarchies, file systems

#### § 10.3.4 — Facade Pattern
  - Simplified interface to a complex subsystem

#### § 10.3.5 — PIMPL (Pointer to Implementation)
  - Compiler firewall pattern
  - `class Foo { struct Impl; std::unique_ptr<Impl> pImpl; };`
  - Reduces compile times, hides implementation details
  - ABI stability

---

### 📦 Module 10.4: Behavioral Patterns

#### § 10.4.1 — Observer Pattern
  - Subject + Observer interface
  - Modern C++: `std::function`-based callbacks, signals/slots

#### § 10.4.2 — Strategy Pattern
  - Runtime: virtual functions / `std::function`
  - Compile-time: template policy classes (e.g., `template <typename SortPolicy>`)

#### § 10.4.3 — Command Pattern
  - Encapsulating actions as objects
  - Undo/Redo system

#### § 10.4.4 — State Machine Pattern
  - `std::variant` + `std::visit` — type-safe state machine
  - Enum-based state machines
  - Table-driven state machines

#### § 10.4.5 — Visitor Pattern
  - Double dispatch
  - `std::variant` + `std::visit` as modern visitor
  - Overloaded lambda trick: `overloaded{[](int i){...}, [](string s){...}}`

#### § 10.4.6 — Iterator Pattern
  - Already built into STL
  - Writing custom iterators: `begin()`, `end()`, `operator++`, `operator*`, `operator!=`
  - Range-based for loop support

---

### 📦 Module 10.5: C++-Specific Patterns

#### § 10.5.1 — Policy-Based Design
  - `template <typename LogPolicy, typename ThreadPolicy> class Server;`
  - Compile-time strategy selection (zero overhead)
  - Alexandrescu's "Modern C++ Design"

#### § 10.5.2 — Type Erasure
  - `std::function`, `std::any`, `std::variant`
  - Custom type erasure: virtual function + templated constructor
  - `std::any` — holds any type (with overhead)

#### § 10.5.3 — Mixin Classes
  - Adding behavior via inheritance without hierarchy
  - CRTP mixins

> ### 🛠️ Phase 10 Project: **"GameEngine2D — A 2D Game Engine Framework"**
> Build a **modular 2D game engine** demonstrating design patterns:
> - **Entity-Component-System (ECS):**
>   - `Entity` = ID, `Component` = data (Position, Velocity, Sprite), `System` = logic (MovementSystem, RenderSystem)
>   - Components stored in `std::unordered_map<EntityID, Component>`
> - **Patterns used:**
>   - **Factory**: `EntityFactory::create("player")` returns configured entity
>   - **Observer**: Event system — `eventBus.subscribe<CollisionEvent>(handler)`
>   - **Command**: Input system — keybindings mapped to command objects (undo support)
>   - **State Machine**: Game states (Menu, Playing, Paused) via `std::variant`
>   - **Strategy**: Rendering backend swappable (console ASCII vs. SDL2)
>   - **PIMPL**: Hide SDL2 dependency behind a clean C++ interface
> - **Game**: Implement a simple Asteroids or Snake using the engine
> - Build with CMake, use `FetchContent` for SDL2

---

## ⚡ PHASE 11 — ADVANCED MODERN C++ & PERFORMANCE
> *"This is where you become dangerous."*

---

### 📦 Module 11.1: Advanced Type System

#### § 11.1.1 — `std::tuple` & Structured Bindings
  - `std::tuple<int, string, double>`
  - `std::get<0>(tup)`, `std::get<int>(tup)`
  - Structured bindings (C++17): `auto [x, y, z] = tup;`
  - Structured bindings with maps: `for (auto& [key, val] : map)`
  - `std::tie` for comparison operators

#### § 11.1.2 — `std::any`, `std::variant`, `std::optional` — Mastery
  - When to use each one
  - `std::visit` with overloaded lambdas pattern
  - Monadic operations (C++23)

#### § 11.1.3 — `std::string_view` — Mastery
  - Non-owning string reference
  - Avoiding unnecessary allocations
  - Pitfalls: dangling views, null termination not guaranteed
  - `std::span<T>` (C++20) — non-owning view of contiguous data

---

### 📦 Module 11.2: Compile-Time Programming

#### § 11.2.1 — `constexpr` Everything
  - `constexpr` functions, variables, `if constexpr`
  - `constexpr std::vector` and `std::string` (C++20)
  - `consteval` — immediate functions
  - `constinit` — constant initialization

#### § 11.2.2 — Template Metaprogramming (TMP) — Deep Dive
  - Recursive template computations
  - Type lists
  - `std::index_sequence` and parameter pack indexing
  - Compile-time string processing

#### § 11.2.3 — Reflection (C++26 — Future)
  - Static reflection proposals
  - `std::meta::info`
  - Automatic serialization, ORM

---

### 📦 Module 11.3: Performance Optimization

#### § 11.3.1 — Profiling & Benchmarking
  - **Google Benchmark** library
  - `perf` (Linux), `Instruments` (macOS), `VTune` (Intel)
  - Microbenchmarking pitfalls: optimizer elimination, cache effects
  - Avoiding premature optimization

#### § 11.3.2 — Cache-Friendly Programming
  - Data-oriented design vs. object-oriented design
  - Array of Structs (AoS) vs. Struct of Arrays (SoA)
  - Cache line size (64 bytes typically)
  - False sharing in multithreaded code: `alignas(64)`
  - Prefetching: `__builtin_prefetch`

#### § 11.3.3 — Move Semantics — Performance Impact
  - Eliminating unnecessary copies
  - `std::move` in containers, return values, argument passing
  - Move-only types: `std::unique_ptr`, `std::thread`

#### § 11.3.4 — Small Object Optimization
  - SSO (Small String Optimization) in `std::string`
  - SBO (Small Buffer Optimization) in `std::function`
  - Designing your own SBO-enabled types

#### § 11.3.5 — Compiler Optimizations & Intrinsics
  - Understanding compiler output (Godbolt)
  - Link-Time Optimization (LTO): `-flto`
  - Profile-Guided Optimization (PGO): `-fprofile-generate` / `-fprofile-use`
  - `[[likely]]`, `[[unlikely]]` (C++20)
  - SIMD intrinsics: SSE, AVX, NEON (overview)

---

### 📦 Module 11.4: Testing & Quality at Scale

#### § 11.4.1 — Testing Frameworks
  - **Google Test (gtest)**: `TEST()`, `EXPECT_EQ`, `ASSERT_TRUE`, fixtures
  - **Catch2**: `TEST_CASE`, `SECTION`, BDD-style
  - **doctest**: lightweight, header-only
  - Mocking: **Google Mock** — `MOCK_METHOD`, `EXPECT_CALL`

#### § 11.4.2 — Continuous Integration
  - CMake + CTest integration
  - GitHub Actions / GitLab CI for C++ projects
  - Code coverage: `gcov` + `lcov` + `codecov`

#### § 11.4.3 — Static Analysis & Linting
  - `clang-tidy` — modernization, bug detection
  - `cppcheck` — static analysis
  - `clang-format` — code formatting
  - `-Wall -Wextra -Wpedantic -Werror` — compiler warnings as errors

#### § 11.4.4 — Fuzzing
  - **libFuzzer**: `LLVMFuzzerTestOneInput`
  - **AFL++** for C++ targets
  - Sanitizer integration (ASan + UBSan + fuzzing)

> ### 🛠️ Phase 11 Project: **"HyperLog — A High-Performance Logging Library"**
> Build a **production-grade, high-performance logging library**:
> - **API**: `LOG_INFO("User {} logged in at {}", name, time);` using `std::format`
> - **Performance:**
>   - Lock-free ring buffer (using `std::atomic`)
>   - Background writer thread (consumer)
>   - Async logging: caller never blocks on I/O
>   - Benchmark: >1M log lines/second
> - **Features:**
>   - Log levels: TRACE, DEBUG, INFO, WARN, ERROR, FATAL
>   - Multiple sinks: console, file, rotating file, custom
>   - `std::source_location` (C++20) for automatic file/line/function
>   - Compile-time log level filtering with `if constexpr`
>   - Thread-safe without global locks
> - **Quality:**
>   - Google Test + Google Benchmark
>   - ASan + TSan verified
>   - clang-tidy clean
>   - CMake with `FetchContent` for dependencies
>   - CI pipeline (GitHub Actions)

---

## ⚡ PHASE 12 — SYSTEMS & REAL-WORLD C++
> *"This is where you build things that matter."*

---

### 📦 Module 12.1: Network Programming in C++

#### § 12.1.1 — POSIX Sockets in C++ (RAII Wrapped)
  - TCP/UDP client & server with C++ RAII wrappers
  - `Socket` class, `TcpListener` class, `TcpStream` class
  - Non-blocking I/O with `epoll` / `kqueue`

#### § 12.1.2 — Asio / Boost.Asio
  - Asynchronous I/O library (foundation of C++ networking)
  - `io_context`, `tcp::socket`, `tcp::acceptor`
  - Async operations: `async_read`, `async_write`, completion handlers
  - Coroutine-based Asio (C++20): `co_await async_read(...)`

#### § 12.1.3 — HTTP in C++
  - Building a simple HTTP server (raw sockets or Asio)
  - Libraries: **cpp-httplib**, **Crow**, **Drogon**
  - REST API development in C++

---

### 📦 Module 12.2: Interoperability

#### § 12.2.1 — C++ & C Interop
  - `extern "C"` — disabling name mangling
  - Calling C libraries from C++
  - Exposing C++ code to C (wrapper functions)

#### § 12.2.2 — C++ & Python Interop
  - **pybind11** — seamless C++ ↔ Python bindings
  - Exposing C++ classes to Python
  - Performance-critical Python extensions in C++

#### § 12.2.3 — C++ & Other Languages
  - Foreign Function Interface (FFI) concepts
  - WebAssembly: Compiling C++ to WASM (Emscripten)

---

### 📦 Module 12.3: Package Management & Ecosystem

#### § 12.3.1 — Package Managers
  - **vcpkg** (Microsoft) — `vcpkg install fmt`
  - **Conan** — `conanfile.txt` / `conanfile.py`
  - **CMake FetchContent** — download dependencies at configure time
  - **CPM.cmake** — lightweight wrapper over FetchContent

#### § 12.3.2 — Popular Libraries to Know
  - **fmt** — formatting (backport of `std::format`)
  - **spdlog** — fast logging
  - **nlohmann/json** — JSON
  - **Boost** — the everything library (Asio, Beast, Spirit, Multiprecision)
  - **Eigen** — linear algebra
  - **SFML / SDL2** — multimedia / games
  - **Dear ImGui** — immediate-mode GUI
  - **GoogleTest + GoogleBenchmark** — testing

---

### 📦 Module 12.4: Domain-Specific Applications

#### § 12.4.1 — Embedded C++
  - C++ on microcontrollers (ARM Cortex-M)
  - `-fno-exceptions`, `-fno-rtti` — constraints
  - `constexpr` for zero-cost abstractions on embedded
  - MISRA C++ guidelines

#### § 12.4.2 — Game Development with C++
  - Game loop architecture
  - ECS (Entity-Component-System)
  - Unreal Engine C++ API overview
  - Custom engine development

#### § 12.4.3 — High-Frequency Trading (HFT)
  - Low-latency patterns: lock-free queues, memory pools
  - Cache optimization, branch prediction
  - Kernel bypass networking (DPDK)
  - Why C++ dominates HFT

#### § 12.4.4 — Compiler & Language Tooling
  - Writing a lexer & parser in C++
  - AST representation with `std::variant`
  - Building a simple interpreter

> ### 🛠️ Phase 12 Capstone Project: **"Orca — A Redis-Like In-Memory Key-Value Store"**
> Build a fully functional **in-memory key-value database** from scratch:
> - **Networking:** Async TCP server using **Asio** (or raw `epoll`)
> - **Protocol:** Implement a subset of RESP (Redis Serialization Protocol)
> - **Commands:** `SET`, `GET`, `DEL`, `EXISTS`, `EXPIRE`, `TTL`, `KEYS`, `INCR`, `LPUSH`, `LPOP`, `LRANGE`, `HSET`, `HGET`
> - **Data Structures:**
>   - Strings: `std::string`
>   - Lists: `std::deque`
>   - Hashes: `std::unordered_map`
>   - Sets: `std::unordered_set`
>   - Sorted Sets: `std::map` or skip list
>   - Value type: `std::variant<String, List, Hash, Set, SortedSet>`
> - **Features:**
>   - Key expiration (TTL) — background cleanup thread
>   - Persistence: RDB-style snapshotting (serialize to binary file)
>   - LRU eviction when memory limit is reached
>   - Pipelining support
>   - Thread-safe with fine-grained locking or lock-free structures
> - **Quality:**
>   - Google Test + Google Benchmark
>   - Valgrind + ASan + TSan clean
>   - CMake build + vcpkg for dependencies
>   - Compatible with `redis-cli` for basic commands
>   - Benchmark: `redis-benchmark` comparison
> - **Documentation:** Full README with architecture diagram, API docs, and build instructions

---

## 📊 PHASE MAP (Visual Summary)

```
Phase 0   ██░░░░░░░░░░░░░░  Environment & Orientation
Phase 1   ███░░░░░░░░░░░░░  Language Fundamentals
Phase 2   ████░░░░░░░░░░░░  Functions, References & Lambdas
Phase 3   ██████░░░░░░░░░░  Object-Oriented Programming
Phase 4   ████████░░░░░░░░  Standard Template Library (STL)
Phase 5   █████████░░░░░░░  Memory Management & Move Semantics
Phase 6   ██████████░░░░░░  Templates & Generic Programming
Phase 7   ███████████░░░░░  Error Handling & Robustness
Phase 8   ████████████░░░░  Concurrency & Multithreading
Phase 9   █████████████░░░  File I/O, Filesystem & Serialization
Phase 10  ██████████████░░  Design Patterns & Architecture
Phase 11  ███████████████░  Advanced Modern C++ & Performance
Phase 12  ████████████████  Systems Programming & Real-World C++
```

---

## 🎯 DIFFICULTY & SKILL PROGRESSION

```
       BEGINNER              INTERMEDIATE              ADVANCED                 EXPERT
    ┌────────────┐        ┌────────────────┐       ┌──────────────┐       ┌──────────────┐
    │  Phase 0   │───────▶│    Phase 3     │──────▶│   Phase 6    │──────▶│   Phase 10   │
    │  Phase 1   │        │    Phase 4     │       │   Phase 7    │       │   Phase 11   │
    │  Phase 2   │        │    Phase 5     │       │   Phase 8    │       │   Phase 12   │
    │            │        │               │       │   Phase 9    │       │              │
    └────────────┘        └────────────────┘       └──────────────┘       └──────────────┘
    "I can write           "I use STL,             "I write              "I build
     C++ programs"          RAII, move"             templates &           production
                                                    concurrent code"      systems"
```

---

## 🎯 CERTIFICATION & CREDIBILITY ALIGNMENT

| Phase | Certification / Credibility |
|-------|----------------------------|
| 0 – 4 | **C++ Institute CPA** (C++ Certified Associate) |
| 3 – 7 | **C++ Institute CPP** (C++ Certified Professional) |
| 6 – 9 | **Bloomberg / Jane Street / Google** interview readiness |
| 8 – 12 | **Senior C++ Engineer** portfolio |
| ALL | **Open-source contributions** (LLVM, Firefox, Godot, etc.) |

---

## 📚 RECOMMENDED RESOURCES

| Resource | Type | Phase |
|----------|------|-------|
| *A Tour of C++* — Bjarne Stroustrup (3rd Ed.) | 📖 Book (Overview) | 0–4 |
| *Programming: Principles and Practice Using C++* — Stroustrup | 📖 Book (Beginner) | 0–5 |
| *C++ Primer* — Lippman, Lajoie, Moo (5th Ed.) | 📖 Book (Comprehensive) | 1–7 |
| *Effective Modern C++* — Scott Meyers | 📖 Book (Must-read) | 4–8 |
| *The C++ Programming Language* — Stroustrup (4th Ed.) | 📖 Book (Reference) | ALL |
| *C++ Templates: The Complete Guide* — Vandevoorde, Josuttis | 📖 Book | 6 |
| *C++ Concurrency in Action* — Anthony Williams (2nd Ed.) | 📖 Book | 8 |
| *Design Patterns in Modern C++* — Dmitri Nesteruk | 📖 Book | 10 |
| *Data-Oriented Design* — Richard Fabian | 📖 Book | 11 |
| **cppreference.com** | 🌐 Reference | ALL |
| **C++ Core Guidelines** (isocpp.github.io) | 🌐 Guidelines | ALL |
| **learncpp.com** | 🌐 Free Course | 0–7 |
| **The Cherno** (YouTube) | 🎥 Video | 0–6 |
| **Jason Turner — C++ Weekly** (YouTube) | 🎥 Video | 4–12 |
| **CppCon** (YouTube) | 🎥 Conference Talks | 6–12 |
| **Back to Basics** (CppCon track) | 🎥 Video | 1–8 |
| **Compiler Explorer** (godbolt.org) | 🧪 Tool | 2–12 |
| **Exercism — C++ Track** | 🧪 Practice | 1–6 |
| **Google Benchmark** | 🧪 Tool | 11 |
| **Catch2 / GoogleTest** | 🧪 Testing | 7–12 |

---

## 🗺️ WHERE C++ TAKES YOU (Career Paths)

```
                                  ┌───────────────────────────┐
                                  │   Game Development        │
                           ┌─────▶│   (Unreal, Custom Engines)│
                           │      └───────────────────────────┘
                           │      ┌───────────────────────────┐
                           │      │   Systems Programming     │
                   ┌───────┤─────▶│   (OS, Drivers, VMs)      │
                   │       │      └───────────────────────────┘
                   │       │      ┌───────────────────────────┐
   ┌────────────┐  │       │      │   High-Frequency Trading  │
   │            │  │       ├─────▶│   (Low-Latency Systems)   │
   │  Master    ├──┤       │      └───────────────────────────┘
   │  C++       │  │       │      ┌───────────────────────────┐
   │            │  │       │      │   Embedded / Robotics /   │
   └────────────┘  │       ├─────▶│   Autonomous Vehicles     │
                   │       │      └───────────────────────────┘
                   │       │      ┌───────────────────────────┐
                   │       │      │   Compilers & Languages   │
                   │       ├─────▶│   (LLVM, GCC, V8)         │
                   │       │      └───────────────────────────┘
                   │       │      ┌───────────────────────────┐
                   │       │      │   Databases & Infra       │
                   └───────┴─────▶│   (MySQL, MongoDB,        │
                                  │    ClickHouse, gRPC)       │
                                  └───────────────────────────┘
```

---

> ### 💡 Final Advice
> **"C++ is not a language you learn once. It's a language you keep learning. The standard evolves every 3 years, and the depth is bottomless."**
>
> Four non-negotiable rules for your C++ journey:
>
> 1. **Always compile with warnings:** `g++ -std=c++20 -Wall -Wextra -Wpedantic -Werror -g`
> 2. **Never use raw `new`/`delete`** — use `std::make_unique`, `std::make_shared`, containers
> 3. **Watch one CppCon talk per week** — this alone will level you up continuously
> 4. **Read other people's C++ code** — study LLVM, Folly (Facebook), Abseil (Google), STL implementations
>
> The difference between a *C++ programmer* and a *C++ engineer* is:
> - **Const correctness**, **move semantics**, **RAII**, **knowing what the compiler generates**
>
> C++ gives you unlimited power. The roadmap above gives you the **discipline to wield it**.

---

*This roadmap takes you from "What's `std::cout`?" to "I can build a database, a game engine, a trading system, or a compiler — all in modern, safe, high-performance C++."* 🚀