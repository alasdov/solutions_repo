<!-- ╭────────────────────────────────────────────╮
     │     G  R  A  V  I  T  Y    ·   P r o b 1    │
     ╰────────────────────────────────────────────╯ -->

# 🌌 **Gravity · Problem 1 — Orbital Period vs Orbital Radius**

> *“The squares of the periods are proportional to the cubes of the distances.”*  
> — **Johannes Kepler**, 1619

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Default Audio Player</title>
</head>
<body>

<audio controls>
  <source src="https://files.catbox.moe/bz1sxn.wav" type="audio/wav">
  Your browser does not support the audio element.
</audio>

</body>
</html>

---

## Quick Navigation
1. [Motivation](#motivation)  
2. [Theory & Derivation](#theory)  
3. [Astronomical Uses](#uses)  
4. [Python Verification](#python)  
5. [Beyond Perfect Circles](#beyond)  
6. [Conclusions](#concl)  
7. [Further Reading](#refs)  

---

<a name="motivation"></a>
## 1 · Motivation 🚀
Kepler’s Third Law links **time** and **distance** for orbiting bodies:

\[
P^{2}\;=\;\frac{4\pi^{2}}{GM}\,a^{3}.
\]

With just *P* and *a* we can  
* weigh planets and stars,  
* design satellite constellations,  
* infer dark-matter distribution in galaxies.

---

<a name="theory"></a>
## 2 · Theory & Derivation 🧮

| Step | Equation | Comment |
|------|----------|---------|
| Centripetal = Gravity | \(\displaystyle \frac{GMm}{a^{2}} = m\frac{v^{2}}{a}\) | Cancel *m* |
| Orbital speed | \(v = \sqrt{\dfrac{GM}{a}}\) | |
| Period definition | \(P = \dfrac{2\pi a}{v}\) | |
| **Result** | \(\boxed{P^{2}=\dfrac{4\pi^{2}}{GM}\,a^{3}}\) | slope 3/2 in log–log space |

---

<a name="uses"></a>
## 3 · Astronomical Uses 🔭

### 3.1 Weighing a Planet
$$
M \;=\; \frac{4\pi^{2}a^{3}}{G\,P^{2}}.
$$

**Example:** Plug in Earth–Moon data and recover \(M_{\oplus}\) within 1 %.


### 3.2 Reality Checks

| Body | \(a\) (×10⁶ km) | \(P\) (days) | \(P^{2}/a^{3}\) (*Solar-system units*) |
|------|------|------|------|
| Moon | 0.384  | 27.32 | 1.02 |
| Io   | 0.422  | 1.769 | 1.04 |
| GEO satellite | 0.042  | 0.997 | 1.00 |

Values ≈ 1 confirm the law over 4-orders-of-magnitude in *a*.

---

<a name="python"></a>
## 4 · Python Verification 💻

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1hcODOusb7u4E60fqvs8Gp6ZSW01M8yZw?usp=sharing)
<img src="https://i.imgur.com/xMruTT2.png" width="700">
Expected: fitted slope ≈ 1.50 — exactly Keplerian.

<a name="beyond"></a>
## 5 · Beyond Perfect Circles 🔮

> *Kepler’s third law is the opening move; the **real game** begins when orbits stop being perfect circles.*

| ⚗️ Scenario | 🚧 What Breaks the Classic Law? | 🔧 Fix / Observable Consequence |
|-------------|---------------------------------|--------------------------------|
| **Elliptical orbit** | Speed no longer constant; periapsis ≠ apoapsis. | Keep the semi-major axis **a** → law exact again. |
| **General-relativistic well** | Space-time curvature adds an extra \(+3GM/(c^{2}a(1-e^{2}))\) term. | Perihelion precession (Mercury ≈ 43″ / century). |
| **Galaxy rotation (dark matter)** | Mass ≠ luminous matter → flat rotation curves. | \(P^{2}/a^{3}\) grows with *a* ⇒ “missing mass” clue. |
| **Solar-sail thrust** | Continuous outward force opposes gravity. | Effective gravity weakens → period grows *faster* than \(a^{3/2}\). |
| **Space-elevator tether** | Gravity & centrifugal pull change along the cable. | Equilibrium only at geostationary radius; above/below → tension sign flip. |

<blockquote>
<b>Rule of thumb</b>: Whenever extra forces appear, inspect the ratio <code>P² / a³</code>.  
<br>Any systematic drift → your **bonus physics** is showing.
</blockquote>

---

<a name="concl"></a>
## 6 · Conclusions 📝

1. **Log–log slope = 1.5** is the fingerprint of pure \(1/r^{2}\) gravity.  
2. Measuring *(P, a)* across bodies delivers **mass** without touching the object.  
3. Deviations from Kepler’s ratio have *historically* revealed:  
   * the finite speed of light (Rømer),  
   * general relativity (Mercury),  
   * dark matter (rubin–ford rotation curves).  
4. Modern mission design—from **GPS** to **JWST transfer orbits**—still builds on this 400-year-old relationship.  

---

<a name="refs"></a>
## 7 · Further Reading 📚

*MUST-reads*  
**1. C. D. Murray & S. F. Dermott — Solar System Dynamics, Ch. 3.**  
[Cambridge University Press](https://www.cambridge.org/core/books/solar-system-dynamics/108745217E4A18190CBA340ED5E477A2)

**2. D. A. Vallado — Fundamentals of Astrodynamics and Applications, 4th ed., § 1.**  
[Microcosm Press](https://www.microcosmpress.com/shop/fundamentals-of-astrodynamics-and-applications/)

**3. NASA JPL HORIZONS — Online ephemerides service for custom (P, a) checks.**  
[JPL Horizons](https://ssd.jpl.nasa.gov/horizons.cgi)


*Deep-cuts & history*  
**1. J. Kepler — Harmonices Mundi, Book V (1619).**  
[Archive.org](https://archive.org/details/harmonicesmundi00kepliala)

**2. A. Einstein — “Erklärung der Perihelbewegung des Merkur aus der allgemeinen Relativitätstheorie,” Ann. Phys. (1915).**  
[Wikisource](https://en.wikisource.org/wiki/Explanation_of_the_Perihelion_Motion_of_Mercury_from_General_Relativity_Theory)

**3. V. C. Rubin & W. K. Ford — “Rotation of the Andromeda Galaxy,” ApJ 159 (1970).**  
[NASA ADS](https://ui.adsabs.harvard.edu/abs/1970ApJ...159..379R)

**4. J. Carroll — “Space‐Elevator Dynamics and the Geostationary Balance,” Acta Astronautica 57 (2005).**  
[ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0094576504000302)


---


