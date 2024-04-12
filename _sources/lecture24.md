# Lecture 24 Apr 4

Last time, we looked at time-dependent perturbation theory and in particular *Fermi's Golden Rule* which gives the transition rate between two different stationary states of the unperturbed Hamiltonian. We applied Fermi's Golden Rule to calculate the transition rate between incoming and outgoing momentum eigenstates due to a scattering potential, and found that it reproduced the Born approximation for the scattering cross-section.

We're going to end the course by looking at transitions in atoms. For example, an atom in an excited state can decay to the ground state, releasing a photon that carries away the excess energy. In order to do so, we need to discuss how we can treat the electromagnetic field in quantum mechanics.

## The electromagnetic field in quantum mechanics

**Wave equation for the vector potential**. Consider an electromagnetic field with no charges or currents. We first write the magnetic field in terms of a time-dependent vector potential $\mathbf{A}(\mathbf{r},t)$, 

$$\mathbf{B} = \nabla\times\mathbf{A},$$

which then automatically satisfies $\mathbf{\nabla}\cdot\mathbf{B}=0$. The magnetic field $\mathbf{B}$ doesn't change if we make a gauge transformation $\mathbf{A}\rightarrow \mathbf{A} + \mathbf{\nabla}\lambda$ where $\lambda$ is a scalar field; this is known as *gauge freedom*. Another way to say this is that while $\nabla\times\mathbf{A}$ has to correspond to the physical field, we are free to choose $\mathbf{\nabla}\cdot\mathbf{A}$. Here, we'll set $\mathbf{\nabla}\cdot\mathbf{A}=0$, which is the *Coulomb gauge*.

With $\mathbf{\nabla}\cdot\mathbf{A}=0$ and also $\mathbf{\nabla}\cdot\mathbf{E}=0$ since we assume we are in vacuum, Faraday's law gives

$${\partial\mathbf{B}\over\partial t} = \nabla\times{\partial \mathbf{A}\over\partial t} = -\nabla\times \mathbf{E}\Rightarrow \mathbf{E} = -{\partial\mathbf{A}\over\partial t}.$$

Ampere's law with no currents gives 

$${1\over c^2}{\partial \mathbf{E}\over \partial t} = -{1\over c^2}{\partial^2 \mathbf{A}\over \partial t^2}= \nabla\times\mathbf{B} = -\nabla^2\mathbf{A},$$

where again in the last step we used $\mathbf{\nabla}\cdot\mathbf{A}=0$. We've arrived at a wave equation for $\mathbf{A}$:

$${1\over c^2}{\partial^2 \mathbf{A}\over \partial t^2} = \nabla^2\mathbf{A}$$

with wave speed $c = 1/\sqrt{\epsilon_0\mu_0}$ equal to the speed of light. This equation has plane wave solutions

$$\mathbf{A}\propto e^{i(\mathbf{k}\cdot\mathbf{r}-\omega t)}$$

with dispersion relation $\omega(k) = ck$. The waves are transverse, since $\mathbf{\nabla}\cdot\mathbf{A}=0\Rightarrow \mathbf{k}\cdot\mathbf{A} =0$; the direction of $\mathbf{A}$ is perpendicular to the propagation direction of the wave.

Because we're dealing with a linear equation, we can write $\mathbf{A}(\mathbf{r},t)$ as a sum over these plane wave solutions

$$\mathbf{A}(\mathbf{r},t) = \sum_{\mathbf{k},s} \left[c_{\mathbf{k},s} \epsilon_{\mathbf{k},s} {e^{i(\mathbf{k}\cdot\mathbf{r}-\omega t)}\over \sqrt{V}} + c^\star_{\mathbf{k},s} \epsilon^\star_{\mathbf{k},s} {e^{-i(\mathbf{k}\cdot\mathbf{r}-\omega t)}\over\sqrt{V}} \right].$$

The second term inside the sum is the complex conjugate of the first; this ensures that the vector potential $\mathbf{A}$ is real. Note that we are using the $1/\sqrt{V}$ normalization from last time; this means that the wave spectrum is discrete and so we sum over discrete $\mathbf{k}$ values. As $V$ becomes large, this sum goes to an integral over a continuous spectrum. The sum over $s$ sums over polarizations of each wave: the polarization $\epsilon_{\mathbf{k},s}$ is a unit vector that specifies the polarization direction, with $\mathbf{k}\cdot\mathbf{\epsilon}_{\mathbf{k},s}=0$. We assume that there are two polarization vectors $\epsilon_{\mathbf{k},1}$ and $\epsilon_{\mathbf{k},2}$, chosen so that $\epsilon^\star_{\mathbf{k},s}\cdot\epsilon_{\mathbf{k},s^\prime}=\delta_{s,s^\prime}$, ie. orthogonal to each other as well as to the propagation direction.

**Energy in the field**. The next step is to derive an expression for the energy of the electromagnetic field,

$$E_\mathrm{EM} = \int d^3\mathbf{r} \left[{1\over 2} \epsilon_0 E^2 +  {B^2\over 2\mu_0}  \right]$$

$$= {\epsilon_0\over 2} \int d^3\mathbf{r} \left[ \left(-{\partial \mathbf{A}\over \partial t}\right)^2 +  c^2 \left(\nabla\times \mathbf{A}  \right)^2\right].$$

This involves quite a lot of algebra, e.g. consider the electric field term. The electric field is

$$\mathbf{E} = i \sum_{\mathbf{k},s} \omega(k) \left[c_{\mathbf{k},s} \epsilon_{\mathbf{k},s} {e^{i(\mathbf{k}\cdot\mathbf{r}-\omega t)}\over \sqrt{V}} - c^\star_{\mathbf{k},s} \epsilon^\star_{\mathbf{k},s} {e^{-i(\mathbf{k}\cdot\mathbf{r}-\omega t)}\over\sqrt{V}} \right]$$

$$\Rightarrow E^2 = - \sum_{\mathbf{k},s}\sum_{\mathbf{k^\prime},s^\prime} \omega(k)\omega(k^\prime)\left[c_{\mathbf{k},s} \epsilon_{\mathbf{k},s} {e^{i(\mathbf{k}\cdot\mathbf{r}-\omega t)}\over \sqrt{V}} - c^\star_{\mathbf{k},s} \epsilon^\star_{\mathbf{k},s} {e^{-i(\mathbf{k}\cdot\mathbf{r}-\omega t)}\over\sqrt{V}} \right]\cdot \left[c_{\mathbf{k^\prime},s^\prime} \epsilon_{\mathbf{k^\prime},s^\prime} {e^{i(\mathbf{k^\prime}\cdot\mathbf{r}-\omega t)}\over \sqrt{V}} - c^\star_{\mathbf{k^\prime},s^\prime} \epsilon^\star_{\mathbf{k^\prime},s^\prime} {e^{-i(\mathbf{k^\prime}\cdot\mathbf{r}-\omega t)}\over\sqrt{V}} \right].$$

This looks complicated but simplifies dramatically because of the orthogonality of the polarization vectors and the plane waves,

$$\int d^3\mathbf{r} {e^{-i\mathbf{k^\prime}\cdot\mathbf{r}}\over \sqrt{V}} {e^{i\mathbf{k}\cdot\mathbf{r}}\over \sqrt{V}}  = \delta_{\mathbf{k}^\prime,\mathbf{k}}.$$

The cross-terms with opposite signs in the exponent cancel between the electric field and magnetic field terms in the integral. The final result is

$$E_\mathrm{EM} = \epsilon_0 \sum_{\mathbf{k}, s} \omega(k)^2 \left( c^\star_{\mathbf{k},s} c_{\mathbf{k},s} + c_{\mathbf{k},s}c^\star_{\mathbf{k},s}\right).$$

We've kept the relative ordering of the $c^\star$ and $c$ coefficients because we will soon turn them into operators in quantum mechanics and then will have to be careful about whether they commute.

**Quantization of the field**. The appearance of the term $c^\star_{\mathbf{k},s} c_{\mathbf{k},s}$ in the energy suggests a number operator, and indeed if we use the expression for the energy $E_\mathrm{EM}$ to define a Hamiltonian by taking 

$$c^\star_{\mathbf{k},s} \rightarrow  \hat{a}^\dagger_{\mathbf{k},s} \left({\hbar\over 2\epsilon_0\omega}\right)^{1/2}$$

$$c_{\mathbf{k},s} \rightarrow  \hat{a}_{\mathbf{k},s} \left({\hbar\over 2\epsilon_0\omega}\right)^{1/2}$$

then we get

$$\hat{H}_\mathrm{EM} = \sum_{\mathbf{k}, s} {\hbar\omega\over 2} \left( \hat{a}^\dagger_{\mathbf{k},s} \hat{a}_{\mathbf{k},s} + \hat{a}_{\mathbf{k},s}\hat{a}^\dagger_{\mathbf{k},s}\right).$$

With a commutation relation 

$$[\hat{a}_{\mathbf{k},s},\hat{a}^\dagger_{\mathbf{k},s}]=1$$

we get

$$\hat{H}_\mathrm{EM} = \sum_{\mathbf{k}, s} \hbar\omega \left( \hat{a}^\dagger_{\mathbf{k},s} \hat{a}_{\mathbf{k},s} + {1\over 2}\right).$$

We interpret the operators $\hat{a}^\dagger_{\mathbf{k},s}$ and $\hat{a}_{\mathbf{k},s}$ as **creation** and **annhilation** operators respectively. They create or destroy photons at each $\mathbf{k}$ and $s$ with corresponding energy $\hbar\omega$. Just as with the harmonic oscillator, we can keep adding photons with a given wavelength by successively applying the creation operator. This is consistent with the idea that photons are bosons and so we can have more than one photon in the same single particle state. We'll develop this idea further next time.


## Further reading

- There is more on time-dependent perturbation theory and Fermi's Golden rule in Townsend Chapter 14.

