<!-- ╭────────────────────────────────────────────────────────╮
     │   ⚡ Circuits · Problem 1 — Equivalent Resistance via Graph Theory   │
     ╰────────────────────────────────────────────────────────╯ -->

# ⚡ **Problem 1: Equivalent Resistance Using Graph Theory**

> *“Turn tangled resistor webs into a simple number—graph theory is the key.”*  

---

## 📋 Table of Contents  
1. [Motivation 🎯](#motivation)  
2. [Graph Representation 🔗](#representation)  
3. [Algorithm Overview 🔍](#overview)  
4. [Options: Pseudocode vs Implementation 💻](#options)  
5. [Worked Examples & Tests 🧪](#examples)  
6. [Complexity & Extensions ⚙️](#complexity)  
7. [Wrap-Up 📝](#conclusions)  
8. [Further Reading 📚](#references)  

---

<a name="motivation"></a>
## 1 · Motivation 🎯  
Calculating equivalent resistance by hand (series/parallel rules) becomes error-prone for large circuits.  
**Graph theory** offers:

- A unified view: nodes = junctions, edges = resistors (weight = resistance).  
- Automated reduction: detect series chains & parallel branches.  
- Scalability: handle nested combos and loops.  

This method underpins modern circuit simulators and network optimizers.

---

<a name="representation"></a>
## 2 · Graph Representation 🔗  

1. **Nodes** ↔ circuit junctions (wire intersections).  
2. **Edges** ↔ resistors; each edge carries a weight \(R_{ij}\).  
3. **Goal**: reduce the graph to a single edge between the two terminals (source & sink) with weight \(R_{\mathrm{eq}}\).

---

<a name="overview"></a>
## 3 · Algorithm Overview 🔍  

> **Core idea**:  
> ✓ **Series reduction** when a node has degree 2 (excluding terminals).  
> ✓ **Parallel reduction** when multiple edges connect the same two nodes.

<img src="https://i.imgur.com/muiULaP.png" width="400">

## 4  Implementation 💻

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1zZMETYf2R7h9i8Gxi4_nMZSkjdMu_LIy?usp=sharing)

Equivalent resistance A→D = 6.200 Ω

<a name="examples"></a>
## 5 · Worked Examples & Tests 🧪

---

### Example 1: Simple Series Chain  
**Circuit:** A — 1 Ω — B — 2 Ω — C — 3 Ω — D  
**Analytical:**  
$$
R_{\rm eq} = 1 + 2 + 3 = 6\;\Omega
$$  
**Code Verify:**

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1_G7BLZLi6sFVG969m2lMs-Hz7gMtXsVB?usp=sharing)

<a name="complexity"></a>
## 6 · Performance & Extensions ⚙️

- **Time Complexity**  
  - Series & parallel scans: each pass is \(O(V + E)\).  
  - Up to \(O(E)\) passes in worst case ⇒ total ~\(O(E^2)\).  
- **Space Complexity**  
  - Stores a graph copy and occasional temporary structures ⇒ \(O(V + E)\).  
- **Practical Optimizations**  
  1. **Degree-2 queue**: maintain a queue of nodes with degree 2 to eliminate series candidates in \(O(1)\).  
  2. **Edge index**: group parallel edges with a map for constant-time lookup and reduction.  
  3. **Δ–Y transforms**: extend to networks that aren’t series-parallel by applying star-delta conversions.  
  4. **Parallel processing**: partition large graphs and reduce subgraphs concurrently.

---

<a name="conclusions"></a>
## 7 · Wrap-Up 📝

- **Graph-based reductions** automate collapsing of series and parallel resistors.  
- **NetworkX’s MultiGraph** API makes implementation straightforward and extensible.  
- The algorithm handles nested and complex topologies with predictable performance.  
- **Next steps**: integrate delta-wye, support voltage/current sources, and generalize to complex impedances.

---

<a name="references"></a>
## 8 · Further Reading 📚

1. Van Valkenburg — *Network Analysis*, Ch. 4: Graph Methods for Circuits  
2. Diestel — *Graph Theory*, §1.5: Reductions in Weighted Graphs  
3. NetworkX Documentation — “Series–Parallel Graph Reduction” example  
4. Dorogovtsev & Mendes — *Evolution of Networks*, §2.3: Electrical Network Models  
5. Ghosh et al. — “Graph-Theoretic Methods in Circuit Analysis,” *IEEE Transactions on Circuits and Systems* (2020)  
