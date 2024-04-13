# Homework solutions

- [Homework 1 solutions](https://github.com/andrewcumming/phys457/blob/main/hw1_solutions.pdf) (TA: Renée Goodman)

- [Homework 2 solutions](https://github.com/andrewcumming/phys457/blob/main/hw2_solutions.pdf) (TA: Ivan Martinez)

- [Homework 3 solutions](https://github.com/andrewcumming/phys457/blob/main/hw3_solutions.pdf) (TA: Clément Fortin)

- [Homework 4 solutions](https://github.com/andrewcumming/phys457/blob/main/hw4_solutions.pdf) (TA: Renée Goodman)

- [Homework 5 solutions](https://github.com/andrewcumming/phys457/blob/main/hw5_solutions.pdf) (TA: Ivan Martinez)

- [Homework 6 solutions](https://github.com/andrewcumming/phys457/blob/main/hw6_solutions.pdf) (TA: Clément Fortin)

- [Homework 7 solutions](https://github.com/andrewcumming/phys457/blob/main/hw7_solutions.pdf) (TA: Renée Goodman)

- [Homework 8 solutions](https://github.com/andrewcumming/phys457/blob/main/hw8_solutions.pdf) (TA: Ivan Martinez)

### Homework 9

```{dropdown} Question 1: the singlet and triplet states as spin eigenstates

The $S_z$ operator is straightforward because we can write $\hat{S}_z = \hat{S}_{1,z} + \hat{S}_{2,z}$. Applying this to the triplet states you will find that they are eigenstates with eigenvalues $m_s\hbar=(1,0,-1)\times \hbar$, while the singlet state has eigenvalue 0. For $\hat{S}^2 = \hat{S}_1^2 + \hat{S}_2^2 + 2\hat{\mathbf{S}}_1\cdot \hat{\mathbf{S}}_2$, we can use Townsend equation (5.10) which gives

$$2\hat{\mathbf{S}}_1\cdot \hat{\mathbf{S}}_2 = \hat{S}_{1+}\hat{S}_{2-} + \hat{S}_{1-}\hat{S}_{2+} + 2\hat{S}_{1z}\hat{S}_{2z}.$$

Then

$$\hat{S}^2 \ket{\uparrow\uparrow} = \left(\hat{S}_1^2 + \hat{S}_2^2 + \hat{S}_{1+}\hat{S}_{2-} + \hat{S}_{1-}\hat{S}_{2+} + 2\hat{S}_{1z}\hat{S}_{2z} \right)  \ket{\uparrow\uparrow}$$

$$= \hbar^2\left({3\over 4} + {3\over 4} + 0 + 0 + 2\times {1\over 4}\right)\ket{\uparrow\uparrow}   $$

$$ = 2\hbar^2 \ket{\uparrow\uparrow}$$

as expected for total spin $s=1$. The state $\ket{\downarrow\downarrow}$ gives the same answer.

For the $m_s=0$ states, we need 

$$\hat{S}^2 \ket{\uparrow\downarrow} = \left(\hat{S}_1^2 + \hat{S}_2^2 + \hat{S}_{1+}\hat{S}_{2-} + \hat{S}_{1-}\hat{S}_{2+} + 2\hat{S}_{1z}\hat{S}_{2z} \right)  \ket{\uparrow\downarrow}$$

$$= \hbar^2\left({3\over 4} + {3\over 4} + 0 + 1 - 2\times {1\over 4}\right)\ket{\uparrow\downarrow}$$

$$ = 2\hbar^2 \ket{\uparrow\downarrow}$$

and the same for $\ket{\downarrow\uparrow}$. This means that the $m_s=0$ triplet state (symmetric) has $s=1$ whereas the $m_s=0$ singlet state (antisymmetric) has $s=0$. 
```

```{dropdown} Question 2: variational principle estimate of the ground state energy

**Townsend 12.7**. We have a potential $V(x) = a|x|$ and want to estimate the ground state energy with the trial wavefunction $\psi(x) = (b/\pi)^{1/4} e^{-bx^2/2}$. The contribution of the potential term in the Hamiltonian is

$$\braket{\psi|V|\psi} = 2a \sqrt{b\over \pi}\int_0^\infty dx \, x e^{-bx^2} = {a\over \sqrt{b\pi}}.$$

The kinetic energy term is

$$\braket{\psi|{p^2\over 2m}|\psi} = -{\hbar^2\over 2m} \sqrt{b\over \pi}\int_{-\infty}^\infty dx \, e^{-bx^2/2} {\partial^2\over\partial x^2}e^{-bx^2/2}= -{\hbar^2\over 2m} \sqrt{b\over \pi}\int_{-\infty}^\infty dx \,  e^{-bx^2} b(bx^2-1)$$

$$ = {\hbar^2\over 2m} \sqrt{b\over \pi} {b\over 2} \sqrt{\pi\over b}$$

$$ = {\hbar^2b\over 4m}.$$

The estimate for the ground state energy is therefore

$$E \leq {\hbar^2b\over 4m} + {a\over \sqrt{b\pi}}$$

Minimize the right hand side with respect to $b$:

$${d\over db} \left({\hbar^2b\over 4m} + {a\over \sqrt{b\pi}}\right) = 0$$

$$\Rightarrow {\hbar^2\over 4m} - {a\over 2\sqrt{\pi}b^{3/2}} = 0$$

$$\Rightarrow b = \left({2ma\over \sqrt{\pi}\hbar^2}\right)^{2/3}$$

Substituting in this value of $b$ gives 

$$E \leq {3\over 2} \left({\hbar^2a^2\over 2\pi m}\right)^{1/3}.$$

(Note that this has the correct units since according to the definition of $V$, $a$ is an energy per unit length).
```


```{dropdown} Question 3: spin-spin interaction between electrons

**Townsend 12.3**. *Estimate the singlet-triplet splitting of the two electrons in helium due to a direct spin-spin interaction.*

The magnetic moment of the electron due to its spin is $\mu= (e/m_e)\times \hat{S}$ (see spin-orbit coupling in lecture 17). Since the magnetic moment is $\propto 1/m$ it should be 2000 times larger for an electron compared to a proton. So we can take the hyperfine splitting discussed in section 5.2 of Townsend and multiply by 2000.

We can get the size of the hyperfine splitting from the energy of a 21cm photon (this is the photon involved in the hyperfine transition), $hc/\lambda \approx 6\mu\mathrm{eV}$. Multiplying by 2000 gives an estimate for the energy of the electron-electron interaction of $\boxed{\approx 10^{-3}\ \mathrm{eV}}$.

We could also estimate the energy from first principles by writing down the energy associated with the magnetic dipole of one of the electrons in the magnetic field of the other, $\mu B$. The magnetic field of a dipole is $B\sim \mu_0 \mu / 4\pi r^3$, and we could take a typical distance between the electrons of $r\sim a_0$ (the Bohr radius). The energy is then

$$\mu B\sim {\mu_0 \mu^2\over 4\pi a_0^3} \sim {\mu_0\over 4\pi a_0^3} \left({e\over m_e}{\hbar\over 2}\right)^2 = {e^2\hbar^2\over 16\pi\epsilon_0 c^2a_0^2m_e^2}.$$

Then simplify using $a_0 = \alpha^{-1}(\hbar/m_ec)$ to get

$${1\over 4} \alpha^4 m_e c^2 =  {\alpha^2\over 2} \times \left({1\over 2}\alpha^2 m_e c^2 \right) = \alpha^2 \times {13.6\ \mathrm{eV}\over 2} = 4\times 10^{-4}\ \mathrm{eV},$$

the same order of magnitude as the previous estimate.

```

### Homework 10


```{dropdown} Townsend 13.3: Validity of the Born approximation


```
```{dropdown} Townsend 13.7: Born approximation example


```

```{dropdown} Townsend 13.10: p-wave scattering from a hard sphere

In the region $r>a$ where $V=0$, the general solution for $\ell=1$ is

$$R(r) = A j_1(kr) + B \eta_1(kr),$$

where $\hbar^2k^2/2\mu=E$ (e.g. see section 10.4 of Townsend). We include the Neumann function here because we exclude the origin so there's no problem with it blowing up.
The boundary condition at $r=a$, $R(a)=0$ can be used to determine one of the coefficients:

$$ A j_1(ka) + B \eta_1(ka)= 0 \Rightarrow B = -A {j_1(ka)\over \eta_1(ka)},$$

so therefore 

$$R(r) = A \left[j_1(kr) - {j_1(ka)\over \eta_1(ka)} \eta_1(kr)\right].$$

At large distance $kr\rightarrow\infty$, this becomes

$$R(r) \xrightarrow[kr\rightarrow\infty]{} {A\over kr} \left[\sin(kr-\pi/2) + {j_1(ka)\over \eta_1(ka)} \cos(kr-\pi/2)\right]$$

(using Townsend 13.63). 

We are looking for the asymptotic form

$$R(r) \xrightarrow[kr\rightarrow\infty]{} {A\over kr} \sin(kr - \pi/2 + \delta_1)$$

where $\delta_1$ is the phase shift. For $\delta_1\ll 1$, this is

$$R(r) \xrightarrow[kr\rightarrow\infty]{} {A\over kr} \left[\sin(kr - \pi/2) + \delta_1\cos(kr - \pi/2)\right],$$

where we assume $\cos\delta_1\approx 1$ and $\sin\delta_1\approx \delta_1$. 

Therefore we identify 

$$\delta_1 \approx {j_1(ka)\over \eta_1(ka)} \approx -{(ka)^3\over 3}$$

where in the last step we expand for $ka\ll 1$ using Townsend (10.69) to get the forms of $j_1$ and $\eta_1$:

$$j_1(x) = {\sin x\over x^2} - {\cos x\over x}\approx {x-x^3/6\over x^2} - {1-x^2/2\over x}\approx {x\over 3}$$

$$\eta_1(x) = -{\cos x\over x^2} - {\sin x\over x} \approx -{1-x^2/2\over x^2} - {x-x^3/6\over x}\approx -{1\over x^2}.$$



```


```{dropdown} Townsend 13.11: comparing Born approximation and partial wave expansion


```





