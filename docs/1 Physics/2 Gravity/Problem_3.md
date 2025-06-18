<!-- ╭────────────────────────────────────────────────╮
     │   🚀  Gravity · Problem 3 — Payload Trajectories Near Earth   │
     ╰────────────────────────────────────────────────╯ -->

# 🚀 **Problem 3: Payload Trajectories Near Earth**

> *“What path will a payload carve once released from its rocket under Earth's pull?”*  

---

## 📋 Quick Navigation
1. [Motivation 🎯](#motivation)  
2. [Equations & Insights 🔭](#theory)  
3. [Conic Classifier 🔍](#classifier)  
4. [Code Playground 💻](#implementation)  
5. [Pro Tips & Limits ⚙️](#limitations)  
6. [Wrap-up 📝](#conclusions)  
7. [Dive Deeper 📚](#references)  

---

<a name="motivation"></a>
## 1 · Motivation 🎯  
> **Imagine** releasing a payload mid-flight from a rocket…  
> Its path isn’t just a simple parabola but a showcase of gravitational dynamics.

- **Why it matters:**  
  - Controlled reentry of cargo capsules  
  - Deployment of scientific probes  
  - Safe return of samples  

---

<a name="theory"></a>
## 2 · Equations & Insights 🔭

<details>
<summary>Show governing equations</summary>

1. **Newton’s law of gravitation**  
   \[
     \mathbf{F} = -\frac{G\,M\,m}{r^{2}}\,\hat{\mathbf{r}}
   \]

2. **Equation of motion**  
   \[
     \ddot{\mathbf{r}} = -\frac{GM}{r^{3}}\,\mathbf{r}
   \]

3. **Specific mechanical energy**  
   \[
     \varepsilon = \frac{v^{2}}{2} \;-\; \frac{GM}{r}
   \]

4. **Eccentricity vector**  
   \[
     \mathbf{e}
     = \frac{\mathbf{v}\times(\mathbf{r}\times\mathbf{v})}{GM}
       - \frac{\mathbf{r}}{r},
     \quad
     e = \|\mathbf{e}\|.
   \]
</details>

> **🔑 Key insight:**  
> - \(\varepsilon<0\) ⇒ bound (ellipse)  
> - \(\varepsilon=0\) ⇒ parabolic (escape)  
> - \(\varepsilon>0\) ⇒ hyperbolic (escape)

---

<a name="classifier"></a>
## 3 · Conic Classifier 🔍

```mermaid
flowchart LR
    A["ε < 0"] -->|e < 1| Elliptical
    B["ε = 0"] -->|e = 1| Parabolic
    C["ε > 0"] -->|e > 1| Hyperbolic
