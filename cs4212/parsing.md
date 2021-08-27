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

If $S \Rightarrow_{lm}^* \alpha$, then $\alpha$ is a left-sentential form.

**Right-most derivation** :
At each derivation, the rightmost non-terminal is chosen.
- Also known as **canonical derivation**.

## Ambiguity

If a grammar can produce _more than one_ parse tree for a sentence, then the grammar is **ambiguous**.

### Inherently Ambiguous CFL

A context-free language in which _every_ context-free grammar is ambiguous is said to be **inherently ambiguous**.

## Properties of CFL

Closed under:
- Union
- Concatenation
- Kleene Closure
- Substitution

Not Closed under:
- Intersection
- Complement

## Pushdown Automata

A pushdown automaton $M$ is a system $(Q, \sum, \Gamma, \delta, q_0, Z_0, F)$ where
1. finite set of states
2. input alphabet
3. stack alphabet
4. initial state
5. particular stack symbol called the start symbol
6. set of final states
7. mapping from $Q \times (\Sigma \cup \epsilon) \times \Gamma$

### Transition Relation


