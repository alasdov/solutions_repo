# 🏹 Problem 1 — Investigating the Range as a Function of the Angle of Projection

> *“There is nothing more practical than a good theory.”*  
> — Ludwig Boltzmann

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Default Audio Player</title>
</head>
<body>

<audio controls>
  <source src="https://files.catbox.moe/5zi95m.wav" type="audio/wav">
  Your browser does not support the audio element.
</audio>

</body>
</html>

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

<img src="https://i.imgur.com/xKOHmlJ.png" width="500">

<a name="limitations"></a>
## 6 · Model Limitations & Possible Extensions

| Assumption | Why It Matters | How to Relax / Extend |
| :--- | :--- | :--- |
| **No air resistance** | Real projectiles (balls, bullets, javelins) lose speed → range shortens, optimal angle shifts. | Add a drag term \(F_d = \frac{1}{2}\rho C_d A v^2\) and integrate ODEs numerically (`scipy.integrate.solve_ivp`). |
| **Constant \(g\)** | Gravity weakens with altitude; negligible for football, critical for rocketry. | Use \(g(h) = g_0 \left(\dfrac{R_\oplus}{R_\oplus + h}\right)^2\). |
| **Flat landing surface** | Many situations have uneven terrain (hills, cliffs, ski jumps). | Stop integration when \(y = y_{\text{terrain}}(x)\) from a DEM or analytic surface. |
| **No wind** | Crosswinds and tail/head winds deflect and stretch the path. | Add a horizontal acceleration term \(a_x = \tfrac{F_{\text{wind}}}{m}\). |
| **Point mass, no spin** | Back-spin/top-spin create Magnus lift; affects golf & baseball markedly. | Couple translational and rotational motion via lift force \(F_L \propto \omega \times v\). |

> **Tip:** Start with air drag only (quadratic), then layer other effects one by one; this keeps the code modular and easy to debug.

---

<a name="conclusions"></a>
## 7 · Conclusions

1. **Maximum range on level ground occurs at ≈ 45 °** when drag and launch height are negligible.  
2. **Range scales as \(v_0^2 / g\)**, so higher launch speeds and lower gravity (e.g., Moon) dramatically increase distance.  
3. **Non-zero launch/landing height skews the curve**: optimal angle drops if you start high and rises if you must clear a cliff.  
4. **Real-world design choices rarely use the textbook 45 °** because of drag, safety clearances, and target elevation.  
5. **Numerical tools bridge the gap between ideal equations and messy reality**, letting engineers tune launch angle, speed, and spin for specific goals.

---

<a name="references"></a>
## 8 · Further Reading

**1. J. B. Marion & S. T. Thornton — Classical Dynamics of Particles and Systems, Ch. 2.**  
[Google Books](https://books.google.com/books?id=HOqLQgAACAAJ)

**2. D. Halliday, R. Resnick & J. Walker — Fundamentals of Physics, 11th ed., §§ 4–5.**  
[Wikipedia](https://en.wikipedia.org/wiki/Fundamentals_of_Physics)

**3. NASA Glenn Research Center — “Projectile Motion with Drag” (interactive tutorial).**  
[NASA Glenn – Projectile Motion with Drag](https://www.grc.nasa.gov/www/k-12/airplane/projdrag.html)

**4. S. Brennen — Fundamentals of Multiphase Flow, § 0.6 “Motion with Quadratic Resistance.”**  
[Cambridge University Press](https://www.cambridge.org/core/books/fundamentals-of-multiphase-flow/FC7E6D7E54AC9D1C178EDF88D6A75FFF)

**5. R. Cross & A. M. Nathan — “Dynamics of Baseball: Influence of Air Drag and Magnus Effect,” Am. J. Phys. 76(10), 2008.**  
[AIP Publishing](https://pubs.aip.org/aapt/ajp/article/76/10/910/1057185)
