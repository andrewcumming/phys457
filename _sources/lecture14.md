# Lecture 14 Feb 20

## The Stark effect in hydrogen and perturbation theory

The Stark effect is the shift in the energy levels of hydrogen when an electric field is applied to the atom. If the electric field is of strength $E$ and points upwards in the $z$-direction, the potential in which the electron moves has an additional term $V=eEz$. You can check the sign here by calculating the force on the electron $-\partial V/\partial dz=-eE$ which is downwards as expected.

The Hamiltonian therefore has an additional term

$$\hat{H}_1 = eE\hat{z}.$$

This extra term in the Hamiltonian will change the energy levels of the atom, but only by a small amount. We can see this because we know that the energy scale of the ground state for instance is $13.6\ \mathrm{eV}$ which tells us that we would need an electric field $E\sim 13.6\ \mathrm{V}/a_0$ to make an order unity correction to the energy (here we've used the Bohr radius $a_0$ as a typical value for the separation $z$). This is a huge electric field! The maximal electric field you can make in air is the breakdown electric field, which is  $E\sim 13.6\ \mathrm{V}/\lambda_\mathrm{mfp}$ where $\lambda_\mathrm{mfp}$ is the mean free path. (This is because an electron or ion that accelerates in the electric field gains enough energy between collisions to ionize further atoms, causing a runaway ionization, and a breakdown of the air.)

So, we have a situation where we are adding a small additional term to the Hamiltonian. We can write this as 

$$\hat{H} = \hat{H}_0 + \lambda \hat{H_1}$$

where we explicitly write a parameter $\lambda$ that "labels" the small part of the Hamiltonian (we can set it to 1 later). In perturbation theory, the idea is then to look for a solution 

$$E_n = E_n^{(0)} + \lambda E_n^{(1)} + \lambda^2 E_n^{(2)} + \dots$$

$$\ket{\Psi_n} = \ket{\Psi_n^{(0)}} + \lambda \ket{\Psi_n^{(1)}} + \lambda^2 \ket{\Psi_n^{(2)}} + \dots$$

where $E_n$ and $\ket{\Psi_n}$ are the eigenvalues and eigenstates of the new Hamiltonian that satisfy $\hat{H}\ket{\Psi_n} = E_n \ket{\Psi_n}$,  ie.

$$ \left(\hat{H}_0 + \lambda \hat{H_1}\right)\left(\ket{\Psi_n^{(0)}} + \lambda \ket{\Psi_n^{(1)}} + \lambda^2 \ket{\Psi_n^{(2)}} + \dots \right) = \left(E_n^{(0)} + \lambda E_n^{(1)} + \lambda^2 E_n^{(2)} + \dots \right)\left(\ket{\Psi_n^{(0)}} + \lambda \ket{\Psi_n^{(1)}} + \lambda^2 \ket{\Psi_n^{(2)}} + \dots \right)  $$

Now we can identify terms with different powers of $\lambda$:

$$\lambda^0:\hspace{1cm} \hat{H}_0 \ket{\Psi_n^{(0)}} = E_n^{(0)}\ket{\Psi_n^{(0)}}$$

$$\lambda^1:\hspace{1cm} \hat{H}_1 \ket{\Psi_n^{(0)}} + \hat{H}_0 \ket{\Psi_n^{(1)}} = E_n^{(0)}\ket{\Psi_n^{(1)}} + E_n^{(1)}\ket{\Psi_n^{(0)}}$$

$$\lambda^2:\hspace{1cm} \hat{H}_1 \ket{\Psi_n^{(1)}} + \hat{H}_0 \ket{\Psi_n^{(2)}} = E_n^{(2)}\ket{\Psi_n^{(0)}} + E_n^{(1)}\ket{\Psi_n^{(1)}} + E_n^{(0)}\ket{\Psi_n^{(2)}}$$

and so on, although we'll only need up to second order here.

The first equation tells us that the zeroth order energies and eigenstates are just those of the original Hamiltonian $\hat{H}_0$. Looking at the second equation, we can see that we can derive an expression for $E_n^{(1)}$ if we operate from the left with $\bra{\Psi_n^{0}}$:

$$\braket{\Psi_n^{(0)}|\hat{H}_1 |\Psi_n^{(0)}} + \braket{\Psi_n^{(0)}|\hat{H}_0 |\Psi_n^{(1)}} = E_n^{(0)}\braket{\Psi_n^{(0)}|\Psi_n^{(1)}} + E_n^{(1)}\braket{\Psi_n^{(0)}|\Psi_n^{(0)}}$$

$$\Rightarrow \braket{\Psi_n^{(0)}|\hat{H}_1 |\Psi_n^{(0)}} + E_n^{(0)}\braket{\Psi_n^{(0)}|\Psi_n^{(1)}} = E_n^{(0)}\braket{\Psi_n^{(0)}|\Psi_n^{(1)}} + E_n^{(1)}$$

$$\Rightarrow \boxed{E_n^{(1)} = \braket{\Psi_n^{(0)}|\hat{H}_1 |\Psi_n^{(0)}} }$$

This tells us that **to find the first order correction to the energy, we just need the zeroth order eigenfunctions**. This is a general pattern: the energy correction at some order only relies on the eigenfunction at the previous order. For example, now operate from the left with $\bra{\Psi_n^{0}}$ on the third equation:

$$\braket{\Psi_n^{(0)}|\hat{H}_1 |\Psi_n^{(1)}} + \braket{\Psi_n^{(0)}|\hat{H}_0|\Psi_n^{(2)}} = E_n^{(2)}\braket{\Psi_n^{(0)}|\Psi_n^{(0)}} + E_n^{(1)}\braket{\Psi_n^{(0)}|\Psi_n^{(1)}} + E_n^{(0)}\braket{\Psi_n^{(0)}|\Psi_n^{(2)}}$$

$$\Rightarrow \braket{\Psi_n^{(0)}|\hat{H}_1 |\Psi_n^{(1)}} + E_n^{(0)}\braket{\Psi_n^{(0)}|\Psi_n^{(2)}} = E_n^{(2)} + E_n^{(1)}\braket{\Psi_n^{(0)}|\Psi_n^{(1)}} + E_n^{(0)}\braket{\Psi_n^{(0)}|\Psi_n^{(2)}}$$

$$\Rightarrow \boxed{E_n^{(2)} =  \braket{\Psi_n^{(0)}|\hat{H}_1 |\Psi_n^{(1)}} - E_n^{(1)}\braket{\Psi_n^{(0)}|\Psi_n^{(1)}} }$$

which shows that we need $\ket{\Psi_n^{(1)}}$ in order to calculate $E_n^{(2)}$.

We can use the original eigenstates $\ket{\Psi_n^{(0)}}$ as a basis for $\ket{\Psi_n^{(1)}}$:

$$\ket{\Psi_n^{(1)}} = \sum_k c_k \ket{\Psi_k^{(0)}}$$

where the coefficients are

$$c_k = \braket{\Psi_k^{(0)}|\Psi_n^{(1)}}.$$

To find the $c_k$'s, we can operate on the $\lambda^1$ equation with $\bra{\Psi_k^{0}}$:

$$\braket{\Psi_k^{(0)}|\hat{H}_1 |\Psi_n^{(0)}} + \braket{\Psi_k^{(0)}|\hat{H}_0 |\Psi_n^{(1)}} = E_n^{(0)}\braket{\Psi_k^{(0)}|\Psi_n^{(1)}} + E_n^{(1)}\braket{\Psi_k^{(0)}|\Psi_n^{(0)}}$$

$$\Rightarrow\braket{\Psi_k^{(0)}|\hat{H}_1 |\Psi_n^{(0)}} + E_k^{(0)}c_k = E_n^{(0)}c_k + E_n^{(1)}\delta_{kn}.$$

For $k=n$, we get the result from above for $E_n^{(1)}$, but for $k\neq n$, we get:

$$\boxed{c_k = {\braket{\Psi_k^{(0)}|\hat{H}_1 |\Psi_n^{(0)}}\over E_n^{(0)}-E_k^{(0)}}}.$$

This gives us all the coefficients except $c_n$. We can get a constraint on that one by looking at the overall normalization:

$$\braket{\Psi_n|\Psi_n} = \braket{\Psi_n^{(0)}|\Psi_n^{(0)}} + \lambda \left(\braket{\Psi_n^{(0)}|\Psi_n^{(1)}}+\braket{\Psi_n^{(1)}|\Psi_n^{(0)}}\right) + \dots$$

$$\Rightarrow \braket{\Psi_n|\Psi_n} = 1 + \lambda \left(c_n + c_n^\star\right) + {\mathcal O}(\lambda^2).$$

This shows that the new state will be normalized to first order in $\lambda$ if $c_n + c_n^\star = \mathrm{Re}(c_n)=0$, i.e. if $c_n$ is pure imaginary. But adding an imaginary $c_n = ia$ is equivalent to changing the overall phase of the wavefunction to first order:

$$\ket{\Psi_n} = (1+ i \lambda a)\ket{\Psi_n^{(0)}} + \lambda \sum_{k\neq n} c_k \ket{\Psi_k^{(0)}}  + {\mathcal O}(\lambda^2)$$

$$\Rightarrow \ket{\Psi_n} = e^{i\lambda a}\left[\ket{\Psi_n^{(0)}} + \lambda \sum_{k\neq n} c_k \ket{\Psi_k^{(0)}}\right]  + {\mathcal O}(\lambda^2)$$

so for simplicity it makes sense to choose $a=0$ and therefore $c_n=0$. The perturbation changes the state in an orthogonal way, i.e. it changes the direction of the state in Hilbert space, but not the magnitude. The same thing happens in 3D space if you rotate a vector by a small amount -- to first order in the angle, the rotation corresponds to adding a perpendicular vector to the original vector. 

We therefore arrive at the results:

$$\boxed{\ket{\Psi_n^{(1)}} =  \sum_{k\neq n} {\braket{\Psi_k^{(0)}|\hat{H}_1 |\Psi_n^{(0)}}\over E_n^{(0)}-E_k^{(0)}} \ket{\Psi_k^{(0)}} }$$

$$\boxed{E_n^{(2)} =  \sum_{k\neq n} {|\braket{\Psi_k^{(0)}|\hat{H}_1 |\Psi_n^{(0)}}|^2\over E_n^{(0)}-E_k^{(0)}}}$$

**Application to the Stark effect in the ground state of hydrogen**: For the ground state of hydrogen, $\ket{n,\ell,m}=\ket{1,0,0}$, with $\hat{H_1}= eE\hat{z}$, we get the first order energy shift

$$E_1^{(1)} = eE \braket{1,0,0|\hat{z}|1,0,0}.$$

But the state $\ket{1,0,0}$ is independent of angle ($Y_{00}$ is constant) and therefore even parity, whereas $\hat{z}$ had odd parity, so the integral vanishes! There is no correction to the energy to first order! We need to go to second order:

$$E_1^{(2)} = \left(eE\right)^2 \sum_{n\neq 1, \ell, m} {|\braket{n,\ell,m|\hat{z}|1,0,0}|^2\over E_1^{(0)}-E_n^{(0)}}$$

where the sum is over all the excited states. Note that the energy correction is quadratic in the electric field, i.e.~$\propto E^2$. This is known as the **quadratic Stark effect**. Physically, what's happening is that the electric field polarizes the ground state, so it develops a dipole moment $\propto E$. The energy of this dipole $\mathbf{p}$ in the electric field $\mathbf{E}$ is $\propto \mathbf{p}\cdot\mathbf{E}\propto E^2$. 

The sum can be evaluated to give the size of the energy shift. Note that because the sum is over all the excited states, there is no problem with the denominator $E_1^{(0)}-E_n^{(0)}$ vanishing. If we instead look at the $n=2$ excited states where there is degeneracy and the denominator does indeed vanish! We'll discuss how to handle that case next time. 


## Further reading

- Townsend 11.1 goes through the derivation of the first and second order corrections in perturbation theory, and 11.4 applies this to the Stark effect.

