# Diffusion and Viscosity

With this background I next want to work throug some examples, mostly from the book, which
demonstrate the role of viscosity as something that diffuses vorticity. This is especially
apparent in two dimensions, for which the vorticity equations are

$$
	D_t \omega = \nu \nabla^2 \omega
$$

This equation is the advection-diffusion equation for vorticity. he vorticity has a tendency to spread out 
over time. Note that this equation shows the degree to which we can think of vorticity (or in 3d stratified
fluids, a related quantity known as *potential vorticity*) as a material quantity that is advected by and 
that diffuses through the fluid.

## Fluid near a moving plate

Before moving to vorticity, let us look at a "simple" 2d problem. Consider a semiinfinite fluid 
occupying $y > 0$ in the $(x,y)$ plane. At $t = 0$ it is completely static. Equal pressure is exerted from
infinity. For $t > 0$, the bottom boundary at $y = 0$ moves in the $+x$ direction with velocity $u_0$.

To solve this, we will assume that ${\vec v} = u(y,t) {\hat x}$, given the uniformity in $x$. 
(Can we think of a good argument for the lack of a $y$ component?). With this ans&auml;tz the 
nonlinear term ${\vec v} \cdot {\vec \nabla} {\vec v}$ drops out. The equation is

$$
	\partial_t u = - \frac{1}{\rho} \partial_x p + \nu \partial_y^2 u
$$

The gradient of $p$ vanishes in the other directions. Since $u$ depends only on $y$, $\partial_x p$ must
be a constant. Since we impose equal pressure at infinity, this constant must be zero. Finally, we need boundary 
conditions. The no-slip condition for a static boundary is $u = 0$. For a uniformly moving boundary, we can work
in the moving reference frame, to get the same no-slip condition. This in the rest frame of the fluid
at infinity, for which the boundary is moving $u(0,t) = u_0$. We must also puta boundary condition at $y = \infty$.
We will demand that $u(\infty, t) = 0$ for any finite $t$; there is not time for the fluid at infinity to
respond to the plate.

Note that we get the same equation for $\partial_y u = - \omega$, so we have a diffusion equation for $\omega$,
which in this simple case is also a diffusion equation for $u$ itself. Initially, we should find that $u,\omega \neq 0$
only at the boundary $y = 0$, corresponding to a delta function-supported *vortex sheet* that diffuses upwards.
Indeed, as we will see, $\omega$ is a Gaussian spreading as $\Delta y \sim \sqrt{\nu t}$. 

Because we expect (dimensionally) $\delta x \sim \sqrt{\nu t}$, we will attempt a *similarity solution* 
$u(y,t) = u_0 f(\eta)$ with $\eta = y/(\nu t)^{1/2}$. We will dig into this sort of ans&auml;tz much later in the book.
Here $f$ is dimensionless and the factor of $u_0$ is used simply because $u_0$ is the only parameter with dimensions
of velocity in the problem. Applying the Navier-stokes equation to this ans&auml;tz, we find

$$
	f''(\eta) + \frac{1}{2} \eta f'(\eta) = 0
$$

We can think of this as a first order equation for $f'$, with solution $f' - C e^{-\eta^2/4}$. Integrating further,

$$
	f = A + C \int_0^{\eta} ds e^{-s^2/4}
$$

Now $C,A$ must be fixed by the boundary conditions. First, we need $f(0) = 1$ 
to satisfy the boundary conditions at $y = \eta = 0$, and thus $A = 1$.
Next, we need $f(\infty) = 0$. Since $ \int_0^{\infty} ds e^{-s^2/4} = \sqrt{\pi}$,
we have $B = - \frac{1}{\sqrt{\pi}$. Thus,

$$
	u(y,t) = u_0 \left[1 - \frac{1}{\sqrt{\pi}} \int_0^{y/\sqrt{\nu t}} ds e^{-s^2/4} \right]
$$

The viscosity is

$$
	\omega = - \partial_y u = \frac{u_0}{\sqrt{\pi \nu t}} e^{- \frac{y^2}{4\nu t}}
$$

Note that this is basically exactly the solution to the diffusion equation for a delta function
initial condition. Indeed you can show from the solution that as $t \to 0$, $\omega \to u_0 \delta(y)$.
