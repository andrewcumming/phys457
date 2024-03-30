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

**Validity of Born approximation.** The conditions for the validity of the Born approximation are discussion at the end of section 13.2 of Townsend and in problem 13.3 which is on Homework 10. The assumption we made was that the scattered wave is small compared to the incident wave in the volume covered by the scattering potential. For a finite spherical well of depth $V_0$ and radius $a$, the condition is 

$${\mu V_0 a^2\over \hbar^2} \ll 1.$$ 

The physical interpretation of this condition is that the potential well must be too shallow to have any bound states (compare with our earlier "back of the envelope" estimates for potential wells).

## Partial wave expansion

Coming soon...


## Further reading

- Partial waves are covered in sections 13.4 and 13.5 of Townsend.
