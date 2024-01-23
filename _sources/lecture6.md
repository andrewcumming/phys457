# Lecture 6 Jan 23

Last time we discussed the symmetries of the two-body Hamiltonian:

* **translational symmetry** when we move both particles together. The generator is the total momentum $\hat{\mathbf{P}}$. The total momentum is conserved

$${d\langle{\mathbf{P}}\rangle\over dt} = {i\over \hbar}\langle[\hat{H},\hat{\mathbf{P}}]\rangle = 0.$$

* **rotational symmetry**. The generator is the component of orbital angular momentum about some (arbitrarily) chosen axis, $\hat{\mathbf{L}}_z$. Angular momentum is conserved:
  
$${d\langle L_z\rangle\over dt} = {i\over \hbar}\langle[\hat{H},\hat{L}_z]\rangle = 0$$


Another symmetry is **parity** which takes $\mathbf{r}\rightarrow -\mathbf{r}$, i.e. $\hat{P}\ket{\mathbf{r}} = \ket{-\mathbf{r}}$. The eigenvalues of $\hat{P}$ are either +1 or -1 since $\hat{P}^2\ket{\mathbf{r}} = \ket{\mathbf{r}}$. We will see that, because $[\hat{H},\hat{P}] = 0$, the stationary states of the two-body problem have a definite parity.


## Reminder of angular momentum operators

You've already seen angular momentum operators in the context of spin, so we can directly use some of the results from there:

- **Commutation relations**. Unlike translations, rotations do not commute, so the angular momentum operators in different directions also do not commute:

$$[\hat{L}_i, \hat{L}_j] = i\hbar \epsilon_{ijk} \hat{L}_k$$

(You will prove this specifically for orbital angular momentum in HW2). Each $\hat{L}_i$ does commute with the total angular momentum $[\hat{L}^2,\hat{L}_i]=0$ where

$$\hat{L}^2 = \hat{L}_x^2+\hat{L}_y^2+\hat{L}_z^2.$$

So in quantum mechanics, we can specify the total angular momentum and one component of the angular momentum simultaneously.

- **Eigenstates.** The angular momentum eigenstates are $\ket{\ell,m}$ which satisfy

$$\hat{L}^2\ket{\ell, m} = \ell(\ell+1)\hbar^2 \ket{\ell, m}$$
$$\hat{L}_z\ket{\ell, m} = m\hbar \ket{\ell, m}$$

$m$ ranges from $-\ell$ to $+\ell$ in integer steps.

- **Ladder operators**. $\hat{L}_{+-} = \hat{L}_x\pm i\hat{L}_y$ 

$$\hat{L}_+\ket{\ell,m} = \sqrt{\ell(\ell+1)-m(m+1)}\ket{\ell,m+1}$$

$$\hat{L}_-\ket{\ell,m} = \sqrt{\ell(\ell+1)-m(m-1)}\ket{\ell,m-1}$$

Note that $\hat{L}_+\ket{\ell, \ell} = 0$ and $\hat{L}_-\ket{\ell, -\ell} = 0$ (why?). These are useful for computing for example $\braket{\hat{L}_x}$ when you know the state in the $\hat{L}_z$ basis because you can express $\hat{L}_x$ in terms of the ladder operators that act on the $\hat{L}_z$ basis states. 

## Orbital angular momentum has integer values

One important difference between spin angular momentum and orbital angular momentum is that **$m$ can take only integer values for orbital angular momentum**; half-integer values are not allowed. To see this (this argument is from Townsend 9.8), go back to the rotation operator $\hat{R}(d\phi\,\mathbf{k})$ and write the position eigenstates now in spherical coordinates, so

$$\hat{R}(d\phi\,\mathbf{k})\, \ket{r, \theta, \phi} = \ket{r, \theta, \phi+d\phi}$$

$$\Rightarrow \bra{r, \theta, \phi}\,\hat{R}^\dagger(d\phi\,\mathbf{k})  = \bra{r, \theta, \phi+d\phi}$$

$$\Rightarrow \bra{r, \theta, \phi}\,\hat{R}(d\phi\,\mathbf{k}) = \bra{r, \theta, \phi-d\phi}$$

(since $\hat{R}^\dagger\hat{R}=1$ so $\hat{R}^\dagger$ is the inverse of $\hat{R}$). This allows us to see how the rotation operator acts on the wavefunction:

$$\braket{r, \theta, \phi|\hat{R}(d\phi\,\mathbf{k})|\Psi} = \braket{r, \theta, \phi-d\phi|\Psi}= \braket{r, \theta, \phi|\Psi} - d\phi {\partial\over\partial \phi}\braket{r, \theta, \phi|\Psi}$$

(keeping first order terms only for infinitesimal $d\phi$). We can also write this in terms of the generator

$$\braket{r, \theta, \phi|\hat{R}(d\phi\,\mathbf{k})|\Psi} = \braket{r, \theta, \phi| \left(1 - {i\over\hbar}\hat{L}_z d\phi\right)  |\Psi}.$$

Equating the first order terms, we see that

$$\braket{r, \theta, \phi| \hat{L}_z |\Psi} = {\hbar\over i} {\partial\over\partial \phi} \braket{r, \theta, \phi|\Psi},$$

i.e. we can write the position space representation of $\hat{L}_z$ as (using the notation of Townsend)

$$\hat{L}_z\rightarrow {\hbar\over i}{\partial\over\partial\phi}.$$

This makes sense since we know that the position space representation of linear momentum is $\hat{\mathbf{p}}\rightarrow (\hbar/i)\mathbf{\nabla}$. The $z$-component of angular momentum is $rp_\phi$, so we could therefore write $\hat{L}_z \rightarrow (i/\hbar)(\partial/\partial \phi)$.

Now let this act on an eigenstate

$$\braket{r, \theta, \phi| \hat{L}_z |\ell, m} = {\hbar\over i} {\partial\over\partial \phi} \braket{r, \theta, \phi|\Psi} = m \hbar \braket{r, \theta, \phi|\Psi}$$

$$\Rightarrow {\partial\over\partial \phi} \braket{r, \theta, \phi|\Psi} = i m\braket{r, \theta, \phi|\Psi}\Rightarrow \braket{r, \theta, \phi|\Psi}\propto e^{im\phi}.$$

It makes sense that the wavefunction of the angular momentum eigenstate of $L_z$ is a plane wave in the $\phi$ direction, representing motion around the $z$-axis.

The requirement that $\psi(r,\theta,\phi)$ be single-valued leads to integer $m$, since we need to have 

$$e^{im(\phi + 2\pi)} = e^{im\phi}.$$

Since $m$ ranges from $-\ell$ to $+\ell$, it follows that $\ell$ is also integer. The half-integral values are not allowed because we are dealing with orbital angular momentum which involves real space rotations.


## Eigenstates of orbital angular momentum in position space

To get the full picture of the eigenstates of orbital angular momentum, we also need the variation in the $\theta$ direction. There a couple of ways to get this. One is to write out the components of $\hat{\mathbf{L}} = \hat{\mathbf{r}}\times\hat{\mathbf{p}}$ in spherical coordinates and compute $\hat{L}^2$. This is covered in Townsend 9.8 (see eqs. 9.125-9.129). The other thing we can do is go back to the two-body Hamiltonian and recognize that the non-radial kinetic energy must be $L^2/2\mu r^2$, ie. $(1/2)L^2/I = (1/2)I\Omega^2$ (we'll see this more formally next time). Since $\hat{p}^2\rightarrow -(\hbar^2/2\mu)\nabla^2$, we can make the identification

$$\hat{L}^2\rightarrow -\hbar^2 r^2 \nabla^2_\perp$$


where $\nabla^2_\perp$ is the non-radial part of the Laplacian. This gives


$$\hat{L}^2\rightarrow -\hbar^2 \left[ {1\over\sin\theta}{\partial\over\partial \theta}\left(\sin\theta {\partial\over\partial \theta}  \right)  + {1\over \sin^2\theta} {\partial^2\over \partial \phi^2}\right]$$

(this is equation 9.129 of Townsend). You probably already know that the eigenfunctions of the angular part of the Laplacian are the **spherical harmonics** $Y_{\ell m}(\theta,\phi)$ which satisfy

$$r^2\nabla^2 Y_{\ell m}(\theta,\phi) = -\ell(\ell+1) Y_{\ell m}(\theta,\phi),$$

which is exactly what we need for the angular momentum eigenstates since the total angular momentum is $\ell(\ell+1)\hbar^2$. In addition, the $\phi$-dependence is $Y_{\ell m}\propto e^{im\phi}$ as expected. The angular momentum eigenstates can therefore be written as 

$$\braket{\theta,\phi | \ell,m} = Y_{\ell m}(\theta,\phi).$$


`````{admonition} Plotting the spherical harmonics

Here is some Python code to plot the spherical harmonics that we can take a look at in class.

````{dropdown} Code
```
import numpy as np
import matplotlib.pyplot as plt
from matplotlib import cm
from scipy.special import sph_harm

def sph2cart(r, phi, theta):
   x = r* np.sin(theta)* np.cos(phi)
   y = r* np.sin(theta)* np.sin(phi)
   z = r* np.cos(theta)
   return x, y, z

phi = np.linspace(0, 2*np.pi, 1000)
theta = np.linspace(0, np.pi, 1000)
phi, theta = np.meshgrid(phi, theta)

l, m = 3,0

Y = sph_harm(m, l, phi, theta)

r = np.abs(Y.real)
#r = np.abs(Y)**2     # this is what is plotted in Townsend

frac = (Y.real - np.min(Y.real)+1e-10)/ (np.max(Y.real)-np.min(Y.real)+1e-10)

x, y, z = sph2cart(r, phi, theta)

fig = plt.figure(figsize=(10,8))
ax = fig.add_subplot(111, projection='3d')
ax.set_aspect('equal')
lim = (-0.5,0.5)
ax.set_xlim(lim)
ax.set_ylim(lim)
ax.set_zlim(lim)
ax.plot_surface(x, y, z, facecolors=cm.cool(frac))
```
````


`````


## Rotational transitions of diatomic molecules





## Further reading

- Townsend 9.6-9.9. 
