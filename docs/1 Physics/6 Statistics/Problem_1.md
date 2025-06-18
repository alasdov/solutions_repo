<!-- ╭───────────────────────────────────────────────────────────╮
     │     📊 Statistics · Problem 1 — Exploring the CLT        │
     ╰───────────────────────────────────────────────────────────╯ -->

# 📊 **Problem 1: Exploring the Central Limit Theorem through Simulations**

> *“Regardless of the original distribution, the mean of many samples whispers ‘normal.’”*  

---

## 📋 Table of Contents
1. [Motivation 🎯](#motivation)  
2. [Theoretical Background 🔭](#theory)  
3. [Simulation Design 🔍](#design)  
4. [Sampling & Visualization 📈](#visualization)  
5. [Parameter Exploration ⚙️](#parameters)  
6. [Python Implementation 💻](#implementation)  
7. [Model Limitations & Extensions 🔧](#limitations)  
8. [Results & Interpretation 🧩](#interpretation)  
9. [Conclusions 📝](#conclusions)  
10. [Further Reading 📚](#references)  

---

<a name="motivation"></a>
## 1 · Motivation 🎯  
The **Central Limit Theorem** (CLT) underpins statistical inference:  
> *The distribution of the sample mean \(\bar X\) tends toward normality as sample size \(n\) grows, regardless of the parent distribution.*  
Simulations make this abstract theorem tangible, showing how quickly “normal” emerges.

---

<a name="theory"></a>
## 2 · Theoretical Background 🔭  

- For i.i.d. random variables \(X_1,\dots,X_n\) with mean \(\mu\) and variance \(\sigma^2\):  
  $$
  \bar X = \frac{1}{n}\sum_{i=1}^n X_i,
  $$
  $$
  \frac{\bar X - \mu}{\sigma/\sqrt{n}}
    \;\xrightarrow{d}\;
    \mathcal{N}(0,1)
    \quad\text{as }n\to\infty.
  $$

- **Implication:** even a highly skewed or discrete population yields an approximately Gaussian \(\bar X\) for moderate \(n\).  

---

<a name="design"></a>
## 3 · Simulation Design 🔍  
1. **Populations:**  
   - Uniform on [0,1]  
   - Exponential with rate λ=1  
   - Binomial(n=10, p=0.3)  
2. **Population size:** generate 100 000 draws per distribution.  
3. **Sample sizes:** \(n \in \{5, 10, 30, 50\}\).  
4. **Repetitions:** for each \(n\), repeat sampling 2000 times and record \(\bar X\).

---

<a name="visualization"></a>
## 4 · Sampling & Visualization 📈  
For each population and each \(n\):  
- Compute the 2000 sample means.  
- Plot their histogram overlaid with the theoretical normal PDF  
  \(\mathcal{N}(\mu,\,\sigma^2/n)\).

---

<a name="parameters"></a>
## 5 · Parameter Exploration ⚙️  
- **Effect of \(n\):** larger \(n\) → tighter, more symmetric histograms.  
- **Effect of variance:** high-variance populations (exponential) converge more slowly.  
- **Skewness:** binomial (discrete, bounded) shows faster “normalization” than exponential.

---

<a name="implementation"></a>
## 6 · Python Implementation 💻

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1qtuoE05v44tcGhbwzsDE3kAASEYv_lUU?usp=sharing)

<img src="https://i.imgur.com/Nec5baF.gif" width="800">

<a name="interpretation"></a>
## 8 · Results & Interpretation 🧩

- **Uniform[0,1]**  
  - At \(n=5\) the sampling distribution is already mildly bell‐shaped.  
  - By \(n=30\)–50 the histogram and overlaid Normal(\(\mu=0.5,\;\sigma/\sqrt{n}\)) PDF are nearly indistinguishable.  
- **Exponential(λ=1)**  
  - For \(n=5\), the mean distribution retains clear right‐skew.  
  - Convergence accelerates: \(n=30\) shows only slight skew, \(n=50\) closely follows the theoretical Normal(\(\mu=1,\;\sigma/\sqrt{n}\)).  
- **Binomial(n=10,p=0.3)**  
  - Discreteness visible at \(n=5\), but by \(n=10\) the “bars” align well with the continuous Normal(\(\mu=3,\;\sigma/\sqrt{n}\)).  
  - At \(n=30\)–50 the binomial sampling distribution is effectively Gaussian.  
- **Scale & spread**  
  - Empirical standard deviation of \(\bar X\) matches \(\sigma/\sqrt{n}\) within Monte Carlo error.  
- **Skew reduction**  
  - Observed skewness of \(\bar X\) decreases roughly as \(O(1/\sqrt{n})\), confirming theoretical rates.

---

<a name="conclusions"></a>
## 9 · Conclusions 📝

1. **The CLT is robust**: regardless of original shape (uniform, skewed, or discrete), \(\bar X\) approaches normality.  
2. **Moderate \(n\)** (≈30) suffices for practical normality in most cases—heavily skewed distributions need larger \(n\).  
3. **Theoretical predictions** for mean and variance of \(\bar X\) hold quantitatively in simulation.  
4. **Simulations complement theory**, providing intuition about convergence speed and finite‐sample behavior.  
5. **Applications**: justifies use of confidence intervals and hypothesis tests even when data deviate from normality.

---

<a name="references"></a>
## 10 · Further Reading 📚

1. W. Feller — *An Introduction to Probability Theory and Its Applications*, Vol. 2, Ch. 8–10.  
2. L. Wasserman — *All of Statistics: A Concise Course in Statistical Inference*, §2.3.  
3. G. Casella & R. L. Berger — *Statistical Inference*, §7.1–7.2.  
4. D. S. Sivia & J. Skilling — *Data Analysis: A Bayesian Tutorial*, App. on sampling distributions.  
5. SciPy Documentation — [`scipy.stats.norm`](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.norm.html) (Normal distribution utilities).  
