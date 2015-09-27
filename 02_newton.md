Lecture 02: Root Finding
========================

Part of "Numerical Methods for Differential Equations", Colin
Macdonald, <cbm@math.ubc.ca>.


Rooting Finding
===============

Iterative techniques for solving $f(x) = 0$ for $x$.

*Bisection*: **Linear convergence**. Start with an interval $[a, b]$ bracketing the root.
Evaluate the midpoint.  Replace one end, maintaining a root bracket.
  Slow but **robust**.

*Newton's Method*: $x_{k+1} = x_k - f(x_k) / f'(x_k)$.  Faster,
**quadratic convergence** (number of correct decimals places doubles each
iteration).

Downsides of Newton's Method: need derivative info, and additional
smoothness.  Convergence usually not guaranteed unless "sufficiently
close": **not robust**.

*Secant Method*: $x_{k+1} = x_k - (f(x_k) (x_{k-1} - x_k)) / (f(x_{k-1}) - f(x_k))$. **Sublinear convergence**:
faster than bisection but slower than Newton's method. Useful when the derivative of the function is more complicated
than the function itself, hard to compute, nd simply doesn't exist. Need two initial values.

Downsides of Secant's Method: similarly to Newton's, not guaranteed to converge if the initial
values are "too far": **not robust**.


Systems
-------

$f(x) = 0$, but now $f : \mathbb{R}^n \to \mathbb{R}^n$.

This is a system of nonlinear equations.  Denote a solution as $\alpha
\in \mathbb{R}^n$.

Derivation: Taylor expansion about $x$

  $$ 0 = f(\alpha) = f(x) + J(x) (\alpha - x) + \text{h.o.t.} $$

where $J(x)$ is the Jacobian matrix...

Pretend h.o.t. are 0, so instead of $\alpha$ we find $x_{k+1}$:

  $$ 0 = f(x_k) + J(x_k) (x_{k+1} - x_k) $$

In principle, can rearrange to solve for $x_k$ but better to solve

  $$ J_k \delta = -f(x_k) $$

That is, solve "$Ax = b$".  Then update:

  $$ x_{k+1} := x_k + \delta $$



