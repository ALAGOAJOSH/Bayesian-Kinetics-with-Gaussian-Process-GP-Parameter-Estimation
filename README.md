# Reaction Kinetics Parameter Estimation with Bayesian ML

## What this project does
Standard nonlinear least squares parameter estimation gives you a point estimate of k0 and Ea
with asymptotic standard errors that are often underestimated.

This project uses Gaussian Process regression in log-rate space to give a full probability
distribution over rate constants at any temperature, then recovers kinetic parameters
with honest uncertainty bounds.

## Results
k0 recovered within 3%, Ea within 1.5% of true values.
GP 95% confidence band correctly brackets all noisy observations.
Uncertainty widens appropriately in data-sparse temperature regions.

## Tech stack
Python 3.10, GPyTorch 1.11, PyTorch 2.0, SciPy, NumPy, Matplotlib

## How to run
```
conda activate mlenv
pip install gpytorch torch scipy
python main.py
```

## Why Bayesian matters here
The uncertainty in kinetic parameters propagates into uncertainty in reactor volume,
heat duty, and selectivity. A GP posterior lets you propagate these uncertainties
honestly through your reactor model.

## Dataset
10 temperature-rate pairs from known Arrhenius parameters (k0=1e8, Ea=75000 J/mol)
with 8% multiplicative Gaussian noise.

## Author
Joshua Alagoa
