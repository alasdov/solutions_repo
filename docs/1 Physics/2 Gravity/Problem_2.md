<!-- ╭────────────────────────────────────────────╮
     │   🚀  Gravity · Problem 2 — Escape Velocities & Cosmic Speeds   │
     ╰────────────────────────────────────────────╯ -->

# 🚀 **Gravity · Problem 2 — Escape Velocities & Cosmic Velocities**

> *“To break free, you only need to reach a speed—then gravity’s leash is cut.”*  
> — adapted from Arthur C. Clarke

---

## ✨ Table of Contents
1. [Motivation](#motivation)  
2. [Theoretical Foundation](#theory)  
3. [Analysis & Parameter Study](#analysis)  
4. [Python Implementation](#implementation)  
5. [Model Limitations & Extensions](#limitations)  
6. [Conclusions](#conclusions)  
7. [Further Reading](#references)  

---

<a name="motivation"></a>
## 1 · Motivation 🌍
Escape velocities define the **speed thresholds** at which a vehicle:
- **orbits** (1st cosmic velocity, *v₁*);
- **escapes** a planet to infinity (2nd cosmic velocity, *v₂*);
- **breaks free** of the entire star system (3rd cosmic velocity, *v₃*).  

Understanding these speeds is critical for satellite deployment, interplanetary missions, and future interstellar travel.

---

<a name="theory"></a>
## 2 · Theoretical Foundation 🔭

### 2.1 Definitions

For a body of mass \(M\) and radius \(R\):

- **First cosmic velocity** \(v_{1}\) (circular orbit speed):
  $$
  v_{1} = \sqrt{\frac{G\,M}{R}}
  $$

- **Second cosmic velocity** \(v_{2}\) (escape speed to infinity):
  $$
  v_{2} = \sqrt{\frac{2\,G\,M}{R}}
  $$

- **Third cosmic velocity** \(v_{3}\) (escape Sun from surface):
  $$
  v_{3}
    = \sqrt{\,v_{2}^{2} + v_{\mathrm{orb}}^{2}\,}
    = \sqrt{\frac{2\,G\,M}{R} \;+\;\frac{G\,M_{\odot}}{r_{\mathrm{orb}}}}
  $$

where the planet’s **orbital speed** around its star is
$$
v_{\mathrm{orb}}
  = \sqrt{\frac{G\,M_{\odot}}{r_{\mathrm{orb}}}}.
$$

### 2.2 Physical Meaning
- **v₁**: minimum speed for a circular orbit just above the surface.  
- **v₂**: minimum speed to reach infinity with zero kinetic energy remaining.  
- **v₃**: speed to leave the planet **and** the star system without further burns.

---

<a name="analysis"></a>
## 3 · Analysis & Parameter Study 📊

| Body    | Mass \(M\) (kg)  | Radius \(R\) (m) | \(v_1\) (km/s) | \(v_2\) (km/s) | \(v_3\) (km/s) |
|:-------:|:----------------:|:----------------:|:-------------:|:-------------:|:-------------:|
| Earth   | 5.972×10²⁴        | 6.371×10⁶        | 7.91          | 11.19         | ~16.70        |
| Mars    | 6.39×10²³         | 3.390×10⁶        | 3.56          | 5.03          | ~8.50         |
| Jupiter | 1.898×10²⁷        | 6.991×10⁷        | 41.7          | 59.1          | ~70.0         |

> **Insight:**  
> - Ratio \(v_2/v_1=\sqrt2\) always.  
> - Third velocity depends on both planetary and stellar gravity.

---

<a name="implementation"></a>
## 4 · Python Implementation — Interactive Notebook 💻

Run or tweak in Google Colab:

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1rFsWxytZ1PumFesCLQF3qKRaPFaX3K8d?usp=sharing)

<img src="https://i.imgur.com/A1HkS8t.png" width="600">

<a name="limitations"></a>
## 5 · Model Limitations & Extensions ⚙️

| Assumption           | Impact                                 | Extension                                  |
|:---------------------|:---------------------------------------|:-------------------------------------------|
| **No atmosphere**    | Overestimates \(v_1, v_2\) in real launches | Add atmospheric drag model & integrate trajectory numerically |
| **Perfect sphere**   | Ignores oblateness & planetary rotation | Include \(J_2\) perturbation and Coriolis terms |
| **Instantaneous burn** | Single impulse for \(v_3\); neglects multi-stage and gravity assists | Simulate multi-stage rockets & patched-conic transfers |
| **Newtonian gravity** | No relativistic correction near massive bodies | Implement General Relativity corrections for deep-gravity regimes |

> **Tip:** Build your model in layers—start vacuum, then add drag, then rotation/oblateness, then multi-body effects.

---

<a name="conclusions"></a>
## 6 · Conclusions 📝

1. **First cosmic velocity** \(v_1 = \sqrt{GM/R}\) sets the bar for low-orbit insertion.  
2. **Second cosmic velocity** \(v_2 = \sqrt{2GM/R}\) is the escape threshold to infinity.  
3. **Third cosmic velocity** \(v_3\) combines planetary and solar escape—crucial for interplanetary departure.  
4. Real-world factors (atmosphere, spin, assist maneuvers) can shift these speeds by up to 20 %.  
5. Mastery of cosmic velocities underpins successful mission design, from satellites to probes.

---

<a name="references"></a>
## 7 · Further Reading 📚

**1. R. R. Bate, D. D. Mueller & J. E. White — Fundamentals of Astrodynamics, Ch. 3.**  
[Google Books](https://books.google.com/books?id=UtJK8cetqGkC)

**2. D. A. Vallado — Fundamentals of Astrodynamics and Applications, §§ 2–3.**  
[Microcosm Press](https://www.microcosmpress.com/shop/fundamentals-of-astrodynamics-and-applications/)

**3. W. H. Prussing & B. A. Conway — Orbital Mechanics, Ch. 4 (Cosmic Velocities & Gravity Assists).**  
[SpringerLink](https://link.springer.com/book/10.1007/978-1-4612-1140-2)

**4. NASA Technical Report — “Atmospheric Drag Effects on Launch Vehicles.”**  
[NTRS](https://ntrs.nasa.gov/citations/20200002975)

**5. Eric W. Weisstein — “Escape Velocity,” MathWorld.**  
[MathWorld](https://scienceworld.wolfram.com/physics/EscapeVelocity.html)
