# Lecture 20 Mar 21

## Variational method applied to helium

The **variational method** uses the fact that for any state $\ket{\Psi}$, 

$${\braket{\Psi|\hat{H}|\Psi}\over \braket{\Psi|\Psi}}\geq E_1$$

where $E_1$ is the ground state energy for the Hamiltonian $\hat{H}$. The denominator is there in case $\ket{\Psi}$ is not normalized. This is straightforward to see: if $\ket{\Psi}$ was the true ground state, then we would get equality. For any other state, we have introduced some contributions from higher order states which have higher energies, so the value increases. 

This is a powerful method which allows an estimate of the ground state energy to be obtained for Hamiltonians $\hat{H}$ that can't be solved exactly.  A common approach is to consider a parametrized family of possible wavefunctions, and find the values of the parameter(s) that minimize the energy. This is then the best estimate (upper limit) for the ground state energy. 

```{admonition} Exercise:

Apply this idea to the ground state of helium.  For the trial wavefunction, replace the charge $Z$ in the hydrogen ground state $\psi_{100}$ with an effective charge $Z_{\rm eff}$ -- the idea is that the electron feels a smaller force from the nucleus because of screening from the other electron. The energy can then be minimized with respect to the parameter $Z_{\rm eff}$. What value of effective charge minimizes the energy and what is the ground state energy that you obtain?

To help you avoid doing a lot of integrals, here are some useful formulae. For a wavefunction $\psi(r) \propto e^{-\beta(r_1+r_2)/a_0}$, 

$$\left\langle {\partial^2\over\partial r_i^2}\right\rangle = {\beta^2\over a_0^2}, \hspace{1cm}\left\langle {1\over r_i}\right\rangle = {\beta\over a_0}, \hspace{1cm}\left\langle {1\over r_{12}}\right\rangle = {5\beta\over 8a_0}.$$

```


## Further reading

- Townsend Chapter 12.