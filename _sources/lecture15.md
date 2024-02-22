# Lecture 15 Feb 22

## Selection rules and the polarizability of the hydrogen ground state

Last time we ended up with the result 

$$E_1^{(2)} = \left(eE\right)^2 \sum_{n\neq 1, \ell, m} {|\braket{n,\ell,m|\hat{z}|1,0,0}|^2\over E_1^{(0)}-E_n^{(0)}}$$

for the energy correction to the hydrogen ground state when an electric field is applied to the atom (quadratic Stark effect). 

Although it looks like we will have to sum over all possible excited states to calculate $E_1^{(2)}$, it turns out that most of the terms vanish for symmetry reasons. First, since 

$$[\hat{L}_z,\hat{z}] = 0$$

(this must be true because $\hat{L}_z$ does not involve $\hat{p}_z$), then operating $\hat{z}$ on the state $\ket{n,\ell,m}$ will not alter the value of $m$. To see this, consider

$$\hat{L}_z\hat{z}\ket{n,\ell,m} = \hat{z} \hat{L}_z \ket{n,\ell,m} = m\hbar \hat{z}\ket{n,\ell,m},$$

which shows that $\hat{z}\ket{n,\ell,m}$ is an eigenstate of $\hat{L}_z$ with eigenvalue $m$. This means that the only surviving matrix elements in the sum are those with the same value of $m$ on both sides, i.e. $m=0$.

Similarly, only certain values of $\ell$ give non-vanishing matrix elements. First, since the parity of $Y_{\ell m}$ is $(-1)^\ell$ and $\hat{z}$ has odd parity, we need the two states in the matrix element to have a difference in $\ell$ which is an odd number. In fact, the properties of the $Y_{\ell m}$'s are such that there is only one non-zero term, the one for which $\Delta \ell = \pm 1$.

The sum is therefore 

$$E_1^{(2)} = \left(eE\right)^2 \sum_{n\neq 1} {|\braket{n,1,0|\hat{z}|1,0,0}|^2\over E_1^{(0)}-E_n^{(0)}}.$$

The requirements that $\Delta m=0$ and $\Delta \ell =1$ are examples of **selection rules**. We'll see these again when we discuss transitions between states in atoms. In that case, the perturbing electric field comes from a passing electromagnetic wave, which perturbs the state and gives a non-zero probability of finding the atom in a different eigenstate, ie. a transition can occur.

It is possible to evaluate the sum and obtain $E_1^{2}$. If we write the energy shift in terms of the polarizability of the atom $\alpha$ as 


$$E_1^{(2)} = -{1\over 2}\alpha E^2$$

(where $\alpha E$ is the electric dipole moment induced in the atom),  the exact calculation gives 

$$\alpha = {9\over 2} a_0^3.$$

That calculation is a bit involved to go through the details here (it is covered in the book by Shankar), but one thing that we can do easily is to place limits on $\alpha$, since we know that 

$$|E_1^{(0)}-E_n^{(0)}| >  |E_1^{(0)}-E_2^{(0)}| = {3\over 4}\mathrm{Ry}$$

where $1\ \mathrm{Ry}=13.6\ \mathrm{eV}$ (Rydberg). We can then write

$$\alpha <  e^2 {4\over 3\mathrm{Ry}} \sum_{n\neq 1, \ell, m} |\braket{n,\ell,m|\hat{z}|1,0,0}|^2$$

$$= 2e^2 {4\over 3\mathrm{Ry}} \sum_{n, \ell, m} |\braket{n,\ell,m|\hat{z}|1,0,0}|^2$$

$$= 2e^2 {4\over 3\mathrm{Ry}} \sum_{n, \ell, m} \braket{1,0,0|\hat{z}|n,\ell,m}\braket{n,\ell,m|\hat{z}|1,0,0}$$

$$= 2e^2 {4\over 3\mathrm{Ry}} \braket{1,0,0|\hat{z}^2|1,0,0}$$

(where we used the identity operator). therefore

$$\alpha < 2e^2{4\over 3\mathrm{Ry}} \langle \hat{z}^2 \rangle,$$

where the expectation value is for the ground state of hydrogen. It is straightforward to show that $\langle z^2\rangle = (1/3)\langle r^2\rangle = a_0^2$, and therefore

$$\alpha < 2e^2 {4\over 3\mathrm{Ry}} a_0^2 = \alpha \hbar c {16\over 3 \alpha^2 m_e c^2} a_0^2$$

$$\Rightarrow \boxed{\alpha <  {16\over 3} a_0^3}$$

This is quite close to the actual answer ($16/3=5.33$ compared with $9/2=4.5$).


## The first excited state: degenerate perturbation theory

Now imagine doing the same calculation but for one of the excited states with $n=2$. There are 4 states with $n=2$: $\ket{2,0,0}$,  $\ket{2,1,0}$,  $\ket{2,1,1}$,  $\ket{2,1,-1}$, all with the same energy.




## Further reading

- Townsend 11.3 discuss degenerate perturbation theory.

