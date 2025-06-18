# 🔄 Problem 2 — Investigating the Dynamics of a Forced Damped Pendulum

> *“Chaos often breeds life, when order breeds habit.”*  
> — Henry Adams  

---

## Table of Contents
1. [Motivation](#motivation)  
2. [Theoretical Foundation](#theory)  
3. [Dynamics & Parameter Study](#dynamics)  
4. [Practical Applications](#applications)  
5. [Python Implementation](#implementation)  
6. [Model Limitations & Possible Extensions](#limitations)  
7. [Conclusions](#conclusions)  
8. [Further Reading](#references)  

---

<a name="motivation"></a>
## 1 · Motivation
The *forced damped pendulum* fuses three key effects—restoring torque, viscous damping, and periodic driving.  
By tuning the driving amplitude **F** and frequency **ω<sub>d</sub>**, one observes:

* **Linear resonance** (small angles).  
* **Beats & quasiperiodicity**.  
* **Deterministic chaos** (period-doubling route).  

These behaviours underpin engineering challenges (vibration isolation, power harvesting) and inspire analogies in climate science and electronics.

---

<a name="theory"></a>
## 2 · Theoretical Foundation

### 2.1 Governing Equation
For a pendulum of length *L*, mass *m*, damping γ, and periodic torque **F cos (ω<sub>d</sub>t)**:

\[
\boxed{\;
\ddot{\theta} + 2\gamma\,\dot{\theta} + \frac{g}{L}\sin\theta
  \;=\; \frac{F}{mL}\cos(\omega_{d} t)
\;}
\]

Define  
\( \omega_0 = \sqrt{g/L} \), \(A=\dfrac{F}{mL}\).

### 2.2 Small-Angle Approximation (|θ| ≪ 1)
Replace \(\sin\theta \approx \theta\):

\[
\ddot{\theta} + 2\gamma\,\dot{\theta} + \omega_0^{2}\,\theta
  = A\cos(\omega_{d} t).
\]

This linear ODE has steady-state solution

\[
\theta_{\text{ss}}(t)=
 \frac{A}{\sqrt{(\omega_0^{2}-\omega_d^{2})^{2}+4\gamma^{2}\omega_d^{2}}}
 \cos\!\bigl(\omega_d t-\phi\bigr),
\]
with phase lag  
\(\tan\phi=\dfrac{2\gamma\omega_d}{\omega_0^{2}-\omega_d^{2}}\).

### 2.3 Resonance
* **Amplitude peak** at  
  \(\displaystyle \omega_{d,\text{res}}=\sqrt{\omega_0^{2}-2\gamma^{2}}\).
* **Quality factor** \(Q=\omega_0/(2\gamma)\) governs sharpness.

Beyond small angles, non-linearity shifts and bends the resonance curve (“backbone curve”).

---

<a name="dynamics"></a>
## 3 · Dynamics & Parameter Study

| Parameter | Effect on Motion |
|-----------|------------------|
| **γ (damping)** | High γ → overdamped decay; moderate γ → sharp resonance; low γ → sustained large oscillations and chaos when driven. |
| **A (driving amplitude)** | Small A → linear response; large A → period-doubling, intermittent chaos. |
| **ω<sub>d</sub> (drive freq.)** | Near ω₀: resonance; irrational ratio ω<sub>d</sub>/ω₀ → quasi-periodicity; wide scan reveals Feigenbaum cascade. |
| **Initial θ, \(\dot θ\)** | Sensitive dependence in chaotic regime; tiny changes → divergent long-time trajectories. |

**Key visual diagnostics**

1. **Time series θ(t).**  
2. **Phase portrait (θ vs \(\dot θ\)).**  
3. **Poincaré section** (stroboscopic map, one point per drive period).  
4. **Bifurcation diagram**: peak θ vs ω<sub>d</sub> or A.  

---

<a name="applications"></a>
## 4 · Practical Applications
- **Rotary energy harvesters** (pendulum converts building sway → electricity).  
- **Suspension bridges & skyscrapers** (tuned mass dampers = driven pendula).  
- **Driven RLC circuits** (mathematically identical to forced pendulum).  
- **Biomechanics** — modelling human gait under rhythmic forcing.  
- **Clocks & metronomes** — synchronisation and limit-cycle locking.

---

<a name="implementation"></a>
## 5 · Python Implementation — Interactive Notebook

Run or tweak the full simulation in Google Colab:

[![Open in Colab](https://colab.research.google.com/drive/17Yx0rQYcFZwqm67f8Gf-BKdRw7pbXefR?usp=sharing)

<img src="https://i.imgur.com/TwQpBJR.png" width="350">


