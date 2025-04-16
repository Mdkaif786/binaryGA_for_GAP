
# Binary-Coded GA for Optimization and GAP Problem

This project contains two major components:
1. **Optimization of the Sphere function with 4 variables using Binary-Coded GA.**
2. **Solving the Generalized Assignment Problem (GAP), specifically `gap12`, using Binary-Coded GA and comparing it with optimal and greedy approximations.**

---

## 📁 Project Structure

```
.
├── binary_ga.ipynb                 # Jupyter notebook containing implementation and experiments
├── binary_ga_results.csv          # Results of GA runs (fitness values and/or assignments)
├── optimal_results.csv            # Optimal values for comparison 
├── greedy_results.csv             # Results from greedy approximation algorithm
├── gap12_comparison.png           # Convergence plot over 100 iterations for GAP12
├── gap_dataset_files/             # Contains GAP instances like gap12.txt
├── README.md  
```

---

## 🧮 1. Sphere Function Optimization

**Objective:**
Minimize the following function using Binary-Coded GA:

min f(x) = ∑ xi²
           4
          i=1

where, xi ∈ [−10, 10]  ∀i

**Key Features:**
- Binary encoding for 4 decision variables.
- Fitness is based on the negative of the objective (since GA maximizes by default).
- Encoding precision is adjusted to balance performance and representation.

---

## 📦 2. GAP Problem (gap12)

**Problem Description:**
The Generalized Assignment Problem (GAP) involves assigning tasks to agents such that:
- Each user is assigned to exactly one server.
- The total utility is maximized.
- Server resource constraints are not violated.

It also includes a comparison of the binary_ga approach with greedy approach results and the optimal solutions.
### Dataset Format

Each `.txt` file contains:
1. Number of instances
2. For each instance:
   - Number of servers and users
   - Utility matrix (servers × users)
   - VM allocation matrix (servers × users)
   - Server capacities (list)
### Output

For each instance:
- Task Assignments (user → server)
- Total Optimal Utility

### Example Output

```
Processing Instance 1 from gap1.txt  
Task Assignments: [1, 2, 0, 3, ...]  
Total Optimal Utility: 562.0
```


**Approach:**
- Binary-Coded Genetic Algorithm to encode assignment vectors.
- A decoder is used to validate feasibility.
- Fitness function considers feasibility, cost, and penalizes constraint violations.

**Comparative Analysis:**
- **Optimal Solution:** Read from `optimal_results.csv`
- **Greedy Approximation:** Based on a heuristic strategy, results in `greedy_results.csv`
- **GA Result:** Stored in `binary_ga_results.csv`

**Visualization:**
- `gap12_comparison.png` shows convergence of the GA over 100 iterations.

---

## 📊 Results & Interpretation

- **Convergence Plot**: Helps track GA performance.
- **Comparison CSVs**: Highlight the effectiveness of GA compared to other approaches.
- **GA Settings**: Customizable parameters like mutation rate, crossover rate, and population size are set in `binary_ga.ipynb`.

---

## 📝 References

- GAP Dataset: [OR-Library GAP Instances](https://people.brunel.ac.uk/~mastjjb/jeb/orlib/gapinfo.html)
- GAP Algorithms:
  - [Efficient Approximation Algorithm](https://github.com/suzhiyang/GAP)
  - [GA, BA, ACO implementations](https://github.com/acco93/GAP-using-GA-ACO-and-BA)
  - [Metaheuristics collection](https://github.com/lorenzogatto/GAPsolvers)

---

## 📌 How to Run

1. Open `binary_ga.ipynb` in Jupyter.
2. Run each section step-by-step to:
   - Solve the Sphere function.
   - Load GAP instance and solve all the gap files.
   - View convergence graph and comparison of `gap12`.

## ✍️ Author

**Md Kaif
M.Tech (cse)
Nit Jamshedpur**
