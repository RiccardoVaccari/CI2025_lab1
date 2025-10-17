# CI2025_LAB1 - Multiple 0/1 Knapsack Problem with Multidimensional Constraints

_This solution was developed in collaboration with Luca Lodesani (s346978)._

## Problem Description

The objective is to maximize the total value of items distributed among a fixed number of knapsacks while respecting each knapsack's multidimensional capacity constraints. Each item can be placed in at most one knapsack.

The problem parameters are defined in the script and include:
- `NUM_KNAPSACKS`: Number of available knapsacks.
- `NUM_ITEMS`: Total number of items to choose from.
- `NUM_DIMENSIONS`: Number of weight dimensions (e.g., weight and volume).
- `VALUES`: Value of each item.
- `WEIGHTS`: Multidimensional weights of each item.
- `CONSTRAINTS`: Maximum capacity for each dimension of each knapsack.

## Proposed Solution

### Solution 1 - Hill Climbing

The first proposed solution employs a **Hill Climbing** algorithm starting from a random solution.

The tweak function toggles a random item in a random knapsack.
The new solution is checked for validity before evaluating its fitness and potentially accepting it.


```
P1 -> Total value: 1065
P2 -> Total value: 36729
P3 -> Total value: 1131580
```

### Solution 2 - Tabu Search

The HC solution has been improved by implementing a **Tabu Search** strategy to avoid already explored solutions and to explore multiple neighbors at each iteration.

The tweak function remains the same, but at each iteration, multiple candidate solutions are generated. Only valid candidates that are not in the tabu list are considered for evaluation. The best candidate is selected for potential acceptance.

```
P1 -> Total value: 1056
P2 -> Total value: 40633
P3 -> Total value: 1629819
```

### Solution 3 - Simulated Annealing

This solution focuses on implementing a **Simulated Annealing** algorithm to escape local optima. 

The tweak function generates a new candidate solution by randomly adding or removing a random item across a random knapsack.

```
P1 -> Total value: 1065
P2 -> Total value: 44590
P3 -> Total value: 1143541
```

