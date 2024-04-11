# Lecture 25 Apr 9

(Still work in progress)

Today we discussed:

- quantization of the electromagnetic field by turning the coefficients $c_{k,s}$ in the expansion of $\mathbf{A}$ into *creation* and *annihiliation* operators $\hat{a}^\dagger_{k,s}$ and $\hat{a}_{k,s}$. These operators obey the commutation relation $[\hat{a}_{k,s},\hat{a}_{k,s}^\dagger]=1$ that we know from the harmonic oscillator.
- we interpret the action of these operators as creating or destroying photons with wavelength given by $2\pi/k$ or frequency $\omega=ck$ and polarization given by $s$. We write the state of the electromagnetic field by keeping track of how many photons we have for each value of $k$ and $s$. 
- the vacuum state has zero photons. It has a non-vanishing energy - each of the oscillators contributes a ground state energy, so the energy actually diverges even for the ground state. In quantum field theory, this *vacuum energy* can also be thought of in terms of short-lived virtual particles that are continuously being created and annihilated in the vacuum. In practice, because it is energy differences that matter, we can ignore this term. Note however that is it possible to carry out experiments that probe this term -- a famous example is the [Casimir effect](https://en.wikipedia.org/wiki/Casimir_effect) which is discussed in section 14.8 of Townsend.
- this approach gives us another way to write down multi-particle states of identical particles, known as **second quantization**. Instead of writing down linear combinations of single particle states and making sure they have the correct particle-exchange symmetry (symmetric for bosons and anti-symmetric for fermions), we instead keep track of how many particles we have placed in each single-particle state, and the nature of the particle is imposed by the quantization condition. For bosons such as the photons in the electromagnetic field, this is the commutator $[\hat{a},\hat{a}^\dagger]=1$. 
- second quantization of fermions is similar except that instead of a commutator, we use an anti-commutator:

$$\left\{\hat{a},\hat{a}^\dagger\right\}=\hat{a}\hat{a}^\dagger + \hat{a}^\dagger\hat{a} = 1.$$

To see that this gives the right properties for the ladder operators, we can act the number operator on the state $\hat{a}^\dagger\ket{n}$, where $\ket{n}$ is the state with $n$ particles:

$$\hat{N} \hat{a}^\dagger\ket{n} = \hat{a}^\dagger\hat{a} \hat{a}^\dagger \ket{n} = \hat{a}^\dagger(1-\hat{a}^\dagger\hat{a}) \ket{n} = (1-n) \hat{a}^\dagger\ket{n}$$

(in the second step we used the anti-commutator).  This shows that $\hat{a}^\dagger\ket{n}$ is an eigenstate of the number operator with eigenvalue $1-n$, i.e.

$$\hat{a}^\dagger\ket{n}\propto \ket{1-n}.$$

If we start with the vacuum $\ket{0}$, we have 

$$\hat{a}^\dagger\ket{0}\propto \ket{1}$$

but

$$\hat{a}^\dagger\ket{1}\propto \ket{0}.$$

We can add at most one particle! This is exactly what we need for fermions.





## Further reading

- There is more on time-dependent perturbation theory and Fermi's Golden rule in Townsend Chapter 14.

