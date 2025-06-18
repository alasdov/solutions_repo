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

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/16ojbD2UqaF1AYzHL1bXiqGTjtT-Qkez9?usp=sharing)

<img src="https://i.imgur.com/KUiB4ND.png" width="1100">

### Visualization of points (for N = 5000)

Below is a scatter plot of 5 000 uniformly distributed points in the square \([-1,1]^2\).  
- **Blue dots** lie inside the unit circle \(x^2 + y^2 \le 1\).  
- **Red dots** lie outside.  

This visual shows why the fraction of blue points \(\approx \pi/4\), and hence \(\pi \approx 4\times(\text{blue}/\text{total})\).


[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1PGlkydYWFW6sKodH___m4eGnBinE6jgF?usp=sharing)

<img src="https://i.imgur.com/A7IWBXR.png" width="1100">

<a name="buffon-code"></a>

### 4.2 Buffon’s Needle Code

Below is a Python implementation of Buffon’s Needle experiment. We drop needles of length \(L=1\) onto a plane with parallel lines spaced \(d=2\) apart and count the fraction that cross a line to estimate π via

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1DK-rE7nJ60-pl5KPTfysorc9fc7IYYQN?usp=sharing)

<img src="https://i.imgur.com/XKlpNM9.png" width="1100">

#### Visualization of needle drops (for N = 200)

The plot below shows 200 random needle drops on a plane ruled by horizontal lines spaced at distance \(d=2\).  
- **Red needles** cross one of the lines.  
- **Blue needles** do not cross.  

This illustrates how the fraction of crossings relates to the theoretical probability \(P = \tfrac{2L}{\pi d}\).

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/15FWyZj728dCV547V_PAjE8CQeavfa1An?usp=sharing)

<img src="https://i.imgur.com/6hOK11f.png" width="1100">

<a name="limitations"></a>
## 5 · Model Limitations & Extensions ⚙️

- **Convergence rate**: both estimators have Monte Carlo error ∝ 1/√N, so achieving one more decimal of accuracy requires 100× more samples.  
- **Circle method**  
  - Edge‐bias: points near the circle boundary may cluster, but uniform sampling in the square keeps bias negligible.  
  - Extension: use stratified sampling or low‐discrepancy sequences (Sobol, Halton) for faster convergence.  
- **Buffon’s Needle**  
  - High variance when needle length L is much smaller than line spacing d.  
  - Extension: choose L≈d for minimal variance; apply antithetic variates to pair drops with complementary angles.  
- **Computational cost**: for N≥10⁶, pure‐Python loops (Buffon) and random draws can become slow.  
  - Extension: vectorize fully in NumPy or leverage Numba/Cython for inner loops.  

---

<a name="interpretation"></a>
## 6 · Results & Interpretation 🧩

- **Error vs N (log–log)**  
  - Slopes for both methods ≈–0.5, confirming O(1/√N) behavior.  
  - The circle method’s error curve lies below Buffon’s for equal N, showing lower variance.  
- **Visual checks**  
  - Circle scatter shows uniform coverage; fraction inside closely matches π/4.  
  - Buffon needle plot reveals roughly half needles cross when L=d, matching theory P=2L/(πd).  
- **Efficiency comparison**  
  - At N=10⁵, circle error ~10⁻³, Buffon error ~2×10⁻³ (roughly twice as noisy).  
- **Takeaway**: geometric‐area sampling is more efficient here; Buffon’s method is conceptually interesting but less practical for high‐precision π.  

---

<a name="conclusions"></a>
## 7 · Conclusions 📝

1. Both Monte Carlo techniques converge to π with error ∝ 1/√N, but prefactors differ.  
2. The circle‐based estimator is straightforward, low‐variance, and vectorizable—ideal for bulk sampling.  
3. Buffon’s Needle provides historical insight into geometric probability, yet yields higher variance per trial.  
4. Variance reduction (stratification, antithetic sampling, quasi‐MC) can dramatically speed convergence.  
5. Monte Carlo paradigms generalize to multidimensional integrals and complex domains beyond π.  

---

<a name="references"></a>
## 8 · Further Reading 📚

1. **Hammersley & Handscomb** — *Monte Carlo Methods*, Ch. 1–2.  
   [PDF (Hammersley & Handscomb)](https://www.cs.fsu.edu/~mascagni/Hammersley-Handscomb.pdf) :contentReference[oaicite:0]{index=0}
2. **A. Owen** — *Monte Carlo Theory, Methods and Examples*, § 3.4: Variance Reduction.  
   [Online (Art Owen)](https://artowen.su.domains/mc/) :contentReference[oaicite:1]{index=1}
3. **Christian P. Robert & George Casella** — *Monte Carlo Statistical Methods*, Ch. 5: Buffon’s Needle.  
   [PDF (Robert & Casella)](https://mcube.lab.nycu.edu.tw/~cfung/docs/books/robert2004monte_carlo_statistical_methods.pdf) :contentReference[oaicite:2]{index=2}
4. **P. Glasserman** — *Monte Carlo Methods in Financial Engineering*, Ch. 2: Convergence Analysis.  
   [PDF (Glasserman)](https://www.bauer.uh.edu/spirrong/Monte_Carlo_Methods_In_Financial_Enginee.pdf) :contentReference[oaicite:3]{index=3}
5. **Harald Niederreiter** — *Random Number Generation and Quasi-Monte Carlo Methods*, low-discrepancy sequences.  
   [SIAM Publication](https://epubs.siam.org/doi/book/10.1137/1.9781611970081) :contentReference[oaicite:4]{index=4}
