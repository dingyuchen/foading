# Lexical Analysis

## Plan for Lexical Analysis

- Construct a machine (**automata**) to handle regular expression
  - convert Regular expression to NFA
  - convert NFA to DFA
- Execute the machine to recognize tokens

## Automating the Automata Generation

- parser generators
- recursive descent parsing

### Jflex

- `Lex` and `Yacc` is the first lexical analyzer and parser

## DFA State Minimization

- There is _always an unique minimum state DFA_ for any regular language.
- The minimum-state DFA can be constructed from any DFA for the same language
- Minimization is achieved by 
  - removing unreachable states
  - grouping equivalent states

### Iterative algorithm

#### Reachability

Basically a BFS from the start state.
All unvisited states are removed from the state space.

#### Grouping Equivalent States

Partitioning the states of the DFA into groups that cannot be distinguished

Two states $p$ and $q$ are **equivalent** if starting from either state, every string $w$ will make transitions into the same state.
Otherwise, they are **distinct**.

