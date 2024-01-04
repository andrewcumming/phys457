# Lecture 1 Jan 4

## Overview

This course follows on directly from PHYS 357 Quantum Physics I last term where you looked at 

- spin 1/2 particles
- angular momentum in quantum mechanics, including the idea of symmetries <-> conserved quantities
- time evolution through the Hamiltonian
- how to deal with 2-particle states (spin singlet and triplet)
- particles moving in 1D potentials $V(x)$, including the harmonic oscillator

as discussed in Chapters 1 to 7 of Townsend's book. This gives you an excellent grounding in the basic ideas of quantum mechanics. In this course, we will push ahead into the second half of the book. The overall goal is to begin to tackle "real" systems by looking at

- what happens when we go into >1D: the two-body problem, bound states of central potentials, the hydrogen atom
- problems that we can't solve exactly: perturbation theory
- more on multiple-particle systems, and in particular the effects of identical particles
- scattering
- interaction of charged particles with electromagnetic radiation

## Postulates of Quantum Mechanics

As a way to get started, let's discuss the basic "rules" that govern quantum systems. These are often given as the *postulates of quantum mechanics*. 

**Postulate 1.** All the information about the system is contained in the state 

$$\ket{\Psi}$$

Here, $\ket{\Psi}$ is a normalized vector in Hilbert space, $\braket{\Psi|\Psi}=1$.

[**Aside:** Actually for open systems, things are more complicated. For example, consider a system in contact with a heat bath at some temperature $T$. Statistical mechanics (see PHYS 362 this term!) tells us that the probability of finding the system in a state with energy $E$ is given by a boltzmann factor $e^{-E/ k_B T }$. So we have a situation where our system is in a stationary state (not a superposition of states, a definite stationary state), *but* we don't necessarily know which of the stationary states $\ket{n}$ it is, just the probability of each one, $e^{-E_n/k_BT}$. In this situation, we say that our system  is in a **mixed state** rather than **pure state**, and we describe the system with a **density matrix $\rho$**. If you take PHYS 551 you'll hear more about mixed states, but in this course we'll focus on pure states only. If you are interested in learning more, you can read about mixed states and the density operator in section 5.7 of Townsend.]

Often we'll construct the state by combining Hilbert spaces, e.g. two spin 1/2 particles could be in the triplet state $\ket{\uparrow\uparrow} = \ket{\uparrow}\ket{\uparrow} = \ket{\uparrow}\otimes\ket{\uparrow}$. We don't usually write out the direct product symbol $\otimes$ explicitly, instead it is  taken implicitly that operators for particle 1 operate in the space corresponding to particle 1 etc. In this course, we'll construct similar states for electrons in atoms, e.g. $\ket{n \ell m}\otimes\ket{m_s}$ where $n, \ell, m$ are the quantum numbers that label the energy, total orbital angular momentum and $z$-component of orbital angular momentum, and $m_s$ is the electron spin.

**Postulate 2.** Observable quantities $A$ are represented by Hermitian operators $\hat{A}$. 

Hermitian $\Rightarrow$ real eigenvalues, as needed for an observable.

The eigenstates of the operator can be used as a basis to represent the state $\ket{\Psi}$.

$$\ket{\Psi} = \sum_n \braket{n|\Psi} \ket{n}$$

$\ket{n}\bra{n}$ acts as a **projection operator**, projecting the state $\Psi$ onto the "direction" $\ket{n}$ in Hilbert space.

Summing these up we get the **identity operator** 

$$\sum_n \ket{n}\bra{n}$$

ie.

$$\ket{\Psi} = \sum_n \braket{n|\Psi} \ket{n}= \left(\sum_n \ket{n}\bra{n} \right)\ket{\Psi}=\ket{\Psi}$$

The list of coefficients $\braket{n|\Psi}$ specify the state given the basis $\left\{\ket{n}\right\}$.

```{admonition} Question
As an example, consider a particle in a 1D box (infinite potential well) in some state $\Psi$. What are some ways you could write down the state?

One answer to this question is that we could use the position eigenstates $\ket{x}$ to expand the state $\ket{\Psi}$. A particle in a position eigenstate $\ket{x}$ is located exactly at position $x$, $\hat{x}\ket{x}=x\ket{x}$. The position eigenstates obey the orthogonality relation $\braket{x|x^\prime} = \delta(x-x^\prime)$, where $\delta(x)$ is the Dirac delta function. 

There are an infinite number of coefficients $\braket{x|\Psi}$ because $x$ is a continuous variable. Specifying these coefficients is equivalent to specifying the wavefunction of the particle, ie. the wavefunction is defined as

$$\psi(x) \equiv \braket{x|\Psi}.$$
Also note that for this case where we have a continuous eigenvalue, the identity operator becomes $\int dx \ket{x}\bra{x}$.

Another basis with a continuous eigenvalue spectrum that we could use is the basis of momentum eigenstates, which satisfy $\hat{p}\ket{p}=p\ket{p}$. In this case, the coefficients are $\phi(p) = \braket{p|\Psi}$ which is the wavefunction in momentum space. [A useful relation is $\braket{x|p} = e^{ipx/\hbar} / \sqrt{2\pi \hbar}$. Try using this and the identity operator to prove that $\Psi(x)$ and $\phi(p)$ are Fourier transforms of each other.]

Finally, a third basis that we could use to expand $\Psi$ is the basis of stationary states $\ket{n}$ which are eigenstates of the Hamiltonian $\hat{H}\ket{n} = E_n\ket{n}$. Again, there are an infinite number of these, but now the eigenvalues are discrete.
```

**Postulate 3.** A measurement of $A$ **collapses** the state into the eigenstate $\ket{n}$ corresponding to observed value $A_n$. The probability that you measure $A_n$ is $|\braket{\Psi|n}|^2$.  

**Postulate 4.** Time evolution of a state is determined by the Hamiltonian 

$$-i\hbar {\partial \over \partial t} \ket{\Psi} = \hat{H}\ket{\Psi}$$

For a time-independent Hamiltonian, we have a time-evolution operator

$$\hat{U}(t) = e^{-i\hat{H}t/\hbar}$$

such that

$$\ket{\Psi(t)} =  \hat{U}(t) \ket{\Psi(0)} = e^{-i\hat{H}t/\hbar} \ket{\Psi(0)} = \sum \braket{n|\Psi(0)}  e^{-iE_nt/\hbar} \ket{n}.$$

This describes the idea that to evolve a state $\ket{\Psi(0)}$ in time, we can first write it as a combination of stationary states $\ket{n}$, update each stationary state using $e^{-iE_nt/\hbar}$ and then sum up to obtain $\ket{\Psi(t)}$.

One of the important quantities we'll look at a few times in this course is the **transition amplitude**, the amplitude to go from a state $\ket{m}$ at time $t^\prime$ to state $\ket{n}$ at time $t$, 

$$\braket{n,t|m, t^\prime}$$
 

## Path integrals

We're going to start with Chapter 8 of Townsend which is on path integrals. We won't be using the formalism of path integrals much  (if at all) in the rest of the course, which is why this topic is often left for a more advanced course. However, it teaches us a lot about how to think about quantum mechanics and its relation to classical physics, so I think it's an interesting topic to look at, with a neat connection to Lagrangian mechanics that you'll see in PHYS 351 if you are taking it this term. 

To describe the motion of a particle in quantum mechanics, we can look at the amplitude for going from position $x^\prime$ at time $t^\prime$ to position $x$ at time $t$. In quantum mechanics language, we need the transition amplitude between the states $\ket{x^\prime}$ and $\ket{x}$ over this time, otherwise known as the **propagator**

$$K(x,t; x^\prime, t^\prime) = \braket{x|e^{-i\hat{H}(t-t^\prime)/\hbar}|x^\prime}$$

The path integral is a way of computing the propagator by considering all possible trajectories of the particle between $x$ and $x^\prime$. For example, as a start we can divide the time period from $t^\prime$ to $t$ into two pieces, $t^\prime$ to $t^{\prime\prime}$ and then from $t^{\prime\prime}$ to $t$. If we do this, we have to consider all the possible intermediate locations $x^{\prime\prime}$ that the particle could move to at the intermediate time $t^{\prime\prime}$, so we'll end up doing an integral $\int dx^{\prime\prime}$ over all those intermediate locations. The path integral is the limit of this process where we divide up the time period $t^\prime$ to $t$ into infinitely small time slices, integrating over all possible positions at each of the time slices. This sounds complicated, but we'll show that the result is

$$K(x,t; x^\prime, t^\prime) \sim \int_\mathrm{paths} e^{iS/\hbar}$$

where the integral is over all possible space-time paths between $(x^\prime, t^\prime)$ and $(x,t)$.

The quantity $S$ is the **action** 

$$S = \int dt\ L$$ 

where $L$ is the **Lagrangian** 

$$ L = (\mathrm{kinetic\ energy} - \mathrm{potential\ energy})$$

(so a bit like the Hamiltonian but with a minus sign between the two terms).

In classical mechanics, there is the **principle of least action** which states that the path a particle follows is the path that minimizes the action $\delta S=0$ (or most correctly extremizes the action, sometimes it's a maximum). We will see that in quantum mechanics the picture is very different -- the particle actually takes all possible paths (!) and the action actually determines the phase contributed by each path (the $e^{iS/\hbar}$ term in the integral). Near the classical path which has $\delta S\approx 0$, the paths all contribute nearly the same phase and so add constructively. Away from the classical path, the phases vary wildly and destructively interfere. 

We will see the details of how to compute the path integral next week! 


## Further Reading

- Chapter 8 of Townsend
- [The Principle of Least Action](https://www.feynmanlectures.caltech.edu/II_19.html) from Volume 2 of the Feynman Lectures on Physics. See also [Optics: The Principle of Least Time](https://www.feynmanlectures.caltech.edu/I_26.html) from Volume 1.
