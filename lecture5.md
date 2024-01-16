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

## Further reading

- Chapter 9 of Townsend. 
