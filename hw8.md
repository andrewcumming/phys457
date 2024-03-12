# Homework 8

This homework is due on Tuesday March 19th. You should submit a PDF of your solutions on myCourses.

1. Prove the following expressions from the formula sheet on the midterm, by evaluating the integrals using the expressions for $R_{n\ell}$ and $Y_{\ell m}$ from Townsend (or elsewhere):

$$\int_0^\infty dr\, r^3\, R_{3,2} R_{3,1} = -{9\sqrt{5}\over 2} a_0$$

$$\int d\Omega\, Y^\star_{2,1} Y_{1,1} \cos\theta = \int d\Omega\, Y^\star_{2,-1} Y_{1,-1} \cos\theta = {1\over \sqrt{5}}$$

Note that you can use Mathematica or other symbolic tool to do the integrals if you want to (show your code in your answer). (The idea behind asking you to do this is so that you can get some hands-on experience with the hydrogen wavefunctions.)

2. A particle of mass $m$ moves in a 1D potential

$$V(x) = \begin{cases} V_0 & \text{$|x| < a$} \\
0 & \text{$a<|x|<b$} \\
\infty & \text{$|x|>b$}
\end{cases}$$

for $-\infty<x<\infty$, where $V_0$ is a positive constant. This is the ``double square well'' potential that we discussed in class.

(a) Sketch $V(x)$ and explain why we can treat this problem by integrating the Schrödinger equation from $x=0$ to $x=b$ (i.e. consider positive $x$ only) if we use boundary conditions $\psi(x=b)=0$ and **either** $\psi(0)=0$ **or** $d\psi/dx|_{x=0} = 0$ at $x=0$.

(b) Writing the solution as 

$$\psi(x) = Ae^{qx} + B e^{-qx}$$

for $x<a$ and 

$$\psi(x) = Ce^{ikx} + De^{-ikx}$$

for $a<x<b$, show that (1) $(ka)^2 + (qa)^2 = {2ma^2V_0/\hbar^2}$ and (2) depending on which boundary condition you choose at $x=0$, $k$ and $q$ are related by either

$${\tanh{qa}\over qa} = - {\tan(k(b-a))\over ka}$$

or

$${1\over qa\tanh{qa}} = - {\tan(k(b-a))\over ka}.$$

(c) Plot conditions (1) and (2) in the $qa$--$ka$ plane, similar to Figure 10.8 in Townsend (Finite Spherical Well, p363). You can do this using the `ContourPlot` function in Mathematica (see [lecture 13](https://andrewcumming.github.io/phys457/lecture13.html#finite-spherical-well)). Make your plot for a specific choice of the ratio $(b-a)/a$, for example you could set $b-a=3a$, and for $2ma^2V_0/\hbar^2$, for example you could choose $2ma^2V_0/\hbar^2=1$. 

(d) Use your plot to find out which of the two $x=0$ boundary conditions gives the lowest energy state. Explain whether your answer makes sense physically.

