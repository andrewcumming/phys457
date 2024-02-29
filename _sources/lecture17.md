# Lecture 17 Feb 29

## More on the ammonia molecule


The example of ammonia that we discussed last time is interesting because it can be solved exactly and compared to the perturbation theory result.

If we use the $\ket{1}$ and $\ket{2}$ states as a basis -- i.e. the states with the nitrogen molecule either above or below the plane -- the Hamiltonian can be written

$$\hat{H} = \begin{pmatrix}
E_0+\mu_e|\mathbf{E}| & -A \\
-A & E_0-\mu_e|\mathbf{E}| 
\end{pmatrix}
$$

The off-diagonal $-A$ terms are there because we know that the $\ket{1}$ and $\ket{2}$ states are not stationary states (because they do not respect the symmetry of the Hamiltonian), so $\ket{1}$ and $\ket{2}$ do not diagonalize the Hamiltonian. However, the electric field couples to the dipole moment of the $\ket{1}$ and $\ket{2}$ states, so the part of the Hamiltonian associated with the electric field is diagonal in this basis.

It is straighforward to find the eigenvalues of $\hat{H}$. They are

$$E = E_0 \pm \sqrt{(\mu_e|\mathbf{E}|)^2 + A^2}.$$

If there is no applied electric field, the energies are $E_0\mp A$ with corresponding stationary states $(\ket{1}\pm \ket{2})\sqrt{2}$ (denoted $\ket{I}$ and $\ket{II}$ in Townsend).

Now we can look at the two different orderings of $\mu_e|\mathbf{E}|$ and $A$ (both assumed to be $\ll E_0$):

1. $\mu_e|\mathbf{E}|\ll 2A$. In this case the electric field is a small perturbation compared to the energy splitting $2A$ between the stationary states. The energies are then

$$E = E_0 \pm \sqrt{(\mu_e|\mathbf{E}|)^2 + A^2}\approx  E_0\pm A \left(1 + {1\over 2}\left({\mu_e|\mathbf{E}|\over A}\right)^2 + \dots\right)$$

There is a quadratic correction to the energy $\propto |\mathbf{E}|^2$: this is exactly what you would find using non-degenerate perturbation theory using the $\ket{I}$, $\ket{II}$ basis and treating the electric field as a perturbation. It makes sense because the two energy levels are non-degenerate, and the corresponding stationary states do not have a dipole moment since they are eigenvectors of the parity operator and respect the symmetry of the Hamiltonian.


2. $\mu_e|\mathbf{E}|\gg 2A$. The energy associated with the electric field now is much larger than the splitting between the unperturbed energy levels. The energy is

$$E = E_0 \pm \sqrt{(\mu_e|\mathbf{E}|)^2 + A^2}\approx  E_0\pm \mu_e|\mathbf{E}|\left(1 + {1\over 2}\left({A\over \mu_e|\mathbf{E}|}\right)^2 + \dots\right)$$

We now see a linear Stark effect, as we would find with degenerate perturbation theory where we move to a basis in which $\hat{H}_1$ is diagonal, i.e. $\ket{1}$, $\ket{2}$. 

The important point about non-degenerate perturbation theory is that we need the terms $\propto \braket{\Psi_n|\hat{H}_1|\Psi_k}/(E_n^{(0)}-E_k^{(0)})$ to remain small. In this problem, that corresponds to the ratio $\mu_e|\mathbf{E}|/2A$. Once this ratio becomes large, we should use degenerate perturbation theory instead.

You can see more of the details of the perturbation theory in each limit worked out in Townsend section 11.4.


## The "real" hydrogen atom: fine structure

We saw that there are $n^2$ degenerate states in each energy level of the hydrogen atom, or actually $2n^2$ once we include the electron spin. In fact there are relativistic effects that break this degeneracy at the level 

$$\left({v_e\over c}\right)^2 \approx {2E\over m_e c^2}\approx (Z\alpha)^2\approx 5\times 10^{-5} Z^2.$$

These small shifts are known as the *fine structure*. There are three contributions (see Townsend section 11.5): (i) the correction from using the relativistic expression for energy rather than non-relativistic, (ii) the spin-orbit interaction, and (iii) the Darwin term. The first is straightforward to deal with, and the third requires relativistic quantum mechanics to derive. We'll focus on the spin-orbit correction, which is a another example of a situation where we have to find the correct basis to diagonalize the perturbation.

First, let's derive the spin-orbit coupling term. The idea is that in the rest frame of the electron there is a magnetic field 

$$\mathbf{B} = -{\mathbf{v}\times \mathbf{E}\over c^2}$$

which comes from the Lorentz transformation into the electron rest frame. The electric field of the proton is $\mathbf{E} = (eZ/4\pi \epsilon_0 r^3)\mathbf{r}$ and also writing $\mathbf{v} = \mathbf{p}/m_e$ gives

$$\mathbf{B} = {eZ\over 4\pi\epsilon_0 m_e c^2 r^3}\mathbf{r}\times \mathbf{p} = {eZ\over 4\pi\epsilon_0 m_e c^2 r^3}\mathbf{L}.$$

[Question to think about: where is the $\mu_0$ in this formula?]

The magnetic moment of the electron is 

$$\mathbf{\mu} = - g \mu_B {\mathbf{S}\over \hbar}$$

where $\mu_B=e\hbar/2m_e$ is the Bohr magneton and $g=2$ for the electron, and $\mathbf{S}$ is the electron spin. The interaction energy is 

$$\hat{H}_1 = -\mathbf{\mu}\cdot \mathbf{B},$$

ie. the magnetic moment wants to align with the magnetic field. Putting together our expressions for $\mathbf{\mu}$ and $\mathbf{B}$ gives

$$\hat{H}_1 = {1\over 2} {Ze^2\over 4\pi\epsilon_0}{1\over m_e^2 c^2 r^3}{\mathbf{L}\cdot\mathbf{S}},$$

where I've also included an extra factor of $1/2$ in the prefactor which comes from a full relativistic treatment of the H atom (this comes from an effect known as Thomas precession and also comes from the non-relativistic expansion of the Dirac equation which is the relativistic version of the Schrödinger equation).

If you make the substitution $e^2/4\pi\epsilon_0=\alpha \hbar c$ and use the Bohr radius $a_0=\hbar/\alpha m_e c$, then you can show that this can be rewritten as

$$\hat{H}_1 = Z^2\alpha^2 \left({a_0\over Zr}\right)^3 {\hat{\mathbf{L}}\cdot\hat{\mathbf{S}}\over \hbar^2} {1\over 2}\alpha^2 Z^2 m_e c^2 $$

which shows that this term is of order $(Z\alpha)^2$ compared to the hydrogen atom ground state energy.

Now that we are including the spin of the electron, so we have stationary states 

$$\ket{n,\ell, m, s, m_s}$$

i.e. we specify the state with $n,\ell$ and $m$ as before but now we also need to add the electron spin $s$ and $z$-component of the spin $m_s$. Since we are dealing with a single electron, we always have $s=1/2$, so we could drop $s$ from the list if we wanted.

It is straightforward to show that the operator $\hat{\mathbf{L}}\cdot\hat{\mathbf{S}}$ is not diagonal in this basis. A way to see this is to use the angular momentum ladder operators to write

$$\hat{\mathbf{L}}\cdot\hat{\mathbf{S}} = {1\over 2}\left(\hat{L}_+\hat{S}_- +\hat{L}_-\hat{S}_+ \right) + \hat{L}_z\hat{S}_z.$$

This shows that $\hat{\mathbf{L}}\cdot\hat{\mathbf{S}}$ will couple a state with $m, m_s$ for example with another state that has $m+1, m_s-1$, i.e. the off-diagonal matrix elements will not vanish. This means that we will have to find the linear combinations of states that diagonalize $\hat{H}_1$ and then we can use degenerate perturbation theory to calculate the corrections to the energies that come from the $\hat{\mathbf{L}}\cdot\hat{\mathbf{S}}$ term.

What are these linear combinations? There is a clue in the fact that $m$ and $m_s$ are changed by the ladder operators, but always in opposite directions. In other words, if we form a total angular momentum operator

$$\hat{\mathbf{J}} = \hat{\mathbf{L}} + \hat{\mathbf{S}}$$

the $z$-component $m_j = m + m_s$ (ie. the eigenvalue of $\hat{J}_z$) is conserved by $\hat{\mathbf{L}}\cdot\hat{\mathbf{S}}$. Furthermore, we can see that the product $\mathbf{L}\cdot\mathbf{S}$ is not changed if we perform a rotation on both the $\mathbf{L}$ and $\mathbf{S}$ vectors together. So the Hamiltonian keeps a rotational symmetry but only if we rotate both, ie. with the generator of rotations $\mathbf{J}$. If we write 

$$2\hat{\mathbf{L}}\cdot\hat{\mathbf{S}} = \hat{\mathbf{J}}^2 - \hat{\mathbf{L}}^2 -\hat{\mathbf{S}}^2$$

then we can see that $[\hat{H},\hat{J}^2]=0$ which also shows that we can write the stationary states in terms of eigenstates of $\hat{\mathbf{J}}$.

This suggests then that the new basis we need to diagonalize $\hat{H}_1$ is

$$\ket{n,\ell, s, j, m_j},$$

i.e. we replace $m$ and $m_s$ by $j$ and $m_j$. The physical reason for this is that the interaction between the magnetic moment of the electron and the magnetic field tries to align the dipole moment with the field, but because the dipole moment is created by the electron spin the result is that the spin precesses rather than aligns. The angular momentum directions change, so that $m$ and $m_s$ are no longer good quantum numbers. The magnitudes are not changed by precession, so $\ell$ is still a good quantum number for example.

We'll look in more detail at these states next time. We can use them to evaluate the corrections to the energy due to the $\hat{\mathbf{L}}\cdot\hat{\mathbf{S}}$ term and we'll see that the energy levels are split, now depending on both $n$ and $j$ rather than $n$ only in the unperturbed H atom.


## Further reading

- Townsend Chapter 11.
- Section 4.5 of Townsend discusses the ammonia molecule (this was covered in the Quantum 1 course).
