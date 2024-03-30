# Lecture 21 Mar 26

## Overview of scattering

Scattering experiments involve sending a beam of particles towards a target and measuring the angular distribution of scattered particle and the rate at which particles are scattered (the cross-section). This allows us to learn about the potential $V(\mathbf{r})$ of the target.

The approach we're going to take is to treat the scattering by finding the stationary solutions to the Schrödinger equation for a given particle energy, represented by the wavevector $k = (2\mu E)^{1/2}/\hbar$. We're using $\mu$ here because we have a two body problem involving the particle and the target, e.g. we could be looking at an electron beam scattering from the Coulomb field of the nucleus of an atom (the famous Rutherford experiment; more on this later).

The incoming beam of particles is represented by a plane wave $A e^{ikz}$.  When the plane wave interacts with the potential, it will generate an outgoing scattered wave. You could think of a plane-parallel surface wave on water that encounters an obstacle, creating a series of circular ripples that spread outwards. If we go to large enough distance from the potential, the scattered wave will be an outgoing radial wave $\propto e^{ikr}/r$. You can see that this is an outgoing wave solution by going back to the radial Schrödinger equation, 

$$\left[-{\hbar^2\over 2\mu}{d^2\over d\mu^2} + {\ell(\ell+1)\hbar^2\over 2\mu r^2}+V\right]u = Eu$$

where recall that $R(r) = u(r)/r$. Setting $V=0$ for a free particle and $\ell=0$ (no angular momentum, radial orbit), gives an outgoing wave solution of the form $R(r)\propto e^{ikr}/r$. 

In particular, we'll look for a solution at large distance composed of the incoming plane wave and the outgoing scattered wave:

$$\psi(\mathbf{r})\xrightarrow[r\rightarrow \infty]{} A e^{ikz} + A\,f(\theta,\phi){e^{ikr}\over r}.$$

Here, we define the **scattering amplitude** $f(\theta,\phi)$, which measures the amplitude of the scattered wave relative to the incoming wave amplitude $A$. 

You may have seen this idea of decomposing the wavefunction into incoming and outgoing components in 1D scattering problems. There are some examples in Townsend section 6.10. An example is a beam of particles travelling from left to right incident on a potential step. To the left of the step, we write the wavefunction as $\psi \propto e^{ikx} + re^{-ikx}$, where the first term represents the incoming particles and the second term the particles that are reflected by the step. Similarly here we split the wavefunction at large distance from the potential into incoming and outgoing components.

## Probability current and differential cross-section

Conservation of probability can be written as 

$${\partial |\psi|^2\over \partial t} = -\mathbf{\nabla}\cdot \mathbf{j}$$

where the probability current is

$$\mathbf{j}  = {\hbar\over 2\mu i}\left(\psi^\star \mathbf{\nabla}\psi - \psi \mathbf{\nabla}\psi^\star\right)$$

(To show this, you can use the time-dependent Schrödinger equation to calculate $\partial |\psi|^2/\partial t = \psi^\star \partial \psi/\partial t + \psi \partial \psi^\star/\partial t$). 

The outgoing wave 

$$\psi = A f(\theta,\phi) {e^{ikr}\over r}$$ 

has a probability current 

$$\mathbf{j}_{sc} = \hat{\mathbf{r}} {\hbar k\over \mu} {1\over r^2} |A|^2 |f(\theta,\phi)|^2$$

(where we've ignored any angular gradients, since they becomes small as $r\rightarrow \infty$). Notice the terms $1/r^2$ and $\hbar k/\mu$, the particle velocity. The $1/r^2$ is there because the total outgoing probability integrated over the surface area of a spherical shell should be independent of radius to conserve probability, i.e. we need $\mathbf{\nabla}\cdot \mathbf{j} = 0$ in steady state, or $(\partial/\partial r)(r^2 j_r)=0\Rightarrow r^2j_r$ constant. The velocity is also expected because of the general form

$$\mathrm{flux} = \mathrm{velocity}\times \mathrm{density}.$$

We can use the probability flux to define a **differential cross-section** $d\sigma/d\Omega$, defined by

$$\mathrm{probability\ per\ unit\ time\ into\ solid\ angle}\ d\Omega =  \mathrm{incident\ flux}\times {d\sigma\over d\Omega} d\Omega$$

$$\mathbf{j}_{sc}\cdot\hat{\mathbf{r}}\ r^2 d\Omega =|\mathbf{j}_\mathrm{inc}|\ {d\sigma\over d\Omega} d\Omega.$$

The incident plane wave has $|\mathbf{j}_\mathrm{inc}| = (\hbar k/\mu)|A|^2$, so we see that

$$\boxed{{d\sigma\over d\Omega}=|f(\theta,\phi)|^2}$$

The total cross-section is $\sigma = \int d\Omega\ (d\sigma/d\Omega)$. 

To summarise, the strategy is going to be:

- develop a (probably approximate) solution to the Schrödinger equation for a given particle energy $k$
- identify the part of the solution corresponding to the outgoing wave at $r\rightarrow\infty$
- read off the scattering amplitude $f(\theta,\phi)$ 
- use the scattering amplitude to obtain the cross-section.

We'll do this in a couple of different ways, first the Born approximation which applies when the scattering potential makes a small perturbation to the incoming wave. 


## Born approximation

**Green's function solution**. The Schrödinger equation

$$\left(\nabla^2 + k^2\right)\psi(\mathbf{r}) = {2\mu\over \hbar^2} V(\mathbf{r})\psi(\mathbf{r})$$

has an integral solution

$$\psi(\mathbf{r}) = Ae^{ikz} + \int d^3\mathbf{r}^\prime \,G(\mathbf{r},\mathbf{r}^\prime) {2\mu\over \hbar^2} V(\mathbf{r}^\prime)\psi(\mathbf{r}^\prime),$$

where 

$$G(\mathbf{r},\mathbf{r}^\prime) = -{e^{ik|\mathbf{r}-\mathbf{r}^\prime|}\over 4\pi|\mathbf{r}-\mathbf{r}^\prime|}$$

is the Green's function which satisfies 

$$\left(\nabla^2 + k^2\right)G(\mathbf{r},\mathbf{r}^\prime) =
\delta^3(\mathbf{r},\mathbf{r}^\prime).$$ (Greens)

To show that this is indeed the Green's function, (1) first note that $\nabla^2(e^{ikr}/r) = -k^2e^{ikr}/r$, so the left hand side (LHS) of equation {eq}`Greens` vanishes except at the origin, and then (2) if you integrate the LHS over a spherical volume centred on the origin you get a value of 1 independent of the radius of the sphere. So the LHS has the properties required of the delta function on the RHS. 

If you haven't seen this kind of solution for  the wave equation before, it might also help to go back to electrostatics: when you calculate the electrostatic potential $V(\mathbf{r})$ associated with a continuous charge density $\rho(\mathbf{r})$, there is a very similar integral but with $k=0$ (since the electrostatic potential obeys Poisson's equation $\nabla^2 V = \rho/\epsilon_0$, which doesn't have the $k^2$ term):

$$V(\mathbf{r}) =  \int d^3\mathbf{r}^\prime {1\over 4\pi \epsilon_0|\mathbf{r}-\mathbf{r}^\prime|} \rho(\mathbf{r}^\prime).$$

The major difference there is that the source term on the right hand side of Poisson's equation is a known function $\rho(\mathbf{r})$, whereas here the source term $\propto V(\mathbf{r})\psi(\mathbf{r})$ depends on the solution itself. So we have an integral equation for $\psi(\mathbf{r})$.

**Solution at large distance**. Therefore we need to solve 

$$\psi(\mathbf{r}) = Ae^{ikz} - {\mu\over 2\pi\hbar^2} \int d^3\mathbf{r}^\prime \, {e^{ik|\mathbf{r}-\mathbf{r}^\prime|}\over |\mathbf{r}-\mathbf{r}^\prime|} V(\mathbf{r}^\prime)\psi(\mathbf{r}^\prime).$$

In particular, we are interested in the solution at large distance $|\mathbf{r}|\rightarrow \infty$. Assuming that the potential has a finite range, then the values of the integration variable satisfy $|\mathbf{r}^\prime|\ll |\mathbf{r}|$ and we can expand 

$${1\over |\mathbf{r}-\mathbf{r}^\prime|} \approx {1\over r}\left(1 + {\hat{\mathbf{r}}\cdot\mathbf{r}^\prime\over r} + \dots\right)$$

and 

$$k |\mathbf{r}-\mathbf{r}^\prime| \approx kr - k \hat{\mathbf{r}}\cdot\mathbf{r}^\prime + \dots $$

$$\Rightarrow e^{ik|\mathbf{r}-\mathbf{r}^\prime|}\approx e^{ikr}e^{-ik\hat{\mathbf{r}}\cdot\mathbf{r}^\prime}$$

(to derive these, you just need to consider the triangle made up of the vectors $\mathbf{r}$, $\mathbf{r}^\prime$ and $\mathbf{r}-\mathbf{r}^\prime$). In the limit $r\rightarrow\infty$, we can take $|\mathbf{r}-\mathbf{r}^\prime|\approx r$ in the denominator, but need to keep the extra term depending on $\mathbf{r}^\prime$ in the exponent to keep track of the phases of the different contributions in the integral:

$$\psi(\mathbf{r}) \xrightarrow[r\rightarrow\infty]{} Ae^{ikz} - {\mu\over 2\pi\hbar^2}{e^{ikr}\over r} \int d^3\mathbf{r}^\prime \, e^{-ik\hat{\mathbf{r}}\cdot\mathbf{r}^\prime} V(\mathbf{r}^\prime)\psi(\mathbf{r}^\prime).$$ (integraleq)

(You'll see a very similar derviation come up if you study electromagnetic radiation from accelerated charges, it's the same situation where we take different powers in the expansion of $|\mathbf{r}-\mathbf{r}^\prime|$ in the denominator and in the phase factor). 

**Born approximation**. You can imagine that one way to solve this kind of equation is to guess an initial form for $\psi(\mathbf{r})$, use that to compute the integral on the right hand side, and then take the resulting $\psi(\mathbf{r})$ from equation {eq}`integraleq` as an updated solution. This process can be repeated and hopefully the solution will converge on the correct answer. The Born approximation is to do one step of this iterative process with an initial guess $\psi(\mathbf{r}^\prime) = Ae^{ikr^\prime}$, i.e. we assume that the potential is "small" in the sense that it has only a small effect on the wavefunction (we'll write down later exactly what this means for the potential). In this case, it's a good approximation to just use the incoming wave as the source term in the integral:

$$\psi(\mathbf{r}) \xrightarrow[r\rightarrow\infty]{} Ae^{ikz} - A{\mu\over 2\pi\hbar^2}{e^{ikr}\over r} \int d^3\mathbf{r}^\prime \, e^{-ik\hat{\mathbf{r}}\cdot\mathbf{r}^\prime} V(\mathbf{r}^\prime)e^{ikz^\prime}.$$

We see that there is an outgoing spherical wave on the right hand side! The scattering amplitude is

$$f(\theta,\phi) =  - {\mu\over 2\pi\hbar^2} \int d^3\mathbf{r}^\prime \, e^{-ik\hat{\mathbf{r}}\cdot\mathbf{r}^\prime} V(\mathbf{r}^\prime)e^{ikz^\prime}.$$ 

**Momentum transfer**. To get this into a simpler form, we use the fact that we are looking at a stationary state, so we are consider an elastic scattering where the particle has incoming momentum $\mathbf{k}_i$ and outgoing momentum $\mathbf{k}_f$ which have the same magnitude but different directions. We're assuming $\mathbf{k}_i$ is in the $z$-direction, so we can write $e^{ikz^\prime}=e^{i\mathbf{k}_i\cdot\mathbf{r}^\prime}$ in the integral. Similarly $\mathbf{k}_f$ is in the radial direction, so $e^{-ik\hat{\mathbf{r}}\cdot\mathbf{r}^\prime}=e^{-i\mathbf{k}_f\cdot\mathbf{r}^\prime}$. In terms of the **momentum transfer**, defined as

$$\mathbf{q} = \mathbf{k}_i - \mathbf{k}_f,$$

we obtain 

$$\boxed{f(\theta,\phi) =  - {\mu\over 2\pi\hbar^2} \int d^3\mathbf{r}^\prime \, e^{i\mathbf{q}\cdot\mathbf{r}^\prime} V(\mathbf{r}^\prime)}$$ 

We see that the scattering amplitude is related to a Fourier transform of the potential. This shows explicitly the idea that by measuring the angular distribution of the outgoing particles, we can learn about the spatial distribution of the scattering potential. 

To see the relation between $\mathbf{q}$ and the angles $\theta$ and $\phi$:

$$\mathbf{q} = \mathbf{k}_i - \mathbf{k}_f$$

$$\Rightarrow q^2 = k_i^2 - 2( \mathbf{k}_i \cdot  \mathbf{k}_f ) + k_f^2 = 2k^2(1-\cos\theta) = 4k^2 \sin^2 {\theta\over 2},$$ 

where $\theta$ is the scattering angle relative to the incoming direction. We'll be dealing with spherically-symmetric potentials, so the scattering amplitude won't having any $\phi$ dependence - ie. the scattering is axisymmetric around the incoming particle direction. 

That was a long derivation today! but now we are in a position next time to use it to look at some examples. 

## Further reading

- I'm following the book quite closely in this part. Townsend 13.1 covers the basic idea of scattering and differential cross-section; 13.2 and 13.3 covers the Born approximation. 

- Townsend 6.10 gives some examples of scattering in 1D which might be helpful to look at and compare to what we're doing in 3D. 
