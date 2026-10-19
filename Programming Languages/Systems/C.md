# 🔧 THE ULTIMATE C LANGUAGE ROADMAP
### From Zero to Systems Programming Mastery

> **Structure:** Phase → Modules → Sections
> **Estimated Duration:** ~6-9 Months (Dedicated Study)

---

## ⚡ PHASE 0 — FOUNDATIONS & ENVIRONMENT SETUP
> *"Before you write code, understand where your code lives."*

### Module 0.1: How Computers Work (For C Programmers)
  - Von Neumann Architecture (CPU, ALU, Registers, Memory, Bus)
  - How RAM works: Stack vs. Heap (high-level overview)
  - Binary, Hexadecimal & Data Representation
  - Bits, Bytes, Words — Why sizes matter in C
  - What is a compiler? Source Code → Preprocessor → Compiler → Assembler → Linker → Executable

### Module 0.2: Setting Up the C Development Environment
  - Installing GCC / Clang (Linux, macOS)
  - Installing MinGW / MSYS2 (Windows)
  - IDEs & Editors: VS Code + C/C++ extension, CLion, Vim, Neovim
  - Terminal basics: navigating, compiling, running
  - Writing your first `hello.c` & compiling manually:
    ```
    gcc hello.c -o hello && ./hello
    ```

### Module 0.3: The Compilation Pipeline (Deep Understanding)
  - **Preprocessing:** `#include`, `#define`, `#ifdef` → `.i` file
  - **Compilation:** C → Assembly (`.s` file)
  - **Assembly:** Assembly → Object code (`.o` file)
  - **Linking:** Object files + Libraries → Executable
  - Exploring each stage: `gcc -E`, `gcc -S`, `gcc -c`
  - Static vs. Dynamic Linking (intro)

### Module 0.4: Essential Tooling
  - `gcc` / `clang` flags: `-Wall`, `-Wextra`, `-Werror`, `-std=c11`, `-g`, `-O2`
  - `make` and basic `Makefile` structure
  - Using `man` pages (your best friend in C)
  - Version control with Git (basics)

> ### 🛠️ Phase 0 Project: **"Build Pipeline Explorer"**
> Write a simple C program and manually run each stage of compilation (`-E`, `-S`, `-c`, linking). Save each intermediate output, annotate it, and create a visual diagram showing how your `hello.c` becomes an executable binary. Inspect the binary with `objdump` and `hexdump`.

---

## ⚡ PHASE 1 — C LANGUAGE FUNDAMENTALS
> *"Master the grammar before you write poetry."*

### Module 1.1: Basic Syntax & Structure
  - Anatomy of a C program: `#include`, `main()`, return values
  - Comments: `//` and `/* */`
  - Statements, Expressions, Blocks `{}`
  - Semicolons, Whitespace rules
  - The `return 0;` convention and exit codes

### Module 1.2: Data Types & Variables
  - Primitive types: `char`, `int`, `float`, `double`
  - Size modifiers: `short`, `long`, `long long`
  - Sign modifiers: `signed`, `unsigned`
  - `sizeof()` operator — platform-dependent sizes
  - Type ranges and limits (`<limits.h>`, `<float.h>`)
  - Fixed-width integers: `int8_t`, `uint32_t`, `int64_t` (`<stdint.h>`)
  - Constants: `const`, `#define`, `enum`
  - Type qualifiers: `const`, `volatile`, `restrict`

### Module 1.3: Operators (Complete)
  - Arithmetic: `+`, `-`, `*`, `/`, `%`
  - Relational: `==`, `!=`, `<`, `>`, `<=`, `>=`
  - Logical: `&&`, `||`, `!`
  - Bitwise: `&`, `|`, `^`, `~`, `<<`, `>>`
  - Assignment: `=`, `+=`, `-=`, `*=`, `<<=`, `&=`, etc.
  - Ternary: `condition ? a : b`
  - Comma operator, `sizeof`, Casting `(type)`
  - **Operator precedence table** (memorize it)

### Module 1.4: Input / Output
  - `printf()` — format specifiers: `%d`, `%u`, `%f`, `%lf`, `%c`, `%s`, `%x`, `%p`, `%zu`
  - Field width, precision, padding, flags (`%-10.2f`)
  - `scanf()` — how it works, common pitfalls, buffer issues
  - `getchar()`, `putchar()`, `gets()` (dangerous!), `fgets()`
  - Return values of `printf` and `scanf`

### Module 1.5: Control Flow
  - **Conditionals:** `if`, `else if`, `else`
  - **Switch-Case:** `switch`, `case`, `default`, fall-through behavior
  - **Loops:** `for`, `while`, `do-while`
  - **Jump statements:** `break`, `continue`, `goto` (and why to avoid it)
  - Nested loops & loop optimization
  - Dangling else problem

> ### 🛠️ Phase 1 Project: **"Mini Calculator & Unit Converter"**
> Build a CLI program that:
> 1. Takes two numbers and an operator (`+`, `-`, `*`, `/`, `%`, `**`) and prints the result
> 2. Handles division by zero, integer overflow detection
> 3. Has a unit converter mode (temperature, distance, weight)
> 4. Uses a `switch-case` menu system with a `do-while` loop for continuous interaction
> 5. Formats output cleanly with `printf` precision specifiers

---

## ⚡ PHASE 2 — FUNCTIONS & PROGRAM ORGANIZATION
> *"Functions are the building blocks of maintainable C code."*

### Module 2.1: Functions — Fundamentals
  - Function declaration (prototype) vs. definition
  - Parameters and arguments (pass by value)
  - Return types & `void`
  - The call stack — how function calls work in memory
  - Stack frames: local variables, return address, saved registers

### Module 2.2: Functions — Advanced
  - Recursion: base case, recursive case, stack depth
  - Recursive vs. Iterative tradeoffs
  - Tail recursion (and why C compilers optimize it)
  - Variadic functions: `stdarg.h` — `va_list`, `va_start`, `va_arg`, `va_end`
  - Function pointers (introduction — deep dive in Phase 4)
  - `inline` functions
  - `static` functions (file scope)

### Module 2.3: Scope, Lifetime & Linkage
  - **Scope:** Block, Function, File, Global
  - **Lifetime:** Automatic (stack) vs. Static vs. Dynamic (heap)
  - **Storage classes:** `auto`, `static`, `extern`, `register`
  - **Linkage:** Internal (`static`) vs. External (`extern`)
  - The difference between *declaration* and *definition*

### Module 2.4: Header Files & Multi-File Programs
  - Creating `.h` header files
  - Include guards: `#ifndef` / `#define` / `#endif` and `#pragma once`
  - Separating interface (`.h`) from implementation (`.c`)
  - Compiling multi-file projects: `gcc file1.c file2.c -o program`
  - Makefiles: targets, dependencies, rules, variables, `phony` targets

### Module 2.5: The C Preprocessor (Deep Dive)
  - Macro definitions: `#define`, parameterized macros
  - Macro pitfalls: side effects, operator precedence (wrapping in parentheses)
  - Conditional compilation: `#if`, `#ifdef`, `#ifndef`, `#elif`, `#else`, `#endif`
  - `#include` search paths: `""` vs `<>`
  - `#pragma`, `#error`, `#warning`
  - Stringification (`#`) and Token Pasting (`##`)
  - Predefined macros: `__FILE__`, `__LINE__`, `__DATE__`, `__func__`

> ### 🛠️ Phase 2 Project: **"Math & Stats Library"**
> Create a **multi-file C library** (`mathlib.h` + `mathlib.c`):
> - Functions: `factorial()`, `fibonacci()`, `power()`, `gcd()`, `lcm()`, `isPrime()`, `nCr()`, `nPr()`
> - Stats: `mean()`, `median()`, `mode()`, `std_deviation()` (take arrays)
> - Implement both iterative and recursive versions where applicable
> - Write a `main.c` that uses the library interactively
> - Build with a proper `Makefile` with `clean`, `all`, and `debug` targets
> - Use `#ifdef DEBUG` for debug print statements

---

## ⚡ PHASE 3 — ARRAYS, STRINGS & BUFFER MANAGEMENT
> *"In C, strings are just arrays. And arrays are just pointers. And pointers are just numbers. Welcome to C."*

### Module 3.1: Arrays
  - Declaration, initialization, zero-initialization
  - Accessing elements, bounds (C does NOT check bounds!)
  - Array decay: arrays as pointers to first element
  - Passing arrays to functions (with size parameter)
  - Multi-dimensional arrays: 2D, 3D
  - Row-major order in memory
  - Variable Length Arrays (VLAs) — C99, and why to be cautious

### Module 3.2: Strings in C
  - Character arrays vs. string literals
  - Null terminator `\0` — the most important byte
  - String initialization: `char s[] = "hello"` vs `char *s = "hello"` (critical difference!)
  - `<string.h>` functions:
    - `strlen()`, `strcpy()`, `strncpy()`
    - `strcat()`, `strncat()`
    - `strcmp()`, `strncmp()`
    - `strchr()`, `strrchr()`, `strstr()`
    - `strtok()` (tokenization — and its statefulness)
    - `memcpy()`, `memmove()`, `memset()`, `memcmp()`
  - Buffer overflow dangers with strings
  - Safe alternatives: `snprintf()`, `strlcpy()` (BSD)

### Module 3.3: Character Handling
  - `<ctype.h>`: `isalpha()`, `isdigit()`, `isalnum()`, `toupper()`, `tolower()`, `isspace()`
  - ASCII table understanding
  - Character arithmetic: `'A' + 1 = 'B'`

### Module 3.4: String Conversion
  - `atoi()`, `atof()`, `atol()` — simple but unsafe
  - `strtol()`, `strtod()`, `strtoul()` — safe with error checking
  - `sprintf()` / `snprintf()` — number to string

> ### 🛠️ Phase 3 Project: **"Text Processing Engine"**
> Build a CLI tool that reads a text file and:
> 1. Counts words, lines, characters, sentences (like `wc` on steroids)
> 2. Finds & replaces a substring (custom `str_replace()`)
> 3. Extracts all unique words and sorts them alphabetically
> 4. Detects palindromes in the text
> 5. Implements a simple Caesar cipher (encrypt/decrypt)
> All string operations must be implemented **manually** (no `<string.h>` for core logic), then benchmarked against standard library versions.

---

## ⚡ PHASE 4 — POINTERS (THE HEART OF C)
> *"If you truly understand pointers, you truly understand C."*

### Module 4.1: Pointer Fundamentals
  - What is a pointer? (Memory address holder)
  - Declaration: `int *p;` — reading pointer declarations
  - Address-of operator: `&`
  - Dereference operator: `*`
  - Pointer size (platform-dependent: 4 bytes on 32-bit, 8 bytes on 64-bit)
  - `NULL` pointer, uninitialized pointers, dangling pointers
  - `void *` — the generic pointer

### Module 4.2: Pointers & Arrays
  - Array name as a pointer to first element
  - Pointer arithmetic: `p + 1`, `p - 1`, `p2 - p1`
  - `*(arr + i)` vs `arr[i]` — identical
  - Iterating arrays with pointers
  - Passing arrays to functions (pointer + size)
  - Pointer to an array vs. array of pointers

### Module 4.3: Pointers & Strings
  - `char *str` vs `char str[]`
  - String literals in read-only memory
  - Array of strings: `char *words[]`
  - Building `argv`-style string arrays

### Module 4.4: Pointer to Pointer (Multi-Level)
  - `int **pp;` — double pointers
  - Use case: modifying a pointer inside a function
  - `char **argv` — command-line arguments
  - Dynamic 2D arrays with `int **`

### Module 4.5: Function Pointers
  - Declaration: `int (*fptr)(int, int);`
  - Assigning and calling function pointers
  - Callback functions
  - Arrays of function pointers (dispatch tables)
  - `qsort()` and `bsearch()` — real-world function pointer usage
  - Simulating polymorphism / strategy pattern in C

### Module 4.6: Pointers & `const`
  - `const int *p` — pointer to const int (can't modify value)
  - `int *const p` — const pointer to int (can't modify address)
  - `const int *const p` — both const
  - Reading declarations right-to-left (the clockwise/spiral rule)

### Module 4.7: Common Pointer Bugs & Debugging
  - Segmentation faults (SIGSEGV)
  - Dangling pointers
  - Wild pointers
  - Memory leaks (intro — deep dive in Phase 5)
  - Using **Valgrind** for memory debugging
  - Using **AddressSanitizer** (`-fsanitize=address`)

> ### 🛠️ Phase 4 Project: **"Dynamic Array Library (Vector)"**
> Implement a **generic dynamic array** (like C++ `std::vector`) in pure C:
> ```c
> typedef struct {
>     void *data;
>     size_t size;
>     size_t capacity;
>     size_t element_size;
> } Vector;
> ```
> Functions:
> - `vector_create()`, `vector_destroy()`
> - `vector_push()`, `vector_pop()`, `vector_get()`, `vector_set()`
> - `vector_resize()` (double capacity on overflow)
> - `vector_sort()` (takes a function pointer comparator)
> - `vector_foreach()` (takes a callback function pointer)
> Test with `int`, `double`, `char*`, and custom structs. Run through **Valgrind** with zero leaks.

---

## ⚡ PHASE 5 — DYNAMIC MEMORY MANAGEMENT
> *"With great power (malloc) comes great responsibility (free)."*

### Module 5.1: Stack vs. Heap
  - Stack: automatic, fast, limited, LIFO
  - Heap: manual, flexible, slower, fragmentation-prone
  - Memory layout of a C program: Text → Data → BSS → Heap → ↕ → Stack
  - Stack overflow vs. heap overflow

### Module 5.2: Dynamic Allocation Functions
  - `malloc()` — allocate uninitialized memory
  - `calloc()` — allocate zero-initialized memory
  - `realloc()` — resize allocation (with gotchas)
  - `free()` — release memory
  - Return value checking (never ignore `malloc` returning `NULL`)
  - Casting `malloc` in C: `(int *)malloc(...)` — unnecessary in C, required in C++

### Module 5.3: Dynamic Arrays & Matrices
  - Allocating 1D dynamic arrays
  - Allocating 2D dynamic arrays:
    - Array of pointers (rows on heap individually)
    - Single contiguous block with row pointers
    - Flattened 1D with index math: `arr[i * cols + j]`
  - Freeing multi-dimensional allocations (reverse order)

### Module 5.4: Dynamic Strings
  - `strdup()` / `strndup()`
  - Building a growable string buffer
  - Implementing a `StringBuilder`

### Module 5.5: Memory Bugs & Tools
  - **Leaks:** forgetting to `free()`
  - **Double free:** freeing the same pointer twice
  - **Use-after-free:** accessing freed memory
  - **Buffer overflow / underflow:** writing past allocation
  - **Valgrind (memcheck):** `valgrind --leak-check=full ./program`
  - **AddressSanitizer (ASan):** `gcc -fsanitize=address`
  - **Electric Fence**, **mtrace()**
  - Setting pointers to `NULL` after `free()`

### Module 5.6: Custom Memory Allocators (Advanced)
  - Why custom allocators? (Performance, pooling, arena)
  - Arena / Bump allocator
  - Pool allocator
  - Free list allocator
  - How `malloc` works internally (sbrk, mmap, free lists, bins)

> ### 🛠️ Phase 5 Project: **"Arena Memory Allocator"**
> Implement a **custom arena (bump) allocator**:
> ```c
> typedef struct {
>     char *buffer;
>     size_t capacity;
>     size_t offset;
> } Arena;
> ```
> Functions:
> - `arena_create(size_t capacity)` — allocate the arena
> - `arena_alloc(Arena *a, size_t size)` — bump the pointer
> - `arena_reset(Arena *a)` — reset offset to 0 (bulk free)
> - `arena_destroy(Arena *a)` — free the underlying buffer
> Use the arena to build a linked list of 10,000 nodes, compare performance against individual `malloc()` calls using `clock()`. Run through Valgrind with zero leaks.

---

## ⚡ PHASE 6 — STRUCTURES, UNIONS & DATA MODELING
> *"C doesn't have classes. It has something more powerful: struct + function pointers."*

### Module 6.1: Structures (`struct`)
  - Defining and declaring structs
  - Accessing members: dot `.` operator
  - Struct initialization: designated initializers (C99): `{.x = 10, .y = 20}`
  - Nested structs
  - Arrays of structs
  - `sizeof` a struct — memory alignment & padding
  - `typedef` for cleaner naming

### Module 6.2: Structs & Pointers
  - Pointer to struct: arrow `->` operator
  - Passing structs to functions: by value vs. by pointer (by pointer is standard)
  - Returning structs from functions
  - Dynamic struct allocation: `malloc(sizeof(struct Node))`
  - Self-referential structs (linked list nodes!)

### Module 6.3: Unions
  - What is a union? (All members share the same memory)
  - `sizeof(union)` = size of largest member
  - Use case: type-punning, variant types, protocol parsing
  - Tagged unions (union + enum discriminator) — simulating algebraic data types

### Module 6.4: Enumerations (`enum`)
  - Defining enums
  - Default values (0, 1, 2...) and custom values
  - Enums as state machines
  - Enum vs. `#define` — advantages

### Module 6.5: Bit Fields
  - Declaring bit fields in structs
  - Packing flags into minimal space
  - Use case: hardware registers, protocol headers
  - Portability concerns

### Module 6.6: Advanced Struct Patterns
  - Opaque pointers (information hiding / encapsulation in C)
  - Flexible array members (C99): `struct { int n; int data[]; };`
  - Struct inheritance simulation (embedding base struct as first member)
  - Object-oriented C: struct + function pointer tables (vtable pattern)

> ### 🛠️ Phase 6 Project: **"Student Database System"**
> Build a complete **student records management system**:
> - **Data model:**
>   ```c
>   typedef struct {
>       uint32_t id;
>       char name[64];
>       float gpa;
>       enum { CS, EE, ME, CE } department;
>       struct { int day, month, year; } dob;
>   } Student;
>   ```
> - **Features:**
>   - Add, Delete, Search (by name/ID), Update records
>   - Sort by name, GPA, or ID (using `qsort` with function pointers)
>   - Save/Load records to/from a binary file (`fwrite`/`fread`)
>   - Save/Load records to/from a CSV file
>   - Dynamic resizing of the student array (realloc)
> - Use opaque pointers to hide the database internals behind an API

---

## ⚡ PHASE 7 — FILE I/O & SERIALIZATION
> *"Programs that can't persist data are just toys."*

### Module 7.1: File Streams
  - `FILE *` type and `fopen()` modes: `"r"`, `"w"`, `"a"`, `"r+"`, `"w+"`, `"rb"`, `"wb"`
  - `fclose()` — always close your files
  - Error checking: `NULL` return from `fopen()`, `errno`, `perror()`, `strerror()`

### Module 7.2: Text File I/O
  - Character: `fgetc()`, `fputc()`
  - String/Line: `fgets()`, `fputs()`
  - Formatted: `fprintf()`, `fscanf()`
  - Reading a file line-by-line (the `fgets` loop pattern)
  - End of file: `feof()` vs checking return values (the right way)

### Module 7.3: Binary File I/O
  - `fread()`, `fwrite()` — reading/writing raw bytes
  - Serializing structs to binary files
  - Endianness concerns (little-endian vs. big-endian)
  - File positioning: `fseek()`, `ftell()`, `rewind()`, `fgetpos()`, `fsetpos()`
  - Random access patterns

### Module 7.4: Standard Streams
  - `stdin`, `stdout`, `stderr`
  - Redirecting output: `freopen()`
  - Piping in Unix: `program1 | program2`
  - Buffering modes: unbuffered, line-buffered, fully-buffered (`setvbuf`)

### Module 7.5: Advanced I/O
  - Memory-mapped I/O with `mmap()` (POSIX)
  - `tmpfile()`, `tmpnam()`
  - Low-level I/O (POSIX): `open()`, `read()`, `write()`, `close()`, file descriptors
  - `select()` / `poll()` / `epoll()` for I/O multiplexing (intro)

> ### 🛠️ Phase 7 Project: **"Custom Log File Analyzer"**
> Build a tool that:
> 1. Parses Apache/Nginx-style log files (text parsing)
> 2. Extracts: IP addresses, timestamps, HTTP methods, status codes, response sizes
> 3. Generates a binary index file for fast random access to any log entry
> 4. Produces a report: top 10 IPs, most common errors, traffic per hour
> 5. Supports `stdin` piping: `cat access.log | ./loganalyzer --top-ips`
> 6. Implements a "follow" mode (like `tail -f`) using `fseek()` polling

---

## ⚡ PHASE 8 — DATA STRUCTURES IN C
> *"Every great C programmer is a great data structure implementer."*

### Module 8.1: Linked Lists
  - Singly Linked List: insert (head, tail, middle), delete, search, reverse
  - Doubly Linked List: bidirectional traversal, insert, delete
  - Circular Linked List
  - Linked List vs. Array tradeoffs (cache, allocation, access patterns)

### Module 8.2: Stacks
  - Array-based stack
  - Linked-list-based stack
  - Applications: expression evaluation, bracket matching, undo system, DFS

### Module 8.3: Queues
  - Array-based queue (circular buffer implementation)
  - Linked-list-based queue
  - Priority Queue (min-heap based)
  - Deque (double-ended queue)
  - Applications: BFS, scheduling, producer-consumer

### Module 8.4: Hash Tables
  - Hash functions: djb2, FNV-1a, murmur
  - Collision resolution: chaining (linked lists) vs. open addressing (linear probing, quadratic probing, double hashing)
  - Load factor & rehashing
  - Implementing a complete hash map in C

### Module 8.5: Trees
  - Binary Tree: traversals (inorder, preorder, postorder, level-order)
  - Binary Search Tree (BST): insert, search, delete, min, max
  - Self-balancing BSTs: AVL tree (rotations), Red-Black tree (concepts)
  - Trie (prefix tree): insert, search, autocomplete
  - Heap: min-heap, max-heap, heapify, heap sort

### Module 8.6: Graphs
  - Representations: adjacency matrix, adjacency list
  - BFS & DFS (iterative & recursive)
  - Dijkstra's shortest path
  - Topological sort
  - Cycle detection

> ### 🛠️ Phase 8 Project: **"LibDSA — A Reusable Data Structures Library"**
> Build a **production-quality C library** (`libdsa`) with:
> - Generic Linked List (using `void *`)
> - Hash Map with chaining (string keys → `void *` values)
> - Min-Heap / Priority Queue
> - BST with insert, delete, in-order iterator
> - Graph with adjacency list, BFS, DFS, Dijkstra
> Each data structure must have:
> - A clean API in a `.h` file
> - Unit tests (using a simple custom test framework or `minunit.h`)
> - Valgrind-verified zero memory leaks
> - A `Makefile` that builds the shared library (`.so` / `.a`)

---

## ⚡ PHASE 9 — SYSTEMS PROGRAMMING (POSIX / Linux)
> *"C is the language of the operating system."*

### Module 9.1: Process Management
  - `fork()` — creating child processes
  - `exec()` family: `execvp()`, `execl()`, etc.
  - `wait()`, `waitpid()` — reaping children
  - Zombie processes, Orphan processes
  - Process IDs: `getpid()`, `getppid()`
  - Environment variables: `getenv()`, `setenv()`

### Module 9.2: Inter-Process Communication (IPC)
  - **Pipes:** `pipe()`, unnamed pipes, `dup2()` for redirection
  - **Named Pipes (FIFOs):** `mkfifo()`
  - **Shared Memory:** `shmget()`, `shmat()`, `shmdt()` (System V) / `shm_open()`, `mmap()` (POSIX)
  - **Message Queues:** System V & POSIX
  - **Signals:** `signal()`, `sigaction()`, common signals (SIGINT, SIGTERM, SIGKILL, SIGSEGV, SIGCHLD)
  - **Sockets** (covered in Module 9.5)

### Module 9.3: Threads (POSIX Threads — pthreads)
  - `pthread_create()`, `pthread_join()`, `pthread_detach()`
  - Thread vs. Process tradeoffs
  - Race conditions & data races
  - **Mutexes:** `pthread_mutex_lock()`, `pthread_mutex_unlock()`
  - **Condition Variables:** `pthread_cond_wait()`, `pthread_cond_signal()`
  - **Read-Write Locks:** `pthread_rwlock_t`
  - **Semaphores:** `sem_init()`, `sem_wait()`, `sem_post()`
  - Deadlock: causes, prevention, detection
  - Thread-safe data structures
  - Thread Pools (producer-consumer pattern)

### Module 9.4: File System Programming
  - `opendir()`, `readdir()`, `closedir()` — directory traversal
  - `stat()`, `lstat()`, `fstat()` — file metadata
  - `chmod()`, `chown()` — permissions
  - Symbolic links: `symlink()`, `readlink()`
  - File watching: `inotify` (Linux)
  - Implementing `ls`, `find`, `tree` from scratch

### Module 9.5: Network Programming (Sockets)
  - Socket API: `socket()`, `bind()`, `listen()`, `accept()`, `connect()`
  - `send()` / `recv()` vs `write()` / `read()`
  - TCP client & server implementation
  - UDP client & server implementation
  - `struct sockaddr_in`, `htons()`, `inet_pton()`, `getaddrinfo()`
  - Handling multiple clients:
    - `fork()` per connection
    - `select()` / `poll()`
    - `epoll()` (Linux — the scalable way)
  - Non-blocking I/O: `fcntl()` with `O_NONBLOCK`
  - HTTP server basics: parsing HTTP requests

### Module 9.6: Memory-Mapped I/O & Advanced Memory
  - `mmap()`, `munmap()`, `msync()`
  - Shared memory via `mmap` with `MAP_SHARED`
  - Memory-mapped files for fast I/O
  - `mprotect()` — changing page permissions
  - `brk()` / `sbrk()` — how `malloc` grows the heap (old way)

> ### 🛠️ Phase 9 Project: **"MiniShell — A Unix Shell"**
> Build a **functional Unix shell** from scratch:
> - **Command execution:** fork + exec for external commands
> - **Built-ins:** `cd`, `pwd`, `echo`, `exit`, `export`, `unset`, `history`
> - **I/O Redirection:** `>`, `>>`, `<`, `2>`
> - **Pipes:** `ls -la | grep .c | wc -l` (unlimited pipe chains)
> - **Background processes:** `command &`, `jobs`, `fg`, `bg`
> - **Signal handling:** Ctrl+C (SIGINT) doesn't kill the shell, only the foreground process
> - **Tab completion** (bonus, using `readline` library)
> - **Command history** (using a linked list or file-backed)
> - Proper zombie reaping with `SIGCHLD` handler

---

## ⚡ PHASE 10 — ADVANCED C & SOFTWARE ENGINEERING
> *"Writing C is easy. Writing correct, secure, maintainable C is an art."*

### Module 10.1: The C Standard Library — Complete Mastery
  - `<stdlib.h>`: `malloc`, `free`, `exit`, `atexit`, `qsort`, `bsearch`, `abs`, `rand`, `srand`, `system`
  - `<string.h>`: all `str*` and `mem*` functions
  - `<math.h>`: `pow`, `sqrt`, `ceil`, `floor`, `log`, `sin`, `cos`, `fabs`
  - `<time.h>`: `time()`, `clock()`, `difftime()`, `strftime()`, `struct tm`
  - `<signal.h>`: `signal()`, `raise()`
  - `<setjmp.h>`: `setjmp()`, `longjmp()` — non-local jumps (error handling)
  - `<assert.h>`: `assert()` — defensive programming
  - `<errno.h>`: error codes & checking
  - `<stdarg.h>`: variadic functions
  - `<stdbool.h>`: `bool`, `true`, `false` (C99)

### Module 10.2: Error Handling Patterns in C
  - Return codes convention (0 = success, -1 = error)
  - `errno` + `perror()` + `strerror()`
  - Goto-based cleanup pattern (Linux kernel style)
  - `setjmp` / `longjmp` for exception-like behavior
  - Error propagation strategies
  - Defensive programming: assertions, preconditions, postconditions

### Module 10.3: Build Systems & Toolchains
  - **Makefile mastery:** pattern rules, automatic variables (`$@`, `$<`, `$^`), `$(wildcard)`, dependencies
  - **CMake:** `CMakeLists.txt`, targets, libraries, `find_package`, cross-compilation
  - **pkg-config** for finding library flags
  - **Static libraries** (`.a`): `ar rcs libfoo.a foo.o`
  - **Shared libraries** (`.so` / `.dll`): `gcc -shared -fPIC`
  - `dlopen()`, `dlsym()` — runtime dynamic loading

### Module 10.4: Testing & Quality Assurance
  - Unit testing frameworks: **Unity**, **CUnit**, **Check**, **minunit**
  - Test-driven development in C
  - Code coverage: `gcov`, `lcov`
  - Static analysis: `cppcheck`, `clang-tidy`, `splint`
  - Dynamic analysis: **Valgrind** (memcheck, cachegrind, callgrind, helgrind)
  - Fuzzing: **AFL** (American Fuzzy Lop), **libFuzzer**
  - Sanitizers: ASan, UBSan (`-fsanitize=undefined`), TSan (thread sanitizer)

### Module 10.5: Performance & Optimization
  - Profiling: `gprof`, `perf`, Valgrind's `callgrind`
  - Cache-friendly programming: data locality, struct of arrays vs array of structs
  - Loop optimization: unrolling, strength reduction
  - Branch prediction hints: `__builtin_expect` / `likely()` / `unlikely()`
  - Compiler optimization levels: `-O0`, `-O1`, `-O2`, `-O3`, `-Os`, `-Ofast`
  - Understanding compiler output: `gcc -S`, Godbolt Compiler Explorer
  - `restrict` keyword for pointer aliasing optimization
  - SIMD intrinsics overview (SSE, AVX)
  - Benchmarking correctly: avoiding dead code elimination, `volatile`

### Module 10.6: C Standards Evolution
  - **C89/C90** (ANSI C): the baseline
  - **C99**: `//` comments, VLAs, `<stdbool.h>`, `<stdint.h>`, designated initializers, `inline`, `restrict`, `snprintf`
  - **C11**: `_Generic`, `_Static_assert`, `<threads.h>`, `_Atomic`, anonymous structs/unions, `aligned_alloc`
  - **C17**: bug fixes only (no new features)
  - **C23**: `#embed`, `typeof`, `nullptr`, `constexpr`, binary literals, improved `auto`
  - Choosing the right standard: `-std=c11`, `-std=c17`, `-std=c2x`

### Module 10.7: Security in C
  - Common vulnerabilities: buffer overflow, format string attacks, integer overflow, use-after-free
  - Secure coding guidelines: CERT C, MISRA C
  - Stack canaries, ASLR, NX bit (OS protections)
  - Safe string functions: `snprintf`, `strlcpy`, `strlcat`
  - Input validation best practices
  - The importance of `-Wall -Wextra -Werror -fstack-protector-strong`

> ### 🛠️ Phase 10 Project: **"HttpForge — A Multi-Threaded HTTP Server"**
> Build a **production-inspired HTTP/1.1 server** from scratch in C:
> - **Networking:** TCP sockets, `epoll`-based event loop
> - **Concurrency:** Thread pool (configurable number of worker threads)
> - **HTTP Parsing:** Parse method, URI, headers, body manually
> - **Features:**
>   - Serve static files (HTML, CSS, JS, images) with correct MIME types
>   - Directory listing
>   - `GET` and `POST` support
>   - `Connection: keep-alive` support
>   - Basic logging to file (with timestamps)
>   - Configurable via a config file (port, root directory, thread count)
>   - Graceful shutdown on `SIGINT` / `SIGTERM`
> - **Quality:**
>   - Built with **CMake**
>   - Unit tests with **Unity**
>   - Zero memory leaks (Valgrind verified)
>   - Benchmarked with **wrk** or **ab** (Apache Bench)
>   - Fuzzed with **AFL** on the HTTP parser

---

## 📊 PHASE MAP (Visual Summary)

```
Phase 0  ██░░░░░░░░░░  Environment & Compilation Pipeline
Phase 1  ███░░░░░░░░░  Language Fundamentals (Types, Operators, Control Flow)
Phase 2  ████░░░░░░░░  Functions & Program Organization
Phase 3  █████░░░░░░░  Arrays, Strings & Buffer Management
Phase 4  ███████░░░░░  Pointers (The Heart of C)
Phase 5  ████████░░░░  Dynamic Memory Management
Phase 6  █████████░░░  Structs, Unions & Data Modeling
Phase 7  ██████████░░  File I/O & Serialization
Phase 8  ██████████░░  Data Structures in C
Phase 9  ████████████  Systems Programming (Processes, Threads, Sockets)
Phase 10 ████████████  Advanced C & Software Engineering
```

---

## 🎯 DIFFICULTY & SKILL PROGRESSION

```
         BEGINNER           INTERMEDIATE            ADVANCED              EXPERT
       ┌─────────┐        ┌─────────────┐       ┌───────────┐       ┌──────────┐
       │ Phase 0  │───────▶│   Phase 3   │──────▶│  Phase 6  │──────▶│ Phase 9  │
       │ Phase 1  │        │   Phase 4   │       │  Phase 7  │       │ Phase 10 │
       │ Phase 2  │        │   Phase 5   │       │  Phase 8  │       │          │
       └─────────┘        └─────────────┘       └───────────┘       └──────────┘
       "I can write        "I own pointers       "I build            "I write
        C programs"         & memory"             libraries"          systems"
```

---

## 📚 RECOMMENDED RESOURCES

| Resource | Type | Phase |
|----------|------|-------|
| *C Programming: A Modern Approach* — K.N. King | 📖 Book (Best for learning) | 0–6 |
| *The C Programming Language* — K&R (2nd Ed.) | 📖 Book (The Bible) | 2–7 |
| *C Primer Plus* — Stephen Prata | 📖 Book (Gentle) | 0–5 |
| *Expert C Programming: Deep C Secrets* — Peter van der Linden | 📖 Book | 4–8 |
| *21st Century C* — Ben Klemens | 📖 Book (Modern practices) | 6–10 |
| *Advanced Programming in the UNIX Environment* — Stevens & Rago | 📖 Book (APUE) | 9 |
| *Computer Systems: A Programmer's Perspective* (CSAPP) | 📖 Book | 5–10 |
| *Beej's Guide to C Programming* | 🌐 Free Online | 0–6 |
| *Beej's Guide to Network Programming* | 🌐 Free Online | 9 |
| CS50 — Harvard (YouTube) | 🎥 Video Course | 0–4 |
| Jacob Sorber (YouTube) | 🎥 Systems C | 4–9 |
| Jens Gustedt — *Modern C* | 📖 Free Book | 6–10 |
| Exercism — C Track | 🧪 Practice | 1–6 |
| Valgrind Documentation | 📄 Tool Docs | 4–10 |
| Godbolt Compiler Explorer | 🧪 Tool | 5–10 |

---

## 🗺️ WHERE C TAKES YOU (Career Paths)

```
                                 ┌──────────────────────┐
                                 │  Embedded Systems /   │
                          ┌─────▶│  IoT / Firmware       │
                          │      └──────────────────────┘
                          │      ┌──────────────────────┐
                          │      │  Operating Systems /  │
                  ┌───────┤─────▶│  Kernel Development   │
                  │       │      └──────────────────────┘
  ┌───────────┐   │       │      ┌──────────────────────┐
  │           │   │       │      │  Systems Programming  │
  │  Master C ├───┤       ├─────▶│  (Databases, VMs,     │
  │           │   │       │      │   Compilers, Engines)  │
  └───────────┘   │       │      └──────────────────────┘
                  │       │      ┌──────────────────────┐
                  │       │      │  Cybersecurity /      │
                  │       ├─────▶│  Reverse Engineering  │
                  │       │      └──────────────────────┘
                  │       │      ┌──────────────────────┐
                  │       │      │  Game Engines /       │
                  └───────┴─────▶│  High-Performance     │
                                 │  Computing (HPC)      │
                                 └──────────────────────┘
```

---

> ### 💡 Final Advice
> **"In C, the compiler trusts you completely. It will let you shoot yourself in the foot, blow off your whole leg, and then hand you another loaded gun. Your safety net is *knowledge*."**
>
> Three non-negotiable habits:
> 1. **Compile with all warnings ON:** `gcc -Wall -Wextra -Werror -std=c11 -g`
> 2. **Run Valgrind on EVERYTHING:** `valgrind --leak-check=full --show-leak-kinds=all ./program`
> 3. **Read the `man` pages** before Googling. They are gold.
>
> C rewards discipline. Every Phase here should be **50% reading, 50% coding with your hands on the keyboard.** Don't skip the projects — they ARE the learning.

---

*This roadmap takes you from "What's a pointer?" to "I can write an HTTP server, a shell, a memory allocator, and a data structures library — all from scratch in pure C."* 🚀