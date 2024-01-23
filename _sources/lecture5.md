# Lecture 5 Jan 18

Let's develop the machinery we will need to solve the two-body problem. Then we will get into symmetries and how we can put them to work to learn about the eigenfunctions. 

## Moving from 1D to 3D

The position and momentum eigenstates that we have in 1D generalize naturally to 3D:

**Position basis**

- Eigenstates: $\ket{\mathbf{r}} = \ket{x, y, z}$
- Wavefunction: $\psi(\mathbf{r}) = \braket{\mathbf{r}|\Psi}$
- Normalization: $\int |\psi|^2\,dV = 1$
- Orthogonality: $\braket{\mathbf{r}|\mathbf{r}^\prime} = \delta^3(\mathbf{r}-\mathbf{r}^\prime)$

**Momentum basis**

- Eigenstates: $\ket{\mathbf{p}} = \ket{p_x, p_y, p_z}$  

- Momentum eigenstates in position basis are plane waves in 3D space :$\braket{\mathbf{r}|\mathbf{p}} = {1\over (2\pi\hbar)^{3/2}} e^{i\mathbf{p}\cdot\mathbf{r}/\hbar}$

- Commutation relations: $[\hat{p}_i, \hat{p}_j] = 0$, $[\hat{x}_i, \hat{p}_j] = i\hbar \delta_{ij}$
- The momentum operator in position basis is now a 3D gradient:

$$\braket{\mathbf{r}|\hat{\mathbf{p}}|\Psi} = {\hbar\over i}\mathbf{\nabla} \braket{\mathbf{r}|\Psi}$$

Note that the position and momentum commutator vanishes when the position and momentum are in different directions. So for example whereas it is not possible to know both $x$ and $p_x$ for a particle at the same time, we can know the precise $x$-coordinate and $y$-momentum $p_y$ at the same time.  


## The two-body problem

We want to look at two particles with masses $m_1$ and $m_2$ interacting through a potential that depends only on the distance between the two particles:

$$\hat{H} = {\hat{\mathbf{p}}_1^2\over 2m_1} + {\hat{\mathbf{p}}_2^2\over 2m_2} + V(|\hat{\mathbf{r}}_1-\hat{\mathbf{r}}_2|).$$

A particular example is the hydrogen atom in which the proton and electron interact through a Coulomb potential

$$\hat{H} = {\hat{\mathbf{p}}_1^2\over 2m_1} + {\hat{\mathbf{p}}_2^2\over 2m_2} - {e^2\over 4\pi \epsilon_0 |\hat{\mathbf{r}}_1-\hat{\mathbf{r}}_2|}.$$

In general, we can build the state of the system out of two particle states

$$\ket{\mathbf{r}_1,\mathbf{r}_2} = \ket{\mathbf{r}_1}\otimes\ket{\mathbf{r}_2},$$

with a direct product of the Hilbert spaces for particles 1 and 2. (We're ignoring the proton and electron spins here, more on that later in the course!)

In fact, as you've probably seen before in classical mechanics, the two-body problem simplifies enormously with a change of coordinates. We work with the relative coordinate between the two particles

$$\mathbf{r} = \mathbf{r}_1 - \mathbf{r}_2,$$

and the centre of mass location

$$\mathbf{R} = {m_1 \mathbf{r}_1 + m_2\mathbf{r}_2\over m_1+m_2 }.$$

Also defining the total mass $M$ and **reduced mass** $\mu$ by 

$$M = m_1+m_2 \ \ ; \hspace{1cm} \mu = {m_1 m_2\over m_1+m_2}$$

and the total momentum $\mathbf{P}=\mathbf{p}_1+\mathbf{p}_2$ and relative momentum 

$$\mathbf{p} = {m_2 \mathbf{p}_1 - m_1\mathbf{p}_2\over m_1+m_2 },$$

the Hamiltonian takes the simple form

$$\hat{H} = {\hat{\mathbf{P}}^2\over 2M} + {\hat{\mathbf{p}}^2\over 2\mu} + V(|\hat{\mathbf{r}}|).$$

(see Townsend problem 9.5 in HW 2).

We see that the problem separates into two pieces: the motion of the centre of mass and the relative motion. We'll work in the centre of mass frame where $\mathbf{P}=0$, which allows us to consider the relative motion only. Then we can solve the one body problem with a particle of mass $\mu$ moving in the central potential $V(r)$, where $r$ is the distance from the origin (centre of mass).


## Symmetries of the Hamiltonian

We can learn a lot about what the stationary states look like by considering symmetries of the Hamiltonian. Previously (see section 6.3 of Townsend) you've seen the idea that the momentum operator is the generator of translations

$$\hat{T}(dx) = 1-{i\over\hbar}\hat{p}_x dx\ ; \hspace{1cm}\hat{T}(dx)\ket{x} = \ket{x+dx}.$$

For a finite translation $a$,

$$\hat{T}(a) = \lim_{N\rightarrow\infty} \left[1 - {i\over \hbar}\hat{p}_x {a\over N} \right]^N = e^{-i\hat{p}_xa/\hbar}\ ; \hspace{1cm} \hat{T}(a)\ket{x} = \ket{x+a}.$$

In 3D, we can generalize this to a vector translation

$$\hat{T}(\mathbf{a}) = e^{-i\hat{\mathbf{p}}\cdot\mathbf{a}/\hbar}\ ; \hspace{1cm} \hat{T}(\mathbf{a})\ket{\mathbf{r}} = \ket{\mathbf{r}+\mathbf{a}}.$$

There is an important connection between symmetries of the Hamiltonian and conserved quantities. If the Hamiltonian is invariant under translations, we must have

$$\hat{T}(-a)\hat{H}\hat{T}(a) = \hat{T}^\dagger(a)\hat{H}\hat{T}(a) = \hat{H}$$

$$\Rightarrow \hat{T}\hat{T}^\dagger\hat{H}\hat{T} = \hat{T}\hat{H}\Rightarrow \hat{H}\hat{T} = \hat{T}\hat{H}\Rightarrow [\hat{H},\hat{T}] = 0,$$

the Hamiltonian commutes with the translation operator. Since the momentum operator is the generator of translations, 

$$[\hat{H},\hat{T}] = 0 \Rightarrow [\hat{H},\hat{p}] = 0$$

and therefore

$${d\langle \mathbf{p}\rangle\over dt} = {i\over\hbar} \braket{\Psi|[\hat{H},\hat{\mathbf{p}}]|\Psi}= 0.$$

We see that **translational invariance of the Hamiltonian is linked directly to momentum conservation**. 

In the two body problem we are considering, we don't have individual momentum conservation because translation of only one of the particle positions without moving the other one changes the relative distance and therefore the potential $V(r)$. However, the Hamiltonian is invariant under translation of *both* particle positions

$$[\hat{H}, \hat{T}_1(\mathbf{a})\hat{T}_2(\mathbf{a})] = 0$$

where

$$\hat{T}_1(\mathbf{a})\hat{T}_2(\mathbf{a}) = e^{-i\hat{\mathbf{p}}_1\cdot\mathbf{a}/\hbar}e^{-i\hat{\mathbf{p}}_2\cdot\mathbf{a}/\hbar} = 
e^{-i\hat{\mathbf{P}}\cdot\mathbf{a}/\hbar}$$

and so

$$[\hat{H}, \hat{\mathbf{P}}] = 0$$

**the total momentum $\mathbf{P}$ is conserved in the two body problem**.

The most important symmetry of this problem is rotational. In the centre of mass frame, we have 

$$\hat{H} = {\hat{\mathbf{p}}^2\over 2\mu} + V(|\hat{\mathbf{r}}|).$$

Since $\hat{H}$ depends only on $|\mathbf{p}|^2=p_x^2+p_y^2+p_z^2$ and $|\mathbf{r}|=(x^2+y^2+z^2)^{1/2}$, we can see that it will be invariant under rotations, so let's choose an axis $z$ to rotate around (unit vector in $z$-direction is $\mathbf{k}$) and define a rotation operator

$$\hat{R}(d\phi\,\mathbf{k})\ket{x,y,z} = \ket{x-y\,d\phi, y+x\,d\phi, z},$$

where we consider an infinitesimal rotation $d\phi$.

To figure out what the generator looks like in this case, we can use the translation operator to make the changes in $x$ and $y$ (following directly the argument in Townsend 9.5):

$$\ket{x-y\,d\phi, y+x\,d\phi, z} = \left[1 - {i\over \hbar}\hat{p}_x(-y\,d\phi)\right]\left[1 - {i\over \hbar}\hat{p}_y(x\,d\phi)\right]\ket{x,y,z}$$

$$= \left[1 - {i\over \hbar}\left(\hat{x}\hat{p}_y-\hat{y}\hat{p}_x\right)d\phi\right]\ket{x,y,z} = \left[1 - {i\over \hbar}\hat{L}_zd\phi\right]\ket{x,y,z}.$$

We see that the **generator of rotations** is $\hat{L}_z$, the $z$-component of the **orbital angular momentum** operator 

$$\hat{\mathbf{L}} = \hat{\mathbf{r}}\times \hat{\mathbf{p}}.$$

The fact that the Hamiltonian is rotationally-invariant therefore implies 

$$[\hat{H},\hat{R}(\phi)] = 0\Rightarrow [\hat{H},\hat{L}_z] = 0$$

which tells us that **orbital angular momentum is conserved** in the two body problem. We choose the $z$-axis arbitrarily (since the system is rotaionally invariant), so this applies no matter what direction we consider.

We'll discuss more about the details of the angular momentum operators next time, but we'll just mention here a crucial difference between linear and angular momentum. In the case of linear momentum, it is possible to know all components of momentum simultaneously:

$$[p_i,p_j] = 0.$$

But whereas the translation operators in different directions commute (order doesn't matter), rotation operators do not (order of rotations does matter). The commutator is

$$[\hat{L}_i, \hat{L}_j] = i\hbar \epsilon_{ijk} \hat{L}_k$$

(you will prove this in HW2).






## Further reading

- Townsend 9.1-9.3, 9.5.
