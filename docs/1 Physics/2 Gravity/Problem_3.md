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

<details open style="border:1px solid #bbb; padding:10px; border-radius:5px; background:#f9f9f9;">
<summary><strong>🔍 Governing Equations & Key Formulas</strong></summary>

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

Before diving into the simulation, it helps to know “which conic” you’re aiming for.

1. Compute specific energy  
   $$
   \varepsilon = \frac{v^2}{2} \;-\; \frac{G\,M}{r}.
   $$

2. Compute eccentricity  
   $$
   \mathbf{e}
     = \frac{\mathbf{v}\times(\mathbf{r}\times\mathbf{v})}{G\,M}
       \;-\; \frac{\mathbf{r}}{r},
   \quad
   e = \lVert \mathbf{e} \rVert.
   $$

3. Classify the path:  
   - If $\varepsilon < 0$ and $e < 1$, the trajectory is **elliptical** (bound).  
   - If $\varepsilon = 0$ and $e = 1$, the trajectory is **parabolic** (marginal escape).  
   - If $\varepsilon > 0$ and $e > 1$, the trajectory is **hyperbolic** (escape).  

The flowchart below then shows this decision process at a glance:

<img src="https://i.imgur.com/xqE2pB3.png" width="300">

<a name="implementation"></a>
## 4 · Code Playground 💻

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1gnPgdtP5c-d5Qyq4MSk7X2K-EFL1byAn?usp=sharing)

<img src="https://i.imgur.com/8s36wPD.png" width="600">

<a name="limitations"></a>
## 5 · Pro Tips & Limits ⚙️

**Build complexity step-by-step:**
1. **Atmospheric Drag & Heating**  
   - Add a quadratic drag force  
     \(\displaystyle F_{d} = \tfrac12\,\rho\,C_{d}\,A\,v^{2}\)  
   - Model thermal ablation to estimate reentry heating  

2. **3D Motion & Earth’s Rotation**  
   - Include Coriolis acceleration and \(J_{2}\) oblateness terms  
   - Simulate inclined release trajectories  

3. **Multi-Body Perturbations**  
   - Add the Moon’s and Sun’s gravity  
   - Switch to patched-conic or full N-body integration  

---

<a name="conclusions"></a>
## 6 · Wrap-up 📝

- **Specific energy** \(\varepsilon\) and **eccentricity** \(e\) dictate the trajectory type:  
  \(\varepsilon<0\) → ellipse, \(\varepsilon=0\) → parabola, \(\varepsilon>0\) → hyperbola.  
- **Small changes** in release velocity or angle can flip between bound orbit, reentry, or escape.  
- **Numerical integration** unifies all conic sections in one simulation framework.  
- **Next steps:** layer in drag, rotation, and third-body forces for mission-grade realism.  

---

<a name="references"></a>
## 7 · Dive Deeper 📚

1. Bate, Mueller & White — *Fundamentals of Astrodynamics*, Ch. 2 (Conic Sections).  
2. Vallado — *Fundamentals of Astrodynamics and Applications*, §3 (Orbit Propagation).  
3. Montenbruck & Gill — *Satellite Orbits: Models, Methods and Applications*, Ch. 4.  
4. Wertz — *Space Mission Analysis and Design*, Vol. 1, Ch. 5 (Trajectory Theory).  
5. NASA TP-2006-214224 — “Reentry Aerodynamics and Heat Transfer.”  
