# Introduction to Compilers

What are common language processors

- Compilers
- structure editors
  - IDEs
- pretty printers
- Static checkers
  - outputs errors
- Interpreters

## A Compilation Model

Analysis
- breaks up a source program into constituent parts
- creates an intermediate representation

Synthesis
- Constructs the final program

### Lexical Analysis

Stream of characters transformed into tokens

### Syntax Analysis

When the token stream is turned into a tree structure.

### Semantic Analysis

Type checking happens here
- Casting also happens here

### Intermediate Code Generation

Translation from the tree structure into SSA

### Code Optimization

the intermediate code is optimized (somehow)
(just statement reduction?)

### Code Generation

Final translation into assembly code

### Assembly

Assembler turns assembly code into binary
(not part of compilers)

## Church's Thesis

The Turing machine is equivalent in computing power to all computers and the most general notions of computations.

### Undecidability

There exists problems for which no Turing machine can halt and return an answer.
- There are unsolvable problems in this universe.
- Not the same as NP-completeness
