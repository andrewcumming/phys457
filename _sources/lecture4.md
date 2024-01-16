# Lecture 4 Jan 16

```{admonition} Warm-up question

Given the wavefunction at time $t=0$, $\psi(x,0)$, how would you use the propagator to calculate the wavefunction at time $t$, $\psi(x,t)$?

```

```{dropdown} Solution

The answer is 

$$\psi(x,t) = \int dx^\prime \braket{x, t| x^\prime, 0} \psi(x^\prime, 0).$$

To see this, we can start with $\ket{\Psi(t)} = e^{-i\hat{H}t/\hbar}\ket{\Psi(0)}$ which gives

$$\braket{x|\Psi(t)} = \braket{x|e^{-i\hat{H}t/\hbar}|\Psi(0)}=\int dx^\prime \braket{x|e^{-i\hat{H}t/\hbar}|x^\prime}\braket{x^\prime|\Psi(0)}$$

where we inserted the identity operator.

This integral expression for $\psi(x,t)$ shows that you can think of the propagator as a Green's function for the Schrödinger equation.

```

We'll start today by finishing our discussion of path integrals. Then we'll move on to Chapter 9 of Townsend, which discusses the two body problem in quantum mechanics. In particular, we'll see that we can use symmetries of the Hamiltonian to infer a lot about the stationary states of the problem. We'll apply what we learn to the hydrogen atom in Chapter 10.

## Back of the envelope hydrogen atom

Before we do any detailed calculations, we can make some estimates of the expected size of the hydrogen atom and its ground state energy. Imagine that the hydrogen atom  has a size $a$. The proton is so heavy we can think of it being fixed and the electron moves around it. By the uncertainty principle, an electron confined to a distance $a$ has an uncertainty in its momentum of $\Delta p\sim \hbar/a$. On average, the electron will have zero momentum, but there will be a non-zero average of $p^2$ due to its motion. It seems reasonable to estimate the minimum value of $\langle p^2\rangle$ as $(\Delta p)^2$.

We can then estimate the ground state energy as

$$E\sim {\hbar^2\over 2ma^2}  -{e^2\over 4\pi \epsilon_0 a}$$

where the first term is the (positive) kinetic energy and the second term is the (negative) electrostatic potential energy between the electron and proton. The mass $m$ is the mass of the electron.

A useful quantity is 

$$\alpha = {e^2\over 4\pi\epsilon_0} = {1\over 137}$$

which is the [fine structure constant](https://en.wikipedia.org/wiki/Fine-structure_constant). We can rewrite the second term using $\alpha$, giving

$$E\sim {\hbar^2\over 2ma^2}  -{\alpha \hbar c\over a}.$$

The two terms act in opposite directions: the kinetic energy term prefers large separations (to lower the energy) whereas the potential energy term prefers small separations. Minimize with respect to $a$

$${\partial E\over \partial a} = -{\hbar^2\over ma^3} + {\alpha \hbar c\over a^2} = 0$$

$$\Rightarrow a = \alpha^{-1} {\hbar\over m c}.$$

The lengthscale $\hbar/mc$ is known as the Compton wavelength of the electron. 

Substituting this value of $a$ into the energy gives

$$E = -{1\over 2}\alpha^2 mc^2.$$

```{admonition} Exercise

Put in numbers and calculate $a$ and $E$. For the energy you can use $mc^2=511\ {\rm keV}$ and calculate the energy in eV.

```

```{dropdown} Solution

The answers are $E= -13.6\ {\rm eV}$, which is the actual ground state energy of hydrogen as we'll see, and $a = 5.3\times 10^{-11}\ {\rm m}$ (often written as $0.53$ Angstroms) which is the [Bohr radius](https://en.wikipedia.org/wiki/Bohr_radius).

```


## Further reading

- We've covered material from Townsend 9.4 here. We'll return to the earlier parts of chapter 9 next time.

