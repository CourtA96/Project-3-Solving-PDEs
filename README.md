# Project 3 Solving PDEs

## Introduction

The code in the file "Heat Equation.ipynb" finds the solution to the heat equation with a potential term $\beta\Phi$ and with no incoming boundary values. It separates the second order PDE into first order PDEs and uses the forward-time-centered-space (FTCS) scheme to compute the solution. It the computes the convergence of the FTCS scheme. The solution is then plotted for different values of 𝛽. The final two sections introduce the solution to $Φ_{'tt} = Φ_{'xx} + sin(Φ)$ and the Runge-Kutta RK3 method for solving the original PDE. RK3 should be unconditionally stable, but there is an error in the code that makes the solution found using this code unstable.

The file "Stability Analysis.pdf" gives a Vonn Neumann stability analysis of the FTCS scheme.

## Results

The stability analysis founds that the FTCS scheme is unconditionally unstable for all $\lambda$.

The following gifs show the FTCS solutions for different values of $\beta$:

![](https://raw.githubusercontent.com/CourtA96/MCMC-Project/master/Data.png)

Comparing the above plots, the solution seems to oscillate more slowly and in a more controlled manner when beta is small. When beta is large, the oscillations are more rapid and the solution quickly gains a large amplitude.

The following plots show the convergence order of the FTCS scheme when $\lambda$, $\beta$ and the number of time steps are varied.


So when we take 10 000 timesteps and vary 𝜆, the solution explodes around 𝜆=0.075



So for 𝜆=0.05 the solution stays reasonably stable up to around 25 000 timesteps.



So the solution slowly becomes less and less convergent as beta increases. The effect is not as dramatic as when the number of timesteps or the value of 𝜆 is changed, but it is still noticeable. This explains the loss of convergence seen above for high beta. The rapid oscillations make it difficult for the algorithm to produce accurate results.
