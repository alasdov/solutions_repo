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
## 5 · Python Implementation

Below is a compact, reusable script. Paste into a Jupyter notebook or `.py` file:

### 💻 Code ‒ Range vs Launch Angle (Earth, h = 0 m)

<details>
<summary>Click to view Python snippet</summary>

import numpy as np
import matplotlib.pyplot as plt

def time_of_flight(theta, v0, g=9.81, h=0.0):
    """Return total flight time for given θ (rad), v0, g, h."""
    vy = v0 * np.sin(theta)
    disc = vy**2 + 2 * g * h
    return (vy + np.sqrt(disc)) / g

def range_flat(theta, v0, g=9.81, h=0.0):
    """Horizontal range R(θ) for given parameters."""
    t = time_of_flight(theta, v0, g, h)
    return v0 * np.cos(theta) * t

# --- Parameters ------------------------------------------------------------
v0_list = [20, 30, 40]        # m/s
g_values = {"Earth": 9.81, "Moon": 1.62}
h = 0.0                       # launch height
theta = np.linspace(0, np.pi/2, 500)

# --- Plotting --------------------------------------------------------------
plt.figure(figsize=(8,5))
for v0 in v0_list:
    R = range_flat(theta, v0, g_values["Earth"], h)
    plt.plot(np.degrees(theta), R, label=f"v₀ = {v0} m/s")

plt.title("Range vs Launch Angle (Earth, h = 0 m)")
plt.xlabel("Launch angle θ (degrees)")
plt.ylabel("Range R (m)")
plt.legend()
plt.grid(True)
plt.show()
import matplotlib.pyplot as plt

def time_of_flight(theta, v0, g=9.81, h=0.0):
    """Return total flight time for given θ (rad), v0, g, h."""
    vy = v0 * np.sin(theta)
    disc = vy**2 + 2 * g * h
    return (vy + np.sqrt(disc)) / g

def range_flat(theta, v0, g=9.81, h=0.0):
    """Horizontal range R(θ) for given parameters."""
    t = time_of_flight(theta, v0, g, h)
    return v0 * np.cos(theta) * t

# --- Parameters ------------------------------------------------------------
v0_list = [20, 30, 40]        # m/s
g_values = {"Earth": 9.81, "Moon": 1.62}
h = 0.0                       # launch height
theta = np.linspace(0, np.pi/2, 500)

# --- Plotting --------------------------------------------------------------
plt.figure(figsize=(8,5))
for v0 in v0_list:
    R = range_flat(theta, v0, g_values["Earth"], h)
    plt.plot(np.degrees(theta), R, label=f"v₀ = {v0} m/s")

plt.title("Range vs Launch Angle (Earth, h = 0 m)")
plt.xlabel("Launch angle θ (degrees)")
plt.ylabel("Range R (m)")
plt.legend()
plt.grid(True)
plt.show()

</details> 