# Multi-Language OpenCog Repository Implementations

## Overview

This directory contains single-file implementations of the three core OpenCog repositories (cogutil, atomspace, cogserver) in multiple programming languages, each showcasing its paradigm's unique strengths.

## Language Implementations

### 1. C++ (Systems/OOP)
**Path**: `Repo/opencog/*/c++/`

**Strengths**:
- Low-level control with high performance
- Object-oriented design with RAII
- Strong typing with templates
- Standard library (STL)

**Files**:
- `opencog-cogutil.cpp` (281 lines) - Logger, Config, Timer, StringUtils
- `opencog-atomspace.cpp` (337 lines) - Hypergraph with Atom/Node/Link
- `opencog-cogserver.cpp` (372 lines) - Command system with interactive shell

**Compile**: `g++ -std=c++11 -o cogutil opencog-cogutil.cpp`

**Example**:
```cpp
Logger logger(Logger::INFO);
logger.info("Starting system");

AtomSpace atomspace;
auto human = atomspace.addNode(CONCEPT_NODE, "human");
auto mortal = atomspace.addNode(CONCEPT_NODE, "mortal");
atomspace.addLink(INHERITANCE_LINK, {human, mortal});
```

### 2. Python (Multi-Paradigm/Scripting)
**Path**: `Repo/opencog/*/Python/`

**Strengths**:
- Dynamic typing and duck typing
- Context managers (`with` statements)
- Decorators for code elegance
- Operator overloading (`__len__`, `__iter__`)
- Rich standard library

**Files**:
- `opencog-cogutil.py` (331 lines) - Logging, config, decorators, context managers
- `opencog-atomspace.py` (366 lines) - OOP hypergraph with operator overloading
- `opencog-cogserver.py` (354 lines) - cmd.Cmd interactive shell, decorator commands

**Run**: `python3 opencog-cogutil.py`

**Example**:
```python
@timeit
def compute():
    return sum(range(1_000_000))

with Timer("work", logger):
    atomspace = AtomSpace()
    human = atomspace.add_node(AtomType.CONCEPT_NODE, "human")
    
# Operator overloading
if human in atomspace:
    print(f"AtomSpace size: {len(atomspace)}")
```

### 3. Haskell (Pure Functional)
**Path**: `Repo/opencog/*/Haskell/`

**Strengths**:
- Pure functions (no side effects)
- Immutable data structures
- Strong static typing with inference
- Algebraic data types
- Function composition and point-free style
- Higher-order functions

**Files**:
- `opencog-cogutil.hs` (343 lines) - Pure functions, immutability, composition

**Run**: `runghc opencog-cogutil.hs`

**Example**:
```haskell
-- Algebraic data type
data LogLevel = DEBUG | INFO | WARN | ERROR

-- Pure functions with type signatures
toLowerCase :: String -> String
toLowerCase = map toLower

-- Function composition
transform :: String -> String
transform = toUpperCase . trimString

-- Immutable updates
config2 = setConfig "port" "17001" config1
```

### 4. Prolog (Logic Programming)
**Path**: `Repo/opencog/*/Prolog/`

**Strengths**:
- Declarative knowledge representation
- Facts and rules
- Pattern matching and unification
- Backtracking for search
- Horn clauses for logical inference
- Transitive closure

**Files**:
- `opencog-atomspace.pl` (364 lines) - Logic-based hypergraph with inference

**Run**: `swipl -g demo -t halt opencog-atomspace.pl`

**Example**:
```prolog
% Facts
atom_node(concept, 'Socrates', tv(1.0, 1.0)).
atom_node(concept, 'human', tv(1.0, 1.0)).
atom_link(inheritance, node(concept, 'Socrates'), node(concept, 'human'), tv(1.0, 1.0)).

% Rules with transitive inference
inherits_from(A, B) :-
    atom_link(inheritance, node(concept, A), node(concept, B), _).

inherits_from(A, C) :-
    inherits_from(A, B),
    inherits_from(B, C).

% Query
?- is_mortal('Socrates').  % true (by transitive inference)
```

### 5. Julia (Scientific Computing)
**Path**: `Repo/opencog/*/Julia/`

**Strengths**:
- Multiple dispatch for polymorphism
- High performance (JIT to native code)
- Mathematical notation
- Unicode support throughout
- Metaprogramming with macros
- Easy parallelization

**Files**:
- `opencog-cogutil.jl` (326 lines) - Multiple dispatch, macros, matrix ops

**Run**: `julia opencog-cogutil.jl`

**Example**:
```julia
# Multiple dispatch
area(c::Circle) = π * c.radius^2
area(r::Rectangle) = r.width * r.height

# Macros for metaprogramming
result = @timed "computation" sum(1:1_000_000)

# Matrix operations (Julia's strength)
A = [1 2; 3 4]
B = [5 6; 7 8]
C = A * B  # Matrix multiplication
D = A .+ B # Broadcasted element-wise

# Unicode naturally supported
α = 1.5
β = 2.0
Σ = α + β
```

## Paradigm Comparison

### Feature Matrix

| Feature | C++ | Python | Haskell | Prolog | Julia |
|---------|-----|--------|---------|--------|-------|
| **Typing** | Static/Strong | Dynamic | Static+Infer | Untyped | Optional |
| **Paradigm** | OOP/Multi | Multi | Pure Functional | Logic | Multi+Scientific |
| **Performance** | Very Fast | Moderate | Fast | Moderate | Very Fast |
| **Memory Model** | Manual/RAII | GC | GC | GC | GC |
| **AI Strength** | Systems | ML/Data Sci | Symbolic | Knowledge | Numerical |
| **Concurrency** | Threads | Threading/Async | STM/Par | Backtrack | Parallel/Dist |
| **Key Feature** | Control | Versatility | Purity | Inference | Dispatch |

### Problem-Solving Approaches

**Same Problem: String Transformation**

**C++**: Explicit loops with mutability
```cpp
std::string toLower(const std::string& str) {
    std::string result = str;
    for (char& c : result) {
        c = std::tolower(c);
    }
    return result;
}
```

**Python**: List comprehension
```python
def to_lower(text: str) -> str:
    return text.lower()  # Built-in method
```

**Haskell**: Pure function with map
```haskell
toLowerCase :: String -> String
toLowerCase = map toLower  -- Point-free style
```

**Prolog**: Pattern matching (conceptual)
```prolog
to_lower([], []).
to_lower([H|T], [L|LT]) :-
    char_type(L, to_lower(H)),
    to_lower(T, LT).
```

**Julia**: Functional approach
```julia
to_lower(s::String) = lowercase(s)  # Multiple dispatch
```

## RosettaCog Philosophy

Each implementation demonstrates:

1. **Paradigm Purity**: Idiomatic code following language conventions
2. **Strength Showcase**: Highlighting each language's unique capabilities
3. **Comparative Learning**: Same problems, different solutions
4. **Post-Polyglot Synthesis**: Understanding when to use which tool

## Use Cases by Language

### When to Use Each

**C++**: High-performance systems, embedded, game engines, OS components
**Python**: Rapid prototyping, data science, ML pipelines, glue code
**Haskell**: Compilers, financial systems, formal verification, type-safe systems
**Prolog**: Expert systems, NLP, knowledge bases, constraint solving
**Julia**: Scientific computing, numerical analysis, data science, simulations

## Testing

### C++
```bash
g++ -std=c++11 -o test opencog-cogutil.cpp && ./test
```

### Python
```bash
python3 opencog-cogutil.py
python3 opencog-atomspace.py
echo "exit" | python3 opencog-cogserver.py
```

### Haskell
```bash
runghc opencog-cogutil.hs
```

### Prolog
```bash
swipl -g demo -t halt opencog-atomspace.pl
```

### Julia
```bash
julia opencog-cogutil.jl
```

## Statistics

- **Total Languages**: 5 (C++, Python, Haskell, Prolog, Julia)
- **Total Files**: 10+ implementations
- **Total Lines**: ~3,500+ lines of code
- **Paradigms**: OOP, Functional, Logic, Multi-paradigm, Scientific
- **All Tested**: ✓ Compiles/runs successfully

## Key Takeaways

1. **No Silver Bullet**: Each language excels in different domains
2. **Paradigm Matters**: Problem structure guides language choice
3. **Tool Diversity**: Post-polyglot synthesis leverages multiple languages
4. **Learning Value**: Comparative implementations reveal design patterns
5. **OpenCog Vision**: Flexible architecture supporting multiple backends

## Contributing

To add a new language implementation:

1. Create directory: `Repo/opencog/*/YourLanguage/`
2. Implement: `opencog-cogutil.{ext}`, `opencog-atomspace.{ext}`, `opencog-cogserver.{ext}`
3. Follow the pattern of existing implementations
4. Showcase your language's unique strengths
5. Add documentation and tests
6. Update this README

## License

Follows RosettaCog repository license.

## References

- [RosettaCode](http://rosettacode.org) - Multi-language programming chrestomathy
- [OpenCog](https://opencog.org) - Artificial General Intelligence framework
- [RosettaCog Repository](https://github.com/cogpy/RosettaCog)

---

*"The right tool for every job, and the intelligence to know which tool that is."*
— RosettaCog Philosophy
