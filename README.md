[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/rH27J4tG)
# kapitza-pendulum

## Assignment

**Due date:**  
Sunday, November 23rd at 11:59 pm  

---

## Overview

In this assignment, you will study the **stability of the inverted state** of a rigid pendulum whose pivot is driven vertically at high frequency (a Kapitza pendulum).

Work with a **dimensionless** equation of motion for the shifted angle $\theta(\tau)$, where $\theta = \pi$ corresponds to the *inverted* position. One convenient form is

$$\theta'' + 2\zeta\ \theta' + \left(\epsilon^2 - \alpha\cos\tau\right)\ \sin\theta = 0,$$

where

- $\epsilon=\frac{\omega_0}{\omega_d}$ is the dimensionless frequency;  
- $\alpha = \frac{y_0}{l}$ is the drive amplitude, relative to the pendulum length;  
- $\zeta = \frac{\gamma}{\omega_d}$ is a dimensionless damping coefficient;
- $\theta'=\frac{d\theta}{d\tau}$; and
- $\tau = \omega_d t$ is time measured in reference to the drive frequency.

Your goal is to **numerically** explore which combinations of $(\epsilon,\alpha,\zeta)$ the inverted state $\theta=pi$ becomes stable.

---

## Objectives

1. **Build a clear, well-documented Colab notebook**  
   - Include short markdown explanations and **pseudocode** describing your numerical strategy before the actual code.  
   - Your notebook should be easy to read and reproduce.

2. **Design your own stability diagnostic**  
   - Choose initial conditions that represent the inverted state (e.g. $\theta_0 \approx \pi$, $\dot{\theta}_0 \approx 0$).  
   - Decide how long to integrate, how to discard transients, and how to quantify “long-time behavior” (e.g. some average or amplitude of $\theta$, $\cos\theta$, etc.).  
   - Justify your choices briefly in the notebook.

3. **Map long-time behavior vs. parameters**  
   - For at least one fixed $\zeta$, sweep over a sensible grid of $\epsilon$ and $\alpha$.  
   - For each point, compute an indicator of whether the inverted state is “stable” or “unstable” according to your diagnostic.

4. **Produce a 2D stability plot with your guessed boundary**  
   - Make a plot with **$\epsilon$ on the x-axis** and **$\alpha$ on the y-axis**, where color (or contours) shows your long-time response measure.  
   - From this data, extract an approximate **stability boundary** $\alpha_c(\epsilon)$ separating stable and unstable behavior.  
   - Propose a simple **functional form** for this boundary (for example,  
     $$\alpha_c(\epsilon) \approx C\ \epsilon^2$$).  
   - **Superimpose your guessed curve** on top of the 2D plot and comment briefly on how well it matches your numerical results.

---

## Minimum deliverables (in your Colab notebook)

- A clearly commented function implementing the equation of motion in a format appropriate for your solver.  
- Pseudocode and code for:
  - Integrating the system for given $(\epsilon,\alpha,\zeta)$,
  - Computing your long-time stability diagnostic.  
- A parameter sweep over $(\epsilon,\alpha)$ for at least one $\zeta$.  
- A 2D plot (α vs. ε) of your response measure, **with your stability curve overlaid**.  
- A short written summary explaining:
  - Your stability criterion,  
  - How you chose numerical parameters (time window, grid, thresholds),  
  - Why you chose your functional form for the boundary, and how well it fits.
