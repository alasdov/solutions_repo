# ⚖️ Measurements · Problem 1: Measuring Earth's Gravitational Acceleration with a Pendulum

> *“The simplest pendulum holds the key to gravity’s pull.”*

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Default Audio Player</title>
</head>
<body>

<audio controls>
  <source src="https://files.catbox.moe/8f1ug5.wav" type="audio/wav">
  Your browser does not support the audio element.
</audio>

</body>
</html>

---

## 📋 Table of Contents
1. [Motivation 🎯](#motivation)  
2. [Task 📝](#task)  
3. [Procedure 🔬](#procedure)  
4. [Calculations & Code 💻](#calculations)  
5. [Analysis 🔍](#analysis)  
6. [Deliverables 📦](#deliverables)  

---

<a name="motivation"></a>
## 1 · Motivation 🎯
The local gravitational acceleration \(g\) is fundamental in mechanics and geophysics.  
By timing a simple pendulum’s oscillations, we can determine \(g\) experimentally and practice uncertainty analysis.

---

<a name="task"></a>
## 2 · Task 📝
1. Measure the period \(T\) of a pendulum of length \(L\).  
2. Analyze measurement uncertainties in \(L\) and timing.  
3. Compute \(g\) and its uncertainty \(\Delta g\).

---

<a name="procedure"></a>
## 3 · Procedure 🔬
1. **Materials**: string (length \(L\)), mass, stopwatch, ruler (resolution \(\Delta L\)).  
2. **Setup**: suspend pendulum, measure \(L\) and record \(\Delta L = \tfrac{\text{(ruler resolution)}}{2}\).  
3. **Data Collection**:  
   - Displace \(<15°\) and release.  
   - Record time for 10 oscillations (\(T_{10}\)); repeat 10 times.  
   - Compute mean \(\overline{T_{10}}\) and standard deviation \(\sigma_{T_{10}}\).  
   - Uncertainty in mean: \(\Delta T_{10} = \sigma_{T_{10}}/\sqrt{n}\) with \(n=10\).

---

<a name="calculations"></a>
## 4 · Calculations & Code 💻
We use:

$$
T = \frac{\overline{T_{10}}}{10}, \quad
\Delta T = \frac{\Delta T_{10}}{10},
$$

$$
g = \frac{4\pi^2\,L}{T^2}, \quad
\Delta g = g \sqrt{\left(\frac{\Delta L}{L}\right)^2 + \left(\frac{2\,\Delta T}{T}\right)^2}.
$$


[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/14llQqLeZ3t0sTuTs3A1MNlcq8qcf0jnn?usp=sharing)
**Results:**  
L = 1.000 ± 0.001 m  
T = 2.0102 ± 0.0015 s  
g = 9.7697 ± 0.0152 m/s²

## 5 · Analysis 🔍
- **Comparison to standard**: measured \(g = 9.7697 \pm 0.0152\)\,m/s² vs. accepted \(9.81\)\,m/s² → difference ≈ 0.0403\,m/s², larger than the random uncertainty.
- **Systematic errors**  
  - Manual reaction time when starting/stopping the stopwatch.  
  - Small‐angle approximation (θ < 15°) introduces a period bias.  
  - Air resistance and pivot friction slightly slow the pendulum.
- **Random errors**  
  - Timing scatter: \(\Delta T = 0.0015\)\,s.  
  - Length measurement uncertainty: ±0.0005\,m.
- **Recommendations**  
  1. Reduce swing angle to 3°–5° for better small‐angle validity.  
  2. Measure a larger number of oscillations (20–30) per timing.  
  3. Use an electronic timer or photogate to eliminate reaction‐time bias.  
  4. Increase the number of trials (n ≫ 10) to improve statistics.

## 6 · Deliverables 📦
1. **Results table**:

   | Quantity | Value        | Uncertainty    |
   |:--------:|:------------:|:--------------:|
   | \(L\)    | 1.000 m      | ± 0.0005 m     |
   | \(T\)    | 2.0102 s     | ± 0.0015 s     |
   | \(g\)    | 9.7697 m/s²  | ± 0.0152 m/s²  |

2. **Discussion** of systematic vs. random error sources and their impact on \(g\).  
3. **Jupyter/Colab notebook** including measurement code, calculations, and plots (if any).  
4. **Reflection** on possible refinements: angle corrections, damping effects, improved timing methods.  
