# Black–Scholes Greeks: Finite Difference Methods

## Overview

This project investigates the numerical computation of Delta and Vega for European call options under the Black–Scholes–Merton model.

The main objective is to implement finite difference methods and examine their accuracy through convergence experiments.

## Methods

Three approaches are considered:

1. **Analytical Greeks:** Compute Delta and Vega using closed-form Black–Scholes formulas.
2. **Bump-and-reprice:** Apply central finite differences to the analytical option pricing function.
3. **Finite difference PDE solver:** Solve the Black–Scholes PDE using an explicit finite difference scheme, then approximate Delta and Vega numerically.

## Numerical Experiments

The experiments use the following parameters:

| Parameter | Value |
|---|---:|
| Initial stock price | 50 |
| Strike price | 50 |
| Risk-free interest rate | 0.10 |
| Volatility | 0.40 |
| Time to maturity | 0.5 |

The analytical values are approximately:

- Delta: 0.6248
- Vega: 13.4085

### Convergence Results

The numerical experiments demonstrate:

- Second-order convergence of central finite differences for Delta and Vega.
- Approximately second-order convergence of the explicit PDE solver for option prices.
- Approximately second-order convergence of PDE-based Delta.
- Approximately second-order convergence of PDE-based Vega under PDE grid refinement.

An important numerical observation is that decreasing the volatility bump alone does not eliminate PDE discretization errors when the PDE grid is held fixed.

## Requirements

- Python 3
- NumPy
- SciPy
- Matplotlib
- Jupyter Notebook

## How to Run

Install the required packages:

```bash
pip install -r requirements.txt
```

Open the notebook:

```bash
jupyter notebook greeks_finite_difference.ipynb
```

Run the cells sequentially to reproduce the numerical experiments and convergence plots.

## Limitations

The implementation uses an explicit finite difference scheme, which requires a sufficiently small time step for stability.

The experiments consider European call options under the standard Black–Scholes assumptions. More general pricing models and alternative discretization schemes are beyond the current scope.


## Related Project

For a further investigation of numerical option pricing,
see my project:

**[Black-Scholes PDE Solver](https://github.com/Huangteng-Yang/black-scholes-engine)**

This project implements explicit, implicit, and
Crank-Nicolson finite difference methods for European
put option pricing.

It also compares numerical PDE solutions with the
Black-Scholes analytical formula and Monte Carlo simulation,
with emphasis on convergence analysis and computational
efficiency.
