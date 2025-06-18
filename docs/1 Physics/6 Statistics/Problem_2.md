<!-- ╭───────────────────────────────────────────────────────────╮
     │     🎲 Statistics · Problem 2 — Estimating π via Monte Carlo    │
     ╰───────────────────────────────────────────────────────────╯ -->

# 🎲 **Problem 2: Estimating π using Monte Carlo Methods**

> *“From random dots and falling needles, emerges the magic of π.”*  

---

## 📋 Table of Contents
1. [Motivation 🎯](#motivation)  
2. [Theoretical Foundation 🔭](#theory)  
   - 2.1 [Circle Method](#circle-theory)  
   - 2.2 [Buffon’s Needle](#buffon-theory)  
3. [Simulation Design 🔍](#design)  
4. [Python Implementation 💻](#implementation)  
   - 4.1 [Circle Method Code](#circle-code)  
   - 4.2 [Buffon’s Needle Code](#buffon-code)  
5. [Model Limitations & Extensions ⚙️](#limitations)  
6. [Results & Interpretation 🧩](#interpretation)  
7. [Conclusions 📝](#conclusions)  
8. [Further Reading 📚](#references)  

---

<a name="motivation"></a>
## 1 · Motivation 🎯
Monte Carlo methods use randomness to estimate deterministic values.  
Estimating π via:

- **Geometric probability** (points in a circle vs square).  
- **Buffon’s Needle** (probability of crossing lines).  

These illustrate how simple random experiments converge to known constants, with applications in physics, finance, and beyond.

---

<a name="theory"></a>
## 2 · Theoretical Foundation 🔭

<a name="circle-theory"></a>
### 2.1 Circle Method
Embed a unit circle (\(r=1\)) in the square \([-1,1]\times[-1,1]\).  
- Area(circle) = π·1² = π  
- Area(square) = 4  
If \(N_{\text{in}}\) of \(N\) random points fall inside the circle,  
$$
\frac{N_{\text{in}}}{N} \approx \frac{\pi}{4}
\quad\Longrightarrow\quad
\pi \approx 4\;\frac{N_{\text{in}}}{N}.
$$

<a name="buffon-theory"></a>
### 2.2 Buffon’s Needle
Drop a needle of length \(L\) onto a plane ruled by parallel lines distance \(d\) apart (\(L\le d\)).  
The probability of crossing a line is  
$$
P_{\text{cross}}
= \frac{2L}{\pi\,d}.
$$
If \(N_{\text{cross}}\) of \(N\) drops cross a line,  
$$
\frac{N_{\text{cross}}}{N} \approx \frac{2L}{\pi d}
\quad\Longrightarrow\quad
\pi \approx 2L \;\frac{N}{d\,N_{\text{cross}}}.
$$

---

<a name="design"></a>
## 3 · Simulation Design 🔍
1. **Circle Method**  
   - Generate \(N\) points \((x,y)\sim U([-1,1]^2)\).  
   - Count points with \(x^2+y^2\le1\).  
   - Estimate π for \(N\) ranging from \(10^3\) to \(10^6\).  
2. **Buffon’s Needle**  
   - Set \(L=1\), \(d=2\).  
   - For each drop:  
     - Sample center distance \(x\sim U[0,d/2]\).  
     - Sample angle \(\theta\sim U[0,\pi]\).  
     - Crosses if \(x \le (L/2)\sin\theta\).  
   - Estimate π for \(N\) from \(10^3\) to \(10^6\).  
3. **Visualization & Analysis**  
   - Plot estimates vs \(N\) on log–log scale.  
   - Show scatter of points (circle) and needles (Buffon).  

---

<a name="implementation"></a>
## 4 · Python Implementation 💻

<a name="circle-code"></a>
### 4.1 Circle Method Code

```python
import numpy as np
import matplotlib.pyplot as plt

def estimate_pi_circle(N):
    x = np.random.uniform(-1, 1, N)
    y = np.random.uniform(-1, 1, N)
    inside = (x*x + y*y) <= 1
    return 4 * inside.sum() / N

# run for increasing N
Ns = [10**3, 10**4, 10**5, 10**6]
pi_est = [estimate_pi_circle(N) for N in Ns]

plt.figure(figsize=(6,4))
plt.loglog(Ns, np.abs(np.array(pi_est) - np.pi), 'o-', basex=10, basey=10)
plt.xlabel('Number of samples N')
plt.ylabel('|π_est − π|')
plt.title('Circle Method Convergence')
plt.grid(True, which='both', ls=':')
plt.show()
