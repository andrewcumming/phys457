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

Start with Townsend (13.48) which is the condition that the Born approximation is valid:

$$\left|{\psi_\mathrm{sc}(0)\over \psi_\mathrm{inc}(0)}\right| = \left|{2\mu\over \hbar^2k}\int_0^\infty dr\, e^{ikr} V(r) \sin kr\right|\ll 1$$

(ie. the wavefunction near the origin is dominated by the incident plane wave, so our approximation for solving the integral equation {eq}`sc_integ_eqn` is a good one).

Now assume the potential has some range $a$, so we only have to consider values of $r$ in the in the integral up to $r\approx a$. At low energy where $ka\ll 1$, we can approximate $e^{ikr}\approx 1$ and $\sin kr\approx kr$, giving

$$\left|{2\mu\over \hbar^2k}\int_0^\infty dr\, e^{ikr} V(r) \sin kr\right|\approx 
\left|{2\mu\over \hbar^2k}\int_0^\infty dr\, V(r) kr\right|$$

Then treating $V(r)\approx V_0\approx $ constant for $r<a$, we can do the integral to get 

$$\left|{2\mu\over \hbar^2k}\int_0^\infty dr\, e^{ikr} V(r) \sin kr\right|\approx 
\left|{2\mu\over \hbar^2k}\int_0^\infty dr\, V(r) kr\right| \approx {\mu V_0a^2\over \hbar^2}.$$

So we have a condition for the Born approximation to be valid at low energies $ka\ll 1$ 

$${\mu V_0a^2\over \hbar^2} \ll 1.$$

The condition for the Born approximation to be valid at high energies $ka\gg 1$ is (Townsend 13.49),

$${\mu V_0\over \hbar^2k^2} \ll 1\Rightarrow {\mu V_0a^2\over \hbar^2} {1\over (ka)^2} \ll 1$$

so we see that if the low energy condition is already satisfied then at high energies we're dividing by the large number $(ka)^2$ and so the high energy condition will automatically be satisfied as well.

Note the physical interpretations of these criteria: the high energy condition is that the particle energy should be much larger than the magnitude of the scattering potential $V_0$; the low energy condition is that the potential should be small enough that there are no bound states. 



```
```{dropdown} Townsend 13.7: Born approximation example

Start with the scattering amplitude for a spherically-symmetric potential, 

$$f = -{2\mu\over\hbar^2q} \int_0^\infty dr\, r V(r) \sin(qr).$$

With $V(r) = V_0 e^{-r/a}$, this becomes

$$f = -{2\mu V_0\over\hbar^2q} \int_0^\infty dr\, r e^{-r/a} \sin(qr) = -{2\mu V_0\over\hbar^2q} {2a^3 q\over (1+(qa)^2)^2}.$$

Therefore

$${d\sigma\over d\Omega} = |f|^2 = \left({4\mu a^2 V_0\over \hbar^2}\right)^2 {a^2\over (1+ (qa)^2)^4}$$

or in terms of the scattering angle 

$${d\sigma\over d\Omega} =  \left({4\mu a^2 V_0\over \hbar^2}\right)^2 {a^2\over (1+ 4(ka)^2\sin^2(\theta/2))^4}.$$

Notice that this has the correct units which we can see from the $a^2$ factor. The first term on the right hand side is dimensionless.


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

The potential we are considering is the finite well $V=-V_0$ for $r<a$ and $V=0$ for $r>a$. The s-wave cross-section is given by equation (13.93) of Townsend:

$$\sigma_{\ell=0} = {4\pi a^2} \left({\tan k_0a\over k_0a} -1\right)^2,$$

where $(k_0a)^2 = (2\mu a^2/\hbar^2)(V_0+E)$ (Townsend 13.88a). We're going to be doing a comparison at low energy, so let's take $E\ll V_0$, and let's also take $k_0a\ll 1$ which is the condition from Townsend problem 13.3 for the validity of the Born approximation:

$$\sigma_{\ell=0}\approx 4\pi a^2 \left( {(k_0a)^2\over 3} \right)^2 = 4\pi a^2 \left( {2\mu a^2V_0\over 3\hbar^2} \right)^2.$$

Now we can compute the Born approximation cross-section and compare the answers. Use equation {eq}`spherical_Born` for the scattering amplitude given a spherically-symmetric potential. This gives

$$\sigma_\mathrm{Born} = \int d\Omega |f|^2 = \int d\Omega \left({2\mu V_0\over \hbar^2q}\right)^2\left|\int_0^a dr\, r \sin(qr)\right|^2$$

$$ = \int d\Omega \left({2\mu V_0\over \hbar^2q}\right)^2\left({1\over q^2}\left[\sin qa - qa \cos qa\right]   \right)^2$$

$$ = a^2 \left({2\mu V_0a^2\over \hbar^2}\right)^2  \int d\Omega\left({1\over (qa)^3}\left[\sin qa - qa \cos qa\right]   \right)^2.$$

To compute the angular integral exactly, we would need to express $q$ in terms of the scattering angle $\theta$. But we are interested here in low energy, so let's first expand the integrand for $qa\ll 1$:

$${\sin qa - qa \cos qa\over (qa)^3}\approx {qa - (qa)^3/6 - (qa)(1-(qa)^2/2) \over (qa)^3 } \approx {1\over 3},
$$

which has no $q$-dependence. As we would expect at low energy the cross-section is isotropic ($\ell=0$ dominates).

This gives

$$\sigma_\mathrm{Born} \approx 4\pi a^2 \left({2\mu V_0a^2\over 3\hbar^2}\right)^2.$$

Both approaches indeed give the same expression for the cross-section in this limit $k_0a\ll 1$ where the Born approximation should be valid.

```


### Chapter 14 practise problems

```{dropdown} Townsend 14.10: exciting a charged particle in a 1D harmonic oscillator

In this question, an oscillating electric field is applied to a charged particle in a 1D harmonic oscillator. 
The perturbation to the Hamiltonian is 

$$\hat{H}_1 = eE(t)\hat{x} = \hat{x}\, e E_0 \cos\omega t.$$

We start off in the ground state and we need to use time-dependent perturbation theory to calculate the probability that the particle is found in state $\ket{n}$ after a time $t$.  Apply equation {eq}`dckdt`

$${dc_n\over dt} \approx -{i\over \hbar} e^{-i n\omega_0 t}\braket{n|\hat{H}_1|0}$$

$$\Rightarrow c_n = -{ieE_0\over \hbar} \braket{n|\hat{x}|0} \int_0^t dt\, e^{-i n\omega_0 t} \cos \omega t$$

and therefore

$$|c_n|^2 = \left({eE_0\over \hbar}\right)^2 \left|\braket{n|\hat{x}|0}\right|^2 \left|\int_0^t dt\, e^{-i n\omega_0 t} \cos \omega t\right|^2.$$

By now you will have seen this kind of matrix element before: use the ladder operators to evaluate it $\hat{x} = (\hbar/2 m\omega_0)^{1/2}(\hat{a}+\hat{a}^\dagger)$ which implies that the only possible $\ket{n}$ is the first excited state $\ket{1}$:

$$\left|\braket{n|\hat{x}|0}\right|^2 = {\hbar\over 2m\omega_0} \left|\braket{1|\hat{a}^\dagger|0}\right|^2 = {\hbar\over 2m\omega_0}.$$

Using Mathematica to evaluate the time integral (setting $n=1$ since we know now that $n=1$ is the only option), I get

$$\int_0^t dt\, e^{-i \omega_0 t} \cos \omega t = {e^{-i\omega_0t}\over \omega^2-\omega_0^2}\left(\omega \sin \omega t -i\omega_0(\cos\omega t - e^{i\omega_0 t})\right)$$

$$= {e^{-i\omega_0t}\over \omega^2-\omega_0^2}\left(\omega \sin \omega t -\omega_0\sin\omega_0t-i\omega_0(\cos\omega t - \cos\omega_0t)\right)$$

Therefore

$$|c_n|^2 = {e^2E_0^2\over 2m\hbar\omega_0}{(\omega \sin \omega t -\omega_0\sin\omega_0t)^2 + \omega_0^2(\cos\omega t - \cos\omega_0t)^2 \over (\omega^2-\omega_0^2)^2}.$$

(If you check you'll see this does have the correct dimensions).

We can evaluate it for the case $\Delta\omega = \omega-\omega_0\rightarrow 0$, just have to be careful with the limit. The numerator is

$$2\omega_0^2 t^2 (\Delta\omega)^2 (1+\cos\omega_0 t)$$

and the denominator is

$$(\omega^2-\omega_0^2)^2 = (\Delta\omega)^2(\omega+\omega_0)^2 \approx \omega_0^2(\Delta\omega)^2.$$

Therefore

$$|c_n|^2 = {e^2E_0^2\over m\hbar\omega_0} {t^2(1+\cos\omega_0 t)}.$$

```


```{dropdown} Townsend 14.11: a time-dependent electric field applied to the hydrogen atom

Aligning our $z$-axis with the applied electric field, the perturbation to the Hamiltonian is 

$$\hat{H}_1 = -eE(t)\hat{z} = -\hat{z}\, e E_0 e^{-t/\tau}.$$

We start off in the ground state and we need to use time-dependent perturbation theory to calculate the probability that the particle will be found in a 2p state as $t\rightarrow\infty$.  Apply equation {eq}`dckdt`:

$${dc_1\over dt} = -{i\over\hbar} e^{-i(E_0-E_1)t/\hbar}\braket{2p|\hat{H}_1|0} = {ieE_0\over\hbar} e^{i\omega_{21}t} e^{-t/\tau}\braket{2p|\hat{z}|1s}$$

where $\omega_{21} = |E_0-E_1|/\hbar$ is the photon frequency involved in the transition. The matrix element is

$$\braket{2,1,0|\hat{z}|1,0,0} =  {1\over \sqrt{3}} \sqrt{3\over 2}{2^8\over 3^5}a_0 = {1\over \sqrt{2}}{2^8\over 3^5}a_0$$

(using the integrals given in lecture 25) (we need $m=0$ on the left-hand side to get a non-vanishing matrix element). 

Therefore

$$|c_1|^2 = {e^2E_0^2\over \hbar^2} {2^{15}\over 3^{10}} a_0^2 \left|\int_0^\infty dt\,e^{i\omega_{21}t}e^{-t/\tau}\right|^2$$

$$={e^2E_0^2\over \hbar^2} {2^{15}\over 3^{10}} a_0^2 {\tau^2\over 1 + (\omega_{21} \tau)^2}.$$

```




```{dropdown} Townsend 14.14: radiative transition in the harmonic oscillator

We're going from the initial state $\ket{i} = \ket{n=1}\ket{0}$ (first excited state of the oscillator, no photon) to final state $\ket{i} = \ket{n=0}\ket{1}$ (ground state of the oscillator, one photon). The calculation is similar to the decay of the hydrogen atom from 2p to 1s (lecture 25), but with different spatial integrals. The perturbing Hamiltonian is 

$$\hat{H}_1 = {e\over \mu} \hat{\mathbf{p}}\cdot\hat{\mathbf{A}}$$

The density of states we need for the outgoing photon is

$$g(E_f) = {V\omega^2d\Omega\over 8\pi^3 c^3\hbar}$$

Then applying Fermi's Golden rule gives

$$d\Gamma = {2\pi\over\hbar} {V\omega^2d\Omega\over 8\pi^3 c^3\hbar} {e^2\over\mu^2}{\hbar\over 2\epsilon_0\omega V} \left|\braket{n=0|\epsilon\cdot\hat{\mathbf{p}}|n=1}\right|^2$$

where similarly to lecture 25 we've assumed $e^{ikr}\approx 1}$ (photon wavelength $\gg$ size of the oscillator). 

Simplifying the prefactor gives

$${d\Gamma\over d\Omega} = {\alpha\omega\over 2\pi\mu^2c^2} \left|\braket{n=0|\epsilon\cdot\hat{\mathbf{p}}|n=1}\right|^2.$$

Notice that this has the correct units ($\mathrm{s}^{-1}$).

We actually have three different choices for the $\ket{n=1}$ state. In Cartesian coordinates, this corresponds to one of the three choices $\ket{n_x,n_y,n_z}=\ket{1,0,0}$, $\ket{0,1,0}$, or $\ket{0,0,1}$. Or in spherical coordinates we have the three states $\ket{\ell, m} = \ket{1,1}$, $\ket{1,0}$ or $\ket{1,-1}$. As with the hydrogen atom, the different states couple to different directions for the polarization vector $\epsilon$. 

The simplest way to evaluate the matrix element is to use Cartesian coordinates, i.e. write 

$$\epsilon\cdot\hat{\mathbf{p}} = \epsilon_x\hat{p}_x +  \epsilon_y\hat{p}_y +  \epsilon_z\hat{p}_z.$$ 

Then we can write the momentum operator in terms of the ladder operators. For example, if we pick the starting state in Cartesian coordinates $\ket{1,0,0}$ (so $n_x=1$), then the only operator that couples this to the ground state $\ket{0,0,0}$ will involve the ladder operator in the $x$-direction, or the $\hat{p}_x$ term:

$$\braket{0,0,0|\epsilon\cdot\hat{\mathbf{p}}|1,0,0} = \braket{0,0,0|\epsilon_x\hat{p}_x|1,0,0} = -i\sqrt{\mu\omega\hbar\over 2}\epsilon_x \braket{0,0,0|(\hat{a}_x - \hat{a}^\dagger_x)|1,0,0} = -i\sqrt{\mu\omega\hbar\over 2}\epsilon_x$$

(using Townsend eq 7.13). The rate of decay for this state is then

$${d\Gamma\over d\Omega} = {\alpha\omega\over 2\pi\mu^2c^2} {\mu\omega\hbar\over 2} \epsilon_x^2.$$

We would get a similar answer for the other two states $n_y=1$ or $n_z=1$ but with the $\epsilon_x$ replaced by the other components of the polarization vector, $\epsilon_y$ or $\epsilon_z$ respectively. If we add up these three rates and divide by 3 we can get the average decay rate assuming there is no preferred initial state:

$${d\Gamma\over d\Omega} = {1\over 3}{\alpha\omega\over 2\pi\mu^2c^2} {\mu\omega\hbar\over 2} (\epsilon_x^2+\epsilon_y^2+\epsilon_z^2) = {1\over 3}{\alpha\omega^2\hbar\over 4\pi\mu c^2}.$$

We used the fact that the polarization vector is a unit vector (has unit length).
This doesn't depend on the outgoing photon direction, so we can do the integral $\int d\Omega\rightarrow 4\pi$ to get the total decay rate

$$\Gamma = {\alpha\omega^2\hbar\over 3\mu c^2}.$$

The other way to do this would be to use spherical coordinates instead and look at the $\ket{\ell,m}$ states. Then you need to convert the $\hat{p}$ in the matrix element to $\hat{r}$ (lecture 25), expand $x$, $y$ and $z$ in terms of $Y_{\ell,m}$'s and do the angular and radial integrals. This is done in section 14.7 of Townsend (equations 14.157 to 14.166). In spherical coordinates, the decay of the $m=1$, $m=0$ or $m=-1$ states involves the polarization components $\epsilon_x+i\epsilon_y$, $\epsilon_z$ and $\epsilon_x-i\epsilon_y$ respectively, i.e. if you start in a state with $m\neq 0$, then the non-zero angular momentum in the initial state is carried away by a circularly-polarized photon. In the Cartesian treatment, we just have motion in one Cartesian direction so the states connect to linear-polarization in that direction.


```


```{dropdown} Townsend 14.16: density of states for an electron

Start with the phase space density in momentum space and transform into energy:

$${Vd^3\mathbf{p}\over h^3} = {Vp^2dpd\Omega\over h^3} = {Vp^2d\Omega\over h^3}{dp\over dE} dE$$

and with $E = p^2/2m$, $dE = p dp/m$ we get the answer

$${V\over (2\pi)^3\hbar^3}m_e p\, d\Omega\, dE.$$

Including spin would give an extra factor of 2 for the two spin states.

```


```{dropdown} Townsend 14.17: Photoelectric effect

In the photoelectric effect, we go from the electron being in the ground state of hydrogen with an incoming photon, write this initial state as $\ket{i} = \ket{1s}\ket{1}$, to the electron in an outgoing plane wave state and no photon, final state $\ket{f}=\ket{\mathbf{k}}\ket{0}$.  The perturbing Hamiltonian that couples the electron and photon states is (lecture 25)

$$\hat{H}_1 = {e\over m_e} \hat{p}\cdot\hat{A}$$

(assume the proton is infinitely heavy and use $\mu=m_e$). 

The matrix element to plug into Fermi's Golden Rule is therefore

$$\braket{f|\hat{H}_1|i} = \left({\hbar\over 2\epsilon_0\omega}\right)^{1/2} {e \over m_e}\int d^3\mathbf{r}\, {e^{i\mathbf{p}_e\cdot\mathbf{r}/\hbar}\over\sqrt{V}}\epsilon\cdot\hat{\mathbf{p}}{e^{i\mathbf{k}\cdot\mathbf{r}}\over \sqrt{V}}\psi_{1s},$$ 

where $\epsilon$ is the photon polarization direction. The  momentum operator is easiest if we operate to the left and convert it to the electron momentum in the final state $\mathbf{p}_e$:

$$\braket{f|\hat{H}_1|i} = \left({\hbar\over 2\epsilon_0\omega}\right)^{1/2} {e \over m_e} (\mathbf{p}_e\cdot\epsilon) {1\over V} \int d^3\mathbf{r}\, e^{-i\mathbf{k}_f\cdot\mathbf{r}} e^{i\mathbf{k}\cdot\mathbf{r}}\psi_{1s},$$ 

where $k_f=p_e/\hbar$. 

Finally, putting in $\psi_{1s}$ gives

$$\braket{f|\hat{H}_1|i} = \left({\hbar\over 2\epsilon_0\omega}\right)^{1/2} {e \over m_e} (\mathbf{p}_e\cdot\epsilon) {1\over V} {1\over \sqrt{\pi}a_0^{3/2}} \int d^3\mathbf{r}\, e^{i\mathbf{q}\cdot\mathbf{r}}e^{-r/a_0}.$$ 

where $\mathbf{q}=\mathbf{k}-\mathbf{k}_f$ is the momentum transfer.

We can use the same trick as in the Born approximation (lecture 22, see derivation of equation {eq}`spherical_Born`) to write the integral

$$\int d^3\mathbf{r}\, e^{i\mathbf{q}\cdot\mathbf{r}}e^{-r/a_0} = {4\pi\over q} \int_0^\infty dr\, r e^{-r/a_0} \sin qr  = {8\pi\over a_0} {1\over ((1/a_0)^2+q^2)^2}.$$

Now using Fermi's Golden Rule we can assemble an expression for the rate 

$$d\Gamma = {2\pi\over\hbar} {V\over (2\pi)^3\hbar^3}m_e p\, d\Omega {e^2 \hbar\over 2\epsilon_0 \omega m_e^2}(\mathbf{p}_e\cdot\epsilon)^2 {1\over V^2\pi a_0^3}{64\pi^2\over a_0^2}{1\over ((1/a_0)^2+q^2)^4}.$$

Now use the hint in the question to divide by $c/V$ for the incident photon flux, to convert to a differential cross-section. Then simplifying factors and using $\alpha = e^2/4\pi\epsilon_0\hbar c$, I find

$${d\sigma\over d\Omega} = {V\over c}{d\Gamma\over d\Omega} = 32\alpha {\hbar\over m_e\omega} {k_f(\epsilon\cdot\mathbf{k}_f)^2\over a_0^5} {1\over ((1/a_0)^2+q^2)^4}$$

which agrees with the answer given in the question. 