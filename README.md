# OEIS A396149 Data

Statistical data for the graphs of [OEIS A396149](https://oeis.org/A396149) (connected graphs where every edge belongs to at least one 3-clique).

## Data Structure
Files are grouped by vertex count $N$ in the `data/` directory (e.g., `data/N8/`). 
Each `.txt` file contains the frequency distribution of a specific graph invariant in a tab-separated format: `[Value] \t [Frequency]`.

**Example (`N8_Edge_Count.txt`):**
```text
--- Edge_Count ---
11      7
12      30
13      88
```

## Computed Invariants
The following 26 metrics are computed for each $N$:

* **Basic:** Edge Count, Triangle Count, K4 Count, Max/Min Degree, Cyclomatic Number, Total Cliques
* **Distance:** Diameter, Radius, Wiener Index, Circumference
* **Connectivity:** Vertex/Edge Connectivity, Cut Vertices
* **Subgraphs & Matchings:** Max Clique Size, Independence Number, Matching Number, Perfect Matchings, Spanning Trees
* **Algebraic & Others:** Chromatic Number, Domination Number, Adjacency Determinant, Hosoya Index, Zagreb M1/M2, Acyclic Orientations

## License
MIT
