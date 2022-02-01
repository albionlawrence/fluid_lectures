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
we have $B = - \frac{1}{\sqrt{\pi}}$. Thus,

$$
	u(y,t) = u_0 \left[1 - \frac{1}{\sqrt{\pi}} \int_0^{y/\sqrt{\nu t}} ds e^{-s^2/4} \right]
$$

The viscosity is

$$
	\omega = - \partial_y u = \frac{u_0}{\sqrt{\pi \nu t}} e^{- \frac{y^2}{4\nu t}}
$$

Note that this is basically exactly the solution to the diffusion equation for a delta function
initial condition. Indeed you can show from the solution that as $t \to 0$, $\omega \to u_0 \delta(y)$.

## Variation: moving plate underneath rigid plate

for the next step I want to highlight another problem described in the text that combines two problems described
above. My goal here is to highlight how the solution is found (since one of the things you should get out
of fluid mechanics is how to solve differential equations). 

Here we have a 2d fluid infinite in extent in the $x$ direction, bounded by plates at $y = 0,h$. The plate at $y = h$
is static. For $t < 0$ the lower plate is as well; at $t = 0$, the lower plate starts to move with velocity $U$.
We assume vanishing pressure gradient. For $t < 0$, we take ${\vec u} = 0$. We assume the pressure is constant.

For $t > 0$, the boundary conditions are ${\vec u} = 0$ at $y = h$, ${\vec u} = U {\hat x}$ at $y = 0$. The latter is deduced
by passing to an inertial reference frame moving with the lower plate. In that frame the lower plate is static,
and we expect the no-slip condition ${\vec u} = 0$ to apply. In moving back to the original frame, we get the boundary condition
above. In addition to this, we have the initial condition ${\vec u}({\vec x},t = 0) = 0$.

Because there is no pressure gradient there is no force inthe $y$ direction. The sudden motion of the fluid at the boundary plate
will induce shear stress; we know this stress is a frictional force parallel to the elative velocity of two fluid layers.
Thus we expect ${\vec u} = u({\vec x},t) {\hat x}$. Finally, since the plate is infinite this shear sress is uniform in $x$ and
w expect no $x$-dependence, so that $u = u(y,t)$.

Plugging this into the Navier-Stokes equation for constant pressure, we find $\partial_t u = \nu \partial_y^2 u$. Given such a second-order
*linear* partial differential equation, it is tempting to proceed as one would for a particle with confining
walls in the Schr&ouml;dinger equation; find a complete basis of solutions of the form $f(t) g(y)$, and add them
with the appropriate coefficients to match the initial condition.

The problem in this case is that the sum of two solutions satisfying $u(0,t) = U$ will not satisfy this boundary condition.
Howeve, we can find a *particular* solution $\partial_t u_p = \nu \partial_y^2 u_p$, for which $u_p(0,t) = U$, $u_p(y,t) = 0$. Then
we can write $u = u_p + f(y,t)$; here $f(0,t) = f(y,t) = 0$, and because the Navier-Stokes equations are linear,
$\partial_t f + \nu \partial_y^2 f$. We can then expand $f$ in a complete set of solutions which all solve the same boundary condition,
imposing $f = -u_p$ at $t = 0$.

To find $u_p$ we consider static solutions so that $\partial_y^2 u_p = 0$. This has the general solution $u_p = C_1 y + C_2$. Imposing
the boundary conditions we find $C_2 = U$, $C_1 = - \frac{U}{h}$. Thus

$$
	u(y,t) = \frac{U}{h}(h - y) + f(y,t)
$$

Now given the Dirichlet boundary conditions, for any fixed $t$ we can expand $f$ in sin functions (eg write a Fourier series),

$$
	f(y,t) = \sum_{n = 1}^{\infty} f_n(t) \sin \frac{n \pi y}{h}
$$

The Navier-Stokes equation implies:

```{math}
:label: nsfourier
\sum_{n = 1}^{\infty} \left({\dot f}_n(t) + \frac{\nu \pi^2 n^2}{h^2}\right) \sin \frac{n \pi y}{h} = 0
```

Using 

$$
	\int_0^h dy \sin \frac{m \pi y}{h} \sin  \frac{n \pi y}{h} = \frac{h}{2} \delta_{m,n}
$$

we multiply {eq}`nsfourier` by $\sin  \frac{n \pi y}{h}$ and integrate $y$ between $[0,h]$, and we find
 
$$
	f_n(t) = c_n e^{-n^2 \pi^2 \nu t/h^2}
$$

where $c_n$ is a constant. Then 

```{math}
:label: finalexp
u(y,t) = \frac{U}{h}(h - y) + \sum_{n=0}^{\infty} c_n  e^{-n^2 \pi^2 \nu t/h^2}  \sin \frac{n \pi y}{h}
```

The final step is to set $c_n$ by satisfying the initial conditions $u(y,0) = 0$. In fact this is a bit problematic.
You could have guessed this because of the infinite acceleration our problem entails. A sign in the solution is that
we are somehow supposed to equate the static solution with $u(0,t\geq 0) = U$ with a sum over solutions that satisfy
Dirichlet conditions. There is a potential problem at $y = 0$; attempting to represent $u_p$, which has a finite
limit as $y \to 0$ with a sine series in which each term vanishes as $y \to 0$, leads to the *Gibbs phenomenon*, in which
the Fourier series does not quite converge right at $y = 0$, but rather overshoots by a finite amount.

That said, e will attempt to find $c_n$ by setting $t = 0$ above, demanding $u(y,0) = 0$, multiplying {eq}`finalexp` by
$\sin  \frac{N \pi y}{h}$, and integrating $y$ over $[0,h]$. The result is

$$
	\int_0^h dy \frac{U}{h}(h - y) \sin  \frac{N \pi y}{h} + \frac{h}{2} c_N =  \frac{h U}{N\pi} - \frac{h}{2} c_N
$$

or $c_N = - \frac{2 U}{N\pi}$, so that

```{math}
:label: finalcoeff
u(y,t) = \frac{U}{h}(h - y) - \sum_{n=0}^{\infty} \frac{2 U}{n \pi} e^{-n^2 \pi^2 \nu t/h^2}  \sin \frac{n \pi y}{h}
```

NOte that as $t \to \infty$, $u \to u_p$. In the next section we will present code that plots out the series versus the static part 
at $t = 0$, such that we can see the overshoot developing.
