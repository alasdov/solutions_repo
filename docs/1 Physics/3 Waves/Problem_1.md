<!-- ╭────────────────────────────────────────────────────────╮
     │   🌊 Waves · Problem 6 — Interference Patterns on Water Surface   │
     ╰────────────────────────────────────────────────────────╯ -->

# 🌊 **Problem 6: Interference Patterns on a Water Surface**

> *“When ripples collide, they weave a tapestry of peaks and troughs.”*  

---

## 💥 Table of Contents
1. [Motivation 🎯](#motivation)  
2. [Theory & Model 📐](#theory)  
3. [Pattern Analysis 🔍](#analysis)  
4. [Interpretation 🧩](#interpretation)  
5. [Python Simulation 💻](#implementation)  
6. [Model Limits & Extensions ⚙️](#limitations)  
7. [Conclusions & Insights 📝](#conclusions)  
8. [Further Reading 📚](#references)  

---

<a name="motivation"></a>
## 1 · Motivation 🎯  
Interference of waves on a water surface is a vivid demonstration of superposition.  
By placing multiple coherent sources at the vertices of a regular polygon, we can:  
- Visualize **constructive** vs **destructive** interference  
- Explore the role of **phase** and **geometry**  
- Connect to real‐world applications (antenna arrays, optics, wave energy)

---

<a name="theory"></a>
## 2 · Theory & Model 📐

### 2.1 Single‐Source Wave
A point source at \((x_i,y_i)\) emits:
$$
\eta_i(x,y,t)
= \frac{A}{\sqrt{r_i}}\;\cos\!\bigl(k\,r_i - \omega\,t + \phi_i\bigr),
\quad
r_i = \sqrt{(x - x_i)^2 + (y - y_i)^2}.
$$

### 2.2 Superposition
Multiple sources sum linearly:
$$
\eta_{\mathrm{sum}}(x,y,t)
= \sum_{i=1}^{N} \eta_i(x,y,t).
$$

---

<a name="analysis"></a>
## 3 · Pattern Analysis 🔍
- **Constructive interference**: phases align → high‐amplitude lobes  
- **Destructive interference**: phases opposite → nodal lines  
- **Fringe spacing** depends on wavelength \(\lambda = 2\pi/k\) and source geometry  
- **Polygon symmetry** yields \(N\)-fold rotational symmetry in the pattern  

---

<a name="interpretation"></a>
## 4 · Interpretation 🧩
- **Bright lobes** in the contour plot are water crests (\(\eta>0\)).  
- **Dark lobes** are troughs (\(\eta<0\)).  
- **Zero‐crossing lines** (nodes) trace destructive interference.  
- As \(N\) increases, the pattern transitions from dipole‐like to sharply defined petals.  

Applications:  
- Designing phased‐array antennas  
- Optical interference & holography  
- Wave‐energy harvesting optimization  

---

<a name="implementation"></a>
## 5 · Python Simulation 💻

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/15RYnexR7yrr13lTq7UTNdHPru4jkckyQ?usp=sharing)

<img src="https://i.imgur.com/4ZelPE8.png" width="600">

<a name="limitations"></a>

## 6 · Model Limits & Extensions ⚙️

| Assumption            | Limitation                              | Possible Extension                             |
|:----------------------|:----------------------------------------|:-----------------------------------------------|
| **Equal source amplitude** | Real emitters may vary in strength      | Assign each source its own amplitude \(A_i\)   |
| **No damping**        | Ignores energy loss over distance       | Multiply each wave by \(e^{-\alpha r_i}\)      |
| **Static snapshot**   | Omits time evolution of interference    | Animate over \(t\) to see wave propagation     |
| **Infinite 2D plane** | Boundaries and depth effects neglected  | Solve shallow‐water equations on a bounded domain |

---

<a name="conclusions"></a>
## 7 · Conclusions & Insights 📝

- A regular \(N\)-gon of coherent sources yields an \(N\)-fold symmetric interference pattern.  
- Constructive lobes (“petals”) occur where path-length differences are integer multiples of the wavelength.  
- Destructive nodal lines trace loci of half-wavelength cancellation.  
- Contour plots reveal both spatial symmetry and the underlying physics of superposition.  
- Extending to time-series animations deepens insight into wave propagation and energy transfer.

---

<a name="references"></a>
## 8 · Further Reading 📚

1. Lord Rayleigh — *The Theory of Sound*, Vol. I, Ch. 4: Wave Interference.  
2. Max Born & Emil Wolf — *Principles of Optics*, 7th ed., §1.4: Interference and Diffraction.  
3. Lawrence E. Kinsler et al. — *Fundamentals of Acoustics*, 4th ed., Ch. 9: Surface Waves.  
4. Henrik Jensen et al. — *Computational Ocean Acoustics*, Ch. 6: Numerical Simulation of Surface Waves.  
5. Tethys Research — “Wave Energy Converter Interference Study,” NASA Tech. Report (2018).  
