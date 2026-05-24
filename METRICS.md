# Mathematical Definitions of Computed Metrics

Let $G = (V, E)$ be a simple, undirected, and connected graph. 
We define the following standard notations used throughout this document:
* $N = |V|$: The number of vertices.
* $M = |E|$: The number of edges.
* $\deg(v)$: The degree of vertex $v \in V$.
* $d(u, v)$: The shortest-path distance between vertices $u$ and $v$.
* $A$: The adjacency matrix of $G$.
* $K_k$: A complete graph (clique) on $k$ vertices.

---

## 1. Basic Properties & Degree

* **Edge_Count** ($M$): The total number of edges in $G$.
  $$M = |E|$$

* **Triangle_Count**: The number of 3-cliques ($K_3$) in $G$.
  $$|\lbrace S \subseteq V \mid |S|=3 \text{ and } G[S] \cong K_3 \rbrace|$$

* **K4_Count**: The number of 4-cliques ($K_4$) in $G$.
  $$|\lbrace S \subseteq V \mid |S|=4 \text{ and } G[S] \cong K_4 \rbrace|$$

* **Max_Degree** $(\Delta(G))$: The maximum degree of any vertex in $G$.
  $$\Delta(G) = \max_{v \in V} \deg(v)$$

* **Min_Degree** $(\delta(G))$: The minimum degree of any vertex in $G$.
  $$\delta(G) = \min_{v \in V} \deg(v)$$

* **Cyclomatic_Number** $(\mu(G))$: The minimum number of edges that must be removed to make the graph acyclic (also known as circuit rank).
  $$\mu(G) = M - N + 1$$

* **Total_Cliques**: The total number of complete subgraphs (of any size $k \ge 1$) in $G$.
  $$\sum_{k=1}^{\omega(G)} |\lbrace S \subseteq V \mid |S|=k \text{ and } G[S] \cong K_k \rbrace|$$

---

## 2. Distances & Paths

* **Diameter** $(D)$: The maximum eccentricity of any vertex in the graph.
  $$D = \max_{u, v \in V} d(u, v)$$

* **Radius** $(r)$: The minimum eccentricity of any vertex in the graph.
  $$r = \min_{v \in V} \max_{u \in V} d(u, v)$$

* **Wiener_Index** $(W(G))$: The sum of the shortest-path distances between all pairs of vertices.
  $$W(G) = \sum_{\lbrace u, v \rbrace \subseteq V} d(u, v)$$

* **Circumference** $(c(G))$: The length of the longest simple cycle in $G$. (If $G$ is a tree, this is typically undefined or $0$, though A396149 graphs always contain triangles).
  $$c(G) = \max \lbrace |C| \mid C \text{ is a cycle in } G \rbrace$$

---

## 3. Connectivity

* **Vertex_Connectivity** $(\kappa(G))$: The minimum number of vertices that must be removed to disconnect the graph (or reduce it to a 1-vertex graph).
  $$\kappa(G) = \min \lbrace |S| \mid S \subset V, G-S \text{ is disconnected} \rbrace$$

* **Edge_Connectivity** $(\lambda(G))$: The minimum number of edges that must be removed to disconnect the graph.
  $$\lambda(G) = \min \lbrace |F| \mid F \subset E, G-F \text{ is disconnected} \rbrace$$

* **Cut_Vertices**: The number of articulation points in $G$.
  $$|\lbrace v \in V \mid G-v \text{ is disconnected} \rbrace|$$

---

## 4. Subgraphs & Matchings

* **Max_Clique_Size** $(\omega(G))$: The clique number of $G$; the number of vertices in the largest maximum clique.
  $$\omega(G) = \max \lbrace |S| \mid S \subseteq V \text{ and } G[S] \cong K_{|S|} \rbrace$$

* **Independence_Number** $(\alpha(G))$: The size of the largest independent set in $G$.
  $$\alpha(G) = \max \lbrace |S| \mid S \subseteq V \text{ and } \forall u, v \in S, uv \notin E \rbrace$$

* **Matching_Number** $(\nu(G))$: The size of the maximum matching (a set of pairwise non-adjacent edges).
  $$\nu(G) = \max \lbrace |M'| \mid M' \subseteq E \text{ is a matching} \rbrace$$

* **Perfect_Matching_Count**: The total number of distinct perfect matchings in $G$. If $N$ is odd, this is always $0$.
  $$|\lbrace M' \subseteq E \mid M' \text{ is a matching and } |M'| = N/2 \rbrace|$$

* **Spanning_Trees** $(\tau(G))$: The total number of distinct spanning trees of $G$. Computed via Kirchhoff's Matrix Tree Theorem:
  $$\tau(G) = \det(L_{ii})$$
  (where $L_{ii}$ is the Laplacian matrix of $G$ with the $i$-th row and column removed).

---

## 5. Algebraic Indices & Advanced Metrics

* **Chromatic_Number** $(\chi(G))$: The minimum number of colors required to color the vertices of $G$ such that no two adjacent vertices share the same color.
  $$\chi(G) = \min \lbrace k \mid \exists c: V \to \lbrace 1, \dots, k \rbrace \text{ s.t. } uv \in E \implies c(u) \ne c(v) \rbrace$$

* **Domination_Number** $(\gamma(G))$: The size of the smallest dominating set.
  $$\gamma(G) = \min \lbrace |S| \mid S \subseteq V \text{ and } V = S \cup N(S) \rbrace$$
  (where $N(S)$ is the set of all neighbors of vertices in $S$).

* **Determinant_Adj**: The determinant of the adjacency matrix $A$.
  $$\det(A)$$

* **Hosoya_Index** $(Z(G))$: The total number of matchings in $G$, including the empty matching. Let $m_k$ be the number of matchings of size $k$.
  $$Z(G) = \sum_{k=0}^{\lfloor N/2 \rfloor} m_k$$

* **Zagreb_M1** $(M_1(G))$: The first Zagreb index.
  $$M_1(G) = \sum_{v \in V} \deg(v)^2$$

* **Zagreb_M2** $(M_2(G))$: The second Zagreb index.
  $$M_2(G) = \sum_{uv \in E} \deg(u)\deg(v)$$

* **Acyclic_Orientations** $(a(G))$: The number of ways to direct the edges of $G$ such that the resulting directed graph contains no directed cycles.
  $$a(G) = |\lbrace \vec{G} \mid \vec{G} \text{ is an orientation of } G \text{ with no directed cycles} \rbrace|$$
