# Lecture 25 Apr 9

## More on quantizing the electromagnetic field 

As we discussed at the end of last time, we quantize the electromagnetic field by turning the coefficients $c_{k,s}$ in the expansion of $\mathbf{A}$ into *creation* and *annihiliation* operators $\hat{a}^\dagger_{\mathbf{k},s}$ and $\hat{a}_{\mathbf{k},s}$. The Hamiltonian can then be written as

$$\hat{H}_\mathrm{EM} = \sum_{\mathbf{k},s} \hbar \omega \left(\hat{a}^\dagger_{\mathbf{k},s}\hat{a}_{\mathbf{k},s} + {1\over 2}\right).$$

The creation and annihiliation operators obey the commutation relation $[\hat{a}_{\mathbf{k},s},\hat{a}_{\mathbf{k},s}^\dagger]=1$ that we know from the harmonic oscillator. We interpret the action of these operators as creating or destroying photons with wavelength given by $2\pi/k$ or frequency $\omega=ck$ and polarization given by $s$. 

We write the state of the electromagnetic field by keeping track of how many photons we have for each value of $\mathbf{k}$ and $s$. The vacuum state has zero photons. We can then add photons with wavevector $\mathbf{k}$ and polarization $s$ by operating with $\hat{a}^\dagger_{\mathbf{k},s}$ as many times as needed.

It is worth noting that the vacuum state has a non-vanishing energy - each of the oscillators contributes a ground state energy, so the energy actually diverges even for the ground state. In quantum field theory, this *vacuum energy* can also be thought of in terms of short-lived virtual particles that are continuously being created and annihilated in the vacuum. In practice, because it is energy differences that matter, we can ignore this term. Note however that is it possible to carry out experiments that probe this term -- a famous example is the [Casimir effect](https://en.wikipedia.org/wiki/Casimir_effect) which is discussed in section 14.8 of Townsend.

## Second quantization

This general approach to writing down multi-particle states of identical particles is known as **second quantization**. Instead of writing down linear combinations of single particle states and making sure they have the correct particle-exchange symmetry (symmetric for bosons and anti-symmetric for fermions), we instead keep track of how many particles we have placed in each single-particle state, and the nature of the particle is imposed by the quantization condition. For bosons such as the photons in the electromagnetic field, this is the commutator $[\hat{a},\hat{a}^\dagger]=1$. 

Second quantization of fermions is similar except that instead of a commutator, we use an anti-commutator:

$$\left\{\hat{a},\hat{a}^\dagger\right\}=\hat{a}\hat{a}^\dagger + \hat{a}^\dagger\hat{a} = 1.$$

To see that this gives the right properties for the ladder operators, we can act the number operator on the state $\hat{a}^\dagger\ket{n}$, where $\ket{n}$ is the state with $n$ particles:

$$\hat{N} \hat{a}^\dagger\ket{n} = \hat{a}^\dagger\hat{a} \hat{a}^\dagger \ket{n} = \hat{a}^\dagger(1-\hat{a}^\dagger\hat{a}) \ket{n} = (1-n) \hat{a}^\dagger\ket{n}$$

(in the second step we used the anti-commutator).  This shows that $\hat{a}^\dagger\ket{n}$ is an eigenstate of the number operator with eigenvalue $1-n$, i.e.

$$\hat{a}^\dagger\ket{n}\propto \ket{1-n}.$$

If we start with the vacuum $\ket{0}$, we have 

$$\hat{a}^\dagger\ket{0}\propto \ket{1}$$

but

$$\hat{a}^\dagger\ket{1}\propto \ket{0}.$$

We can add at most one particle, exactly what we need for fermions. You'll see more of second quantization if you study quantum field theory applied to particle physics or condensed matter systems. For now, we'll stay focused on the example of photons.


## Decay rate of the 2p-state in hydrogen

To show how we can put this to use, let's calculate the decay rate of the 2p state in hydrogen. In this transition, an example of **spontaneous emission**, an electron in the 2p state drops into the 1s state (ground state) and emits a photon with energy $(1-1/4)\times 13.6\ \mathrm{eV} = 10.2\ \mathrm{eV}$ (the [Ly-$\alpha$](https://en.wikipedia.org/wiki/Lyman-alpha) transition). Why does this transition occur? The reason is that once we've introduced the electromagnetic field, we need to update the Hamiltonian for the hydrogen atom to include the effect of the electromagnetic field on the motion of the electron. The stationary states that we found earlier for the hydrogen atom are no longer stationary states of the modified Hamiltonian. They no longer diagonalize the full Hamiltonian and so are not time-independent. If we start in the hydrogen atom 2p state, the state will evolve in time to include some contribution from other states.

We can treat this using time-dependent perturbation theory if we identify the additional part of the Hamiltonian that comes from including the effect of the electromagnetic field on the electron motion. Previously in [lecture 3](https://andrewcumming.github.io/phys457/lecture3.html#interference-experiments-with-gravity-and-magnetic-fields), we mentioned that the vector potential $\mathbf{A}$ enters into the Lagrangian as an extra term $q\mathbf{v}\cdot\mathbf{A}$. This extra term can give rise to interference effects (the Aharanov-Bohm effect). In the Hamiltonian, the change we need to make is to replace the particle momentum $\mathbf{p}$ with the canonical momentum $\mathbf{p}-q\mathbf{A}$. We won't prove this here, but you can show that this leads to the correct equations of motion for a charged particle under the Lorentz force. See Appendix E of Townsend for a full derivation. 

The kinetic energy term in the Hamiltonian becomes

$${\hat{p}^2\over 2\mu} \rightarrow {1\over 2\mu}\left(\hat{\mathbf{p}}-q\hat{\mathbf{A}}\right)^2 = {\hat{p}^2\over 2\mu} - {q\over\mu}\hat{\mathbf{p}}\cdot\hat{\mathbf{A}} + {q^2\hat{A}^2\over 2\mu}$$

where we use the fact that the $\hat{\mathbf{p}}$ and $\hat{\mathbf{A}}$ operators commute for our assumed gauge $\mathbf{\nabla}\cdot\mathbf{A}=0$. 

For hydrogen, with $q=-e$, we can therefore write the full Hamiltonian as 

$$\hat{H} = \hat{H}_\mathrm{0} + \hat{H}_\mathrm{EM} + \hat{H}_1,$$

where $\hat{H}_0$ is the Hamiltonian for the hydrogen atom without the electromagnetic field, and we treat the extra terms as a perturbation 

$$\hat{H}_1 = {e\over\mu}\hat{\mathbf{p}}\cdot\hat{\mathbf{A}} + {e^2\hat{A}^2\over 2\mu}.$$

Recall that we are writing the vector potential operator as a sum of plane waves

$$\hat{\mathbf{A}} = \left({\hbar\over 2\epsilon_0\omega}\right)^{1/2} \sum_{\mathbf{k},s} \left(\hat{a}_{\mathbf{k},s} \mathbf{\epsilon}_{\mathbf{k},s}{e^{i\mathbf{k}\cdot\mathbf{r}-i\omega t}\over \sqrt{V}}  +  \mathrm{c.c.}   \right)$$

where c.c. represents the complex conjugate of the first term. This means that the term $\hat{\mathbf{p}}\cdot\hat{\mathbf{A}}$ in $\hat{H}_1$ will couple photon states that differ by 1 photon at each $\mathbf{k}$ and $s$. This term is the important one for the 2p$\rightarrow$1s transition which emits a single photon. The $\hat{A}^2$ term, which describes two-photon processes, does not contribute.

Note that since the terms inside $\hat{\mathbf{A}}$ are $\propto e^{\pm i\omega t}$, we have an oscillating perturbation in time. Treating this with time-dependent perturbation theory, we can then apply Fermi's Golden Rule

$$\Gamma = {2\pi\over\hbar} g(E_f) |\braket{f|\hat{H}_1|i}|^2.$$

Here, $g(E_f)$ is the density of states corresponding to the outgoing photon (in the rate we are summing over all the possible outgoing photon states). This can be obtained from

$${V d^3\mathbf{p}\over h^3} = {V p^2 dp d\Omega\over h^3} = {V E^2 dE d\Omega\over c^3h^3}= g(E) dE$$

$$\Rightarrow g(E_f) = {V\omega^2d\Omega\over 8\pi^3c^3\hbar}$$

where we use $p=E/c$ for photons.

The initial and final states are 

$$\ket{i} = \ket{2p}\ket{0};\hspace{1cm} \ket{f} = \ket{1s}\ket{1}.$$

Here we use the notation $\ket{0}$ to represent the electromagnetic field vacuum (no photons) and $\ket{1}$ to represent the state with 1 photon with $k$ corresponding to the photon released in the 2p$\rightarrow$1s transition. The states $\ket{2p}$ and $\ket{1s}$ are the hydrogen atom states that are stationary states of the unperturbed hydrogen Hamiltonian $\hat{H}_0$; the states $\ket{0}$ and $\ket{1}$ are the stationary states of the electromagnetic Hamiltonian $\hat{H}_\mathrm{EM}$. Both $\ket{i}$ and $\ket{f}$ are therefore stationary states of the unperturbed Hamiltonian $\hat{H}_0+\hat{H}_\mathrm{EM}$.

Putting this together gives the following expression for the rate:

$$d\Gamma = {2\pi\over \hbar}\left({V\omega^2d\Omega\over 8\pi^3c^3\hbar}\right) {e^2\over\mu^2} {\hbar\over 2\epsilon_0\omega V}\left|\braket{1|\hat{a}^\dagger|0}\right|^2\left|\braket{2p|e^{i\mathbf{k}\cdot\mathbf{r}}\mathbf{\epsilon}\cdot\hat{\mathbf{p}}|1s}\right|^2.$$

We write $d\Gamma$ because we are looking at the rate going into a particular direction and solid angle $d\Omega$.

For the part of the matrix element involving the H atom wavefunctions, we first note that the wavelength of the transition is much larger than the size of the atom: the Ly-$\alpha$ photon wavelength is 1215 Angstroms compared to about 1 Angstrom for the atom. Therefore we can set $e^{i\mathbf{k}\cdot\mathbf{r}}\approx 1$ in the integral. Then with a few manipulations we can get the matrix element into a more familiar form:

$$\mathbf{\epsilon}\cdot\braket{2p|\hat{\mathbf{p}}|1s} = \mu \mathbf{\epsilon}\cdot\braket{2p|{d\hat{\mathbf{r}}\over dt}|1s} = {i\mu\over\hbar} \mathbf{\epsilon}\cdot\braket{2p|[\hat{H},\hat{\mathbf{r}}]|1s} = {i\mu\over\hbar} (E_{1s}-E_{2p})\braket{2p|\mathbf{\epsilon}\cdot\hat{\mathbf{r}}|1s}$$

$$= i\mu\omega\braket{2p|\mathbf{\epsilon}\cdot\hat{\mathbf{r}}|1s}.$$

So we see that we are dealing with a similar dipole matrix element that we had in the Stark effect! We know that for these integrals to be non-zero we need $\Delta m=0$ and $\Delta\ell=\pm 1$, which is why we have been looking at 2p as the initial state rather than 2s. 

Simplifying all the prefactors (including using our favourite formula $e^2/4\pi\epsilon_0 = \alpha \hbar c$), we have therefore

$$d\Gamma = {\alpha \omega^3 d\Omega\over 2\pi c^2} \left|\braket{2p|\mathbf{\epsilon}\cdot\hat{\mathbf{r}}|1s}\right|^2.$$

If we choose the polarization direction to be the $z$-direction, we can do the integrals just like we did for the Stark effect:

$$\int dr\ r^2 R^\star_{2,1} r R_{1,0} = \sqrt{3\over 2} {2^8\over 3^5} a_0$$

(given in Townsend 14.163)

$$\int d\Omega\, Y^\star_{2,0} Y_{1,0} \cos\theta = {1\over \sqrt{3}}$$

(from the midterm formula sheet)

$$\Rightarrow \left|\braket{2p|\mathbf{\epsilon}\cdot\hat{\mathbf{r}}|1s}\right|^2 = {2^{15}\over 3^{10}} a_0^2$$

In this case we need to start in the $m=0$ 2p state, otherwise the angular integration will vanish. Townsend discusses the other polarizations (see section 14.7): $m=-1$ or $m=+1$ correspond to choosing polarizations which are linear combinations of $x$ and $y$ (circular polarizations). We are out of time to go through the details, but averaging over all polarizations gives an extra factor of $1/3$. Finally, we can integrate over the different outgoing directions to get the total decay rate 

$$\Gamma = \int d\Omega {\alpha \omega^3 d\Omega\over 2\pi c^2} {2^{15}\over 3^{11}}a_0^2 = \alpha {2^{16}\over 3^{11}} \left({a_0\over\lambda}\right)^2 \omega.$$ 

Using $\hbar\omega = (3/4) \times 13.6\ \mathrm{eV} = (3/8)\alpha^2 m_ec^2$, this can also be written

$$\Gamma = \left({2\over 3}\right)^8 \alpha^5 {m_e c^2\over \hbar} = 0.6\times 10^9\ \mathrm{s^{-1}}.$$

This corresponds to a lifetime for the $2p$ state of order a nanosecond. 




## Further reading

- The relevant sections of Townsend are 14.4 (Hamiltonian of the atom) and 14.7 (Spontaneous emission).

- Appendix E of Townsend goes through how to write down the Lagrangian and Hamiltonian for a particle in an electromagnetic field.


