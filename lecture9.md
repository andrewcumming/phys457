# Lecture 9 Feb 1

```{admonition} Discussion: wavefunctions and energy levels of hydrogen

We know how $u(r)$ behaves in the $r\rightarrow 0$ and $r\rightarrow\infty$ limits. We can use this to sketch the possible radial wavefunctions for different values of $\ell$.

Now consider the ground state ($n=1$). What will the wavefunction look like, ie. what will be the $\ell$ value and the shape of the radial wavefunction?

What about the first excited state ($n=2$)? Second excited state ($n=3$)? 

What is the degeneracy? (How many states are there as a function of $n$?)
```

Important points:

- The radial wavefunctions $R(r)$ start off as $\propto r^\ell$ at $r=0$ and then at large $r$ have to decay exponentially. In between they can have $n_r=0,1,2,\dots$ radial nodes.

- The ground state ($n=1$) has no radial nodes and $\ell=0$, this is the 1s state. The wavefunction $R(r)$ is just an exponential function of $r$.

- For the first excited state ($n=2$), we can either add a node in the angular direction $\ell=1$ and keep $n_r=0$, or we can add a node in the radial direction $n_r=1$ and keep $\ell=0$. These are the 2s and 2p states.

- For the next excited state ($n=3$), we now have two nodes to distribute between the radial and angular directions, so we can have $(n_r,\ell)=(2,0), (1,1)$, or $(0,2)$. These are the 3s, 3p, 3d states.

- Counting up all the possible states (including the $2\ell+1$ different $m$ values for each $\ell$) gives a total number of states corresponding to each energy level $n$ of $n^2$. (We're ignoring spin here, once we take spin into account this becomes $2n^2$ since each state can have either a spin up or spin down electron). There is a high degree of **degeneracy** (which comes from the high degree of symmetry of our Hamiltonian).

- The effective potential $V_\mathrm{eff}(r)$ is the sum of the repulsive centrifugal term $\ell(\ell+1)\hbar^2/2\mu$ and the attractive Coulomb term $-e^2/4\pi\epsilon_0 r$. For $\ell>0$ there is a potential barrier preventing the particle from reaching $r=0$, and we see that in the behavior of the wavefunction near the origin, which becomes flatter at $r=0$ as $\ell$ increases ($\propto r^\ell$).

- The **classically-forbidden region** is the region where $E<V(r)$ and the wave cannot propagate (wiggle) and instead evanesces (decays). (The same as in solutions to the 1D Schrödinger equation, e.g. finite square well).
 

## Further reading

- Townsend section 10.2.

