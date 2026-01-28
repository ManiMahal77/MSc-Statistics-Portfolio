# Monte Carlo Methods & Sampling Algorithms

## Overview
This project implements and analyzes fundamental **Monte Carlo simulation techniques** for statistical inference. It explores efficient sampling strategies from non-standard distributions, optimization of rejection sampling constants, and variance reduction techniques using Importance Sampling.

The project demonstrates the practical application of probability theory to computational statistics, specifically focusing on tail behavior and convergence properties of different estimators.

## Key Implementations

### 1. Inverse Transform Sampling
* **Objective:** Sample from the transformed random variable $Y = X^\alpha$, where $X$ follows a standard Laplace distribution.
* **Method:** Derived the analytical CDF and inverse CDF for $Y$. Implemented the Probability Integral Transform to generate samples for various shape parameters ($\alpha$).
* **Outcome:** Visualized the impact of non-linear transformations on tail weight and density shape.

### 2. Rejection Sampling Optimization
* **Objective:** Sample from a heavy-tailed target distribution using a Student's t-distribution proposal.
* **Optimization:** Numerically optimized the degrees of freedom ($\nu$) of the proposal distribution to minimize the rejection constant $M$.
* **Result:** Achieved an optimal acceptance rate by setting $\nu \approx 3.92$, maximizing computational efficiency.

### 3. Variance Reduction: Importance Sampling (IS) vs. Simple Monte Carlo (SMC)
* **Objective:** Estimate the expectation of $\phi(t) = e^{-t^4}$ under a heavy-tailed distribution ($t_2$).
* **Analysis:** Compared the variance of Simple Monte Carlo against Importance Sampling using a standard normal proposal $N(0,1)$.
* **Key Insight:** demonstrated that despite the proposal having lighter tails than the target (typically a violation of IS principles), the rapid decay of the test function $\phi(t)$ stabilizes the weights, resulting in finite variance and comparable performance to SMC.

## Technologies Used
* **R Language:** Core statistical programming.
* **R Markdown:** Literate programming for combining code, LaTeX math, and analysis.
* **ggplot2:** Advanced data visualization.
* **Numerical Optimization:** Using base R `optimize` for parameter tuning.

## Visualizations
The full report includes:
* **Convergence Plots:** Comparing the running estimates of IS and SMC estimators with confidence bands.
* **Efficiency Curves:** illustrating the relationship between degrees of freedom and the rejection sampling constant $M$.
* **Density Overlays:** Validating sample histograms against theoretical PDFs.

## How to View
📄 [Click here to view the full rendered report with plots and derivation](Monte_Carlo_Methods_Sampling_Algorithms_files/Monte_Carlo_Methods_Sampling_Algorithms.md)
*(Note: Please click the link above to see the mathematical notation and graphs rendered correctly).*

## Author
**Calum Smith**
* MSc Statistics with Data Science, University of Warwick
* https://www.linkedin.com/in/calumwillsmith/
