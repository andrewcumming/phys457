# Lecture 23 Apr 2

We'll start by continuing our discussion of the partial wave expansion, in particular the effect of attractive/repulsive potentials on the phase shift, and what happens when there is a resonance. Then we'll go onto consider time-dependent perturbation theory, another way to get the Born approximation expression for the scattering amplitude:

## Time-dependent perturbation theory

Let's go back to pertubation theory but this time we're going to look at how states evolve in time when a perturbation is applied to the Hamiltonian $\hat{H} = \hat{H}_0 + \hat{H_1}$. Write the eigenstates of the unperturbed Hamiltonian as $\ket{n}$ with $\hat{H}_0\ket{n} = E_n\ket{n}$.
Then we can expand 

$$\ket{\Psi(t)} = \sum_n c_n(t) e^{-iE_nt/\hbar}\ket{n},$$

where we write the time-dependence under the unperturbed Hamiltonian explicitly and then put the remaining time-dependence from the perturbation into the coefficients $c_n$. We are effectively expanding the state at any given time in terms of the time-evolved eigenstates of $\hat{H}_0$; this is known as the **interaction picture**.

Substituting the expansion for $\ket{\Psi}$ into the time-dependent Schrödinger equation gives

$$i\hbar{\partial\ket{\Psi}\over \partial t} = (\hat{H}_0+\hat{H}_1)\ket{\Psi}$$

$$\Rightarrow i\hbar \sum_n \left[ \dot{c}_n - {iE_n\over \hbar}c_n\right] e^{-iE_nt/\hbar}\ket{n} = \sum_n c_n e^{-iE_nt/\hbar}\left[E_n\ket{n} + \hat{H}_1\ket{n}\right]$$

$$\Rightarrow i\hbar \sum_n \dot{c}_n e^{-iE_nt/\hbar}\ket{n} = \sum_n c_n e^{-iE_nt/\hbar}\hat{H}_1\ket{n}$$

$$\Rightarrow \boxed{\dot{c}_k = -{i\over\hbar}\sum_n c_n e^{-i(E_n-E_k)t/\hbar}\braket{k|\hat{H}_1|n}}.$$

This is a set of coupled ODEs that we could solve to determine the evolution of any initial state under the action of the full Hamiltonian $\hat{H}$. 

Now we want to consider the case that we are initially in an eigenstate of $\hat{H}_0$, e.g. $\ket{\Psi(0)}=\ket{N}$, in which case $c_N=1$ initially and all the other $c_n$'s are zero initially. If the perturbation $\hat{H}_1$ couples $\ket{N}$ to other states, their coefficients will become non-zero, in other words the perturbation will mix the initial state and the other stationary states. As long as the perturbation is small and we evolve for only a short time, the term with $n=N$ will dominate the right hand side and we can set $c_N\approx 1$, giving

$${dc_k\over dt} \approx -{i\over \hbar} e^{-i(E_N-E_k)t/\hbar}\braket{k|\hat{H}_1|N}.$$

In general, $\hat{H}_1$ will have some time-dependence. We can consider one Fourier-mode by writing $\hat{H}_1 = \hat{V} e^{-i\omega t}$. Using this and integrating in time gives

$$c_k(t) = {\braket{k|\hat{V}|n}\over E_N-E_k+\hbar\omega}\left[e^{-i(E_N-E_k+\hbar\omega)t/\hbar}-1\right].$$

This means that after a time $t$ the probability that the system will be found in the state $\ket{k}$ is

$$P_k(t) = |c_k|^2 = {|\braket{k|\hat{V}|n}|^2\over (E_N-E_k+\hbar\omega)^2}\left[2 - 2\cos\left({(E_N-E_k+\hbar\omega)t\over \hbar}\right)\right]$$

$$=4|\braket{k|\hat{V}|n}|^2 {\sin^2\left({(E_N-E_k+\hbar\omega)t\over 2\hbar}\right)\over (E_N-E_k+\hbar\omega)^2}.$$

At very small times this grows $\propto t^2$, but then oscillates.

**Fermi's Golden Rule**. In general we will be in a situation in which there are many possible end states. In the scattering problem we were looking at for example, there are many outgoing states depending on the scattering angle. We can sum over these possible end states using the density of states $g(E)$, where there are $g(E)dE$ possible states with energy between $E$ and $E+dE$. The transition probability is

$$P(t) = 4\int dE_k\, g(E_k) \,|\braket{k|\hat{V}|N}|^2{\sin^2\left({(E_N-E_k+\hbar\omega)t\over 2\hbar}\right)\over (E_N-E_k+\hbar\omega)^2}.$$

Now define a new integration variable $x = (E_N-E_k+\hbar\omega)/2\hbar$, or $E_k = E_N +\hbar\omega - 2\hbar x.$ Then the integral becomes

$${2\over \hbar}\int dx\, g(E_N +\hbar\omega - 2\hbar x) \,|\braket{k|\hat{V}|N}|^2{\sin^2(xt)\over x^2}.$$

The function $\sin^2(xt) / x^2$ has a peak $\propto t^2$ and central peak width $\propto 1/t$. So as $t$ grows, it becomes more and more peaked near $x\approx 0$, i.e. final states with $E_k\approx E_N+\hbar\omega$ are preferred. The area is therefore linear in $t$, so the transition probability is linear in $t$. As $t$ becomes large, 

$${\sin^2(xt)\over x^2}\xrightarrow[t\rightarrow\infty]{} \pi t\delta(x),$$

which we can use to do the integral:

$$P(t) = {2\pi t\over \hbar} g(E_N+\hbar\omega) |\braket{k|V|N}|^2.$$

A linear growth of $P$ with time means a constant transition rate $dP/dt$. Writing the initial and final states as $\ket{i}$ and $\ket{f}$ respectively and $E_f$ as the final energy we obtain **Fermi's Golden Rule**

$$\boxed{\Gamma = {2\pi\over \hbar} |\braket{f|V|i}|^2 g(E_f)}.$$


**Application to scattering**. Let's apply Fermi's Golden rule to scattering. The initial state is $\ket{\mathbf{k}_i}$ and we need to consider a range of final states $\ket{\mathbf{k}_f}$ with $k_f^2=k_i^2$. The density of states in a volume $V$ is  given by (this is derived in section 14.6 of Townsend if you haven't yet seen this in your statistical mechanics class)

$${V d^3\mathbf{p}\over h^3} = {V p^2 dp\, d\Omega\over h^3} = {V p \mu\, d\Omega\over h^3} dE \Rightarrow g(E) = {V\over (2\pi \hbar)^3} \mu\, \hbar k\, d\Omega$$

(where we used $E=p^2/2\mu \Rightarrow dE = p dp/\mu$). Therefore the transition rate into $d\Omega$ is

$${2\pi\over \hbar} {1\over (2\pi\hbar)^3} \mu \,\hbar k\, d\Omega\,  
V |A|^4 \left[\int d^3\mathbf{r} \, e^{-i\mathbf{k}_i\cdot\mathbf{r}}V(\mathbf{r})e^{i\mathbf{k}_f\cdot\mathbf{r}}\right]^2,$$

where $A=1/V^{1/2}$ is the normalization of the plane wave.

If we divide by the incident flux

$$j_\mathrm{inc} = {\hbar k\over \mu} |A|^2,$$

we find

$${d\sigma\over d\Omega} = {\mu^2\over (2\pi)^2\hbar^4} \left[\int d^3\mathbf{r} \, e^{-i\mathbf{k}_i\cdot\mathbf{r}}V(\mathbf{r})e^{i\mathbf{k}_f\cdot\mathbf{r}}\right]^2$$

which agrees with our expression from the Born approximation.

## Further reading

- There is more on time-dependent perturbation theory and Fermi's Golden rule in Townsend Chapter 14.

