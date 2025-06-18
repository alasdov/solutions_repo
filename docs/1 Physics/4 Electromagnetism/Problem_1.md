<!-- ╭──────────────────────────────────────────────────────╮
     │  🔌 Electromagnetism · Problem 1 — Lorentz Force Simulation │
     ╰──────────────────────────────────────────────────────╯ -->

# 🔌 **Problem 1: Simulating the Effects of the Lorentz Force**

> *“Charge in motion under E and B fields reveals nature’s most elegant spirals and drifts.”*  

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Default Audio Player</title>
</head>
<body>

<audio controls>
  <source src="https://files.catbox.moe/thoh9b.wav" type="audio/wav">
  Your browser does not support the audio element.
</audio>

</body>
</html>

---

## 📋 Table of Contents
1. [Motivation 🎯](#motivation)  
2. [Theory & Equations 🔭](#theory)  
3. [Scenarios & Parameter Study 🔍](#scenarios)  
4. [Python Implementation 💻](#implementation)  
5. [Model Limitations & Extensions ⚙️](#limitations)  
6. [Results & Interpretation 🧩](#interpretation)  
7. [Conclusions 📝](#conclusions)  
8. [Further Reading 📚](#references)  

---

<a name="motivation"></a>
## 1 · Motivation 🎯
The **Lorentz force**,
\[
\mathbf{F} = q\,\bigl(\mathbf{E} + \mathbf{v}\times\mathbf{B}\bigr),
\]
governs charged‐particle dynamics in fields.  
Simulating these trajectories lets us:

- Understand **cyclotron** and **helix** motion in uniform \(\mathbf{B}\).  
- Explore **\(\mathbf{E}\times\mathbf{B}\) drift** and **magnetic mirroring**.  
- Apply to real devices: **cyclotrons**, **mass spectrometers**, **magnetic traps**.

---

<a name="theory"></a>
## 2 · Theory & Equations 🔭

### 2.1 Equation of Motion  
\[
m\frac{d\mathbf{v}}{dt}
 = q\bigl(\mathbf{E} + \mathbf{v}\times\mathbf{B}\bigr),
\quad
\frac{d\mathbf{r}}{dt} = \mathbf{v}.
\]

### 2.2 Key Relations
- **Cyclotron frequency**: \(\displaystyle \omega_c = \frac{qB}{m}\).  
- **Larmor radius**: \(\displaystyle r_L = \frac{v_\perp}{\omega_c}\).  
- **\(\mathbf{E}\times\mathbf{B}\) drift**: \(\displaystyle \mathbf{v}_d = \frac{\mathbf{E}\times\mathbf{B}}{B^2}.\)

---

<a name="scenarios"></a>
## 3 · Scenarios & Parameter Study 🔍

| Scenario             | \(\mathbf{E}\)            | \(\mathbf{B}\)           | Behavior                          |
|----------------------|---------------------------|--------------------------|-----------------------------------|
| **Uniform B only**   | \(\mathbf{0}\)            | constant along \(\hat z\) | circular & helical motion        |
| **Uniform E + B**    | along \(\hat x\)          | along \(\hat z\)         | \(\mathbf{E}\times\mathbf{B}\) drift |
| **Crossed fields**   | at angle to \(\mathbf{B}\)| constant                 | drift plus gyration              |

**Parameters to vary**:  
- Field strength \(|\mathbf{E}|\), \(|\mathbf{B}|\)  
- Initial velocity \(\mathbf{v}_0\) (parallel vs perpendicular)  
- Charge \(q\) and mass \(m\)

---

<a name="implementation"></a>
## 4 · Python Implementation 💻

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1WR2jmQMNRYqvzfILJa0BtHhbyFR1IbeX?usp=sharing)

<img src="https://i.imgur.com/A2rLSc1.png" width="600">

<a name="limitations"></a>
## 5 · Model Limitations & Extensions ⚙️

| Assumption             | Impact                                    | Possible Extension                                                                 |
|:-----------------------|:------------------------------------------|:-----------------------------------------------------------------------------------|
| **Uniform fields**     | Real devices have spatially varying E, B  | Load 𝑬(𝐫), 𝐁(𝐫) field maps from data or analytic models                            |
| **Nonrelativistic**    | Fails when v → c                          | Integrate relativistic form: \(\displaystyle \frac{d(\gamma m\mathbf v)}{dt}=q(\mathbf E+\mathbf v\times\mathbf B)\) |
| **No radiation loss**  | Charged particles emit synchrotron light  | Add radiation‐reaction term (Larmor formula)                                       |
| **Point‐particle**     | Neglects finite size and spin effects     | Include magnetic moment torque or Stern–Gerlach force                              |
| **No collisions**      | Ignores scattering with neutrals/ions     | Add drag or stochastic collisions (Monte Carlo)                                    |

> **Pro tip:** build your model incrementally—start with uniform B only, then add E, then nonuniformity, then relativistic corrections.

---

<a name="interpretation"></a>
## 6 · Results & Interpretation 🧩

- **Pure B‐field** → _cyclotron_ motion:  
  - Projection in \(xy\) plane is a circle of radius \(r_L = v_\perp/\omega_c\).  
  - Center offset at \((0,-r_L)\) when starting at origin with \(v_x>0\).  
- **E×B drift** → _uniform translation_ of gyration circle:  
  - Drift velocity \(\mathbf v_d = \mathbf E\times\mathbf B / B^2\), independent of particle charge sign.  
- **Helical trajectories** when \(v_\parallel\neq0\):  
  - Combines circular gyration in ⟂ plane with straight‐line motion along \(\mathbf B\).  
- **Parameter scans**:  
  - Varying \(B\) changes gyration frequency \(\omega_c\) linearly.  
  - Varying \(E\) controls drift speed linearly.  

Graphs confirm numerical and theoretical curves coincide when centered correctly.

---

<a name="conclusions"></a>
## 7 · Conclusions 📝

1. **[Lorentz force](https://en.wikipedia.org/wiki/Lorentz_force)** produces rich dynamics: circular, helical, and drifting orbits.  
   [Wikipedia: Lorentz force](https://en.wikipedia.org/wiki/Lorentz_force)

2. **Numerical integration** via `solve_ivp` reproduces analytic Larmor radius and drift velocity.  
   [SciPy `solve_ivp` documentation](https://docs.scipy.org/doc/scipy/reference/generated/scipy.integrate.solve_ivp.html)

3. **Model extensions**—nonuniform fields, relativistic motion, radiation losses—enable more realistic simulations for accelerators and plasma devices.  
   [Wikipedia: Charged particle motion](https://en.wikipedia.org/wiki/Charged_particle)

4. **Takeaway**: combining theory and computation gives both quantitative accuracy and intuitive insight into charged-particle motion.  
   [Wikipedia: Computational physics](https://en.wikipedia.org/wiki/Computational_physics)
