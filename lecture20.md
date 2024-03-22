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

```{dropdown} Derivation of these expectation values

Let's do first $\langle 1/r_1\rangle$. The full integration we need to do is 

$$\left\langle {1\over r_1} \right\rangle = \int d^3\mathbf{r}_1 \int d^3\mathbf{r}_2 \psi^\star(r_1, r_2) {1\over |\mathbf{r_1}|} \psi(r_1, r_2)\Bigg/\int d^3\mathbf{r}_1 \int d^3\mathbf{r}_2 |\psi(r_1, r_2)|^2  ,$$

where the trial wavefunction depends only on $r_1$ and $r_2$, not on the angles $\theta_1$, $\phi_1$, $\theta_2$ or $\phi_2$, and I've explicitly included the normalization factor. Since the quantity we're averaging depends only on $r_1$, the integrals cancel except for the $r_1$ integration, giving

$$\left\langle {1\over r_1} \right\rangle = \int_0^\infty r_1^2 dr_1 {1\over r_1} e^{-2\beta r_1/a_0} \Bigg/ \int_0^\infty r_1^2 dr_1 e^{-2\beta r_1/a_0}$$

$$= \int_0^\infty r_1 dr_1 e^{-2\beta r_1/a_0} \Bigg/ \int_0^\infty r_1^2 dr_1 e^{-2\beta r_1/a_0} ={\beta\over a_0}.$$

The answer is the same for $\langle 1/r_2\rangle$.

Similarly, 

$$\left\langle {\partial^2\over\partial r_1^2} \right\rangle = \int_0^\infty r_1^2 dr_1  e^{-\beta r_1/a_0} {\partial^2\over\partial r_1^2} e^{-\beta r_1/a_0} \Bigg/ \int_0^\infty r_1^2 dr_1 e^{-2\beta r_1/a_0} = {\beta^2\over a_0^2}$$

and the same for $r_2$. 

The last one is more tricky. 
We want

$$I = \int d^3\mathbf{r}_1\int d^3\mathbf{r}_2\ e^{-2\beta(r_1+r_2)/a_0}{1\over |\mathbf{r}_2-\mathbf{r}_1|}$$

Choose coordinates such that the $z$-axis lies along $\mathbf{r}_1$. Then $\mathbf{r}_1\cdot\mathbf{r}_2 = r_1r_2\cos\theta$ and we can write the integral as

$$
I=\int d^3\mathbf{r}_1\int 2\pi r_2^2dr_2\ e^{-2\beta(r_1+r_2)/a_0}\int \sin\theta d\theta {1\over \sqrt{r_1^2+r_2^2-2r_1r_2\cos\theta}}$$

The angular part is

$$\int_{-1}^{1} d\mu {1\over \sqrt{r_1^2+r_2^2-2r_1r_2\mu}} = {r_1+r_2 - |r_2-r_1|\over r_1r_2}$$

giving

$$I=\int_0^\infty 4\pi r_1^2dr_1 \left[\int_0^{r_1} 2\pi r_2^2dr_2\ e^{-2\beta(r_1+r_2)/a_0} {2\over r_1} + \int_{r_1}^\infty 2\pi r_2^2dr_2\ e^{-2\beta(r_1+r_2)/a_0} {2\over r_2} \right]$$

$$=16\pi^2 \int_0^\infty r_1 dr_1  e^{-2\beta r_1/a_0} \left[ \int_0^{r_1} r_2^2dr_2\ e^{-2\beta r_2/a_0} +  \int_{r_1}^\infty r_1r_2\,dr_2\ e^{-2\beta r_2/a_0}\right]$$

$$= 16\pi^2 {a_0^3\over 4\beta^3} \int_0^\infty r_1 dr_1  e^{-4\beta r_1/a_0} \left( e^{2\beta r_1/a_0} - 1 - {\beta r_1\over a_0}\right)$$

$$= 16\pi^2 {a_0^3\over 4\beta^3} \left[ {a_0^2\over 4\beta^2} - {a_0^2\over 16\beta^2} - {\beta\over a_0}{2a_0^3\over 64\beta^3}\right]$$

$$= 16\pi^2 {a_0^5\over 16 \beta^5} \left[1 - {1\over 4} - {1\over 8}\right]$$

$$= 16\pi^2 {a_0^5\over 16 \beta^5} {5\over 8}.$$

The normalization factor is

$$\int d^3\mathbf{r}_1\int d^3\mathbf{r}_2\ e^{-2\beta(r_1+r_2)/a_0}=16\pi^2 \int r_1^2 dr_1 r_2^2 dr_2 e^{-2\beta(r_1+r_2)/a_0} = 16\pi^2 {a_0^6\over 16\beta^6}.$$

Therefore

$$\left\langle {1\over r_{12}}  \right\rangle = {5\over 8}{\beta\over a_0}.$$

```


## Further reading

- Townsend Chapter 12.