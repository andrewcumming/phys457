# Lecture 8 Jan 30

## Diatomic molecules

The rotational and vibrational energy levels of diatomic molecules are discussed in Townsend 9.7. It's interesting to do some back of the envelope type estimates to see how the vibrational and rotational energies relate to the atomic binding energy of 13.6 eV that we saw for hydrogen.

**Rotation**. First consider rotation. If the reduced mass of the molecule is $\mu$ and the separation of the two atoms is $a$, then we have

$$E_\mathrm{rot}\approx {\ell(\ell+1) \hbar^2\over 2\mu a^2}.$$

We'd expect the separation between the two nuclei in a molecule to be of order the Bohr radius, $a = \alpha^{-1} \hbar/m_ec$, so we can write

$$E_\mathrm{rot}\approx {\ell(\ell+1) \hbar^2\over 2\mu}{\alpha^2 m_e^2 c^2\over \hbar^2}\approx \ell(\ell+1)\left[{1\over 2} \alpha^2 m_e c^2\right] \left({m_e\over\mu}\right).$$

You might recognize the energy $(1/2)\alpha^2m_ec^2 = 13.6\ {\rm eV}$ as the [binding energy of hydrogen](https://andrewcumming.github.io/phys457/lecture4.html#back-of-the-envelope-hydrogen-atom). So we see that the spacing between rotational levels is smaller than this by a factor $m_e/\mu\sim m_e/m_p\sim 1/2000$, corresponding to energies $\sim 7\ {\rm meV}$. This corresponds to photons in the microwave range.

**Vibrations**. Since Coulomb forces determine the equilibrium separation of the nuclei in the molecule, we'd expect the restoring force resulting from a small perturbation in the spacing $a\rightarrow a+\Delta a$ to be 

$$\mathrm{restoring\ force}\sim -{e^2\over 4\pi \epsilon_0 a^2}{\Delta a\over a}$$

giving an equation of motion 

$$\mu{d^2\over dt^2}\Delta a \sim -{e^2\over 4\pi \epsilon_0 a^3}\Delta a$$

and therefore an oscillation frequency given by 

$$(\hbar\omega)^2 \approx {\hbar^2e^2\over 4\pi \epsilon_0 \mu a^3} \approx  {\alpha\hbar^3c\over \mu a^3}\approx {\alpha\hbar^3c\over\mu} {\alpha^3 (m_e c)^3\over \hbar^3}\approx 
\alpha^4 m_e^2 c^4 {m_e\over \mu}$$

giving 

$$E_\mathrm{vib}\approx \left[\alpha^2 m_e c^2\right] \left({m_e\over\mu}\right)^{1/2}.$$

We see that vibrational levels lie in between the atomic and rotational energy scales, with $\hbar\omega\sim 27\ \mathrm{eV} /(2000)^{1/2}\sim 0.6\ \mathrm{eV}$. In terms of photon energy, these transitions involve infrared photons.

Townsend shows some examples of photon spectra showing the discrete energies involved in transitions between these different modes of vibration and rotation. We'll come back to the interaction of radiation and atoms and molecules later in the course.


## Schrödinger equation for the radial part of the hydrogen atom wavefunction

[Last time](https://andrewcumming.github.io/phys457/lecture7.html#the-radial-part-of-the-two-body-problem), we ended up with the equation for the radial part of the wavefunction $R(r)$ written in terms of the function $u(r) = rR(r)$, which obeys

$$\left[- {\hbar^2\over 2\mu}{d^2\over d r^2} +  {\ell(\ell+1)\hbar^2\over 2\mu r^2} + V(r)\right]u(r) = E u(r).$$

The problem has reduced to solving the 1D Schrödinger equation! One important difference from the standard 1D problem is that the coordinate $r$ runs from 0 to $\infty$ rather than $\pm \infty$. 

We can get a feeling for the behaviour of $u(r)$ by looking at the limits as $r\rightarrow 0$ and as $r\rightarrow \infty$.

For $r\rightarrow 0$, the centrifugal term dominates the terms containing $V(r)$ and $E$ which means that the second derivative has to balance the centrifugal term in order for the equation to be satisfied:

$$u^{\prime\prime} = {\ell(\ell+1)u\over r^2}.$$

If we try a power law solution $u\propto r^n$, we get

$$n(n-1) = \ell(\ell+1)\Rightarrow n=-\ell, \ell+1.$$

The solution $u\propto r^{-\ell}$ diverges at the origin [for $\ell=0$, $u$ is constant but then $R=u/r$ diverges], so we need the solution

$$u\propto r^{\ell +1}\hspace{1cm} r\rightarrow 0.$$

For $r\rightarrow \infty$, the second derivative is balanced by the constant term involving $E$, ie.

$$u^{\prime\prime} = -{2\mu E\over \hbar^2} u.$$

We are looking for bound states which have $E<0$, so it is useful to write

$$u^{\prime\prime} = +\left({2\mu (-E)\over \hbar^2}\right) u$$

which gives 

$$u\propto \exp\left(-{\sqrt{2\mu(-E)} r\over \hbar} \right)\hspace{1cm} r\rightarrow \infty.$$

(There's also a growing exponential solution, but we discard that one because $u$ would then diverge at large $r$).

With these limits in hand, we can then sketch possible solutions for $u(r)$ and learn something about the energy levels of the atom. We'll do this next time.



## Further reading

- Townsend 10.1 on the radial wavefunction
- Townsend 9.7 on diatomic molecules

