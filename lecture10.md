# Lecture 10 Feb 6

Today we'll continue with the discussion of the hydrogen atom wavefunctions and energy levels.

## How this works mathematically: Laguerre polynomials

One we make the subsitution $u(r) = rR(r)$, we have

$$\left[- {\hbar^2\over 2\mu}{d^2\over d r^2} +  {\ell(\ell+1)\hbar^2\over 2\mu r^2} -{e^2\over 4\pi \epsilon_0 r}\right]u(r) = E u(r).$$

It is interesting to develop the analytic solution to this equation and to see where the quantization of energy comes in. We'll use the notation from Townsend so we match section 10.2 of the book. First, we define

$$\rho = \sqrt{8\mu(-E)\over \hbar^2} r$$

which gives

$${d^2 u\over d\rho^2} - {\ell(\ell+1)\over \rho^2} u + \left({\lambda\over \rho} - {1\over 4}\right)u = 0$$

where 

$$\lambda = {e^2\over 4\pi\epsilon_0\hbar}\sqrt{\mu\over 2(-E)}.$$

The limiting solutions are then $\rho^{\ell+1}$ for $\rho\rightarrow 0$ and $e^{-\rho/2}$ for $\rho\rightarrow \infty$. To incorporate this behaviour, look for a solution

$$\boxed{u(\rho) = \rho^{\ell+1} e^{-\rho/2} F(\rho)}$$

Substituting this in gives the following equation for $F(\rho)$,

$$\boxed{{d^2F\over d\rho^2} + \left({2\ell+2\over\rho} -1\right){dF\over d\rho} + {\lambda-\ell-1\over\rho}F = 0}$$

The solutions to this equation are the **associated Laguerre polynomials**.

Look for a polynomial solution

$$F(\rho) = \sum_{k=0}^\infty c_k\rho^k,$$

$$\Rightarrow \sum_{k=2}^\infty k(k-1) c_k \rho^{k-2} + 
\sum_{k=1}^\infty (2\ell+2) k c_k \rho^{k-2} + 
\sum_{k=0}^\infty \left[-k+\lambda -\ell-1  \right]c_k \rho^{k-1} = 0.$$

Since we have $\rho^{k-2}$ in the first two terms and $\rho^{k-1}$ in  the last term, it is useful to translate the index $k$ by 1  in the first two terms so that all the terms have a $\rho^{k-1}$ in them, ie. we write

$$\sum_{k=2}^\infty k(k-1) c_k \rho^{k-2}=\sum_{k=1}^\infty (k+1)k c_{k+1} \rho^{k-1} = \sum_{k=0}^\infty (k+1)k c_{k+1} \rho^{k-1}$$

$$\sum_{k=1}^\infty (2\ell+2) k c_k \rho^{k-2} = \sum_{k=0}^\infty (2\ell+2) (k+1) c_{k+1} \rho^{k-1}$$

then

$$\sum_{k=0}^\infty \left\{\left[k(k+1)+(2\ell+2)(k+1)\right]c_{k+1} + \left[-k +\lambda-\ell-1\right]c_k \right\}\rho^{k-1} = 0.$$

Since this must be true for arbitrary values of $\rho$, the coefficient has to vanish in every term, giving a *recurrence relation* for the polynomial

$${c_{k+1}\over c_k} = {k + \ell + 1 -\lambda\over (k+1)(k+2\ell+2)}.$$

The key part of the argument is to see that for large $k$, this ratio is $c_{k+1}/c_k\rightarrow 1/k$ which is the same as for an exponential function since

$$e^x = \sum_{k=0}^\infty {x^k\over k!} \Rightarrow {c_{k+1}\over c_k} = {1\over k+1} \approx {1\over k}$$

for large $k$. This suggests that we won't be able to satisfy the boundary condition that the wavefunction remain finite as $\rho\rightarrow \infty$. However, there is a way out when $\lambda-\ell-1$ is an integer! Then the series will terminate at the term with $k=n_r$ where

$$n_r = \lambda-\ell-1 = 0, 1, 2,\dots$$

(it terminates because then $c_{n_r+1}/c_{n_r}=0$ so the coefficient of the next term and therefore subsequent terms vanishes).

The fact that $\lambda$ must be an integer shows that the energy $E$ must be quantized. We write the integer value of $\lambda$ as the **principle quantum number** $n$, which gives

$$E_n = - {1\over 2}\mu c^2 \left({e^2\over 4\pi\epsilon_0 \hbar c}\right)^2 {1\over n^2} = - {1\over 2} \alpha^2 \mu c^2 {1\over n^2}.$$

For hydrogen with $\mu\approx m_e$, this is $E_n=-(13.6\ \mathrm{eV})/n^2$.


```{admonition} Exercise: plot the radial wavefunctions

We can use [`scipy.special.genlaguerre`](https://docs.scipy.org/doc/scipy/reference/generated/scipy.special.genlaguerre.html#scipy.special.genlaguerre) to obtain the Laguerre polynomials. The equation given in the documentation for these functions is 

$$x{d^2\over dx^2}L_n^\alpha + (\alpha+1-x){d\over dx}L_n^\alpha + n L_n^\alpha =0.$$

We see that this corresponds to our equation for $F(\rho)$ if we take $n\rightarrow n_r$ and $\alpha\rightarrow 2\ell+1$.

Use this to plot the radial functions

$$R(\rho) = \rho^\ell e^{-\rho/2} F(\rho)$$ 

for different $\ell$ and $n_r$.

Note that $n_r$ determines the number of radial nodes. The relation $n = n_r + \ell + 1$  shows the partitioning of energy between radial and angular motion. For a given $n$ there are $n^2$ different ways to choose $n_r$ and $\ell$. This is similar to the angular momentum eigenfunctions where $\ell$ sets the overall wavelength but the number of nodes in $\theta$ or $\phi$ depend on the choice of $m$. 

Also note that for a given $n$, the maximum value of $\ell$ we can have corresponds to $n_r=0$, i.e. $\ell = 0,\dots n-1$.

```



## Summary: hydrogen atom wavefunctions

To summarize, we can now write the stationary states for the hydrogen atom as

$$\braket{\mathbf{r}|\Psi} = R_{n,\ell}(r) Y_{\ell m}(\theta,\phi)$$

where the angular function depends on $\ell$ and $m$ and the radial function depends on $n$ and $\ell$. For a given $n$, $\ell$ goes from $0$ to $n-1$, and for a given $\ell$, $m$ goes from $-\ell$ to $+\ell$. In spectroscopic notation, we get the orbitals 1s, 2s, 2p, 3s, 3p, 3d, 4s, 4p, 4d, 4f, etc.

In terms of $r$, the variable $\rho$ is

$$\rho = \sqrt{8\mu(-E)\over \hbar^2}r = {2\mu c\alpha r\over \hbar n} = {2r\over na_0}$$ 

where $a_0$ is the Bohr radius. We can then write down the radial functions $R(r)$, for example the ground state with $n_r=0$ has $F$ constant, giving

$$R_{10} = 2\left({1\over a_0}\right)^{3/2}e^{-r/a_0}.$$

This also holds for a general hydrogenic (one electron) atom with a nuclear charge $Z$ if we replace $a_0\rightarrow a_0/Z$. 

Here are the $n=2$ eigenfunctions:

$$R_{20} = 2\left({1\over 2a_0}\right)^{3/2}\left(1-{r\over 2a_0}\right)e^{-r/2a_0}$$

$$R_{21} = {1\over \sqrt{3}}\left({1\over 2a_0}\right)^{3/2}{r\over 2a_0}e^{-r/2a_0}$$

You can see that the $\ell=n-1=1$ function has an extra factor of $r$ compared to $R_{10}$, as it must since we need $R\propto r^\ell$ near the origin. You can also see that $R_{20}$ with $\ell=0$ has a radial node (i.e. it will change sign as $r$ increases), as expected since we now have $n_r=n-\ell-1=1$.


```{admonition} Exercise: size of atom

Consider the state with $\ell = n-1$, i.e. with maximal angular momentum for a given $n$. Explain why this simplifies the form of the radial part of the wavefunction. Compute the radius which maximises the probability density $r^2|\Psi|^2$ for this state. Write your answer in terms of $a_0$, $Z$ and $n$.

```




## Further reading

- Townsend section 10.2.

