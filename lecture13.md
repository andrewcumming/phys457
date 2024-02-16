# Lecture 13 Feb 15

Discussion of some remaining topics to finish off Chapters 9 and 10. 

## Finite spherical well

Last time we had the two solutions

$$u(r) = \begin{cases}  A \sin k_0 r & \text{$r<a$}\\
C e^{-qr} & \text{$r>a$}
\end{cases}
$$

where 

$$q = \sqrt{2\mu(-E)\over \hbar^2}; \hspace{1 cm} k_0 = \sqrt{2\mu(V_0+E)\over \hbar^2}.$$

The matching conditions at $r=a$ are that $u$ and $du/dr$ should be continuous, i.e.

$$A \sin k_0 a = C e^{-qa}$$

and 

$$A k_0 \cos k_0 a = - C q e^{-qa}$$

$$\Rightarrow \boxed{k_0 a \cot k_0 a = - qa}$$

We also have

$$\boxed{(qa)^2 + (k_0a)^2 = {2\mu V_0a^2\over \hbar^2} = r_0^2}$$

For a given potential well, we know the product $V_0a^2$ and therefore the parameter $r_0$. We can then plot contours in the $k_0$--$q$ plane that show where each of the two equations are satisfied. Where the curves overlap shows possible solutions. You can look at Figure 10.8 in Townsend or make your own, e.g. in Mathematica:

```
r0 = 2; ContourPlot[{x Cot[x] == -y, x^2 + y^2 == r0^2}, {x, 0, 2 Pi}, {y, 0, 8}]
```

For small $r_0$, there is no solution: the spherical well does not necessarily have a bound state. It needs to be either deep enough (large enough $V_0$) or wide enough (large enough $a$ to reduce the kinetic energy). The first bound state appears when $r_0\approx \pi/2$, corresponding to a weakly bound state whose energy lies just below the continuum $0<(-E)\ll V_0$. This is the case with the deuteron discussed last time.
 
## Infinite spherical well

In the infinite spherical well, we take $V=0$ inside the well ($r<a$) and $V=\infty$ outside ($r>a$). This can serve as a first model of an atomic nucleus, since we can think of a given neutron or proton trapped in a deep well corresponding to its strong attraction to the other nucleons.

Just as in 1D, the wavefunction now vanishes at the edge of the well, since there is no penetration into the classically-forbidden region when we take $V\rightarrow \infty$. The equation for the radial wavefunction $R(r)$ inside the well is then

$${d^2R\over dr^2} + {2\over r}{dR\over dr} - {\ell(\ell+1)\over r^2 R}+k^2 R=0$$

where $k^2 = 2\mu E/\hbar^2$. This is just the equation for a free particle since $V=0$ inside the well. 

The solutions to this equation are the [spherical Bessel functions](https://en.wikipedia.org/wiki/Bessel_function#Spherical_Bessel_functions) $R(r) = j_\ell(k r)$. There is also a second solution $\eta_\ell(kr)$, the spherical Neumann function, but they diverge at the origin so we don't include them in this case. Note that the solution we found for the finite well above is exactly $j_0(kr)$ -- we had $u\propto \sin(k_0 r)$ and therefore $R = u/r = \sin(k_0 r)/r \propto j_0(k r)$.

You can plot these functions in Mathematica using `Plot[SphericalBesselJ[0, x], {x, 0, 20}]` etc.

To implement the boundary condition $R=0$ at $r=a$, we need to choose $k$ and therefore $E$ so that $j_\ell(ka)=0$. For $\ell=0$, the zeros are at $ka=n_r\pi$ for $n_r=1,2,3,\dots$ ($n_r$ is the number of radial nodes, including the one at $r=a$), giving
 
$$E_{\ell=0} = {\hbar^2\over 2\mu a^2} (n_r\pi)^2.$$

For other values of $\ell$, you will need to look up or calculate the zeros of the Bessel functions (e.g. in Mathematica you can do `FindRoot[SphericalBesselJ[0, x], {x, 2}]` where you give an initial guess $x=2$ for the location of the root, this will return $\pi$ which is the first root of $j_0$). You can find a useful table in Townsend giving the first few zeros for $\ell$ up to 3. Figure 10.12 shows the energy levels as a funciton of $n_r$ and $\ell$. Unlike the H atom or harmonic oscillator, **there is no accidental degeneracy**: it is not possible to characterize the energy by a single principle quantum number. Instead, the energy depends on both $n_r$ and $\ell$.


 






## Further reading

- Townsend sections 10.3, 10.4. We are now done with Chapters 9 and 10 and will move onto Chapter 11 Perturbation theory next week.

