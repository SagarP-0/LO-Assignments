# LO ASSIGNMENTS
## SAGAR PARAJULI - CS26BTKMU11003
### Assignment 1: Handwritten simplex algorithm notes
### Assignment 2: Python implementation of the simplex algorithm
# Linear Programming Problem and Test Results

## 1. Example Linear Programming Problem

Consider the following linear programming problem:

**Maximize**
\[
z = 3x_1 + 5x_2
\]

**Subject to the constraints**
\[
\begin{aligned}
x_1 &\leq 4,\\
2x_2 &\leq 12,\\
3x_1 + 2x_2 &\leq 18,\\
x_1 &\geq 0,\\
x_2 &\geq 0.
\end{aligned}
\]

### Program Output

Our program produces the following output:

```text
n = 2 variables, m = 5 constraints

Initial vertex
  x        = [4, 3]
  z        = 27
  feasible = True

Vertices visited
  iter vertex                z           tight rows
  0    [4, 3]                27          [1, 3]
  1    [2, 6]                36          [2, 3]

Result
  Optimal vertex: [2, 6]
  Optimal objective value: 36
```

The program identifies \((4,3)\) as the initial feasible vertex and then moves to \((2,6)\), where the objective function attains its maximum value of \(36\).

Thus, the **optimal solution** is
\[
(x_1,x_2)=(2,6), \qquad z_{\max}=36.
\]

## 2. Results for Other Test Cases

The program was also evaluated on several additional test cases covering different types of linear programming problems.

| Test case | Description | Status | Objective value (\(z\)) | Optimal vertex | Vertices visited |
|:--|:--|:--|--:|:--|--:|
| 1 | Unique optimum | Optimal | 36 | \([2,6]\) | 3 |
| 2 | Multiple optima | Optimal | 4 | \([1,3]\) | 3 |
| 3 | Infeasible | Infeasible | — | — | 0 |
| 4 | Unbounded | Unbounded | — | — | 1 |
| 5a | Degenerate, 2D | Optimal | 6 | \([2,2]\) | 3 |
| 5b | Degenerate, 3D, \(c=(0,0,1)\) | Optimal | 1 | \([0,0,1]\) | 1 |
| 5c | Degenerate, 3D, \(c=(1,1,0)\) | Optimal | 2 | \([1,1,0]\) | 2 |
| 6 | Redundant constraints | Optimal | 4 | \([2,2]\) | 3 |
| 7 | Negative data | Optimal | -4 | \([2,1]\) | 2 |
| 8 | Four variables | Optimal | 8 | \([1,1,0.5,0]\) | 4 |
| 8b | 40 random problems compared with SciPy | Optimal | — | — | — |
| 9a | Nearly tight constraint | Optimal | 2 | \([1,1]\) | 3 |
| 9b | Tiny step | Optimal | 1 | \([0,1]\) | 1 |

*Note:* A dash (—) indicates that the corresponding value was not reported or is not applicable.

## 3. Summary

The program was tested on **13 test cases**, covering unique and multiple optimal solutions, infeasible and unbounded problems, degenerate vertices, redundant constraints, negative data, higher-dimensional problems, random comparisons with SciPy, and numerical edge cases.

**All 13 tests passed.**
