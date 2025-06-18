# 🏹 Problem 1 — Investigating the Range as a Function of the Angle of Projection

> *“There is nothing more practical than a good theory.”*  
> — Ludwig Boltzmann

---

## Table of Contents
1. [Motivation](#motivation)  
2. [Theoretical Foundation](#theory)  
3. [Range–Angle Analysis](#analysis)  
4. [Practical Applications](#applications)  
5. [Python Implementation](#implementation)  
6. [Model Limitations & Possible Extensions](#limitations)  
7. [Conclusions](#conclusions)  
8. [Further Reading](#references)  

---

<a name="motivation"></a>
## 1 · Motivation
Projectile motion is deceptively simple: a body launched with an initial velocity **v₀** under gravity **g** follows a parabolic path.  
Yet, by tweaking parameters—launch angle **θ**, speed **v₀**, height **h**—we unlock a rich family of solutions that apply to sports, engineering, and astronautics.  
Our goal: **quantify how the horizontal range _R_ depends on the launch angle** and explore how other parameters reshape that relationship.

---

<a name="theory"></a>
## 2 · Theoretical Foundation

### 2.1 Equations of Motion
Assuming no air resistance and constant gravity:

\[
\begin{aligned}
x(t) &= v_0\cos\theta \; t \\[4pt]
y(t) &= h + v_0\sin\theta \; t - \frac{1}{2}gt^{2}.
\end{aligned}
\]

### 2.2 Time of Flight (landing at \(y=0\))
Solve \(y(t)=0\):

\[
t_{\text{flight}}
  = \frac{v_0\sin\theta}{g}
    \bigl[1+\sqrt{1+2gh/(v_0^2\sin^2\theta)}\,\bigr].
\]

For level ground (\(h=0\)), this reduces to \(t_{\text{flight}} = \dfrac{2v_0\sin\theta}{g}\).

### 2.3 Horizontal Range
$$R(\theta) = v_0\cos\theta \, t_{\text{flight}}.$$

On level ground:

\[
\boxed{\,R(\theta) = \frac{v_0^{2}\sin(2\theta)}{g}\,}.
\]

---

<a name="analysis"></a>
## 3 · Range–Angle Analysis

| Aspect | Key Result |
| :--- | :--- |
| **Optimal angle (flat ground)** | \( \theta_\text{max} = 45^\circ \) where \( \sin(2\theta)=1 \). |
| **Symmetry** | \(R(\theta)=R(90^\circ-\theta)\). |
| **Effect of \(v_0\)** | \(R \propto v_0^2\). Doubling speed quadruples range. |
| **Effect of \(g\)** | Inverse: \(R \propto 1/g\). The same launch on the Moon (\(g\approx1/6\,g_\oplus\)) travels ~6× farther. |
| **Non-zero \(h\)** | Skews curve; optimal angle < 45° if launching from height, > 45° if landing on a cliff. |

**Visual Roadmap**

1. Plot \(R(\theta)\) for a baseline case (e.g., \(v_0=30\text{ m/s}, h=0\)).  
2. Overlay curves for different \(v_0\) values.  
3. Overlay curves for Earth vs Moon gravity.  
4. Highlight the shift when \(h \neq 0\).

---

<a name="applications"></a>
## 4 · Practical Applications
- **Sports** · Soccer kicks, javelin throws, basketball arcs.  
- **Engineering** · Artillery targeting, water-jet fountains.  
- **Astrodynamics** · Low-speed lander hops on the Moon or Mars.  
- **Terrain Variations** · Ski-jump design, drone delivery from rooftops.  
- **With Drag/Wind** · Ballistics tables, golf club selection.

---

<a name="implementation"></a>

## 5 · Python Implementation — Interactive Notebook

Run or tweak the full code interactively in Google Colab:

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1uAEP93nZ4RhJKgKYPPJQxNHYy_3Xo81w?usp=sharing)

![Optimal-angle sketch](https://i.imgur.com/xKOHmlJ.png)
