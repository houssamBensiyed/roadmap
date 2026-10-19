# 🐍 THE ULTIMATE PYTHON ROADMAP
### From Zero to Production-Grade Python Mastery

> **Structure:** Phase → Modules → Sections
> **Estimated Duration:** ~7-10 Months (Dedicated Study)
> **Prerequisite:** None — starts from absolute zero
> *Python is the most versatile language alive. It's the #1 language for beginners AND the #1 language for AI/ML, data science, automation, and scripting.*

---

## ⚡ PHASE 0 — ENVIRONMENT SETUP & PYTHON ORIENTATION
> *"Python's power is in its simplicity. But simplicity doesn't mean shallow."*

---

### 📦 Module 0.1: Understanding Python's Identity

#### § 0.1.1 — What is Python & Why It Dominates
  - Created by Guido van Rossum (1991), named after Monty Python
  - Design philosophy: readability, simplicity, "batteries included"
  - The Zen of Python: `import this` — 19 guiding principles
  - Where Python dominates: AI/ML, data science, web backends, automation, scripting, DevOps, scientific computing, education, prototyping

#### § 0.1.2 — How Python Works
  - Interpreted language (technically compiled to bytecode, then interpreted)
  - Source (`.py`) → Bytecode (`.pyc`) → Python Virtual Machine (PVM)
  - CPython: the reference implementation (written in C)
  - Dynamic typing: types are checked at runtime, not compile time
  - Duck typing: "If it walks like a duck and quacks like a duck..."
  - Strongly typed: `"1" + 1` raises `TypeError` (unlike JavaScript)
  - Garbage collected: reference counting + cyclic garbage collector

#### § 0.1.3 — Python Implementations
  - **CPython** — the default, standard implementation
  - **PyPy** — JIT-compiled, much faster for long-running programs
  - **Jython** — Python on JVM
  - **IronPython** — Python on .NET
  - **MicroPython / CircuitPython** — Python for microcontrollers
  - **GraalPy** — Python on GraalVM

#### § 0.1.4 — Python Version History
  - **Python 2** — legacy, EOL since Jan 2020 (never learn Python 2)
  - **Python 3.6** — f-strings, type hints improvements
  - **Python 3.7** — dataclasses, `breakpoint()`
  - **Python 3.8** — walrus operator `:=`, positional-only params
  - **Python 3.9** — dict merge `|`, type hinting generics in builtins
  - **Python 3.10** — structural pattern matching (`match/case`), better error messages
  - **Python 3.11** — 10-25% faster, exception groups, `tomllib`
  - **Python 3.12** — improved f-strings, per-interpreter GIL (experimental), `type` statement
  - **Python 3.13** — free-threaded mode (no-GIL experimental), JIT compiler (experimental)
  - **Python 3.14+** — continued performance improvements, GIL removal progress
  - Always use the latest stable release

---

### 📦 Module 0.2: Setting Up the Development Environment

#### § 0.2.1 — Installing Python
  - Official installer from python.org
  - Linux: usually pre-installed, `sudo apt install python3 python3-pip python3-venv`
  - macOS: `brew install python`
  - Windows: official installer (check "Add to PATH"!)
  - Verifying: `python3 --version`, `pip3 --version`
  - `python` vs `python3` — platform differences in naming

#### § 0.2.2 — Editors & IDEs
  - **VS Code + Python extension** (Microsoft) — the most popular choice
  - **PyCharm** (JetBrains) — the most powerful Python IDE
  - **Jupyter Notebook / JupyterLab** — interactive, cell-based (data science standard)
  - **Vim/Neovim + Pyright LSP** — lightweight, fast
  - **IDLE** — built-in, good for absolute beginners
  - Why PyCharm or VS Code: debugging, refactoring, virtual env integration, linting

#### § 0.2.3 — The Python REPL & Interactive Tools
  - `python3` — standard REPL
  - `ipython` — enhanced REPL (syntax highlighting, tab completion, magic commands)
  - Jupyter Notebook — browser-based interactive computing
  - Using the REPL for quick experimentation and learning

#### § 0.2.4 — Virtual Environments (Critical from Day One)
  - Why virtual environments: isolated dependencies per project
  - `python3 -m venv .venv` — create a virtual environment
  - Activating: `source .venv/bin/activate` (Linux/macOS), `.venv\Scripts\activate` (Windows)
  - Deactivating: `deactivate`
  - `pip install package` — install into active virtual environment
  - `pip freeze > requirements.txt` — export dependencies
  - `pip install -r requirements.txt` — install from requirements file
  - **Never install packages globally** — always use virtual environments

#### § 0.2.5 — Modern Python Tooling (Overview)
  - **`pip`** — package installer (built-in)
  - **`uv`** — ultra-fast package installer and resolver (Astral, Rust-based — the future)
  - **`poetry`** — dependency management + packaging
  - **`pdm`** — PEP-compliant project management
  - **`ruff`** — extremely fast linter + formatter (replacing flake8, isort, black)
  - **`mypy`** — static type checker
  - **`pytest`** — testing framework (the standard)
  - Deep dive on each in Phase 9

---

### 📦 Module 0.3: Python Culture & Conventions

#### § 0.3.1 — PEP (Python Enhancement Proposals)
  - **PEP 8** — Style Guide for Python Code (memorize the key rules)
  - **PEP 20** — The Zen of Python (`import this`)
  - **PEP 257** — Docstring Conventions
  - **PEP 484** — Type Hints
  - PEPs are the governance mechanism for Python's evolution

#### § 0.3.2 — PEP 8 Essentials
  - 4 spaces for indentation (NEVER tabs)
  - Line length: 79-88 characters (modern projects use 88, Black's default)
  - `snake_case` for functions and variables
  - `PascalCase` for classes
  - `UPPER_SNAKE_CASE` for constants
  - `_private` for internal use, `__mangled` for name mangling
  - Two blank lines before top-level definitions, one blank line inside classes
  - Imports: standard library → third-party → local (separated by blank lines)

#### § 0.3.3 — Pythonic Thinking
  - "There should be one — and preferably only one — obvious way to do it"
  - Readability counts — code is read far more often than it is written
  - EAFP: "Easier to Ask Forgiveness than Permission" (use `try/except` over `if` checks)
  - LBYL: "Look Before You Leap" (use `if` checks) — sometimes appropriate
  - Python favors EAFP over LBYL

> ### 🛠️ Phase 0 Project: **"Environment Bootstrapper"**
> Write a Python script that prints:
> - Python version, implementation (CPython/PyPy), platform, architecture
> - All `sys.path` entries, virtual environment status
> - Installed packages with versions (via `importlib.metadata`)
> - The Zen of Python (capture `import this` output)
> - System info: OS, CPU count, total/available memory
> - Create it inside a virtual environment, install `ipython`, run it from both the standard REPL and `ipython`, and document the entire workflow

---

## ⚡ PHASE 1 — PYTHON LANGUAGE FUNDAMENTALS
> *"Python reads like English. That's by design."*

---

### 📦 Module 1.1: Variables, Data Types & Memory Model

#### § 1.1.1 — Variables & Assignment
  - Variables are names bound to objects (labels on boxes, not boxes themselves)
  - No variable declaration — just assign: `x = 42`
  - Multiple assignment: `a, b, c = 1, 2, 3`
  - Swap: `a, b = b, a` (no temp variable needed)
  - Augmented assignment: `+=`, `-=`, `*=`, `/=`, `//=`, `**=`, `%=`
  - Everything in Python is an object — integers, strings, functions, classes, modules
  - `id()` — memory address of an object
  - `type()` — type of an object
  - `is` vs `==`: identity vs equality

#### § 1.1.2 — Numeric Types
  - `int` — arbitrary precision integers (no overflow!)
  - `float` — 64-bit IEEE 754 floating point
  - `complex` — complex numbers: `3 + 4j`
  - `bool` — `True` / `False` (subclass of `int`: `True == 1`, `False == 0`)
  - Numeric operators: `+`, `-`, `*`, `/` (true division), `//` (floor division), `%`, `**` (power)
  - `divmod(a, b)` — returns `(quotient, remainder)`
  - `abs()`, `round()`, `pow()`
  - Underscore separators: `1_000_000`
  - `decimal.Decimal` — exact decimal arithmetic (financial calculations)
  - `fractions.Fraction` — exact rational numbers

#### § 1.1.3 — Strings (Immutable)
  - Single quotes, double quotes, triple quotes (multi-line)
  - f-strings (formatted strings): `f"Hello, {name}! {2 + 2 = }"`
  - Raw strings: `r"no\escape\here"` (regex, file paths)
  - Byte strings: `b"bytes"`
  - String methods: `upper()`, `lower()`, `strip()`, `split()`, `join()`, `replace()`, `find()`, `index()`, `startswith()`, `endswith()`, `count()`, `isdigit()`, `isalpha()`, `isalnum()`, `zfill()`, `center()`, `ljust()`, `rjust()`
  - String slicing: `s[start:stop:step]`, reverse with `s[::-1]`
  - `len()`, `in` operator: `"sub" in string`
  - Strings are immutable — every operation creates a new string
  - `str.format()` — older formatting (know it, prefer f-strings)
  - `%` formatting — legacy (recognize it, don't use it)
  - `textwrap` module for text formatting

#### § 1.1.4 — None Type
  - `None` — Python's null/nil
  - Singleton: there's only one `None` object
  - Check with `is None`, NOT `== None`
  - Used for: default arguments, optional values, function without explicit return

#### § 1.1.5 — Type Conversions
  - `int()`, `float()`, `str()`, `bool()`, `list()`, `tuple()`, `set()`, `dict()`
  - Truthiness: `bool(x)` — what evaluates to `False`?
    - `None`, `0`, `0.0`, `""`, `[]`, `()`, `{}`, `set()`, `frozenset()`, `range(0)`
  - Everything else is `True`

---

### 📦 Module 1.2: Operators

#### § 1.2.1 — Arithmetic Operators
  - `+`, `-`, `*`, `/` (true division → always float), `//` (floor division), `%`, `**`
  - No `++` or `--` operators in Python

#### § 1.2.2 — Comparison Operators
  - `==`, `!=`, `<`, `>`, `<=`, `>=`
  - Chained comparisons: `1 < x < 10` (reads naturally, evaluates correctly)
  - `is`, `is not` — identity comparison (same object in memory)

#### § 1.2.3 — Logical Operators
  - `and`, `or`, `not` — keywords, not symbols
  - Short-circuit evaluation
  - `and` / `or` return the actual value, not just `True`/`False` (truthy/falsy evaluation)
  - `x = a or b` — common pattern for defaults

#### § 1.2.4 — Bitwise Operators
  - `&`, `|`, `^`, `~`, `<<`, `>>`

#### § 1.2.5 — Membership & Identity
  - `in`, `not in` — membership testing
  - `is`, `is not` — identity testing
  - `in` works on: strings, lists, tuples, sets, dicts (checks keys), ranges

---

### 📦 Module 1.3: Control Flow

#### § 1.3.1 — Conditional Statements
  - `if`, `elif`, `else`
  - No parentheses needed, colon required, indentation defines blocks
  - Ternary expression: `value = a if condition else b`
  - No `switch/case` before Python 3.10

#### § 1.3.2 — Structural Pattern Matching (Python 3.10+)
  - `match` / `case` — not just switch, it's full pattern matching
  - Literal patterns, capture patterns, wildcard `_`
  - Sequence patterns: `case [first, *rest]:`
  - Mapping patterns: `case {"action": "buy", "quantity": qty}:`
  - Class patterns: `case Point(x=0, y=0):`
  - Guard clauses: `case x if x > 0:`
  - OR patterns: `case "quit" | "exit" | "q":`

#### § 1.3.3 — Loops
  - `for item in iterable:` — iterate over anything iterable
  - `for i in range(start, stop, step):` — numeric iteration
  - `while condition:`
  - `break`, `continue`
  - `for/else`, `while/else` — else runs when loop completes WITHOUT break (unique to Python!)
  - `enumerate(iterable, start=0)` — index + value
  - `zip(iter1, iter2, ...)` — parallel iteration
  - `zip` with `strict=True` (Python 3.10+) — error on unequal lengths
  - `reversed()`, `sorted()`
  - Nested loops and `itertools.product` as alternative

#### § 1.3.4 — Comprehensions (Pythonic Looping)
  - List comprehension: `[expr for item in iterable if condition]`
  - Set comprehension: `{expr for item in iterable}`
  - Dict comprehension: `{key: value for item in iterable}`
  - Generator expression: `(expr for item in iterable)` — lazy, memory efficient
  - Nested comprehensions: `[expr for row in matrix for item in row]`
  - Comprehension vs `map`/`filter` — comprehensions are more Pythonic
  - When NOT to use comprehensions: complex logic, side effects, more than 2 levels

---

### 📦 Module 1.4: Data Structures — Built-in

#### § 1.4.1 — Lists (Mutable, Ordered)
  - Creation: `[]`, `list()`, `list(iterable)`
  - Methods: `append()`, `extend()`, `insert()`, `remove()`, `pop()`, `clear()`, `index()`, `count()`, `sort()`, `reverse()`, `copy()`
  - Slicing: `lst[start:stop:step]`
  - List as stack: `append()` / `pop()` (LIFO)
  - Shallow copy: `lst.copy()`, `lst[:]`, `list(lst)`
  - Deep copy: `copy.deepcopy(lst)`
  - List multiplication: `[0] * 10` — gotcha with mutable elements!

#### § 1.4.2 — Tuples (Immutable, Ordered)
  - Creation: `()`, `(1, 2, 3)`, `tuple(iterable)`
  - Single element tuple: `(42,)` — comma is required!
  - Tuple unpacking: `a, b, c = (1, 2, 3)`
  - Extended unpacking: `first, *rest = [1, 2, 3, 4, 5]`
  - Named tuples: `collections.namedtuple('Point', ['x', 'y'])`
  - `typing.NamedTuple` — typed named tuples (modern approach)
  - When to use tuples: heterogeneous fixed collections, dict keys, function returns
  - Tuples are hashable (if all elements are hashable) — can be dict keys and set elements

#### § 1.4.3 — Dictionaries (Mutable, Ordered since 3.7)
  - Creation: `{}`, `dict()`, `dict(key=val)`, `dict(zip(keys, values))`
  - Access: `d[key]` (raises `KeyError`), `d.get(key, default)` (safe)
  - Methods: `keys()`, `values()`, `items()`, `update()`, `pop()`, `popitem()`, `setdefault()`, `clear()`
  - Merge: `d1 | d2` (Python 3.9+), `{**d1, **d2}` (older)
  - Merge update: `d1 |= d2` (Python 3.9+)
  - `defaultdict` — auto-creates missing keys with default factory
  - `Counter` — count occurrences
  - `OrderedDict` — insertion-ordered (less relevant since 3.7)
  - `ChainMap` — search through multiple dicts
  - Dict comprehension: `{k: v for k, v in pairs}`

#### § 1.4.4 — Sets (Mutable, Unordered, Unique)
  - Creation: `{1, 2, 3}`, `set(iterable)` — `{}` creates empty dict, NOT set!
  - Methods: `add()`, `remove()` (raises error), `discard()` (no error), `pop()`, `clear()`
  - Set operations: `union()` / `|`, `intersection()` / `&`, `difference()` / `-`, `symmetric_difference()` / `^`
  - Subset/superset: `issubset()` / `<=`, `issuperset()` / `>=`
  - `frozenset` — immutable set (hashable, can be dict key or set element)
  - Use case: membership testing (O(1)), removing duplicates, set mathematics

#### § 1.4.5 — Other Built-in Types
  - `range(start, stop, step)` — lazy integer sequence
  - `bytes` — immutable byte sequence
  - `bytearray` — mutable byte sequence
  - `memoryview` — zero-copy access to binary data

---

### 📦 Module 1.5: Functions — Fundamentals

#### § 1.5.1 — Defining Functions
  - `def function_name(parameters):` — function definition
  - `return` statement — returns a value (returns `None` if omitted)
  - Multiple return values: `return a, b, c` (returns a tuple)
  - Docstrings: `"""Description of the function."""` (first line of function body)
  - Functions are first-class objects: assign, pass, return

#### § 1.5.2 — Parameters & Arguments
  - Positional arguments: `func(a, b)`
  - Keyword arguments: `func(name="Alice", age=30)`
  - Default parameters: `def func(x, y=10):`
  - Mutable default argument trap: `def func(lst=[])` — NEVER use mutable defaults!
  - `*args` — variable positional arguments (tuple)
  - `**kwargs` — variable keyword arguments (dict)
  - Positional-only parameters (Python 3.8+): `def func(a, b, /, c, d):`
  - Keyword-only parameters: `def func(a, b, *, c, d):`
  - Full signature: `def func(pos_only, /, normal, *, kw_only, **kwargs):`

#### § 1.5.3 — Scope & LEGB Rule
  - **L**ocal — inside the current function
  - **E**nclosing — inside enclosing function (closures)
  - **G**lobal — module level
  - **B**uilt-in — Python's built-in names
  - `global` keyword — access/modify global variable from function
  - `nonlocal` keyword — access/modify enclosing function's variable
  - Avoid `global` — pass values as arguments and return results

#### § 1.5.4 — Lambda Functions
  - `lambda params: expression` — anonymous single-expression function
  - Use case: short callbacks, `sorted(key=lambda x: x[1])`, `map`, `filter`
  - Limitation: single expression only, no statements
  - When to use: very short, obvious operations
  - When NOT to use: anything complex (use named function instead)

> ### 🛠️ Phase 1 Project: **"TextStats — A Text Analysis Tool"**
> Build a CLI text analysis tool:
> - Read text from a file or stdin
> - Calculate: word count, line count, character count, sentence count, paragraph count
> - Frequency analysis: top N most common words, least common words, word length distribution
> - Statistics: average word length, average sentence length, reading level estimate (Flesch-Kincaid)
> - Find: longest word, shortest word, most repeated word, unique word count
> - Pattern matching: find all words matching a pattern (simple wildcard)
> - Use list and dict comprehensions extensively
> - Use `Counter` from collections for frequency analysis
> - Use `enumerate`, `zip`, and comprehensions idiomatically
> - Output as formatted table using f-strings with alignment

---

## ⚡ PHASE 2 — FUNCTIONS ADVANCED & PYTHONIC PATTERNS
> *"In Python, functions are first-class citizens. Treat them like royalty."*

---

### 📦 Module 2.1: Higher-Order Functions

#### § 2.1.1 — Functions as Arguments
  - Passing functions to other functions
  - `sorted(iterable, key=func)` — sort by custom key
  - `map(func, iterable)` — apply function to every element (returns iterator)
  - `filter(func, iterable)` — keep elements where function returns True
  - `functools.reduce(func, iterable)` — fold/accumulate
  - Comprehensions vs `map`/`filter` — comprehensions are preferred in modern Python

#### § 2.1.2 — Functions as Return Values
  - Factory functions: functions that create and return other functions
  - Parameterized behavior

#### § 2.1.3 — Closures
  - Inner function captures variables from enclosing scope
  - Free variables: variables referenced in a function but not defined there
  - `nonlocal` keyword for modifying enclosed variables
  - Use case: function factories, memoization, callback configuration
  - `func.__closure__` — inspect closure variables

---

### 📦 Module 2.2: Decorators

#### § 2.2.1 — Understanding Decorators
  - Decorator: a function that takes a function and returns a modified function
  - `@decorator` syntax — syntactic sugar for `func = decorator(func)`
  - Inner wrapper function pattern
  - `functools.wraps` — preserving the original function's metadata (name, docstring)

#### § 2.2.2 — Common Decorator Patterns
  - Logging decorator — log function calls
  - Timing decorator — measure execution time
  - Retry decorator — retry on failure with backoff
  - Authentication/authorization decorator
  - Caching decorator (manual, then `functools.lru_cache`)

#### § 2.2.3 — Advanced Decorators
  - Decorators with arguments: triple-nested function pattern
  - Class-based decorators: implementing `__call__`
  - Stacking decorators: `@dec1 @dec2 @dec3` — order matters (bottom-up)
  - Decorating class methods: `@staticmethod`, `@classmethod`, `@property`
  - `functools.lru_cache` — built-in memoization decorator
  - `functools.cache` (Python 3.9+) — simpler unbounded cache
  - `functools.total_ordering` — auto-generate comparison methods
  - `functools.singledispatch` — single-dispatch generic functions

---

### 📦 Module 2.3: Iterators & Generators

#### § 2.3.1 — The Iterator Protocol
  - `__iter__()` — returns the iterator object
  - `__next__()` — returns the next value, raises `StopIteration` when done
  - `for` loop calls `iter()` then `next()` repeatedly
  - Everything iterable: lists, tuples, strings, dicts, files, generators, ranges
  - Creating custom iterators by implementing `__iter__` and `__next__`

#### § 2.3.2 — Generators (Lazy Iterators)
  - `yield` keyword — turns a function into a generator
  - Generator function vs regular function: returns a generator object
  - Lazy evaluation: values produced one at a time, on demand
  - Memory efficient: can represent infinite sequences
  - Generator expressions: `(x**2 for x in range(1000000))` — no list in memory
  - `yield from` — delegate to a sub-generator (Python 3.3+)
  - Generator methods: `send()`, `throw()`, `close()`
  - Use case: reading large files line by line, infinite sequences, data pipelines

#### § 2.3.3 — `itertools` — Iterator Building Blocks
  - Infinite: `count()`, `cycle()`, `repeat()`
  - Terminating: `chain()`, `compress()`, `dropwhile()`, `takewhile()`, `islice()`, `starmap()`, `tee()`, `zip_longest()`
  - Combinatoric: `product()`, `permutations()`, `combinations()`, `combinations_with_replacement()`
  - `groupby()` — group consecutive elements
  - `accumulate()` — running totals
  - `pairwise()` (Python 3.10+) — sliding pairs
  - `batched()` (Python 3.12+) — split into batches

---

### 📦 Module 2.4: Functional Programming Tools

#### § 2.4.1 — `functools` Module
  - `partial()` — freeze some arguments of a function
  - `reduce()` — fold an iterable
  - `lru_cache()` / `cache()` — memoization
  - `wraps()` — preserve decorated function metadata
  - `total_ordering()` — auto-generate comparison methods
  - `singledispatch` — function overloading by first argument type
  - `cached_property` (Python 3.8+) — lazily computed property

#### § 2.4.2 — `operator` Module
  - `operator.add`, `operator.mul`, `operator.itemgetter`, `operator.attrgetter`
  - Use with `sorted()`, `map()`, `reduce()` instead of lambdas
  - `operator.methodcaller` — call a method by name

---

### 📦 Module 2.5: Unpacking & Advanced Assignment

#### § 2.5.1 — Iterable Unpacking
  - Tuple unpacking: `a, b = (1, 2)`
  - Extended unpacking: `first, *middle, last = [1, 2, 3, 4, 5]`
  - Nested unpacking: `(a, b), (c, d) = [(1, 2), (3, 4)]`
  - Unpacking in function calls: `func(*args, **kwargs)`
  - Dict unpacking: `{**dict1, **dict2}`

#### § 2.5.2 — Walrus Operator `:=` (Python 3.8+)
  - Assignment expression — assign AND return value in one expression
  - `if (n := len(data)) > 10:` — assign `n` and test in one line
  - `while chunk := file.read(8192):` — read and check in loop
  - Use sparingly — readability first

> ### 🛠️ Phase 2 Project: **"DataPipeline — A Lazy Data Processing Framework"**
> Build a generator-based data processing pipeline:
> - Source generators: read CSV line by line, read JSON line-delimited files, generate synthetic data
> - Transform generators: filter rows, map/transform fields, normalize values, deduplicate
> - Sink generators: write to CSV, write to JSON, print to console, collect into memory
> - Pipeline composition: chain generators together lazily (no intermediate lists)
> - Decorator suite: `@timer` (measure execution time), `@retry` (retry on failure), `@validate` (validate input/output), `@log_calls` (log function name + arguments)
> - Use `itertools` extensively: `chain`, `islice`, `groupby`, `batched`
> - Process a 1GB+ file using constant memory (prove with memory measurement)
> - Use `functools.lru_cache` for expensive computed values
> - Use `functools.partial` for creating pre-configured pipeline stages

---

## ⚡ PHASE 3 — OBJECT-ORIENTED PROGRAMMING
> *"Python's OOP is flexible, pragmatic, and un-dogmatic. Use it when it helps, not because Java said so."*

---

### 📦 Module 3.1: Classes & Objects

#### § 3.1.1 — Defining Classes
  - `class ClassName:` — class definition
  - `__init__(self)` — initializer (constructor)
  - `self` — reference to the current instance (explicit, not implicit like `this`)
  - Instance attributes: assigned in `__init__` via `self.attr = value`
  - Class attributes: defined directly in the class body (shared across instances)
  - Instance methods: first parameter is `self`
  - Instantiation: `obj = ClassName(args)` — no `new` keyword

#### § 3.1.2 — Class Methods & Static Methods
  - `@classmethod` — receives `cls` as first argument (for alternative constructors)
  - `@staticmethod` — no `self` or `cls` (utility functions logically grouped in class)
  - Factory methods using `@classmethod`: `Person.from_json(data)`
  - When to use which: instance method (default), classmethod (factory), staticmethod (utility)

#### § 3.1.3 — Properties
  - `@property` — getter (computed attribute, looks like attribute access)
  - `@name.setter` — setter with validation
  - `@name.deleter` — deleter
  - Properties vs getters/setters: Pythonic way is to start with plain attributes, add properties when needed
  - "We're all consenting adults" — Python doesn't enforce private access

#### § 3.1.4 — Access Control (Python's Approach)
  - **No true private** — Python trusts the developer
  - `public` — no prefix (default)
  - `_private` — single underscore: convention for "internal" (not enforced)
  - `__mangled` — double underscore: name mangling (`_ClassName__attr`) — discourages access, doesn't prevent it
  - `__dunder__` — double underscore both sides: magic/dunder methods (reserved for Python)
  - Python philosophy: privacy by convention, not enforcement

---

### 📦 Module 3.2: Magic / Dunder Methods

#### § 3.2.1 — String Representation
  - `__repr__(self)` — unambiguous string for developers (always implement this)
  - `__str__(self)` — readable string for users
  - `__format__(self, format_spec)` — custom formatting with f-strings
  - Rule: `__repr__` should ideally be valid Python code to recreate the object

#### § 3.2.2 — Comparison Methods
  - `__eq__`, `__ne__`, `__lt__`, `__le__`, `__gt__`, `__ge__`
  - `__hash__` — required for hashable objects (dict keys, set elements)
  - If you define `__eq__`, `__hash__` becomes `None` (objects become unhashable by default)
  - `@functools.total_ordering` — implement `__eq__` + one of `__lt__`/`__gt__`, get the rest for free

#### § 3.2.3 — Arithmetic Operator Overloading
  - `__add__`, `__sub__`, `__mul__`, `__truediv__`, `__floordiv__`, `__mod__`, `__pow__`
  - Reflected operators: `__radd__`, `__rsub__` (when left operand doesn't support the operation)
  - In-place operators: `__iadd__`, `__isub__` (`+=`, `-=`)
  - `__neg__`, `__pos__`, `__abs__`, `__invert__`

#### § 3.2.4 — Container Protocol Methods
  - `__len__` — `len(obj)`
  - `__getitem__` — `obj[key]` (subscript access)
  - `__setitem__` — `obj[key] = value`
  - `__delitem__` — `del obj[key]`
  - `__contains__` — `item in obj`
  - `__iter__` — `for item in obj`
  - `__reversed__` — `reversed(obj)`

#### § 3.2.5 — Callable & Context Manager Protocols
  - `__call__` — make instances callable: `obj(args)`
  - `__enter__`, `__exit__` — context manager protocol (`with` statement)
  - `__bool__` — truthiness: `if obj:`
  - `__len__` — also used for truthiness when `__bool__` is not defined

#### § 3.2.6 — Attribute Access Methods
  - `__getattr__` — called when attribute is NOT found (fallback)
  - `__getattribute__` — called for EVERY attribute access (rarely override)
  - `__setattr__` — called on every attribute assignment
  - `__delattr__` — called on `del obj.attr`
  - `__dir__` — customize `dir(obj)` output

---

### 📦 Module 3.3: Inheritance & Composition

#### § 3.3.1 — Single Inheritance
  - `class Child(Parent):` — child inherits from parent
  - `super()` — call parent's methods
  - `super().__init__()` — call parent's initializer
  - Method overriding: child redefines parent's method
  - `isinstance(obj, Class)` — type checking (works with inheritance)
  - `issubclass(Child, Parent)` — class hierarchy checking

#### § 3.3.2 — Multiple Inheritance & MRO
  - `class C(A, B):` — inherits from multiple classes
  - Method Resolution Order (MRO): C3 linearization algorithm
  - `ClassName.__mro__` or `ClassName.mro()` — inspect resolution order
  - `super()` follows the MRO (not just the direct parent)
  - Diamond problem: resolved by MRO
  - Mixin classes: small, focused classes designed for multiple inheritance

#### § 3.3.3 — Abstract Base Classes
  - `from abc import ABC, abstractmethod`
  - `class Shape(ABC):` — cannot be instantiated
  - `@abstractmethod` — subclasses MUST implement
  - `@abstractmethod` on properties: `@property @abstractmethod`
  - Use case: defining interfaces/contracts
  - `collections.abc` — abstract base classes for containers: `Iterable`, `Iterator`, `Sequence`, `Mapping`, `MutableMapping`

#### § 3.3.4 — Composition Over Inheritance
  - "Has-a" vs "is-a" relationship
  - Delegation: forward method calls to contained objects
  - Python community strongly favors composition
  - When to use inheritance: true "is-a" relationships, ABC/protocol definitions
  - When to use composition: everything else

---

### 📦 Module 3.4: Advanced OOP

#### § 3.4.1 — Dataclasses (Python 3.7+)
  - `from dataclasses import dataclass`
  - `@dataclass` — auto-generates `__init__`, `__repr__`, `__eq__`
  - Field options: `field(default=..., default_factory=..., repr=..., compare=...)`
  - `@dataclass(frozen=True)` — immutable dataclass (hashable)
  - `@dataclass(slots=True)` (Python 3.10+) — use `__slots__` for memory efficiency
  - `@dataclass(kw_only=True)` (Python 3.10+) — keyword-only arguments
  - Post-initialization: `__post_init__(self)`
  - `asdict()`, `astuple()` — conversion utilities
  - Inheritance with dataclasses

#### § 3.4.2 — `__slots__`
  - Restrict attributes to a fixed set: `__slots__ = ('x', 'y')`
  - Memory optimization: no `__dict__` per instance
  - Faster attribute access
  - Prevent dynamic attribute creation
  - Use case: classes with many instances (data-heavy applications)

#### § 3.4.3 — Descriptors
  - The mechanism behind `property`, `classmethod`, `staticmethod`
  - Data descriptor: implements `__get__` and `__set__`
  - Non-data descriptor: implements only `__get__`
  - Descriptor protocol: `__get__`, `__set__`, `__delete__`, `__set_name__`
  - Use case: validation, lazy loading, ORM fields, type checking
  - How `property` works under the hood

#### § 3.4.4 — Metaclasses (Advanced)
  - Classes are objects — `type` is the metaclass of all classes
  - `type(name, bases, namespace)` — dynamic class creation
  - Custom metaclasses: `class Meta(type): ...`
  - `__new__` vs `__init__` in metaclasses
  - Use case: ORMs (Django models), API frameworks, serialization frameworks
  - "Metaclasses are deeper magic than 99% of users should ever worry about" — Tim Peters
  - Modern alternative: `__init_subclass__` hook (Python 3.6+)

#### § 3.4.5 — Protocols (Python 3.8+)
  - `typing.Protocol` — structural subtyping (static duck typing)
  - Define a protocol: class with method signatures
  - Any class with matching methods satisfies the protocol — no inheritance needed
  - `@runtime_checkable` — allow `isinstance()` checks
  - Protocols vs ABCs: protocols are structural (duck typing), ABCs are nominal (explicit inheritance)

---

### 📦 Module 3.5: Enums

#### § 3.5.1 — Enum Fundamentals
  - `from enum import Enum, auto`
  - `class Color(Enum): RED = 1; GREEN = 2; BLUE = 3`
  - `auto()` — auto-assign values
  - Accessing: `Color.RED`, `Color['RED']`, `Color(1)`
  - Iteration: `for color in Color:`
  - `IntEnum` — enum values are integers (can be compared with ints)
  - `StrEnum` (Python 3.11+) — enum values are strings
  - `Flag`, `IntFlag` — bitwise flag enums
  - Enum members are singletons: `Color.RED is Color.RED` → `True`

> ### 🛠️ Phase 3 Project: **"MoneyPy — A Financial Library"**
> Build a financial calculation library demonstrating OOP:
> - `class Money` — represents monetary values with currency
>   - Operator overloading: `+`, `-`, `*`, comparison operators
>   - Prevent cross-currency arithmetic (raise `CurrencyMismatchError`)
>   - `__repr__` and `__str__` for display
>   - Immutable (use `__slots__`, frozen dataclass, or manual immutability)
> - `class Currency(Enum)` — USD, EUR, GBP, JPY with symbols and decimal places
> - `class ExchangeRateProvider(ABC)` — abstract base with `@abstractmethod get_rate(from, to)`
>   - `StaticRateProvider` — hardcoded rates
>   - `FileRateProvider` — read rates from JSON file
> - `class Account` — balance tracking with transaction history
>   - `@property balance`, deposit, withdraw with validation
>   - Transaction log using dataclass
> - `class Portfolio` — composition: holds multiple `Account` objects
>   - Aggregate balance by currency
>   - Custom iteration (`__iter__`)
>   - Pretty printing (`__str__`, `__repr__`)
> - Use descriptors for validated fields (positive amounts, valid currencies)
> - Use `@dataclass(frozen=True)` for immutable value objects
> - Use `Protocol` for any pluggable behavior

---

## ⚡ PHASE 4 — ERROR HANDLING & CONTEXT MANAGERS
> *"EAFP — Easier to Ask Forgiveness than Permission. That's the Python way."*

---

### 📦 Module 4.1: Exception Handling

#### § 4.1.1 — The Exception Hierarchy
  - `BaseException` (root — don't catch this)
    - `SystemExit`, `KeyboardInterrupt`, `GeneratorExit` (never catch normally)
    - `Exception` (catch this and below)
      - `ValueError`, `TypeError`, `KeyError`, `IndexError`, `AttributeError`
      - `RuntimeError`, `NotImplementedError`
      - `OSError` → `FileNotFoundError`, `PermissionError`, `ConnectionError`, `TimeoutError`
      - `StopIteration`, `StopAsyncIteration`
      - `ArithmeticError` → `ZeroDivisionError`, `OverflowError`
      - `LookupError` → `KeyError`, `IndexError`
      - `ImportError` → `ModuleNotFoundError`

#### § 4.1.2 — `try/except/else/finally`
  - `try:` — code that might raise
  - `except ExceptionType as e:` — handle specific exception
  - `except (Type1, Type2) as e:` — handle multiple exception types
  - `except Exception as e:` — catch all "reasonable" exceptions
  - `else:` — runs ONLY if no exception was raised (rarely used but valuable)
  - `finally:` — always runs (cleanup)
  - Bare `except:` — catches everything including `SystemExit`, `KeyboardInterrupt` — NEVER do this

#### § 4.1.3 — Raising Exceptions
  - `raise ValueError("invalid input")`
  - `raise` — re-raise the current exception
  - `raise NewException("msg") from original_exception` — chained exceptions
  - `raise NewException("msg") from None` — suppress exception chain

#### § 4.1.4 — Custom Exceptions
  - Inherit from `Exception` (or more specific subclass)
  - Add custom attributes: error codes, context data
  - Create exception hierarchies for your library/application
  - Keep custom exceptions simple — don't overengineer

#### § 4.1.5 — Exception Groups (Python 3.11+)
  - `ExceptionGroup("msg", [exc1, exc2, exc3])` — multiple simultaneous errors
  - `except*` — handle specific types within a group
  - Use case: concurrent operations (multiple tasks fail simultaneously)

---

### 📦 Module 4.2: Context Managers

#### § 4.2.1 — The `with` Statement
  - `with open("file.txt") as f:` — guaranteed cleanup
  - Protocol: `__enter__` (setup), `__exit__` (cleanup)
  - `__exit__` receives exception info: `(exc_type, exc_val, exc_tb)`
  - Returning `True` from `__exit__` suppresses the exception
  - Multiple context managers: `with open("a") as a, open("b") as b:`
  - Parenthesized context managers (Python 3.10+): multiline `with` statement

#### § 4.2.2 — Creating Context Managers
  - Class-based: implement `__enter__` and `__exit__`
  - Generator-based: `@contextlib.contextmanager` decorator
  - `contextlib.closing` — auto-close objects
  - `contextlib.suppress(ExceptionType)` — suppress specific exceptions
  - `contextlib.redirect_stdout`, `redirect_stderr` — redirect output
  - `contextlib.ExitStack` — dynamic stack of context managers
  - `contextlib.nullcontext` — no-op context manager (useful for conditional context)
  - Async context managers: `__aenter__`, `__aexit__`, `@asynccontextmanager`

#### § 4.2.3 — Context Manager Use Cases
  - File handling: auto-close
  - Database connections: auto-close / auto-commit/rollback
  - Lock management: auto-release
  - Timing blocks: measure execution time
  - Temporary state changes: change directory, modify settings, mock values
  - Transaction management: commit on success, rollback on failure

---

### 📦 Module 4.3: Logging

#### § 4.3.1 — The `logging` Module
  - Levels: `DEBUG`, `INFO`, `WARNING`, `ERROR`, `CRITICAL`
  - `logging.getLogger(__name__)` — logger per module
  - Handlers: `StreamHandler`, `FileHandler`, `RotatingFileHandler`, `TimedRotatingFileHandler`
  - Formatters: custom log line format
  - `logging.basicConfig()` — quick setup
  - `dictConfig()` — production configuration from dict/YAML
  - Never use `print()` for logging in production code
  - Lazy formatting: `logger.info("User %s logged in", username)` (not f-string in log calls)

> ### 🛠️ Phase 4 Project: **"Resilient File Processor"**
> Build a robust file processing application:
> - Process multiple files with comprehensive error handling
> - Custom context managers: `Timer` (measure block time), `TempWorkDir` (change directory, restore on exit), `AtomicWrite` (write to temp file, rename on success)
> - Custom exception hierarchy: `ProcessingError` → `ParseError`, `ValidationError`, `TransformError`
> - Error accumulation: collect all errors from all files, report at the end
> - Use `ExceptionGroup` for concurrent file processing errors
> - Logging setup: file handler + console handler, different formats, log rotation
> - Retry logic with configurable attempts and backoff (using a decorator)
> - Process summary: files processed, succeeded, failed, time taken, errors per file
> - Use `contextlib.ExitStack` for managing variable number of file handles

---

## ⚡ PHASE 5 — MODULES, PACKAGES & PROJECT STRUCTURE
> *"A well-organized Python project is a joy to work with. A poorly organized one is a nightmare."*

---

### 📦 Module 5.1: Modules & Imports

#### § 5.1.1 — Module Fundamentals
  - A module is a `.py` file
  - `import module` — import entire module
  - `from module import name` — import specific names
  - `from module import name as alias` — import with alias
  - `import module as alias` — alias for entire module
  - `from module import *` — import all (NEVER use in production code)
  - `__name__` — `"__main__"` when run directly, module name when imported
  - `if __name__ == "__main__":` — guard for executable scripts

#### § 5.1.2 — Module Search Path
  - Current directory → `PYTHONPATH` → standard library → site-packages
  - `sys.path` — the full search path list
  - `sys.modules` — cache of already-imported modules

#### § 5.1.3 — Import System Internals
  - Finders and loaders
  - `importlib` — programmatic imports
  - `importlib.reload()` — reload a module (rarely needed)
  - Circular imports: causes and solutions
  - Lazy imports for performance

---

### 📦 Module 5.2: Packages

#### § 5.2.1 — Package Fundamentals
  - Package = directory with `__init__.py` (can be empty)
  - `__init__.py` — package initialization, defines public API
  - Subpackages: nested directories
  - Relative imports: `from . import module`, `from ..sibling import name`
  - Absolute imports (preferred): `from mypackage.submodule import func`

#### § 5.2.2 — Namespace Packages (PEP 420)
  - Packages without `__init__.py` (Python 3.3+)
  - Split a package across multiple directories
  - Mostly for plugin systems and very large projects

#### § 5.2.3 — `__all__` — Controlling Public API
  - `__all__ = ["func1", "Class1"]` — defines what `from module import *` exports
  - Best practice: always define `__all__` in `__init__.py`

---

### 📦 Module 5.3: Project Structure

#### § 5.3.1 — Standard Python Project Layout
  - `src/` layout (recommended):
    ```
    project-name/
    ├── src/
    │   └── mypackage/
    │       ├── __init__.py
    │       ├── core.py
    │       └── utils.py
    ├── tests/
    │   ├── __init__.py
    │   ├── test_core.py
    │   └── test_utils.py
    ├── pyproject.toml
    ├── README.md
    └── LICENSE
    ```
  - Flat layout (simpler):
    ```
    project-name/
    ├── mypackage/
    │   ├── __init__.py
    │   └── ...
    ├── tests/
    ├── pyproject.toml
    └── ...
    ```

#### § 5.3.2 — `pyproject.toml` — The Modern Standard
  - Replaces `setup.py`, `setup.cfg`, `requirements.txt` (for library metadata)
  - Build system specification: `[build-system]`
  - Project metadata: `[project]` — name, version, description, dependencies
  - Tool configuration: `[tool.pytest]`, `[tool.ruff]`, `[tool.mypy]`
  - Backend choices: `setuptools`, `hatchling`, `flit-core`, `pdm-backend`

#### § 5.3.3 — Dependency Management Approaches
  - `pip` + `requirements.txt` — simple, widespread
  - `pip-tools` — `requirements.in` → `requirements.txt` (locked)
  - `poetry` — `pyproject.toml` + `poetry.lock`
  - `pdm` — PEP-compliant, modern
  - `uv` — ultra-fast, Rust-based (emerging standard)
  - `pipenv` — older, less popular now
  - Choosing: `uv` for new projects, `poetry` for established projects

> ### 🛠️ Phase 5 Project: **"PyToolkit — A Publishable Python Library"**
> Build a well-structured utility library:
> - Package structure: `src/pytoolkit/` with subpackages: `text/`, `collections/`, `io/`, `decorators/`
> - `__init__.py` with `__all__` defining public API for each subpackage
> - Proper `pyproject.toml` with metadata, dependencies, optional dependencies
> - Entry points: `[project.scripts]` for CLI commands
> - Version management: `__version__` accessible programmatically
> - README with badges, installation instructions, usage examples
> - Build and install locally: `pip install -e .` (editable mode)
> - Build wheel: `python -m build` → `.whl` file
> - Test with `pytest`, configure in `pyproject.toml`

---

## ⚡ PHASE 6 — TYPE HINTS & STATIC ANALYSIS
> *"Python is dynamically typed. Type hints make it optionally statically checked. Best of both worlds."*

---

### 📦 Module 6.1: Type Hints Fundamentals

#### § 6.1.1 — Basic Type Annotations
  - Variable annotations: `name: str = "Alice"`
  - Function annotations: `def greet(name: str) -> str:`
  - No runtime enforcement — type hints are ignored by Python itself
  - Static checkers enforce them: `mypy`, `pyright`, `pytype`

#### § 6.1.2 — Built-in Types as Generic (Python 3.9+)
  - `list[int]`, `dict[str, int]`, `tuple[int, str, float]`, `set[str]`
  - Before 3.9: `from typing import List, Dict, Tuple, Set` (legacy, still works)
  - Variable-length tuples: `tuple[int, ...]`
  - `type[ClassName]` — the class itself, not an instance

#### § 6.1.3 — `Optional`, `Union` & `None`
  - `Optional[str]` = `str | None` (Python 3.10+ pipe syntax)
  - `Union[int, str]` = `int | str` (Python 3.10+ pipe syntax)
  - Prefer pipe syntax in modern Python: `int | str | None`

---

### 📦 Module 6.2: Advanced Type Hints

#### § 6.2.1 — `Any`, `Never`, `NoReturn`
  - `Any` — opt out of type checking (escape hatch)
  - `NoReturn` — function never returns (raises exception or infinite loop)
  - `Never` (Python 3.11+) — bottom type, no possible value

#### § 6.2.2 — Callable Types
  - `Callable[[int, str], bool]` — function taking int and str, returning bool
  - `Callable[..., ReturnType]` — any arguments
  - `ParamSpec` (Python 3.10+) — preserve parameter types in decorators
  - `Concatenate` — add parameters to callable types

#### § 6.2.3 — Generic Types
  - `TypeVar`: `T = TypeVar('T')` — generic type variable
  - `TypeVar` with bounds: `T = TypeVar('T', bound=Comparable)`
  - `TypeVar` with constraints: `T = TypeVar('T', int, float)`
  - Generic classes: `class Box(Generic[T]):` or `class Box[T]:` (Python 3.12+)
  - Generic functions: `def first(items: list[T]) -> T:`
  - New syntax (Python 3.12+): `def first[T](items: list[T]) -> T:`

#### § 6.2.4 — `TypeAlias` & `type` Statement
  - `Vector: TypeAlias = list[float]` (Python 3.10+)
  - `type Vector = list[float]` (Python 3.12+, preferred)
  - Complex type aliases for readability

#### § 6.2.5 — `Literal`, `Final`, `TypeGuard`
  - `Literal["read", "write"]` — restrict to specific values
  - `Final` — variable cannot be reassigned: `MAX: Final = 100`
  - `TypeGuard` (Python 3.10+) — narrow types in conditional checks
  - `TypeIs` (Python 3.13+) — improved type narrowing

#### § 6.2.6 — `TypedDict`
  - `class Config(TypedDict): host: str; port: int; debug: bool`
  - Type-safe dictionaries with known keys
  - `total=False` — all keys optional
  - `Required` and `NotRequired` (Python 3.11+) — per-key optionality
  - Use case: JSON/API response typing

#### § 6.2.7 — `Protocol` (Structural Subtyping)
  - Define expected interface without inheritance
  - `@runtime_checkable` for `isinstance()` support
  - Protocols vs ABCs: structural vs nominal typing
  - Use case: duck typing with type safety

---

### 📦 Module 6.3: Static Analysis Tools

#### § 6.3.1 — `mypy` — Static Type Checker
  - `mypy --strict source.py` — strictest checking
  - Configuration in `pyproject.toml`: `[tool.mypy]`
  - `# type: ignore` — suppress specific errors
  - `reveal_type(expr)` — debug type inference
  - Stub files (`.pyi`) for untyped libraries
  - `typeshed` — type stubs for the standard library

#### § 6.3.2 — `pyright` / `pylance`
  - Microsoft's type checker (faster than mypy)
  - Powers VS Code's Python extension (Pylance)
  - Stricter by default than mypy
  - `pyrightconfig.json` or `pyproject.toml` configuration

#### § 6.3.3 — `ruff` — Linter & Formatter
  - Replaces: `flake8`, `isort`, `pyflakes`, `pycodestyle`, `black` (formatter mode)
  - Written in Rust — 10-100x faster than Python linters
  - `ruff check .` — lint, `ruff format .` — format
  - Configuration in `pyproject.toml`: `[tool.ruff]`
  - Rules: hundreds of rules from multiple linter ecosystems
  - Auto-fix: `ruff check --fix .`

> ### 🛠️ Phase 6 Project: **"TypeSafe Collections Library"**
> Build a fully type-annotated generic collections library:
> - `class Stack[T]` — generic stack with push, pop, peek, is_empty (Python 3.12+ syntax)
> - `class Queue[T]` — generic queue with enqueue, dequeue, peek
> - `class Result[T, E]` — Ok/Err type (like Rust), with map, flat_map, unwrap_or
> - `class Optional[T]` — Some/None with map, filter, or_else (don't shadow built-in Optional)
> - `TypedDict` for configuration structures
> - `Protocol` for pluggable behaviors (comparable, serializable, printable)
> - 100% type coverage — zero `mypy --strict` errors
> - `ruff` compliant with zero warnings
> - All public functions/methods have docstrings and type annotations

---

## ⚡ PHASE 7 — CONCURRENCY & PARALLELISM
> *"Python has four concurrency models. Knowing when to use each is the real skill."*

---

### 📦 Module 7.1: Understanding the GIL

#### § 7.1.1 — What is the GIL (Global Interpreter Lock)
  - Only one thread executes Python bytecode at a time (in CPython)
  - Protects CPython's reference counting garbage collection
  - Threads still useful for I/O-bound work (GIL is released during I/O)
  - GIL does NOT affect multiprocessing
  - GIL-free Python (Python 3.13+ experimental): `--disable-gil` / free-threaded build

#### § 7.1.2 — Concurrency vs Parallelism
  - **Concurrency**: dealing with many things at once (structure)
  - **Parallelism**: doing many things at once (execution)
  - I/O-bound tasks → threading or asyncio
  - CPU-bound tasks → multiprocessing
  - Decision matrix: choosing the right model

---

### 📦 Module 7.2: Threading (`threading` Module)

#### § 7.2.1 — Thread Fundamentals
  - `threading.Thread(target=func, args=(...))` — create a thread
  - `thread.start()`, `thread.join(timeout)`
  - `thread.is_alive()`, `thread.daemon`
  - Daemon threads: die when main thread exits
  - Thread naming for debugging: `thread.name`
  - `threading.current_thread()`, `threading.active_count()`

#### § 7.2.2 — Synchronization Primitives
  - `threading.Lock` — mutual exclusion: `acquire()`, `release()`, `with lock:`
  - `threading.RLock` — reentrant lock (same thread can acquire multiple times)
  - `threading.Semaphore(n)` — limit concurrent access
  - `threading.Event` — signal between threads: `set()`, `wait()`, `clear()`
  - `threading.Condition` — wait/notify pattern
  - `threading.Barrier(n)` — wait for N threads

#### § 7.2.3 — Thread-Safe Data Structures
  - `queue.Queue` — thread-safe FIFO queue
  - `queue.LifoQueue` — thread-safe stack
  - `queue.PriorityQueue` — thread-safe priority queue
  - Producer-consumer pattern with `Queue`
  - `queue.SimpleQueue` — faster, simpler thread-safe queue

#### § 7.2.4 — `concurrent.futures.ThreadPoolExecutor`
  - `ThreadPoolExecutor(max_workers=n)` — managed thread pool
  - `executor.submit(func, args)` → `Future` object
  - `executor.map(func, iterable)` — parallel map
  - `future.result(timeout)`, `future.done()`, `future.cancel()`
  - `as_completed(futures)` — process results as they finish
  - Context manager: `with ThreadPoolExecutor() as executor:`
  - When to use: I/O-bound work (HTTP requests, file I/O, database queries)

---

### 📦 Module 7.3: Multiprocessing (`multiprocessing` Module)

#### § 7.3.1 — Process Fundamentals
  - `multiprocessing.Process(target=func, args=(...))` — create a process
  - Each process has its own Python interpreter and memory space
  - No GIL limitation — true parallelism for CPU-bound work
  - `process.start()`, `process.join()`, `process.terminate()`

#### § 7.3.2 — Inter-Process Communication
  - `multiprocessing.Queue` — process-safe queue
  - `multiprocessing.Pipe` — bidirectional communication
  - `multiprocessing.Value`, `multiprocessing.Array` — shared memory
  - `multiprocessing.Manager` — managed shared objects (dicts, lists, etc.)

#### § 7.3.3 — `concurrent.futures.ProcessPoolExecutor`
  - `ProcessPoolExecutor(max_workers=n)` — managed process pool
  - Same API as `ThreadPoolExecutor` — easy to switch between them
  - `executor.submit()`, `executor.map()`
  - When to use: CPU-bound work (number crunching, image processing, data transformation)
  - Overhead: process creation and IPC is slower than threading

#### § 7.3.4 — Shared Memory (Python 3.8+)
  - `multiprocessing.shared_memory.SharedMemory` — named shared memory segments
  - Zero-copy data sharing between processes
  - Use case: large numpy arrays, buffers

---

### 📦 Module 7.4: Asynchronous Programming (`asyncio`)

#### § 7.4.1 — Async/Await Fundamentals
  - `async def` — defines a coroutine function
  - `await` — suspend coroutine until result is available
  - `asyncio.run(main())` — run the event loop
  - Coroutine objects: calling `async def` returns a coroutine (must be awaited)
  - Event loop: single-threaded concurrency manager

#### § 7.4.2 — Core asyncio Functions
  - `asyncio.gather(*coros)` — run coroutines concurrently, wait for all
  - `asyncio.create_task(coro)` — schedule coroutine as a task
  - `asyncio.wait()` — more control over multiple tasks
  - `asyncio.sleep(seconds)` — async sleep (don't use `time.sleep`!)
  - `asyncio.wait_for(coro, timeout)` — timeout for coroutine
  - `asyncio.shield(coro)` — protect from cancellation
  - `asyncio.to_thread(func, args)` (Python 3.9+) — run sync function in thread
  - `asyncio.TaskGroup` (Python 3.11+) — structured concurrency

#### § 7.4.3 — Async Iterators & Generators
  - `async for item in async_iterable:` — async iteration
  - `async with resource:` — async context manager
  - `async def gen(): yield value` — async generator
  - `aiter()`, `anext()` (Python 3.10+)

#### § 7.4.4 — Async Patterns
  - Semaphore for rate limiting: `asyncio.Semaphore(n)`
  - `asyncio.Queue` — async producer-consumer
  - `asyncio.Lock`, `asyncio.Event`, `asyncio.Condition`
  - Cancellation: `task.cancel()`, handling `CancelledError`
  - Error handling in tasks: unhandled exceptions in tasks

#### § 7.4.5 — Async Libraries
  - `aiohttp` — async HTTP client/server
  - `httpx` — async-capable HTTP client (requests replacement)
  - `aiofiles` — async file I/O
  - `asyncpg` — async PostgreSQL driver
  - `motor` — async MongoDB driver
  - `aiomysql` — async MySQL driver

#### § 7.4.6 — When to Use asyncio
  - High-concurrency I/O: thousands of simultaneous connections
  - Web scraping, API calls, WebSocket servers
  - When NOT to use: CPU-bound work, simple scripts, few concurrent operations
  - Async all the way: once async, everything in the call chain must be async (the "colored function" problem)

---

### 📦 Module 7.5: `subprocess` — Running External Commands

#### § 7.5.1 — Running Commands
  - `subprocess.run(["cmd", "arg1"], capture_output=True, text=True)` — run and wait
  - `subprocess.Popen` — low-level, non-blocking
  - Capturing output: `result.stdout`, `result.stderr`
  - Return code: `result.returncode`
  - `check=True` — raise `CalledProcessError` on non-zero exit
  - Security: NEVER use `shell=True` with user input
  - Piping: connect stdout of one command to stdin of another

> ### 🛠️ Phase 7 Project: **"AsyncScraper — A Concurrent Web Content Aggregator"**
> Build a web content aggregator using all concurrency models:
> - **Version 1 (Threading)**: `ThreadPoolExecutor` to fetch N URLs concurrently
> - **Version 2 (Asyncio)**: `aiohttp` + `asyncio.gather` for async fetching
> - **Version 3 (Multiprocessing)**: `ProcessPoolExecutor` for CPU-bound HTML parsing
> - **Combined**: async fetch → process pool parse → thread pool save to DB
> - Features:
>   - Configurable concurrency limits (semaphore)
>   - Rate limiting per domain
>   - Retry with exponential backoff on failures
>   - Graceful cancellation on Ctrl+C
>   - Progress reporting
>   - Error collection and summary report
> - Benchmarks: compare sequential, threaded, async, and multiprocessing approaches
>   - Measure: total time, memory usage, CPU usage
>   - Document results in a table

---

## ⚡ PHASE 8 — FILE I/O, DATA FORMATS & DATABASES
> *"Data in, data out — the essence of most real-world programs."*

---

### 📦 Module 8.1: File I/O

#### § 8.1.1 — Reading & Writing Files
  - `open(path, mode, encoding)` — always specify encoding (`encoding="utf-8"`)
  - Modes: `r`, `w`, `a`, `x` (exclusive create), `b` (binary), `+` (read/write)
  - Always use `with` statement for file handling
  - `f.read()`, `f.readline()`, `f.readlines()`, `f.write()`, `f.writelines()`
  - Iterating: `for line in file:` — memory efficient line-by-line

#### § 8.1.2 — `pathlib` — Modern Path Handling
  - `from pathlib import Path`
  - `Path("dir") / "subdir" / "file.txt"` — path composition
  - `path.exists()`, `path.is_file()`, `path.is_dir()`
  - `path.read_text()`, `path.write_text()` — one-liner read/write
  - `path.read_bytes()`, `path.write_bytes()`
  - `path.mkdir(parents=True, exist_ok=True)`
  - `path.rename()`, `path.unlink()`, `path.rmdir()`
  - `path.glob("*.py")`, `path.rglob("**/*.py")` — pattern matching
  - `path.stem`, `path.suffix`, `path.parent`, `path.name`
  - `Path.home()`, `Path.cwd()`
  - Prefer `pathlib` over `os.path` for all new code

#### § 8.1.3 — Temporary Files & Directories
  - `tempfile.NamedTemporaryFile()`, `tempfile.TemporaryDirectory()`
  - Auto-cleanup as context managers

---

### 📦 Module 8.2: Data Formats

#### § 8.2.1 — JSON
  - `json.dumps(obj)` — Python object → JSON string
  - `json.loads(string)` — JSON string → Python object
  - `json.dump(obj, file)`, `json.load(file)` — file-based
  - Custom serialization: `default` parameter, `json.JSONEncoder` subclass
  - Custom deserialization: `object_hook` parameter
  - `orjson` — fastest JSON library for Python (10x+ faster)
  - `pydantic` for JSON validation and parsing (covered later)

#### § 8.2.2 — CSV
  - `csv.reader`, `csv.writer` — basic row-based
  - `csv.DictReader`, `csv.DictWriter` — dictionary-based (preferred)
  - Handling: quoting, delimiters, line terminators, encoding

#### § 8.2.3 — TOML
  - `tomllib` (Python 3.11+, read-only, built-in)
  - `tomli_w` — TOML writing
  - `pyproject.toml` uses TOML format

#### § 8.2.4 — YAML
  - `pyyaml` — `yaml.safe_load()`, `yaml.safe_dump()`
  - NEVER use `yaml.load()` without `Loader=SafeLoader` (security risk!)

#### § 8.2.5 — Other Formats
  - XML: `xml.etree.ElementTree` (built-in), `lxml` (fast, full-featured)
  - INI: `configparser` (built-in)
  - MessagePack: `msgpack` — binary, faster than JSON
  - Protocol Buffers: `protobuf` — schema-driven binary serialization
  - Pickle: `pickle` — Python-specific serialization (NEVER unpickle untrusted data!)

---

### 📦 Module 8.3: Database Access

#### § 8.3.1 — SQLite (Built-in)
  - `sqlite3` module — zero-configuration database
  - Connection, cursor, execute, fetchall/fetchone
  - Parameterized queries: `cursor.execute("SELECT * FROM users WHERE id = ?", (user_id,))`
  - Context manager for auto-commit/rollback
  - Use case: prototyping, small applications, embedded databases, testing

#### § 8.3.2 — PostgreSQL & MySQL
  - `psycopg` (v3) — PostgreSQL adapter (async support)
  - `asyncpg` — high-performance async PostgreSQL
  - `pymysql` — MySQL adapter
  - `aiomysql` — async MySQL
  - Connection pooling

#### § 8.3.3 — SQLAlchemy — The Standard ORM
  - **Core**: SQL expression language (programmatic SQL)
  - **ORM**: Object-Relational Mapping (Python classes ↔ database tables)
  - SQLAlchemy 2.0 style (modern): declarative models, type-annotated
  - `Mapped`, `mapped_column`, `relationship`
  - Session management: `Session`, `sessionmaker`
  - Querying: `select()`, `where()`, `join()`, `order_by()`, `group_by()`
  - Transactions, eager/lazy loading, migrations
  - Async support: `AsyncSession`, `create_async_engine`

#### § 8.3.4 — Database Migrations
  - `Alembic` — SQLAlchemy's migration tool
  - `alembic init`, `alembic revision --autogenerate`, `alembic upgrade head`
  - Migration versioning and management

#### § 8.3.5 — NoSQL
  - `pymongo` — MongoDB driver
  - `motor` — async MongoDB
  - `redis-py` — Redis driver
  - `aioredis` — async Redis

---

### 📦 Module 8.4: Data Validation (Pydantic)

#### § 8.4.1 — Pydantic Fundamentals
  - `BaseModel` — data validation and serialization
  - Automatic type coercion and validation
  - `model_validate()`, `model_dump()`, `model_dump_json()`
  - Field validators: `@field_validator`, `@model_validator`
  - `Field()` — metadata, default values, constraints
  - Nested models, lists of models
  - Pydantic settings: `BaseSettings` for configuration from environment variables
  - JSON Schema generation: `model_json_schema()`
  - Use case: API request/response validation, configuration, data parsing

> ### 🛠️ Phase 8 Project: **"DataVault — A Multi-Format Data Manager"**
> Build a data management application:
> - Import data from: CSV, JSON, TOML, SQLite, PostgreSQL
> - Export data to: CSV, JSON, Excel (openpyxl), SQLite
> - Pydantic models for data validation on import
> - SQLAlchemy ORM for persistent storage
> - Alembic migrations for schema changes
> - Operations: filter, sort, aggregate, join datasets, deduplicate
> - Async database operations for large imports
> - `pathlib` for all file operations
> - CLI interface with subcommands: `import`, `export`, `query`, `migrate`
> - Comprehensive error handling for malformed data
> - Transaction support: import all-or-nothing

---

## ⚡ PHASE 9 — TESTING, TOOLING & CODE QUALITY
> *"Untested Python code is broken Python code. You just don't know it yet."*

---

### 📦 Module 9.1: Testing with `pytest`

#### § 9.1.1 — pytest Fundamentals
  - Test functions: `def test_something():` — pytest discovers them automatically
  - Assertions: plain `assert` statements (pytest rewrites them for clear output)
  - Running: `pytest`, `pytest -v` (verbose), `pytest -k "test_name"` (filter)
  - Test discovery: files named `test_*.py`, functions named `test_*`
  - `pytest.raises(ExceptionType)` — assert exceptions
  - `pytest.approx(value)` — floating point comparison

#### § 9.1.2 — Fixtures
  - `@pytest.fixture` — setup/teardown for tests
  - Fixture scopes: `function` (default), `class`, `module`, `session`
  - `yield` fixtures: setup before yield, teardown after
  - `conftest.py` — shared fixtures across test files
  - Built-in fixtures: `tmp_path`, `capsys`, `monkeypatch`, `caplog`
  - Fixture parameterization
  - Fixture composition: fixtures using other fixtures

#### § 9.1.3 — Parameterized Tests
  - `@pytest.mark.parametrize("input,expected", [(1, 2), (2, 4)])` — multiple test cases
  - Multiple parameterize decorators: cartesian product
  - Parameterize with fixture: `@pytest.fixture(params=[...])`
  - IDs for readable test names: `pytest.param(value, id="name")`

#### § 9.1.4 — Markers & Configuration
  - `@pytest.mark.skip`, `@pytest.mark.skipif(condition)`
  - `@pytest.mark.xfail` — expected failure
  - `@pytest.mark.slow` — custom markers for selective running
  - `pytest.ini` / `pyproject.toml` — configuration: `[tool.pytest.ini_options]`
  - Plugins: `pytest-cov`, `pytest-asyncio`, `pytest-mock`, `pytest-xdist`, `pytest-benchmark`

---

### 📦 Module 9.2: Mocking

#### § 9.2.1 — `unittest.mock`
  - `Mock`, `MagicMock` — mock objects with auto-created attributes
  - `patch()` — replace objects during tests
  - `@patch("module.ClassName")` — decorator form
  - `with patch("module.func") as mock_func:` — context manager form
  - `mock.return_value`, `mock.side_effect`
  - `mock.assert_called_once_with(args)`
  - `mock.call_count`, `mock.call_args_list`
  - `PropertyMock` — mock properties
  - `patch.object()` — patch on specific objects

#### § 9.2.2 — `pytest-mock`
  - `mocker` fixture — cleaner interface to `unittest.mock`
  - `mocker.patch()`, `mocker.spy()`
  - Auto-cleanup of patches

#### § 9.2.3 — Mocking Best Practices
  - Mock at the boundary, not everywhere
  - Mock I/O, external services, time, randomness
  - Don't mock what you own — test the real code
  - Prefer dependency injection over patching

---

### 📦 Module 9.3: Advanced Testing

#### § 9.3.1 — Code Coverage
  - `pytest-cov` plugin: `pytest --cov=mypackage --cov-report=html`
  - Coverage reports: terminal, HTML, XML (for CI)
  - Branch coverage: `--cov-branch`
  - Coverage configuration in `pyproject.toml`
  - 80%+ coverage is a reasonable target, 100% is often counterproductive

#### § 9.3.2 — Property-Based Testing
  - `hypothesis` library — generates random test inputs
  - `@given(st.integers(), st.text())` — strategies for input generation
  - Finds edge cases you wouldn't think of
  - Shrinking: automatically finds the minimal failing input
  - Use case: parsers, serializers, data structures, algorithms

#### § 9.3.3 — Integration & End-to-End Testing
  - `testcontainers-python` — spin up real databases in Docker for tests
  - `httpx` / `requests-mock` for API testing
  - `pytest-asyncio` — testing async code
  - Factory pattern for test data: `factory_boy`, `faker`

#### § 9.3.4 — Benchmarking
  - `pytest-benchmark` — performance testing
  - `timeit` module — quick microbenchmarks
  - `memory_profiler` — memory usage testing
  - `py-spy` — sampling profiler

---

### 📦 Module 9.4: Code Quality Tools

#### § 9.4.1 — Linting & Formatting
  - `ruff` — fastest linter + formatter (the modern standard)
  - `ruff check .` — lint, `ruff format .` — format
  - `ruff` replaces: `flake8`, `isort`, `pyflakes`, `pycodestyle`, `pydocstyle`, `black`
  - Configuration in `pyproject.toml`

#### § 9.4.2 — Type Checking
  - `mypy --strict` — comprehensive type checking
  - `pyright` — faster alternative (Microsoft)
  - Gradual typing: start with `--warn-return-any`, increase strictness

#### § 9.4.3 — Security Scanning
  - `bandit` — security-focused static analysis
  - `safety` — check dependencies for known vulnerabilities
  - `pip-audit` — audit installed packages
  - `ruff` has some security rules built in

#### § 9.4.4 — Pre-commit Hooks
  - `pre-commit` framework — run checks before every commit
  - `.pre-commit-config.yaml` — configure hooks
  - Common hooks: ruff, mypy, pytest, trailing whitespace, end-of-file fixer
  - `pre-commit install`, `pre-commit run --all-files`

> ### 🛠️ Phase 9 Project: **"TestMaster — A Testing Framework Showcase"**
> Take ANY previous project and add comprehensive testing:
> - Unit tests with `pytest` for all functions and methods
> - Table-driven parameterized tests for algorithmic logic
> - Fixtures for database, file system, and HTTP mocking
> - `hypothesis` property-based tests for parsers/validators
> - Integration tests with `testcontainers` for database operations
> - Mock all external dependencies
> - Coverage report: 90%+ line coverage, 80%+ branch coverage
> - `pytest-benchmark` for performance-critical functions
> - CI pipeline config (GitHub Actions): lint (ruff), type check (mypy), test (pytest), coverage
> - Pre-commit hooks: ruff, mypy, pytest (fast subset)
> - All configured in `pyproject.toml` — zero config files

---

## ⚡ PHASE 10 — DESIGN PATTERNS & ARCHITECTURE
> *"Python doesn't need as many patterns as Java. But the ones it needs, it needs deeply."*

---

### 📦 Module 10.1: Pythonic Design Principles

#### § 10.1.1 — SOLID in Python
  - SRP: small modules, focused classes, single-purpose functions
  - OCP: duck typing and protocols enable extension without modification
  - LSP: subtypes must honor the base type's contract
  - ISP: small protocols and ABCs, not monolithic interfaces
  - DIP: depend on abstractions (protocols, ABCs), not concrete classes
  - Python's dynamic nature makes SOLID less ceremonial than Java

#### § 10.1.2 — Python-Specific Principles
  - EAFP vs LBYL — "Easier to Ask Forgiveness than Permission"
  - Duck typing: "If it quacks like a duck..."
  - "We're all consenting adults" — convention over enforcement
  - "Flat is better than nested"
  - "Simple is better than complex"
  - Composition over inheritance (even more than Java — Python uses mixins sparingly)
  - Functions are objects — many patterns become trivial

---

### 📦 Module 10.2: Creational Patterns

#### § 10.2.1 — Singleton Pattern
  - Module-level variable — Python modules are singletons naturally
  - `__new__` method override
  - Metaclass-based singleton
  - Why modules-as-singletons is the Pythonic approach
  - Usually an anti-pattern — prefer dependency injection

#### § 10.2.2 — Factory Pattern
  - Factory function: plain function returning objects
  - Class method factories: `@classmethod` alternative constructors
  - Registry pattern: dict mapping keys to constructor callables
  - `__init_subclass__` for auto-registration

#### § 10.2.3 — Builder Pattern
  - Method chaining with `return self`
  - `dataclass` with `@dataclass` replacing most builder needs
  - `attrs` library for complex building
  - Rarely needed in Python — keyword arguments serve the same purpose

#### § 10.2.4 — Prototype Pattern
  - `copy.copy()` — shallow copy
  - `copy.deepcopy()` — deep copy
  - `__copy__` and `__deepcopy__` dunder methods for custom behavior

---

### 📦 Module 10.3: Structural Patterns

#### § 10.3.1 — Decorator Pattern (Not Python Decorators)
  - Wrapping objects to add behavior
  - Python's `functools.wraps` and decorator syntax make this trivial
  - Function decorators are the Pythonic version
  - Class-based decorators for stateful wrapping

#### § 10.3.2 — Adapter Pattern
  - Wrapper class converting one interface to another
  - Often just a function or a thin class
  - `__getattr__` delegation for transparent proxying

#### § 10.3.3 — Facade Pattern
  - Simplified interface to complex subsystems
  - Module-level functions as a facade for complex class hierarchies
  - `__init__.py` as a facade for package internals

#### § 10.3.4 — Proxy Pattern
  - Lazy loading, caching, access control
  - `__getattr__` for transparent delegation
  - `functools.cached_property` — lazy computed property
  - Descriptors for proxy behavior

#### § 10.3.5 — Composite Pattern
  - Tree structures with uniform interface
  - Using duck typing — objects just need compatible methods

---

### 📦 Module 10.4: Behavioral Patterns

#### § 10.4.1 — Strategy Pattern
  - In Python: just pass a function (or callable)
  - `sorted(key=strategy_func)` — strategy as a parameter
  - Protocol or ABC for complex strategies
  - First-class functions make strategy trivial in Python

#### § 10.4.2 — Observer Pattern
  - Callback-based: list of functions to call on events
  - Signal libraries: `blinker`
  - Custom event system with decorators
  - `asyncio` event handling for async observers

#### § 10.4.3 — Command Pattern
  - Callables as commands (functions, lambdas, classes with `__call__`)
  - Command queue for undo/redo
  - Python's first-class functions reduce command pattern to simple callables

#### § 10.4.4 — Iterator Pattern
  - Built into Python: `__iter__`, `__next__`, generators
  - `itertools` for complex iteration
  - Range-based iteration, generator expressions

#### § 10.4.5 — State Machine Pattern
  - Enum-based states with transition table (dict)
  - Class-based states with polymorphic behavior
  - `transitions` library for complex state machines
  - Dataclass + enum for simple state machines

#### § 10.4.6 — Template Method Pattern
  - Abstract base class with concrete and abstract methods
  - Alternative: pass strategy functions (more Pythonic)

#### § 10.4.7 — Chain of Responsibility
  - Middleware pattern: list of handlers processed in order
  - Each handler decides to process or pass
  - Common in web frameworks: ASGI/WSGI middleware

---

### 📦 Module 10.5: Architectural Patterns

#### § 10.5.1 — Repository Pattern
  - Abstract data access behind a clean interface
  - Protocol or ABC defining data operations
  - Concrete implementations for different backends (SQL, file, memory)
  - Enables testing with in-memory repositories

#### § 10.5.2 — Service Layer Pattern
  - Business logic separated from presentation and data access
  - Service classes coordinate between repositories and domain objects
  - Use case-driven architecture

#### § 10.5.3 — Dependency Injection in Python
  - Constructor injection: pass dependencies as parameters
  - No framework needed — Python's dynamic nature makes DI simple
  - DI containers: `dependency-injector`, `injector` (when complexity warrants it)
  - Protocols for defining injectable interfaces

#### § 10.5.4 — Clean Architecture / Hexagonal Architecture
  - Domain layer: entities, value objects, business rules (no external dependencies)
  - Application layer: use cases, service interfaces
  - Infrastructure layer: database, HTTP, file system implementations
  - Ports and adapters: interfaces at boundaries
  - Dependency rule: inner layers don't know about outer layers

---

### 📦 Module 10.6: Anti-Patterns to Avoid

#### § 10.6.1 — Python-Specific Anti-Patterns
  - God module / God class — too many responsibilities
  - Mutable default arguments — `def func(lst=[])` bug
  - Bare `except:` — catches everything including `SystemExit`
  - `from module import *` — namespace pollution
  - Circular imports — redesign your modules
  - Over-engineering: applying Java patterns to Python (unnecessary factories, managers, handlers)
  - Premature abstraction: creating ABCs and protocols when a simple function would work
  - Ignoring built-in types: writing a custom class when a dict/namedtuple/dataclass would suffice

> ### 🛠️ Phase 10 Project: **"EventBroker — A Pattern-Driven Event Processing System"**
> Build an event processing system demonstrating Pythonic patterns:
> 
> **Creational:**
> - Factory functions for creating events from different sources (JSON, dict, Protobuf)
> - Module-level singleton for the event broker registry
> - Prototype pattern for event templates (copy and customize)
>
> **Structural:**
> - Decorator (Python-style) for middleware: logging, timing, validation, enrichment
> - Facade for a simplified publish/subscribe API hiding internal complexity
> - Adapter for integrating different message sources (file, HTTP webhook, queue)
>
> **Behavioral:**
> - Strategy for routing events (round-robin, content-based, priority)
> - Observer for event subscribers (callback-based, async-capable)
> - State machine for event lifecycle (received → validated → processing → completed/failed)
> - Chain of responsibility for event validation pipeline
> - Command pattern for undoable event operations
>
> **Architecture:**
> - Clean layering: API → Service → Repository (all connected via Protocols)
> - Dependency injection via constructor parameters
> - Pydantic models for event validation
> - Type annotations throughout, zero mypy errors
> - 90%+ test coverage with pytest

---

## ⚡ PHASE 11 — WEB DEVELOPMENT
> *"Python powers millions of web applications — from Instagram to Spotify to Pinterest."*

---

### 📦 Module 11.1: Web Fundamentals for Python

#### § 11.1.1 — WSGI & ASGI
  - WSGI (Web Server Gateway Interface) — synchronous standard
  - ASGI (Asynchronous Server Gateway Interface) — async standard
  - How web frameworks interface with web servers
  - ASGI is the future — supports HTTP, WebSocket, background tasks

---

### 📦 Module 11.2: FastAPI (Modern, Async)

#### § 11.2.1 — FastAPI Fundamentals
  - `app = FastAPI()` — application instance
  - Route decorators: `@app.get("/")`, `@app.post("/items")`
  - Path parameters: `@app.get("/items/{item_id}")`
  - Query parameters: automatic from function signature
  - Request body: Pydantic models — auto-validation, auto-documentation
  - Response models: `response_model=ItemResponse` — filter output fields
  - Status codes: `status_code=201`

#### § 11.2.2 — Dependency Injection in FastAPI
  - `Depends(func)` — dependency injection system
  - Database session injection
  - Authentication dependency
  - Nested dependencies
  - Scoped dependencies: per-request, per-app

#### § 11.2.3 — Request Validation & Serialization
  - Pydantic models for request bodies
  - `Query()`, `Path()`, `Header()`, `Cookie()` — parameter validation
  - `Field()` — field-level constraints
  - Custom validators
  - Nested model validation

#### § 11.2.4 — Authentication & Security
  - OAuth2 with password flow
  - JWT token authentication
  - API key authentication
  - `HTTPBearer`, `HTTPBasic` security schemes
  - Middleware for CORS, trusted hosts

#### § 11.2.5 — Database Integration
  - SQLAlchemy async with FastAPI
  - Dependency for database sessions
  - Alembic migrations
  - Repository pattern with FastAPI

#### § 11.2.6 — Advanced FastAPI
  - Background tasks: `BackgroundTasks`
  - WebSocket support
  - Middleware: custom middleware, CORS
  - Event handlers: `on_startup`, `on_shutdown`, lifespan
  - File upload/download
  - Streaming responses
  - Sub-applications and routers: `APIRouter`
  - Auto-generated OpenAPI docs: `/docs` (Swagger), `/redoc`

---

### 📦 Module 11.3: Django (Batteries-Included)

#### § 11.3.1 — Django Fundamentals
  - `django-admin startproject`, `manage.py startapp`
  - MTV pattern: Model, Template, View
  - Settings, URL configuration, WSGI/ASGI
  - Django ORM: models, migrations, queries
  - Admin interface: auto-generated CRUD admin

#### § 11.3.2 — Django ORM
  - Model definition: `class User(models.Model):`
  - Fields: `CharField`, `IntegerField`, `ForeignKey`, `ManyToManyField`
  - QuerySet API: `filter()`, `exclude()`, `order_by()`, `annotate()`, `aggregate()`
  - Managers: custom queryset methods
  - Migrations: `makemigrations`, `migrate`
  - N+1 query problem: `select_related()`, `prefetch_related()`

#### § 11.3.3 — Django REST Framework (DRF)
  - Serializers: model ↔ JSON conversion with validation
  - ViewSets and Routers: CRUD in minimal code
  - Permissions: `IsAuthenticated`, `IsAdminUser`, custom
  - Pagination, filtering, searching, ordering
  - Authentication: Token, JWT, Session
  - Throttling / rate limiting

#### § 11.3.4 — Django Ecosystem
  - `django-allauth` — authentication (social login, email verification)
  - `django-cors-headers` — CORS
  - `django-filter` — advanced filtering
  - `celery` — async task queue (with Django integration)
  - `channels` — WebSocket and async support for Django
  - Django vs FastAPI: when to use which

---

### 📦 Module 11.4: Flask (Minimalist)

#### § 11.4.1 — Flask Fundamentals (Overview)
  - Micro-framework: minimal core, add what you need
  - Routing, templates (Jinja2), request/response
  - Extensions: Flask-SQLAlchemy, Flask-Login, Flask-RESTful
  - When Flask: simple applications, prototypes, microservices
  - Flask vs FastAPI: Flask is sync-first, FastAPI is async-first with auto-docs

---

### 📦 Module 11.5: API Design & Best Practices

#### § 11.5.1 — REST API Design
  - Resource naming, HTTP methods, status codes
  - Pagination: cursor-based vs offset-based
  - Filtering, sorting, field selection
  - Versioning: URL path, header, query parameter
  - HATEOAS overview
  - Error response format: RFC 7807 Problem Details

#### § 11.5.2 — GraphQL with Python
  - `strawberry` — modern Python GraphQL library (type-safe, dataclass-based)
  - `graphene` — older, more established
  - Schema definition, queries, mutations, subscriptions
  - When GraphQL vs REST

#### § 11.5.3 — API Documentation
  - OpenAPI / Swagger — auto-generated by FastAPI
  - DRF generates OpenAPI via `drf-spectacular`
  - Writing API documentation as code

> ### 🛠️ Phase 11 Project: **"TaskForge API — A Production REST Backend"**
> Build a complete task management API:
> - **Framework**: FastAPI (primary) + optional Django implementation for comparison
> - **Stack**: FastAPI + SQLAlchemy (async) + PostgreSQL + Pydantic + JWT auth
> - **Entities**: User, Workspace, Project, Task, Comment, Label (with relationships)
> - **Features**:
>   - User registration, login, JWT refresh tokens
>   - CRUD for all entities with proper authorization (workspace members only)
>   - Task assignment, status transitions, due dates, priority
>   - Filtering, sorting, pagination (cursor-based)
>   - File attachments (upload/download)
>   - WebSocket notifications for task updates
>   - Background tasks: send email notifications, generate reports
>   - Rate limiting middleware
> - **Architecture**:
>   - Clean layering: Router → Service → Repository (Protocols at boundaries)
>   - Pydantic models for all request/response schemas
>   - Alembic database migrations
>   - Dependency injection for database sessions, auth, config
> - **Quality**:
>   - pytest with async fixtures
>   - `testcontainers` for PostgreSQL integration tests
>   - 85%+ coverage
>   - `mypy --strict` clean
>   - `ruff` clean
>   - Auto-generated OpenAPI docs

---

## ⚡ PHASE 12 — DATA SCIENCE, AUTOMATION & SPECIALTY DOMAINS
> *"Python isn't just a language. It's a gateway to every domain in computing."*

---

### 📦 Module 12.1: Data Science & Analysis

#### § 12.1.1 — NumPy
  - `ndarray` — N-dimensional array (the foundation of scientific Python)
  - Array creation: `np.array`, `np.zeros`, `np.ones`, `np.arange`, `np.linspace`
  - Vectorized operations: element-wise math without loops
  - Indexing, slicing, boolean indexing, fancy indexing
  - Broadcasting: operations on arrays of different shapes
  - Linear algebra: `np.dot`, `np.linalg.solve`, `np.linalg.eig`
  - Random: `np.random.default_rng()`
  - Performance: 10-100x faster than Python lists for numerical operations

#### § 12.1.2 — Pandas
  - `DataFrame` and `Series` — the core data structures
  - Reading data: `pd.read_csv`, `pd.read_json`, `pd.read_sql`, `pd.read_excel`
  - Selection: `loc[]` (label), `iloc[]` (position), `[]` (column)
  - Filtering: boolean indexing, `query()` method
  - Aggregation: `groupby()`, `agg()`, `pivot_table()`
  - Transformation: `apply()`, `map()`, `transform()`
  - Merging: `merge()`, `concat()`, `join()`
  - Handling missing data: `isna()`, `fillna()`, `dropna()`
  - Time series: `DatetimeIndex`, `resample()`, `rolling()`

#### § 12.1.3 — Data Visualization
  - `matplotlib` — the foundation (low-level, highly customizable)
  - `seaborn` — statistical visualization (built on matplotlib)
  - `plotly` — interactive plots (web-based)
  - Chart types: line, bar, scatter, histogram, heatmap, box plot

---

### 📦 Module 12.2: Automation & Scripting

#### § 12.2.1 — CLI Applications
  - `argparse` (built-in) — argument parsing
  - `click` — decorator-based CLI framework (popular)
  - `typer` — FastAPI-style CLI framework (modern, type-hint-based)
  - `rich` — beautiful terminal output (tables, progress bars, syntax highlighting)
  - `textual` — TUI (Terminal User Interface) framework

#### § 12.2.2 — Web Scraping
  - `requests` — HTTP client
  - `httpx` — modern async HTTP client
  - `BeautifulSoup4` — HTML parsing
  - `lxml` — fast XML/HTML parsing
  - `Scrapy` — full-featured web scraping framework
  - `Playwright` / `Selenium` — browser automation for JavaScript-heavy sites
  - Ethical scraping: `robots.txt`, rate limiting, legal considerations

#### § 12.2.3 — System Automation
  - `pathlib` — file system operations
  - `shutil` — high-level file operations (copy, move, archive)
  - `subprocess` — running external commands
  - `schedule` — job scheduling
  - `watchdog` — file system monitoring
  - `fabric` / `paramiko` — SSH automation
  - `pyautogui` — GUI automation (mouse/keyboard)

#### § 12.2.4 — Working with APIs
  - `requests` / `httpx` — consuming REST APIs
  - Authentication: API keys, OAuth2, JWT
  - Pagination handling
  - Rate limiting and retry
  - Webhook handling

---

### 📦 Module 12.3: Machine Learning & AI (Overview)

#### § 12.3.1 — ML Libraries (Awareness Level)
  - `scikit-learn` — traditional ML (classification, regression, clustering)
  - `TensorFlow` / `Keras` — deep learning
  - `PyTorch` — deep learning (research-focused, increasingly dominant)
  - `XGBoost` / `LightGBM` — gradient boosting
  - `Hugging Face Transformers` — NLP, LLMs
  - `LangChain` / `LlamaIndex` — LLM application frameworks

#### § 12.3.2 — Data Engineering
  - `polars` — fast DataFrame library (Rust-based, alternative to Pandas)
  - `dask` — parallel computing for larger-than-memory datasets
  - `Apache Spark (PySpark)` — distributed data processing
  - `Airflow` — workflow orchestration
  - `Prefect` / `Dagster` — modern orchestration

---

### 📦 Module 12.4: DevOps & Infrastructure

#### § 12.4.1 — Docker for Python
  - Multi-stage Dockerfile for Python apps
  - Slim base images: `python:3.12-slim`
  - `pip install --no-cache-dir` — reduce image size
  - `docker-compose.yml` for local development
  - Poetry/uv in Docker: lock file installation

#### § 12.4.2 — CI/CD
  - GitHub Actions for Python: lint, type check, test, publish
  - `tox` — test across multiple Python versions
  - `nox` — modern alternative to tox (Python-based config)
  - Publishing to PyPI: `twine upload`, `python -m build`

#### § 12.4.3 — Monitoring & Observability
  - `prometheus_client` — expose metrics
  - `opentelemetry-python` — distributed tracing
  - `structlog` — structured logging
  - `sentry-sdk` — error tracking

> ### 🛠️ Phase 12 Capstone Project: **"PyForge — A Full-Stack Automation Platform"**
> Build a comprehensive automation platform:
> - **Backend**: FastAPI with async SQLAlchemy + PostgreSQL + Redis
> - **Automation Engine**:
>   - Define workflows as Python code (DAG of tasks)
>   - Task types: HTTP requests, shell commands, file operations, database queries, API calls
>   - Scheduling: cron-like expressions, one-time, recurring
>   - Concurrent execution with `asyncio` + `ProcessPoolExecutor` for CPU-bound tasks
>   - Retry with exponential backoff on failure
> - **Features**:
>   - REST API: CRUD for workflows, tasks, schedules, execution history
>   - Real-time: WebSocket for live execution status
>   - Dashboard data: execution history, success/failure rates, timing stats
>   - Notification: webhook callbacks on completion/failure
>   - Secrets management: encrypted storage for API keys, passwords
>   - Plugin system: load custom task types from Python modules
> - **Data Pipeline Demo**:
>   - Scrape data from 3 websites (aiohttp)
>   - Parse and validate with Pydantic
>   - Transform with Pandas
>   - Store in PostgreSQL
>   - Generate report with matplotlib, serve as downloadable file
> - **Observability**:
>   - Structured logging with `structlog`
>   - Prometheus metrics endpoint
>   - OpenTelemetry tracing
> - **Quality**:
>   - pytest with async fixtures, 85%+ coverage
>   - mypy strict, ruff clean
>   - Dockerfile + docker-compose (API + PostgreSQL + Redis + Prometheus)
>   - GitHub Actions CI pipeline
>   - Full OpenAPI documentation

---

## 📊 PHASE MAP (Visual Summary)

```
Phase 0   ██░░░░░░░░░░░░░░░░  Environment & Python Philosophy
Phase 1   ███░░░░░░░░░░░░░░░  Language Fundamentals
Phase 2   █████░░░░░░░░░░░░░  Functions Advanced, Decorators, Generators
Phase 3   ███████░░░░░░░░░░░  Object-Oriented Programming
Phase 4   ████████░░░░░░░░░░  Error Handling & Context Managers
Phase 5   █████████░░░░░░░░░  Modules, Packages & Project Structure
Phase 6   ██████████░░░░░░░░  Type Hints & Static Analysis
Phase 7   ███████████░░░░░░░  Concurrency & Parallelism
Phase 8   ████████████░░░░░░  File I/O, Data Formats & Databases
Phase 9   █████████████░░░░░  Testing, Tooling & Code Quality
Phase 10  ██████████████░░░░  Design Patterns & Architecture
Phase 11  ███████████████░░░  Web Development (FastAPI, Django)
Phase 12  ████████████████░░  Data Science, Automation & Specialty Domains
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
    "I can write           "I write typed,          "I build tested,       "I architect
     Pythonic code          modular, well-           concurrent, and        production
     with OOP &             structured Python"       database-backed        systems and
     comprehensions"                                 applications"          platforms"
```

---

## 📚 RECOMMENDED RESOURCES

| Resource | Type | Phase |
|----------|------|-------|
| **Python.org Official Tutorial** | 🌐 Official | 0–3 |
| *Python Crash Course* — Eric Matthes (3rd Ed.) | 📖 Book (Beginner) | 0–3 |
| *Automate the Boring Stuff* — Al Sweigart | 📖 Book (Free Online) | 0–4 |
| *Fluent Python* — Luciano Ramalho (2nd Ed.) | 📖 Book (MUST READ) | 2–10 |
| *Effective Python* — Brett Slatkin (2nd Ed.) | 📖 Book (MUST READ) | 2–10 |
| *Python Cookbook* — David Beazley & Brian K. Jones | 📖 Book (Recipes) | 3–9 |
| *Robust Python* — Patrick Viafore | 📖 Book (Type hints, architecture) | 6–10 |
| *Architecture Patterns with Python* — Percival & Gregory | 📖 Book (DDD, Clean Arch) | 10–11 |
| *High Performance Python* — Gorelick & Ozsvald | 📖 Book | 7 |
| *Python Concurrency with asyncio* — Matthew Fowler | 📖 Book | 7 |
| *Using Asyncio in Python* — Caleb Hattingh | 📖 Book | 7 |
| *Two Scoops of Django* — Greenfeld & Greenfeld | 📖 Book | 11 |
| **Real Python** (realpython.com) | 🌐 Tutorials | ALL |
| **Python Morsels** (pythonmorsels.com) | 🌐 Exercises | 1–6 |
| **Talk Python To Me** (podcast) | 🎙️ Podcast | ALL |
| **ArjanCodes** (YouTube) | 🎥 Video (Design, Modern Python) | 3–10 |
| **mCoding** (YouTube) | 🎥 Video (Deep Python) | 2–10 |
| **Corey Schafer** (YouTube) | 🎥 Video (Fundamentals) | 0–6 |
| **Anthonywritescode** (YouTube) | 🎥 Video (Tooling, Internals) | 4–9 |
| **Exercism — Python Track** | 🧪 Practice | 1–6 |
| **LeetCode** (Python) | 🧪 DSA Practice | 1–4 |
| **FastAPI Documentation** | 📄 Official Docs | 11 |
| **Django Documentation** | 📄 Official Docs | 11 |
| **Pydantic Documentation** | 📄 Official Docs | 8, 11 |
| **docs.python.org** | 📄 Official Docs | ALL |

---

## 🗺️ WHERE PYTHON TAKES YOU (Career Paths)

```
                                  ┌───────────────────────────┐
                                  │   Backend / API           │
                           ┌─────▶│   Engineering             │
                           │      │   (FastAPI, Django, Flask) │
                           │      └───────────────────────────┘
                           │      ┌───────────────────────────┐
                           │      │   Data Science &          │
                   ┌───────┤─────▶│   Analytics               │
                   │       │      │   (Pandas, NumPy, Jupyter) │
                   │       │      └───────────────────────────┘
                   │       │      ┌───────────────────────────┐
   ┌────────────┐  │       │      │   Machine Learning &      │
   │            │  │       ├─────▶│   Artificial Intelligence  │
   │  Master    ├──┤       │      │   (PyTorch, scikit-learn,  │
   │  Python    │  │       │      │    HuggingFace, LLMs)      │
   │            │  │       │      └───────────────────────────┘
   └────────────┘  │       │      ┌───────────────────────────┐
                   │       │      │   DevOps / Automation /   │
                   │       ├─────▶│   Scripting               │
                   │       │      │   (Ansible, Fabric, CLI)   │
                   │       │      └───────────────────────────┘
                   │       │      ┌───────────────────────────┐
                   │       │      │   Cybersecurity /         │
                   │       ├─────▶│   Penetration Testing     │
                   │       │      │   (Scapy, Burp, Tooling)   │
                   │       │      └───────────────────────────┘
                   │       │      ┌───────────────────────────┐
                   │       │      │   Scientific Computing /  │
                   └───────┴─────▶│   Research                │
                                  │   (SciPy, SymPy, Jupyter)  │
                                  └───────────────────────────┘
```

---

> ### 💡 Final Advice
> **"Python is the easiest language to learn and one of the hardest to master. The gap between beginner and expert Python is enormous — and it's filled with idioms, not syntax."**
>
> Five non-negotiable rules for your Python journey:
>
> 1. **Read *Fluent Python* by Luciano Ramalho** — it's the single most important book for going from "I know Python" to "I truly UNDERSTAND Python." Covers generators, descriptors, metaclasses, coroutines, and every Pythonic pattern.
> 2. **Use type hints from Phase 3 onward** — Python's dynamic typing is powerful but dangerous at scale. Type hints + `mypy` give you the best of both worlds. Modern Python without type hints is incomplete Python.
> 3. **Master generators and iterators** — they are Python's secret weapon for memory-efficient, elegant, composable data processing. If you're using lists where generators would work, you're not writing Pythonic code.
> 4. **Use `ruff` + `mypy` + `pytest` on EVERY project** — this trinity of tools catches bugs before they reach production. Configure them in `pyproject.toml` and never think about it again.
> 5. **Learn one web framework deeply** — FastAPI if you want modern async Python, Django if you want batteries-included. Don't learn both superficially — master one, then learn the other's differences.
>
> The difference between a *Python programmer* and a *Python engineer* is:
> - **Writing idiomatic Python** (comprehensions, generators, context managers, unpacking)
> - **Understanding the data model** (dunder methods, descriptors, protocols)
> - **Testing and typing everything** (pytest, mypy, pydantic)
> - **Knowing when Python is NOT the right tool** (CPU-bound work → Go/Rust/C, mobile → Swift/Kotlin)

---

*This roadmap takes you from "What's a variable?" to "I can architect, build, test, and deploy production-grade web APIs, data pipelines, automation platforms, and ML systems — all in idiomatic, typed, tested Python."* 🐍🚀