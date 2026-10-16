Differentiability Explorer
Project Overview
Differentiability Explorer is an interactive web application built with HTML, CSS, and JavaScript to investigate continuity and differentiability through numerical approximations. Users select a function, choose an evaluation point $a$, and adjust a positive step size $h$ to explore how one-sided derivative estimates behave.
The goal is to show how numerical evidence can help identify differentiable points, corners, discontinuities, and possible vertical tangents—while emphasizing that numerical classifications are not formal proofs.
Mathematical Background
A function is differentiable at $a$ when the following limit exists and is finite:
\[
f'(a)=\lim_{h\to 0}\frac{f(a+h)-f(a)}{h}.
\]
The application uses the following one-sided approximations for $h>0$:
Left-hand estimate:
\[
D_L(a,h)=\frac{f(a)-f(a-h)}{h}
\]
Right-hand estimate:
\[
D_R(a,h)=\frac{f(a+h)-f(a)}{h}
\]
For differentiability, both estimates must approach the same finite limit as $h$ approaches zero. Differentiability implies continuity, but continuity alone does not guarantee differentiability. For example, $f(x)=|x|$ is continuous at $x=0$, although its one-sided derivatives are $-1$ and $1$.
Features
- Function selection with smooth and nondifferentiable examples
- Adjustable evaluation point $a$ and step size $h$
- Interactive function graph and secant/tangent-slope visualizations
- Displays $f(a)$, $f(a+h)$, and left- and right-hand derivative estimates
- Numerical differentiability diagnostics and explanatory conclusions
- Theory content to connect the calculations to calculus concepts
Numerical Classification
The program compares the one-sided estimates using
\[
\Delta=|D_L(a,h)-D_R(a,h)|.
\]
If $\Delta$ is within a chosen tolerance, the program may label the point “Likely differentiable at a.” It also uses a large-slope threshold to flag possible vertical tangents and may recommend reducing $h$ when estimates are inconclusive.
These are heuristics, not mathematical proofs. In particular, a steep but finite derivative can exceed the large-slope threshold, and agreement at one finite step size does not establish that a derivative exists.
How to Run
1. Download or clone this repository.
2. Open the application's HTML file (for example, index.html) in a modern browser.
3. Select a function and adjust $a$ and $h$.
4. Examine the graph, numerical estimates, and classification.
The application runs in a browser without a separate installation step.
Suggested Experiments
Smooth function: $f(x)=x^2$
Set $a=2$ and decrease $h$. The left- and right-hand estimates should approach the exact derivative $f'(2)=4$.
Corner: $f(x)=|x|$
Set $a=0$. The left- and right-hand estimates approach $-1$ and $1$, respectively, indicating nondifferentiability despite continuity.
Vertical-tangent example
Select the application's vertical-tangent function and observe whether the slope magnitudes increase as $h$ decreases. A single large numerical slope is not enough to establish a vertical tangent.
Piecewise function
Investigate a piecewise function near the boundary between its pieces and compare the one-sided behavior.
Numerical Limitations
- Finite step sizes approximate limits but do not calculate them exactly.
- Large $h$ values may introduce truncation error.
- Extremely small $h$ values can amplify floating-point rounding and cancellation errors.
- Fixed tolerance and slope thresholds can misclassify some functions.
- Numerical results should be interpreted alongside mathematical reasoning.
Technologies
- HTML — Interface structure
- CSS — Styling and layout
- JavaScript — Function evaluation, numerical calculations, and interactive updates
Educational Purpose
This project explores how definitions from calculus can be translated into computational methods. It connects continuity, differentiability, numerical error, and graphical interpretation, while encouraging critical evaluation of algorithmic conclusions.

AI Assistance Disclosure
ChatGPT was used as a learning and development resource for JavaScript implementation, debugging, mathematical explanations, numerical-method discussions, and documentation. Suggestions were reviewed and revised during development; numerical outputs should be independently checked against the relevant mathematics.
