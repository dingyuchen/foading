# Parsing

Parser takes in tokens and outputs a syntax tree

1. Universal
   1. can parse any grammar, but inefficient
2. Top-down
   1. Builds parse trees from root to the leaves
3. Bottom-up
   1. Builds parser trees from leaves to the root

## Prerequisite

The subject programming language must be expressed in **context-free grammar** format

## Context-Free Grammar (CFG)

- A set of **Productions**
- A set of **Terminals**
- A set of **Non-Terminals**
- A **Start Symbol**

### Formal Definition

4-tuple
- a finite set of **non-terminal** symbols (variables)
- a finite set of **terminal** symbols
- a finite set of **production rules**
- a special **start symbol**

### Derivation

Final output of all terminals is called a **sentence**.

Intermediate forms are called **sentential form**, and can be represented by a greek symbol.

**Left-most derivation** :
At each derivation, the leftmost non-terminal is chosen.
