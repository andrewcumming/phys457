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


Coming soon...


## Further reading

- I'm following the book quite closely in this part. Townsend 13.1 covers the basic idea of scattering and differential cross-section; 13.2 and 13.3 covers the Born approximation. 

- Townsend 6.10 gives some examples of scattering in 1D which might be helpful to look at and compare to what we're doing in 3D. 
