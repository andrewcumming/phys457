# Lecture 11 Feb 8

## 3D Harmonic Oscillator

The 3D harmonic oscillator refers to a particle moving in a potential $V(r) = (1/2) m\omega^2 r^2$, i.e. it experiences a force always directed towards the origin and proportional to the distance to the origin.

**Solution in Cartesian coordinates**. The simplest way to solve this is to recognize that we can split the Hamiltonian into three separate 1D harmonic oscillators if we work in Cartesian coordinates:

$$\hat{H} = {\hat{p_x}^2+\hat{p_y}^2+\hat{p_z}^2\over 2m} + {1\over 2}m\omega^2 (\hat{x}^2+\hat{y}^2+\hat{z}^2)$$

$$= {\hat{p_x}^2\over 2m} + {1\over 2}m\omega^2\hat{x}^2 + {\hat{p_y}^2\over 2m} + {1\over 2}m\omega^2\hat{y}^2 + {\hat{p_z}^2\over 2m} + {1\over 2}m\omega^2\hat{z}^2.$$

We can write the stationary states as $\ket{n_x, n_y, n_z}=\ket{n_x}\ket{n_y}\ket{n_z}$, i.e. a separable solution $\psi(x,y,z)=X(x)Y(y)Z(z)$ which will have an energy

$$E = \hbar\omega\left(n_x + n_y + n_z+{3\over 2}\right) = \hbar\omega\left(n+{3\over 2}\right)$$

for $n_x,n_y,n_z,n=0,1,2,\dots$. The ground state has energy $(3/2)\hbar\omega$ with $n_x=n_y=n_z=0$. The first excited state involves increasing one of the $n_i$'s to 1, with three possible ways to do it. The second excited state has either two $n_i$'s equal to 1 or one of the $n_i$'s equal to 2, with 6 possible states, etc.

**Spherical coordinates**. Now consider solving this problem in spherical coordinates. From the rotational symmetry of the Hamiltonian, we can write the stationary states as $\ket{E,\ell}\ket{\ell,m}$, ie. the angular part is given by the angular momentum eigenstates. The radial part then satisfies 

$$\hat{H}_\ell \ket{E,\ell} = \left[{\hat{p}_r^2\over 2m} + {\ell(\ell+1)\hbar^2\over 2m \hat{r}^2} + {1\over 2}m\omega^2\hat{r}^2\right]\ket{E,\ell} = E\ket{E,\ell}$$

for energy $E$. Here, we write the radial part of the kinetic energy with a radial momentum operator $\hat{p}_r$. In position representation, this is

$$\hat{p}_r\rightarrow {\hbar\over i} \left({\partial\over \partial r}+{1\over r}\right)$$

which gives the correct form for the radial part of the Laplacian since

$$\hat{p}_r^2\ket{\Psi}\rightarrow -\hbar^2 \left({\partial\over \partial r}+{1\over r}\right)\left({\partial\over \partial r}+{1\over r}\right)\psi= -\hbar^2 \left({\partial^2\over\partial r^2} +  {2\over r}{\partial\over\partial r}\right)\psi = -\hbar^2 \nabla_r^2\psi$$

where $\nabla^2_r$ is the radial part of the Laplacian. This operator is introduced in Townsend section 9.6. Two useful commutation relations that you can prove are 

$$[\hat{r},\hat{p}_r]=i\hbar;\hspace{1cm}\left[{1\over\hat{r}},\hat{p}_r\right]=-{i\hbar\over \hat{r}^2}.$$

We'll use these later. 


**Solution to the radial equation**. One approach is to solve the radial equation

$$\left[-{\hbar^2\over 2m}\nabla_r^2 + {\ell(\ell+1)\hbar^2\over 2m r^2} + {1\over 2}m\omega^2 r^2\right]R(r) = E R(r)$$

just as we did for the hydrogen atom. You will work through this in HW5. Just as with the hydrogen atom, there is a quantization condition that is needed to truncate the polynomial solution,

$$\boxed{n = 2n_r + \ell}$$

where $n$ is the principal quantum number and $n_r$ is the number of radial nodes. The energy is

$$\boxed{E = \hbar\omega \left(n+{3\over 2}\right) = \hbar\omega \left(2n_r +\ell +{3\over 2}\right)}$$

There's an interesting difference from hydrogen, which is that the radial nodes contribute twice as much energy compared to increasing $\ell$. So the ground state has $n_r=0, \ell=0$, same as hydrogen, but there is only one option for the first excited state: $n_r=0, \ell=1$. For the second excited state, there is $n_r=1, \ell=0$ or $n_r=0, \ell=2$. You can check that the number of states at each $n$ matches what we found in Cartesian coordinates.


## An operator approach to the 3D harmonic oscillator

**Operator approach in 1D.** First a reminder about what happens in 1D: we try to complete the square in the Hamiltonian 

$$\hat{H} = {\hat{p}^2\over 2m} + {1\over 2}m\omega^2\hat{x}^2$$

by defining operators

$$\hat{a} = {1\over\sqrt{2m\hbar\omega}} \left(i\hat{p} + m\omega\hat{x}\right); \hspace{1cm} \hat{a}^\dagger = {1\over\sqrt{2m\hbar\omega}} \left(-i\hat{p} + m\omega\hat{x}\right).$$

It is straightforward to show that 

$$\hat{H} = \hbar\omega\left(\hat{a}^\dagger\hat{a} + {1\over 2}\right),$$

and also that $[\hat{a}, \hat{a}^\dagger]=1$ (you will need to use $[\hat{x},\hat{p}]=i\hbar$).

Then we can investigate the effect of $\hat{a}^\dagger$ and $\hat{a}$ on the eigenstates of $\hat{H}$, or equivalently the number operator $\hat{N}=\hat{a}^\dagger\hat{a}$. First, the commutator between $\hat{a}$ and $\hat{N}$ is

$$[\hat{a},\hat{N}] = \hat{a}\hat{a}^\dagger\hat{a} - \hat{a}^\dagger\hat{a}\hat{a} = [\hat{a},\hat{a}^\dagger]\hat{a} = \hat{a}.$$

Write the eigenstates of $\hat{N}$ as $\ket{n}$ with corresponding eigenvalues $n$. Then

$$\hat{a}n\ket{n} = \hat{a}\hat{N}\ket{n} = \hat{N}\hat{a}\ket{n} + \hat{a}\ket{n}\Rightarrow \hat{N}\left(\hat{a}\ket{n}\right)=(n-1)\left(\hat{a}\ket{n}\right)$$

so we see that $\hat{a}\ket{n}$ must be $\propto \ket{n-1}$, i.e. $\hat{a}$ is a lowering operator. A similar argument shows that $\hat{a}^\dagger$ is a raising operator, since $[\hat{a}^\dagger,\hat{N}]=-\hat{a}^\dagger$. The lowest value of $n$ is zero since the fact that the ground state is annihilated by the lower operator $\hat{a}\ket{0}=0$ is then consistent with $\hat{N}\ket{0} = 0$. We see then that the states have integer values of $n=0,1,2,\dots$, generated by successively applying $\hat{a}^\dagger$ to the ground state to generate the excited states. The normalizations of the raising and lowering operators are such that $\hat{a}\ket{n}=\sqrt{n}\ket{n-1}$ and $\hat{a}^\dagger\ket{n} = \sqrt{n+1}\ket{n+1}$. 


**Operator approach in 3D**. Let's see if we can use a similar approach in 3D. Let's find operators that can complete the square in the radial Hamiltonian

$$\hat{H}_\ell = \left[{\hat{p}_r^2\over 2m} + {\ell(\ell+1)\hbar^2\over 2m \hat{r}^2} + {1\over 2}m\omega^2\hat{r}^2\right].$$

Let's try

$$\hat{a}_\ell = {1\over \sqrt{2m\hbar\omega}} \left(i\hat{p_r} - {(\ell+1)\hbar\over \hat{r}} + m\omega\hat{r}\right).$$

Then

$$\hbar\omega \hat{a}_\ell^\dagger\hat{a}_\ell = \hat{H}_\ell + {i\omega\over 2}[\hat{r},\hat{p}_r] - i{(\ell+1)\hbar\over 2m}\left[{1\over \hat{r}}, \hat{p}_r\right] + {(\ell+1)\hbar^2\over 2mr^2}-(\ell+1)\hbar\omega$$

or

$$\hat{H}_\ell  = \hbar\omega\left(\hat{a}^\dagger_\ell \hat{a}_\ell + \ell + {3\over 2} \right).$$

A natural next step is to interpret $\hat{a}_\ell^\dagger\hat{a}_\ell=\hat{N}_\ell$ as a number operator that counts the radial excitations. If we label the eigenstates as $\ket{k,\ell}$, where $\hat{N}_\ell\ket{k,\ell} = k\ket{k,\ell}$, then we can investigate the effect of $\hat{a}_\ell$ on $\ket{k,\ell}$. Just as in 1D, we will need the commutator $[\hat{a}_\ell^\dagger, \hat{a}_\ell]$. Using the definition above gives

$$[\hat{a}_\ell, \hat{a}_\ell^\dagger] = 1 + {\hbar(\ell+1)\over m\omega r^2} = 1 + {\hat{H}_{\ell+1}-\hat{H}_\ell\over\hbar\omega} = 2 + \hat{N}_{\ell+1} - \hat{N}_\ell,$$ 

so that

$$[\hat{a}_\ell, \hat{N}_\ell] = \hat{a}_\ell\hat{a}_\ell^\dagger\hat{a}_\ell - \hat{a}_\ell^\dagger\hat{a}_\ell\hat{a}_\ell = [\hat{a}_\ell,\hat{a}_\ell^\dagger]\hat{a}_\ell = (2 + \hat{N}_{\ell+1} - \hat{N}_\ell)\hat{a}_\ell$$ 

$$\Rightarrow \hat{a}_\ell \hat{N}_\ell = 2\hat{a}_\ell + \hat{N}_{\ell+1}\hat{a}_\ell.$$

Now apply this to the state $\ket{k, \ell}$:

$$\hat{a}_\ell \hat{N}_\ell\ket{k, \ell} = \hat{a}_\ell k\ket{k, \ell} = 2\hat{a}_\ell\ket{k, \ell} + \hat{N}_{\ell+1}\hat{a}_\ell\ket{k, \ell}$$

$$\Rightarrow \hat{N}_{\ell+1} \left(\hat{a}_\ell\ket{k, \ell}\right) = (k-2)\left(\hat{a}_\ell\ket{k, \ell}\right)$$

which tells us that 

$$\hat{a}_\ell\ket{k, \ell} \propto \ket{k-2, \ell+1}$$

an eigenstate of $\hat{N}_{\ell+1}$ with eigenvalue $k-2$. So we see that $\hat{a}_\ell$ lowers the radial quantum number by 2 while simultaneously increasing $\ell$ by 1. You can show in a similar way that   $\hat{a}_\ell^\dagger$ increases the radial quantum number by 2 while decreasing $\ell$ by 1. Starting at the ground state with $k=0$ we can apply $\hat{a}^\dagger$ to add a radial excitation (while also decreasing $\ell$ by 1), which will increase $k$ by 2. We can therefore see that the energies will be $E = \hbar\omega \left(2n_r +\ell +{3/2}\right)$ with $n_r=0,1,2,\dots$ and $\ell=0,1,2,\dots$, in agreement with the solution above from the radial equation.





## Further reading

- Townsend section 10.2.

