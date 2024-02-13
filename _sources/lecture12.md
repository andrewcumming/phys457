# Lecture 12 Feb 13

The first thing today is to finish off the discussion of the 3D harmonic oscillator from last time. Then we'll move onto two final examples of central potentials: finite and infinite spherical wells which can be used as starting models for the energy levels of neutrons and protons in nuclei.


**Effect of raising operator**

Here is the proof that we discussed in class showing how the raising operator works:

$$[\hat{a}^\dagger_\ell, \hat{N}_\ell] = \hat{a}^\dagger_\ell\hat{a}_\ell^\dagger\hat{a}_\ell - \hat{a}_\ell^\dagger\hat{a}_\ell\hat{a}^\dagger_\ell = -\hat{a}_\ell^\dagger[\hat{a}_\ell,\hat{a}_\ell^\dagger] = -\hat{a}_\ell^\dagger (2 + \hat{N}_{\ell+1} - \hat{N}_\ell)$$ 

$$\Rightarrow \hat{N}_\ell \hat{a}_\ell^\dagger = 2\hat{a}_\ell^\dagger + \hat{a}_\ell^\dagger\hat{N}_{\ell+1}.$$

Now apply this to the state $\ket{k, \ell+1}$:

$$ \hat{N}_\ell\hat{a}_\ell^\dagger\ket{k, \ell+1} = 2\hat{a}_\ell^\dagger\ket{k, \ell+1} + \hat{a}_\ell^\dagger\hat{N}_{\ell+1}\ket{k, \ell+1} = 2\hat{a}_\ell^\dagger\ket{k, \ell+1} + \hat{a}_\ell^\dagger k\ket{k, \ell+1}$$

$$\Rightarrow \hat{N}_{\ell} \left(\hat{a}_\ell^\dagger\ket{k, \ell+1}\right) = (k+2)\left(\hat{a}_\ell^\dagger\ket{k, \ell+1}\right)$$

which tells us that 

$$\boxed{\hat{a}^\dagger_\ell\ket{k, \ell+1} \propto \ket{k+2, \ell}}$$

From last time we also had

$$\boxed{\hat{a}_\ell\ket{k, \ell} \propto \ket{k-2, \ell+1}}$$

Apply these one at a time you can show that $\hat{a}_\ell^\dagger \hat{a}_\ell \ket{k,\ell}\propto \ket{k,\ell}$ as it should since $\ket{k,\ell}$ is an eigenstate of the number operator.

## Finite spherical well

The potentials we've looked at so far, $1/r$ and $r^2$ have the property that the energies of the stationary states are independent of $\ell$. It makes sense that the energy would be independent of $m$ because of the rotational symmetry - the direction of the angular momentum shouldn't affect the energy of the state. But these potentials also have the property that the energy is independent of the magnitude of the angular momentum. 
In general, this is not the case, as we will now see for the problem of a spherical well. 

The spherical well is the potential 

$$V(r) = \begin{cases}
-V_0 & \text{$r\leq a$}\\
0 & \text{$r>a$}
\end{cases}$$

which is the spherically-symmetric 3D equivalent to the square well in 1D. Here $a$ is the size of the well and $V_0$ the depth.

One application of this potential is as a first model of the atomic nucleus. Consider first the deuteron which is a bound state of a neutron and proton (ie. the deuteron is the nucleus of deuterium, heavy hydrogen). The binding energy of deuterium is $\approx -2.2\ \mathrm{MeV}$, so it is quite weakly bound. This nucleus plays an important role in nucleosynthesis in stars, being the product of the hydrogen burning $p+p\rightarrow d + e^+ + \nu_e$ reaction. 

Unlike in 1D, where the finite square well always has a bound state (see HW 2 Q1), the spherical well does not. We can see this by considering the boundary condition at $r=0$. The radial wavefunction $u(r) = rR(r)$ satisfies

$$\left[{-\hbar^2\over 2\mu}{d^2\over d r^2} + {\ell(\ell+1)\hbar^2\over 2\mu r^2} + V(r)\right]u = Eu,$$

with a boundary condition $u\propto r^{\ell+1}$ as $r\rightarrow 0$ so that $u=0$ at $r=0$. Inside the well, $u$ has to therefore increase from $u=0$ at the origin to some maximum value before decaying in the classically-forbidden region $r>a$. This gives a curvature $\sim 1/a$ to the wavefunction, and therefore a minimum energy $\sim \hbar^2/2ma^2$. If this exceeds the depth of the well $V_0$, then a bound state is not possible. The combination $a^2V_0$ for the deuteron is just large enough to allow a bound state -- the depth of the well is $V_0\approx 35 \ \mathrm{MeV}$, much larger than the binding energy, so the bound state lies just below the continuum.

We can solve for the ground state by first setting $\ell=0$ since we expect the ground state will have zero angular momentum. Then we can write down the solution in each region $r<a$ and $r>a$ and use a matching condition to match the two solutions at the boundary:

**Outer solution**. For $r>a$ we have

$$-{\hbar^2\over 2\mu}{d^2u\over d r^2} = Eu$$

which can be written 

$${d^2u\over d r^2} = q^2 u$$

$$\Rightarrow \boxed{u = C e^{-qr}}$$

where 

$$q = \sqrt{2\mu(-E)\over \hbar^2}$$

and we've taken only the exponentially decreasing solution because we need $u$ to remain finite as $r\rightarrow\infty$. As expected, the solution decays in the classically-forbidden region.

**Inner solution**. For $r<a$ we have

$$-{\hbar^2\over 2\mu}{d^2u\over d r^2} = (V_0+E)u$$

which we can write

$${d^2u\over d r^2} = -k_0^2 u$$

$$\Rightarrow \boxed{u = A \sin k_0 r}$$

where 

$$k_0 = \sqrt{2\mu(V_0+E)\over \hbar^2}.$$

We include the $\sin$ part of the solution but not the $\cos$ because we need $u$ to vanish at $r=0$. The solution oscillates in the classically-allowed region. 

We can match the two solutions at $r=a$ by enforcing continuity of $u$ and its derivative. We'll do this next time.



## Further reading

- Townsend section 10.2.

