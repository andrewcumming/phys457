# Lecture 22 Mar 28

## Born approximation continued

**General properties**. We can look at the limits of 

$$f(\theta,\phi) =  - {\mu\over 2\pi\hbar^2} \int d^3\mathbf{r}^\prime \, e^{i\mathbf{q}\cdot\mathbf{r}^\prime} V(\mathbf{r}^\prime)$$

at low and high energy. For low energy $q\rightarrow 0$, the scattering becomes **isotropic**

$$f(\theta,\phi) \xrightarrow[q\rightarrow 0]{}  - {\mu\over 2\pi\hbar^2} \int d^3\mathbf{r}^\prime \, V(\mathbf{r}^\prime)\sim -{\mu V_0 a^3\over \hbar^2}\hspace{1cm}\mathrm{independent\ of\ angle}$$

where $a$ is the range of the potential.

For large $q$, high energy, the phase $\mathbf{q}\cdot\mathbf{r}^\prime$ oscillates rapidly in the exponent, so most of the integrand will cancel. The only coherent contribution is from the region where $\mathbf{q}\cdot\mathbf{r}^\prime\lesssim \pi$ which corresponds to small angles where $k a\theta\lesssim \pi$. This implies **forward scattering** at high energies.

**Spherically-symmetric potential**. With a spherically-symmetric potential $V(r)$, we can do the angular integration by choosing the $z^\prime$ axis to lie along the direction of $\mathbf{q}$. Then

$$\mathbf{q}\cdot\mathbf{r}^\prime = qz^\prime = qr^\prime\cos\theta^\prime.$$

Then writing $\mu^\prime = \cos\theta^\prime\Rightarrow d\Omega^\prime = 2\pi \sin\theta^\prime d\theta^\prime = 2\pi d\mu^\prime$ gives

$$f = -{\mu\over 2\pi\hbar^2}\int dr^\prime r^{\prime 2} V(r^\prime) \int_{-1}^1 2\pi\ d\mu\ e^{iqr^\prime \mu^\prime}$$

or

$$\boxed{f = -{2\mu\over \hbar^2} \int dr^\prime r^{\prime 2} V(r^\prime) {\sin qr^\prime\over q r^\prime}}$$


**Yukawa potential and Rutherford scattering**. As an example, we can try a screened Coulomb potential (Yukawa potential)

$$V(r) = g {e^{-m_0r}\over r}.$$

Then 

$$f = -{2\mu\over\hbar^2} {q\over q} \int_0^\infty d r^\prime e^{-m_0 r^\prime} \sin q r^\prime = -{2\mu g\over \hbar^2(m_0^2 + q^2)}.$$

Writing $q$ in terms of the scattering angle $\theta$ gives the differential cross-section as 

$${d\sigma\over d\Omega} = |f(\theta)|^2 = {4\mu^2 g^2\over \hbar^4\left[m_0^2 + 4k^2 \sin^2 (\theta/2)\right]^2}.$$

With $m_0\rightarrow 0$ (no screening) and taking $g = Z_1Z_2 e^2/4\pi \epsilon_0$, we get the famous [Rutherford scattering](https://en.wikipedia.org/wiki/Rutherford_scattering) formula

$${d\sigma\over d\Omega} = \left({Z_1Z_2e^2\over 4\pi\epsilon_0} \right)^2 {1\over 16 E^2 \sin^4 (\theta/2)}$$

where $E=(\hbar k)^2/2\mu$ is the particle energy. Note that $\hbar$ doesn't appear in this formula: in fact it can be derived classically. 

If you try $\int d\Omega$ to get the total cross-section, you'll find that it diverges in the limit $m_0\rightarrow 0$. This is because the Coulomb force is long range, so small-angle scattering occurs even for large impact parameters. In reality, there is always a some kind of cutoff or screening that sets a limit to how large an impact parameter can contribute to the integral.

**Validity of Born approximation.** The conditions for the validity of the Born approximation are discussed at the end of section 13.2 of Townsend and in problem 13.3 which is on Homework 10. The assumption we made was that the scattered wave is small compared to the incident wave in the volume covered by the scattering potential. For a finite spherical well of depth $V_0$ and radius $a$, and for low energy particles, the condition is 

$${\mu V_0 a^2\over \hbar^2} \ll 1.$$ 

The physical interpretation of this condition is that the potential well must be too shallow to have any bound states (compare with our earlier "back of the envelope" estimates for potential wells). For high energy particles, the condition becomes $V_0/E\ll 1$. 

## Partial wave expansion

We saw already in the Born approximation the idea that low energy leads to isotropic scattering and high energy to forward scattering. So there is a connection between the energy and the angular distribution of the outgoing particles. 

One way to think about this is in terms of the angular momentum components that can interact with the potential. If the potential has a finite range $a$, then the largest impact parameter that can interact with the potential is also $\sim a$, with corresponding angular momentum $\mathbf{r}\times\mathbf{p}\sim a \hbar k$. If we write this maximum angular momentum as $\ell_\mathrm{max}\hbar$ we see that 

$$\boxed{\ell_\mathrm{max}\sim ka}$$

As the energy increases, higher angular momentum states are present in the outgoing wave, which implies more angular structure. For a spherically-symmetric potential in particular it makes sense to expand in angular momentum components because the potential conserves angular momentum and we can consider the scattering of each component separately.

The incoming plane wave can be written as 

$$e^{ikz} = e^{ikr\cos\theta} = \sum_{\ell=0}^\infty i^\ell (2\ell+1) j_\ell(kr) P_\ell (\cos\theta)$$

You can look at problem 13.8 in Townsend if you want to prove / get more of a feeling for this, otherwise, note that the expansion is in terms of Legendre polynomials $P_\ell$ which makes sense because we have axisymmetry around the beam direction (so $m=0$), and spherical Bessel functions $j_\ell$ which we have already seen come up in the solution of the radial equation for spherical symmetry (look back at our discussion of the [infinite spherical well](https://andrewcumming.github.io/phys457/lecture13.html#infinite-spherical-well)).

The expansion of the incoming wave includes only the spherical Bessel functions $j_\ell$ and not the spherical Neumann functions $\eta_\ell$ because we need it to be finite at the origin. At large distance from the origin, where we expect to have an outgoing spherical wave, we have the possibility of both components, so we expand

$$\psi\xrightarrow[r\rightarrow\infty]{} \sum_\ell \left[A_\ell j_\ell(kr)+B_\ell \eta_\ell(kr)\right]P_\ell(\cos\theta).$$

For $r\rightarrow\infty$, we can make use of the asymptotic forms

$$j_\ell(kr)\xrightarrow[r\rightarrow\infty]{}{\sin(kr-\ell\pi/2)\over kr};\hspace{1cm}\eta_\ell(kr)\xrightarrow[r\rightarrow\infty]{}-{\cos(kr-\ell\pi/2)\over kr}$$

Whereas the incoming wave only contains the $\sin$ component ($j_\ell$), the outgoing wave also has a $\cos$ component ($\eta_\ell$) $\Rightarrow$ the outgoing wave has a **phase shift** 

$$e^{ikz} \underset{r\rightarrow\infty}{=} \ \sum_{\ell=0}^\infty i^\ell (2\ell+1) {\sin(kr-\ell\pi/2)\over kr} P_\ell (\cos\theta)$$

$$\psi \underset{r\rightarrow\infty}{=} \ \sum_{\ell=0}^\infty C_\ell {\sin(kr-\ell\pi/2 + \delta_\ell(k))\over kr} P_\ell (\cos\theta)$$

Here $\psi$ is the *total* wavefunction; to identify the scattered component, we can subtract off the incident plane wave

$$\psi_{sc} \underset{r\rightarrow\infty}{=} \ \sum_{\ell=0}^\infty {P_\ell (\cos\theta)\over kr}\left[C_\ell \sin(kr-\ell\pi/2 + \delta_\ell(k))- i^\ell (2\ell+1) \sin(kr-\ell\pi/2)\right].$$

Each term in this expression has an incoming wave component -- i.e. if you write the $\sin$ in terms of exponentials, there are terms $\propto e^{-ikr}$. To match the boundary condition that we have an outgoing wave only at $r\rightarrow\infty$, we need to choose $C_\ell$ so that the incoming wave pieces of each term cancel. This means we need to choose

$$C_\ell = i^\ell (2\ell+1)  e^{i\delta_\ell}.$$

Making this subsitution gives 

$$\psi_{sc} \underset{r\rightarrow\infty}{=} \ \sum_{\ell=0}^\infty {P_\ell (\cos\theta)\over kr}{i^\ell(2\ell+1)\over 2i}\left[
\left(e^{ikr - i\ell\pi/2 + i\delta_\ell}-e^{-ikr+i\ell\pi/2-i\delta_\ell}   \right)e^{i\delta_\ell} - \left(e^{ikr - i\ell\pi/2}-e^{-ikr+i\ell\pi/2}\right)\right]$$

$$=\sum_{\ell=0}^\infty {P_\ell (\cos\theta)\over kr}{(2\ell+1)\over 2i}\left[e^{ikr}\left(e^{2i\delta_\ell}-1\right)\right]$$

$$={e^{ikr}\over r} \sum_{\ell=0}^\infty (2\ell+1) {e^{i\delta_\ell}\sin\delta_\ell\over k} P_\ell(\cos\theta)$$

Once again we have a spherical outgoing wave with 

$$\boxed{f(\theta)= \sum_{\ell=0}^\infty (2\ell+1) {e^{i\delta_\ell}\sin\delta_\ell\over k} P_\ell(\cos\theta)}$$

The total cross-section is $\sigma=\int d\Omega |f|^2$ which gives

$$\boxed{\sigma = {4\pi\over k^2} \sum_{\ell=0}^\infty (2\ell+1) \sin^2\delta_\ell}$$

where we've used the orthogonality relation for the Legendre polynomials,

$$\int^1_{-1} P_\ell(\mu) P_{\ell^\prime}(\mu) d\mu = {2\over 2\ell+1}\delta_{\ell,\ell^\prime}.$$

**General strategy**. This gives us a way to determine cross-sections. The general strategy is:

+ solve the Schrödinger equation for a given $\ell$ to obtain $u(r) = rR(r)$ given $V(r)$

+ match the asymptotic form $u\propto \sin(kr -\ell \pi /2 + \delta_\ell)$ to obtain $\delta_\ell$

+ do this for different $\ell$'s and then sum over the $\ell$ components to obtain the total cross-section

**Example: hard sphere** 

$$V(r) = \begin{cases} \infty & \text{$r<a$} \\
0 & \text{$r>a$}
\end{cases}$$

At low energies, $\ell=0$ dominates. In that case, the Schrödinger equation has a solution that is already of the form we are looking for as $r\rightarrow\infty$: we can write the solution at $r>a$ as $u=C\sin(kr+\delta_0)$. We just have to apply the boundary condition to get the phase shift. Setting $u=0$ at $r=a$ gives 

$$\delta_0 = -ka.$$

Therefore 

$$\sigma_{\ell=0} = {4\pi\over k^2} \sin^2 ka.$$

At low energies, $ka\rightarrow 0$, we have therefore

$$\sigma\rightarrow (4\pi/k^2) (ka)^2=4\pi a^2.$$

We see that this gives us a sensible answer for the cross-section -- it is related to the geometric cross-section for the hard sphere $\pi a^2$, but is actually 4 times larger. We'll discuss this more next time.


## Further reading

- Partial waves are covered in sections 13.4 and 13.5 of Townsend.
