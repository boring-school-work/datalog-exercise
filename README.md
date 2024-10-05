# Datalog Exercise - Shortest Path

## Getting Started

In general a datalog program is:

- A set of variables,
- a set of rules, and
- a set of assertions combining the two.

### Concepts

- **Consult:** Running a file(s).
- **Abolish:** Clear all rules and facts in current datalog environment.
- **Solve:** To make a query or ask a question based on rules and facts.
- **Predicate:** Used to establish a relationship between variables in a form of
  logical assertion.
- **Variable:** A placeholder for any value.
- **Facts:** A predicate which is declared as true.
- **Rule:** Defines a relationship between predicates.

### Few Commands

- To perform consultation, use the following set of syntax:

```datalog
/c filename

% or a group of files
/c file1, file2

```

- To abolish datalog database:

```datalog
/abolish
```

- To solve a query in datalog:

```datalog
% in repl
/solve query

% in a file
:-solve(query).
```

## Printing "Hello World"

```datalog
message('hello world').
:-solve(message(X)).
```

## Using Facts & Rules

```datalog
parent(john, mary).
parent(mary, alice).
grandparent(X,Y) :- parent(X, Z), parent(Z, Y).
:-solve(grandparent(john,X)).
```

## Performing Addition

```datalog
add(X, Y, Z) :-
    Z = X + Y.

:-solve(add(2,3,X)).
```

## Solving The 'Shortest Path' Problem
