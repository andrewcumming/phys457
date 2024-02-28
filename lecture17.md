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

There is a quadratic correction to the energy $\propto |\mathbf{E}|^2$: this is exactly what you would find using non-degenerate perturbation theory treating the electric field as a perturbation. It makes sense because the two energy levels are non-degenerate, and the corresponding stationary states do not have a dipole moment since they are eigenvectors of the parity operator and respect the symmetry of the Hamiltonian.


2. $\mu_e|\mathbf{E}|\gg 2A$. The energy is 



## The "real" hydrogen atom: fine structure




## Further reading

- Townsend Chapter 11.
- Section 4.5 of Townsend discusses the ammonia molecule (this was covered in the Quantum 1 course).
