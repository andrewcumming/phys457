# Lecture 7 Jan 25

```{admonition} Warm-up question

Another estimation (back of the envelope) question:  In a finite square well, the energies of the stationary states are $\propto n^2$, but in the harmonic oscillator they are $\propto n$. Why?

```

Last time, we discussed the orbital angular momentum eigenfunctions $\ket{\ell, m}$.

Recall that $\hat{L}^2$ commutes with any of the components $\hat{L}_i$, so the idea is that we are free to choose one of the components, usually taken to be $\hat{L}_z$, and find a simultaneous set of eigenstates of $\hat{L}^2$ and $\hat{L}_z$:

$$\hat{L}^2 \ket{\ell,m} = \ell (\ell+1) \hbar^2 \ket{\ell, m}$$

$$\hat{L}_z \ket{\ell,m} = m \hbar \ket{\ell, m}.$$

These are *not* eigenstates of either $\hat{L}_x$ or $\hat{L_y}$ since the different components of angular momentum do not commute. We can see this directly using the ladder operators. For example, since

$$\hat{L}_x = {1\over 2}\left(\hat{L}_+ + \hat{L}_-\right),$$ 

$$\hat{L}_x \ket{\ell,m} = {\hbar\over 2}\sqrt{\ell(\ell+1)-m(m+1)} \ket{\ell, m+1} + {\hbar\over 2}\sqrt{\ell(\ell+1)-m(m-1)} \ket{\ell, m-1}.$$

We also saw last time how to write these operators in position representation. First, 

$$\hat{L}_z\rightarrow {\hbar\over i}{\partial \over \partial \phi}$$

which shows that the eigenstates of $\hat{L_z}$ are given by 

$$\braket{\mathbf{r}|m} \propto e^{im\phi}.$$

And we also have 

$$\hat{L}^2\rightarrow -\hbar^2 r^2 \nabla^2_\perp = -\hbar^2 \left[ {1\over\sin\theta}{\partial\over\partial \theta}\left(\sin\theta {\partial\over\partial \theta}  \right)  + {1\over \sin^2\theta} {\partial^2\over \partial \phi^2}\right],$$

where the notation $\nabla^2_\perp$ refers to the non-radial part of the Laplacian operator. The set of functions that obey 

$$r^2\nabla^2 \braket{\mathbf{r}|\ell, m} = -\ell(\ell+1) \braket{\mathbf{r}|\ell, m},$$

are the **spherical harmonics**

$$\braket{\mathbf{r}|\ell, m}=Y_{\ell m}(\theta, \phi).$$

Note that $Y_{\ell m}\propto e^{im\phi}$, so these are also eigenstates of $\hat{L}_z$ as expected. Let's take a closer look at these functions.


## Properties of the spherical harmonics

- We can use the code from the end of lecture 6 to plot these functions. 

- [Table of spherical harmonics](https://en.wikipedia.org/wiki/Table_of_spherical_harmonics)

- Normalization

$$\int_0^\pi \sin\theta\,d\theta \int_0^{2\pi} d\phi \,|Y_{\ell m}(\theta,\phi)|^2 = 1.$$

- They can be written in terms of associated Legendre polynomials $P^m_\ell(\mu)$

$$Y_{\ell m} \propto e^{im\phi}P^m_\ell(\cos\theta).$$


## Spectroscopy of diatomic molecules

One application is to rotational transitions of diatomic molecules. If we assume the interatomic spacing $a$ is fixed, the Hamiltonian is just $\hat{H} = \hat{L}^2/2\mu a^2$ with energy levels $E_\ell = \ell(\ell+1) \hbar^2/2\mu a^2$. 

See Townsend 9.7.


## The radial part of the two-body problem

We have the angular part of the eigenfunctions of the two body problem now, but we are still missing the radial part. To get this we can use the formula that you derived in HW2:

$$\hat{\mathbf{L}}^2 = \hat{\mathbf{r}}\times \hat{\mathbf{p}}\cdot \hat{\mathbf{r}}\times \hat{\mathbf{p}} = \hat{\mathbf{r}}^2\hat{\mathbf{p}}^2 -(\hat{\mathbf{r}}\cdot\hat{\mathbf{p}})^2 + i\hbar \hat{\mathbf{r}}\cdot\hat{\mathbf{p}},$$

by looking at the quantity $\braket{\mathbf{r}|\hat{L}^2|\Psi}$ (this is the argument in Townsend 9.6). The idea is to rewrite the $\hat{\mathbf{p}}^2$ in the Hamiltonian in terms of $\hat{\mathbf{L}}^2$ and see what else is left over. We need the three terms:

$$\braket{\mathbf{r}|\hat{\mathbf{r}}^2\hat{\mathbf{p}}^2|\Psi} = r^2 \braket{\mathbf{r}|\hat{\mathbf{p}}^2|\Psi}$$

$$\braket{\mathbf{r}|\hat{\mathbf{r}}\cdot\hat{\mathbf{p}}|\Psi} = \mathbf{r}\cdot {\hbar\over i}\mathbf{\nabla} \braket{\mathbf{r}|\Psi} = {\hbar\over i}r {\partial\over\partial r}\braket{\mathbf{r}|\Psi}$$

$$\braket{\mathbf{r}|(\hat{\mathbf{r}}\cdot\hat{\mathbf{p}})^2|\Psi} = - \hbar^2 r {\partial\over\partial r} \left(r {\partial\over\partial r}\braket{\mathbf{r}|\Psi}\right)$$

which gives

$$\braket{\mathbf{r}|\hat{\mathbf{p}}^2|\Psi} = - \hbar^2\left({\partial^2\over \partial r^2}  +{2\over r} {\partial\over \partial r}     \right)\braket{\mathbf{r}|\Psi} +  {1\over r^2}\braket{\mathbf{r}|\hat{L}^2|\Psi}.$$

This is the separation of the kinetic energy term into a radial part and an angular part that we talked about last time. The Laplacian in spherical coordinates is given by 

$$\nabla^2 = {1\over r^2}{\partial \over \partial r}\left(r^2{\partial \over \partial r}\right) + 
{1\over r^2\sin\theta}{\partial\over\partial \theta}\left(\sin\theta {\partial\over\partial \theta}  \right)  + {1\over r^2\sin^2\theta} {\partial^2\over \partial \phi^2}$$

which has the same radial component! So we see that we just have 

$$\braket{\mathbf{r}|\hat{\mathbf{p}}^2|\Psi} = - \hbar^2\nabla^2\braket{\mathbf{r}|\Psi}$$

which is exactly what we would have expected from the fact that the momentum operator in position representation is $-i\hbar \mathbf{\nabla}$! This also justifies what we were saying last time that $\hat{L}^2$ should correspond to the non-radial part of the Laplacian.

Now we can look at the full Hamiltonian with kinetic energy and potential energy terms:

$$\braket{\mathbf{r}|\hat{\mathbf{H}}|\Psi} = - {\hbar^2\over 2\mu}\left({\partial^2\over \partial r^2}  +{2\over r} {\partial\over \partial r}     \right)\braket{\mathbf{r}|\Psi} +  {1\over 2\mu r^2}\braket{\mathbf{r}|\hat{L}^2|\Psi} + V(r)\braket{\mathbf{r}|\Psi}.$$

If we look for stationary states that are simultaneous eigenstates of $\hat{H}$, $\hat{L}^2$ and $\hat{L}_z$, we need to solve

$$\left[- {\hbar^2\over 2\mu}\left({\partial^2\over \partial r^2}  +{2\over r} {\partial\over \partial r}     \right)+  {\ell(\ell+1)\hbar^2\over 2\mu r^2} + V(r)\right]\braket{\mathbf{r}|E, \ell, m} = E \braket{\mathbf{r}|E, \ell, m}.$$

The only derivatives are radial, so we can write the separable solution

$$\braket{\mathbf{r}|E, \ell, m} = R(r) Y_{\ell m}(\theta,\phi)$$

where the radial function $R(r)$ obeys

$$\left[- {\hbar^2\over 2\mu}\left({d^2\over d r^2}  +{2\over r} {d\over d r}     \right)+  {\ell(\ell+1)\hbar^2\over 2\mu r^2} + V(r)\right]R(r) = E R(r).$$

With $u(r) = rR(r)$, this becomes

$$\left[- {\hbar^2\over 2\mu}{d^2\over d r^2} +  {\ell(\ell+1)\hbar^2\over 2\mu r^2} + V(r)\right]u(r) = E u(r)$$

which is the usual 1D Schrödinger equation with an effective potential 

$$V_{\rm eff} = V(r) +  {\ell(\ell+1)\hbar^2\over 2\mu r^2}$$

(i.e. we add a centrifugal term to the potential).

The symmetries of the Hamiltonian have reduced the 3D problem to a 1D problem that we know how to solve! 
We'll look at solutions for different $V(r)$, including the hydrogen atom, next week!


## Further reading

- Keep looking at Townsend Chapter 9

