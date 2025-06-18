<!-- ╭──────────────────────────────────────────────╮
     │     G  R  A  V  I  T  Y    ·   P r o b 1     │
     ╰──────────────────────────────────────────────╯ -->

# 🌌 **Gravity · Problem 1 — Orbital Period vs Orbital Radius**

> **Kepler’s whisper:**  
> *“The squares of the times are as the cubes of the distances.”*

---

<div align="center">

| ⏱️  |  **TOC—Jump Drive** |
|:---:|:--------------------------------------------------------|
| 1 | [Why we care](#motivation) |
| 2 | [Derivation ☕](#theory) |
| 3 | [Astronomy Impact](#implications) |
| 4 | [Reality Check 👁️](#examples) |
| 5 | [Python Sandbox 💻](#implementation) |
| 6 | [Beyond Circles 🔮](#extensions) |

</div>

---

<a name="motivation"></a>
## 1 · Why we care 🚀

Kepler’s 3rd Law stitches together **time** and **distance** in the cosmic dance.  
With it, we:

* weigh planets without a scale,  
* triangulate exoplanets light-years away,  
* schedule GPS satellites to the millisecond.

<blockquote>
<b>Mnemonic</b> · “<i>P</i><sup>2</sup> ∝ <i>a</i><sup>3</sup>” — *Period squares marry radius cubes.*
</blockquote>

---

<a name="theory"></a>
## 2 · Derivation ☕ <sup>(click to expand)</sup>

<details>
<summary><strong>Show full math</strong></summary>

### 2.1 Force balance

\[
\frac{G M m}{a^{\,2}} = m\frac{v^{2}}{a}
\qquad\Longrightarrow\qquad
v = \sqrt{\frac{G M}{a}}
\]

### 2.2 Period–radius link  
\(P = \dfrac{2\pi a}{v}\) ⇒

\[
\boxed{P^{2} = \frac{4\pi^{2}}{GM}\;a^{3}}
\]

**Take-away:** slope in log–log space is *exactly* **3 ⁄ 2**.
</details>

---

<a name="implications"></a>
## 3 · Astronomy Impact 🔭

| 🛠️ Use-case | How P² ≈ a³ helps |
|--------------|------------------|
| **Weighing planets** | Rearranging yields \(M = \tfrac{4\pi^{2}a^{3}}{G P^{2}}\). |
| **Measuring stellar mass in binaries** | Observe \(P,a\) of the dance → derive total mass. |
| **Mapping the Solar System** | Early astronomers used Jupiter’s moons as celestial “meters & seconds”. |

> **Fun-fact:** the law survived relativity tweaks — only the prefactor changes for strong gravity.

---

<a name="examples"></a>
## 4 · Reality Check 👁️ — Two quick plots

<details open>
<summary><strong>Mermaid sketch of Solar‐System log–log fit</strong></summary>

```mermaid
%% Just a static illustration (not a data plot)
graph LR
  subgraph log(P) vs log(a)
    A["Mercury"] --> B["Venus"] --> C["Earth"] --> D["Mars"]-->E["Jupiter"]
  end
  classDef dotted stroke-dasharray: 3 3;
  class A,B,C,D,E dotted;

### The Moon 🌙 — sanity-check

| Parameter | Symbol | Value | Source |
|-----------|:------:|-------|--------|
| Mean orbital radius | \(a\) | 384 400 km | JPL DE431 |
| Sidereal period | \(P\) | 27.321 d | IAU 2009 |
| Kepler ratio | \(\dfrac{P^{2}}{a^{3}}\) | \(1.02\) × solar-system mean | ✅ within 2 % |

*Computation:*  
\[
\frac{P^{2}}{a^{3}}
 = \frac{(27.321/365.25)^{2}}{(0.00257)^{3}} ≈ 1.02.
\]

---

### Jupiter’s Io 🌋 — second datapoint

| Parameter | Symbol | Value |
|-----------|:------:|-------|
| \(a\) | 421 800 km |
| \(P\) | 1.769 d |
| \(\dfrac{P^{2}}{a^{3}}\) | 1.04 (again < 5 % drift) |

The near-unity ratios confirm the *P² ∝ a³* law across wildly different scales.

---

<a name="implementation"></a>
## 5 · Python Sandbox 💻 — Test the Law

> *Aim:* sweep artificial satellites from LEO to GEO, fit slope in log–log space, and verify it lands on **1.5**.

```python
import numpy as np, matplotlib.pyplot as plt
from scipy.stats import linregress

G, M_earth = 6.6743e-11, 5.972e24

# radii 1–6 Earth radii
a = np.linspace(6.371e6, 6*6.371e6, 24)
P = 2*np.pi*np.sqrt(a**3 / (G*M_earth))      # s

# linear fit in log-space
slope, intercept, *_ = linregress(np.log10(a), np.log10(P))

plt.figure(figsize=(6,4), dpi=110)
plt.loglog(a/6.371e6, P/3600, 'o', label='synthetic orbits')
plt.loglog(a/6.371e6,
           10**intercept * (a)**slope / 3600,
           '--', label=f'fit: slope={slope:.2f}')
plt.xlabel('Radius ($R_⊕$)')
plt.ylabel('Period (h)')
plt.title('Kepler fit for circular Earth orbits')
plt.grid(True, which='both', ls=':')
plt.legend(); plt.show()

<a name="extensions"></a>
## 6 · Beyond Circles 🔮 — Where Kepler Bends

> *Quick peek at “edge-cases” where the classic **P² ∝ a³** needs extra seasoning.*

| Scenario | What changes? | One-liner take-away |
|----------|---------------|---------------------|
| **Elliptical orbits** | Replace “radius” with **semi-major axis a**; law still exact. | Planet speeds up at periapsis, slow at apoapsis, *but* average obeys Kepler. |
| **General Relativity** | Space-time curvature tweaks central force. | P² ∝ a³ holds to 1st order; higher order gives Mercury’s 43″/century shift. |
| **Dark-matter halos** | Extra unseen mass flattens galaxy rotation curves. | Observed P²/a³ grows with radius → evidence for DM. |
| **Ringworld / space elevator** | Non-point-mass gravity + tether tension. | Effective gravity varies → “sweet spot” at geostationary radius. |
| **Non-Keplerian (solar sail)** | Continuous thrust adds outward force. | Period increases faster than a³ — sail orientation tunes orbit. |

<blockquote>
<b>Designer tip</b> · Treat <code>P²/a³</code> as a “fingerprint”-ratio: deviations shout “new physics or extra forces”.
</blockquote>

---

<a name="references"></a>
## 7 · Further Reading 📚

1. **C. Murray & S. Dermott** — *Solar System Dynamics*, Chs. 2–3.  
2. **D. Vallado** — *Fundamentals of Astrodynamics and Applications*, §1 (Keplerian motion).  
3. **A. Einstein** — “Explanation of the Perihelion Motion of Mercury,” *Annalen der Physik* (1915).  
4. **V. Rubin & W. Ford** — “Rotation of the Andromeda Galaxy,” *ApJ* 159, 379 (1970) — dark-matter clue.  
5. **NASA JPL HORIZONS** — online ephemeris to verify P, a for any body.  
6. **J. Carroll** — “Space Elevators and the Geostationary Balance,” *Acta Astronautica* 57 (2005).  

---
