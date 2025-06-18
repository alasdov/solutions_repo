<!-- ╭──────────────────────────────────────────────────────╮
     │  🔌 Electromagnetism · Problem 1 — Lorentz Force Simulation │
     ╰──────────────────────────────────────────────────────╯ -->

# 🔌 **Problem 1: Simulating the Effects of the Lorentz Force**

> *“Charge in motion under E and B fields reveals nature’s most elegant spirals and drifts.”*  

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

