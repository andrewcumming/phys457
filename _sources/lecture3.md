# Lecture 3 Jan 11

```{admonition} Warm-up question
Derive an expression for the momentum propagator $\braket{p^\prime, t^\prime | p_0, t_0}$.
```

Today, we'll first finish off the derivation of the path integral from last time. This gives us the result 

$$\braket{x^\prime,t^\prime|x_0, t_0} = \int \mathcal{D}[x(t)] \exp\left({iS(x(t))\over \hbar}\right)=\int \mathcal{D}[x(t)] \exp\left({i\over \hbar}\int dt\ L(x, \dot{x})\right).$$

Next, let's discuss some of the implications and applications of this result.


## Applications of path integrals


### The classical path and the semi-classical approximation

We noted last time that the free-particle propagator ends up being of the form 

$$\braket{x^\prime,t^\prime|x_0, t_0} = f(t^\prime-t_0) e^{iS_c/\hbar},$$

where $f(t^\prime-t_0)$ is a normalization factor that depends on the time-difference, and $S_c$ is the action corresponding to the path $x_c(t)$ that the particle would take according to classical physics (a straight line for a free particle with $V(x)=0$). What is the significance of this? 

The classical trajectory of a particle is given by the **Principle of least action** which says that the trajectory $x_c(t)$ extremizes (usually minimizes) the action. This means that for any perturbation to the path $x_c(t)\rightarrow x_c(t) + \delta x(t)$, we have $\delta S=0$, where

$$\delta S = \int dt \left({\partial L\over \partial x}\delta x + {\partial L\over \partial \dot{x}}\dot{\delta x}\right).$$

The second term can be integrated by parts:

$$\delta S = \left[ {\partial L\over \partial \dot{x}}\delta x\right] + \int dt \left({\partial L\over \partial x} - {d\over dt}{\partial L\over \partial \dot{x}}\right)\delta x.$$

The boundary term vanishes, since we consider only perturbed paths that start and end at the same locations ($x_0$ and $x^\prime$), so $\delta x=0$ at $t=t_0$ or $t=t^\prime$, so we have

$$\delta S = \int dt \left({\partial L\over \partial x} - {d\over dt}{\partial L\over \partial \dot{x}}\right)\delta x = \int dt {\delta L\over \delta x} \delta x,$$

where $\delta L/\delta x$ is known as the *functional derivative*. Then setting $\delta S=0$ for arbitrary perturbations $\delta x$ gives the [Euler-Lagrange equation](https://en.wikipedia.org/wiki/Euler–Lagrange_equation)

$${\partial L\over \partial x} - {d\over dt}{\partial L\over \partial \dot{x}}=0,$$

which is the equation of motion for a particle with Lagrangian $L$. You will see this in your classical mechanics course, if not already.

The significant of this result for us is that the classical trajectory has a special property that it is the trajectory where $\delta S=0$ for neighbouring paths. This means that the classical trajectory and its neighbours add up in phase with each other when we sum up their contributions $e^{iS_c/\hbar}$ to the path integral. A trajectory that is far away from the classical path does not have $\delta S=0$, so then neighbouring paths contribute different phases and cancel out. 

As a simple example of this, consider the propagator from the point $(x,y) = (-1,0)$ to $(1,0)$ and for simplicity let's consider paths for which the particle travels in a straight line to a point $(0,y)$ in half the time and then from there in a straight line to the endpoint in the remaining half of the time. The action is then

$$S = 2\times {m\over 2}{1 + y^2\over (t^\prime-t_0)/2}  = {2m(1+y^2)\over (t^\prime-t_0)}.$$

Summing $e^{iS/\hbar}$ over the different paths taking a discrete set of $y$ values $y_n = n\Delta y$, the path integral is then proportional to

$$\sum_{n=0}^N \exp\left(i(1+(n\Delta y)^2)\right).$$


```{admonition} Exercise:
Plot this sum in the complex plane for increasing values of $N$, starting at $N=0$ and increasing to larger values. Which terms in the sum contribute most to the final answer?
``` 


For classical particles where $S$ is large compared to $\hbar$, only paths extremely close to the classical path can add in phase, the others cancel. The homework questions will give you a chance to calculate the numerical value of $S$ for different cases and get a feeling for when we can consider the motion classical (path integral dominated by classical trajectory) or quantum ($S$ is small enough that even non-classical trajectories can make a significant contribution to the integral).

The **semi-classical approximation** involves expanding $S$ around the classical value:

$$S[x]\approx S[x_c] + {1\over 2} \int dt \int dt^\prime \delta x(t^\prime) {\delta^2 L\over \delta x(t)\delta x(t^\prime)}  \delta x(t) + \dots$$

where now we are using the second order functional derivative term (the first order term vanishes for the classical path). We won't go into the details of this here, but you can see that the propagator will be $\propto e^{iS[x_c]/\hbar}$ multiplied by a correction term corresponding to the integral over the different trajectories $\delta x(t)$. This is what we found for the free particle, and in fact this holds also for Lagrangians that are up to and including quadratic in $x$ or $\dot{x}$ (see comment in Townsend section 8.5). This includes the harmonic oscillator (HW 1, question 8.3 from Townsend).

### Interference experiments with gravity and magnetic fields

Section 8.7 of Townsend talks about an interesting experiment that looks for the phase difference between two neutron beams, one of which moves upwards in the Earth's gravitational field and gets an extra phase shift $\approx  imgHt/\hbar$. 

Another example is in section 14.1 of Townsend which talks about the **Aharanov-Bohm effect**. We'll discuss this more later, but a charged particle has a term in the Lagrangian 

$$L = {q\over c} \vec{A}\cdot\vec{v}.$$

This means that a charged particle picks up a phase that depends on the vector potential $\vec{A}$, even in a region where the magnetic field $\vec{B} = \vec{\nabla}\times\vec{A}$ vanishes. Paths that go around a solenoid on different sides have a net phase, even though the magnetic field outside the solenoid vanishes! Classically a particle would have no idea that the solenoid was there, but the quantum particle does!


### Relation to statistical mechanics

Path integrals also turn out to be useful in statistical mechanics through the idea of *imaginary time*. 

Consider the quantity 

$$\int dx \braket{x,t|x,0} = \int dx \braket{x|e^{-i\hat{H}t/\hbar}|x} $$

$$ = \int dx \sum_n \braket{x|n} \braket{n|e^{-i\hat{H}t/\hbar}|x} = \int dx \sum_n \braket{x|n} \braket{n|x} e^{-iE_nt/\hbar}$$

$$ = \sum_n \int dx\ |\braket{x|n}|^2\ e^{-iE_nt/\hbar} = \sum_n e^{-iE_nt/\hbar}.$$ (partition)

This is actually the result we expect, since the first line shows that we are evaluating the *trace* of the Hamiltonian in the position basis, but the trace of an operator is the same in any basis, so it can also be evaluated in the basis of stationary states which gives the final expression.

A similar sum over energies appears in statistical mechanics as the **partition function**

$$Z = \sum_n e^{-\beta E_n},$$

where $\beta = 1/k_BT$. The partition function is an important quantity because it can be used to obtain many different thermodynamic properties of a system, e.g. the energy is given by $E = -\partial \ln Z/\partial \beta$. You'll see more of this in your stat mech courses, but for us the important point is that the expression for the partition function can be obtained from equation {eq}`partition` if we evaluate it at the imaginary time $it/\hbar\rightarrow \beta$. This allows the application of path integral techniques to statistical mechanics.




## Further reading

- Sections 8.6 and 8.7 of Townsend. Section 14.1 for the Aharanov-Bohm effect.

- [Path Integrals in Quantum Physics](https://arxiv.org/abs/1209.1315v4) - a comprehensive set of lectures aimed at graduate students if you want to dive into this topic in more depth, covering path integrals in quantum mechanics and statistical mechanics.

