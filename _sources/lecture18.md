# Lecture 18 Mar 15

## More on the H atom fine structure

Last time we looked at the spin-orbit coupling in hydrogen and argued that the states that diagonalize the perturbation $\hat{H}_1\propto \hat{\mathbf{L}}\cdot \hat{\mathbf{S}}$ in the degenerate subspace at a given energy level $n$ are the eigenstates of the total angular momentum operator $\hat{\mathbf{J}} = \hat{\mathbf{L}} + \hat{\mathbf{S}}$, i.e.

$$\ket{\ell, s, j, m_j}.$$

A general rule in quantum mechanics is that when we add two angular momentum vectors with angular momentum quantum numbers $\ell_1$ and $\ell_2$, the total angular momentum can take values 

$$\ell_1+\ell_2, \dots |\ell_1-\ell_2|$$

in integer steps. In our case, we have $\ell_1=\ell$ and $\ell_2=s=1/2$. This means that for a given $\ell$, the allowed values of $j$ are either $\ell+1/2$ or $\ell-1/2$ (for $\ell=0$ there is just one value $j=1/2$). The states that diagonalize the perturbation are

$$\ket{\ell, s={1\over 2}, j=\ell\pm {1\over 2}, m_j} = \sqrt{\ell\pm m_j + {1\over 2}\over 2\ell+1}\ket{\ell,m_j-{1\over 2}}\ket{\uparrow} +\sqrt{\ell\mp m_j + {1\over 2}\over 2\ell+1}\ket{\ell,m_j+{1\over 2}}\ket{\downarrow} $$

i.e. at a given $\ell$, the perturbation mixes together states that have the same $m_j$, either with $m=m_j-{1\over 2}$ and $m_s=+{1\over 2}$ or with $m=m_j+{1\over 2}$ and $m_s=-{1\over 2}$.

The angular part of the matrix element can then be computed, e.g. for $j=\ell+{1\over 2}$, as

$$\braket{\ell,{1\over 2},\ell+{1\over 2},m_j|\hat{\mathbf{L}}\cdot \hat{\mathbf{S}}|\ell,{1\over 2},\ell+{1\over 2},m_j}$$

$$\propto \braket{\ell,{1\over 2},\ell+{1\over 2},m_j|\hat{J}^2-\hat{L}^2-\hat{S}^2|\ell,{1\over 2},\ell+{1\over 2},m_j}$$

$$\propto j(j+1)-\ell(\ell+1)-s(s+1)$$

$$\propto (\ell+{1\over 2})(\ell+{3\over 2}) - \ell(\ell+1) - {3\over 4}$$

$$\propto \ell.$$

For $j=\ell-{1\over 2}$ the same argument gives $-\ell-1$. For the full spin-orbit matrix element, we also have to do the radial integral over the states. The prefactor is $\propto 1/r^3$, so we need

$$\langle {1\over r^3}\rangle = {Z^3\over a_0^3 n^3} {1\over \ell (\ell+1)(\ell+{1\over 2})}$$

(Townsend problem 11.19 proves this). Putting this together gives the final energy correction for spin-orbit coupling as 

$$E^{(1)} = \left(Z\alpha\right)^2 {13.6\ \mathrm{eV}\over 2n^3 \ell (\ell+1)(\ell+{1\over 2})} \begin{cases}
\ell  & \text{$j=\ell+{1\over 2}$}\\
-\ell-1 & \text{$j=\ell-{1\over 2}$}
\end{cases}.
$$

What this means is that the energy levels at a given $n$ have a small correction (fine structure) that depends on $n$, $\ell$ and $j$. 

Now in fact, once the different relativistic corrections (relativistic kinetic energy, spin orbit coupling, Darwin term) are all added together, the energy shift is

$$E^{(1)} = -\left(Z\alpha\right)^2 {13.6\ \mathrm{eV}\over n^3} \left({1\over j+{1\over 2}}-{3\over 4n}\right),
$$

so that the energy of a given state depends on the two quantum numbers $n$ and $j$ (but not $\ell$ explicitly).

**Spectroscopic notation** is used to write down the different states. For example, the ground state(s) of hydrogen can be written as 

$$1^2s_{1/2}.$$

Here the leading "1" specifies that $n=1$. The 's' indicates that $\ell=0$ (s-orbital). The superscript 2 corresponds to $2s+1$ -- for a single electron this will always be 2, so we could  omit this for hydrogen. But it's needed for more complicated multi-electron states of atoms. Finally, the subscript $1/2$ indicates the value of $j$ (which can only be 1/2 for the ground state of hydrogen with $\ell=0$ and $s=1/2$). Note that there are two states here, since $j=1/2$ so we can have either $m_j=-{1\over 2}$ or $m_j=+{1\over 2}$, this corresponds to the electron being spin up or spin down.

For $n=2$, the possible states are (omitting the superscript for the spin since we just have one electron) $2s_{1/2}$, $2p_{1/2}$, and $2p_{3/2}$.  If you add up the possible $m_j$ values for each $j$, you should find that we have 8 possible states, which equals $2n^2$ as expected for level $n$ ($2n^2$ rather than $n^2$ because we are now including the spin of the electron).

## Multi-particle states and spin-statistics

We next are going to look at systems with multiple particles, and a good first example to think about is a system with two identical non-interacting spin 1/2 particles. There are clearly 4 different arrangements of the two spins, since either spin can be up or down. If both particles are spin up, we could write the state as $\ket{\uparrow\uparrow}$, where the notation is such that the first arrow indicates the state of particle 1 and the second indicates the state of particle 2. Similarly, both particles down would be the state $\ket{\downarrow\downarrow}$. 

What about the situation where one particle is spin up and the other spin down? We could write $\ket{\uparrow\downarrow}$ but this has a problem that in quantum mechanics two identical particles are indistinguishable. We can predict the probability of finding one particle here and the other particle there in a two-particle system, but we can't say which particle is which. This is unlike classical mechanics where there is no problem identifying one of the particles as "particle 1" and the other as "particle 2".

The mathematical statement of this is that we need our two-particle state to be unchanged under the action of the particle-exchange operator $\hat{P}_{1,2}$ that exchanges the two particle labels. However, when we say "unchanged" in fact we could introduce a phase, that would be okay since we can always multiply a quantum state by a complex phase and it doesn't change the physical state. What phases are allowed? We can only have 0 or $\pi$ since we need that state to come back to its original state when we apply the particle-exchange operator twice. 

So, there are two kinds of two-particle states that we can construct: **symmetric** under particle exchange

$$\hat{P}_{12}\ket{\Psi} = \ket{\Psi}$$

or **antisymmetric** 

$$\hat{P}_{12}\ket{\Psi} = -\ket{\Psi}.$$

Whenever we write down a multiparticle state, we need to make sure it is either symmetric or antisymmetric under exchange of two particles.

For the two-spin system, the symmetric states are

$$\ket{\uparrow\uparrow}$$

$$\ket{\downarrow\downarrow}$$

$${1\over \sqrt{2}}\left(\ket{\uparrow\downarrow} + \ket{\downarrow\uparrow}\right)$$

while there is only one antisymmetric state

$${1\over \sqrt{2}}\left(\ket{\uparrow\downarrow} - \ket{\downarrow\uparrow}\right).$$

The **spin-statistics** theorem states that **fermions** (half-integer spin particles) must have anti-symmetric states while **bosons** (integer spin particles) have symmetric states. The proof relies on relativistic quantum mechanics, so we won't prove this here. We'll discuss some of the consequences of this next time and apply this as we write down the eigenstates of the two electrons in the helium atom.


## Further reading

- Townsend 11.5 and 11.6 has a lot more detail on fine structure if you are interested.
- We're starting Townsend Chapter 12 and will talk about the helium atom next time.
