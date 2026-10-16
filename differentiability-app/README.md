# Differentiability Explorer

## Project Overview

**Differentiability Explorer** is an interactive web application built with HTML, CSS, and JavaScript to investigate continuity and differentiability using numerical approximations.

Users can select a function, choose an evaluation point (`a`), and adjust a positive step size (`h`) to explore the behavior of one-sided derivative estimates.

The goal is to demonstrate how numerical evidence can help identify differentiable points, corners, discontinuities, and possible vertical tangents. Numerical classifications are **not mathematical proofs**.

## Mathematical Background

A function is differentiable at a point `a` when its derivative exists as a finite limit:

```math
f'(a) = \lim_{h \to 0} \frac{f(a+h)-f(a)}{h}
```

The application calculates two one-sided derivative estimates for a positive step size `h`.

**Left-hand estimate:**

```math
D_L(a,h) = \frac{f(a)-f(a-h)}{h}
```

**Right-hand estimate:**

```math
D_R(a,h) = \frac{f(a+h)-f(a)}{h}
```

For differentiability, the one-sided estimates must approach the **same finite value** as `h` approaches zero.

Differentiability implies continuity, but continuity does not guarantee differentiability. For example, the absolute value function is continuous at zero, but its left-hand derivative is -1 and its right-hand derivative is +1.

## Application Features

- Select from smooth and nondifferentiable example functions.
- Adjust the evaluation point (`a`) and step size (`h`).
- View a graph of the selected function.
- Examine secant lines and tangent-slope approximations.
- View function values and left- and right-hand derivative estimates.
- Read numerical diagnostics and a likely-differentiability conclusion.
- Explore related concepts in the application's Theory section.

## Numerical Classification

The application compares the left- and right-hand derivative estimates using the absolute difference:

```math
\Delta = \left|D_L(a,h)-D_R(a,h)\right|
```

If this difference is sufficiently small relative to a chosen tolerance, the application may display **"Likely differentiable at a."**

The application also uses a slope threshold to flag **possible vertical tangents**. When the step size is relatively large, it may instead recommend decreasing `h` before interpreting the results.

**Important:** These classifications are numerical heuristics. A large finite slope is not necessarily a vertical tangent, and close agreement at one step size does not prove differentiability.

## How to Run

1. Download or clone the repository.
2. Open the application's HTML file (such as `index.html`) in a modern web browser.
3. Choose a function and adjust the evaluation point (`a`) and step size (`h`).
4. Examine the graph, numerical estimates, and conclusion.

The application runs in the browser and does not require additional software installation.

## Suggested Experiments

### Experiment 1: Smooth Function

Select `f(x) = x²` and set `a = 2`. As `h` decreases, the left- and right-hand estimates should approach the exact derivative of 4.

### Experiment 2: Sharp Corner

Select `f(x) = |x|` and set `a = 0`. The left- and right-hand derivative estimates approach -1 and +1, respectively. The function is continuous but not differentiable at this point.

### Experiment 3: Vertical Tangent

Select the application's vertical-tangent example. Observe how the magnitude of the slope estimates changes as `h` decreases. A single large slope does not, by itself, establish a vertical tangent.

### Experiment 4: Piecewise Function

Select a piecewise function and examine what happens near the boundary between its pieces. Compare the behavior of the left- and right-hand estimates.

## Numerical Limitations

- A finite step size approximates a limit; it does not evaluate the exact limit.
- Large step sizes can introduce truncation error.
- Extremely small step sizes can increase the effect of floating-point rounding and cancellation errors.
- Fixed numerical tolerances may incorrectly classify certain functions.
- A slope threshold cannot by itself distinguish a steep finite derivative from a vertical tangent.

The application's output should be interpreted as **numerical evidence**, supported by mathematical reasoning.

## Technologies Used

| Technology | Purpose |
| --- | --- |
| HTML | Application structure and controls |
| CSS | Visual design and layout |
| JavaScript | Function evaluation, derivative estimates, and interactive updates |

## Educational Purpose

This project explores how mathematical definitions from calculus can be implemented with computational methods. It connects continuity, differentiability, numerical approximation, and floating-point error, while emphasizing critical interpretation of algorithmic results.

## AI Assistance Disclosure

ChatGPT was used as a learning and development resource for JavaScript implementation, debugging, mathematical explanations, numerical-method discussions, and documentation. Suggestions were reviewed and revised during development. Numerical results should be checked against the underlying mathematics.
