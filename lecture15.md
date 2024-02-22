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

Now imagine doing the same calculation but for one of the excited states with $n=2$. There are 4 states with $n=2$: $\ket{2,0,0}$,  $\ket{2,1,0}$,  $\ket{2,1,1}$,  $\ket{2,1,-1}$, all with the same energy. This means that we have a lot of freedom in choosing our unperturbed basis $\ket{\Psi_n^{(0)}}$ because any linear combination of the four $n=2$ states is also an eigenstate of the Hamiltonian with the same energy. We say that the $n=2$ states span a **degenerate subspace**. Which linear combinations should we choose? Even more of a problem is that when we try to calculate the first order correction to the eigenstate $\ket{\Psi^{(1)}_n}$, the denominator $E_n^{(0)}-E_k^{(0)}$ will vanish for any pair of degenerate states. This is a signal that unless we are careful in choosing our basis states, the degenerate basis states do not have a small correction term. 

One way to think of this is as a singular limit -- imagine if we could solve the new Hamiltonian exactly and find the new states $\ket{\Psi_n}$. As we reduce the electric field strength to zero, these new states should continuously evolve into the unperturbed states $\ket{\Psi_n^{(0)}}$. Usually the perturbation breaks the symmetry of the original Hamiltonian that lead to the degeneracy, so there is a preferred basis for the degenerate subspace that reflects this symmetry-breaking. When we go the other way and start with $E=0$, we don't have a preferred basis and this leads to trouble when we try to find the corrections to the eigenstates.

We can see mathematically that we can solve the problem of the degeneracy in the denominator if we could make the numerator $\braket{\Psi_n^{0}|\hat{H}_1|\Psi_k^{0}}$ also vanish. This is saying that we should choose the basis states for the degenerate subspace so that the off-diagonal matrix elements vanish: i.e. the basis states we need are the states that diagonalize $\hat{H}_1$. Since we have four $n=2$ states, there are in principle 16 different matrix elements that we need to calculate. However, the selection rules $\Delta m=0$ and $\Delta \ell=\pm 1$ mean that there are actually only 2 non-vanishing matrix elements:

$$\braket{2,0,0|\hat{z}|2,1,0}\hspace{1cm} \mathrm{and}\hspace{1cm} \braket{2,1,0|\hat{z}|2,0,0}$$

Using the hydrogen atom wavefunctions you can show that 

$$\braket{2,0,0|\hat{z}|2,1,0} = \int dV R^\star_{20}Y^\star_{00}\ r \cos\theta\ R_{21}Y_{10} = -3a_0$$

so the matrix representation of $\hat{H}_1$ in the basis ($\ket{2,0,0}$,  $\ket{2,1,0}$,  $\ket{2,1,1}$,  $\ket{2,1,-1}$) is

$$\begin{pmatrix} 0 & -3a_0 & 0 & 0\\ -3a_0 & 0 & 0 & 0\\0 & 0 & 0 & 0\\0 & 0 & 0 & 0  \end{pmatrix}$$

The eigenvectors and eigenvalues of this matrix are:

$$\ket{2,1,1}\hspace{1cm} 0$$

$$\ket{2,1,-1}\hspace{1cm} 0$$

$$\ket{+} = {1\over\sqrt{2}}\left(\ket{2,0,0}-\ket{2,1,0}\right)\hspace{1cm} +3a_0$$

$$\ket{-} = {1\over\sqrt{2}}\left(\ket{2,0,0}+\ket{2,1,0}\right)\hspace{1cm} -3a_0$$

So now the idea is that we can adopt the basis $(\ket{2,1,1},\ket{2,1,-1},\ket{+}, \ket{-})$ for the $n=2$ zeroth order eigenstates. The first order energy shift for these 4 states
are

$$\braket{2,1,1|\hat{H}_1|2,1,1} = 0$$

$$\braket{2,1,-1|\hat{H}_1|2,1,-1} = 0$$

$$\braket{+|\hat{H}_1|+} = 3eEa_0$$

$$\braket{-|\hat{H}_1|-} = -3eEa_0$$

The perturbing electric field breaks the degeneracy of the $n=2$ states: two of the states stay at the same energy, one state increases and one decreases in energy. Note that the corrections are linear in the electric field -- this is the **linear Stark effect**.

Also note that when we calculate the second order correction to energy or the first order correction to the states, the terms with the zero denominators now vanish because we are using the new basis that diagonalizes $\hat{H}_1$ in the degnerate subspace. (The other terms involving higher order states will still be there and lead to higher order corrections).

The particular combinations $\ket{+}$ and $\ket{-}$ are selected out by the perturbation because they have a permanent dipole moment. This existing dipole moment then interacts with the electric field to give a linear dependence of the energy on electric field.



## Further reading

- Townsend 11.3 discuss degenerate perturbation theory.

