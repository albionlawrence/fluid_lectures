# Nonlinear waves

So far in this section we have focused on small-amplitude waves which can be 
well-described by *linea* partial differential equations in space and time. In 
thesese cases there is a fairly systematic method for solving the equations. 
We find a set of soluions which at fixed time provide a complete set of 
functions of space (such as sines and/or cosines) in which any initial 
condition can represented as a linear combination of these functions. 
The time evolution  then follows by summing the time-evolved components. 
This is he essence of solutions to both Maxwell's and Schr&ouml;dinger's 
equations as well as to the diffusion equation. The result is waves which
may or may not disperse, with modes of different wavelength having distinct
phase velocities.

When we pass to nonlinear equations, there is generally no such 
systematic method for solving them, except perhaps in the case that 
the nonlinearity is weak. Qualitatively different phenomena can emerge, 
such as shocks, singularities, and turbulence, in which through nonlinear 
effects, energy can be passed to shorter and shorter distance scales (or in
the case of 2d turbulence, longer and longer scales). 

To get a hint of how this might happen, let us consider he following
nonlinear ODE:

$$
	{\ddot x} + \Omega^2 x - g x^2 = 0
$$

where we take $\epsilon = g/\Omega^2 \ll 1$. We can then expand

$$
	x = x_0 + \epsilon x_1 + \ldots
$$

where ${\ddot x_0} + \Omega^2 x_0 = 0$. This is solved by $x_0 = X \cos\Omega t$
(we have shifted an extra phase away by redefining the origin of $t$.) Now
at order $\epsilon$ we have:

$$
	{\ddot x}_1 + \Omega^2 x_1 = \Omega^2 X \cos^2 \Omega t = \frac{1}{2} 
	\Omega^2 X (1 + \cos 2 \Omega t)
$$

We will solve this with Green's function techniques. That is, if we find
$G$ such that $\partial_t^2 G(t,t') + \Omega^2 G(t,t') = \delta(t - t')$,
then we merely need write

$$
	x_1 = \Omega^2 \int_0^{\infty} dt' G(t,t') x_0(t')^2
$$

You can convince yourself that

$$
	G(t,t') = \frac{1}{\Omega} \sin \Omega (t-t') \theta(t-t')
$$

satisfies this equation, and because of the Heaviside step function ensures that response follows stimulus. Returbing to the problem above, we find

$$
	x_1 = \frac{1}{12} X (- 4 + 3 \cos \Omega t + \cos 3 \Omega t)
$$

so you can see that higher frequencies get excited at this leading 
nonlinear order.

	
