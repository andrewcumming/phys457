# Lecture 2 Jan 9

```{admonition} Warm-up question
Does $\ket{\Psi}$ have units? Does $\psi(x)$ have units?
Explain why $\ket{p} = e^{ipx/\hbar}/\sqrt{2\pi \hbar}$ has that normalization.
```

Today the goal is to go through the calculation of the propagator using a path integral. We'll find that the path integral takes the form of an integral of $\exp(-iS/\hbar)$ over the different possible paths a particle can take, where $S$ is the action, as discussed at the end of last time.

Before we start on that, one thing that we forgot to mention last time in our review of operators and observables is the importance of commuting vs non-commuting operators. Commuting operators ($[\hat{A},\hat{B}]=0$) share a complete set of simultaneous eigenstates, and are *compatible observables*. We can know the value of both observables at the same time, since the operators have the same eigenstates. Non-commuting operators such as position and momentum are *incompatible observables*. They have different eigenstates, so that a measurement of one quantity results in some uncertainty in the value of the other. The associated uncertainty relation is

$$\langle(\Delta A)^2\rangle \langle(\Delta B)^2\rangle \geq {1\over 4}\left|  \langle [\hat{A},\hat{B}] \rangle \right|^2.$$

The canonical example of incompatible observables is position-momentum, for which the commutator is $[\hat{x},\hat{p}_x]=i\hbar$. 


## The propagator for a free-particle

We want to derive an expression for the propagator 

$$\braket{x^\prime,t^\prime|x_0, t_0} = \braket{x^\prime|e^{-i\hat{H}(t^\prime-t_0)/\hbar}|x_0}.$$

For a free-particle, $\hat{H}=\hat{p}^2/2m$, and so the propagator takes the form

$$\braket{x^\prime|e^{-i\hat{H}(t^\prime-t_0)/\hbar}|x_0} = \braket{x^\prime|e^{-i\hat{p}^2(t^\prime-t_0)/2m\hbar}|x_0}$$

We can evaluate this by inserting the identity operator $\int dp \ket{p}\bra{p}$:

$$\braket{x^\prime|e^{-i\hat{p}^2(t^\prime-t_0)/2m\hbar}|x_0} = \int dp \braket{x^\prime|p}\braket{p|e^{-i\hat{p}^2(t^\prime-t_0)/2m\hbar}|x_0}$$

$$ = \int dp \braket{x^\prime|p}\braket{p|x_0}e^{-ip^2(t^\prime-t_0)/2m\hbar}$$

$$ = {1\over 2\pi\hbar}\int dp\  e^{ip(x^\prime-x_0)/\hbar}e^{-ip^2(t^\prime-t_0)/2m\hbar}.$$

We can evaluate this by completing the square

$$-{p^2(t^\prime-t_0)\over 2m\hbar}+{p(x^\prime-x_0)\over\hbar} = 
-\left({t^\prime-t_0\over 2m\hbar}\right)\left[p^2 - p\left({2m(x^\prime-x_0)\over t^\prime-t_0}\right) \right]$$

$$=-\left({t^\prime-t_0\over 2m\hbar}\right)\left[\left(p - {m(x^\prime-x_0)\over t^\prime-t_0}\right)^2  - \left({m(x^\prime-x_0)\over t^\prime-t_0}\right)^2\right]$$

$$= -q^2 + {m(x^\prime-x_0)^2\over 2\hbar(t^\prime-t_0)},$$

which defines a new integration variable $q$. The integral becomes 

$$ {1\over 2\pi\hbar} \left({2m\hbar\over t^\prime-t_0}\right)^{1/2}  \exp\left({im(x^\prime-x_0)^2\over 2\hbar(t^\prime-t_0)}\right) \int dq\  e^{-iq^2}.$$

Using $\int^\infty_{-\infty} dq\ e^{-iq^2}=(1-i)\sqrt{\pi/2}=\sqrt{\pi/i}$ we get the answer

$$\boxed{\braket{x^\prime,t^\prime|x_0, t_0} = \left({m\over 2\pi\hbar i(t^\prime-t_0)}\right)^{1/2} \exp\left({im(x^\prime-x_0)^2\over 2\hbar(t^\prime-t_0)}\right)}$$ (freeparticleprop)

(this is equation (8.9) of Townsend).

Notice that this is proportional to $e^{iS_c/\hbar}$ where $S_c$ is the classical action, i.e. the action for the classical trajectory in which the particle moves at constant velocity, giving 

$$S_c = \int L dt = \int {1\over 2} mv^2\ dt = {m(x^\prime-x_0)^2\over 2(t^\prime-t_0)}.$$

So we see that for this particular case that we get a propagator related to $e^{iS/\hbar}$. Next we want to show this for a particle moving in a general potential $V(x)$.

## Derivation of the path integral

In the general case, $\hat{H} = \hat{p}^2/2m + V(\hat{x})$ which makes evaluating the propagator a lot more tricky. Our approach is going to be to divide the time period $t^\prime-t_0$ into infinitesimally small steps $\Delta t= \epsilon(t^\prime-t_0)$ where $\epsilon\ll 1$ and we'll eventually take the limit $\epsilon\rightarrow 0$. The reason to do this is that we can then factorize the time-evolution operator over one of the small intervals like this:

$$\exp\left(-{i\hat{H}\epsilon(t^\prime-t_0)\over\hbar}\right)\approx \exp\left(-{i\hat{p}^2\epsilon(t^\prime-t_0)\over 2m\hbar}\right)\exp\left(-{iV(\hat{x})\epsilon(t^\prime-t_0)\over \hbar}\right).$$

We need $\epsilon$ to be small for this to work because otherwise there are correction terms involving the commutator of the two operators: the *Baker-Campbell-Hausdorff formula* gives $\ln e^A e^B = A+B + [A,B]/2 + \dots$ for two operators $A$ and $B$. In our case, $A$ and $B$ correspond to the kinetic energy and potential energy terms. Because they are both $\propto \epsilon$ with $\epsilon\ll 1$, we can ignore the correction terms because they are of order $\epsilon^2$ or smaller. 

For the free particle, we made progress by inserting the identity operator $\int dp \ket{p}\bra{p}$ which allowed us to convert the $\hat{p}$ operator in the exponent into its eigenvalue $p$. We can do the same thing here with both momentum and position by inserting identity operators $\int dp \ket{p}\bra{p}$ and $\int dx \ket{x}\bra{x}$. However, we need to do this $\approx 1/\epsilon$ times, once for each small timestep.

Our expression for the propagator then looks like this:

$$\bra{x^\prime}   e^{-i\hat{H}\Delta t/\hbar} e^{-i\hat{H}\Delta t/\hbar}\dots e^{-i\hat{H}\Delta t/\hbar}                \ket{x_0}$$

Focus on the first intermediate step:

$$ = \bra{x^\prime} \dots   \int dx_1 \ket{x_1} \bra{x_1}  e^{-i\hat{p}^2\Delta t/2m\hbar}e^{-i\hat{V}\Delta t/\hbar}             \int dp_1 \ket{p_1} \braket{p_1|x_0}$$

$$ = \bra{x^\prime} \dots   \int dx_1 \int dp_1\ \ket{x_1} \braket{x_1|p_1}  e^{-ip_1^2\Delta t/2m\hbar}e^{-iV(x_1)\Delta t/\hbar}              \braket{p_1|x_0}$$

$$ = \bra{x^\prime} \dots   \int dx_1 \int dp_1\ \ket{x_1} {1\over 2\pi\hbar} e^{ip_1(x_1-x_0)/\hbar}   e^{-ip_1^2\Delta t/2m\hbar}e^{-iV(x_1)\Delta t/\hbar}  $$

$$ = \bra{x^\prime} \dots   \int dx_1 \int {dp_1\over 2\pi \hbar}\ \ket{x_1} 
\exp\left({i\Delta t\over \hbar}\left[ p_1{x_1-x_0\over \Delta t} - {p_1^2\over 2m} - V(x_1)      \right]\right)$$

Now add intermediate step 2:


$$ = \bra{x^\prime} \dots   \int dx_2 \int {dp_2\over 2\pi \hbar} \int dx_1 \int {dp_1\over 2\pi \hbar}\ \ket{x_2}  \times $$

$$\exp\left({i\Delta t\over \hbar}\left[ p_2{x_2-x_1\over \Delta t} - {p_2^2\over 2m} - V(x_2) \right]\right)
\exp\left({i\Delta t\over \hbar}\left[ p_1{x_1-x_0\over \Delta t} - {p_1^2\over 2m} - V(x_1)      \right]\right)$$

We can see that filling in the remaining steps will give

$$\boxed{ \braket{x^\prime,t^\prime|x_0, t_0}\approx  \int dx_{N-1}\dots dx_1 \int {dp_N\dots dp_1\over (2\pi \hbar)^N} \exp\left({i\Delta t\over \hbar}\sum_j\left[ p_{j}{x_{j}-x_{j-1}\over \Delta t} - {p_j^2\over 2m} - V(x_j) \right]\right)}$$

(this is equation (8.22) of Townsend).

We can do the momentum integrals by completing the square, just as we did when deriving the free particle propagator. Adapting that result gives

$$ {1\over 2\pi\hbar}\int dp_j\  e^{ip_j(x_j-x_{j-1})/\hbar}e^{-ip_j^2\Delta t/2m\hbar} = \left({m\over 2\pi\hbar i\Delta t}\right)^{1/2} \exp\left({im(x_j-x_{j-1})^2\over 2\hbar\Delta t}\right)$$

and therefore


$$\boxed{ \braket{x^\prime,t^\prime|x_0, t_0}\approx  \left({m\over 2\pi i \hbar \Delta t}\right)^{N/2} \int dx_{N-1}\dots dx_1\ \exp\left({i\Delta t\over \hbar}\sum_j\left[  {m(x_j-x_{j-1})^2\over 2(\Delta t)^2}- V(x_j) \right]\right)}$$ (pathintegral)

(this is equation (8.24) of Townsend).

In the continuum limit $\epsilon\rightarrow 0$, these expressions become exact. The term $(x_j-x_{j-1})/\Delta t\rightarrow \dot{x}$, and the expression in the exponent of either of the boxed equations becomes $iS/\hbar$, where $S$ is the action. In the first case, before integrating over momentum, we have 

$$\int dt \left(p\dot{x} - H(x,p)\right) = \int dt\ L(x,\dot{x}) = S$$

(this is the Legendre transform from classical mechanics relating the Hamiltonian $H$ and Lagrangian $L$). In the second case, we have 

$$\braket{x^\prime,t^\prime|x_0, t_0} = \int \mathcal{D}[x(t)] \exp\left({i\over \hbar}\int dt\ \left({1\over 2}m\dot{x}^2 - V(x)\right)\right)$$

or

$$\braket{x^\prime,t^\prime|x_0, t_0} = \int \mathcal{D}[x(t)] \exp\left({i\over \hbar}\int dt\ L(x, \dot{x})\right)$$

where

$$\mathcal{D}[x(t)] = \mathrm{lim}_{N\rightarrow \infty} \int dx_{N-1}\dots dx_1\ \left({m\over 2\pi i \hbar \Delta t}\right)^{N/2}$$

represents the integral over all possible paths.


```{admonition} Exercise

To close the loop, use equation {eq}`pathintegral` to evaluate the propagator for a free particle ($V=0$) and check that your result agrees with equation {eq}`freeparticleprop`.

Try it yourself first, but if you get stuck you can look at section 8.5 of Townsend which works through this.

```

## Further reading

- Sections 8.1-8.5 of Townsend

- Two of the mathematical results we used: [Baker-Campbell-Hausdorff formula](https://en.wikipedia.org/wiki/Baker–Campbell–Hausdorff_formula), [Fresnel integrals](https://en.wikipedia.org/wiki/Fresnel_integral)
