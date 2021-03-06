# Hydrostatics

The focus of his course is fluid *dynamics* in which fluid parcels
have interesting nonrivial motion. Nonethelss I would like to pause here
and make a couple of statements about static fluid configurations
in the presence of nontrivial forces.

## 1. Conservative force field

First, if the force per unit mass is conservative, then 

$$
	\frac{1}{\rho} {\vec F}_{ext} = {\vec \nabla} \Psi
$$

Note this is not necessarily the same as ${\vec F}_{ext}$ being a gradient.
Note also that it does include cases such as a constant vertical gravitational
field for which $\Psi = - g z$. In this case, if the fluid parcels are static,

$$
	{\vec \nabla} p = \rho 	{\vec \nabla} \Psi
$$

For constant $\rho$ we would just have $p = \rho \Psi$. More generally, taking
the curl of both sides and recalling that the curl of the gradient vanishes,

$$
	{\vec \nabla} \rho \times {\vec \nabla \Psi} = 0
$$

which is only possible if the gradients of $\rho$ and $\Psi$ are parallel, and
thus their level lines coincide.

## 2. Example: Isothermal atmospere

Let us consider the case that the atmosphere is uniform 
in the directions horizontal to the ground, so that $p,\rho$ depend 
on the vertical coordinate $z$ only, and

$$
	\partial_z p = - \rho g
$$

If $\rho$ is constant, then $p(z) = p(0) - g \rho z$. If $\rho$ is not
constant but the atmosphere is an ideal gas at fixed temperature,
$p = \rho T/m$ is the ideal gas law, where $m$ is the mass per molecule
(for a monomolecular gas) so hat $\rho/m$ is he number of molecules per
unit volume. For constant $T$ ("isothermal gas"), the hydrostatic equation
becomes:

$$
	\partial_z p = \frac{T}{m} \partial_z \rho = - \rho g
$$

This has the exponential solution
$$
	\rho(z) = \rho(0) e^{-m g z/T} \Rightarrow p(z) = \frac{T \rho(0)}{m} 
	e^{-mgz/T}
$$
where $z = 0$ is the ground and $z$ increases aboveground.

The actual atmosphere is more complex: the temperature itself drops in the
troposhere up to the *tropopause*, around $\sim 10$km 
high, and then after remaining constant for another $\sim 30$ km, 
begins to rise wih height in the stratosphere. The actual profile 
$p(z)$ is somewhere between exponentially decaying and linearly decaying.
In general, the atmosphere and ocean are *stratified fluids* with 
vertically varying densities.

